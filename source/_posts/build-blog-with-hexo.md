---
title: 使用Hexo搭建GitHub Pages个人博客
date: 2026-06-09 14:30:00
tags: [Hexo, GitHub Pages, 教程]
categories: 技术教程
---
# 使用 Hexo 搭建 GitHub Pages 个人博客

## 什么是 Hexo？

[Hexo](https://hexo.io/) 是一个快速、简洁且高效的博客框架。它使用 Markdown 解析文章，在几秒内即可生成静态网页。

## 搭建步骤

### 1. 安装 Hexo

```bash
npm install -g hexo-cli
```

### 2. 初始化博客

```bash
hexo init myblog
cd myblog
npm install
```

### 3. 创建文章

```bash
hexo new "文章标题"
```

### 4. 本地预览

```bash
hexo server
```

访问 `http://localhost:4000` 即可预览。

### 5. 部署到 GitHub Pages

安装部署插件：

```bash
npm install hexo-deployer-git --save
```

配置 `_config.yml`：

```yaml
deploy:
  type: git
  repo: https://github.com/username/username.github.io.git
  branch: main
```

部署命令：

```bash
hexo deploy
```

## 总结

通过以上步骤，你就可以拥有一个免费的、属于自己的个人博客了！
