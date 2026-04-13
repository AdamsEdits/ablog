---
layout: default
title: Categories
permalink: /category/
---

<h1>Categories</h1>

<ul>
{% assign categories = site.posts | map: "categories" | join: "," | split: "," | uniq | sort %}
{% for cat in categories %}
  {% if cat %}
    <li><a href="/blog/category/{{ cat | slugify }}/">{{ cat }}</a></li>
  {% endif %}
{% endfor %}
</ul>
