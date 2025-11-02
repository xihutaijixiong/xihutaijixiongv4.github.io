---
layout: default
title: 首页
---
<h1>{{ site.title }}</h1>
<p>{{ site.description }}</p>

<h2>最新文章</h2>
<ul>
    {% for post in site.posts %}
    <li>
        <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
        <small>{{ post.date | date: "%Y-%m-%d" }}</small>
    </li>
    {% endfor %}
</ul>
