---
layout: fr
title: j-berman full-time development (4 months)
author: j-berman
date: May 4, 2026
amount:  302 Monero
milestones:
  - name: Month 1
    funds: 25% (75.5 Monero)
    done:
    status: unfinished
  - name: Month 2
    funds: 25% (75.5 Monero)
    done:
    status: unfinished
  - name: Month 3
    funds: 25% (75.5 Monero)
    done:
    status: unfinished
  - name: Month 4
    funds: 25% (75.5 Monero)
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

- FCMP++/Carrot beta stressnet.
   - Help triage and fix any identified bugs or issues.
- [FCMP++ audit handling](https://github.com/seraphis-migration/monero/issues/294).
   - Phase 1 should be complete before July.
   - Respond to & implement any issues identified.
   - Prepare for the next audit phases to eliminate downtime between audits.
- Prepare all FCMP++ code for upstream review and merge.
   - Will submit piecemeal PR's for all line items across all Audit Phases from [here](https://github.com/seraphis-migration/monero/issues/294).
   - Will submit piecemeal PR's from [this table](https://github.com/seraphis-migration/monero/issues/103).
- Documentation for the FCMP++ integration.
   - WIP [here](https://github.com/seraphis-migration/monero/blob/db799d655e5b484ff174501a99eff46a871dade2/docs/FCMP%2B%2B_INTEGRATION.md) ([tracking PR](https://github.com/seraphis-migration/monero/pull/110))
- Help on whatever tasks I can to get the FCMP++/Carrot fork to mainnet, including review.
   - TODO list tracker [here](https://github.com/seraphis-migration/monero/issues/53).
- Potentially look in to implementing [Share or Perish (selfish mining mitigation)](https://github.com/monero-project/research-lab/issues/146) to bolster PoW security.
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
   - AI is increasing load on this front.

A note: I plan to work on Serai independent from this CCS as time permits (I am prioritizing FCMP++/Carrot tasks). I would like to see Serai launched and operating smoothly.

## Who

j-berman on github / jberman on matrix / IRC

Past CCS's:
- https://ccs.getmonero.org/proposals/j-berman-4months-full-time-12.html
- https://ccs.getmonero.org/proposals/j-berman-4months-full-time-11.html
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

302 XMR

640 hours, 0.3 XMR/hr + $65/hr, $377/XMR from coingecko
