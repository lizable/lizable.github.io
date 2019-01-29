---
title: "Posts about Data Structure"
layout: archive
permalink: /categories/
author_profile: true
sidebar_main: true
sidebar:
    nav: "_posts"
---

{% assign posts = site.categories.data-structure | sort:"date" %}

{% for post in posts %}
  {% include archive-single.html type=page.entries_layout %}
{% endfor %}
