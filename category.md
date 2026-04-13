---
layout: default
title: Categories
permalink: /blog/category/
---

<h1>Categories</h1>

<ul>
{% assign categories = site.posts | map: "categories" | join: "," | split: "," | uniq | sort %}
{% for cat in categories %}
  {% unless site.hidden_categories contains cat %}
    {% if cat %}
      <li><a href="/blog/category/{{ cat | slugify }}/">{{ cat }}</a></li>
    {% endif %}
  {% endunless %}
{% endfor %}
</ul>
