---
layout: default
title: Blog
permalink: /blog/
---

This is where I will occasionally publish new blog posts. Find them below:

<ul>
  {% for post in site.posts %}
  <a href="{{ post.url }}">
    <div class="card">
      <div class="card-title">
            <span><h3>
      {{ post.title }}
      </h3> {{ post.date | date: '%B %d, %Y'}}</span>
      </div>
    <div class="card-content">
          <p>
      {{ post.excerpt | strip_html }}
      </p>
    </div>
    </div>
    </a>

  {% endfor %}
</ul>