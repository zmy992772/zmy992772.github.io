---
layout: home
title: 首页
---

# 欢迎来到我的博客

这里会自动显示文章列表（由 Jekyll 生成）。

---

## 博主在线状态

<div id="status" style="font-size:18px;">加载中...</div>
<div id="time" style="font-size:14px;color:#666;">最后更新：--</div>

<script>
fetch('https://raw.githubusercontent.com/zmy992772/zmy992772.github.io/main/data.json?t=' + Date.now())
  .then(res => res.json())
  .then(json => {
    const now = Date.now();
    const pcOnline = (now - json.pc * 1000) < 600000;
    const phoneOnline = (now - json.phone * 1000) < 600000;
    document.getElementById('status').innerHTML = `
      💻 电脑：${pcOnline ? '🟢 在线' : '🔴 离线'}<br>
      📱 手机：${phoneOnline ? '🟢 在线' : '🔴 离线'}
    `;
    document.getElementById('time').textContent = '最后更新：' + new Date().toLocaleString();
  })
  .catch(() => {
    document.getElementById('status').textContent = '加载失败，请刷新';
  });
</script>
