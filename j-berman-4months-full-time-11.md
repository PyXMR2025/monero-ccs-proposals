---
layout: fr
title: j-berman full-time development (4 months)
author: j-berman
date: August 11, 2025
amount:  344 Monero
milestones:
  - name: Month 1
    funds: 25% (86 Monero)
    done:
    status: unfinished
  - name: Month 2
    funds: 25% (86 Monero)
    done:
    status: unfinished
  - name: Month 3
    funds: 25% (86 Monero)
    done:
    status: unfinished
  - name: Month 4
    funds: 25% (86 Monero)
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

## What

Work full-time 4 months on:

- Completing the FCMP++ integration.
    - We will be launching an alpha stressnet soon.
        - I will help triage and fix identified bugs/issues.
        - The plan to mainnet: alpha stressnet, beta stressnet, finish code review/audits, testnet, mainnet.
    - Work on the following, some of which @jeffro256 and @articmine are already working on:
        - Review and implement updated fee logic for FMCP++ (@articmine is currently finalizing a proposal).
        - Review @jeffro256's cold wallet <> hot wallet integration.
        - Review @jeffro256's HW wallet work.
        - Multisig.
          - Manage the tree correctly.
          - Use the [`monero-fcmp-plus-plus`](https://github.com/kayabaNerve/fcmp-plus-plus/tree/develop/networks/monero/ringct/fcmp%2B%2B) crate for core logic.
        - Final touchup tasks.
          - Final pass-through cleaning up the FFI (removing asserts/unwraps, returning errors correctly, clippy/fmt).
          - Final organizational changes in line with thoughts mentioned [here](https://github.com/seraphis-migration/monero/pull/43).
          - See [this TODO list tracker](https://github.com/seraphis-migration/monero/issues/53).
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
        - Integrate the FCMP++ tree builder + Carrot scanning.
- Misc. high priority tasks as they arise, including vulnerability response as requested.

A note: once I've completed all work on FCMP++/reviewing Carrot (and after reviewing [p2p encryption](https://github.com/monero-project/monero/pull/8996)), I may work on Serai independent from this CCS. I would like to see Serai launched and operating smoothly (and technically I still owe @kayabaNerve [more work on Serai in exchange for their research into FCMP's](https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/359#note_21276)). I would then return to continue Seraphis wallet library work.

## Who

j-berman on github / jberman on matrix / IRC

Past CCS's:
- https://ccs.getmonero.org/proposals/j-berman-4months-full-time-10.html
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

344 XMR

640 hours, 0.3 XMR/hr + $65/hr, $273/XMR from coingecko
