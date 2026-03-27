---
layout: default
title: Blog
permalink: /blog/
---
<h1>Blog</h1>
<section>
{% if site.posts.size > 0 %}
  {% for post in site.posts %}
  <p>
    <a href="{{ post.url }}">{{ post.title }}</a><br>
    <span style="font-size: 0.85rem; color: #666;">{{ post.date | date: "%-d %B %Y" }}</span>
    {% if post.excerpt %}
    <br>{{ post.excerpt | strip_html | truncatewords: 25 }}
    {% endif %}
  </p>
  {% endfor %}
{% else %}
  <p>No posts yet.</p>
{% endif %}
</section>
