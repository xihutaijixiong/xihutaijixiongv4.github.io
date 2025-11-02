---
layout: default
title: "首页"
nav_order: 0
description: "欢迎来到我的个人知识库"
---

# 🎯 欢迎来到我的知识库

这里是我个人学习和成长的记录空间，致力于构建系统的知识体系。

## 📚 知识分类

### 📊 [数据分析](/数据分析/)
- Python数据分析
- Excel高级技巧  
- 数据可视化
- 统计学基础

### 🗂️ [知识管理](/知识管理/)
- 笔记方法体系
- 数字工具推荐
- 工作流优化
- 第二大脑构建

### 🇺🇸 [英语学习](/英语学习/)
- 词汇积累方法
- 听力训练体系
- 阅读材料精选
- 口语练习技巧

### ✈️ [旅游记录](/旅游记录/)
- 旅行攻略
- 景点评测
- 装备推荐
- 见闻随笔

---

## 🔥 最新更新

{% for post in site.pages %}
{% if post.url != "/" and post.title %}
- [{{ post.title }}]({{ post.url }}) {% if post.date %}- {{ post.date | date: "%Y-%m-%d" }}{% endif %}
{% endif %}
{% endfor %}

---

<div align="center">
  <small>📅 最后更新: {{ site.time | date: "%Y-%m-%d" }} | 🌐 访问量: 持续增长中</small>
</div>
