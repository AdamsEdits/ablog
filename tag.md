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
    {% assign should_hide = site.hidden_tags contains tag %}
    {% assign posts_with_tag = site.posts | where_exp: "post", "post.tags contains tag" %}
    
    {% for post in posts_with_tag %}
      {% if post.show_all_tags %}
        {% assign should_hide = false %}
        {% break %}
      {% endif %}
    {% endfor %}
    
    {% if should_hide == false %}
      <li><a href="/blog/tag/{{ tag | slugify }}/">{{ tag }}</a></li>
    {% endif %}
  {% endif %}
{% endfor %}
</ul>
