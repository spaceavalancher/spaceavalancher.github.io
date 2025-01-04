---
layout: page
permalink: /publications/
title: Publications
description:
years: [2024, 2023, 2022, 2021, 2020, 2019, 2018, 2017, 2016, 2015, 2014, 2013, 2012, 2011, 2010, 2009, 2008, 2007, 2006, 2005, 2004, 2002, 2001, 2000, 1999, 1998, 1997]
nav: true
nav_order: 2
---
<!-- _pages/publications.md -->
* **Orcid ID:** [0000-0001-7007-4222](https://orcid.org/0000-0001-7007-4222)
* **ResearcherID:** [G-6427-2010](https://www.webofscience.com/wos/author/rid/G-6427-2010)
* **Google Scholar:** [9FWrY48AAAAJ](https://scholar.google.com/citations?user=9FWrY48AAAAJ)
* **HAL (open archive):** [mark-wieczorek](https://cv.archives-ouvertes.fr/mark-wieczorek)

<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>
