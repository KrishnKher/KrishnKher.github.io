---
layout: page
permalink: /publications/
title: Publications
description: >
    <p>Only selected manuscripts/publications have been displayed here. For a list of all acknowledged works that I have participated in, please check my Google Scholar/dblp profile(s). <br>
    <b>Note</b>: Publications with a <span>\"†\"</span> symbol appended to the immediate right of my name indicate my first (co-)authorship therein.</p>

nav: false
nav_order: 2
display_categories: [Machine Learning, TCS/Math, Systems]
---

<!-- _pages/publications.md -->

<!-- Bibsearch Feature -->

{% include bib_search.liquid %}

<div class="publications">

{% bibliography --file papers %}

{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_publications = bibliography | where: "category", category %}
   {% for publication in categorized_publications %}
      {% include bib.liquid %}
    {% endfor %}
    {% endfor %}
{% endif %}

</div>
