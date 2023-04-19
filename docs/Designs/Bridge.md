---
sidebar_position: 4
---

# Bridge to L1/L2

Bridges are foundational for cross-chain users and applications. There are already Layer-2s like Arbiturm and Taiko that provides better user experiences than ETH. Users might come to another application specific chain, such as MXC (a ZK-rollup IoT focused). To do this, they need to bridge funds over. Notoriously, bridging has been a dangerous operation. How do you make sure that this bridge is secure?

Let's explain bridging on MXC. We will answer the following questions:

- What is the difference between MXC bridge and Taiko Bridge
- What is the MXC bridge dapp?
- What if I want to use ETH on MXC zkEVM?

MXC's innovative bridging design enhances the interconnectivity of the Ethereum Virtual Machine (EVM) chains, providing a robust framework for the creation of diverse applications on zkEVM. This design, furthermore, facilitates the seamless integration of MXC stable coins across all EVM chains. Consequently, MXC is well-positioned to facilitate the growth of the decentralized finance (DeFi) space by enabling the development of new, innovative applications on its cutting-edge platform.

## Bridging different EVMs

MXC's bridge design is poised to revolutionize the DeFi ecosystem by enabling seamless transactions on its cutting-edge platform. Specifically, this design empowers users of IoT sensors and NFTs to seamlessly transact using MXC tokens without the need for ETH. To achieve this, the Arbitrum version of MXC will serve as the default gas fee on the zkEVM chain, which fosters a more streamlined user experience.

Furthermore, the [Taiko bridge](https://taiko.xyz/docs/concepts/bridging/cross-chain-messaging) has provided a detailed outline of its cross-chain messaging framework, which bridges ETH to the chain and leverages it as the default gas fee. This innovative design serves to elevate user experiences on Ethereum by enabling better transaction throughput and enhanced interoperability.

## Revolutionary IoT Bridge

The bridge, a technological masterpiece, comprises a set of intelligent contracts and a frontend web app that leverages cutting-edge technology to enable the seamless transfer of testnet MXC and ERC-20 tokens between Arbitrum and MXC zkEVM. This is a remarkable feat that highlights the advanced capabilities of zkEVM, particularly its signal service, which can be utilized to develop bridges with ease.

It is worth noting that this bridge is just one of the many possibilities built on top of zkEVM, and it serves as a testament to the platform's immense potential. In fact, anyone can leverage the signal service to build bridges, which underscores the flexibility and scalability of this innovative platform. If you're curious about the bridge, you can explore its features and functionalities by [trying it out yourself](https://wannsee).


## How to bridge ETH

Even though ETH is not the default gas fee in MXC zkEVM, there is still a possibility to bridge and use ETH on the platform. This is made possible by the existence of Wrapped ETH [(WETH)](https://arbiscan.io/token/0x82af49447d8a07e3bd95bd0d56f35241523fbab1) in the Arbitrum chain, which can be effortlessly ported to MXC SupernodeV2 using the bridge.

Furthermore, it is essential to note that all other native chain tokens wrapped in EVM chains can be easily ported to MXC zkEVM to enhance interactions and streamline transactions on the platform. This functionality is critical in providing users with more options and greater flexibility, ultimately enhancing their overall user experience.
