---
layout: cp
title: EVM Atomic Swaps Development
author: hbs
date: July 12, 2025
amount: 135 XMR
milestones:
  - name: Initial view only dApp
    funds: 81 XMR
    done: 30 November 2025
    status: finished
  - name: Swap creation and management
    funds: 54 XMR
    done: 31 January 2026
    status: finished
payouts:
  - date: 20 January 2026
    amount: 81
  - date: 6 February 2026
    amount: 54
---

# Summary

Work on ETH-XMR atomic swaps was initiated by [noot](https://github.com/AthanorLabs/atomic-swap) and partly funded by a previous [CCS](https://ccs.getmonero.org/proposals/noot-eth-xmr-atomic-swap.html) and a [MAGIC grant](https://donate.magicgrants.org/monero/projects/eth_xmr_atomic_swaps). After gaining some momentum, work on this project has stopped in 2023 and noot confirmed in a private email that she did not intend to contribute further to its development.

Since that project was halted, multiple exchanges have delisted Monero and services such as LocalMonero and Exch have shut down or are about to do so, therefore reducing the options for swaps to and from Monero. This has led to increased interest in alternate solutions already live, like [RetoSwap](https://retoswap.com/) or in the making like [Serai](https://serai.exchange/).

While those projects undoubtedly contribute to increase Monero swap liquidity, the popularity, decentralization and flexibility of EVM compatible blockchains make them ideal base environments for offering atomic swaps, especially since a functioning [base protocol](https://github.com/AthanorLabs/atomic-swap/blob/master/docs/protocol.md) has already been designed.

During the first half of 2025 I worked on re-implementing a smart contract for doing atomic swaps between Monero and the native currency of EVM blockchains. The goal was to remove the need to run a long lived dedicated local program. I wrote a Python CLI program to interact with the smart contract, this utility only needs to be run for performing specific actions, the actual swaps are fully handled on-chain. Those two components are completed and the contract has been deployed on Gnosis Chain. The Python CLI `moneroswap` can be used to interact with the contract and perform atomic swaps between xDAI and Monero. The code for this work is available on [codeberg](https://codeberg.org/moneroswap/moneroswap) under a permissive MIT license. I also presented this work at both [MoneroKon](https://monerokon.org) and [EthCC](https://www.youtube.com/watch?v=HkzqwAKx77k).

While the atomic swaps are now fully functional, the reliance on a CLI program to interact with the smart contract might still prove to be a roadblock to adoption.

This proposal aims at developing a decentralized web application (dApp) to serve as a front end for the atomic swap smart contract. The web application will only require a Web browser with an [EIP-1193](https://eips.ethereum.org/EIPS/eip-1193) compatible wallet such as Metamask, and will allow the users to interact with any MoneroSwap contract. Any user will be able to list offers, view their details and their progress towards completion. Users willing to participate will have the ability to create buy or sell offers, update their offers' parameters and take offers. For taken offers, the participants will have the ability to make the offers progress as the counterparties complete their tasks.

### About me (hbs)

I've been involved in the Monero community for several years now, contributing to the organization of the last three editions of MoneroKon in Prague. I've also contributed to small pieces related to Monero. [Support for the Nano S+ hardware wallet](https://github.com/monero-project/monero/pull/8232), Trezor [SLIP-0017 and SLIP-0013](https://github.com/satoshilabs/slips/commit/55de03357a0eb1dc3df31ce5f548ec8cc553fef2) documentation shilling Monero, I've also contributed privately to serhack multiple chapters towards the second edition of Mastering Monero unfortunately still in the making. Overall I am also a seasoned [contributor](https://github.com/hbs) to multiple open source projects. I've worked with the EVM for multiple years now, and did a presentation about [EVM development](https://www.youtube.com/watch?v=L95LjeHzTuo) at Devoxx France in 2022.

Over the beginning of 2025 I've worked on a full rewrite of EVM-Monero atomic swaps based on the existing protocol. This work is now fully functional and has been presented at EthCC and MoneroKon where it was welcomed with a lot of enthusiasm. I also delivered an improvised workshop at MoneroKon where attendees were walked through the whole process of conducting a swap. A longer version of this workshop is available in the [moneroswap repo](https://codeberg.org/moneroswap/moneroswap/src/branch/main/workshop) for *home study*.

# Motivation

The implementation I've worked on doesn't offer a GUI for doing atomic swaps, therefore the motivation for this proposal is to create a web application to make it easier for users to do atomic swaps.

# Milestones

The project has been divided into two major milestones.

## 1. Initial view only dApp

This first version of the dApp (decentralized Application) will allow to visualize the swaps being offered by a MoneroSwap smart contract and see the details of a given swap, including its progression towards completion. This initial version aims at raising the awareness about atomic swaps by making it easy to explore the space.

The dApp will be compatible with any deployment of the MoneroSwap smart contract on any EVM chain.

This dApp will be developed using [SvelteKit](https://svelte.dev/docs/kit/introduction) as a Single Page Application that can be deployed on IPFS in order to ensure decentralization and safety (via content addressing).

## 2. Adding creation and management of swaps to the dApp

This milestone is an evolution of the application created at milestone 1, it adds the possibility to create buy or sell offers, take offers and make swaps progress towards completion. This milestone aims at providing a fully functional dApp to conduct EVM-Monero atomic swaps.

After this milestone is completed, the dApp will offer the same swap management features as the Python CLI, except for advanced operations such as viewing or settings the parameters and all operations related to the funding of *funding requests*. As those advanced operations appeal to fewer users, whether they are deployers of MoneroSwap contract instances or funders of funding requests, they can require the use of the CLI.

This milestone is dependent on milestone 1.

# Licensing

The codebase will be licensed under the same permissive Open Source [MIT License](https://opensource.org/license/mit) as the existing moneroswap code.

# Amount

The estimated amount of work to complete the 2 milestones is estimated at around 60 days or 480 hours. At an hourly rate of 65 EUR, and considering the [EMA50 Euro monthly rate](https://www.investing.com/crypto/monero/xmr-eur-technical), 230.755 EUR at the time of last commit, this leads to a total of 135 XMR. The first milestone requires more work than the second one, so amount was split 3:2 between them.

- Initial view only dApp: 81 XMR
- Creation and management of swaps: 54 XMR

# Expiration date

Given the estimated time required to complete the milestones and the amount of time I can dedicate to the project, the project should complete within a 10 months window.

This CCS will expire on June 1 2026.
