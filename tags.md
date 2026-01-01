---
layout: page
title: Tags
---

{% assign tags = site.posts | map: 'tags' | join: ',' | split: ',' | uniq | sort %}

{% for tag in tags %}
  <h2 id="{{ tag }}">{{ tag }}</h2>
  <ul>
    {% for post in site.posts %}
      {% if post.tags contains tag %}
        <li>
          <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        </li>
      {% endif %}
    {% endfor %}
  </ul>
{% endfor %}
