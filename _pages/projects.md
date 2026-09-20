---
layout: page
title: Projects
permalink: /projects/
description: Government-sponsored initiatives, enterprise LLM safety benchmarks, and adaptive multi-agent frameworks built at RespAI Lab.
nav: true
nav_order: 2
display_categories: [funded, research, platforms]
horizontal: false
---

<div class="projects">
  <!-- Editorial Project Hero Header -->
  <div class="header-bar project-hero">
    <div class="project-hero-badge">
      <i class="fa-solid fa-diagram-project"></i> Systems & Benchmarks
    </div>
    <h1 class="project-hero-title">Research Projects</h1>
    <p class="project-hero-subtitle">
      Government-sponsored initiatives, enterprise LLM safety benchmarks, and deployed production platforms.
    </p>
  </div>

  <!-- Categorized Project Sections -->
{% for category in page.display_categories %}
    {% assign categorized_projects = site.projects | where: "category", category %}
    {% assign sorted_projects = categorized_projects | sort: "importance" %}

    <section class="project-section-wrapper mb-5" id="{{ category }}">
      <div class="project-category-header">
        <h2 class="category-heading">
          {% if category == 'funded' %}
            <i class="fa-solid fa-building-columns"></i> Funded Research Initiatives
          {% elsif category == 'research' %}
            <i class="fa-solid fa-flask-vial"></i> Core Research & Open Benchmarks
          {% elsif category == 'platforms' %}
            <i class="fa-solid fa-rocket"></i> Production Systems & Web Platforms
          {% else %}
            {{ category | capitalize }}
          {% endif %}
        </h2>
        <span class="project-count-pill">{{ sorted_projects.size }} {% if sorted_projects.size == 1 %}Project{% else %}Projects{% endif %}</span>
      </div>

      <div class="row row-cols-1 row-cols-md-2">
        {% for project in sorted_projects %}
          {% include projects.liquid %}
        {% endfor %}
      </div>
    </section>
{% endfor %}
</div>
