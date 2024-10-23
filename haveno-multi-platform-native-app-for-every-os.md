---
layout: wip
title: Haveno Multi-Platform Native App for Android, iOS, Windows and Linux.
author: Kewbit
date: August 19, 2024
amount: 215
milestones:
  - name: Create the User Interface
    funds: 75
    done:
    status: unfinished
  - name: Write the Protocol Interface
    funds: 75
    done: 13 October 2024
    status: finished
  - name: Create the Desktop Connector
    funds: 15
    done:
    status: unfinished
  - name: Create Multi-Platform Installers for Windows, Linux, Mac, Android and iOS.
    funds: 50
    done:
    status: unfinished
payouts:
  - date: 23 October 2024
    amount: 75
  - date:
    amount: 75
  - date:
    amount: 15
  - date:
    amount: 50
---
# Haveno Multi-Platform Native App for Android, iOS, Windows, MacOS and Linux

**Author**: Kewbit  
**Date**: 19/08/2024

## Overview

The Haveno Multi-Platform Native App will be an interface for decentralized applications that can connect to the Haveno Daemon, allowing users to conduct transactions in Monero (XMR) using the Haveno decentralized network. Users will be able to buy and sell multiple fiat currencies with their XMR through Haveno. The app will be able through all app stores and installers, or you can build from source.

![Haveno App Montage](https://i.ibb.co/8xvJrPd/Screenshot-20240817-204709-imageonline-co-merged.png "App Montage")
## Security Considerations

- **Open Source**: All software created will be open-source, and only auditable, open-source libraries will be used. The project will be released under the AGPL 3.0 license upon completion.
- **Tor Integration**: The app will enforce Tor usage, requiring users to connect via a Tor VPN relay (such as Orbot or InviZible). Without a Tor connection, the app will not proceed past the splash screen.
- **gRPC Protocol**: The app will connect to Haveno Daemon using the native gRPC HTTP/2 over Tor (not translated from HTTP/1.2 or HTTP/1)
- **Haveno Integration**: The app seamlessly connect to any Haveno Daemon hosted anywhere (using .onion via Tor)
- **Censorship Resistance**: By abstracting the VPN relay away from the app itself and requiring Orbot or InviZible, we avoid potential censorship issues. The app will not require VPN-enabled entitlements that need signing, thus preserving its censorship-resistant nature. The app will be available on [F-Droid](https://f-droid.org/en/).
- **Secure Device Linking**: The app will support secure linking to a running desktop or server instance via a QR code containing a hashed password in the URI of the Onion Link. [Onion Client Authentication](https://support.torproject.org/onionservices/client-auth/) will be available fro advanced users.
- **Native Libraries**: The app with use native library per OS directly from trusted sources.
- **Service Segregation**: Each component of the software will run under it's own service on Dekstop versions, you'll be able to manage the services via a System Tray on Windows, Linux and Mac operating systems.

## Features

- Ability to connect to any Haveno network that you want
- Customize based on your locale
- Ability to see Haveno network trade offers
- Start trades, open your own trades
- Chat with the peer trader
- Open disputes if a transaction isn't working out and chat with an arbitrator
- Manage your payment accounts for both crypto & fiat
- Get notifications when your have new trades or chat messages (local notifications that don't depend on Google's push notification system)
- Deposit and withdraw from your wallet
- Beautiful candlestick trading view for Haveno network activity
- System Tray to manage your Tor & Haveno Daemon services, keep your daemon online without the client open for mobile users.
- Docker image will be available for advanced users contingent on colaberative efforts between the Haveno DEX team.

## Installers Available As:

- **Linux**: **.AppImage**
- **Windows**: A windows **.exe** file.
- **MacOS**: A **.pkg** file or an **.xarchive** file
- **Android**: A **.apk** or **.aab** file
- **iOS**: A **.ipa** file or an **.xarchive** file

## Possible Future Plans

- Matrix integration for server-side notifications to the mobile device (this might be nessesary for iOS users to get notifications reliably and timely.)
- Design the P2P protocol from Haveno in Dart, so that you may not depend on the Haveno Daemon for the app to work (Standalone Mobile App)
- A redesign of the desktop version of the app to fit the Figma design plan in [haveno-design](https://github.com/haveno-dex/haveno-design/blob/master/haveno_mockups.pdf)

## Purpose

### What the Proposal is About

This proposal aims to bring the Haveno / Monero ecosystem together through Haveno with a user-friendly, multi-platform app that considers security, censorship resistance, and hardware wallet support. I would like to continue adding value to this project so am seeking funds to priorize it beyond the 2 months I scoped out myself.

### Who Will Complete the Proposal

Kewbit (kewbitxmr@protonmail.com)

### Why It Is Important for Monero and the Community

This app is crucial for the Monero community because it promotes a censorship-resistant and decentralised ecosystem. There is great difficulty in finding places to trade XMR due to certain website closures and crackdowns. By intending to make the app available on multiple OS and platforms, including on F-Droid, Play Store, and App Store, we ensure that it reaches a wide audience, including those who prefer non-traditional Android phones using Play Store.

## Milestones and Projected Timeline

- **Create the User Interface**
  - **Funds**: 75 XMR
  - **Status**: Started

- **Write the Protocol Interface**
  - **Funds**: 75 XMR
  - **Status**: Started

- **Create the Desktop Connector**
  - **Funds**: 15 XMR
  - **Status**: Started

- **Create Multi-Platform Installers for Windows, Linux, Mac, Android, and iOS**
  - **Funds**: 50 XMR
  - **Status**: Started

## Payouts

- **10/11/2024**: 75 XMR
- **10/11/2024**: 75 XMR
- **10/11/2024**: 15 XMR
- **01/12/2024**: 50 XMR

## Expiration Date

I do not intend for there to be an expiration date. I plan to release the app quickly as I am working on it full-time, even before producing a CCS. I see this as an ongoing project but expect to have a beta absolute latest by 31st December 2024. 

## Alpha Builds
You can check out the current source and alpha builds.

https://github.com/KewbitXMR/haveno-plus/ (Name of project is subject to change, as is the organisation)

I provider further updates regularly on my blog which you can subscribe to if interested at [Kewbit.org](https://kewbit.org) you can also find [my current public key](https://kewbit.org/public-key/), which I would encourage you to import into your PGP client.

