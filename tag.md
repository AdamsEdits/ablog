---
layout: default
title: Tags
permalink: /blog/tag/
---

<h1>Tags</h1>

<ul>
{% assign tags = site.posts | map: "tags" | join: "," | split: "," | uniq | sort %}
{% for tag in tags %}
  {% if tag and site.hidden_tags contains tag == false %}
    <li><a href="/blog/tag/{{ tag | slugify }}/">{{ tag }}</a></li>
  {% endif %}
{% endfor %}
</ul>