---
layout: fr
title: BTCPay Server Monero Plugin
author: Deverickapollo & Napoly
date: January 6, 2025
amount: 273
milestones:
  - name: Requirements analysis and core infrastructure 
    funds: 41
    done:
    status: unfinished
  - name: Improve functionality and UI/UX for managing daemon and wallet-rpc
    funds: 68
    done:
    status: unfinished
  - name: Creating MVP for Monero Plugin to support multiwallet
    funds: 96
    done:
    status: unfinished
  - name: Final UI/UX Enhancements, Bug Fixing, Merchant Migration
    funds: 68
    done:
    status: unfinished
payouts:
  - date:
    amount:
  - date:
    amount:
---

_Note: 27.16 XMR has been donated to this proposal from bounties [1](https://bounties.monero.social/posts/36/2-100m-video-tutorial-how-to-set-up-btcpayserver-for-monero-only-on-vps-home-server) / [2](https://bounties.monero.social/posts/88/15-008m-btcpay-server-additional-optimizations) / [3](https://bounties.monero.social/posts/77/10-052m-make-btcpay-server-configuration-accessible)_

## Overview

**Hello everyone!**

We are thrilled to announce our plans to refactor the Monero integration for BTCPay Server. With the release of [BTCPay Server 2.0](https://blog.btcpayserver.org/btcpay-server-2-0/), the platform has undergone a major update, introducing breaking changes to the Monero integration. This redesign transitions non-core features, such as Monero support, into a plugin-based architecture. This shift provides an excellent opportunity for the Monero community to take ownership of the integration and ensure its long-term development. [The BTCPay team has expressed their support](https://github.com/btcpayserver/btcpayserver/pull/6535) for this initiative, and we are fully committed to making it a success. To prepare for this work, the Monero codebase has already been migrated into its own repository, paving the way for its transition into a [standalone plugin](https://github.com/btcpayserver/btcpayserver-monero-plugin).

We’d like to thank the BTCPay development team, particularly @NicolasDorier, for laying the groundwork for the Monero plugin and ensuring a stable transition from core integration. As they noted in [PR #6535](https://github.com/btcpayserver/btcpayserver/pull/6535), the move to plugins empowers the Monero community to take full control of its development and lifecycle—without being bottlenecked by core BTCPay priorities or unfamiliarity with Monero’s internals.

**How did we get here?** 

The initial integration was developed by @kukks of the BTCPay team and funded through [a CCS proposal](https://repo.getmonero.org/monero-project/ccs-proposals/-/merge_requests/63) by an anonymous donor. While this implementation successfully introduced Monero support to BTCPay Server, there is an opportunity to expand its functionality by adding features such as multi-wallet support and enhanced wallet management tools. During our work on [open bounties](https://bounties.monero.social/posts/124/5-019m-btcpay-server-allow-syncing-via-remote-node) and [2](https://bounties.monero.social/posts/88/15-008m-btcpay-server-additional-optimizations) for the Monero community, we identified the need to realign our efforts on the [plugin migration](https://github.com/btcpayserver/btcpayserver/pull/6239#issuecomment-2373319844) to ensure continued support for Monero within BTCPay Server. 

Thanks to funding from the Magic Grants and Coincards, we had the opportunity to meet at Monerotopia 2024 and analyze this challenge in depth. During this collaboration, we established a [comprehensive roadmap](https://github.com/users/deverickapollo/projects/5/views/1) and a [plugin repository](https://github.com/napoly/btcpayserver-plugin-monero) with CI/CD support for stable releases and development. The plugin is currently in the proof-of-concept stage, with a focus on establishing a solid foundation for the plugin.

There was initial confusion in the Monero community about whether BTCPay Server would continue maintaining the Monero integration after 2.0. To clarify: the plugin is now fully community-owned. BTCPay Server will no longer hosts or manages the Monero integration beyond platform-level support and docker artifacts following BTCPayServer v2.1. This proposal is intended to ensure the plugin remains functional, actively developed, and aligned with Monero users’ expectations.

**What's next?**

We are seeking funding to continue developing and maintaining the Monero plugin for BTCPay Server. This includes building a robust proof of concept and minimum viable product (MVP), improving the user interface, addressing bugs, and assisting with merchant migration from the legacy Monero integration. Our near-term goal is to merge earlier boilerplate work, developed after Monerotopia 2024, into the current plugin repository and begin its migration to the new [btcpay-monero GitHub organization](https://github.com/organizations/btcpay-monero). This move will help formalize community ownership and better organize contributions going forward.

We aim to extend the plugin with capabilities to manage multiple Monero wallets within a single BTCPay Server instance. This enhancement will enable **third-party hosting scenarios**, allowing service providers to support multiple vendors without requiring each vendor to manage their own infrastructure. This is particularly beneficial for merchants who prefer a hosted solution over self-deployment.

In addition, there are several open bounties currently available for the Monero integration:

- [Make BTCPay Server configuration accessible](https://bounties.monero.social/posts/77/10-052m-make-btcpay-server-configuration-accessible)
- [Allow syncing via remote node](https://bounties.monero.social/posts/124/5-019m-btcpay-server-allow-syncing-via-remote-node)
- [Additional Monero optimizations](https://bounties.monero.social/posts/88/15-008m-btcpay-server-additional-optimizations)

We propose incorporating these bounty funds into the broader plugin development effort, ensuring that all outstanding tasks align with our roadmap and long-term strategy.

As part of this transition, we also plan to eventually migrate Dockerfiles and supporting infrastructure currently hosted under the BTCPay organization to the btcpay-monero GitHub org. This reduces reliance on BTCPay’s infrastructure and aligns with their recommendation that each altcoin community manage its own deployment lifecycle and testing.


Contributors:

 * [Deverickapollo](https://github.com/deverickapollo)
 * [Napoly](https://github.com/napoly)

## Milestones

### Milestone 1: Requirements Analysis and Core Infrastructure
- **Deliverables:**
  - Plugin repository established and accessible.
  - Operational CI/CD pipeline for plugin development and releases.
  - Testing framework and code coverage
  - Support for existing merchants and users
- **Funds:** 15% of funds
- **Timeline:** Week 1-4
- **Status:** Mostly done

---

### Milestone 2: Refactor of UI and Improvements
- **Deliverables:**
  - UI improvements for Monero daemon configuration.
  - Refactor wallet setup interface.
  - Release as v0.1.0
- **Funds:** 25%
- **Timeline:** Week 5-10
- **Status:** Not started

---

### Milestone 3: Minimum Viable Product (MVP) for Multiwallet Support
- **Deliverables:**
  - Basic `monero-lws` support tested and integrated.
  - Release as 0.2.0
- **Funds:** 35%
- **Timeline:** Week 11-18
- **Status:** Not started

---

### Milestone 4: Final Release (Polishing and Merchant Migration)
- **Deliverables:**
  - UI/UX enhancements for seamless user experience.
  - Comprehensive documentation (installation, usage, troubleshooting, migration).
  - Bug fixing and testing.
  - Review remote node implementation
  - Final release of the plugin.
  - Post-release support and maintenance plan.
- **Funds:** 25%
- **Timeline:** Week 19-24
- **Status:** Not started

## Timeline

The integration process is expected to take approximately 16-24 weeks.

## Future Roadmap
- Plans for ongoing maintenance and support for the plugin.
- Launch first community instance of BTCPay
- Expand wallet features and functionality. 
- Continue reviewing open pull request, complete testing and manage releases


