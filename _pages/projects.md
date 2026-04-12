---
layout: page
title: Resources
permalink: /projects/
description:
nav: true
nav_order: 4
display_categories: [datasets, software, teaching, videos]
horizontal: true
compact_cards: true
---
<!-- pages/projects.md -->
This page gathers research datasets, scientific software, teaching resources, and videos associated with my work. Each entry points to a primary repository or archive record, with previews stored locally on this site for long-term stability.

{% assign category_titles = "datasets:Datasets|software:Software|teaching:Teaching|videos:Videos" | split: "|" %}

<nav class="resources-jump-menu">
  <p>
    Browse the collection by section:
  {% for category in page.display_categories %}
    {% assign label = category %}
    {% for entry in category_titles %}
      {% assign parts = entry | split: ":" %}
      {% if parts[0] == category %}
        {% assign label = parts[1] %}
      {% endif %}
    {% endfor %}
    <a href="#{{ category }}">{{ label }}</a>{% unless forloop.last %} · {% endunless %}
  {% endfor %}
  </p>
</nav>

<div class="projects">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  {% assign category_title = category %}
  {% for entry in category_titles %}
    {% assign parts = entry | split: ":" %}
    {% if parts[0] == category %}
      {% assign category_title = parts[1] %}
    {% endif %}
  {% endfor %}
  {%- assign categorized_projects = site.projects | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" %}
  <section id="{{ category }}" class="resource-section">
  <h2 class="category">{{ category_title }}</h2>
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-1">
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
  </section>
  {% endfor %}

{%- else -%}
<!-- Display projects without categories -->
  {%- assign sorted_projects = site.projects | sort: "importance" -%}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-1">
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
