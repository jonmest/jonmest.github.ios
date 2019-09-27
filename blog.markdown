---
layout: default
title: Blog
permalink: /blog/
---

This is where I will occasionally publish new blog posts. Find them below:

<ul>
  {% for post in site.posts %}
    <div class="card">
      <div class="card-title">
            <h3>
      <a href="{{ post.url }}">{{ post.title }}</a>
      </h3>
      </div>
    <div class="card-content">
          <p>
      {{ post.excerpt }}
      </p>
    </div>
    </div>

  {% endfor %}
</ul>