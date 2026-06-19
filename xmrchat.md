---
layout: cp
title: XMRChat - a service for content creators to receive messages and tips in Monero.
author: FiatDemise
date: December 8, 2024
amount: 114
milestones:
  - name: Milestone 1 - MVP (minimum viable product) using LWS
    funds: 40
    done: August 4, 2024
    status: finished
  - name: Milestone 2 - video display of xmrchats with Streamyard and OBS, find creator page, private xmrchats, making repo open source
    funds: 30.56
    done: November 20, 2024
    status: finished
  - name: Milestone 3 - creator specific minimum tip amount, links to more creator content + new tab UI for that and other settings, audio tip received notification, How To section in FAQ, old xmrchats expiration, admin page, site monitoring.
    funds: 17
    done: 2 June 2025
    status: finished
  - name: Milestone 4 - on screen special effects and notifications based on tip tier, moderator / cohost page, feature currently live streams, fee system
    funds: 27
    done: 5 June 2026
    status: finished    
payouts:
  - date: 19 March 2025
    amount: 70.56
  - date: 1 July 2025
    amount: 17
  - date: 19 June 2026
    amount: 27
---

_Note: 70.56XMR has been awarded to XMRChat from [TipXMR](https://ccs.getmonero.org/proposals/tipxmr.live.html)_

Who?

Douglas Tuman - Host of popular YouTube show, Monero Talk. Host of weekly show Monerotopia livestreamed in multiple platforms. Creator of Monerotopia annual conference - monerotopia.com. Creator of the Copamonero annual Monero-sponsored soccer tournament - copamonero.com. Sets up booth/tent at Libertarian party conventions and Porcfest to spread Monero awareness. Creator of gratuitas.org coffee beans business (and coffee brewer/bartender at XMR meetups/conventions. Founder of xmrbazaar.com online, p2p marketplace. Founder of plug-n-play XMR node implementation, the Nodo - moneronodo.com. X handle @DouglasTuman.

FiatDemise - Guy with project management experience that joined the Monero community in 2020. Helped save Kuno (kuno.anne.media) and volunteers time there as a moderator. Contributed to testing and provided feature feedback for xmrbazaar. Created a Monero for All brochure that is available in several languages and was distributed at Porcfest 2024. X handle @FiatDemise.

Saeed - Front-end web developer found via Monero Jobs & Proposals Telegram group, GitHub https://github.com/sa8ab. Developed dex alcor.exchange, github.com/avral/alcor-ui. Created raceroms.com. Has a network of other front and back end developers he partners with.

What?

XMRChat is website that provides content creators with a service, allowing them a way to receive messages and tips in Monero. We launched https://xmrchat.com/ on 8/4/2024, using it for the first time in MoneroTopia episode 177, where Doug interviewed Saeed, going over the project and what the site is capable of. https://www.youtube.com/watch?v=f1sy8ICsgBQ. We are looking to raise a total amount of 114 XMR at this time, split in 4 milestones as seen above.

Website: https://xmrchat.com/
X Account: https://x.com/xmr_chat
Code: https://github.com/sa8ab/xmrchat

How we got started?

In early 2024, FiatDemise was watching a streamer, one that accepts tips from viewers and reads their messages as part of their show. They accept fiat using YouTube Superchats, Rumble Rants, and Streamlabs. They publicly stated they’d like to accept crypto too. FiatDemise started a conversation with their staff to try to get them to use Luke Smith’s Shadowchat. FiatDemise volunteered to pay for a company to install and configure it too. After some promising back and forth, FiatDemise got a response saying the team’s web dev / admin was too busy with current projects and they didn’t want to devote any time towards installing or managing Shadowchat. FiatDemise learned that the market wanted a very simple solution that doesn’t require any installation, hosting, or technical knowledge.

At the time, FiatDemise was volunteering as a tester for xmrbazaar and raised the idea of a simple, hosted superchat solution in that Matrix group. Doug supported it right away, and we began working on requirements and giving shape to the vision with a Balsamiq wireframe. We worked with one developer to create a rough proof of concept. Then we found Saeed, a talented developer who could take the project to the next level. We saw the limitation of RPC, only being able to monitor incoming tips for one wallet, which wouldn’t work with the goal of hosting a solution for many content creators. After research, trial and error, and consultations with VTNerd and Radanne, we got LWS to work. After several more updates, the MVP was launched.

