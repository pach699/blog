# 个人博客（Jekyll + GitHub Pages）

这是一个不需要 Node.js、npm 或 React 的 Jekyll 静态博客，推送到 GitHub 后由 Actions 自动构建并发布。

## 改哪里

| 想改的内容 | 文件 |
| --- | --- |
| 名字、简介、邮箱、GitHub 链接、头像字母 | `_config.yml` 里的 `author` |
| 浏览器标签上的标题 | `_config.yml` 里的 `title` |
| 首页大标题和项目卡片 | `index.html` |
| 关于页 | `about.md` |
| 配色和排版 | `assets/style.css` |
| 文章 | `_posts/YYYY-MM-DD-title.md` |

## 已经上线

- 仓库：<https://github.com/pach699/blog>
- 网址：<https://pach699.github.io/blog/>
- Pages 的 Source 已经是 **GitHub Actions**，推送到 `main` 就会自动重建。

## 发布一次更新

1. 改文件（文章放 `_posts/YYYY-MM-DD-title.md`，保留 Front Matter）。
2. `git add -A`，`git commit -m "..."`，`git push`。
3. 等 Actions 里的 `Build and deploy Jekyll site` 变绿，刷新网址即可。

注意：仓库里的 `index.html` 是 Jekyll 模板源码，不能靠双击本地文件看到最终页面；最终 HTML 会由 GitHub Actions 生成。

## 写一篇新文章

在 `_posts/` 中复制示例文章，文件名使用：

```text
YYYY-MM-DD-title.md
```

文章开头保留 Front Matter：

```yaml
---
layout: post
title: 文章标题
date: 2026-10-08
excerpt: 一句话摘要
tags:
  - 学习
---
```

第二个 `---` 之后直接写 Markdown 正文：标题、段落、列表、链接、代码块都可以使用。

## 发布流程

1. 修改或新增 `_posts/*.md`。
2. 修改首页内容时编辑 `index.html`。
3. 修改关于页时编辑 `about.md`。
4. 修改配色和排版时编辑 `assets/style.css`。
5. 在浏览器中检查文件内容和链接。
6. `git diff` 检查变更。
7. `git add`、`git commit`、`git push`。
8. GitHub Actions 自动运行 Jekyll，将 Markdown 编译成 HTML 并发布到 GitHub Pages。

## 第一次启用 Pages

把仓库推送到 GitHub 后，在仓库中打开：

```text
Settings → Pages → Source → GitHub Actions
```

之后每次推送到 `main`，workflow 都会重新生成网站。

## 需要学生理解的概念

```text
Markdown 文章
      ↓
Jekyll / GitHub Actions
      ↓
HTML 页面
      ↓
GitHub Pages URL
```

学生不需要在本地安装 Ruby、Jekyll、Node.js 或 npm。构建发生在 GitHub Actions 上。

## Agent 提示词

```text
/goal 这是一个 Jekyll 静态博客项目。请先读取 README、_config.yml、index.html、_layouts 和 _posts。
以后新增文章时，只在 _posts/ 中创建 YYYY-MM-DD-title.md，并使用现有 Front Matter 和 layout: post。
不要引入 React、Vue、Node.js、npm、外部 CDN 或新的构建工具。
修改前先列出文件和计划；修改后检查 Markdown Front Matter、文章链接、相对资源路径和 Git diff。
我确认目标仓库后，才执行 git commit 和 git push。
```
