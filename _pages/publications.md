---
layout: page
permalink: /publications/
title: Publications
description:
years: [2025,2024, 2023, 2022, 2021, 2020, 2019, 2018, 2017, 2016, 2015, 2014, 2013, 2012, 2011, 2010, 2009, 2007]
nav: true
nav_order: 2
---
<!-- _pages/publications.md -->
* **Orcid ID:** [0000-0003-2192-4416](https://orcid.org/0000-0003-2192-4416)
* **ResearcherID:** [A-9752-2009](https://www.webofscience.com/wos/author/rid/A-9752-2009)
* **Google Scholar:** [8kg1qzsAAAAJ](https://scholar.google.com/citations?user=8kg1qzsAAAAJ)
* **HAL (open archive):** [dralucas](https://cv.archives-ouvertes.fr/dralucas)

{%- capture venue_template -%}{% raw %}
{{ reference }}{% assign venue = entry.journal
  | default: entry.booktitle
  | default: entry.institution
  | default: entry.school
  | default: entry.publisher %}
{% if venue %} <em>{{ venue }}</em>{% endif %}
{% endraw %}{%- endcapture -%}


<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}
</div>

<br>
<h1 class="post-title">Other publications</h1>

<div class="publications">
  {% bibliography -f others --template venue_template %}
</div>

