---
title: Obsidian 结合 MkDocs
aliases: 
author: chushen
tags:
  - obsidian
  - mkdocs
  - 博客
  - 网站
  - github
categories:
  - 网站
  - 博客
description: 使用 obsidian-enveloppe 插件快速搭建基于 MkDocs 的网站，可缩短发布流程
date: 2025-03-17T13:07:26+08:00
abbrlink: 20250317130726
updated: 2025-03-20T16:45:22+08:00
share: true
status: new
---
# Obsidian 结合 MkDocs

[TOC]

## 背景

之前的[[./使用Obsidian、Hexo、MkDocs搭建个人博客|个人博客搭建方案]]还是过于繁琐, 不方便发布。步骤一多人就懒

前段时间翻了翻 [2024 Gems of the year winners - Obsidian](https://obsidian.md/blog/2024-goty-winners/)，发现[这款插件](https://github.com/Enveloppe/obsidian-enveloppe)，配置好后只需在 Obsidian 中添加一个属性，然后点击即可发布。使用无负担，数据不丢失

话不多说，这就来看看部署流程

## 配置 GitHub 仓库


1. 在 [Mkdocs](https://enveloppe.ovh/wikis/Mkdocs/#quick-installation-tutorial) 的指导下，使用[提供的mkdocs模板](https://github.com/enveloppe/mkdocs/generate) 创建自己的仓库
2. 然后按照这个仓库的说明添加 `GH_TOKEN` 并进行后续操作。这里我用的是[细粒度权限 token](https://github.com/settings/personal-access-tokens/new)
3. 然后填写信息运行 `Generate website`
	- 不出意外应该会失败，出现此错误👉 `The URL isn't valid`。不过不用担心，不用管
4. 配置 `Pages`

*下面配置可选*

### 域名

如果有自己域名，并在 GitHub `Pages` 中填写了，那记得在 `docs` 目录下添加 `CNAME`，不然部署时会将仓库里设置的 `Custom domain` 清空。

添加后 [[../../../MkDocs使用手册|MkDocs]] 执行部署时会将此文件添加到根目录


### 字体

1. 将 `mkdocs.yml` 中的 `font` 注释掉
2. 使用[霞鹜文楷屏幕阅读版 网络字体仓库](https://github.com/CMBill/lxgw-wenkai-screen-web) ，在 `mkdocs.yml` 中新增 
	```yml
	extra_css:
	    - https://cdn.jsdelivr.net/npm/lxgw-wenkai-screen-web/lxgwwenkaiscreen/result.css
	    - _static/css/font.css
	```
3. 在 `_static/css` 目录下新建 `font.css`，并填写
	```css
	body {
	    font-family: "LXGW WenKai Screen",sans-serif;
	    font-weight: normal;
	}
	```

### 评论

按照文档操作👉 [Adding a comment system - Material for MkDocs](https://squidfunk.github.io/mkdocs-material/setup/adding-a-comment-system/)

注释掉 `overrides\partials\comments.html` 中的 `if page.meta.comments&endif` 即可为所有文章开启评论，从而无需在文章中添加 `comments` 属性

### 字数统计及阅读时间插件

按照[文档](https://github.com/TonyCrane/mkdocs-statistics-plugin)在 `mkdocs.yml` 中添加插件

Obsidian-enveloppe 插件使用 uv 管理依赖配置，把前面创建的仓库克隆下来，执行命令更新下配置文件：
```shell
pip install uv
uv add mkdocs-statistics-plugin
```

### 本地化

有些比较隐蔽的提一下：
- `overrides\partials\source-file.html` 中将作者 `Auteur` 修改为 `Author`
-  `mkdocs.yml` 中修改 `git-revision-date-localized` 的 `locale` 为 `zh`

### 其他

 详细阅读[官方文档](https://squidfunk.github.io/mkdocs-material/getting-started/) ，按需修改 `mkdocs.yml` 进行个性化设置

## Obsidian 安装插件

前面的操作完成后，在 Obsidian 中安装插件。然后按照 [Github Configuration](https://enveloppe.ovh/Settings/Github/) 进行配置

1. `token` 可以和前面生成的共用一个
2. 目录设置，个人使用的是属性 `Property key` ，对应 `categories`。另外目录确保以 `docs` 开头，不然 MkDocs 不会生成对应文章。同理，后面的图片目录也要以 `docs` 开头
3. 开启 `File Menu`，这样可以在编辑模式下可右键上传，也可在文件菜单中选择上传。
	- 对应 `Upload single current active note` 命令，只会上传当前文件及其链接的分享文件（即符合 `share: true` 的文件）

*下面配置可选*

### 修改 PR 标题

修改 [PR 标题](https://github.com/Enveloppe/obsidian-enveloppe/blob/d86555227f455c1f4382d772a3bf0e319e3aaf6a/src/main.ts#L245)，打开此插件目录，这里是 `obsidian-mkdocs-publisher`，在 `main.js` 中搜索 `app.vault.getName`。

删除 `${this.app.vault.getName().replaceAll(" ","-").replaceAll(".","-")}-` 即可将 PR 标题中的 Obsidian 仓库名去掉，只保留日期

### 中文目录链接

对于中文标题必须进行修改后才能正确跳转链接

-  `mkdocs.yml` 中添加 `slugify`，指定[处理逻辑](https://squidfunk.github.io/mkdocs-material/setup/extensions/python-markdown/?h=permalink#+toc.slugify)
	```yml
	markdown_extensions:
	- toc:
	    permalink: true
	    slugify: !!python/object/apply:pymdownx.slugs.slugify {}
	```
- Obsidian 中将 `Sluglify anchor in markdown links` 设置为 `Convert all to ……` (strict 模式)

不过由于 [obsidian-enveloppe](https://github.com/Enveloppe/obsidian-enveloppe/blob/d86555227f455c1f4382d772a3bf0e319e3aaf6a/src/conversion/links.ts#L290) 使用的 [slugify](https://www.npmjs.com/package/slugify) 包与 [pymdown](https://facelessuser.github.io/pymdown-extensions/extras/slugs/) 不同，细节上还是有差别，比如 `/` 的处理，导致不是完美匹配

## 成果

- [GitHub - chu-shen/obsidian-mkdocs](https://github.com/chu-shen/obsidian-mkdocs)


## 已知不足

- 双链、悬浮预览，具体可以对比 [[../../Obsidian/Obsidian插件推荐#网络发布 / obsidian-digital-garden&Hexo|obsidian-digital-garden示例站点]]
	- 悬浮预览使用的是 [Tippy.js](https://tippyjs.bootcss.com/)。效果不好，不能点击，而且必须是完整链接才能预览，所以基本没用
- 部分样式/插件不支持


## 小 tips

- `categories` 如果添加多个，会在目录中形成嵌套关系。如果使用 `/` 也会形成嵌套

| 元数据字段    | 类型  | 说明                                      |
| -------- | --- | --------------------------------------- |
| Share    | 复选框 | 勾选代表分享上传至网络                             |
| Comments | 复选框 | 勾选代表此篇文章开启[[Obsidian 结合 MkDocs#评论\|评论]] |
| Status   | 文本  | 文章状态，MkDocs 支持的 `new`、`deprecated`、自定义  |
