---
title: "Backend"
layout: archive
permalink: /categories/Backend/
taxonomy: Backend
sidebar:
  nav: "docs"
---

{% assign posts = site.categories['Backend']%}
{% for post in posts %}
  {% include archive-single.html type=page.entries_layout %}
{% endfor %}
