---
layout: cp
title: Offline Signing Library for XmrSigner to Production
date: August 31, 2024
author: Thor a.k.a. vThor a.k.a DiosDelRayo
amount: 196
milestones:
  - name: Upfront
    funds: 20 XMR
    done: 11 November 2024
    status: finished
  - name: First month, minus upfront
    funds: 46 XMR
    done: 5 December 2024
    status: finished
  - name: Second month
    funds: 65 XMR
    done: 30 January 2025
    status: finished
  - name: Third month
    funds: 65 XMR
    done: 30 June 2026
    status: finished
payouts:
  - date: 15 November 2024
    amount: 20
  - date: 13 December 2024
    amount: 46
  - date: 10 February 2025
    amount: 65
  - date: 23 July 2026
    amount: 65
---

# Offline Signing Library for XmrSigner Production

## About

This proposal aims to create a minimal library for offline signing on
air-gapped devices, and make XmrSigner production ready to actual use secure, focusing on essential features:

- Seed phrase generation (including polyseed)
- Address and key generation
- Account and sub-address management
- Address verification
- Output importing and Key Image exporting (raw and encrypted)*
- Unsigned transaction handling (description, sanity checks, signing)
- Block height and date estimation

The library will be implemented in C++ with a C ABI, allowing use in
multiple languages. It will be based on the current Monero source but
without relying on wallet2, aiming for minimal external dependencies,
not inventing the wheel again, nor rolling own crypto.

Key objectives:
- Comprehensive documentation (OTS library, OTS Python library, buildroot packages desired integrated into monero docs for a easy and quick start to build something)
- Quick start guide for offline and hardware wallet developers
- Documentation of challenges in stripping down and cross-compiling
- Buildroot package for easy target system integration
- Python module for library usage
- Test code
- Modification of XmrSigner to use this new library

## Who

