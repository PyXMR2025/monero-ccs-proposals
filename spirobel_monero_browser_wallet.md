---
layout: wip
title: Monero Browser Wallet
date: February 26, 2025
author: Spirobel
amount: 335
milestones:
  - name: prepayment for first month
    funds: 20 XMR
    done:
    status: finished
  - name: Monero Payment Links + multi wallet syncing
    funds: 90 XMR
    done:
    status: unfinished
  - name: Monero Browser Wallet
    funds: 125 XMR
    done:
    status: unfinished
  - name: Multisig companion app + escrow library
    funds: 100 XMR
    done:
    status: unfinished
payouts:
  - date:
    amount:
  - date:
    amount:
  - date:
    amount:
  - date:
    amount:
---

# Monero Browser Wallet

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

#### implemented a Monero Browser wallet extension PoC

https://www.youtube.com/watch?app=desktop&v=4DLcsQ45zoE

https://github.com/spirobel/monerochan-city-wallet

#### wallet-rpc library

https://ccs.getmonero.org/proposals/spirobel_robust_modular_wallet_rpc.html

https://www.npmjs.com/package/@spirobel/monero-wallet-api

https://github.com/monerochan-ecosystem/monero-wallet-api

Contact: twitter.com/spirobel

## What

**Result:** Monero browser wallet, selfhostable stripe payment links alternative, multisig companion app,
accessible cross platform Monero library

The deliverable for this proposal will be:

1. A selfhostable Stripe Payment Links alternative built on
   the [monero-wallet-api library](https://github.com/monerochan-ecosystem/monero-wallet-api).
   It is necessary to have a checkout flow with real world use to establish the Wallet-Webapp
   interaction UX. The [preliminary UI work](https://x.com/spirobel/status/1871161899410440670)
   on this product has been well received.
2. The Monero browser wallet.
   The next step is the implementation of the send functionality in the library and the wallet itself.
   The second milestone contains all the UI for syncing, sending, error states and the Wallet-Webapp interaction. The extension will be published to the Chrome Web Store and the Firefox extension store.
3. A Multisig companion app that allows to split spend keys over multiple devices. This means a phone can serve as a second factor to a laptop and both devices need to be compromised to access funds. The work will make use of the [recently audited](https://ccs.getmonero.org/proposals/monero-serai-wallet-audit.html) multisig code. As a side effect it will become more accessible to build escrow and multisignature enabled apps with the underlying typescript library.

### Implementation

list of initial tasks:

- add multi wallet syncing to the library
- integration of checkout flow in the Payment Links app
- enable multi wallet background syncing in Monero Payment Links
- build Monero Payment Links transaction section and transactions tab
- calculate & display aggregate amount per wallet

- add private key management to the extension
- build indexeddb backend for output storage
- implement spend function
- add transaction history screen to the browser extension
- implement interactive checkout that will remove need to copy addresses

- add FROST dkg methods to the monero wallet api typescript library
- implement initial connection and setup in extension and multisig companion app
- handle transaction signing & display in the companion app
- implement transaction submission
- recovery from fresh scan

  this task list is not exhaustive and subject to change

## Milestones

value commitment:

The 3 deliverables outlined in the **What** section are the promised outcome of this proposal.
In addition, new functionality becomes available in the underlying library.
The Monero Payment Links product is 110, the Browser Wallet extension 125, the Multisig Companion app + lib 100, in total 335 xmr

## Why

The goal is to **remove all friction from the privacy enabled web shopping experience**. Currently most **Monero shoppers** have to copy and paste addresses from the tor browser into their wallets. This opens the door to unnecessary opsec failures, as it is easy to get confused and intimidated by long strings of random numbers.

**A core part of staying private and safe online is to compartmentalize identities.** Qubes OS made some advancements in improving the UX of this activity by coloring different windows that are tied to different identities in a unique way.

The reality is, that installing a different operating system is a large ask for the average person. At the same time we need to onboard as many people as possible to these habits, so we can operate safely in the crowd.

The other venue of attack is **using the browser for compartmentalization.** And before anybody complains: no this does not involve untrusted javascript frontend code.

There is a big difference between a browser wallet and web wallet. A web wallet is a flawed experiment that is borderline custodial, as it runs wallet code inside the context of a website. This is not to be confused with a browser wallet.
**A browser wallet runs trusted code as a compartmentalized, constrained program inside of a sandbox.**

There is a massive opportunity here to reduce friction by making it easy to separate online identities. The TOR browser currently enables the use of one separate TOR circuit for each tab. **Imagine we have one monero address per tab that is used for login and to send and receive payments.** It makes it much harder to mess up.

The potential that a browser wallet opens up goes beyond that. It opens up a new design space that means that **innovation can be modular**. The barrier to building something new is drastically lowered if you don't have to publish and distribute a wallet application to make the change that you have in mind. Users don't have to install new apps to try what you built.

One last concern that comes up is that there might be zero day exploits in the browser, as it exposes a potentially larger attack surface. This can be mitigated by making the wallet a multisignature wallet and **using a second device like an android phone or a monero seedsigner to authorize every transaction.**
This means two devices need to be compromised to capture funds, which is unlikely.
