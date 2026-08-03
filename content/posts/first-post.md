---
title: "第一篇文章:Hello, Hugo"
date: 2026-08-03T00:00:00+08:00
draft: false
tags: ["Hugo", "建站"]
description: "用 Hugo + PaperMod 搭建个人博客的第一篇记录。"
---

这是用 **Hugo** 和 **PaperMod** 主题搭建的个人博客的第一篇文章。

## 为什么选 Hugo

Hugo 是一个用 Go 编写的静态网站生成器,优点很明显:

- **速度快** — 几秒钟就能生成整个站点
- **单一二进制** — 没有复杂的依赖
- **Markdown 原生** — 写文章就是写 Markdown

## 为什么选 PaperMod

PaperMod 是个简洁、响应式的 Hugo 主题,特点:

- 自带明暗主题切换
- 搜索、RSS、面包屑一应俱全
- 移动端友好
- 配置项丰富但开箱即用

## 部署到 Cloudflare Pages

Cloudflare Pages 提供**免费**的静态网站托管:

1. 把代码推到 GitHub
2. 在 Cloudflare 后台连接仓库
3. 设置构建命令 `hugo`
4. 完成,自动部署 + 全球 CDN

接下来就开始写吧。
