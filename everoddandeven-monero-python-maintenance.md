---
layout: fr
title: "Monero Python Maintenance"
author: everoddandeven
date: July 18, 2025
amount: 23.43
milestones:
  - name: First stable release + All documentation
    funds: 23.43 XMR
    done:
    status: unfinished
payouts:
  - date:
    amount:
---

# Monero Python Maintenance

## What
[monero-python](https://github.com/everoddandeven/monero-python) is a project that exposes and extends [monero-cpp](https://github.com/woodser/monero-cpp) classes and functionality through python bindings (pybind11). I believe this library could be an excellent starting point for python developers looking to build monero applications, as it offers a robust and conceptually uncluttered API model. 

Furthermore, as mentioned earlier, the monero-python library implements classes such as [MoneroDaemonRpc](https://github.com/everoddandeven/monero-python/blob/main/src/cpp/daemon/py_monero_daemon.h#L2720) and [MoneroWalletRpc](https://github.com/everoddandeven/monero-python/blob/main/src/cpp/wallet/py_monero_wallet.h#L3796) (and relative data model), which are not offered by the monero-cpp library. These additional RPC client implementations are fully written in CPP and linked through Python bindings, just like monero-cpp objects. Implementing these classes required writing a non-trivial amount of code (and time) that needs to be properly tested, fixed, and, where possible, improved.

One of the library's strengths is the ability to use a [MoneroWalletFull](https://github.com/woodser/monero-cpp/blob/master/src/wallet/monero_wallet_full.h) (full wrapper of wallet2.cpp) instead of a remote MoneroWalletRpc. This locally managed wallet allows developers and users to avoid the burden of configuring a [monero-wallet-rpc](https://docs.getmonero.org/rpc-library/wallet-rpc/) server, or manage even multiple wallets locally. Furthermore, the project is open to implementing additional features and possible new bindings e.g. for a hypothetical (perhaps not so much) [MoneroWalletLight](https://github.com/woodser/monero-cpp/pull/73).

I propose to finish this work by myself, as I believe that this library could significantly contribute to the entire Monero ecosystem, and possibly replace other unmaintained monero python libraries (e.g legacy [monero-python](https://github.com/monero-ecosystem/monero-python) library), as it offers everything a python developer needs to build scripts and applications without having to implement custom logic, thanks to a simple and powerful API. Overall, it could be an excellent entry point for those who want to get started without having to have in-depth knowledge of strong-rule programming languages.

## Demo
An example of how this library can be used can be found here [[PR] Upgrade Monero integration to support Odoo 15.0](https://github.com/monero-integrations/moneroodoo/pull/20). In that PR I have adapted the moneroodoo plugin code to the later versions of the odoo software. In these adjustments, the legacy monero-python library was deprecated with this new API.

This made it possible to add a new feature: the possibility to use a local wallet (only primary address and view key are needed in configuration), in addition to the classic remote RPC wallet, requesting the user only the configuration of the address of a trusted RPC node, allowing odoo shop owners to immediately accept Monero as payment, making the configuration burden of a monero-wallet-rpc optional.

## What's Missing

The example above covers a minimum part of the cases of use of this library. Although a high degree of completeness of the data model and implementations has been achieved, currently to achieve a complete and production-ready product, the library needs:

1. Implement any missing features regarding rpc clients
2. Move implementations to cpp files (currently everything is implemented in header files, it's just a sign of my laziness, sorry)
3. Code reorganization and refactory, were neeeded 
4. Implement more tests, in order to achieve a decent test coverage, especially for rpc clients
5. Fix for bugs found during testing
6. Move consolidated RPC implementations and data model to monero-cpp ([PR - RPC Daemon and Wallet Implementation](https://github.com/woodser/monero-cpp/pull/87))
7. Build and test packages for Windows and MacOS
8. Build and deploy documentation pages
9. Extend Linux package support more architetures (arm64, armhf)
10. Docker build support
11. Implement a PoC application as reference for developers

Following the completion of all these points, I will make the release of the first stable version of this library.

## Funding
**Timeframe:** 2 months (4 hours/day, 240 total hours)  
**Total:** 23.43 XMR ($8000 USD @ 1XMR/$341, 60-day EMA 2025-11-18 Kraken)  
**Rate:** $33.3/hour (8000 / 240)

As mentioned before, the library is essentially complete in its implementations. However, it needs to cross a testing phase through the implementation of new tests (and bug fixing), this will be the heart of my work in this 2 months. I also want to be able to provide packages ready to be used in production environments and detailed documentation of the whole API in such a way that developer can consult it comfortably and without the need for any help.

## Future Roadmap
- Extended maintenance and support for monero-python
- Publish package on PyPI and official debian/ubuntu repository
- Extend library wallet and daemon support for monero-lws
- Review of any PRs, complete testing and manage releases
- Evaluation of a possible replacement of the current binding technology with [nanobind](https://github.com/wjakob/nanobind), which is more efficient.

## Who Am I?

I am [everoddandeven](https://github.com/everoddandeven), a computer engineering student at University of Pisa close to graduation and with over 3 years of experience in GIS software development. 

- Maybe you will remember [monero-gui](https://github.com/everoddandeven/monerod-gui) a GUI for monerod, based on ElectronJS and Angular.

- But also [monero-ecwid](https://github.com/everoddandeven/monerod-ecwid), a payment processor for ECWID stores.

- My work on the monero light wallet client has been mentioned on the [Monero Community Workgroup Meeting: February 1st 16:00 UTC](https://github.com/monero-project/meta/issues/1149).

- I have also made some microscopic contributions to [haveno-ts](https://github.com/haveno-dex/haveno-ts), [monero-cpp](https://github.com/woodser/monero-cpp), [monero-java](https://github.com/woodser/monero-java) and [monero-lws](https://github.com/vtnerd/monero-lws).

