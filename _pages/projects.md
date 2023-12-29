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
Online resource allocation (with continuous actions) and online bipartite matching (with discrete actions) model many key problems in sustainable computing, network resource management, inverntory mangement, online advertising, etc. In these problems, the solutions must satisfy strict long-term budget constraints, e.g. in sustainable computing, the total carbon emission should not exceed a carbon budget. 
Even with the expert policy priors, the budget constriants make the learning-augmented designs for these problems even more challenging. With the goal of improving the statistical performance subject to the worst-case guarantee, we design the first learning-augmented algorithm for online allocation with replenishable budgets on the basis of the proposed competitive algorithm OACP (see SIGMETRICS'24). In addition, we design the first learning-augmented online switching algorithm for online bipartite matching (see ICML'22). 

**Knowledge Informed Learning**
Learning-augmented algorithms is an important direction in knowledge informed learning which utilizes domain knowledge in ML to achieve better generalization, robustness, and interpretability. Thus, a rigorous analysis of knowledge informed learning is necessary to understand the effects of domain knowledge in machine learning. Our study considers a general framework which integrates domain knowledge in the training objective and shows how the quality of domain knowledge affect the generalization performance (see ICML'22). As a concrete example, a traning algorithm based on expert knowledge is developed for smoothed online convex optimization and achieve better performance than pure ML (see SIGMETRICS'22).



## AI and Sustainability ##
Large AI models have witnessed remarkable success in recent years. As more and more large AI models are deployed in data centers, the energy consumption of data centers has been rapidly increasing. Thus, the environmental footprints of AI have become a concern that cannot be ignored (see our study on AI water footprints). My research aims to address the key challenges from sustainable AI and computing. First and foremost, we optimize the environmental efficiency of data centers by designing new resource allocation and load balancing algorithms which are aware of the new requirements and objectives of systainable AI. In addition, we develop new methods to optimize the inference efficiency of neural architectures for diverse hardware systems.


**Fundamental Resource Allocation Algorithms**

**Environmentally Equitable Computing**

**Hardware-efficient Neural Architecture Search**


<!-- pages/projects.md -->
<div class="projects">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_projects = site.projects | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}

{%- else -%}
<!-- Display projects without categories -->
  {%- assign sorted_projects = site.projects | sort: "importance" -%}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>
