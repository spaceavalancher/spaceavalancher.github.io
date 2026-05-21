---
layout: page
permalink: /publications/
title: Publications
description:
years: [in review, 2026, 2025, 2024, 2023, 2022, 2021, 2020, 2019, 2018, 2017, 2016, 2015, 2014, 2013, 2012, 2011, 2010, 2009, 2007]
nav: true
nav_order: 2
---

<!-- _pages/publications.md -->

* **Orcid ID:** [0000-0003-2192-4416](https://orcid.org/0000-0003-2192-4416)
* **ResearcherID:** [A-9752-2009](https://www.webofscience.com/wos/author/rid/A-9752-2009)
* **Google Scholar:** [8kg1qzsAAAAJ](https://scholar.google.com/citations?user=8kg1qzsAAAAJ)
* **HAL (open archive):** [dralucas](https://cv.archives-ouvertes.fr/dralucas)
  
<div class="pub-links">
  <strong>Jump to:</strong>
  {% for y in page.years %}
    {% assign y_string = y | append: "" %}
    {% assign y_id = y_string | replace: " ", "-" %}
    <a href="#pub-{{ y_id }}">{{ y }}</a>{% unless forloop.last %} · {% endunless %}
  {% endfor %}
  · <a href="#comments-news-views-perspectives">Comments, News &amp; Views and Perspectives</a>
  · <a href="#proceedings-chapters-white-papers">Proceedings, chapters and white papers</a>
  · <a href="#thesis">Thesis</a>
</div>

<div class="publications">

{%- for y in page.years %}
  {% assign y_string = y | append: "" %}
  {% assign y_id = y_string | replace: " ", "-" %}
  <h2 id="pub-{{ y_id }}" class="year">{{ y }}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>

<h1 id="comments-news-views-perspectives" class="post-title">Comments, News &amp; Views and Perspectives</h1>

<div class="publications">
  {% bibliography -f comments %}
</div>

<h1 id="proceedings-chapters-white-papers" class="post-title">Proceedings, chapters and white papers</h1>

<div class="publications">
  {% bibliography -f others %}
</div>

<h1 id="thesis" class="post-title">Thesis</h1>

<div class="publications">
  {% bibliography -f thesis --template thesis %}
</div>
