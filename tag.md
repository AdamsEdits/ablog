---
layout: default
title: Tags
permalink: /blog/tag/
---

<h1>Tags</h1>

<ul>
{% assign tags = site.posts | map: "tags" | join: "," | split: "," | uniq | sort %}
{% for tag in tags %}
  {% unless site.hidden_tags contains tag %}
    {% if tag %}
      <li><a href="/blog/tag/{{ tag | slugify }}/">{{ tag }}</a></li>
    {% endif %}
  {% endunless %}
{% endfor %}
</ul>
