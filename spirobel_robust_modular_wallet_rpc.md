---
layout: wip
title: Robust and modular wallet-rpc library
date: Sep 10, 2024
author: Spirobel
amount: 100
milestones:
  - name: Deved + prepayment for first month
    funds: 20 XMR
    done: 9 October 2024
    status: finished
  - name: First month
    funds: 30 XMR
    done:
    status: unfinished
  - name: Second month + value commitment
    funds: 50 XMR
    done:
    status: unfinished
payouts:
  - date: 16 October 2024
    amount: 20
  - date:
    amount:
  - date:
    amount:
---

# Robust and modular wallet-rpc library

## Who

**Spirobel**

References:

#### found and reported a "pay what you want" vulnerability in AcceptXMR

https://x.com/spirobel/status/1672479215512588288

https://github.com/busyboredom/acceptxmr/issues/64

#### open sourced a Patreon like tool for Monero

https://x.com/spirobel/status/1595949928634667008

https://github.com/spirobel/monero-discourse-subscriptions

#### open sourced a merchant focused wallet-rpc

https://x.com/spirobel/status/1596299822516285440

https://github.com/spirobel/monerochan-merchant-rpc


#### implemented a Monero Browser wallet extension

https://www.youtube.com/watch?app=desktop&v=4DLcsQ45zoE

Contact: twitter.com/spirobel

## What

Result: A robust and modular wallet-rpc library, implemented in Rust with WebAssembly (WASM) as the primary target. This library aims to provide a flexible foundation for Monero wallet functionality. The deliverable for this proposal will be:

1. the first part of the wallet-rpc library that can sync transactions and works reliably with remote nodes.
2. A checkout flow built with this library. This is meant to be used, not just to demonstrate the features.
3. Detailed documentation for the library, the relationship between nodes and wallets during the syncing process and a guide on how to use this to implement monero payment gateways.

### Implementation

list of initial tasks:

- create function to turn address and private viewkey into viewpair
- create function to scan transaction with sub functions
- verify that there is no timelock present
- calculate transaction amount
- clarify responsibility of burning bug prevention for the caller

- implement transaction fetching and storage
- implement burning bug prevention in the checkout flow
- write unit tests, document and publish the library
- implement UI for the checkout flow

this task list is not exhaustive and subject to change

## Why

As discussed as far back as two years ago: https://github.com/seraphis-migration/strategy/issues/2
The wallet2 Monero library is a 15k lines CPP file. The official monero repo does not contain a deliverable that is easily linkable from other programs. Every project that is a wallet or contains wallet-like functionality (payment processors, hardware wallets, point of sale terminals) needs to implement its own wrapper to expose a C ABI.

This results in collectively wasted hours and headaches. It increases supply chain risk and makes building things with Monero harder. As a result, projects get more expensive, take longer or don't happen at all.

This library aims to counteract the issues and limitations of wallet2.cpp by directly targeting wasm.
Using wasm as the main target means that this library is forced to be implemented in a way that meets the expectations outlined here: https://github.com/seraphis-migration/strategy/issues/1

The benefits of this approach:

### 1. It will be easily linkable

WASM is a very constrained target. There is no garbage collection and multi threading. Getting code to run there means having to write it in a way that is easy to interact with from any language and in any environment.

### 2. It will be more robust

The current monero wallet-rpc is at times unresponsive, because its concurrency mixes the responses of the local rpc with the network interacting with the node. More details in the [monero-playground repository](https://github.com/spirobel/monero-playground). The WASM target constraints ensure that this library decouples the concurrency and networking from the wallet code. The result will be more robust.

### 3. It will be more flexible and not tied to any platform / target

Wallet code deals with the most sensitive data. It should not have unnecessary dependencies or bloat. To give a practical example: monero currently vendors a 4000 lines of code [logging library](https://github.com/monero-project/monero/blob/master/external/easylogging%2B%2B/easylogging%2B%2B.cc) that introduces a dependency on signals. The WASM target constraint means that things like that can't and wont be introduced into this library.

## Milestones and Timeline

value commitment:

The 3 deliverables outlined in the **What** section are the promised outcome of this proposal. Any time left over from the time commitment will be used to further advance the road map. The value commitment is due for the milestone of the second month.

time commitment:

- 100 hours per month for two months (100 hours total)
- Compensation: 50 XMR per month (100 XMR total)
- Total compensation: 100 XMR

## Future Roadmap

The next step on the road map is to add transaction building and signing functionality to the library and migrate [the browser wallet](https://www.youtube.com/watch?v=4DLcsQ45zoE) to it.

My endgame is to **remove all friction from the privacy enabled web shopping experience**. Currently most **Monero shoppers** have to copy and paste addresses from the tor browser into their wallets. This opens the door to unnecessary opsec failures, as it is easy to get confused and intimidated by long strings of random numbers.

**A core part of staying private and safe online is to compartmentalize identities.** Qubes OS made some advancements in improving the UX of this activity by coloring different windows that are tied to different identities in a unique way.

The reality is, that installing a different operating system is a large ask for the average person. At the same time we need to onboard as many people as possible to these habits, so we can operate safely in the crowd.

The other venue of attack is **using the browser for compartimentalization.** And before anybody complains: no this does not involve untrusted javascript frontend code.

There is a big difference between a browser wallet and web wallet. A web wallet is a flawed experiment that is borderline custodial, as it runs wallet code inside the context of a website. This is not to be confused with a browser wallet.
**A browser wallet runs trusted code as a compartmentalized, constrained program inside of a sandbox.**

There is a massive opportunity here to reduce friction by making it easy to separate online identities. The TOR browser currently enables the use of one separate TOR circuit for each tab. **Imagine we have one monero address per tab that is used for login and to send and receive payments.** It makes it much harder to mess up.

One last concern that comes up is that there might be zero day exploits in the browser, as it exposes a potentially larger attack surface. This can be mitigated by making the wallet a multisignature wallet and **using a second device like an android phone or a monero seedsigner to authorize every transaction.**
This means two devices need to be compromised to capture funds, which is unlikely.
