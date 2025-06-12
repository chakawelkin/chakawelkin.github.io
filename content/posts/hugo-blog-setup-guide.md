---
title: "Hugo 博客搭建入门指南"
date: 2025-07-20T15:30:00+08:00
draft: false
tags:
  - "Hugo"
  - "博客搭建"
  - "教程"
categories:
  - "技术"
---

## 欢迎来到 Hugo 博客搭建入门指南！

本篇文章将带您了解如何从零开始搭建一个 Hugo 博客，并将其部署到 GitHub Pages。

### 步骤 1：安装 Hugo

首先，您需要安装 Hugo。根据您的操作系统，可以选择不同的安装方式。例如，在 macOS 上可以使用 Homebrew：

```bash
brew install hugo
```

### 步骤 2：创建新站点

安装完成后，您可以创建一个新的 Hugo 站点：

```bash
hugo new site my-new-blog
cd my-new-blog
```

### 步骤 3：添加主题

选择一个您喜欢的主题，例如 LoveIt 主题，并将其添加到您的站点：

```bash
git submodule add https://github.com/dillonzq/LoveIt.git themes/LoveIt
```

然后在 `hugo.toml` 文件中设置主题：

```toml
theme = "LoveIt"
```

### 步骤 4：创建文章

现在您可以开始创建您的第一篇文章了：

```bash
hugo new content posts/my-first-post.md
```

编辑 `content/posts/my-first-post.md` 文件，添加您的内容。

### 步骤 5：部署到 GitHub Pages

要将您的博客部署到 GitHub Pages，您需要配置 GitHub Actions 工作流。一个典型的 `hugo.yml` 文件会包括构建和部署步骤，确保每次代码推送到 `main` 分支时，您的博客都能自动更新。

希望这篇指南能帮助您快速搭建起自己的 Hugo 博客！ 