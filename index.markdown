---
layout: default
title: My Blog
---

<h1>Posts</h1>
<ul class="post-list">
  {% for post in site.posts %}
  <li>
    <h3>
      <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
    </h3>
    <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>
    <p>{{ post.excerpt | strip_html | truncatewords: 25 }}</p>

    {% if post.tags.size > 0 %}
      <div class="tags">
        <small>Tags:</small>
        {% for tag in post.tags %}
          <a href="{{ '/tags/' | relative_url }}{{ tag | slugify }}/">{{ tag }}</a>
        {% endfor %}
      </div>
    {% endif %}
  </li>
  {% endfor %}
</ul>