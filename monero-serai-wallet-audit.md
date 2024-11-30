---
layout: wip
title: Audit monero-serai and monero-wallet
author: kayabaNerve
date: October 11, 2024
amount: 1050 XMR
milestones:
  - name: Audit of monero-[serai, wallet], including the FROST-inspired multisig protocol
    funds: 1050 XMR
    done:
    status: unfinished
payouts:
  - date:
    amount:
---
 
monero-serai and monero-wallet are public-good libraries built by myself as part of my work on Serai DEX. Despite the "-serai" name, both libraries have always been intended to be usable and actually used by the Monero community as a whole. Development has been ongoing for over two years. During that time, I have hired developers to work on and review it (including j-berman who truly needs credit and acknowledgement for their contributions), yet have never seeked community funding for my work. Now that monero-serai and monero-wallet are ready for their 1.0 release, meaning they have reached the necessary milestone to be considered sufficiently developed and meaningful, I have decided to request the community's support for their audits.
 
monero-serai is a from-scratch reimplementation of the Monero transaction protocol in Rust. It originally also
included wallet functionality yet that was split out into the monero-wallet library to offer greater
flexibility to consumers.
 
monero-serai is used by Cuprate[[1]](
  https://github.com/Cuprate/cuprate
)[[2]](
  https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/405
)[[3]](
  https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/422
)[[4]](
  https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/431
)[[5]](
  https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/456
)[[6]](
  https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/469
)[[7]](
  https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/484
) for its parsing/handling/stateless verification of Monero transactions. Specifically, included is:
 
- An implementation of v1 and v2 transactions
- Cryptonote ring signature, MLSAG, and CLSAG verification
- Borromean, Bulletproofs, and Bulletproofs(+) verification
 
monero-serai also underpins monero-wallet, a Rust library for sending and receiving Monero. It's intended to have a clean, high-level API, be usable in a variety of contexts (from desktops to embedded devices to web browsers), and support everything from traditional wallets to more novel use cases (such as atomic swaps). As part of this, it offers:
 
- Proving CLSAG, Bulletproofs, and Bulletproofs(+)
- Honest-sender outgoing view keys (deterministically derived transaction keys to simplify payment proofs and allow verifying transactions match an intent)
- A FROST-inspired multisig which has O(1) per-signer upload complexity and O(n) computational complexity, compared to Monero's multisig which has O(n!) complexity (where n is the amount of signers)
 
Potentially of most note is the work on multisig. FROST is a widely regarded, [IRTF standardized](https://datatracker.ietf.org/doc/rfc9591/) multisignature protocol for Schnorr signatures which I've applied to Monero's CLSAG (caveats apply). The application to CLSAG is built upon [modular-frost](https://github.com/serai-dex/serai/tree/develop/crypto/frost), a FROST implementation I wrote for Serai and have already [prior audited](https://github.com/serai-dex/serai/tree/develop/audits/Cypher%20Stack%20crypto%20March%202023).

Monero has historically had issues with its multisig which has a novel high-complexity DKG and a signing protocol which isn't formalized (though is currently Musig2-inspired). monero-wallet represents an opportunity to step forth with a formalized, proven, and audited multisignature implementation. One idea occassionally brought up has been to remove multisig from Monero proper, placing it in its own distinct repository, in order to not have multisig burden Monero. With the work done on monero-wallet, and the audit being funded here, completely deferring multisig to it would become a viable option.
 
monero-wallet has also been checked to have a matching decoy selection algorithm (specifically, a matching distribution of selected decoys), fee algorithm, and various other properties (such as TX extra) to ensure its transactions won't be fingerprintable.
 
There is interest by multiple wallets to use monero-wallet, and it's already being developed on top of by Serai, a user-facing multisignature use case, and an application premised on web technology (which compiles monero-wallet to WASM).
 
This CCS is to fund the formalization of the implemented CLSAG multisig protocol (already outlined), provide the necessary security proofs (derived from FROST), and audit monero-[serai, wallet]. The audit will be done by Cypher Stack (their quoted amount being the amount requested). The one milestone is to be paid directly, immediately, and in full, to Cypher Stack for their work.

After the audit, the plan is to transfer monero-serai into the newly created [monero-oxide](https://github.com/monero-oxide/monero-oxide) organization (head by myself and boog900 from Cuprate). This is to help ensure it stands as a public good and doesn't solely service a single project's needs. Additional discussions are ongoing regarding the future governance of monero-wallet.
