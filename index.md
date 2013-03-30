---
layout: page
title: "最近发表"
comments : false
---
{% include JB/setup %}

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date:"%Y年%m月%d日" }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>

  {% endfor %}
</ul>
