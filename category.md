---
layout: default
title: Categories
permalink: /blog/category/
---

<h1>Categories</h1>

<ul>
{% assign categories = site.posts | map: "categories" | join: "," | split: "," | uniq | sort %}
{% for cat in categories %}
  {% if cat %}
    {% assign should_hide = site.hidden_categories contains cat %}
    {% assign posts_with_cat = site.posts | where_exp: "post", "post.categories contains cat" %}
    
    {% for post in posts_with_cat %}
      {% if post.show_all_categories %}
        {% assign should_hide = false %}
        {% break %}
      {% endif %}
    {% endfor %}
    
    {% if should_hide == false %}
      <li><a href="/blog/category/{{ cat | slugify }}/">{{ cat }}</a></li>
    {% endif %}
  {% endif %}
{% endfor %}
</ul>