Thor (vThor/DiosDelRayo), completed the [XmrSigner (MoneroSigner Resurrection) proposal](https://ccs.getmonero.org/proposals/%20MoneroSignerResurrection.html).

## Why

[XmrSigner](https://github.com/XmrSigner/xmrsigner), while functional, is currently more of a proof of concept than a
production-ready tool. This library addresses several key issues:

1. Performance: The current implementation using wallet RPC is slow,
especially on resource-constrained devices.
2. Security: Minimizing dependencies and code base improves auditability
and reduces attack surface.
3. Flexibility: A dedicated library allows for easier integration into
various offline signing solutions.
4. Resource efficiency: Stripping down to essential features enables use on
lower-power devices.

By creating this library, we will:
- Bring XmrSigner to production readiness
- Provide a foundation for future hardware wallet development
- Explore the viability of using even more resource-constrained devices (e.g., MCUs) for offline signing
- Build the basis for a lib which could also serve for quick payment way (seems there exists something like it called pocket change, was not aware of before) even if the customer is offline. Talked about that in [#monero-community](https://libera.monerologs.net/monero-community/20241018#c446995)

A proof of concept has been developed to validate this approach:
[c_abi_for_cpp_code_PoC](https://github.com/DiosDelRayo/c_abi_for_cpp_code_PoC)

This library will significantly improve XmrSigner's performance, security,
and usability while opening doors for more diverse Monero hardware wallet
solutions in the future.

## Milestones and Timeline
# Offline Signing Library for XmrSigner Production

## Milestones and Timeline

### 1. Setting up documentation site (4 hours)

All OTS library related will go into a fork of docs.get-monero.org and should take me no more than a blink of an eye to get going.
For the XmrSigner related part I will setup the same mkdocs via github pages.
This is apart from the Doxygen and Sphinx documentation, which I need to see how to make it best available on the way.
<details>
<summary>View tasks</summary>

| Task | Hours | Sessions |
|------|-------|----------|
| Set up initial documentation structure | 2 | 1 |
| Configure documentation site | 2 | 1 |
| Use existing Monero documentation through PR's | 0 | 0 |

</details>

### 2. MVP library with C ABI (164 hours)

The main task of this proposal, creating an ots folder in monero/src and nit pick the parts the lib needs together
to create and compile a actual library. On top add the C ABI and make the build script as easy and robust as possible.
<details>
<summary>View tasks</summary>

| Task | Hours | Sessions |
|------|-------|----------|
| Initial ABI design | 16 | 8 |
| Seed phrase generation | 8 | 4 |
| Address and key generation | 10 | 5 |
| Account and sub-address management | 10 | 5 |
| Address verification | 10 | 5 |
| Output importing and Key Image exporting | 30 | 15 |
| Unsigned transaction handling | 30 | 15 |
| Write Doxygen documentation | 14 | 7 |
| Create detailed documentation of the ABI and library internals | 14 | 7 |
| Develop unit tests with Check | 14 | 7 |
| PR process revisions and merge | 8 | 4 |

</details>

### 3. Python cffi classes (44 hours)

Building the clue code between the C ABI and Python in a pythonic way.

<details>
<summary>View tasks</summary>

| Task | Hours | Sessions |
|------|-------|----------|
| Design Python class structure | 10 | 5 |
| Implement Python wrapper classes | 20 | 10 |
| Write rich inline documentation | 8 | 4 |
| Create Sphinx documentation | 2 | 1 |
| Develop unit tests for Python classes | 4 | 2 |

</details>

### 4. Building library in buildroot (44 hours)

buildroot is a build kit to create an embedded linux with the help of
packages which get cross compiled for the target platform. Here the dependencies
to build the OTS library from the monero sources need to be fulfilled.

<details>
<summery>Show more...</summary>
A very critical part to use the library on the pi zero (or other target device - maybe modifications will be needed here fore).
I build for XmrSigner before buildroot packages, but struggled to get monero-wallet-rpc as binary running on
the pi via Buildroot (how I was building on the Pi itself and there are so many dependencies that finally I pulled
the plug on that version, becauseit was clear that monero-wallet-rpc was only a temporary solution to finish the CCS
in a running state)
</details>

<details>
<summary>View tasks</summary>

| Task | Hours | Sessions |
|------|-------|----------|
| Adapt CMakeLists.txt for the library and its dependencies | 20 | 10 |
| Create buildroot package for downloading and compiling | 12 | 6 |
| Write documentation for builders/developers | 12 | 6 |

</details>

### 5. Buildroot package for Python library (12 hours)

The same but a lot easier then for the OTS library, here the Python OTS
library will get compiled via CPython, how there are only two dependencies (the OTS library and
cffi) it should be much easier even with a deterministic build.

<details>
<summary>View tasks</summary>

| Task | Hours | Sessions |
|------|-------|----------|
| Create buildroot package for the Python library | 8 | 4 |
| Write documentation for builders/developers | 4 | 2 |

</details>

### 6. XmrSigner integration (34 hours)

Here the XmrSigner code get's the upgrade, monero-wallet-rpc, python-monero, python-polyseed will
be replaced by the Python OTS library.

<details>
<summary>View tasks</summary>

| Task | Hours | Sessions |
|------|-------|----------|
| Remove existing dependencies and integrate new Python library | 26 | 13 |
| Update XmrSigner documentation | 8 | 4 |

</details>

### 7. XmrSigner on XmrSigner OS (buildroot2) (42 hours)

Here all gets assembled together to create the actual XmrSigner production image.

<details>
<summery>Show more...</summary>
How I did that already outside of the last CSS, I need only to make some modifications,
get the dependencies right, the biggest part will be testing and debugging if something
goes wrong - I had this issue already, but hope that this time is minimal to use the calculated
time for Milestone 9 because I really like to improve there. But 30 hours can vanish quick debugging
issues there because it took like 30min to build on a 4c ore i7 with 16GB (lack at the moment something more powerful)
and then flashing to microSD and test. But how from the buildroot image was forked from SeedSignerOS which stripped handy
everything unnecessary away - good for security and speed - but terrible to debug.
</details>

<details>
<summary>View tasks</summary>

| Task | Hours | Sessions |
|------|-------|----------|
| Create buildroot package for XmrSigner | 8 | 4 |
| Test and debug XmrSigner in buildroot environment | 30 | 15 |
| Write documentation for XmrSigner OS integration | 4 | 2 |

</details>

### 8. Unify XmrSigner-related components (48 hours)

Getting all the XmrSigner stuff on one place together and the OTS library stuff on docs.get-monero.org, or
at least in close reach.
<details>
<summery>Show more...</summary>
Through the excessive amount of time the last CCS took the rebranding to XmrSigner and
putting documentation and linking nice together suffered a bit. So here everything will
get separated what is actual XmrSigner and what is needed to build a different Offline Signer
from the OTS library and BCUR. So that XmrSigner is XmrSigner, and the building blocks a close to get-monrero.org
as possible. All development resources should be on monero docs after the PR got merged, so there is a quickstart
and all documents to create an offline signer pretty quick.
</details>

<details>
<summary>View tasks</summary>

| Task | Hours | Sessions |
|------|-------|----------|
| Reorganize and consolidate XmrSigner-related content on GitHub | 8 | 4 |
| Create separate documentation for UR codes | 20 | 10 |
| Register UR types used | 6 | 3 |
| Final review and organization of all documentation | 14 | 7 |

</details>

### 9. (Optional/Stretch) Clean-up and Optimization (82 hours)

Here is where my heart is, but after carefully calculating through the time, and catching myself,
arguing on almost each point it could be done faster, and almost halving most points... I still with 138h more
then the original 240 hours estimated. And instead of doubling or triple the time to have more air for unforeseen
challenges I'm now even tighter, so that I probably will end up again working a lot of hours for free to get all done.
But I still hope to safe enough time to get this milestone done, too.

<details>
<summary>View tasks</summary>

| Task | Hours | Sessions |
|------|-------|----------|
| Analyze Monero source dependencies | 20 | 10 |
| Remove unnecessary dependencies | 20 | 10 |
| Optimize remaining code | 10 | 5 |
| Document changes and rationale | 16 | 8 |
| Analyze minimal resources needed for OTS library on restricted devices | 8 | 4 |
| PR process revisions and merge | 8 | 4 |

</details>

### 10. (Stretch) Xmr Signer Pure (Rewrite in C++) (98 hours)

If I have the mega flow, I will continue here to move substitute the Python code
to C++. Why C++ and not Go or not Rust? First I'm still learning daily in C++, but
the more important reason, I think there is a benefit in thinking on a bare metal
XmrSigner NG in future. [circle](https://github.com/rsta2/circle) and [libcamera](https://github.com/rsta2/libcamera)
would make it possible to run XmrSigner on bare metal what is a C++ environment...
So done this here well, most of the work would be already done for the next step.

<details>
<summary>View tasks</summary>

| Task | Hours | Sessions |
|------|-------|----------|
| Build environment | 6 | 3 |
| Screen | 8 | 4 |
| UI | 12 | 6 |
| Logic | 20 | 10 |
| OTS | 4 | 2 |
| CBOR | 8 | 4 |
| BCUR | 8 | 4 |
| Zxing | 12 | 6 |
| Cam | 20 | 10 |

</details>

### 11. (Stretch) JNI classes (44 hours)

This is another thing I wanted to include but the time constraints will probably not allow it.
One to have a second language using the C ABI with documentation, and second to be used
for Android apps.

<details>
<summary>View tasks</summary>

| Task | Hours | Sessions |
|------|-------|----------|
| Design Java class structure | 10 | - |
| Implement Java wrapper classes | 20 | - |
| Create Java documentation | 10 | - |
| Develop unit tests for Java classes | 4 | 44 |
</details>

## Total Estimated Time

Core Milestones (1-8): 392 hours
Optional/Stretch Milestones (9-11): 224 hours
Grand Total: 616 hours

*Note: This timeline is an estimate and may be subject to adjustments as the project progresses. The sessions are based on the Pomodoro technique to maintain high focus and productivity throughout the project.*
  
Given the significant time investment and potential challenges ahead, I
propose a shift from my usual value-based pricing to an monthly rate for
this project.

Proposed terms:
- 65 Promodoro Sessions (130 hours) per month for three months (196 sessions in total, first month one extra session)
- Compensation: 1 XMR per session, making 66 XMR first and 65 XMR second and 65 third month. (196 in total)
- I would kindly request a 20 xmr upfront on start from the first month.
- Total compensation: 196 XMR

Hours worked beyond in the running month shall roll over to the next month. If I can work some time out I will work
on the optional/strech goals. If time is missing to get milestone 1-8 done in the calculated hours, I will work hours for free to get it done - I always do.

I will commit every day my work, on starting each repository I will advertise them here in a comment an push my commits every day.
And I will create a repository/blog or something as a daily logbook to document the work done and the daily progress.

<details><summary>I set up a [website](https://diosdelrayo.github.io) which syncronizes my actual pomodoro sessions, and the last 48 hours the work done</summary> on which tasks and how many sessions, even each unit time, so it is more transparent. On the way I plan to render also all tasks with the total time and a calendar. But the raw data is available in the issues of the [github repository](https://github.com/DiosDelRayo/DiosDelRayo.github.io) of the site. The time worked on each task can be calculated by the label and unlabeling of `WIP` label is start to work and unlabel end of work on it.
</details>
