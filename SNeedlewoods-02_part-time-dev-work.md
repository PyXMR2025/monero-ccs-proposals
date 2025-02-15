---
layout: wip
title: SNeedlewoods-02_part-time dev work
author: SNeedlewooods
date: January 27, 2025
amount: 23
milestones:
  - name: M1 - Harden sensitive material in the Wallet API
    funds: 2.4
    done:
    status: unfinished
  - name: M2 - Replace wallet2 with Wallet API in simplewallet
    funds: 20.6
    done:
    status: unfinished
payouts:
  - date:
    amount:
  - date:
    amount:
---

## What?

Since the feature-complete Wallet API [PR](https://github.com/monero-project/monero/pull/9464) from my previous CCS proposal is finally in "pending review" state (I will give my best to quickly resolve issues coming up during the review, so it hopefully will get merged soon), it's time for the next steps:
- Harden handling of sensitive material in the Wallet API (Discussions: [#1](https://github.com/monero-project/monero-gui/issues/1537), [#2](https://github.com/feather-wallet/feather/issues/72#issuecomment-1405602142), [#3](https://github.com/monero-project/monero/pull/8619#issuecomment-1632951461)).
- Replace wallet2 with the Wallet API in simplewallet as proposed [here](https://github.com/seraphis-migration/wallet3/issues/64) in step 2 by @j-berman.

I'll try to spend at least 12 h/week coding.


## Who?

This is my second proposal, the previous one can be found here:

- [Proposal 1](https://ccs.getmonero.org/proposals/SNeedlewoods-01_part-time-dev-work-1-month.html)


## Milestone

(Disclaimer: I can't promise the estimated times are accurate, but I tried to keep them low and I'll take the risk if a milestone takes longer to complete.)

1. M1 (2.4 XMR): PR to harden handling of sensitive material in the Wallet API is merged to monero-project/monero
   - Stop caching the password (in Wallet API and GUI)
   - Use `epee::wipeable_string` instead of `std::string` for secret keys
   I estimate this can be completed in ~ 2 weeks, which makes:
   12 (h/week) * 2 (weeks) = 24 (h total M1).

2. M2 (20.6 XMR): PR to replace wallet2 with the Wallet API in simplewallet is merged to monero-project/monero
   I estimate this can be completed in ~ 4 months, which makes:
   12 (h/week) * 4.3 (weeks/month) * 4 (months) = 206.4 (h total M2).


## Payment

I am setting my rate at 0.1 (XMR/h) regardless of fiat market price (but for reference, that is roughly around 20,50€ or $21.50 per hour, according to the current 7-day range on coingecko: 195,68€-217,73€ or $202.95-$226.65).

M1: 24 (h) * 0.1 (XMR/h) = 2.4 (XMR).
M2: 206.4 (h) * 0.1 (XMR/h) = 20.64 (XMR).

That makes for a (rounded) total of:
2.4 (XMR) + 20.64 (XMR) = 23 (XMR total).
