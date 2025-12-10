---
layout: fr
title: vtnerd full-time 2025 q4
author: Lee Clagett (vtnerd)
date: November 29, 2025
amount: 75.73 XMR
milestones:
  - name: Month 1 (160 hours)
    funds: 25.24 XMR
    done:
    status: unfinished
  - name: Month 2 (320 hours)
    funds: 25.24 XMR
    done:
    status: unfinished
  - name: Month 3 (480 hours)
    funds: 25.25
    done:
    status: unfinished
payouts:
  - date:
    amount:
  - date:
    amount:
  - date:
    amount:
---

3-Months full-time software development on monero components in 2025 q4

## What
Work primarily on `monerod`, `wallet2`, `monero-lws`, and `lwsf`. Some of the work to be attempted or investigated:
  - Code reviews of monero core PRs
  - monerod/monero-lws/lwsf bug fixes and HackerOne mitigations as they arrive
  - Keep existing PRs up-to-date:
    - New Serialization routine
    - Change from raw pointers to weak_ptrs in levin code
    - Socks v5
    - P2P SSL Support
    - Updating levin callbacks to C++14 moves
  - Find (possible) memory leak in weak_ptr PR
  - Complete work necessary to merge [DANE/TLSA in wallet2/epee](https://github.com/vtnerd/monero/tree/improve/dane_tlsa).
  - Adding trust-on-first-use support to wallet2
  - Add msgpack (or cbor) support to monerod-ZMQ
  - `monero-lws` work:
    - Complete support for new draft/PR of `/import_wallet_request` with lookahead (already in-progress)
    - Determine a “push” interface for LWS clients (instead of existing poll interface)
    - Update LWS spec and implementation to support new "carrot" features (view-balance key, etc). [Note this is basically complete - only an interface for curve tree spending is needed]
    - Complete LWS backend to work with fcmp++ experimental branch (this is nearly complete, minus the spending portion)
    - Add a "scale" factor to remote scanning load balancing - send more accounts to systems with faster single thread performance 
    - Add 64-bit ed25519 code for faster arm64 scanning. Latest "Supercop" has unverified neon implementation.
    - Provide pre-built binaries
    - (Unlikely) - reproducible builds so community members can verify+sign the binary hashes
    - Add msgpack (or cbor) support to ZMQ-REP and ZMQ-PUB (faster scanning)
  - `lwsf` (LWSF-frontend) work:
    - Implement fee estimation
    - Add carrot/fcmp++ legacy + view-balance-key support (receive and spend). View-incoming will not be used by lwsf.
    - Fix subaddress handling:
      - New wallets will have less lookahead, as the frontend should know about every subaddress
      - Imported wallets will use the draft/PR lookahead spec
    - Complete remainder of functions, EXCEPT for multisig and a few other non-critical functions.
      - The remainder of work is primarily support for hardware devices
    - Better support for handling (dropping) "dust" outputs during "sweeps"

There is intentionally more work than time allows - to ensure there is always something to work on in the proposal.

## Who

Lee Clagett (vtnerd). [I've](https://ccs.getmonero.org/proposals/vtnerd-2025-q1.html) [had](https://ccs.getmonero.org/proposals/vtnerd-tor-tx-broadcasting.html) [seven](https://ccs.getmonero.org/proposals/vtnerd-2020-q4.html) [CCS](https://ccs.getmonero.org/proposals/vtnerd-2021-q1.html), [proposals](https://ccs.getmonero.org/proposals/vtnerd-2023-q3.html) ([6](https://ccs.getmonero.org/proposals/vtnerd-2024-q3.html) [7](https://ccs.getmonero.org/proposals/vtnerd-2025-q4.html)), and [one Magic Grant](https://monerofund.org/projects/Q1Q2_2024_dev_vtnerd).

Some of my biggest features in monero core repo are [Dandelion++](https://github.com/monero-project/monero/pull/6314), [adding supercop ASM speedups to wallet code](https://github.com/monero-project/monero/pull/6337), [ZeroMQ Pub Support for new blocks and transactions](https://github.com/monero-project/monero/pull/6418), and [SSL support to p2p](https://github.com/monero-project/monero/pull/8996).

Most recently I've created `lwsf` - a client library for the LWS protocol that implements the `monero-gui` C++ interface. This library powers the new [skylight wallet](https://skylight.magicgrants.org), and is now in real-world use.

I've also made a functional LWS wallet scanner - which the lwsf/skylight communicates with - which is fully non-blocking to support more responses per thread, admin REST API, LMDB storage, subaddress support, webhook/zmq/rmq publishing (new receives, spends, and accounts), multi-machine scanning with (primitive) load-balancing, and an untrusted daemon mode that verifies PoW is valid (whereas normal wallets trust `monerod` responses entirely).

## Proposal

Work on the various tasks outlined above for 40 hours/week over the next 3 months after potential funding. I already use time-tracking software for work; if the hours dip in a given month unexpectedly, the update/milestone will be at the completion of the hours listed above.

The funds were calculated with 65 USD/hour with ~412.00 USD/XMR which is the 14-day exponential moving average on Kraken through 2025/11/29.
