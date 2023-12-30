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

In some problems such as smoothed online convex optimization and online control, the agent has access to dynamic models and reward/cost models and the challenges mainly come from the uncertainty of future context. We propose expected robustified learning algorithms (see [NeurIPS'23](https://arxiv.org/pdf/2310.20098.pdf), [INFOCOM'23](https://arxiv.org/abs/2305.00677)) that provably guarantee competitiveness. It is more challenging to guarantee competitiveness in more general decision-making problems where the agent has no access to dynamic models or reward/cost models. For these problems, we design Anytime-Competitive Reinforcement Learning (see [NeurIPS'23](https://arxiv.org/pdf/2311.01568.pdf)) which defines safe action sets to guarantee the constraint satisfaction for any instance. 

**Learning-Augmented Online Allocation and Matching**
Online resource allocation (with continuous actions) and online bipartite matching (with discrete actions) model many key problems in sustainable computing, network resource management, inventory management, online advertising, etc. In these problems, the solutions must satisfy strict long-term budget constraints, e.g. in sustainable computing, the total carbon emission should not exceed a carbon budget. 
Even with the expert policy priors, the budget constraints make the learning-augmented designs for these problems even more challenging. With the goal of improving the statistical performance subject to the worst-case guarantee, we design the first learning-augmented algorithm for online allocation with replenishable budgets on the basis of the proposed competitive algorithm OACP (see [SIGMETRICS'24](https://drive.google.com/file/d/1XscszklITzTUpR83hbU2agudw9uAiEoL/view)). In addition, we design the first learning-augmented online switching algorithm for online bipartite matching (see [ICML'23](https://jianyiyang-ai.github.io/publications/)). 

**Knowledge Informed Learning**
Learning-augmented algorithms is an important direction in knowledge informed learning which utilizes domain knowledge in ML to achieve better generalization, robustness, and interpretability. Thus, a rigorous analysis of knowledge informed learning is necessary to understand the effects of domain knowledge in machine learning. Our study considers a general framework which integrates domain knowledge in the training objective and shows how the quality of domain knowledge affect the generalization performance (see [ICML'22](https://proceedings.mlr.press/v162/yang22l/yang22l.pdf)). As a concrete example, a training algorithm based on expert knowledge is developed for smoothed online convex optimization and achieve better performance than pure ML (see [SIGMETRICS'22](https://arxiv.org/pdf/2204.08572.pdf)).



## AI and Sustainability ##
Large AI models have witnessed remarkable success in recent years. As more and more large AI models are deployed in data centers, the energy consumption of data centers has been rapidly increasing. Thus, the environmental footprints of AI have become a concern that cannot be ignored (see our study on [AI water footprints](https://arxiv.org/pdf/2304.03271.pdf)). My research aims to address the key challenges from sustainable AI and computing. First and foremost, we optimize the environmental efficiency of data centers by designing new resource allocation and load balancing algorithms which are aware of the new requirements and objectives of sustainable AI. In addition, we develop new methods to optimize the inference efficiency of neural architectures for diverse hardware systems.


**Fundamental Resource Allocation Algorithms**
Online allocation with budget constraints is a key technique for sustainable AI. To improve the environmental efficiency of data centers where AI models are deployed, the data center operator needs to decide when and where to allocate energy (or equivalently schedule the workload) to make full use of the renewables which are time-varying and notably hard to predict.  Thus, the key challenge to meet the environmental requirements is to decide the allocations subject to energy budget constraints which can be replenished by renewables. Our research designs algorithms for these problem with the guarantees of asymptotic competitive ratio and proposes learning-augmented algorithm to improve the statistical performance under the worst-case performance guarantee (see [SIGMETRICS'24](https://drive.google.com/file/d/1XscszklITzTUpR83hbU2agudw9uAiEoL/view)).

**Environmentally Equitable Computing**
AI models are often deployed in data centers with different locations and have regional environmental impacts. Thus, besides environmental efficiency, we should also consider geographical environmental justice when we decide when and where to schedule the AI workloads (as is pointed out by [Environmentally Equitable AI](https://arxiv.org/abs/2307.05494)).  Our research designs new geographical load balancing algorithms that jointly optimize the service latency and the environmental justice relying on the regional footprints. 

**Hardware-efficient and user-centered Neural Architecture Search**
Hardware-aware Neural Architecture Search (NAS) is to optimize multiple performance metrics of AI models (accuracy, latency, energy consumption) when they are deployed on hardware systems. To complete hardware-aware NAS, we need to evaluate the performances of AI models on various devices. However, building a latency or energy predictor for various devices requires significant effort of measurements. We design novel methods that exploit latency monotonicity of different types of devices to significantly reduce the measurements (see [SIGMETRIC'22](https://arxiv.org/pdf/2111.01203.pdf)).

Another problem of AI deployment for diverse devices is to optimize the user experience which depends on accuracy latency, energy, etc. Our studies develop user-centered online learning algorithms to select AI models for edge users, improving the user experience asymptotically (see [IOTJ'22](https://ieeexplore.ieee.org/abstract/document/9795664?casa_token=otBMbLQqXpUAAAAA:PqGO6w8ybjy6qLhEF1qLbA4DPLwJe4cnNGvBLFnxFL3H8TP9TlGHgpwO0FJyx7zm8nPDs_OWsI0)).

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
