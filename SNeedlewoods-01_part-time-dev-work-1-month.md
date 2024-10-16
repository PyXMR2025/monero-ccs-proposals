---
layout: fr
title: SNeedlewoods-01_part-time dev work (1 month)
author: Sneedlewooods
date: October 4, 2024
amount: 2.15
milestones:
  - name: month 1
    funds: 2.15
    done:
    status: unfinished
payouts:
  - date:
    amount:
---

## What?

For this proposal the focus of work will be on the new wallet API ([context](https://github.com/monero-project/monero/issues/9308)). The work is already ongoing since May 2024, there is [this PR](https://github.com/monero-project/monero/pull/9368) to organize functions and [this branch](https://github.com/monero-project/monero/compare/master...SNeedlewoods:seraphis_wallet:x_api_comments) to add comments, but most recent and most important is this [WIP PR](https://github.com/monero-project/monero/pull/9464) that adds functions to the API to make it "feature-complete" with `wallet2`.

There will not be a direct deliverable for the milestone and it's very unlikely the feature-complete API will be completely done (including reviews) before this proposal ends, but here are alternatives I would work on:
- If current API PR gets finished:
  - Help with step 2 from [this proposal](https://github.com/seraphis-migration/wallet3/issues/64): "Stop using the wallet2 object in the CLI and RPC wallets and instead use the wallet API."
  - Add unit_tests for the wallet API, or try to resurrect libwallet_api_tests (which are [temporarily disabled](https://github.com/monero-project/monero/blame/9866a0e9021e2422d8055731a586083eb5e2be67/Makefile#L60))
- If for any reason current API PR gets blocked:
  - Things found during the API work, mostly in CLI and RPC wallet. An incomplete list can be found [here](https://github.com/SNeedlewoods/seraphis_wallet/issues/1).

I give weekly updates on what I've worked on in the "Monero Tech Meeting", where I also get feedback from more experienced devs to decide which way to go.

Besides that I try to help out where I can.
This is a "pilot" proposal to see how things work out. If the majority is satisfied at the end of this proposal, I see it as confirmation that I can justify putting more time and energy into Monero (and will increase my hourly rate in future proposals). Hopefully I will become a long term contributor for general development.

I aim for 15+ hours/week on average, but for precaution I won't promise more than 10 hours/week.


## Who?

Hey, I'm SNeedlewoods, since early 2023 I'm lurking around in the Monero community.
In November 2023 I joined the weekly "Seraphis wallet workgroup meeting" (now called "Monero Tech Meeting") in the [no-wallet-left-behind](https://matrix.to/#/#no-wallet-left-behind:monero.social) matrix room and got encouraged by our friendly and very helpful devs to start coding for Seraphis.
Only when the main focus in development shifted from Seraphis to FCMPs earlier this year, I started working on Monero core or more accurately on wallet related stuff.

Admittedly I don't have much to show and my expertise is not on par with other contributors, but I think considering the amount I'm asking for this proposal is fair.

Code contributions so far:
[Seraphis](https://github.com/UkoeHB/monero/pulls?q=is:pr+author:SNeedlewoods)
[Monero](https://github.com/monero-project/monero/pulls?q=is:pr+author:SNeedlewoods)


## Payment

Work 10 hours/week for 1 month.
10 (hours/week) * 4.3 weeks_per_month = 43 hours total. I am setting my hourly rate at 0.05 XMR/hour regardless of fiat market price (but for those who care, that is roughly around 6,50€ or $7.50 per hour, according to the current 7-day range on coingecko: 123,43€-147,32€ or $136.38-$164.58), that makes for a total of 2.15 XMR.
