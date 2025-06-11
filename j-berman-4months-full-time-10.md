---
layout: wip
title: j-berman full-time development (4 months)
author: j-berman
date: April 14, 2025
amount:  396 Monero
milestones:
  - name: Month 1
    funds: 25% (99 Monero)
    done: 16 May 2025
    status: finished
  - name: Month 2
    funds: 25% (99 Monero)
    done:
    status: unfinished
  - name: Month 3
    funds: 25% (99 Monero)
    done:
    status: unfinished
  - name: Month 4
    funds: 25% (99 Monero)
    done:
    status: unfinished
payouts:
  - date: 11 June 2025
    amount: 99
  - date:
    amount:
  - date:
    amount:
  - date:
    amount:
  - date:
    amount:
---

## What

Work full-time 4 months on:

- Completing the FCMP++ integration.
    - Complete the blinds cache to speed up FCMP++ transaction construction ([WIP PR](https://github.com/seraphis-migration/monero/pull/25)).
    - Work on the following, some of which @jeffro256 is already working on:
        - Fee logic for FMCP++.
        - Incorporate composition changes to tree building and remove code for the key image migration: https://github.com/monero-project/meta/issues/1168
        - Cold wallet <> hot wallet integration.
        - HW wallet interface changes.
        - Multisig.
        - The `scan_tx` feature.
        - Background sync.
        - Clean up the FFI.
        - Cleaner logging.
    - Manage the [FCMP++ optimization contest](https://github.com/j-berman/fcmp-plus-plus-optimization-competition) and implement the winning submissions as necessary.
        - It should be noted: if the contest does not yield significant improvements specifically to `helioselene`, it may be worth it to re-work the FCMP++ wallet scanner to *download* the tree instead of re-build it locally.
            - Re-working the wallet scanner would likely take 1-2 weeks.
- Review the Carrot integration.
- Update documentation for the FCMP++ integration, using the same format as in this (now outdated) [WIP PR](https://github.com/monero-project/monero/pull/9436).
- Start submitting piecemeal FCMP++ PR's to the main Monero repo.
- Review @vtnerd's p2p encryption PR: https://github.com/monero-project/monero/pull/8996
- Continue Seraphis wallet library work:
    - My next task on this front is to bring the Serpahis lib async scanner into the current wallet API ([source](https://github.com/seraphis-migration/wallet3/issues/64#issuecomment-2067030930))
    - In the latest round of tests, I observed scanning speed-ups of 50-60% with a clearnet remote node, 35-45% with a tor node, 25-35% with a local node.
    - The async scanner has already undergone a round of review ([source](https://github.com/UkoeHB/monero/pull/23))
    - To be usable in the wallet API, the following still needs to be implemented:
        - A mutable subaddress lookahead ([source](https://github.com/UkoeHB/monero/pull/23#issuecomment-2036086371))
        - Pool scanning ([source](https://github.com/UkoeHB/monero/issues/41))
        - A clean way to save tx metadata ([source](https://github.com/UkoeHB/monero/issues/48))
        - The FCMP++ tree builder + Carrot scanning needs to be integrated.

A note: once I've completed all work on FCMP++, reviewing the Carrot integration, and reviewing [p2p encryption](https://github.com/monero-project/monero/pull/8996)), I may work on Serai independent from this CCS. I would like to see Serai launched and operating smoothly (and I still owe @kayabaNerve [more work on Serai in exchange for their research into FCMP's](https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/359#note_21276)). I would then return to continue Seraphis wallet library work.

## Who

j-berman on github / jberman on matrix / IRC

Past CCS's:
- https://ccs.getmonero.org/proposals/j-berman-3months-full-time-9.html
- https://ccs.getmonero.org/proposals/j-berman-3months-full-time-8.html
- https://ccs.getmonero.org/proposals/j-berman-3months-full-time-7.html
- https://ccs.getmonero.org/proposals/j-berman-3months-full-time-6.html
- https://ccs.getmonero.org/proposals/j-berman-3months-full-time-5.html
- https://ccs.getmonero.org/proposals/j-berman-3months-full-time-4.html
- https://ccs.getmonero.org/proposals/j-berman-3months-full-time-3.html
- https://ccs.getmonero.org/proposals/j-berman-3months-full-time-2.html
- https://ccs.getmonero.org/proposals/j-berman-3-months-full-time.html

## Proposal

396 XMR

640 hours, 0.3 XMR/hr + $65/hr, $204/XMR from coingecko

Requesting a raise of 0.05 XMR/hr from my prior CCS given I have demonstrated the ability to take the FCMP++ integration to the finish line.
