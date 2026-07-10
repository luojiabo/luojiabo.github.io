# 妖怪佬的博客 🚀

基于 Hexo + Butterfly 主题的个人技术博客。

## 快速开始

```bash
# 安装依赖
npm install

# 本地预览（访问 http://localhost:4000）
npm run server

# 构建静态文件
npm run build

# 清理缓存
npm run clean
```

## 写文章

在 `source/_posts/` 下创建 `.md` 文件：

```markdown
---
title: 文章标题
date: 2026-07-10 14:30:00
tags:
  - 标签1
  - 标签2
categories:
  - 分类名
---

文章内容，支持 Markdown 语法。
```

## 部署到 Netlify（推荐）

### 1. 推送代码到 GitHub

```bash
# 在 GitHub 新建一个仓库（例如 blog）
git remote add origin https://github.com/你的用户名/blog.git
git push -u origin main
```

### 2. Netlify 连 GitHub 自动部署

1. 打开 [netlify.com](https://netlify.com) → 点 **Add new site** → **Import an existing project**
2. 选择你刚 push 的 GitHub 仓库
3. 以下配置会自动识别，确认即可：

| 配置项 | 值 |
|--------|-----|
| Build command | `npm run build` |
| Publish directory | `public` |
| Node version | `22` |

4. 点击 **Deploy site**，等 1-2 分钟就部署好了

### 3. 绑定自定义域名

1. 在 Netlify 后台 → **Domain settings** → **Add custom domain**
2. 输入 `blog.laoyaoguai.top`
3. 去你的域名 DNS 管理后台，添加一条 **CNAME 记录**：

```
blog → 你的-netlify-app.netlify.app
```

4. 等 DNS 生效（通常几分钟），Netlify 会自动申请 HTTPS 证书

### 4. 以后写文章

```bash
# 新建文章
hexo new "文章标题"

# 写完后 push 到 GitHub，Netlify 自动部署
git add .
git commit -m "新文章：xxx"
git push
```

## 评论系统配置

部署完成后，去 Twikoo 管理后台（https://twikoo.js.org/）按指引获取 `envId`，然后填入 `_config.butterfly.yml` 中的 `twikoo.envId`。

## 目录结构

```
blog/
├── source/              # 源代码目录
│   ├── _posts/          # 文章（Markdown）
│   ├── about/           # 关于页面
│   ├── tags/            # 标签页
│   └── categories/      # 分类页
├── themes/              # 主题（Butterfly）
├── _config.yml           # 主配置文件
├── _config.butterfly.yml # 主题配置文件
├── netlify.toml          # Netlify 部署配置
└── package.json
```

## 许可证

MIT
