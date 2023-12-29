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

**Learning-Augmented Online Decision-Making** 
Many system problems such as robot tracking, data center resource provisioning, battery management for EV charging station, cooling system control, etc can be modeled as online decision processes. For various online decision processes, we design novel learning-augmented algorithms to minimize the expected cost (or maximize the expected reward ) while guaranteeing anytime competitiveness. The anytime competitiveness requires that for any sequence, the cost is upper bounded by the cost of an expert policy prior scaling by a preset parameter λ ≥ 0, i.e. cost(π) ≤ (1 + λ)cost(π†) with π† being the expert algorithm. 

In some problems such as smoothed online convex optimization and online control, the agent has access to dynamic models and reward/cost models and the challenges mainly come from the uncertainty of future context. We propose expected robustified learning algorithms (see NeurIPS'23, INFOCOM'23) that provably guarantee competitiveness. It is more challenging to guarantee competitiveness in more general decision-making problems where the agent has no access to dynamic models or reward/cost models. For these problems, we design Anytime-Competitive Reinforcement Learning (see NeurIPS'23) which defines safe action sets to guarantee the constraint satisfication for any instance. 

**Learning-Augmented Online Allocation and Matching**
In many computing systems, the comput- ing resources are finite and limited, so algorithms are needed to to optimize the utility under resource budget constraints. Examples include power allocation for edge computing and data center server provisioning with carbon neutrality. The problem is challenging due to the strict budget constraints, the existence of a budget cap, and the online nature. My study [11, 2] gives a deep unrolling model based on the online primal-dual decision pipeline which can achieve superior average performance . Also, my study designs the first dual mirror descent algorithm for online allocation with replenishment with competitive ratio guarantee. In addition, a learning-augmented algorithm is designed to improve the empirical performance under the provable guarantee of the worst-case performance.

**Knowledge Informed Learning**
The designs of learning- augmented algorithms successfully utilize the domain knowledge. Actually, domain knowledge has been extensively utilized in ML to achieve better generalization, robustness, and interpretability. My study [17] gives the first rigorous analysis about the role of domain knowledge in machine learning and shows how the quality of domain knowledge affect the generalization. We define the metrics of the imperfectness of labels and domain knowledge and show the dependency of the generalization bound on the imperfectness. Also, the analysis of sampling complexity for informed ML establishes a quantitative equivalence between domain knowledge and labeled samples.



## Fundamental Algorithms for Online Resource Allocation ##

**Online Allocation with Budget Replenishment**

**Online Budgeted Maching**

## AI and Sustainability ##
