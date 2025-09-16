---
layout: wip
title: jeffro256 full-time development 2025Q3
author: jeffro256
date: August 11, 2025
amount: 123
milestones:
  - name: Month 1
    funds: 33.33% (41.0)
    done:
    status: unfinished
  - name: Month 2
    funds: 33.33% (41.0)
    done:
    status: unfinished
  - name: Month 3
    funds: 33.33% (41.0)
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

The last quarter I finished integrating Carrot/FCMP++ transaction construction into `wallet2`, and tested it with CLI, RPC, and GUI wallets.
I also implemented and [integrated](https://github.com/seraphis-migration/monero/pull/52) working hot-cold wallets for Carrot/FCMP++. I began
[laying out the groundwork](https://github.com/seraphis-migration/monero/issues/63) for helping helping hardware wallet developers integrate
Carrot/FCMP++. Some community members have begun outreach to established HW devs to get them aware of the upgrade. I helped @j-berman
judge/administrate the [FCMP++ optimization competition](https://www.getmonero.org/2025/04/05/fcmp++-contest.html). We have created a
[TODO list](https://github.com/seraphis-migration/monero/issues/53) for FCMP++ launch, and are getting much closer to a public testnet, even
though we previously thought it would arrive much sooner before the divisors turbulence.

For this next quarter, I want to continue the work I have been doing to get Carrot/FCMP++ off the ground (see the TODO list). Here is a list of
things I will attempt to work on this quarter, in rough order of execution:

- Further reach out and provide support to existing hardware wallet manufacturors on how to securely support Carrot/FCMP++ scanning/spending
- Begin soliciting Carrot audits for protocol tweaks since first audit
- Begin soliciting Carrot core implementation audits
- Provide Rust implementation of Carrot for Serai/Cuprate
- Solicit help for multisig implementations of Carrot
- Help out with the FCMP++ integration wherever I can

## Who

I have been contributing to the Monero core repository for [over two years](https://github.com/monero-project/monero/pulls?page=2&q=is%3Apr+author%3Ajeffro256) with a total of [111 merged commits to master](https://github.com/monero-project/monero/commits?author=jeffro256) thus far, with many open PRs. Over the last few months, I wrote up the [Carrot specification](https://github.com/jeffro256/carrot/blob/master/carrot.md), organized [auditing](https://github.com/cypherstack/carrot-audit), for which the community graciously funded, and [began](https://github.com/monero-project/monero/pull/9559) [implementing](https://github.com/monero-project/monero/pull/9697) it. Carrot will be the main supported addressing protocol post-FCMP++ if all goes according to plan. I also worked on the Seraphis migration project in 2023/2024.

Previous Proposals:
- https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/319
- https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/390
- https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/421
- https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/436
- https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/467
- https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/504
- https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/540
- https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/578

## Payment

I propose to work for 3 months at a rate of 41 XMR per month.
