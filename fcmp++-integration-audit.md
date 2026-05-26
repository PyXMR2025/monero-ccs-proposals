---
layout: wip
title: FCMP++ Integration Audit
author: j-berman
date: April 6, 2026
amount:  500 Monero
milestones:
  - name: Phase 1
    funds:
    done:
    status: unfinished
  - name: Phase 2
    funds:
    done:
    status: unfinished
  - name: Phase 3
    funds:
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

This CCS proposal is to audit the FCMP++ integration. The goal is that by the end of the audit, the actual code merged into the Monero repository will have received highly qualified independent scrutiny and review by a singular or multiple 3rd parties.

The plan is to conduct the audit in 3 phases:

1. **FCMP++ Crypto**

    1a. _Crypto in C/C++_
    
    1b. _Integrated Crypto_

2. **FCMP++ Curve Tree Building**
3. **FCMP++ Consensus Integration**

Each phase builds off the prior, and each phase is further divided into pull requests (PR's) that build off prior PR's.

As of this writing, the Phase 1 scope and goals are fully fleshed out and detailed [here](https://github.com/seraphis-migration/monero/issues/294), and we are currently soliciting quotes from a number of candidates for Phase 1. At the completion of Phase 1, the goal is to have the PR's from Phase 1 ready to be merged into the Monero code base.

Phases 2 and 3 will follow the same pattern. The goal is that at the end of Phase 3, the FCMP++ integration code is largely ready for mainnet, with FCMP++ research audits/review and the beta stressnet progressing in parallel.

This proposal requests a budget of 500 XMR ($150k USD at time of writing + a 5% volatility buffer) for all 3 Audit Phases of the FCMP++ integration. This CCS requests an upfront amount to cover all 3 Phases, though we would start with Phase 1. Like with the [FCMP++ Research CCS](https://ccs.getmonero.org/proposals/fcmp++-research.html), which raised a large amount upfront, the intent behind raising a large amount upfront is to be able to move from Phase 1 to Phase 2 to Phase 3 as efficiently as possible, with as little downtime as possible.

Like with the Research CCS, we will discuss the candidates for each Phase in MRL meetings, before engaging in an agreement to commence an Audit Phase with a final candidate. Ideally MRL signs off on a candidate before proceeding with a candidate, just like how the Research CCS has done.

If there are leftover funds at the end of the audits, then the funds would be re-purposed for an audit & review of FCMP++ integration code that is less critical (one example is code that **wallets** may use to check pre-fork outputs for torsion using a technique that is not currently academically proven -- this is deemed *not* critical because it does not affect consensus, and would have limited impact if incorrect).
