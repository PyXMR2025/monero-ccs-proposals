---
layout: wip
title: SyntheticBird Cuprate Arti integration and development (2 months)
author: SyntheticBird
date: March 9, 2025
amount: 52.5
milestones:
  - name: April
    funds: 50% (26 XMR)
    done:
    status: unfinished
  - name: May and completion of Arti integration
    funds: 50% (26.5 XMR)
    done:
    status: unfinished
payouts:
  - date:
    amount:
  - date:
    amount:
---

# Who

I am [SyntheticBird](https://github.com/SyntheticBird45), Cuprate contributor.

# What

Cuprate is currently in alpha version and a lot of features are planned on the roadmap up to beta phase. One of the features present on this roadmap, and that was [originally presented when announcing Cuprate](https://github.com/Cuprate/cuprate/blob/fc9b077d946fe8b7746c45ae8b299a87b2014cbf/readme.md?plain=1#L57), is native support for Tor network. This CCS proposal intend to fulfill this milestone.

I will work for an estimated 2 months, from April to end of May, on Cuprate with the goal of implementing native Tor support into `cuprated` through the `arti-client` crate and other miscellaneous improvements.
At the end of this CCS, testers will be able to:
- Bootstrap Tor network within Cuprate or use Tor system daemon.
- Use Tor for outbound clearnet connections.
- Natively connect to onion monero nodes.
- Generate an onion service for accepting inbound Tor connections.

# Tasks

The planned set of tasks to complete can be found at this Github gist: https://gist.github.com/SyntheticBird45/4c554d3c1e7ae6f8d237d7dd49c2d2f0

It is subject to change but overall the required work can be separated into 3 categories:

### 1. Alternative network integration into P2P components.

Currently, Some P2P components have limited support for alternative network rules. This will require modifying `AddressBook`, `Connector`, `HandshakeBuilder`, `cuprate-dandelion` crate and `cuprated`'s dandelion implementation, and others to be *anonymization-network-aware*. After this work, we will define a new `NetworkZone` called `Tor` to connect to onion monero nodes.

### 2. Implementation of Arti and Tor Daemon support

Implementing `arti-client` inside `cuprated` and `cuprate-p2p{-*}`. Configurations, initialization, bootstrapping and launching onion services if requested. System tor daemon will also be supported.

### 3. Documentation

Update [Architectural book](https://architecture.cuprate.org) and [User book](https://user.cuprate.org/)

# Additional work

In the event that all guaranteed items are completed before the 2 months, I will spend my remaining time assisting (Issues, PRs and Reviews) on whatever is agreed is highest priority, or working on the following items:

- Custom Allocator support (Performance improvements for Musl based linux distributions and potentially minor improvements on other OSs)
- SOCKS5 proxy support for p2p
- Fjall database integration
- Related documentation

# Milestones

### 1. First month

26 XMR

### 2. Second Month and completion of main tasks

26.5 XMR

# Licensing

All the works completed under this CCS will be delivered to the [`Cuprate/cuprate.git`](https://github.com/Cuprate/cuprate) github repository. This work will follow the current repository licensing:
- All work inside `/binaries` is licensed under `AGPL-3.0-only`.
- The rest of the root and crates are licensed under `MIT`.

For more information about the Cuprate github organization, please [visit the organization page](https://github.com/Cuprate)

# Funding

I will be working 30 hours per week during 8 weeks at 45\$/hr - 205\$/XMR.
30×8=240 | 240×45=10800 | 10800÷205=52.5

Total: 52.5 XMR
