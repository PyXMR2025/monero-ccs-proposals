---
layout: fr
title: CCS Frontend Redesign
author: redsh4de
date: February 10, 2026
amount: 36
milestones:
  - name: New frontend on existing backend
    funds: 26
    done:
    status: unfinished
  - name: Final touches
    funds: 10
    done:
    status: unfinished
payouts:
  - date:
    amount:
  - date:
    amount:
---

## What this proposal is about

This proposal rewrites the CCS frontend in Astro to match the styling of the [new getmonero.org site](https://beta.monerodevs.org).

## Why

With the new getmonero.org site soon live, the CCS frontend needs to follow the same design language. Today the two sites are built on different stacks, which makes it harder for contributors to work across both, and visually disconnects the CCS from the rest of the project's web presence.

## What technologies would be used?

- [**Astro**](https://docs.astro.build/en/getting-started/): Renders pages to static HTML by default and ships zero client-side JavaScript. The [new getmonero.org site](https://beta.monerodevs.org) is also built in Astro, so the CCS and main site would share UI components and design language.

## What will be accomplished

### Milestone 1: Astro implementation (~26 XMR)

- Full page re-implementation in Astro, matching the design language of the new getmonero.org site
- Feature parity with the current site
- No client-side JS

Preview of some in-progress work:

![Index page](https://raw.githubusercontent.com/SyntheticBird45/monero-ccs-site/refs/heads/misc/previews/previews/index.jpeg "Index Page")
![Explorer](https://raw.githubusercontent.com/SyntheticBird45/monero-ccs-site/refs/heads/misc/previews/previews/explorer.jpeg "Explorer")
![Selected Tabs](https://raw.githubusercontent.com/SyntheticBird45/monero-ccs-site/refs/heads/misc/previews/previews/selectedtab.jpeg "Explorer: Tab Selected")

**Estimated completion: ~5 weeks from funding**

### Milestone 2: Testing, docs, and handover (~10 XMR)

Polish, testing, and handover.

- Setup scripts, documentation
- CI pipeline
- Handover to the current CCS maintainers
- Address community review feedback

**Estimated completion: ~2 weeks after Milestone 1**

## Who will complete the proposal

**[redsh4de](https://github.com/redsh4de)** - Previous CCS:
  - https://ccs.getmonero.org/proposals/redsh4de-getmonero-redesign.html

## Why it is important for Monero and the community

With the new getmonero.org site going live in the coming months, unifying the CCS and main page design + codebase keeps the online presence visually consistent and makes it easier for contributors to work across both.

## Funding

32 hours per week at $50/hr for 7 weeks (224 hours total). At ~$310/XMR:

M1: ~26 XMR\
M2: ~10 XMR

Total: ~36 XMR across ~7 weeks.
