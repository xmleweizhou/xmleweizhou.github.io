---
layout: default
title: 文章归档
---

<!-- 归档页面头部 -->
<header class="archive-header">
  <h1 class="archive-title">文章归档</h1>
  <p class="archive-subtitle">按年份整理所有博文</p>
</header>

<!-- 导航栏（已修复高亮逻辑） -->
<nav class="site-nav">
  <a href="/" class="nav-item {% if page.url == '/' %}active{% endif %}">首页</a>
  <a href="/about" class="nav-item {% if page.url contains '/about' %}active{% endif %}">关于我</a>
  <a href="/archives" class="nav-item {% if page.url contains '/archives' %}active{% endif %}">文章归档</a>
  <a href="/now" class="nav-item {% if page.url contains '/now' %}active{% endif %}">Now</a>
</nav>

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
            <a href="{{ post.url | relative_url }}" class="archive-post-link">{{ post.title }}</a>
          </li>
        {% endfor %}
      </ul>
    {% endfor %}
  {% else %}
    <div class="no-archive-posts">暂无归档文章</div>
  {% endif %}
</div>

<!-- 底部信息 -->
<footer class="site-footer">
  <a href="#" class="back-to-top" onclick="window.scrollTo({top:0,behavior:'smooth'});return false;">返回顶部 ↑</a>
  <p class="copyright">© {{ site.time | date: '%Y' }} {{ site.title }} | YAYU THEME</p>
</footer>

<!-- 归档页面样式（修复所有问题 + 风格统一） -->
<style>
  :root {
    --bg:#121212;
    --text:#e0e0e0;
    --link:#4da6ff;
    --border:#2a2a2a;
    --active-nav:#fff; /* 补全缺失的高亮变量 */
  }
  * {margin:0;padding:0;box-sizing:border-box;}
  /* 补全body基础样式，和其他页面统一 */
  body {
    font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,sans-serif;
    background:var(--bg);
    color:var(--text);
    line-height:1.6;
    padding:2rem 4rem;
    max-width:800px;
    margin:0 auto;
  }

  /* 导航样式（修复优先级 + 统一效果） */
  .site-nav {margin:2rem 0;text-align: center;}
  .nav-item {
    color:var(--text);
    text-decoration:none;
    margin-right:1.5rem;
    font-size:0.95rem;
    opacity:0.8;
    transition: all 0.2s;
  }
  .nav-item.active {
    opacity: 1 !important; /* 强制生效，避免覆盖 */
    color: var(--active-nav) !important;
    font-weight: 600;
  }
  .nav-item:hover:not(.active) {
    opacity:1;
    color:var(--link);
  }
  
  /* 归档头部样式 */
  .archive-header {text-align: center;margin: 3rem 0 2rem;}
  .archive-title {font-size: 1.8rem;font-weight: 700;color: #ffffff;margin-bottom: 0.5rem;}
  .archive-subtitle {font-size: 1rem;opacity: 0.7;color: #cccccc;}
  
  /* 归档内容样式 */
  .archive-content {max-width: 700px;margin: 0 auto;padding: 0 2rem;}
  .archive-year {
    font-size: 1.4rem;
    margin: 2.5rem 0 1rem;
    padding-bottom: 0.5rem;
    border-bottom: 1px solid var(--border);
    color: #ffffff;
  }
  .archive-post-list {list-style: none;margin-left: 0.5rem;}
  .archive-post-item {
    display: flex;
    margin: 0.8rem 0;
    align-items: center;
  }
  .archive-post-date {
    width: 80px;
    font-size: 0.9rem;
    opacity: 0.6;
    color: #999;
  }
  .archive-post-link {
    color: var(--link);
    text-decoration: none;
    font-size: 0.95rem;
    transition: color 0.2s;
  }
  .archive-post-link:hover {color: #66b3ff;}
  
  /* 无文章提示 */
  .no-archive-posts {
    text-align: center;
    color: var(--text);
    opacity: 0.7;
    padding: 3rem 0;
    font-size: 1rem;
  }

  /* 底部信息样式 */
  .site-footer {margin:4rem 0 2rem;font-size:0.9rem;opacity:0.7;text-align: center;}
  .back-to-top {
    color:var(--link);
    text-decoration:none;
    display:inline-block;
    margin-bottom:0.5rem;
  }
  .back-to-top:hover {text-decoration:underline;}
  
  /* 完整响应式适配（和其他页面统一） */
  @media (max-width:768px) {
    body {padding:1rem 1.5rem;} /* 补全body适配 */
    .archive-title {font-size: 1.5rem;}
    .archive-subtitle {font-size: 0.85rem;} /* 适配副标题 */
    .nav-item {margin-right:1rem;font-size:0.9rem;} /* 适配导航项 */
    .archive-content {padding: 0 1rem;}
    .archive-post-item {flex-direction: column;align-items: flex-start;}
    .archive-post-date {width: auto;margin-bottom: 0.2rem;}
  }
</style>
