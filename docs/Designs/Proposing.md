---
sidebar_position: 1
---

# Proposing MXC Blocks

Docusaurus creates a **page for each blog post**, but also a **blog index page**, a **tag system**, an **RSS** feed...

## Proposing the L2 zk MXC Blocks to L1

On MXC zkEVM, the next L2 state is known immediately and deterministically at the time a block is proposed to the zkL1 contract. After a block is proposed, a series of checks are done to compute this post-L2 state:

1. Block is proposed by any proposer (permissionlessly).
2. Block level properties are checked validity by TaikoL1 contract ([proposed block intrinsic validity function](https://taiko.xyz/docs/concepts/creating-taiko-blocks/intrinsic-validity-functions#proposed-block-intrinsic-validity-function).
3. Proposed block is downloaded by a MXC Supernode, and the transaction list is parsed over and checked for validity ([transaction list intrinsic validity function](https://taiko.xyz/docs/concepts/creating-taiko-blocks/intrinsic-validity-functions#transaction-list-intrinsic-validity-function).
    - IF every transaction in the list is valid, an ordered subset of the list is created by skipping over transactions which have an invalid nonce or the sender has too little MXC balance to pay for the transaction. This ordered subset is used along with the [anchor transaction](https://taiko.xyz/docs/concepts/creating-taiko-blocks/anchor-transaction) to create a MXC L2 block.
    - IF any transaction in the list is invalid, the block is proven to be invalid.
4. MXC is the default gas to pay L2 proposers and on the top of that they need to burn a certain amount of MXC to compete for proposing blocks to L1