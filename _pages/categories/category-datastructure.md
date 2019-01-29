---
title: "Posts about Data Structure"
layout: archive
permalink: /categories/datastructure
author_profile: true
sidebar_main: true
sidebar:
    nav: "_posts"
---

{% assign posts = site.categories.dataStructure | sort:"date" %}

{% for post in posts %}
  {% include archive-single.html type=page.entries_layout %}
{% endfor %}
