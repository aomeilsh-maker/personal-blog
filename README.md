# Aomei 的个人博客（Astro）

这是 `Aomei的小屋` 的源码仓库。站点采用 **Astro + Markdown**，发布到 **GitHub Pages**。

## 在线地址

- 主页：<https://aomeilsh-maker.github.io/personal-blog/>
- 文章列表：<https://aomeilsh-maker.github.io/personal-blog/blog>

## 技术栈

- Astro (静态站点)
- Markdown 内容管理
- GitHub Actions 自动构建与部署

## 目录结构

```text
personal-blog/
├── public/                    # 静态资源
├── src/
│   ├── components/            # 通用组件（Header/Footer 等）
│   ├── content/blog/          # 文章 Markdown
│   ├── layouts/               # 页面布局（含文章详情布局）
│   ├── pages/                 # 路由页面（首页/文章/About）
│   └── styles/                # 全局样式
├── astro.config.mjs
└── .github/workflows/deploy.yml
```

## 本地开发

```bash
cd personal-blog
npm install
npm run dev
```

打开 <http://localhost:4321> 预览。

## 发布文章

在 `src/content/blog/` 新建 `.md` 文件，例如：

```md
---
title: "文章标题"
description: "一句摘要"
pubDate: 2026-02-24
---

这里写正文。
```

保存后本地可立即预览；推送到 `main` 后会自动发布。

## 部署（GitHub Pages）

仓库需开启：

1. `Settings -> Pages` 选择 **GitHub Actions**
2. `Settings -> Secrets and variables -> Actions -> Variables` 设置：
   - `SITE_URL = https://aomeilsh-maker.github.io/personal-blog`
   - `BASE_PATH = /personal-blog`

每次 push 到 `main` 会触发 `.github/workflows/deploy.yml` 自动部署。

## 迁移说明

- 已完成从旧站归档到本项目的文章迁移。
- `migration-links.txt` 用于保存迁移映射记录（日期/链接/标题）。
