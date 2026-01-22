---
layout: wip
title: emsczkp research Bulletproofs*
author: emsczkp
date: November 25, 2025
amount: 150
milestones:
  - name: Milestone 1, adapt Bulletproof to Protostar (design Bulletproofs*)
    funds: 33% (50 XMR)
    done:
    status: unfinished
  - name: Milestone 2, security proofs of Bulletproofs*
    funds: 33% (50 XMR)
    done:
    status: unfinished
  - name: Milestone 3, extend Bulletproofs* to Generalized Bulletproofs
    funds: 33% (50 XMR)
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

**Who and proposal**:
Hi, I am Emanuele “emsczkp”:
https://libera.monerologs.net/monero-research-lab/20240612#c385652

Here, a year ago more or less, I discussed about my research:
https://moneroresearch.info/index.php?action=resource_RESOURCEVIEW_CORE&id=221&list=1&highlight=1

In particular, I discussed the potential optimization of Bulletproofs IPA prover/verifier time by removing inverses. I’ve continued working in this direction. Removing inverses from the IPA is only the initial step of my real goal. Indeed, I’d like to enable folding schemes in the spirit of the Protostart compiler, which promise very interesting improvements:
https://eprint.iacr.org/2023/620

This CCS is to support my research work and complete the remaining roadmap towards enabling a folding scheme for Bulletproofs, which would asymptotically reduce verifier execution time to logarithmic across many proofs.
I will summarize this research, as well as the final product, under the name "Bulletproofs*" (BulletproofsStar, BP*).

**Why Protostar and not Halo?**
Roughly speaking, both Halo and Protostar are accumulation schemes. However, Protostar generalizes to (2k−1)-move special-sound protocols and its compiler can be suited to fold the algebraic components of Bulletproofs. By contrast, Halo compiles to an IPA which turns out to be a polynomial evaluation proof tied to the Sonic frontend (even though there is a generalization to any PCS). Instead, Protostar’s generic folding works with vector commitments and a low-degree verifier and avoids FFTs, leading to a more efficient prover. So, in summary, folding a Bulletproofs-like protocol is much closer to Protostar abstraction than Halo.

**Impact on Monero** (thanks to Luke “kayabanerve” for helping with the following):
Under FCMP++, the proofs that are candidates for folding are the membership and range proofs. The membership proof uses Generalized Bulletproofs (GBPs), an extension of the Bulletproofs arithmetic circuits that supports vector commitments. The range proof is a Bulletproofs+ (BP+) aggregate range proof.
GBP is linear to the amount of commitments and logarithmic to program size. With Curve Forests a near-constant membership proof size is achieved, but at the cost of building a unique Merkle tree per amount of inputs. Since 128 inputs are currently supported, this means 128 trees, so both the verification cost and the infrastructure required for Curve Forests are quite expensive.

The idea is that, by combining IVC folding and GBPs, we can support many-input transactions, using only a fraction of the bandwidth and verification time, and without having to build so many trees as seen with Curve Forests (dramatically extending the time to update the state after importing a block). Finally, this work would naturally extend to BP+ aggregate range proofs as well.

**How does this translate in practice?** There are several application scenarios for folding in Monero, including (but not limited to) the following:

- “Chain folding”. Suppose Alice and Bob each include their own membership proof in a single transaction without revealing their witnesses to each other: Alice creates her proof, passes it to Bob, and Bob adds his proof on top. In this case, we aggregate single-input transactions into one many-input transaction and create a single folded proof.
- “Stream proving”. This would enable zkRollups, where many statements are collected across transactions and a folded proof is generated for a batch of transactions.
- “Transaction uniformity”. In this scenario, all transactions have a fixed number of inputs and outputs so that all transactions look the same, improving privacy. We currently lack such a feature because larger transactions are too expensive for it to be worth the benefit to privacy. Cheaper standalone multi-input transactions through folding would address this issue.

Clearly, the first two scenarios require an additional scheme on top to fold proofs across transactions, while the third does not.

However, to identify the simplest and common pattern to start designing Bulletproofs*, we can phrase the following: “we want to optimize the current FCMP from n invocations of the circuit, executed sequentially in one proof with linear computation and logarithmic bandwidth, to n folded invocations in a way that reduces the verifier’s computational complexity”.

Given this, discussions about changes to the network (or similar system-level aspects) may be deferred until we obtain such proofs. 

**What to be done**:
The first step is to adapt the (algebraic) verifier to the Protostar form. A second step is to ensure that this modification does not break the security of Bulletproofs. Given the abstraction of the Protostar paper, this provides solid steps toward that goal. 
One more step is to extend the approach to the Generalized Bulletproofs (GBPs) proof system, while still supporting its arithmetic circuits.

This is a research proposal and there is a non-negligible risk that may not succeed in constructing a folding GBP. However, any intermediate results will still be valuable to progress toward this goal, and even a negative outcome will help identify the most promising future directions. All work will be documented and, where relevant results are obtained, we will submit them to top-tier conferences and journals (e.g., IEEE S&P, PoPETS, …).

**Budget and Timelines**:
150 XMR is the total badget for 6 months of full-time work (960 hours = 160 hours * 6 months).
My rate is 60$ /hour, this means 960 hours * 60$ = 150 XMR (rounded and considering $385/XMR from Coingecko).
I've diveded the work in 3 milestones, each of 2 months of work at 50 XMR (so it corresponds to 25 XMR/month).
This proposal expires on November 1, 2026.
