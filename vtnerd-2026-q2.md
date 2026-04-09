---
layout: fr
title: vtnerd Full-time 2026 Q2
author: Lee Clagett (vtnerd)
date: March 12, 2026
amount: 89.91 XMR
milestones:
  - name: Month 1 (160 hours)
    funds: 29.97 XMR
    done:
    status: unfinished
  - name: Month 2 (320 hours)
    funds: 29.97 XMR
    done:
    status: unfinished
  - name: Month 3 (480 hours)
    funds: 29.97 XMR
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

3-Months full-time software development on monero components in 2026 q2

## What
Work primarily on `monerod`, `wallet2`, `monero-lws`, `lwsf` (and new lib, see below). Some of the work to be attempted or investigated:
  - Code reviews of monero core PRs
  - monerod/monero-lws/lwsf bug fixes and HackerOne mitigations as they arrive
  - Investigate removing "pratical" limit on block sizes
    - This will primarily be posted as a GH issue, as we have to switch serialization algorithms to make this achievable
      - My new serialization hasn't really been reviewed :/
      - The system RAM is primary issue/blocker
      - Can we split blocks across network messages, etc.?
      - Investigate what other blockchains (BCH perhaps?) are doing here
  - Keep existing PRs up-to-date:
    - New Serialization routine
    - Change from raw pointers to weak_ptrs in levin code
    - P2P SSL Support
    - Updating levin callbacks to C++14 moves
  - Find (possible) memory leak in weak_ptr PR
  - Complete work necessary to merge [DANE/TLSA in wallet2/epee](https://github.com/vtnerd/monero/tree/improve/dane_tlsa).
  - Adding trust-on-first-use support to wallet2
  - Add msgpack (or cbor) support to monerod-ZMQ (first stage PR for zmq-pub has been issued!)
  - `monero-lws` work:
    - Create 1.0 release
      - Deciding what features should make the release.
      - Need to publish a decent code signing key, this is a wip.
    - Complete “push” (now called `/feed`) interface for LWS clients (instead of existing poll interface)
      - The server and client implementation are completed and working. Just needs more (unit) testing and formalized written spec.
    - Update LWS spec and implementation to support new "carrot" features (view-balance key, etc).
      - LWS draft PR supports view-balance keys, but a spec needs to be written and posted.
    - Keep LWS backend synced with fcmp++ experimental branch
       - LWS backend is _mostly_ ready for fcmp++, but changes to fcmp++ branch mean changes in LWS draft PR are needed.
       - May need to change the draft spec for fcmp++ curve trees
    - Add a "scale" factor to remote scanning load balancing - send more accounts to systems with faster single thread performance 
    - Add 64-bit ed25519 code for faster arm64 scanning. Latest "Supercop" has unverified neon implementation.
      - This may get shelved as fcmp++ looms.
    - Provide pre-built binaries (snaps? useful?)
    - (Unlikely) - reproducible builds so community members can verify+sign the binary hashes
    - Add msgpack (or cbor) support to ZMQ-REP and ZMQ-PUB (faster scanning)
      - Slow reviews in Monero mainline are the blocker on this.
  - `lwsf` (LWSF-frontend) work:
    - Implement fee estimation (may skip until fcmp++, much easier)
    - Add carrot/fcmp++ view-balance-key support (receive and spend). View-incoming will not be used by lwsf.
      - legacy keys and fcmp++ are verified as working
      - update fcmp++ draft pr to match latest changes
      - waiting on monero core to decide how to handle carrot wallets - polyseed? some other thing?
    - Complete subaddress improvements (basically done, but waiting on new server release)
    - Complete remainder of functions, EXCEPT for multisig and a few other non-critical functions.
      - The remainder of work is primarily support for hardware devices
    - Better support for handling (dropping) "dust" outputs during "sweeps"
    - Identify + fix bug with double spend and pending transactions
  - Create new FIDO2 encryption library/standard/spec (name pending) for encrypting wallet metadata+keys
    - Will be integrated into [`lwcli`](https://github.com/cifro-codes/lwcli) as a proof-of-concept
       - A wallet I created WITHOUT CCS funding
       - I figured out how to get everything working below in LWCLI even when using standard `wallet2` backend.
    - Encrypt metadata (always) + keys (when not hardware wallet) with FIDO2 hmac-secret devices. Trezor/Ledger also support this mode
      - Guarantees 256-bit quantum-safe security of metadata+key files
      - A password-encrypted `.fido2` file will contain FIDO2 nonces+userid.
        - Passphrase + FIDO2 device + `.fido2` file OR _just_ the seed phrase is required to decrypt metadata+keys
      - Full backup to cloud only requires metadata file; `.fido2` and `.keys` files can be omitted in backup for additional security
        - Quick/natural 2FA unlock in typical case, full metadata recovery using seed (+ optional Ledger/Trezor) in worse case
        - Ledger/Trezor will require backup of `.fido2` file, only randomized (quantum-safe) numbers leak if password is cracked
      - Register multiple FIDO2 devices
        - A (non Trezor/Ledger) FIDO2 device can decrypt view keys from file, and spending still requires Trezor/Ledger
          - More useful with Carrot outgoing-view-keys

There is intentionally more work than time allows - to ensure there is always something to work on in the proposal.

## Who

Lee Clagett (vtnerd). [I've](https://ccs.getmonero.org/proposals/vtnerd-2025-q1.html) [had](https://ccs.getmonero.org/proposals/vtnerd-tor-tx-broadcasting.html) [eight](https://ccs.getmonero.org/proposals/vtnerd-2020-q4.html) [CCS](https://ccs.getmonero.org/proposals/vtnerd-2021-q1.html), [proposals](https://ccs.getmonero.org/proposals/vtnerd-2023-q3.html) ([6](https://ccs.getmonero.org/proposals/vtnerd-2024-q3.html) [7](https://ccs.getmonero.org/proposals/vtnerd-2025-q3.html), and [8](https://ccs.getmonero.org/proposals/vtnerd-2025-q4.html)), and [one Magic Grant](https://monerofund.org/projects/Q1Q2_2024_dev_vtnerd).

Some of my biggest features in monero core repo are [Dandelion++](https://github.com/monero-project/monero/pull/6314), [adding supercop ASM speedups to wallet code](https://github.com/monero-project/monero/pull/6337), [ZeroMQ Pub Support for new blocks and transactions](https://github.com/monero-project/monero/pull/6418), and [SSL support to p2p](https://github.com/monero-project/monero/pull/8996).

Most recently I've created `lwsf` - a client library for the LWS protocol that implements the `monero-gui` C++ interface. This library powers the new [skylight wallet](https://skylight.magicgrants.org), and is now in real-world use. This library also supports a [websocket `/feed`](https://github.com/vtnerd/lwsf/tree/update/feed) from the [server](https://github.com/vtnerd/monero-lws/pull/237) such that real-time updates to a wallet are now possible (as opposed to polling/delayed notificaiton in all others). 

I've also made a functional LWS wallet scanner - which the lwsf/skylight communicates with - which is fully non-blocking to support more responses per thread, admin REST API, LMDB storage, subaddress support, webhook/zmq/rmq publishing (new receives, spends, and accounts), multi-machine scanning with (primitive) load-balancing, and an untrusted daemon mode that verifies PoW is valid (whereas normal wallets trust `monerod` responses entirely).

## Proposal

Work on the various tasks outlined above for 40 hours/week over the next 3 months after potential funding. I already use time-tracking software for work; if the hours dip in a given month unexpectedly, the update/milestone will be at the completion of the hours listed above.

The funds were calculated with 65 USD/hour with ~347.00 USD/XMR which is the 14-day exponential moving average on Kraken through 2026/03/12.
