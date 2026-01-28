---
layout: wip
title: Getmonero.org Redesign Implementation
author: redsh4de
date: October 29, 2025
amount: 40
milestones:
  - name: Technical foundation, UI components, and blog system
    funds: 60% (24 XMR)
    done: 27 December 2025
    status: finished
  - name: Accessibility, CI/CD, and final updates & optimizations
    funds: 40% (16 XMR)
    done:
    status: unfinished
payouts:
  - date: 27 January 2026
    amount: 24
  - date:
    amount:
---

## What the proposal is about

This proposal delivers a full technical foundation of the redesign for getmonero.org, including UI components and the blog with complete migration of historical blog posts. It does not change or migrate any other non-historical content (e.g., page content, Moneropedia, Guides, Dev docs), as there doesn't seem to be consensus on that yet.

I already have a working prototype of the website that I developed as volunteer work and open-sourced, which you can preview and explore:
* Source: https://github.com/redsh4de/monero-site
* Preview: https://getmonero-redesign-impl.vercel.app

Content migration can be done seperately once there's community consensus on what should be added in or adapted for the new website. (e.g. the "Knowledge Base" section, which consolidates a couple "Resources" sections)

The website is built using the Astro framework, which is a JavaScript static site generator that allows for modern web development features while shipping zero client-side JavaScript by default.

The design implements the planned [Figma redesign](https://www.figma.com/design/OuY892nD4zD1CEQDvC2Kty/Monero-Website-Redesign-2024--Copy-?node-id=0-1&p=f&t=M2axgNzZQ5oT69QT-0) that was made by Diego Salazar, with responsiveness across all devices.

## What will be accomplished

1. Complete Technical Skeleton + UI Components
    - All remaining routes/layouts (incl. /404) with placeholders.
    - Additions to the UI component library (buttons, cards, accordions, tabs, alerts, tables, code blocks, etc.)
    - Enforced no client-side JavaScript in shipped pages through CI (JavaScript used at build time only).

2. Blog System + Full Blog Migration
    - Blog index, author metadata, per-post pages.
    - Migration of existing blog/news posts (authorship, tags preserved).
    - RSS feed generation.

3. Icon/Media Pipeline (Tor Browser-friendly)
    - SVG-free shipping for icons to satisfy Tor Browser "Safest".
    - Icons shipped as AVIFs via a typed <Icon> component which provides theming via CSS masks.

4. Cross-browser/device testing.

5. CI/CD & Automation
    - Existing GitHub Actions ported, and new ones for linting, building, accessibility audits, no-JS enforcement.

## Who will complete the proposal?

I am redsh4de, a software developer with several years of experience and occasional contributor to cryptocurrency projects. I spent a weekend in implementing the core design, responsiveness, light/dark mode, and a scalable Weblate friendly i18n system, demonstrating my technical capability in completing this proposal in a timely manner. You can check my work on the prototype linked above.

## Why it is important for Monero and the community
A modern, fast website is essential for Monero - for many, it serves as the first contact point about the project. Implementing the community approved design doesn't let it go to waste and turns the prior Figma work into a tangible upgrade. As an addition, the new website launch with the FCMP++ mainnet release would provide a coherent, timely message - a new era for Monero, both technically and visually.

Migrating from Jekyll to Astro also improves the developer experience: componentized UI, simpler content pipelines, and a leaner codebase. These changes lower ongoing maintenance costs and make future updates - whether content, languages, design or features, easier and more efficient.

## Milestones and projected timeline

### Milestone 1: Technical foundation, UI components, and blog system (60% / 24 XMR)
* Develop the complete technical skeleton with all routes and UI components.
* Provide updates on progress within the #monero-site Matrix channel and implement community feedback.
* Implement the blog system with full migration of historical posts.
* Ensure zero client-side JavaScript output.
* CI/CD setup for building and testing.
* Estimated completion: ~8 weeks from funding

### Milestone 2: Accessibility, CI/CD, and final updates & optimizations (40% / 16 XMR)
* Accessibility improvements
* Full CI/CD automation including audits and validations
* Tor Browser "Safest" compatibility and final optimizations.
* Develop documentation for maintainers.
* Implementing iterative feedback and testing before final delivery
* Estimated completion: 5 additional weeks (total ~13 weeks)

## Funding
I am willing to dedicate at least 36 hours per week to this project, at a $35 per hour rate, with the following schedule:
- Monday to Friday: 4 hours
- Saturday & Sunday: 8 hours each day

Using the XMR/USD exchange rate of $409 per XMR, the cost of the project is estimated as follows:
Working 13 weeks @ 36 hours -> 36 hours * 13 weeks * $35 = $16,380 - around 40 XMR.

No separate designer budget is required for this scope; I will leverage the existing design assets and handle minor design tweaks within the development time.

## Expiration date for the proposal

If this proposal is not funded or completed by February 31st, 2026, the allocated funds shall be distributed to other active proposals or the General Fund.
