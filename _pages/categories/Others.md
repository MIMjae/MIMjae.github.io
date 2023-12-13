---
title: "Others"
layout: archive
permalink: /categories/Others/
taxonomy: Others
sidebar:
  nav: "docs"
---

{% assign posts = site.categories['Front']%}
{% for post in posts %}
  {% include archive-single.html type=page.entries_layout %}
{% endfor %}
