---
layout: default
title: Home
description: "All things laptop"
nav_exclude: true
permalink: /
---

# Laptop Wiki

#### Thank you to the contributors of Laptop Wiki!

<ul class="list-style-none">
{% for contributor in site.github.contributors %}
  <li class="d-inline-block mr-1">
     <a href="{{ contributor.html_url }}"><img src="{{ contributor.avatar_url }}" width="32" height="32" alt="{{ contributor.login }}"/></a>
  </li>
{% endfor %}
</ul>