---
layout: post
title: "Peninsulas and Islands: When the Internet Is Only Partly There"
date: 2026-09-30
paper_authors: "Guillermo Baltra, Tarang Saluja, Yuri Pradkin, John Heidemann"
paper_venue: "NINeS 2026"
paper_url: "https://2026.nines-conference.org/papers/p004-Baltra.pdf"
week: 2
tags: [routing, reachability, measurement]
---


## Key Idea

Most outage research treats reachability as on or off. But peering disputes, firewalls, and routing hiccups often leave a network able to reach only part of the Internet. Baltra et al. define the Internet core as the active public addresses that can reach more than half of all such addresses, which means there can only ever be one core. They then look for *peninsulas* (stuck with partial connectivity) and *islands* (cut off entirely) in existing Trinocular and RIPE Atlas data. It turns out peninsulas are about as common as outages, and 90% of peninsula-time comes from a handful of long-lived events.

## Critique

I like the majority definition a lot, since it doesn't need anyone in charge. The DNSmon result is also pretty convincing: what looked like DNS root loss was mostly islands and peering fights. The validation is shakier, though. Precision against CAIDA Ark is somewhere between 0.42 and 0.82, Trinocular has only six vantage points, and the causes are guessed from where traceroutes stop.

## Connections

Gao-Rexford promises BGP converges, not that everyone can reach everyone. Peer routes never go to other peers, so when two ISPs refuse to peer (Hurricane Electric and Cogent over IPv6), you get a perfectly stable peninsula.