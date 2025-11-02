---
layout: default
title: 首页
---
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{{ site.title }}</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            line-height: 1.6;
            color: #333;
            background-color: #f9f9f9;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* 导航栏 */
        header {
            background-color: #fff;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
        }
        
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
        }
        
        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            color: #2c3e50;
        }
        
        .nav-links {
            display: flex;
            list-style: none;
        }
        
        .nav-links li {
            margin-left: 30px;
        }
        
        .nav-links a {
            text-decoration: none;
            color: #333;
            font-weight: 500;
            transition: color 0.3s;
        }
        
        .nav-links a:hover {
            color: #3498db;
        }
        
        /* 主要内容区域 */
        main {
            margin-top: 80px;
            min-height: calc(100vh - 160px);
        }
        
        section {
            padding: 80px 0;
        }
        
        h1, h2, h3 {
            margin-bottom: 20px;
            color: #2c3e50;
        }
        
        p {
            margin-bottom: 15px;
        }
        
        /* 英雄区域 */
        .hero {
            text-align: center;
            padding: 100px 0;
            background: linear-gradient(135deg, #3498db, #8e44ad);
            color: white;
        }
        
        .hero h1 {
            font-size: 3rem;
            margin-bottom: 20px;
            color: white;
        }
        
        .hero p {
            font-size: 1.2rem;
            max-width: 600px;
            margin: 0 auto 30px;
        }
        
        .btn {
            display: inline-block;
            background: #fff;
            color: #3498db;
            padding: 12px 30px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: bold;
            transition: all 0.3s;
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
        }
        
        /* 博客文章列表 */
        .posts {
            background-color: #fff;
        }
        
        .post-list {
            list-style: none;
        }
        
        .post-item {
            margin-bottom: 30px;
            padding: 20px;
            border: 1px solid #eee;
            border-radius: 8px;
            transition: transform 0.3s, box-shadow 0.3s;
        }
        
        .post-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        
        .post-title {
            font-size: 1.5rem;
            margin-bottom: 10px;
        }
        
        .post-title a {
            color: #2c3e50;
            text-decoration: none;
        }
        
        .post-title a:hover {
            color: #3498db;
        }
        
        .post-date {
            color: #666;
            font-size: 0.9rem;
            margin-bottom: 10px;
        }
        
        .post-excerpt {
            color: #555;
        }
        
        /* 页脚 */
        footer {
            background-color: #2c3e50;
            color: white;
            text-align: center;
            padding: 30px 0;
        }
        
        /* 响应式设计 */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }
            
            .hero h1 {
                font-size: 2.5rem;
            }
        }
    </style>
</head>
<body>
    <!-- 导航栏 -->
    <header>
        <div class="container">
            <nav>
                <div class="logo">{{ site.title }}</div>
                <ul class="nav-links">
                    <li><a href="#home">首页</a></li>
                    <li><a href="#posts">博客</a></li>
                    <li><a href="#about">关于</a></li>
                    <li><a href="#contact">联系</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- 主要内容 -->
    <main>
        <!-- 英雄区域 -->
        <section id="home" class="hero">
            <div class="container">
                <h1>你好，我是{{ site.author.name }}</h1>
                <p>{{ site.description }}</p>
                <a href="#posts" class="btn">查看我的博客</a>
            </div>
        </section>

        <!-- 博客文章列表 -->
        <section id="posts" class="posts">
            <div class="container">
                <h2>最新文章</h2>
                <ul class="post-list">
                    {% for post in site.posts %}
                    <li class="post-item">
                        <h3 class="post-title">
                            <a href="{{ post.url }}">{{ post.title }}</a>
                        </h3>
                        <div class="post-date">
                            {{ post.date | date: "%Y年%m月%d日" }}
                        </div>
                        <div class="post-excerpt">
                            {{ post.excerpt | strip_html | truncate: 200 }}
                        </div>
                    </li>
                    {% endfor %}
                </ul>
            </div>
        </section>

        <!-- 关于区域 -->
        <section id="about" class="about">
            <div class="container">
                <h2>关于我</h2>
                <p>我是一名开发者，对技术和设计充满热情。</p>
                <p>GitHub: <a href="https://github.com/{{ site.github_username }}">{{ site.github_username }}</a></p>
            </div>
        </section>

        <!-- 联系区域 -->
        <section id="contact" class="contact">
            <div class="container">
                <h2>联系我</h2>
                <p>邮箱: {{ site.author.email }}</p>
            </div>
        </section>
    </main>

    <!-- 页脚 -->
    <footer>
        <div class="container">
            <p>&copy; 2023 {{ site.author.name }}. 保留所有权利.</p>
        </div>
    </footer>

    <script>
        // 平滑滚动
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                if(targetId === '#') return;
                
                const targetElement = document.querySelector(targetId);
                if(targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 80,
                        behavior: 'smooth'
                    });
                }
            });
        });
        
        // 导航栏滚动效果
        window.addEventListener('scroll', function() {
            const header = document.querySelector('header');
            if (window.scrollY > 100) {
                header.style.boxShadow = '0 5px 15px rgba(0,0,0,0.1)';
            } else {
                header.style.boxShadow = '0 2px 5px rgba(0,0,0,0.1)';
            }
        });
    </script>
</body>
</html>
