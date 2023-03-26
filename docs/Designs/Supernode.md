---
sidebar_position: 5
---

# MXC SupernodeV2

Previous documents published about MXC [SupernodeV1](https://www.mxc.org/supernode)

In the zkEVM SupernodeV2,there are two parts to a MXC Supernode, which are connected over the engine API:
- `mxc-geth`
- `mxc-client`


## MXC geth

The [mxc-geth](https://github.com/MXCzkEVM/) repo is a fork of [taiko-geth](https://github.com/taikoxyz/taiko-geth) with some changes according to MXprotocol, it serves as an IoT Web3 platform, which needs to be coupled to a LPWAN cluster mentioned in previous chapter, like L1/L2 ethereum execution engines, it will listen to new IoT transactions broadcasted in the IoT network, executes them in EVM, and holds the latest state and database of all current IoT data and submit proofs via Zero-Knowledge.

## MXC client

The compiled binary `bin/mxc-client` is the main entrypoint which includes three sub-commands:

- `driver`: keep the IoT execution engine's chain in sync with the `MXCL1` contract, by directing the IoT [execution engine](https://ethereum.org/en/glossary/#execution-client).
- `proposer`: propose new transactions from the IoT execution engine's transaction pool to the `MXCL1` contract.
- `prover`: request ZK proofs from the zkEVM, and send transactions to prove the proposed blocks are valid or invalid.

### Driver

MXC client's driver software serves as an IoT consensus client. It will listen for new IoT blocks from the MXC layer 1 protocol contract, then direct the connected IoT execution engine to insert them into its local chain through the Engine API.

#### Engine API

Driver directs an IoT execution engine to insert new blocks or reorg the local chain through the [Engine API](https://github.com/ethereum/execution-apis/blob/main/src/engine/specification.md).

#### Chain synchronization process

> NOTE: The MXC allows a block's timestamp to be equal to its parent block's timestamp, which differs from the original Ethereum protocol. So it's fine that there are two `MXCL1.proposeBlock` transactions included in one L1 block.

Driver will inform the IoT execution engine MXC contract's latest verified IoT head, and try to let it catch up the latest verified IoT block through P2P at first. Driver will monitor the execution engine's sync progress, if it is not able to make any new sync progress in a period of time, driver will switch to insert the verified blocks to its local chain through the Engine API one by one.

After the IoT execution engine catches up the latest verified IoT head, driver will subscribe to `MXCL1.BlockProposed` events, and when a new pending block is proposed:

1. Get the corresponding `MXCL1.proposeBlock` L1 transaction.
2. Decode the txList and block metadata from the transaction's calldata.
3. Check whether the txList is valid based on the rules defined in MXC.

If the txList is **valid**:

4. Assemble a deterministic `MXCL2.anchor` transaction based on the rules defined in the protocol, and put it as the first transaction in the proposed txList.
5. Use this txList and the decoded block metadata to assemble a deterministic IoT block.
6. Direct IoT execution engine to insert this assembled block and set it as the current canonical chain's head via the Engine API.

If the txList is **invalid**:

4. Create a `MXCL2.invalidateBlock` transaction and then assemble an IoT block only including this transaction.
5. Direct the IoT execution engine to insert this block, but does not set it as the chain's head via the Engine API.

> NOTE: For more detailed information about: block metadata, please see `5.2.2 Block Metadata` in the white paper.

> NOTE: For more detailed information about txList validation rules, please see `5.3.1 Validation` in the white paper.

> NOTE: For more detailed information about the `MXCL2.anchor` transaction and proposed block's determination, please see `5.4.1 Construction of Anchor Transactions` in the white paper.

### Proposer

MXC client's proposer software will fetch pending transactions in an IoT execution engine's mempool intervally, then try to propose them to the MXC layer 1 protocol contract.

#### Proposing strategy

Since tokenomics have not been fully implemented in the MXC zkEVM, the current proposing strategy is simply based on time interval.

In the future it will use the burn and PoS concensus to propose the blocks.

#### Proposing process

Proposing a block involves a few steps:

1. Fetch the pending transactions from the IoT execution engine through the `txpool_content` RPC method.
2. If there are too many pending transactions in the IoT execution engine, split them into several smaller txLists. This is because the MXC restricts the max size of each proposed txList.
3. Commit hashes of the txLists by sending `MXCL1.commitBlock` transactions to L1.
4. Wait for `MXCData.Config.commitConfirmations` (currently `0`) L1 blocks confirmations.
5. Propose all splitted txLists by sending `MXCL1.proposeBlock` transactions.

### Prover

#### Proving strategy

Since tokenomics have not been fully implemented in the MXC zkEVM, the prover software currently proves all proposed blocks.

#### Proving process

When a new block is proposed:

1. Get the `MXCL1.proposeBlock` L1 transaction calldata, decode it, and validate the txList. Just like what the `driver` software does.
2. Wait until the corresponding block is inserted by the IoT execution engine's `driver` software.
3. Generate a ZK proof for that block asynchronously.

If the proposed block has a valid txList:

4. Generate the merkel proof of the block's `MXCL2.anchor` transaction to prove its existence in the `block.txRoot`'s [MPT](https://ethereum.org/en/developers/docs/data-structures-and-encoding/patricia-merkle-trie/), and also this transaction receipt's merkel proof in the `block.receiptRoot`'s MPT from the IoT execution engine.
5. Submit the `MXCL2.anchor` transaction's RLP encoded bytes, its receipt's RLP encoded bytes, generated merkel proofs, and ZK proof to prove this block **valid**, by sending a `MXCL1.proveBlock` transaction.

If the proposed block has an invalid txList:

4. Generate the merkel proof of the block's `MXCL2.invalidateBlock` transaction receipt to prove its existence in the `block.receiptRoot`'s MPT from the IoT execution engine.
5. Submit the `MXCL2.invalidateBlock` transaction receipt's RLP encoded bytes, generated merkel proof, and ZK proof to prove this block **invalid**, by sending a `MXCL1.proveBlockInvalid` transaction.

> NOTE: For more information about why we need these merkel proofs when proving, please see `5.5 Proving Blocks` in the white paper.