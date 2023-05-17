---
title: "Backend"
layout: archive
permalink: /categories/Backend/
taxonomy: Front
sidebar:
  nav: "docs"
---

{% assign posts = site.categories['Backend']%}
{% for post in posts %}
  {% include archive-single.html type=page.entries_layout %}
{% endfor %}
