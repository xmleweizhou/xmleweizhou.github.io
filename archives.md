---
layout: default
title: 文章归档
---

<!-- 归档页面头部 -->
<header class="archive-header">
  <h1 class="archive-title">文章归档</h1>
  <p class="archive-subtitle">按年份整理所有博文</p>
</header>

<!-- 导航栏 -->
<nav class="site-nav">
  
  <a href="/" class="nav-item">首页</a>
  <a href="/about" class="nav-item">关于我</a>
  <a href="/archives" class="nav-item">文章归档</a>
  <a href="/now" class="nav-item">Now</a>
  
  
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
            <a href="{{ post.url }}" class="archive-post-link">{{ post.title }}</a>
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

<!-- 内联样式（包含博主名称的样式） -->
<style>
  :root {--bg:#121212;--text:#e0e0e0;--link:#4da6ff;--border:#2a2a2a;--active-nav:#fff;}
  * {margin:0;padding:0;box-sizing:border-box;}
  body {font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,sans-serif;background:var(--bg);color:var(--text);line-height:1.6;padding:2rem 4rem;max-width:800px;margin:0 auto;}
  
  /* 博主名称头部样式 */
  .blog-header {text-align: center;margin: 3rem 0 1rem;}
  .blog-name {font-size: 2.2rem;font-weight: 700;color: #ffffff;margin-bottom: 0.5rem;}
  .blog-subtitle {font-size: 1rem;opacity: 0.7;color: #cccccc;}
  
  .site-nav {margin:2rem 0;text-align: center;} /* 导航栏居中，和博主名称对齐 */
  .nav-item {color:var(--text);text-decoration:none;margin-right:1.5rem;font-size:0.95rem;opacity:0.8;transition:opacity 0.2s;}
  .nav-item:hover {opacity:1;color:var(--link);}
  .section-title {margin:3rem 0 1.5rem;font-size:1.2rem;font-weight:600;border-bottom:1px solid var(--border);padding-bottom:0.5rem;}
  .post-list {list-style:none;}
  .post-item {display:flex;margin:0.8rem 0;}
  .post-date {width:100px;font-size:0.9rem;opacity:0.6;}
  .post-link {color:var(--link);text-decoration:none;font-size:0.95rem;transition:color 0.2s;}
  .post-link:hover {color:#66b3ff;}
  .no-posts {color:var(--text);opacity:0.7;padding:2rem 0;text-align:center;}
  .site-footer {margin:4rem 0 2rem;font-size:0.9rem;opacity:0.7;text-align: center;}
  .back-to-top {color:var(--link);text-decoration:none;display:inline-block;margin-bottom:0.5rem;}
  .back-to-top:hover {text-decoration:underline;}
  
  /* 响应式适配 */
  @media (max-width:768px) {
    body {padding:1rem 1.5rem;}
    .blog-name {font-size: 1.8rem;}
    .blog-subtitle {font-size: 0.9rem;}
    .nav-item {margin-right:1rem;font-size:0.9rem;}
    .post-item {flex-direction:column;}
    .post-date {width:auto;margin-bottom:0.2rem;}
  }
</style>





