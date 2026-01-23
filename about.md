---
layout: default
title: 关于我
---
<!-- 页面头部 -->
<header class="archive-header">
  <h1 class="archive-title">关于我</h1>
  <p class="archive-subtitle">做人晶莹剔透 做事水滴石穿</p>
</header>

<!-- 导航栏（新增当前页面高亮逻辑） -->
<nav class="site-nav">
  <a href="/" class="nav-item {% if page.url == '/' %}active{% endif %}">首页</a>
  <a href="/about" class="nav-item {% if page.url contains '/about' %}active{% endif %}">关于我</a>
  <a href="/archives" class="nav-item {% if page.url contains '/archives' %}active{% endif %}">文章归档</a>
  <a href="/now" class="nav-item {% if page.url contains '/now' %}active{% endif %}">Now</a>
</nav>

<!-- 个人简介 + 更新日志（优化排版） -->
<div class="about-content">
  <p><strong>乐为舟</strong>是笔名，取材自“书山有路勤为径、学海无涯苦作舟”</p>
  <p>泛舟学海并不一定“苦”，亦可“以乐为舟”</p>
  <p>一位跑者，对技术持有原始的好奇、努力生活、不忘思考，偶有所获，想留下些记录，以备回想，故而有了本站</p>
  <p>GitHub：<a href="https://github.com/xmleweizhou" class="about-link">https://github.com/xmleweizhou</a></p>
  
  <h3 class="log-title">博客更新日志</h3>
  <ul class="log-list">
    <li>2026-01-21 基本完成主页框架及栏目设置</li>
    <li>2026-01-22 将_posts下的测试文档清空，上传第一篇正式文档</li>
  </ul>
</div>

<!-- 底部信息 -->
<footer class="site-footer">
  <a href="#" class="back-to-top" onclick="window.scrollTo({top:0,behavior:'smooth'});return false;">返回顶部 ↑</a>
  <p class="copyright">© {{ site.time | date: '%Y' }} {{ site.title }} | YAYU THEME</p>
</footer>

<!-- 内联样式 -->
<style>
  :root {--bg:#121212;--text:#e0e0e0;--link:#4da6ff;--border:#2a2a2a;--active-nav:#fff;}
  * {margin:0;padding:0;box-sizing:border-box;}
  body {font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,sans-serif;background:var(--bg);color:var(--text);line-height:1.6;padding:2rem 4rem;max-width:800px;margin:0 auto;}
  
  /* 头部样式 */
  .archive-header {text-align: center;margin: 3rem 0 2rem;}
  .archive-title {font-size: 1.8rem;font-weight: 700;color: #ffffff;margin-bottom: 0.5rem;}
  .archive-subtitle {font-size: 1rem;opacity: 0.7;color: #cccccc;}
  
  /* 导航样式 */
  .site-nav {margin:2rem 0;text-align: center;}
  .nav-item {color:var(--text);text-decoration:none;margin-right:1.5rem;font-size:0.95rem;opacity:0.8;transition:opacity 0.2s;}
  .nav-item:hover {opacity:1;color:var(--link);}
  .nav-item.active {
    opacity: 1;
    color: var(--active-nav);
    font-weight: 600;
  }
  .nav-item:hover:not(.active) {
    opacity:1;
    color:var(--link);
  }
  
  /* 关于我内容排版 */
  .about-content {
    max-width: 700px;
    margin: 2rem auto;
    font-size: 0.95rem;
    line-height: 1.8;
  }
  .about-content p {
    margin-bottom: 1rem;
  }
  .about-link {
    color: var(--link);
    text-decoration: none;
  }
  .about-link:hover {
    text-decoration: underline;
  }
  .log-title {
    margin: 2rem 0 1rem;
    font-size: 1.1rem;
    font-weight: 600;
    border-bottom: 1px solid var(--border);
    padding-bottom: 0.5rem;
  }
  .log-list {
    list-style: none;
    padding-left: 0.5rem;
  }
  .log-list li {
    margin: 0.8rem 0;
    opacity: 0.9;
  }
  
  /* 底部样式 */
  .site-footer {margin:4rem 0 2rem;font-size:0.9rem;opacity:0.7;text-align: center;}
  .back-to-top {color:var(--link);text-decoration:none;display:inline-block;margin-bottom:0.5rem;}
  .back-to-top:hover {text-decoration:underline;}
  
  /* 响应式适配 */
  @media (max-width:768px) {
    body {padding:1rem 1.5rem;}
    .archive-title {font-size: 1.5rem;}
    .archive-subtitle {font-size: 0.85rem;}
    .nav-item {margin-right:1rem;font-size:0.9rem;}
    .about-content {padding: 0 0.5rem;}
  }
</style>

