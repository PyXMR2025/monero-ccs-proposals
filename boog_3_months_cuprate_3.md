---
layout: wip
title:  Boog900 full time work on Cuprate (3 months) + January
author: Boog900
date: February 11, 2025
amount: 160
milestones:
  - name: January
    funds: 40 XMR
    done: 18 March 2025
    status: finished
  - name: Month 1
    funds: 40 XMR
    done: 18 March 2025
    status: finished
  - name: Month 2
    funds: 40 XMR
    done:
    status: unfinished
  - name: Month 3
    funds: 40 XMR
    done:
    status: unfinished
payouts:
  - date: 8 April 2025
    amount: 80
  - date:
    amount:
  - date:
    amount:
  - date:
    amount:
---

# Who

I am [Boog900](https://github.com/Boog900), you can see my last CCS [here](https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/469).

# What

I will work for 3 months on Cuprate with an initial focus on releasing an alpha `cuprated`, the basic roadmap can be seen here: https://github.com/Cuprate/cuprate/issues/376.
I plan to work on what I think is best to advance the project.

I am also asking for payment for the hours I worked in January. We had some discussions about changing the way we
get funded, potentially making a combined "cuprate CCS", however we decided against it, this lead to the delay of this CCS. 
A list of things I did during January:

- finished the init PR: https://github.com/Cuprate/cuprate/pull/344
- worked on improving our consensus API: https://github.com/Cuprate/cuprate/pull/366, to prepare for fast-sync.
- Started working on [issue 174](https://github.com/Cuprate/cuprate/issues/174): https://github.com/Cuprate/cuprate/pull/382
- Investigated why monerod was syncing the first 100,000 blocks faster than cuprated, which lead to this PR: https://github.com/Cuprate/cuprate/pull/377
- Started working on changing monero-oxide's tx type to use compressed points: https://github.com/Cuprate/serai/tree/monero-comp-points
- Started working on fast-sync: https://github.com/Cuprate/cuprate/tree/fast-sync

All the tasks that have been started are pretty much ready just need to be cleaned up, they are all used in the fast-sync branch
which a few people have tested syncs on, the quickest sync _so far_ was just over 4 hours.

# Funding 

I am asking for 40 XMR for my work in January.

$55/hr for 480 hrs at $220/XMR: 120 XMR

total: 160 XMR
