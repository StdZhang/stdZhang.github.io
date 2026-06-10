---
title: 用Hexo搭了个免费博客
date: 2026-06-09 14:30:00
tags: [Hexo, GitHub Pages, 教程]
categories: 技术教程
---
## 起因

之前一直想搞个个人博客，但要么嫌花钱买服务器，要么嫌折腾。后来发现 GitHub Pages 可以白嫖，那还等什么。

选 Hexo 主要是因为它够轻量，Node.js 一装就能跑，不用像 WordPress 那样还得配数据库。

## 搭建过程

### 装 Hexo

```bash
npm install -g hexo-cli
```

### 初始化

```bash
hexo init myblog
cd myblog
npm install
```

跑完这几条命令，一个基本的博客架子就出来了。

### 写文章

```bash
hexo new "文章标题"
```

然后去 `source/_posts/` 目录下找对应的 md 文件，直接写 Markdown 就行。

### 本地预览

```bash
hexo server
```

浏览器打开 `http://localhost:4000` 就能看到效果，边写边改很方便。

### 部署到 GitHub Pages

要先装个部署插件：

```bash
npm install hexo-deployer-git --save
```

然后在 `_config.yml` 里配一下仓库地址：

```yaml
deploy:
  type: git
  repo: https://github.com/你的用户名/你的用户名.github.io.git
  branch: main
```

最后执行：

```bash
hexo deploy
```

完事。访问 `https://你的用户名.github.io` 就能看到了。

## 踩坑记录

- `hexo init` 的时候 GitHub 连不上，它会自动切到本地复制模式，继续走完就行，不用慌
- 如果用 Git 管理源文件的话，记得把 `public/` 和 `node_modules/` 加到 `.gitignore` 里
- `main` 分支放编译后的静态页面，建议再建个分支专门放源码，不然源文件会被覆盖

## 最后

有免费的空间不用白不用，觉得自己动手能力还行的可以试试。

```bash
hexo deploy
```

## 总结

通过以上步骤，你就可以拥有一个免费的、属于自己的个人博客了！
