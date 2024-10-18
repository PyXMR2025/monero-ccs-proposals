---
layout: wip
title: Carrot Spec Peer Review
author: Monero Research Lab
date: October 11, 2024
amount: 126
milestones:
  - name: Carrot spec peer review
    funds:
    done:
    status: unfinished
payouts:
  - date:
    amount:
---

## Carrot Peer Review

This CCS will provide funding for the first step towards a Carrot implementation in Monero. Carrot is a specification for a backwards-compatible addressing protocol, as well as a new wallet key hierarchy for the upcoming FCMP++ consensus upgrade. This peer review will be over the specification, not any specific implementation. CypherStack was chosen for this audit from among several firms during the Monero Resarch Lab meetings the last couple weeks.

## Scope / Deliverables

A full peer review of the spec document [[link](https://github.com/jeffro256/carrot/blob/master/carrot.md)]. Note that at the time of writing this proposal, the paper is not yet published in a peer-reviewed conference/journal.

The deliverable is a write-up which will include security proofs for all properties listed in section 9. It will also include notes on weaknesses, issues, or recommendations (if any). In the case that a security proof is not possible, a note will be included describing why that proof is not possible. In the case that CypherStack requires more funds to complete the security proofs, an MRL meeting will be held and a new CCS may be opened.

## Out of scope

- Multiparty computation. There are no specific protocols presented for this, and no corresponding security model of proofs of security.
- Collaborative construction. For the same reason as multiparty computation.

## Funding

Because CypherStack has had a long successful history with Monero, has agreed to accept the XMR directly, wishes to mitigate volatility risks, and has received upfront payment for reviews before, the 126 XMR for this review is to be paid out in full to Cypherstack immediately upon reaching the funding goal.
