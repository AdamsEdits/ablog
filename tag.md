---
layout: default
title: Tags
permalink: /tag/
---

<h1>Tags</h1>

<ul>
{% assign tags = site.posts | map: "tags" | join: "," | split: "," | uniq | sort %}
{% for tag in tags %}
  {% if tag %}
    <li><a href="/blog/tag/{{ tag | slugify }}/">{{ tag }}</a></li>
  {% endif %}
{% endfor %}
</ul>
