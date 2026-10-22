---
layout: post
title: "Which Congestion Signals Are Worth Header Space?"
date: 2026-10-14
paper_authors: "Sarah McClure, Nandita Dukkipati, Sylvia Ratnasamy, Scott Shenker"
paper_venue: "NINeS 2026"
paper_url: "https://2026.nines-conference.org/papers/p012-McClure.pdf"
week: 4
tags: [congestion-control, in-network-telemetry, datacenter]
---


## Key Idea

Switches can now report in-network telemetry (INT) like queue length or link utilization. But header space and ASIC support are limited, so vendors have to pick. To judge a signal without tying it to one algorithm, McClure et al. learn a near-optimal algorithm for each signal set with R+, a souped-up Remy. The surprise: on average, INT is within about 3% of plain end-to-end signals (RTT plus send and receive rates), and the INT signals are within 1% of each other. Link signals lean toward low delay and queue signals toward throughput.

## Critique

The method is really the contribution here. The BBR and DCTCP checks sold me, since simple RTT thresholds got the same gains as INT. Still, a learned algorithm is standing in for the optimal one, averages hide tails, and the topologies are just dumbbells and lines with no incast. The part I'd want more on: one-way signals helped no matter what they measured, so maybe delivery matters more than content.

## Connections

[Ware et al.](https://dl.acm.org/doi/10.1145/3365609.3365855) warned that one number can hide who gets hurt, and "within 3% on average" has the same problem. Signals also steer routing: the load balancer in
pmecmp post, re-paths flows on ECN marks.