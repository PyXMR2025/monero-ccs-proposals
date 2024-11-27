---
layout: fr
title: Gingeropolous 1TB MRC upgrade
author: Gingeropolous
date: November 9, 2024
amount: 20
milestones:
  - name: Install 1TB ram in new epyc server
    funds: 100% (20 xmr)
    done:
    status: unfinished
payouts:
  - date:
    amount:
---


1TB ram for new MRC server

I finally purchased a new epyc server, and I need to get ram for it. I was just going to get the minimal needed to make the thing mine some xmr, but figured we can pack this thing to the gills to provide some monstrous compute capacity for monero R&D.

For some background, I manage the Monero Research Computing cluster, which is essentially just my mining rigs that I've put more ram and storage in. I provide access to the MRC to various monero researchers and developers, so they can get some stuff done. The rigs mine when there is no activity by the users. 

Currently, monero researchers are primarily using the box "Junior", which is a 64 thread AMD Ryzen Threadripper 3970X with 256 GB ram (max ram for the mobo). There is a 5x nvme striped lv thingy that allows for some fast swap, but its still just swap. This rig was upgraded years ago through the CCS (https://ccs.getmonero.org/proposals/gingeropolous_zenith_storage.html) to provide ample storage space for researchers (74 TB HDD - funded by me, 14TB nvme - funded by CCS), as working with the monero blockchain requires storing and moving massively large files. I have other boxes, but they are your average mobo that can take a max 128 GB. Rucknium has been able to do some distributed compute across all the boxes (at one point 7 or so boxes?), but I've found most folks just want a single box with massive amounts of ram. 

This proposal is for funds for me to purchase 1 TB of ram to install in a new 2x 7h12 server (256 threads!) so monero researchers can stop fiddling with memory constraints when working or waiting for the poor 64 threads to chug through their tasks. The system maxes out at 4 TB (!!!!), so perhaps if funding goes over the request and hits enough to get more ram, then that will happen. 

This is important for the community because more compute ==  more research capabilities for monero researchers. This request was already brought up during a monero research lab meeting, and the members were interested in adding this capacity to our cluster. 

Milestone 0 isn't included, because its me purchasing the 2x epyc server. I just did that. So thats done. 

Milestone 1 is when I have the 2x epyc server up and running with 1TB of ram installed. I'll take a screen shot and upload it. 
Timeline: 3 months? This should all be done by 2025-02-01 at the latest, but I expect this to be up and running by 2025-01-01.

Amount: I plan on purchasing this ram:
https://www.ebay.com/itm/225753803091

So that comes out to around 15 xmr. I'm requesting 20 xmr for some padding and to pay for some of my time and I'll probably end up buying more stuff I wouldn't need for mining (like a 4TB nvme for the box because always more storage). If I receive a lot over the requested amount, I'll consider either finding higher quality ram (anyone have any input on that A-tech stuff?) or more ram. 

