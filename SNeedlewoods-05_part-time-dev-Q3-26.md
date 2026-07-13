---
layout: fr
title: SNeedlewoods-05_part-time-dev-Q3-26
author: SNeedlewoods
date: June 30, 2026
amount: 15.48
milestones:
  - name: Q3 - Jul-Sep
    funds: 15.48
    done:
    status: unfinished
payouts:
  - date:
    amount:
---

## What?

- By now I have a [couple big PRs](https://github.com/monero-project/monero/pulls/SNeedlewoods) pending for which I plan to address review comments ASAP. To name the most important ones:
  1. Add functions to Wallet API [#9464](https://github.com/monero-project/monero/pull/9464)
  2. Remove cached password from Wallet API [#10232](https://github.com/monero-project/monero/pull/10232)
  3. Both based on 1. and 2.
     a) Replace `wallet2` with Wallet API in `monero-wallet-cli` [#10233](https://github.com/monero-project/monero/pull/10233)
     b) Replace `wallet2` with Wallet API in `monero-wallet-rpc` [#10819](https://github.com/monero-project/monero/pull/10819)
- There are some issues related to restore height I could eventually address (and partially already started investigating or working on):
  - Get actual block height on wallet creation from daemon and only rely on estimated restore height when offline.
  - Figure out if it's worth to improve "get restore height by restore date", this could be beneficial for wallets created with Polyseed (which stores the birthdate).
- Try to help where I can, e.g. PR reviews, issues on Github or discovered during other work, requests/suggestions from other devs.

Adjusting the paid hours per week from 10 to 12. From my [latest report](https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/664#note_36773) you can see that on average I was exceeding 13 h/week.


## Who?

I write code, mainly wallet related (Wallet API, wallet-cli, wallet-rpc). My previous CCS-proposals can be found here:

- [Proposal 1](https://ccs.getmonero.org/proposals/SNeedlewoods-01_part-time-dev-work-1-month.html)
- [Proposal 2](https://ccs.getmonero.org/proposals/SNeedlewoods-02_part-time-dev-work.html)
- [Proposal 3](https://ccs.getmonero.org/proposals/SNeedlewoods-03_part-time_dev_work-Q1-26.html)
- [Proposal 4](https://ccs.getmonero.org/proposals/SNeedlewoods-04_part-time-dev-Q2-26.html)


## Payment

Keeping my rate at 0.1 XMR/h regardless of fiat market price.

Q3: 12 (h/week) * 4.3 (weeks/month) * 3 (months) * 0.1 (XMR/h) = 15.48 (XMR).

So the total amount requested for this proposal is 15.48 XMR.
