---
layout: wip
title:  Boog900 Cuprate RPC for wallet support (Rust Monero node).
author: Boog900
date: March 12, 2026
amount: 108
milestones:
  - name: Month 1.
    funds: 36 XMR
    done:
    status: unfinished
  - name: Month 2.
    funds: 36 XMR
    done:
    status: unfinished
  - name: Month 3.
    funds: 36 XMR
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

# Who

I am [Boog900](https://github.com/Boog900), you can see my last CCS [here](https://ccs.getmonero.org/proposals/boog_3_months_cuprate_4.html).

# What

This CCS I plan to put my full focus on getting the RPC interface done for wallet support. During my last CCS, I started this and
got wallet sync working, however, most of my last CCS was spent on changing our database to a much more efficient one for our
workload. With this new DB wallet sync is already a lot faster in my testing. I managed to do a full wallet sync in 23 minutes
compared to 1 hour 4 minutes with monerod. The actual improvement in response time is even more significant as that drop in sync time
still includes all the tx scanner operations that need to be done. The branch where this work is being done is here: https://github.com/Cuprate/cuprate/tree/rpc-stage

The main task I plan to move to when RPC is complete is getting Cuprate ready for FCMP++. I have already got a rough plan
for how tree management could work: https://github.com/Cuprate/cuprate/issues/591. 

# Funding

$70/hr for 540 hrs at $350/XMR: 108 XMR

I am asking for a raise in my hourly rate. I think this is justified given I’ve consistently shown that I can dramatically 
boost Monero node performance across many areas (DB, P2P, consensus) and find vulnerabilities in the C++ impl.
