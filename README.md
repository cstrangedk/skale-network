<div align="center">
  <img src="https://uploads-ssl.webflow.com/5be05ae542686c4ebf192462/5be2f8beb08f6d0fbd2ea797_Skale_Logo_Blue-p-500.png"><br><br>
</div>

SKALE is a decentralized proof-of-stake network of high-throughput low-latency elastic sidechains that run in parallel with the Ethereum blockchain. Skale enables you to run your dApp with a better user experience without trading-off security. 

[![](http://img.youtube.com/vi/Twe_hPFGlbY/0.jpg)](http://www.youtube.com/watch?v=Twe_hPFGlbY "Explainer")


<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  

- [SKALE'S Mission](mission)
- [SKALE Demos](#skale-demos)
- [Getting Started with SKALE](#getting-started-with-skale)
- [Architecture](#architecture)
  - [Sidechains(S-chains)](#sidechainss-chains)
  - [SKALE-d](#skale-d)
  - [SKALE Manager](#skale-manager)
  - [Docker Containers](#docker-containers)
  - [Validators](#validators)
- [Additional Features](#additional-features)
- [Contributing](#contributing)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

[![Discord](https://img.shields.io/badge/chat-discord.chat-yellow.svg?style=flat)](https://discord.gg/mtAy3cv)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)


## SKALE'S Mission 
Our mission is to empower dApps. We believe in a decentralized world where value accrues more equitably and we are building infrastructure to support a thriving dApp ecosystem. 

## SKALE Demos 

We have built several demo dApps that run on Skale. Play around with them and see how quickly transactions are confirmed. 

https://github.com/skalenetwork/skale-demo

## Getting Started with SKALE

We want to make it easy to get started using SKALE which is why we support Truffle and your favorite Web3 wallets.

We are working on a CLI tool for developers to request a SKALE chain, but until then we have an interim process in place.

- If you are a developer, follow the instructions in [SChainSetup](SChainSetup.md) to learn how to migrate and deploy your smart contracts to the SKALE chain 

- If you are a validator, follow the instructions in [ValidatorSetup](ValidatorSetup.md) to set-up a SKALE node 


## Architecture

The SKALE network is comprised of sidechains(s-chains), validator nodes, the Skale Manager, and the Skale daemon (Skale-d). All nodes operate in a containerized architecture to enable enterprise grade performance and optionality. 
Architecture diagram (update?): https://medium.com/skale/the-skale-tech-stack-5beb025acb6a

### Sidechains(S-chains)

A S-chain is simply a blockchain that exists alongside the Ethereum mainnet and runs inside of a Docker container. S-chains are elastic because they come in different sizes depending on the needs of the dApp. S-chains operate within a daemon named SKALED. 

### Validator Nodes

The SKALE network is secured by a group of independent validators. These operators can run one or multiple nodes. Each validator node must stake SKALE tokens to participate in the network. Good behavior is incentivized through bounty rewards and bad behavior is disencentivized through slashing.

We will provide more information on validator economics before launching the Incentivized DevNet. If you'd like to participate in the Incentivized DevNet, please fill out [this form] (https://skale.network/validators-signup)

### Docker Containers 
A validator node consists of, at a minimum, the following 3 Docker containers:
    - MySQL
    - SLA
    - BountySKALE Admin

If a validator node is randomly selected to participate in a S-chain, the following Docker containers are instantiated:
    - Interchain Messaging (IMA)
    - S-chain 

You can read more about the Docker containers we use in our [developer portal](https://skale.network/validators/skale-node#list-of-skale-containers)

### SKALE Manager

SKALE Manager is a series of smart contracts on the Ethereum mainnet. These smart contracts orchestrate the Skale network. Skale Manager is responsible for the following activities:
  - node registration
  - node operation
  - bounty rewards for validators
  - S-chain creation
  - S-chain destruction

### SKALE-d

Each node runs SKALE-d, or Skale-daemon, which is fully compatible with Ethereum. It is a fork of Aleth, Ethereum's C++ client (shout out and thank you to the Aleth team). SKALE-d uses an improved consensus mechanism and libBLS to enable higher through-put and lower-latency. You can read more about SKALE's consensus and BLS rollup in our developer portal here: 


## Additional Features

We have modified the EVM to allow for much larger file storage capabilities. Additionally, we have built a mechanism for relaying and executing messages between sidechains. 
 
    - File Storage
    - Interchain Messaging (IMA)



## Contributing

We would love to get code contributions from our community and are grateful for even the smallest contibutions. 

Please see our [Contributions Guide] (insert link) for some guidelines to follow.









