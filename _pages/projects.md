---
layout: page
title: projects
permalink: /projects/
description: A growing collection of your cool projects.
nav: true
nav_order: 3
display_categories: [work, fun]
horizontal: false
---

- #### Exploring Complex Regularization techniques for Image Classification

  Report []

  - Analyzed impact of dropout, data augmentation, ridge, and ensemble regularization of performance of convolutional neural network built to classify 15 classes from tiny ImageNet dataset.
  - Conceptualized Mobile Inverted Bottleneck layers and compound scaling of EfficientnetB0 and implemented various regularization techniques for ImageNet dataset.

- #### Fine-tuning Large Language Models with Romanized Text
  Report []
  - Devised methods to finetune Meta’s Tiny-llama and Microsoft’s Phi-2 large language models (LLMs) using low rank adapters for sentiment analysis and machine translation for non-Latin languages Hindi and Korean
  - Established the positive impact of romanization, pretraining and continual finetuning on performance of LLMs
- #### Applying NLP to understand aviation safety problems on US runways

  Website []

  - Devised methods to finetune Meta’s Tiny-llama and Microsoft’s Phi-2 large language models (LLMs) using low rank adapters for sentiment analysis and machine translation for non-Latin languages Hindi and Korean
  - Established the positive impact of romanization, pretraining and continual finetuning on performance of LLMs

- #### Student Interest Group Prediction
  Report []
  - Developed a student recommendation system for higher education institutions.
  - Utilized clustering analysis to identify student groups with similar interests.
  - Contributed to the field of Educational Data Mining (EDM) by applying it to enhance student connections with relevant interest groups.

<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_projects = site.projects | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
