---
layout: default
title: 文章归档
---

<!-- 归档页面头部 -->
<header class="archive-header">
  <h1 class="archive-title">文章归档</h1>
  <p class="archive-subtitle">按年份整理所有博文</p>
</header>

<!-- 按年份归档核心逻辑 -->
<div class="archive-content">
  {% assign postsByYear = site.posts | group_by_exp: "post", "post.date | date: '%Y'" %}
  
  {% if postsByYear.size > 0 %}
    {% for year in postsByYear %}
      <!-- 年份标题 -->
      <h2 class="archive-year">{{ year.name }} 年</h2>
      <!-- 该年份的文章列表 -->
      <ul class="archive-post-list">
        {% for post in year.items %}
          <li class="archive-post-item">
            <span class="archive-post-date">{{ post.date | date: "%m-%d" }}</span>
            <a href="{{ post.url }}" class="archive-post-link">{{ post.title }}</a>
          </li>
        {% endfor %}
      </ul>
    {% endfor %}
  {% else %}
    <div class="no-archive-posts">暂无归档文章</div>
  {% endif %}
</div>

<!-- 归档页面样式（和主页风格统一） -->
<style>
  :root {--bg:#121212;--text:#e0e0e0;--link:#4da6ff;--border:#2a2a2a;}
  * {margin:0;padding:0;box-sizing:border-box;}
  
  /* 归档头部样式 */
  .archive-header {text-align: center;margin: 3rem 0 2rem;}
  .archive-title {font-size: 1.8rem;font-weight: 700;color: #ffffff;margin-bottom: 0.5rem;}
  .archive-subtitle {font-size: 1rem;opacity: 0.7;color: #cccccc;}
  
  /* 归档内容样式 */
  .archive-content {max-width: 700px;margin: 0 auto;padding: 0 2rem;}
  .archive-year {font-size: 1.4rem;margin: 2.5rem 0 1rem;padding-bottom: 0.5rem;border-bottom: 1px solid var(--border);color: #ffffff;}
  .archive-post-list {list-style: none;margin-left: 0.5rem;}
  .archive-post-item {display: flex;margin: 0.8rem 0;align-items: center;}
  .archive-post-date {width: 80px;font-size: 0.9rem;opacity: 0.6;color: #999;}
  .archive-post-link {color: var(--link);text-decoration: none;font-size: 0.95rem;transition: color 0.2s;}
  .archive-post-link:hover {color: #66b3ff;}
  
  /* 无文章提示 */
  .no-archive-posts {text-align: center;color: var(--text);opacity: 0.7;padding: 3rem 0;font-size: 1rem;}
  
  /* 响应式适配 */
  @media (max-width:768px) {
    .archive-title {font-size: 1.5rem;}
    .archive-content {padding: 0 1.5rem;}
    .archive-post-item {flex-direction: column;align-items: flex-start;}
    .archive-post-date {width: auto;margin-bottom: 0.2rem;}
  }
</style>