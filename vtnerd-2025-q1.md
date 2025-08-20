---
layout: wip
title: vtnerd full-time 2025 q1/q2
author: Lee Clagett (vtnerd)
date: February 21, 2025
amount: 134.37 XMR
milestones:
  - name: Month 1 (160 hours)
    funds: 44.79 XMR
    done: 01 April 2025
    status: finished
  - name: Month 2 (320 hours)
    funds: 44.79 XMR
    done: 13 May 2025
    status: finished
  - name: Month 3 (480 hours)
    funds: 44.79
    done: 22 July 2025
    status: finished
payouts:
  - date: 25 April 2025
    amount: 44.79
  - date:
    amount:
  - date:
    amount:
---

3-Months full-time software development on monero "core" components in 2025 q1/q2.

## What
Work primarily on `monerod`, `wallet`, and `monero-lws`. Some of the work to be attempted or investigated:
  - Code reviews of monero core PRs
  - monerod/monero-lws bug fixes and HackerOne mitigations as they arrive
  - Keep existing PRs up-to-date:
    - New Serialization routine
    - Change from raw pointers to weak_ptrs in levin code
    - Socks v5
    - P2P SSL Support
    - Updating levin callbacks to C++14 moves
    - Embargo timeout fix
  - Find (possible) memory leak in weak_ptr PR
  - Complete work necessary to merge [DANE/TLSA in wallet2/epee](https://github.com/vtnerd/monero/tree/improve/dane_tlsa).
  - Adding trust-on-first-use support to wallet2
  - Add msgpack support to monerod-ZMQ (requires merging of new serialization system)
  - `monero-lws` work:
    - Determine a “push” interface for LWS clients (instead of existing poll interface)
    - Complete LWS frontend (using `wallet_api.h` as interface) so that wallets can begin using LWS API easily. This is separate from woodser et al working on LWS API within `wallet2` which may be deprecated.
    - Add a new utility (to LWS-frontend) that accepts a spend key to report balance+spent transactions of wallet (requested via Github Issues). This will help verify accuracy of LWS endpoints
    - Update LWS spec and implementation to support new "carrot" features (view-balance key, etc)
    - Update LWS backend to work with fcmp++ experimental branch
    - Add a "scale" factor to remote scanning load balancing - send more accounts to systems with faster single thread performance 
    - Add 64-bit ed25519 code for faster arm64 scanning
    - Provide official LWS docker-image
    - Provide pre-built binaries
    - (Unlikely) - reproducible builds so community members can verify+sign the binary hashes

There is intentionally more work than time allows - to ensure there is always something to work on in the proposal.

## Who

Lee Clagett (vtnerd). I've [had](https://ccs.getmonero.org/proposals/vtnerd-tor-tx-broadcasting.html) [five](https://ccs.getmonero.org/proposals/vtnerd-2020-q4.html) [CCS](https://ccs.getmonero.org/proposals/vtnerd-2021-q1.html), [proposals](https://ccs.getmonero.org/proposals/vtnerd-2023-q3.html) ([last one](https://ccs.getmonero.org/proposals/vtnerd-2024-q3.html)), and [one Magic Grant](https://monerofund.org/projects/Q1Q2_2024_dev_vtnerd).

Some of my biggest features in monero core repo are [Dandelion++](https://github.com/monero-project/monero/pull/6314), [adding supercop ASM speedups to wallet code](https://github.com/monero-project/monero/pull/6337), [ZeroMQ Pub Support for new blocks and transactions](https://github.com/monero-project/monero/pull/6418), and [SSL support to p2p](https://github.com/monero-project/monero/pull/8996).

I've also made a functional LWS wallet scanner under CCS/Magic - which now has a MyMonero compatible REST API (now fully non-blocking to support more responses per thread), admin REST API, LMDB storage, subaddress support, webhook/zmq/rmq publishing (new receives, spends, and accounts), multi-machine scanning with (primitive) load-balancing, and an untrusted daemon mode that verifies PoW is valid (whereas normal wallets trust `monerod` responses entirely).

## Proposal

Work on the various tasks outlined above for 40 hours/week over the next 3 months after potential funding. I already use time-tracking software for work; if the hours dip in a given month unexpectedly, the update/milestone will be at the completion of the hours listed above.

The funds were calculated with 65 USD/hour with ~232.20 USD/XMR which is the 14-day exponential moving average on Kraken through 2025/02/21.
