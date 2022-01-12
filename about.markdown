---
layout: page
title: 我的想法
permalink: /about/
---

<ul>
    {% for post in site.posts %}
      <li>
        <a href="{{ post.url }}">{{ post.title }}</a>
        <!-- {{ post.excerpt }} -->
      </li>
    {% endfor %}
</ul>