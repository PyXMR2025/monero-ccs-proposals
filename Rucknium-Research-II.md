---
layout: wip
title: Rucknium Research II
author: Rucknium
date: July 25, 2025
amount: 93
milestones:
  - name: Month 1
    funds: 33% (31 XMR)
    done:
    status: unfinished
  - name: Month 2
    funds: 33% (31 XMR)
    done:
    status: unfinished
  - name: Month 3
    funds: 33% (31 XMR)
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

# What

I propose to carry out research to improve Monero's privacy & security, guide protocol decisions, and respond to Monero developer requests for statistical analysis of code changes where needed.

I will work on three major research tasks:

1) Researching how network-level privacy can be improved, especially countermeasures against spy nodes in the peer-to-peer node network.

2) Prepare a manuscript for submission to [Proceedings on Privacy Enhancing Technologies Symposium (PoPETs)](https://crysp.petsymposium.org/) for peer review and publication based on the methodology and results of [Optimal Static Parametric Estimation of Arbitrary Distributions (OSPEAD) for the Monero decoy selection algorithm ](https://github.com/Rucknium/OSPEAD).

3) Investigate causes and potential solutions of the concentration of Monero miners in a few large mining pools, which can present the risk of a 51% double-spending attack.

### Network Privacy 

I will continue the research on network-level privacy that [I started in my last CCS proposal](https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/439#note_30863). Both short-term and long-term solutions will be considered. Long-term solutions will include protocols that can be adopted by all users and/or node operators, seeking the ideal of "privacy by default". Therefore, research efforts will not focus on protocols that score poorly on any of the elements of the Confidentiality, Integrity, and Availability triad of information security. The specific tasks may include research of:

- Solutions to the unreachable node problem in Dandelion++. The problem reduces the plausible deniability of transactions originating from nodes that do not have inbound connections, which is probably the majority of nodes. The solution could involve modifications of Dandelion++, adoption of [Clover](https://link.springer.com/article/10.1007/s12083-021-01241-z) without modifications, modification of Clover, or a Clover-Dandelion++ hybrid.

- Continued data collection and empirical analysis of the Monero network.

- Solutions directly targeting proxy behavior of spy nodes, such as [Practical Proof Of Storage](https://ieeexplore.ieee.org/document/10174897).

### OSPEAD Journal Submission

Formal peer review provides valuable feedback and a backstop for errors in the cutting-edge research process. I will package the methodology and results of [OSPEAD ](https://github.com/Rucknium/OSPEAD) for peer review and publication in [Proceedings on Privacy Enhancing Technologies Symposium (PoPETs)](https://crysp.petsymposium.org/). Even when Full-Chain Membership Proofs (FCMP++) is deployed on mainnet, some wallets may still choose a transaction-construction method that can leak information to an untrusted node (but not on the blockchain) if OSPEAD-related statistical issues are not handled. Therefore, formal peer review of OSPEAD can still add privacy for some users in the FCMP++ era.

### Mining Pool Concentration

Concentration of proof-of-work mining hashpower by a few mining pools can present a risk of 51% double-spending attack, especially if unauthorized seizure of mining pool infrastructure is possible. The top Monero mining pool now regularly reaches 30 - 40% of network hashpower. My research of the problem could include:

- Review of the research literature about the causes of mining pool centralization and possible solutions.

- Assessing historical and present-day availability of data on Monero mining pool behavior.

- Economic modeling of the objectives of mining pool operators and individual miners.

- Investigating the viability of voluntary adoption of a dynamic [Pigouvian fee](https://en.wikipedia.org/wiki/Pigouvian_tax) by mining pool operators to discourage miners from congregating in large mining pools.

Given the current situation with [Qubic attempting to gain a large share of mining hashpower for malicious purposes](https://web.archive.org/web/20250810235057/https://www.coinspeaker.com/is-monero-at-risk-5-orphan-blocks-spotted-amid-qubic-mining-war/), mining pool concentration will be prioritized over the two other research tasks.

### Loose Ends

I will also tie up a few loose ends from earlier work:

- Finalize ["March 2024 Suspected Black Marble Flooding Against Monero: Privacy, User Experience, and Countermeasures"](https://github.com/Rucknium/misc-research/blob/main/Monero-Black-Marble-Flood/pdf/monero-black-marble-flood.pdf) as a Monero Research Lab research bulletin.

- Finalize ["Subnet Deduplication for Monero Node Peer Selection"](https://github.com/Rucknium/misc-research/blob/main/Monero-Peer-Subnet-Deduplication/pdf/monero-peer-subnet-deduplication.pdf) as a Monero Research Lab research bulletin.

- Finish write-up of ["Preliminary results of risk of OSPEAD deployment without hard fork"](https://gist.github.com/Rucknium/fb638bcb72d475eeee58757f754acbee), including three methods: decision by explicit rules, decision by machine learning, and hybrid.


# Who


> Make sure to be thankful there are weirdos like Rucknium and many others that spend ridiculous amounts of time working on privacy tech so we can try to avoid a dystopian panopticon future. 

-- [Duke Leto](https://web.archive.org/web/20250407220122/https://duke.hush.is/memos/6/)

I am an empirical microeconomist. My contributions to Monero include: reducing time to first transaction confirmation by 60 seconds, analysis of the 2024 black marble spam attack and evaluation of countermeasures, optimal decoy selection for ring signatures, countermeasures against spy nodes on the network, analysis of the privacy risk of nonstandard transactions, and evaluation of the security of the 10 block lock on re-spending transactions.

My [GitHub account](https://github.com/Rucknium) and [website](https://rucknium.me/). Previous CCS proposals: [OSPEAD: Fortifying Monero Against Statistical Attack](https://ccs.getmonero.org/proposals/Rucknium-OSPEAD-Fortifying-Monero-Against-Statistical-Attack.html) and [Rucknium Statistical Research](https://ccs.getmonero.org/proposals/Rucknium-Statistical-Research.html).


# Budget

I will work 20 hours/week for three months (13 weeks). My fiat-equivalent labour rate is the same as my previous proposal: 110 USD/hour. The average daily closing USD/XMR exchange rate for the last 14 days (2025-07-26 to 2025-08-08) according to CoinGecko was 300.76.

The above numbers compute to `20 * 13 * (110/300.76) = 95.092`. Rounding down to get whole numbers for the three milestones sets the total budget for this proposal to 93 XMR paid in three milestones of 31 XMR each. This proposal expires on August 1, 2026.

