---
layout: page
title: Blog
permalink: /blog/
---

Tell us about your blog. Hopefully it's cool.

<ul class="listing">
{% for post in site.posts %}
  {% capture y %}{{post.date | date:"%Y"}}{% endcapture %}
  <!--{% if post.categories contains 'notebook' %}
  {% continue %}
  {% endif %}-->
  {% if post.categories contains 'draft' %}
  {% continue %}
  {% endif %}
  {% if year != y %}
    {% assign year = y %}
    <li class="listing-seperator">{{ y }}</li>
  {% endif %}
  <li class="listing-item">
    <time datetime="{{ post.date | date:"%Y-%m-%d" }}">{{ post.date | date:"%Y-%m-%d" }}</time>
    <a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
  </li>
{% endfor %}
</ul>