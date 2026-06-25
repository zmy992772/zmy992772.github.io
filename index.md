---
layout: home
title: 首页
---

<style>
/* ===== 红黑配色 · 暗黑风格 ===== */
body {
    background: #0d0d0d;
    color: #e0e0e0;
    font-family: -apple-system, 'PingFang SC', 'Microsoft YaHei', sans-serif;
}
.posts-list .post {
    background: #1a1a1a;
    padding: 24px 28px;
    border-radius: 16px;
    border-left: 4px solid #cc0000;
    box-shadow: 0 4px 20px rgba(204, 0, 0, 0.08);
    margin-bottom: 20px;
    transition: box-shadow 0.25s ease, transform 0.2s ease;
}
.posts-list .post:hover {
    box-shadow: 0 8px 40px rgba(204, 0, 0, 0.18);
    transform: translateY(-2px);
}
.post-link {
    color: #ffffff;
    font-weight: 600;
    text-decoration: none;
    font-size: 1.4rem;
}
.post-link:hover {
    color: #ff3333;
    text-decoration: underline;
}
.post-meta {
    color: #888888;
    font-size: 0.9rem;
}
.page-heading {
    color: #ffffff;
    font-weight: 700;
    letter-spacing: -0.02em;
    border-bottom: 2px solid #cc0000;
    padding-bottom: 8px;
}
#status {
    background: #1a1a1a;
    padding: 16px 20px;
    border-radius: 12px;
    border: 1px solid #cc0000;
    box-shadow: 0 0 20px rgba(204, 0, 0, 0.10);
    margin-top: 24px;
    font-weight: 500;
    color: #e0e0e0;
}
#status .online { color: #66ff66; }
#status .offline { color: #ff4444; }
a { color: #ff3333; }
a:hover { color: #ff6666; }
.site-footer {
    border-top: 1px solid #2a2a2a;
    color: #777777;
}
.feed-subscribe {
    background: #cc0000;
    color: #fff;
    padding: 4px 14px;
    border-radius: 20px;
    font-size: 0.8rem;
    font-weight: 600;
    text-decoration: none;
    transition: background 0.2s;
}
.feed-subscribe:hover {
    background: #ff1a1a;
    color: #fff;
}
</style>
<style>
/* 头像 + 博主名片样式 */
.profile {
    display: flex;
    align-items: center;
    gap: 20px;
    background: #1a1a1a;
    padding: 20px 24px;
    border-radius: 20px;
    border-left: 4px solid #cc0000;
    margin-bottom: 30px;
    box-shadow: 0 4px 20px rgba(204,0,0,0.08);
}
.profile img {
    width: 70px;
    height: 70px;
    border-radius: 50%;
    object-fit: cover;
    border: 2px solid #cc0000;
}
.profile .info h2 {
    margin: 0;
    color: #ffffff;
    font-size: 22px;
}
.profile .info p {
    margin: 4px 0 0;
    color: #aaaaaa;
    font-size: 14px;
}
</style>

<div class="profile">
    <!-- 头像：换成你自己的图片链接 -->
    <img src="https://raw.githubusercontent.com/zmy992772/zmy992772.github.io/main/avatar.jpg" alt="头像">
    <div class="info">
        <h2>第五千零一朵玫瑰</h2>
        <p>🌍 总有一天你会明白，生活就是生锈的过程，反不反抗最后都会变成一把铁石心肠的零件。”</p>
    </div>
</div>
# 欢迎来到我的博客

这里会自动显示文章列表（由 Jekyll 生成）。

---

## 博主在线状态

<div id="status">加载中...</div>
<div id="time" style="font-size:14px;color:#888;margin-top:8px;">最后更新：--</div>

<script>
fetch('https://raw.githubusercontent.com/zmy992772/zmy992772.github.io/main/data.json?t=' + Date.now())
  .then(res => res.json())
  .then(json => {
    const now = Date.now();
    const pcOnline = (now - json.pc * 1000) < 600000;
    const phoneOnline = (now - json.phone * 1000) < 600000;
    document.getElementById('status').innerHTML = `
      💻 电脑：<span class="${pcOnline ? 'online' : 'offline'}">${pcOnline ? '🟢 在线' : '🔴 离线'}</span><br>
      📱 手机：<span class="${phoneOnline ? 'online' : 'offline'}">${phoneOnline ? '🟢 在线' : '🔴 离线'}</span>
    `;
    document.getElementById('time').textContent = '最后更新：' + new Date().toLocaleString();
  })
  .catch(() => {
    document.getElementById('status').textContent = '⚠️ 加载失败，请刷新';
  });
</script>
