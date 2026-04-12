---
layout: page
title: Resources
permalink: /projects/
description:
nav: true
nav_order: 4
display_categories: [datasets, software, teaching]
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
  · <a href="#videos">Videos</a>
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

<section id="videos" class="resource-videos">
  <h2 class="category resource-videos-title">Videos</h2>

  <div class="video-entry">
    <h3 id="avalanche-de-debris-responsable-dun-tsunami-dans-un-fjord-au-groenland">Avalanche de débris responsable d&#39;un tsunami dans un Fjord au Groenland</h3>
    <p>Animation réalisée en 2024 pour la publication {% cite svennevig:insu-04725704 %}</p>
    <div class="video-embed">
      <iframe width="500" height="250" src="https://www.youtube.com/embed/POq5UPN2kmY" title="Avalanche de débris responsable d&#39;un tsunami dans un Fjord au Groenland" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
    </div>
  </div>

  <div class="video-entry">
    <h3 id="dynamique-des-paysages-dans-le-systeme-solaire">Dynamique des paysages dans le système solaire</h3>
    <p>École d'été du CLEA 2016 au Col Bayard, synthèse des travaux qui ont donné lieu aux publications {% cite lucas:insu-02320751 lucas:hal-01072249 Lucas_2014 Rodriguez_2014 lucas:hal-01233073 charnay:hal-01223167 %}</p>
    <div class="video-embed">
      <iframe src="https://media.tremplin.ens-lyon.fr/media/2016/20160823/AntoineLucas/Video/20160823_antoinelucas.mp4" width="500" height="250"></iframe>
    </div>
  </div>

  <div class="video-entry">
    <h3 id="exploration-des-mers-de-sable-sur-titan">Exploration des mers de sable sur Titan</h3>
    <p>Journée scientifique du labex UnivEarthS du 16 mai 2014 à AIM/CEA, {% cite Lucas_2014 %}</p>
    <div class="video-embed">
      <iframe src="https://www.youtube.com/embed/5IJql3HQj7w?start=393" width="500" height="250"></iframe>
    </div>
  </div>
</section>
