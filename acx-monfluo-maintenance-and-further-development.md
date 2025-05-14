---
layout: wip
title: acx part-time work on Monfluo (3 months)
author: acx
date: February 28, 2025
amount: 13.98
milestones:
  - name: Month 1
    funds: 4.66 XMR
    done: 18 April 2025
    status: finished
  - name: Month 2
    funds: 4.66 XMR
    done:
    status: unfinished
  - name: Month 3
    funds: 4.66 XMR
    done:
    status: unfinished
payouts:
  - date: 13 May 2025
    amount: 4.66
  - date:
    amount:
  - date:
    amount:
---

## Who

Hi, I am acx.  
About six months ago I have forked Mysu (an abandoned Android wallet) and continued its development and maintenance.  
The fork is named Monfluo and is available [here](https://codeberg.org/acx/monfluo)  

Since starting the fork, I did (among other things) the following:  

* Implemented multi-wallet functionality (also wallet renames and deletion)
* Implemented multi-account functionality
* Separated wallet password and seed offset (previously you could not set them to different values)
* Reworked secrets tab, allowing the user to apply seed passpharse offset when saving seed
* Fixed a bug where sync progress was lost when the wallet was closed before the sync is finished
* Implemented APK building in the pipeline (making it easier for users to test any commit without waiting for a release)
* and several other changes, you can check all of them [here](https://codeberg.org/acx/monfluo/compare/b939d526652d174eb6081a0b5e9dd407c409c90a...master)

Monfluo is by design a very simple wallet, and one of the goals is having no "integrations" such as swapping services, sending to other cryptos, fiat on/off-ramps, etc. I do not earn any fees from the wallet.

## What

I will continue maintenance and development of Monfluo. I will be working on the things listed [here](https://codeberg.org/acx/monfluo/issues), among the most important ones:

* Updating to newer Monero versions, when required
* Setting up a clearnet F-Droid repo together with an onion mirror
* Setting up translations
* Issues [#67](https://codeberg.org/acx/monfluo/issues/67) and [#71](https://codeberg.org/acx/monfluo/issues/71)
* Working on making Monfluo reproducible (I do **not** expect to finish this one during this CCS, but I want to start investigating it)

## Funding

I am asking for 25$/h.  
With 40 hours a month (~9 hours a week) \* 3 months at ~$215/XMR this makes 25\*40\*3/215 ~= 14 XMR  

