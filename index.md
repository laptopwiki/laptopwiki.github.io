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

{% for issue in site.collections %}
  <li>
    <h6 class="post-meta">
      Issue {{ issue[1].label }}
      &mdash;
      {{ issue[1].date | date: "%b %-d, %Y" }}
    </h6>
    <h2>
      {{ issue[1].title }}
    </h2>
  </li>
{% endfor %}