---
title: "Post about Algorithms"
layout: archive
permalink: /categories/algorithms
author_profile: true
sidebar_main: true
---

{% assign posts = site.categories.algorithms | sort:"tags" | reverse %}

{% for post in posts %}
  {% include archive-single.html type=page.entries_layout %}
{% endfor %}
