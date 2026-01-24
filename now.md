---
layout: default
title: Now
---
<!-- 页面头部 -->
<header class="archive-header">
  <h1 class="archive-title">Now</h1>
  <p class="archive-subtitle">记录现在的自己</p>
</header>

<!-- 导航栏（新增当前页面高亮逻辑） -->
<nav class="site-nav">
  <!-- 通过 Liquid 语法判断当前页面路径，为对应导航项添加 active 类 -->
  <a href="/" class="nav-item {% if page.url == '/' %}active{% endif %}">首页</a>
  <a href="/about" class="nav-item {% if page.url contains '/about' %}active{% endif %}">关于我</a>
  <a href="/archives" class="nav-item {% if page.url contains '/archives' %}active{% endif %}">文章归档</a>
  <a href="/now" class="nav-item {% if page.url contains '/now' %}active{% endif %}">Now</a>
</nav>

📨 Mail Client: 工作邮件用Foxmail，移动端使用官方App，兼用网页端

📝 Notes: flomo、Apple Notes、原子笔记

✅ To-Do: Aplle Notes

📷 iPhone Android Photo Shooting: 手机系统自带相机

📆 Calendar: 系统默认日历

📁 Cloud File Storage: 轻度使用百度网盘、阿里云盘

📖 RSS: Foxmail自带

🙍🏻‍♂️ Contacts: 使用系统自带联系人应用

🌐 Browser: Windows 下主要使用 Chrome，移动端使用 Chrome 和Safari

💬 Chat: 微信、QQ

🤖 AI Model: DeepSeek、豆包

🔖 Bookmarks: 浏览器自带

📜 Word Processing: Typora、记事本、Sublime Text

📈 Spreadsheets: Microsoft Excel

📊 Presentations: Microsoft Powerpoint

🛒 Shopping Lists: Apple Notes

🍴 Meal Planning: 不会做饭

💰 Budgeting and Personal Finance: 挖财记账

📰 News: IT之家、RSS订阅

🎵 Music: Apple Music

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
  .site-nav {margin:2rem 0;text-align: center;} /* 导航栏居中，和博主名称对齐 */
  .nav-item {color:var(--text);text-decoration:none;margin-right:1.5rem;font-size:0.95rem;opacity:0.8;transition:opacity 0.2s;}
  .nav-item:hover {opacity:1;color:var(--link);}

  /* 新增：当前页面导航高亮 */
  .nav-item.active {
    opacity: 1;
    color: var(--active-nav);
    font-weight: 600;
  }
  .nav-item:hover:not(.active) {
    opacity:1;
    color:var(--link);
  }

  /* 底部样式 */
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



