---
layout: cp
title: jeffro256 full-time development 2025Q1
author: jeffro256
date: January 27, 2025
amount: 114
milestones:
  - name: Month 1
    funds: 33% (38.0)
    done: 18 February 2025
    status: finished
  - name: Month 2
    funds: 33% (38.0)
    done: 28 March 2025
    status: finished
  - name: Month 3
    funds: 33% (38.0)
    done: 24 April 2025
    status: finished
payouts:
  - date: 24 February 2025
    amount: 38
  - date: 10 April 2025
    amount: 38
  - date: 8 May 2025
    amount: 38
---

## What

The last quarter I implemented the core cryptography for [Carrot](https://github.com/jeffro256/carrot/blob/master/carrot.md). I will note that preliminary performance tests put Carrot scanning at about 30% faster on CPU usage versus scanning today, mostly thanks to the use of the X25519 ECDH library [mx25519](https:://github.com/tevador/mx25519). I also implemented pruned `cryptonote::transaction` [construction and scanning](https://github.com/monero-project/monero/pull/9697) for Carrot. The FCMP++ integration and Carrot integration are finally meeting ends and are almost ready for hot path integration. This next quarter, I want to continue this work to get a testnet out ASAP.

To recap, here is a list of things I will attempt to work on this quarter, in rough order of execution:

- Integrate Carrot scanning/transaction construction into main wallet codepaths
- Provide support to existing hardware wallet manufacturors on how to securely support Carrot outputs
- Use benchmarkings and static analysis to inform MRL decisions on transaction weight discussions etc
- Begin soliciting Carrot core implementation audits
- Provide Rust implementation of Carrot for Serai/Cuprate
- Solicit help for multisig implementations of Carrot
- Help out with the FCMP++ integration wherever I can

## Who

I have been contributing to the Monero core repository for [over two years](https://github.com/monero-project/monero/pulls?page=2&q=is%3Apr+author%3Ajeffro256) with a total of [84 merged commits to master](https://github.com/monero-project/monero/commits?author=jeffro256) thus far, with many open PRs. Over the last few months, I wrote up the [Carrot specification](https://github.com/jeffro256/carrot/blob/master/carrot.md), organized []auditing](https://github.com/cypherstack/carrot-audit), for which the  community graciously funded, and [began](https://github.com/monero-project/monero/pull/9559) [implementing](https://github.com/monero-project/monero/pull/9697) it. Carrot will be the main supported addressing protocol post-FCMP++ if all goes according to plan. I also worked on the Seraphis migration project in 2023/2024.

Previous Proposals:
- https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/319
- https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/390
- https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/421
- https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/436
- https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/467
- https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/504

## Payment

I propose to work for 3 months at a rate of 38 XMR per month.

