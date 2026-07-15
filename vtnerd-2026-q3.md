---
layout: wip
title: vtnerd Full-time 2026 Q3
author: Lee Clagett (vtnerd)
date: July 9, 2026
amount: 97.06 XMR
milestones:
  - name: Month 1 (160 hours)
    funds: 32.35 XMR
    done:
    status: unfinished
  - name: Month 2 (320 hours)
    funds: 32.35 XMR
    done:
    status: unfinished
  - name: Month 3 (480 hours)
    funds: 32.36 XMR
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

3-Months full-time software development on monero components in 2026 q3

## What
Work primarily on `monerod`, `wallet2`, `monero-lws`, `lwsf`, and `fhse`. Some of the work to be attempted or investigated:
  - Code reviews of monero core PRs
  - monerod/monero-lws/lwsf bug fixes and HackerOne mitigations as they arrive
  - Investigate removing "practical" limit on block sizes
    - This will primarily be continuing the [GH issue](https://github.com/monero-project/monero/issues/10782), and continuing the serialization PRs
      - Modifying existing serialization code to remove the "hard" 16,383 tx limit is possible, but the "soft" 8,190 tx limit on pruned blocks is harder to remove
    - Other projects appear to just use working memory; if the block exceeds working memory of the machine, it just hard fails
  - Add cbor support to ZMQ REP/REQ sockets 
  - Keep existing PRs up-to-date:
    - New Serialization routine
    - Change from raw pointers to weak_ptrs in levin code
    - P2P SSL Support
    - Updating levin callbacks to C++14 moves
    - Add cbor support to monerod-ZMQ PUB/SUB
  - Find (possible) memory leak in weak_ptr PR
  - Complete work necessary to merge [DANE/TLSA in wallet2/epee](https://github.com/vtnerd/monero/tree/improve/dane_tlsa).
  - Adding trust-on-first-use support to wallet2
  - `monero-lws` work:
    - Add a “quick-sync” more where the client can sync from a specific height that is _not_ the wallet creation height
      - This is trickier than it first appears due to reorgs
    - Finish 1.0 release/tag
      - Branch and signing keys are done, just awaiting more testing
      - GPG signing key is ready, just needs distribution
    - Update LWS spec and implementation to support new "carrot" features (view-balance key, etc).
      - LWS draft PR supports view-balance keys, but a spec needs to be written and posted.
    - Keep LWS backend synced with fcmp++ experimental branch
       - May need to change the draft spec for fcmp++ curve trees
    - Add a "scale" factor to remote scanning load balancing - send more accounts to systems with faster single thread performance 
    - Add 64-bit ed25519 code for faster arm64 scanning. Latest "Supercop" has unverified neon implementation.
      - This may get shelved as fcmp++ looms.
    - (Unlikely) - reproducible builds so community members can verify+sign the binary hashes
  - `lwsf` (LWSF-frontend) work:
    - Add "push" updates to Skylight wallet:
      - Add `on_refresh` callbacks to `monero_c` fork
      - Add `on_refresh` dart hooks to `monero_c`
      - Update Skylight to let `lwsf`/`wallet2` handle refreshing
      - Hopefully upstream maintainers accept! - a LWS server configured with ZMQ PUB/SUB gets nearly immediate update in wallet UI
    - Add a “quick-sync” more where the client can sync from a specific height that is _not_ the creation height
    - Implement fee estimation (may skip until fcmp++, much easier)
    - Add carrot/fcmp++ view-balance-key support (receive and spend). View-incoming will not be used by lwsf.
      - legacy keys and fcmp++ are verified as working
      - update fcmp++ draft pr to match latest changes
      - waiting on monero core to decide how to handle carrot wallets - polyseed? some other thing?
    - Complete remainder of functions, EXCEPT for multisig and a few other non-critical functions.
      - The remainder of work is primarily support for hardware devices
    - Better support for handling (dropping) "dust" outputs during "sweeps"
    - Identify + fix bug with double spend and pending transactions
  - [FHSE library](https://github.com/vtnerd/fhse)
    - Investigate NFC FIDO2 hmac-secret support on iOS and Android
    - Create dart/flutter bindings in the hope that Cake and/or Skylight will incorporate the lib
    - Investigate incorporating into [lwcli](https://github.com/cifro-codes/lwcli) for testing feasibility. This is easier than incorporating into flutter, which requires dart bindings, and separate FIDO2 for mobile
    - Perhaps Skylight will accept this library? Will look into getting it working on non-mobile platforms at the least.
    - Adoption is likely stalled until carrot/jamtis as recovery process is easier
       - Plenty of time to get the NFC stuff working!

There is intentionally more work than time allows - to ensure there is always something to work on in the proposal.

## Who

Lee Clagett (vtnerd). [I've](https://ccs.getmonero.org/proposals/vtnerd-2025-q1.html) [had](https://ccs.getmonero.org/proposals/vtnerd-tor-tx-broadcasting.html) [nine](https://ccs.getmonero.org/proposals/vtnerd-2020-q4.html) [CCS](https://ccs.getmonero.org/proposals/vtnerd-2021-q1.html), [proposals](https://ccs.getmonero.org/proposals/vtnerd-2023-q3.html) ([6](https://ccs.getmonero.org/proposals/vtnerd-2024-q3.html) [7](https://ccs.getmonero.org/proposals/vtnerd-2025-q3.html), [8](https://ccs.getmonero.org/proposals/vtnerd-2025-q4.html), and [9](https://ccs.getmonero.org/proposals/vtnerd-2026-q2.html)), and [one Magic Grant](https://monerofund.org/projects/Q1Q2_2024_dev_vtnerd).

Some of my biggest features in monero core repo are [Dandelion++](https://github.com/monero-project/monero/pull/6314), [adding supercop ASM speedups to wallet code](https://github.com/monero-project/monero/pull/6337), [ZeroMQ Pub Support for new blocks and transactions](https://github.com/monero-project/monero/pull/6418), and [SSL support to p2p](https://github.com/monero-project/monero/pull/8996).

I've created `lwsf` - a client library for the LWS protocol that implements the `monero-gui` C++ interface. This library powers the new [skylight wallet](https://skylight.magicgrants.org), and is now in real-world use. This library also supports a [websocket `/feed`](https://github.com/vtnerd/lwsf/tree/update/feed) from the [server](https://github.com/vtnerd/monero-lws/pull/237) such that real-time updates to a wallet are now possible (as opposed to polling/delayed notificaiton in all others). 

I’ve also created a [lib for encrypted files with FIDO2 keys](https://github.com/vtnerd/fhse). The objective is for wallets to opt-in to FIDO2 wallet encryption (instead of password only protection). This may have to wait for carrot/fcmp++, as recovery can be made easier.

I've also made a functional LWS wallet scanner - which the lwsf/skylight communicates with - which is fully non-blocking to support more responses per thread, admin REST API, LMDB storage, subaddress support, webhook/zmq/rmq publishing (new receives, spends, and accounts), multi-machine scanning with (primitive) load-balancing, and an untrusted daemon mode that verifies PoW is valid (whereas normal wallets trust `monerod` responses entirely).

## Proposal

Work on the various tasks outlined above for 40 hours/week over the next 3 months after potential funding. I already use time-tracking software for work; if the hours dip in a given month unexpectedly, the update/milestone will be at the completion of the hours listed above.

The funds were calculated with 65 USD/hour with ~321.45 USD/XMR which is the 14-day exponential moving average on Kraken through 2026/07/09.