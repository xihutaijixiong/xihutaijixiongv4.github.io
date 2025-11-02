---
layout: default
title: 首页
---
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>{{ site.title }}</title>
    <style>
        body { font-family: Arial; max-width: 800px; margin: 40px auto; padding: 20px; }
        .post-list { list-style: none; padding: 0; }
        .post-item { margin: 20px 0; padding: 15px; border: 1px solid #ddd; }
    </style>
</head>
<body>
    <h1>{{ site.title }}</h1>
    <p>{{ site.description }}</p>
    
    <h2>最新文章</h2>
    <ul class="post-list">
        {% for post in site.posts %}
        <li class="post-item">
            <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
            <small>{{ post.date | date: "%Y-%m-%d" }}</small>
        </li>
        {% endfor %}
    </ul>
</body>
</html>
