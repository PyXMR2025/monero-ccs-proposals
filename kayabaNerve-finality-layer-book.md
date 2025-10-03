---
layout: wip
title: Development of a Book on a Finality Layer
author: kayabaNerve
date: August 14, 2025
amount: 175 XMR
milestones:
  - name: Development of the book
    funds: 175 XMR
    done:
    status: unfinished
payouts:
  - date:
    amount:
---
 
This proposal seeks funding to sponsor my time writing a 'book' (see https://monero-book.cuprate.org for an example of a 'book', though this would be less technical reference and more explanatory) regarding a finality layer. The book would be comprehensive to the design questions asked when working on a finality layer, possible answers, and a conclusive recommendation of the author's opinion. The intent of this book would be an educational resource advancing the discussion on finality layers (by ensuring everyone is on the same page) and a reference design, should we ever decide to move forward with implementation.
 
https://github.com/monero-project/research-lab/issues/135 is the existing GitHub issue on the topic, overviewing the premise of a finality layer. Summarizing here, a finality layer would be a secondary network parallel to Monero which decides Monero blocks to finalize. Once a Monero block is finalized, it'd be unable to be reorganized out of the best chain, preventing deep reorganizations. Additionally, we would be able to replace the 10-block lock with a finality-block lock, ideally causing its effective removal.
 
The book would cover the basic premises of synchronous vs. asynchronous consensus, data availability, possible goals of any finality layer, potential methods of selecting validators, potential methods to decide on finality, features from there, and various trade-offs. Also included would be the role of Proof of Work in the remaining network, compared to its role currently. The book would not exclusively cover options requiring a hard fork, nor options requiring the introduction of Proof of Stake.

The book would be made available as a web resource (such as Read the Docs) for accessibility, and to track updates via Git.
