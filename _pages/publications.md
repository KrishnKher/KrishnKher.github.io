---
layout: page
permalink: /publications/
title: Publications
description: >
    <p>Only selected manuscripts/publications have been displayed here. For a list of all acknowledged works that I have participated in, please check my Google Scholar/dblp profile(s). <br>
    <b>Note</b>: Publications with a <span>\"†\"</span> symbol appended to the immediate right of my name indicate my first (co-)authorship therein.</p>

nav: false
nav_order: 2
display_categories: [Machine Learning, TCS/Math, Systems, Miscellaneous]
---

<!-- _pages/publications.md -->

<!-- Bibsearch Feature -->

{% include bib_search.liquid %}

<div class="publications">

<!-- Thanks to https://github.com/alshedivat/al-folio/issues/1264#issuecomment-1519180549, https://gist.github.com/Teino1978-Corp/325442fda3e3776f49e0#bibliography-filters-->
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
    <a id="{{ category }}" href=".#{{ category }}">
        <h2 class="category">{{ category }}</h2>
    </a>
        {%- capture citecount -%}
        {%- bibliography_count -f {{site.scholar.bibliography}} -q @*[year={{y}} && category={{category}}] -%}
        {%- endcapture -%}

        {%- if citecount !="0" %}

        <h2 class="year">{{y}}</h2>
        {% bibliography -f {{site.scholar.bibliography}} -q @*[year={{y}} && category={{category}}] %}
        {%- endif -%}
  {%- endfor %}
{% else %}
{% bibliography --file papers %}
{% endif %}
</div>
