---
layout: cp
title: j-berman full-time development (4 months)
author: j-berman
date: December 1, 2025
amount:  296 Monero
milestones:
  - name: Month 1
    funds: 25% (74 Monero)
    done: 14 January 2026
    status: finished
  - name: Month 2
    funds: 25% (74 Monero)
    done: 15 February 2026
    status: finished
  - name: Month 3
    funds: 25% (74 Monero)
    done: 27 March 2026
    status: finished
  - name: Month 4
    funds: 25% (74 Monero)
    done: 30 April 2026
    status: finished
payouts:
  - date: 26 January 2026
    amount: 74
  - date: 5 March 2026
    amount: 74
  - date: 9 April 2026
    amount: 74
  - date: 19 June 2026
    amount: 74
---

## What

Work full-time 4 months on:

- Completing the FCMP++ integration.
    - We launched the alpha stressnet, and it's currently on release version 1.4: https://github.com/seraphis-migration/monero/releases
    - We are currently finishing ironing out the core issues identified during the alpha stressnet.
        - Here is a more detailed status update: https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/600#note_33193
    - Once alpha stressnet participants confirm the core issues are ironed out, I would like to begin preparing for the beta stressnet.
        - I will continue to help triage and fix identified bugs/issues.
        - The plan to mainnet: alpha stressnet, beta stressnet, finish code review/audits, testnet, mainnet.
        - Here is the TODO list for beta: https://github.com/seraphis-migration/monero/issues/166
    - Work on the following, some of which @jeffro256, @0xFFFC0000, and @articmine are already working on:
       - [v1.5 of the alpha stress network](https://github.com/seraphis-migration/monero/pull/240).
        - Sync failures: https://github.com/seraphis-migration/monero/issues/244
        - One user (u/Lyza) is reporting unexpectedly slow time to verify FCMP++ proofs during sync on their machine: https://github.com/seraphis-migration/monero/issues/246
        - Collaborate with @0xFFFC0000 to get [tx relay v2](https://github.com/seraphis-migration/monero/pull/184) across the finish line.
        - Continue deliberating on, reviewing, and implementing updated fee/scaling logic for FMCP++.
          - We need to reach rough consensus on the scaling approach for the beta stress network: https://github.com/seraphis-migration/monero/issues/44
        - Review @jeffro256's cold wallet <> hot wallet integration.
        - Review @jeffro256's HW wallet work.
        - Multisig.
          - A) update multisig sync to manage the tree correctly on import.
          - B) use [`monero-wallet`](https://github.com/serai-dex/serai/tree/develop/networks/monero) for the core protocol. 
        - See [this TODO list tracker](https://github.com/seraphis-migration/monero/issues/53).
- Complete documentation for the FCMP++ integration.
    - WIP [here](https://github.com/seraphis-migration/monero/blob/db799d655e5b484ff174501a99eff46a871dade2/docs/FCMP%2B%2B_INTEGRATION.md) ([tracking PR](https://github.com/seraphis-migration/monero/pull/110))
- Continue submitting piecemeal FCMP++ PR's to the main Monero repo.
    - See this upstreaming plan here: https://github.com/seraphis-migration/monero/issues/103
    - I would like to get the crypto PR's audited as well, and will work on pushing that forward during this proposal.
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

A note: once I've completed all blocking work on the FCMP++ / Carrot integration, I plan to work on Serai independent from this CCS. I would like to see Serai launched and operating smoothly. I would then return to continue Seraphis wallet library work.

## Who

j-berman on github / jberman on matrix / IRC

Past CCS's:
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

296 XMR

640 hours, 0.3 XMR/hr + $65/hr, $399/XMR from coingecko
