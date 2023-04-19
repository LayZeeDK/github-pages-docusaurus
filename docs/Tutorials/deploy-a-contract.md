---
title: Deploy a contract
sidebar_position: 7
---
:::caution
Make sure you are using a test / throwaway wallet, to be safe. Don't ever reveal the private key of your main wallet!
:::

This guide will help you deploy a smart contract to MXC (Wannsee testnet) using Foundry.

## Prerequisites

- [Foundry](https://book.getfoundry.sh/getting-started/installation) is installed.
- You have the private key handy to an account that has Test MXC Token on MXC Wannsee (to pay the transaction fee for deploying the contract).
    - [Retrieve private key with MetaMask](https://support.metamask.io/hc/en-us/articles/360015289632-How-to-export-an-account-s-private-key#:~:text=On%20the%20account%20page%2C%20click,click%20%E2%80%9CConfirm%E2%80%9D%20to%20proceed.).
    - [Generate wallet keys with OpenSSL](https://gist.github.com/miguelmota/3793b160992b4ea0b616497b8e5aee2f).
    - [Generate wallet keys with ethereumjs-wallet](https://piyopiyo.medium.com/how-to-generate-ethereum-private-key-and-address-in-local-offline-environment-90294308593c).
- Have some Test MXC Token on MXC Wannsee:
    - First, [request Test MXC Token](/docs/Tutorials/receive-tokens) from the faucet.
    - Then, [use the bridge](/docs/Tutorials/use-the-bridge) to send the Test MXC Token to MXC Wannsee testnet.

## Steps

### Create a project with Foundry
To scafold a new foundry run:
```sh
forge init hello_foundry && cd hello_foundry
```

### Deploy the contract
:::info
Ensure that Gas is 3000gWei to avoid Error: (code: -32000, message: contract creation code storage out of gas, data: None)!
:::
Replace `YOUR_PRIVATE_KEY` below with your private key which has some Test MXC Token on MXC Wannsee testnet.

Deploy the contract located at `src/Counter.sol`.

> Note: The `--legacy` flag is needed because EIP-1559 is currently disabled on MXC, it will be re-enabled in the future.
```sh
forge create --legacy --rpc-url https://wannsee-rpc.mxc.com --private-key YOUR_PRIVATE_KEY src/Counter.sol:Counter
```

### View your contract
Paste the address from the output into the [MXC Wannsee block explorer](https://wannsee-explorer.mxc.com) and verify that the contract was deployed.
