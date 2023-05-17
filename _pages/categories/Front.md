---
title: "Front"
layout: archive
permalink: /categories/Front/
taxonomy: Front
sidebar:
  nav: "docs"
---

{% assign posts = site.categories['Front']%}
{% for post in posts %}
  {% include archive-single.html type=page.entries_layout %}
{% endfor %}
