---
layout: fr
title: jeffro256 full-time development 2025Q4
author: jeffro256
date: November 14, 2025
amount: 96
milestones:
  - name: Month 1
    funds: 33.33% (32.0)
    done:
    status: unfinished
  - name: Month 2
    funds: 33.33% (32.0)
    done:
    status: unfinished
  - name: Month 3
    funds: 33.33% (32.0)
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


## What

The last quarter we launched the FCMP++ Alpha Stressnet. It has generally been a huge success, showing that the node can handle a reasonable level
of FCMP++ stress while still revealing a large swath of improvements to make. We've tackled a lot of those issues, and are currently working
through many of them now. To browse the issues reported on Github, see: https://github.com/seraphis-migration/monero/issues. This last quarter, I
also solicited a review of some tweaks to the Carrot protocol from Cypherstack. I worked on and reported on a
[privacy vulnerability](https://github.com/monero-project/monero/issues/10059). I wrote a
[Carrot library in Rust](https://github.com/jeffro256/carrot-rs). I wrote and tested a [PR](https://github.com/monero-project/monero/pull/10157)
to improve the transaction input verification cache under load, improving block propagation and reorg times. I polished the Hot/Cold wallet
support in FCMP++. I wrote a few PRs overhauling HW device / Carrot-account / hybrid-account support in the Carrot libraries. I have been slowly
upstreaming commits to the Monero core repository, and I have been reviewing Berman's FCMP++ related work.

In the following quarter, I want to continue on this journey. Here is a list of tasks I want to work towards completing in rough order:

- Support new [unbiased hash-to-point](https://github.com/monero-project/research-lab/issues/142) in the Carrot code
- Make some misc code changes to Carrot code to better match the spec
- Research/review/reach consensus/implement scaling changes as discussed in https://github.com/seraphis-migration/monero/issues/44
- Begin soliciting Carrot core implementation audits
- Help launch FCMP++ Beta Stressnet with consensus / addressing protcol changes
- Further reach out and provide support to existing hardware wallet manufacturors on how to securely support Carrot/FCMP++ scanning/spending
- Solicit help for multisig implementations of Carrot
- Help out with the FCMP++ integration wherever I can

## Who

I have been contributing to the Monero core repository for [over two years](https://github.com/monero-project/monero/pulls?page=2&q=is%3Apr+author%3Ajeffro256) with a total of [125 merged commits to master](https://github.com/monero-project/monero/commits?author=jeffro256) thus far, with many open PRs. Over the last few months, I wrote up the [Carrot specification](https://github.com/jeffro256/carrot/blob/master/carrot.md), organized [auditing](https://github.com/cypherstack/carrot-audit), for which the community graciously funded, and [began](https://github.com/monero-project/monero/pull/9559) [implementing](https://github.com/monero-project/monero/pull/9697) it. Carrot will be the main supported addressing protocol post-FCMP++ if all goes according to plan. I also worked on the Seraphis migration project in 2023/2024.

Previous Proposals:
- https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/319
- https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/390
- https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/421
- https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/436
- https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/467
- https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/504
- https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/540
- https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/578
- https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/602

## Payment

I propose to work for 3 months at a rate of 32 XMR per month.
