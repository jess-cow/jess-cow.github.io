
---
layout: page
permalink: /publications/
title: Publications
description: Here are my publications 🥳 
nav: true
author_profile: true
nav_order: 3
---
<!-- _pages/publications.md -->
<div class="publications">
The full list is on 
<a href='https://inspirehep.net/authors/1978707?ui-citation-summary=true' style='color: #6ab0d6;'> INSPIRE </a>

{% bibliography -f {{ site.scholar.bibliography }} %}

</div>
{% if site.author.googlescholar %}
  <div class="wordwrap">You can also find my articles on <a href="{{site.author.googlescholar}}">my Google Scholar profile</a>.</div>
{% endif %}
{% bibliography -f {{ site.scholar.bibliography }} %}
{% include base_path %}

<!-- New style rendering if publication categories are defined -->
{% if site.publication_category %}
  {% for category in site.publication_category  %}
    {% assign title_shown = false %}
    {% for post in site.publications reversed %}
      {% if post.category != category[0] %}
        {% continue %}
      {% endif %}
      {% unless title_shown %}
        <h2>{{ category[1].title }}</h2><hr />
        {% assign title_shown = true %}
      {% endunless %}
      {% include archive-single.html %}
    {% endfor %}
  {% endfor %}
{% else %}
  {% for post in site.publications reversed %}
    {% include archive-single.html %}
  {% endfor %}
{% endif %}



