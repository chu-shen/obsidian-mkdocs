---
title: 使用Obsidian、Hexo、MkDocs搭建个人博客
aliases: 
author: chushen
tags:
  - 博客
  - 网站
  - obsidian
  - hexo
  - mkdocs
categories:
  - 网站/博客
description: 通过改造已有插件，形成Obsidian编写文档，Hexo和MkDocs发布的流程
date: 2022-07-12 16:33
abbrlink: 20220712163320
updated: 2025-03-17T23:41:35+08:00
status: deprecated
share: true
---
# 使用Obsidian、Hexo、MkDocs搭建个人博客

> [!error] 已过时
> 最新方案👉 [Obsidian 结合 MkDocs](./Obsidian%20%E7%BB%93%E5%90%88%20MkDocs.md)


[TOC]

## 实现流程

![Obsidian、Hexo、MkDocs流转图.excalidraw.svg](../../_assets/img/Obsidian%E3%80%81Hexo%E3%80%81MkDocs%E6%B5%81%E8%BD%AC%E5%9B%BE.excalidraw.svg)

## 实现步骤

### Obsidian

使用Obsidian正常完成文档的编写。如果要联动Hexo，则还需进行如下配置：

1. 文档元数据必须包含`abbrlink`字段。该字段用于生成永久链接，否则404
2. 安装[Link Server Plugin](https://github.com/moelody/link-info-server)，通过API提供Obsidian文件信息

### Hexo

除了常规配置外，还需要安装以下插件：

1. [hexo-abbrlink](https://github.com/rozbo/hexo-abbrlink)：用于生成永久链接，对应Obsidian的`abbrlink`字段
2. [hexo-link-obsidian](https://github.com/moelody/hexo-link-obsidian)：用于请求Obsidian插件，获取文档信息。处理图片、视频、wiki等链接。
	- 图片被拷贝至`posts`目录
	- 如果转换后的链接文档不在hexo的`_posts`目录中，则此链接修正为404

#### Hexo使用

至此完成了Obsidian和Hexo的联动，只需要执行以下操作即可：

1. 拷贝Obsidian文档至Hexo的`_posts`目录
2. Hexo生成并发布

### MkDocs

<font color=white>虽然Hexo非常不错，但不折腾就难受</font>

鉴于Hexo部分已经把该做的都做了，这里直接偷懒，拷贝一份Hexo处理后的文件到MkDocs目录。

#### 思路

> [!note] 目录说明
> 
> Hexo与MkDocs目录需要在同一级

**TL;DR**

使用[该文件](https://github.com/chu-shen/hexo-link-obsidian/blob/mkdocs/index.js)替换`Hexo/node_modules/hexo-link-obsidian/index.js`即可

**思路如下：**

1. 在Hexo执行图片拷贝时，同时复制一份到MkDocs的`MkDocs/docs/images`目录
2. 将Hexo处理后的MD文件输出到MkDocs的`MkDocs/docs`目录
	- 处理不正确的URL
	- 重新添加元数据信息到处理后的MD
	- 写入到`abbrlink.md`文件
3. 将处理后的文件链接写入到`MkDocs/docs/SUMMARY.md`，推荐搭配mkdocs-literate-nav插件使用

#### MkDocs使用

至此完成Hexo与MkDocs的联动，在[前两步](%E4%BD%BF%E7%94%A8Obsidian%E3%80%81Hexo%E3%80%81MkDocs%E6%90%AD%E5%BB%BA%E4%B8%AA%E4%BA%BA%E5%8D%9A%E5%AE%A2.md#Hexo使用)的基础上执行：

3. 整理`SUMMARY.md`，构建nav导航
4. MkDocs生成并发布

## 成果

- [Hexo](https://chushen.xyz/posts/20220712163320/)
- [MkDocs](https://md.chushen.xyz/20220712163320/)
	- [GitHub - chu-shen/mkdocs-blog](https://github.com/chu-shen/mkdocs-blog)


## 已知不足

### MkDocs

- Categories界面点击分类并无对应子界面
- Categories不兼容当前使用的格式
- RSS无法使用
- Tag不完善
- MkDocs的标题链接为英文+编号，无法对应

