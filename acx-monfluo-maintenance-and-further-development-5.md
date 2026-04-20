---
layout: fr
title: acx part-time work on Monfluo 2026Q2
author: acx
date: March 31, 2026
amount: 10.8
milestones:
  - name: Month 1
    funds: 3.6 XMR
    done:
    status: unfinished
  - name: Month 2
    funds: 3.6 XMR
    done:
    status: unfinished
  - name: Month 3
    funds: 3.6 XMR
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

## Who

Hi, I am acx.  
I develop [Monfluo](https://codeberg.org/Monfluo/monfluo-android) - a pure Monero wallet for Android.  
Previous CCS:
* https://ccs.getmonero.org/proposals/acx-monfluo-maintenance-and-further-development-4.html

## What

I will continue maintenance and development of Monfluo-android.  

At the end of my last CCS I have delivered a [proof of concept](https://codeberg.org/Monfluo/monfluo-android/src/branch/oxide) that integrates Rust libraries (monero-oxide & monero-wallet-util) into Monfluo. In this PoC monero-wallet-util is used to color words during wallet restore depending on whether they are or are not valid seed words. I want to continue this work with the eventual goal of completely moving away from wallet2_api.h to the new API based on those libs.  
I will split the work into the following projects:  
* [monfluo-oxide](https://codeberg.org/Monfluo/monfluo-oxide) - library with platform-independent (not Android specific) Monero/wallet primitives, using monero-oxide & monero-wallet-util.
* [monfluo-cli](https://codeberg.org/Monfluo/monfluo-cli) (placeholder repository) - CLI tool for interacting with the `monfluo-oxide` library. It should support wallet creation, synchronization, etc. This is not the main deliverable of my CCS (although I do hope that in the long-term it will result in a usable CLI tool for the Monero community, as an alternative to `monero-wallet-cli`), but rather something I will use for quicker iteration instead of slower approach of starting with rewriting `monfluo-android` immediately.
* [monfluo-android](https://codeberg.org/Monfluo/monfluo-android/src/branch/oxide) (with [monfluo-oxide-jni](https://codeberg.org/Monfluo/monfluo-android/src/branch/oxide/monfluo-oxide-jni) and [monfluo-oxide-kotlin](https://codeberg.org/Monfluo/monfluo-android/src/branch/oxide/monfluo-oxide-kotlin) components) - the Android app.

I would like to split my time approximately as follows: 60-80% working on the new oxide stuff, and 20-40% maintaining the current version (e.g. adding small features / fixing bugs / etc).

I am intentionally making this CCS more open-ended compared to my previous CCSs as I am not sure how much I will be able to achieve during this quarter and what roadblocks I might encounter, but at the very least by the end of this CCS I would like to have a `monfluo-cli` that can create & sync wallets and also send & receive transactions.

As always, updating to new Monero versions and fixing bugs / security issues in current Monfluo-android project will be prioritized.  

## Funding

I am asking for 30$/h.  
With 40 hours a month (~9 hours a week) \* 3 months at ~$330/XMR this makes 30\*40\*3/330 ~= 10.8 XMR  

