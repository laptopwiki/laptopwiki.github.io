---
layout: default
title: Home
description: "All things laptop"
nav_exclude: true
permalink: /
---

# Laptop Wiki

{% for collection in site.collections %}
  <h2>Items from {{ collection.label }}</h2>
  <ul>
    {% for item in site[collection.label] %}
      <li><a href="{{ item.url }}">{{ item.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}