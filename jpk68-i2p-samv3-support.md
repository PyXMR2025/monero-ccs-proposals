---
layout: wip
title: "I2P SAMv3 support"
author: jpk68
date: March 7, 2026
amount: 50
milestones:
  - name: Research and prototype, core SAMv3 implementation
    funds: 25
    done: 28 June 2026
    status: finished
  - name: GUI integration and docs
    funds: 10
    done:
    status: unfinished
  - name: Beta testing and review
    funds: 15
    done:
    status: unfinished
payouts:
  - date: 9 July 2026
    amount: 25
  - date:
    amount:
  - date:
    amount:
---

_Note: this proposal has been funded entirely using funds from a [declined bounty](https://bounties.monero.social/posts/32/140-219m-i2p-baked-into-the-monero-gui)_

## What

Monero's core software currently has very limited support for the I2P network, which is through the use of SOCKS proxies. This has a number of [disadvantages](https://i2p.net/en/docs/api/socks/) in terms of both security and ease of use.

I propose to work on improving and modernizing I2P support in Monero through the following:

- Implementing I2P's SAMv3 protocol in `monerod`
- Adding functionality to the GUI for configuring I2P connections
- Contributing to and improving upon existing documentation for anonymity networks in Monero
- Attending community/development meetings
- Other tasks mentioned below

The scope of tasks/effort needed is very similar to that which has already been discussed [here](https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/454).

## Milestones

### Milestone 1: Research and prototype, core SAMv3 implementation (25 XMR)

- Study SAMv3 docs, evaluate existing protocol implementations
- Decide on ACCEPT vs FORWARD for incoming connections, permanent vs transient destinations
- Full SAMv3 integration in addition to the SOCKS proxy path
- Support for both Java I2P and i2pd routers
- Handle external router start/stop/restart gracefully
- Sane default tunnel configuration per I2P expert guidance
- Deliver a working PR with SAMv3, functional for CLI usage, with unit tests as per guidelines

### Milestone 2: GUI integration and docs (10 XMR)

- Toggle to enable/configure I2P connections in the GUI; indicator for router status (up/down)
- Configuration options exposed in GUI
- Rewritten docs: new install (i2pd + Java I2P), migration from i2p-zero, migration of existing setups
- Verify and update seed node list

### Milestone 3: Beta testing and review (15 XMR)

- Announce and recruit beta testers
- Address community feedback from testing
- Pass code review requirements
- Address all PR review comments
- PR has loose approval, and is ready to be merged into `master` branch

## Who

I'm a self-taught programmer who has been interested in Monero and similar projects for quite some time now. I have been active in development discussion/happenings on IRC/Matrix for several months, and have also contributed a number of merged PRs (albeit mostly small ones) to core Monero repos as well as Monero-adjacent community projects. Here are some examples:

- [Added I2P support to P2Pool](https://github.com/SChernykh/p2pool/commit/941e5114d8964ac4c552c81234f20ae2364889aa)
- [Added IPv6 support to the ZMQ interface in `monerod`](https://github.com/monero-project/monero/commit/d380a6ac85fb96c7edc2d967c5c80d297a3aadc6)
- Contributed documentation fixes and improvements to P2Pool, Monfluo, and monero-lws ([1](https://github.com/SChernykh/p2pool/commit/f8310f27b86ff9cc72ae3062ba424d8fb6269560), [2](https://github.com/SChernykh/p2pool/commit/6e7311a83ce1706f09eab061c8d5235477990572), [3](https://codeberg.org/Monfluo/monfluo-android/commits/branch/master/search?q=after%3A2022-09-04%2C+before%3A2026-03-08%2C+author%3Ajpk68%40tutanota.com), [4](https://github.com/vtnerd/monero-lws/commit/fe3f4099bbdb6ada379708ef9eea752bad3ace60))

## Funding

I am requesting a total of 50 XMR for all milestones combined, with the corresponding amount to be paid out upon the completion of each individual milestone.
