# 部署与安全建议（本地写作 + 静态发布）

这是你选的方案：
- 本地写作/预览
- 静态构建后发布（无数据库、无后台）

## 1) 本地使用

```bash
npm run dev
```

默认仅本机访问（localhost），不要加 `--host`，这样不会暴露到局域网。

## 2) 发布到 GitHub Pages

1. 新建 GitHub 仓库并推送本项目
2. 在仓库 `Settings -> Pages` 中把 Source 设为 **GitHub Actions**
3. 在仓库 `Settings -> Secrets and variables -> Actions -> Variables` 新建：
   - `SITE_URL` = 你的站点地址（例如 `https://<username>.github.io`）
4. push 到 `main` 后自动部署

## 3) 安全基线（低维护）

- 不部署动态后端（本项目就是纯静态）
- 本地开发机开启系统自动更新
- 浏览器/GitHub 开启 2FA（推荐 Passkey 或硬件密钥）
- 仓库只保存文章内容，不放私密文件和密钥
- 定期备份（Time Machine 或 Git 远端）

## 4) 你后续可选增强

- 自定义域名（HTTPS 自动）
- 评论系统（Giscus，基于 GitHub Discussions）
- 站点访问统计（Umami / Plausible）
