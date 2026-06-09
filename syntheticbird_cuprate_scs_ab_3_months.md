---
layout: fr
title: SyntheticBird Cuprate Address Book, Reproducible Build and Supply Chain Security (3 months)
author: SyntheticBird
date: May 24, 2026
amount: 80
milestones:
  - name: First month
    funds: 26 XMR
    done:
  - name: Second Month AND completion of address book improvements
    funds: 27 XMR
    done:
  - name: Third month AND completion of reproducible build
    funds: 27 XMR
    done:
payouts:
  - date:
    amount:
  - date:
    amount:
  - date:
    amount:

---

# Who

I am [SyntheticBird](https://github.com/SyntheticBird45), a Cuprate contributor.

# What

Cuprate is currently closer than ever to a beta release, which is a good thing considering the FCMP++ Hardfork arriving at full speed. One of the requirements for the beta release is reproducible builds.

I will work on Cuprate for an estimated three months with the goal of implementing reproducible builds, improving the supply chain security of the repository, improving the Address Book component of Cuprate, and reviewing other contributors' PRs.

At the end of this CCS, everyone will be able to build the exact same Cuprate binary, bit by bit.

# Tasks

The planned set of tasks is as follows:

### 1. Improvements to the Address Book

The Address Book, despite careful efforts over the past three years, still lacks some important features. Notably: 
- Support for ban lists compatible with Monerod. 
- Peer bucketing. This enables discriminating the storage and selection of peers based on their subnets. We do not want subnets containing many nodes to be disproportionately likely to be selected.
- Implementation of missing commands. With the addition of RPC, some remain missing from the Address Book.

And generally improvements will be made where deemed suitable.

### 2. Reproducible builds and supply chain security

Supply chain security has become an extremely important topic recently with a wave of attacks compromising big players. 

Reproducible builds are necessary to ensure transparency regarding the binaries distributed to users. monero previously held collaborative building sessions to mitigate the risk of a rogue contributor or a compromised CI pipeline, distributing a consensus-verified hash of the resulting binary. This method has been deprecated in favor of using the Guix package manager to pull and build monerod and all its dependencies recursively.

Cuprate aims to follow a similar path toward enabling reproducible builds by using [StageX](https://stagex.tools/). This has been defined as a hard requirement for the beta release and the general distribution of the binaries to the public.

An often-quoted argument against Cuprate and in favor of Monerod is that monerod is less susceptible to supply chain attacks. While this is a somewhat vague statement, it is important to recognize that the Rust language has a culture of dependencies. This milestone will also be an opportunity to review potential improvements for mitigating supply chain attacks within the Rust ecosystem, notably by implementing dependency update policies and changing import methods.

### 3. PR Reviews and Late-Night Ideas

Over these three months, I will assist in reviewing PRs from other contributors/maintainers and occasionally propose PRs unrelated to the main milestones.

# Milestones

### 1. First month

26 XMR

### 2. Second Month AND completion of address book improvements

27 XMR

### 3. Third month AND completion of reproducible build

27 XMR

# Delivery

All work completed under this CCS will be submitted to the [`Cuprate/cuprate.git`](https://github.com/Cuprate/cuprate) GitHub repository.

# Funding

I will be working 35 hours per week for 12 weeks at 50\€/hr - 260\€/XMR.
35 × 12 = 420 | 420 × 50 = 21,000 | 21,000 ÷ 260 = 80

Total: 80 XMR
