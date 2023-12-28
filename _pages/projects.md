---
layout: page
title: research
permalink: /projects/
description: 
nav: true
nav_order: 2
horizontal: false
---

My research focuses on both fundamental algorithms (learning-augmented algorithms, online resource allocation algorithms) and their applications in sustainable and efficient AI systems. Recent projects are summarized as below.

## Learning-Augmented Algorithms ##
Learning-augmented algorithms utilize ML advice or
data-driven methods in algorithm design to improve the empirical performance with theoretical guarantee. In many mission-critical systems such as data centers, energy systems, edge/cloud computing,
and transportation systems, classic expert
algorithms or policies have worst-case performance
guarantee or have been programmed in the real world for a
long time, so they can be trusted in terms of some critical
performance metrics. However, they may not achieve a satisfactory empirical performance on average. 
Therefore, we design learning-augmented algorithms for various problems to improve the average reward while guaranteeing the critical metrics.

**Learning-Augmented Online Optimization and Control** 
Online optimization/control models numerous applications such as robot tracking, data center resource provisioning, battery manage-
ment for EV charging station, cooling system control, etc. The goal of policy design is to minimize
the expected cost E[cost(π)] while guaranteeing competitiveness which means that for each sequence,
the cost is upper bounded by the cost of an expert algorithm scaling by a preset parameter λ ≥ 0,
i.e. cost(π) ≤ (1 + λ)cost(π†) with π† being the expert algorithm. To achieve this goal, the proposed
learning-augmented algorithms design safe action sets based on expert policy and project the
ML outputs into the safe action sets as shown in Figure 2. Importantly, we provide reservation designs
Figure 2 – Robust decision-making to guarantee the nonempty of safe action sets and provably guarantee competitiveness for any sequence sample.
