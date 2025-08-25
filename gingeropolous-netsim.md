---
layout: wip
title: Monero Network Simulation Tool
author: Gingeropolous
date: July 9, 2025
amount: 30 
milestones:
  - name: Working simulation
    funds: 30
    done:
    status: unfinished
payouts:
  - date:
    amount:
---

CCS Proposal: Monero Network Simulation Tool
Create Monero simulation tool ($8,750)

Proposer:
Gingeropolous

Amount Requested:

The total fiat amount will be converted to XMR using a 14-day (EMA) from Kraken. A 10% buffer is added to the XMR amount to mitigate risks associated with XMR price volatility between funding and fund utilization.
Total Estimated Fiat Value: $8750 USD
2 week EMA as of edit: $319
XMR Amount: 8750 / 319 * 1.10 = 30.2 XMR

Details - I am using heavy AI assistance to create Monerosim, a piece of software that coordinates running monero in the shadow network simulator. Current work can be found here: https://github.com/Fountain5405/monerosim

Progress - I have a minimal simulation environment working (2 nodes, blocks generated, transaction passing from node 1 to node 2). Currently optimizing / refining things.

Milestones - I have edited this CCS to be just a single deliverable based milestone. I will request payout once I can run a simulated monero network with 1000 nodes, provide setup scripts and documentation.
