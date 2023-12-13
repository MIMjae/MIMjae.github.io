---
title: "Generative AI"
layout: archive
permalink: /categories/gai/
taxonomy: Generative AI
sidebar:
  nav: "docs"
---

{% assign posts = site.categories['openAI']%}
{% for post in posts %}
  {% include archive-single.html type=page.entries_layout %}
{% endfor %}
