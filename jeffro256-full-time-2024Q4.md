---
layout: fr
title: jeffro256 full-time development 2024Q4
author: jeffro256
date: September 16, 2024
amount: 144
milestones:
  - name: Month 1
    funds: 33% (48.0)
    done:
    status: unfinished
  - name: Month 2
    funds: 33% (48.0)
    done:
    status: unfinished
  - name: Month 3
    funds: 33% (48.0)
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

The last quarter I began implementing [Jamtis-RCT](https://gist.github.com/tevador/d3656a217c0177c160b9b6219d9ebb96), as written by tevador. However, with the FCMP++ integration PR opened against master, and upon discussion of the general health of wallet development in the broader ecosystem, it became readily apparent that the way to move forward is to initially support existing Monero addresses in a way that would be indistinguishable on-chain from Jamtis-RCT, adding full Jamtis-RCT support later. As such, I formulated the [Carrot specification](https://github.com/jeffro256/carrot/blob/master/carrot.md), which expanded upon the legacy address section in tevador's original Jamtis-RCT proposal. I contacted and conducted meetings with auditors in regards to auditing this spec, which culminated in several proposals. I also implemented transaction scanning code and transaction construction code for Carrot. I would like to continue this work for the next few months ahead of the hardfork. The main things to work on for Carrot at this point are 1) persistent enote stores for both legacy and Carrot scan types together, 2) integration into the main wallet codepaths, 3) hardware device support, and 4) picking and organizing an auditor to move forward with. Ideally, there should also come a point in the near future where the implementation is reviewed against the audited specification. I wish the development of Carrot generally to be swift, in order not to impede the release date of the FCMP++ consensus protocol. It should be noted that if the current addressing protocol is not modified, then users' transactions will *not* be afforded conditional forward secrecy. This would mean that a potential future adversary with the ability to solve the decisional Diffie-Helman problem (e.g. a usable quantum computer) would be able to retroactively reveal the transaction graph without any obfuscation. Carrot, like Jamtis-RCT, leverages the forward secrecy property of FCMP++ while also tackling other issues like the burning bug, Janus attacks, etc. If all goes well, the adoption of Carrot will seamlessly move Monero users into the full realization of the privacy and security that the FCMP++ proving system has to offer. 

To recap, here is a list of things I will attempt to work on this quarter, in rough order of execution:

- Finalize Carrot spec audit
- Implement Carrot enote store
- Implement Carrot hardware device support
- Integrate Carrot into main wallet codepaths
- Begin soliciting Carrot implementation audit

P.S. To all the generous supporters of my previous proposals, I apologize that the direction of my work has shifted so significantly and so frequently in the past. So many developments have occurred within the last year that it makes my head spin, which in the end will no doubt be a good thing. So while a lot of previous goals have been abandoned, and a lot of previous work put on ice indefinitely, things seem to be finally solidifying towards a forseeable, readily-achieveable outcome in regards to the upcoming hardfork, thanks to many hard-working contributors. Hopefully, all of the work for this quarter will actually see the light of day in the short to medium term. Thanks for your patience. I am very grateful for it.

## Who

I have been contributing to the Monero core repository for [over two years](https://github.com/monero-project/monero/pulls?page=2&q=is%3Apr+author%3Ajeffro256) with a total of [76 merged commits to master](https://github.com/monero-project/monero/commits?author=jeffro256) thus far, with many open PRs. I also began working on the Seraphis migration project, so you can see some of my contributions [here](https://github.com/seraphis-migration/monero/pulls?q=is%3Apr+author%3Ajeffro256) and [here](https://github.com/UkoeHB/monero/pulls?q=is%3Apr+author%3Ajeffro256). Additionally, as I mentioned, last quarter I wrote up the [Carrot specification](https://github.com/jeffro256/carrot/blob/master/carrot.md) for formal auditing, which will be the main addressing protocol post-FCMP++ if all goes according to plan.

Previous Proposals:
- https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/319
- https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/390
- https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/421
- https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/436
- https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/467

## Payment

I propose to work 40 hours/week for 3 months so `40 (hours/week) * 3 (months) * weeks_per_month = 40 (hours/week) * 3 (months) * (365 / 12 / 7) (weeks/month) = 521` hours total on-paper, though I usually work more than that. The proposal is broken into 3 milestones, one for each month. I am setting my hourly rate at 47 USD/hour (+1 USD/hour higher than last quarter), and at a market price of 170.37 USD/XMR, that makes for a total of 143.7 XMR. Price was calculated as 14-day simple average of opening prices on [CoinGecko](https://www.coingecko.com/en/coins/monero/historical_data) from 2024-09-04 to 2024-09-17 (day of writing), same as last quarter.

