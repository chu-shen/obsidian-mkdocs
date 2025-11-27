---
title: Obsidian插件推荐
aliases:
author: chushen
tags:
  - obsidian
  - 经验
  - 技巧
  - 插件
categories:
  - Obsidian
description: 合理使用 Obsidian 插件，提高知识流转效率
date: 2023-03-19 13:11:46
abbrlink: 20230319131146
updated: 2025-11-27T18:24:22+08:00
share: true
---
# Obsidian插件推荐

[TOC]

## 背景

社区插件是 Obsidian 一大特色，刚接触这款软件容易陷入**插件地狱**，~~特别是之前没有明确工作流的情况~~ *从未明确，一直再变*😅

为少走弯路，特记录当前使用到的插件，并尽量说明其在工作流中的作用

> [!tip]
> 按需使用，用到再装
> 
> - [PKMer\_Obsidian 插件集市](https://pkmer.cn/products/plugin/pluginMarket/)
> - [Explore New, Updated, Trending, Most Downloaded, and Top Rated Obsidian Plugins](https://www.obsidianstats.com/)

## 核心增强

### 数据库 / Base

[Introduction to Bases - Obsidian Help](https://help.obsidian.md/bases)

**特点：**

- 官方功能，无[[Obsidian插件推荐#文件夹数据库 / obsidian-db-folder|性能问题]]
- 简单易用

**实践：**

- 开发中，功能不完善
- 缺少 [[Obsidian插件推荐#文件夹数据库 / obsidian-db-folder|db-folder]] 中的 `关联` 与 `关联对象引用` 类型字段，无法多表关联
- 样式平庸
- 无分页功能
- 新建功能不支持模板，或者说其模板逻辑还不完善

### 数据查询 / obsidian-dataview

> [!attention] 最新动态
> 原作者开发的后继者 [datacore](https://github.com/blacksmithgu/datacore/)，截止2025年3月12日仍未发布正式版本

> [!info] 官方路线
> 新核心插件 Base/数据库已发布
> 
> ~~根据 [Obsidian Roadmap - Obsidian](https://obsidian.md/roadmap/) 来看，截止2025年3月19日，正在筹备类似功能：~~
> ~~- **Dynamic views**: Create dynamic tables using data stored in note properties.~~


[obsidian-dataview](https://github.com/blacksmithgu/obsidian-dataview) 插件提供了查询库中数据的方法

**特点：**

- 数据查询

**实践：**

见 [[Obsidian插件推荐#库活跃历史热力图 / obsidian-activity-history|activity-history]] 中实践部分。更多示例见插件文档

> [!error] 难度
> 可以先学习简单的使用方法，或者使用基于此插件开发的新插件，如有代码基础可以深入学习从而完成特定需求

> [!tip]
> 可结合 [[Obsidian插件推荐#项目管理 / obsidian-projects|obsidian-projects]] 使用

### 白板 / obsidian-excalidraw-plugin

[obsidian-excalidraw-plugin](https://github.com/zsviczian/obsidian-excalidraw-plugin) 插件将 excalidraw 绘图工具集成到 Obsidian 中

**特点：**

- 绘图工具、手写
- 支持 Obsidian 语法、双链
- 作者有详尽的教程示例

**实践：**

无特殊需求请优先尝试使用自带的 `白板` 功能

### 模板 / quickadd&Templater

[quickadd](https://github.com/chhoumann/quickadd) 插件提供模板、捕获、宏的快捷操作

[Templater](https://github.com/SilentVoid13/Templater) 插件提供了一种模板语言

**特点：**

- 模板
- 自动化

**实践：**

> [!error] 难度
> - quickadd 相对容易上手，且带管理界面，便于操作
> - Templater 则相对较难

关闭自带的 `模板` 核心插件，详细用法见插件文档

要求不高可以替换成自带的 `模板` 核心插件

> [!question]+
> Templater 最开始用过，用来在开头提醒文档日期：`> 本文档最后更新于：**<%+ tp.file.last_modified_date() %>** ，请注意文章时效性！`
> 
> 后面发现不是很好用，其他地方也没用上此插件，QuickAdd 完全满足需求了，至少目前是这样
> 
> 导致现在到处都是上面的提醒句，不好处理

### 工作区增强 / obsidian-workspaces-plus

> [!error] 最新动态
> 此插件目前已停止维护，但不影响使用

[obsidian-workspaces-plus](https://github.com/nothingislost/obsidian-workspaces-plus) 插件增强的自带的 `工作区` 核心插件，提供了更加便捷的管理方式

**特点：**

- 工作区增强

**实践：**

状态栏点击即可创建或切换工作区

现在一般将 `工作区：更新工作区布局` 绑定到 `alt+w` 快捷键，实现切换工作区的**同时保存**工作区布局

> [!tip]
> 此插件还提供了一个保存 Obsidian 设置的模式，可以用在不同模式开关不同插件/主题的场景下。但此插件目前已停止维护，`Modes` 模式难产，半成品，虽可控制不同主题但并没有记录插件的开关
> 
> [Workspace Modes](https://github.com/nothingislost/obsidian-workspaces-plus/issues/59)

### 快速切换 / obsidian-another-quick-switcher&obsidian-omnisearch

[obsidian-another-quick-switcher](https://github.com/tadashi-aikawa/obsidian-another-quick-switcher) 插件提供了更加丰富的搜索功能，用于快速打开文件，支持文件名、标签、标题、链接过滤，替代自带的 `快速切换` 核心插件。

[obsidian-omnisearch](https://github.com/scambier/obsidian-omnisearch) 插件是一个用于 Obsidian 的全文搜索引擎

**特点：**

- 更加丰富的搜索条件/范围
- 全文搜索

**实践：**

安装两个插件，禁用自带的 `快速切换` 核心插件

obsidian-another-quick-switcher 的 landmark 搜索绑定到 `ctrl+o`，用于搜索文件名、标题等。

obsidian-omnisearch 绑定到 `alt+o`，用于全文搜索，也可以选择使用自带的搜索功能

> [!tip]
> 此外 `obsidian-omnisearch` 可以结合使用 [obsidian-text-extractor](https://github.com/scambier/obsidian-text-extractor) 插件来实现图片、文档、PDF 的索引

> [!info] 替代插件
> - obsidian-another-quick-switcher 可替换为 [obsidian-switcher-plus](https://github.com/darlal/obsidian-switcher-plus)，看个人喜好
> - 可继续使用自带的 `搜索` 核心插件来避免安装 obsidian-omnisearch
> - 如果搜索复杂，还可以看看此插件是否符合需求👉 [vantage-obsidian](https://github.com/ryanjamurphy/vantage-obsidian)

### 人工智能 / obsidian-textgenerator-plugin

[obsidian-textgenerator-plugin](https://github.com/nhaouari/obsidian-textgenerator-plugin) 插件将 AI 引入 Obsidian，扩展可能性

**特点：**

- AI 加持
- 提示词模板

**实践：**

> [!question] 发展中
> 目前 Obsidian AI 插件有多个处于开发状态，可以自行选择合适的插件体验
> - 基于标签区分对话角色： [obsidian-tars](https://github.com/TarsLab/obsidian-tars)
> - 基于笔记链接： [obsidian-smart-connections](https://github.com/brianpetro/obsidian-smart-connections)
> - [obsidian-copilot](https://github.com/logancyang/obsidian-copilot)

调整配置，确认传输给 AI 的数据范围及 Token 大小

将命令添加到 [[Obsidian插件推荐#工具栏 / obsidian-editing-toolbar|obsidian-editing-toolbar]] 中，主要使用其 `Generate Text` 功能

另外此插件也附带了[[../../🗞️总结、归纳|模板]]，可以选择合适的使用

> [!attention] 缺点
> - 好像没有连续对话功能
> - 貌似不支持直接传递读取文件，不知道给的 `{{read "readme.md"}}` 咋用

### 手写

[obsidian_ink](https://github.com/daledesilva/obsidian_ink) 插件将能够添加手写模块，不能识别转换

**特点：**

- 手写

**实践：**

还未尝试过

## 编辑增强

### 文本格式化 / easy-typing-obsidian

[easy-typing-obsidian](https://github.com/Yaozhuwa/easy-typing-obsidian) 插件可自动格式化文本，增强符号编辑

**特点：**

- 文档格式化
- 符号编辑增强

**实践：**

中文输入必备，输入的==同时==对本块进行*格式化*

安装并启用后查看插件文档和配置，基本能开启的都开启，需要填写的不动即可

> [!tip] 替代插件
> ~~文本格式化的插件还有 [obsidian-pangu](https://github.com/Natumsol/obsidian-pangu)~~（已停更），更全面的可配置的格式化插件有 [obsidian-linter](https://github.com/platers/obsidian-linter)
> 
> 不过这两个或多或少还是不太便利，初次接触直接选此插件即可

### 中文分词 / cm-chs-patch

[cm-chs-patch](https://github.com/aidenlx/cm-chs-patch) 插件提供中文分词支持

**特点：**

- 中文分词

**实践：**

推荐同时安装 jieba 分词，为 [[Obsidian插件推荐#快速切换 / obsidian-another-quick-switcher&obsidian-omnisearch|obsidian-omnisearch]] 提供更精确的分词结果

### 标注块 / obsidian-admonition&标注

[obsidian-admonition](https://github.com/valentine195/obsidian-admonition) 是一个用于添加及渲染警告块样式的插件

> [!info]
> 目前官方已内置类似的[标注块功能](https://help.obsidian.md/Editing+and+formatting/Callouts)，此插件也已更新支持官方样式

**特点：**

- 标注功能，更加醒目
- 类型可选，官方内置的则没有提示，全靠记忆

**实践：**

必备插件，快速生成所需标注块，相比一般的高亮更容易一眼看到，但其目的不是取代高亮，推荐用于需要重点关注的文本

命令输入 `Callout` 则为官方样式（使用==引用==语法），`Admonition` 则为社区样式（使用==代码块==语法）

支持的标注类型有：

| Type     | Aliases                     |
| -------- | --------------------------- |
| note     | note, seealso               |
| abstract | abstract, summary, tldr     |
| info     | info, todo                  |
| tip      | tip, hint, important        |
| success  | success, check, done        |
| question | question, help, faq         |
| warning  | warning, caution, attention |
| failure  | failure, fail, missing      |
| danger   | danger, error               |
| bug      | bug                         |
| example  | example                     |
| quote    | quote, cite                 |

> [!warning] 缺点
> - 样式兼容性：由于此标注块不属于 [[../../Markdown|Markdown]] 原生语法，因此 Obsidian 的样式与其他家不一定相同，在其他平台使用时需要注意修改样式
> 	- Github 部分支持，比如 Callout 的 `Tip`
> - 目前进入了仅维护状态


> [!note] 搭配
> - $ [obsidian-list-callouts](https://github.com/mgmeyers/obsidian-list-callouts) 插件通过固定的前缀（详见配置）使列表同样能表现出标注的样式 


### 表格增强 / advanced-tables-obsidian&表格

[advanced-tables-obsidian](https://github.com/tgrosinger/advanced-tables-obsidian) 插件提供表格增强功能

**特点：**

- 对齐、移动、增删、排序、公式、导出
- 快速生成表格

**实践：**

> [!attention]
> ~~推荐两个插件同时使用~~，随着[官方对表格的支持](https://obsidian.md/changelog/2024-03-19-desktop-v1.5.11/)，[obsidian-table-generator](https://github.com/quorafind/obsidian-table-generator) 插件提供表格快速生成功能的优势不再明显，已退出历史舞台
> - `obsidian-table-generator` 插件则注册到右键菜单，点击后选择行列数即可
> 	- 需要注意，`obsidian-table-generator` 插件的行数包含了标题行

- `advanced-tables-obsidian` 提供了一个插件页面，可以拖放到两侧放置使用

`advanced-tables-obsidian` 公式的使用参见文档 [formulas.md](https://github.com/tgrosinger/md-advanced-tables/blob/main/docs/formulas.md)，[命令执行方式](https://github.com/tgrosinger/advanced-tables-obsidian/blob/main/docs/help.md)，下面是一个使用公式计算总数的例子👇

| Item              | Grams |
| ----------------- | ----- |
| Whole Wheat Flour | 110   |
| Bread Flour       | 748   |
| Warm Water        | 691   |
| Salt              | 18    |
| Starter           | 40    |
| **Total Grams**   | 1607  |
<!-- TBLFM: @>$2=sum(@I..@-1) -->

### 工具栏 / obsidian-editing-toolbar

[obsidian-editing-toolbar](https://github.com/cumany/obsidian-editing-toolbar) 基于 [cMenu-Plugin](https://github.com/chetachiezikeuzor/cMenu-Plugin) 魔改而来，是一个类似 MicroSoft Word 中工具栏的插件

**特点：**

- 类富文本软件的工具栏
- 自定义工具栏
- 工具栏位置可选
- 子菜单
- 更多内置命令

**实践：**

*重新修改适配 3.0.1 版本，将 cMenu 前缀替换为 editing（2025 年 3 月 20 日）*

<font color="#00b0f0">设置多个工具栏的方法：</font>

1.  复制一份插件文件夹，改名为 `editing-toolbar-2`，并启用
2.  修改`manifest.json`中`id`为`editing-toolbar-2`
3.  替换 `main.js` 和 `styles.css` 中的 `editingToolbarModalBar` 为 `editingToolbarModalBar2`

<font color="#00b0f0">修改默认样式：</font>

默认的样式不太符合我，而且图标偏小，这里使用自带的 `CSS代码片段` 功能来覆盖样式，样式如下：

```css
/*----------------------------------------------------------------  
包含：editingToolbarModalBar，following模式适用  
----------------------------------------------------------------*/  
  
/* Button resize */  
:is(#editingToolbarModalBar,#editingToolbarPopoverBar) svg{  
height: 24px !important;  
width: 24px !important;  
max-width: 24px  !important;  
max-height: 24px  !important;  
}  
  
/*----------------------------------------------------------------  
悬浮效果  
----------------------------------------------------------------*/  
#editingToolbarModalBar button.editingToolbarCommandItem:hover {  
  background-color: var(--interactive-accent-hover);  
}  
:is(#editingToolbarModalBar, #editingToolbarPopoverBar) button[class^=editingToolbarCommandsubItem]>.subitem button.menu-item:hover{  
  background-color: var(--interactive-accent-hover);  
}



/*----------------------------------------------------------------  
包含：editingToolbarModalBar2，fixed模式适用  
----------------------------------------------------------------*/  
  
/* Button resize */  
  
:is(#editingToolbarModalBar2,#editingToolbarPopoverBar) svg{  
height: 20px !important;  
width: 20px !important;  
max-width: 20px  !important;  
max-height: 20px  !important;  
}  
  
  
/*----------------------------------------------------------------  
边框+阴影  
----------------------------------------------------------------*/  
#editingToolbarModalBar2.editingToolbarGlassAesthetic{  
  box-shadow: 0px 3px 32px rgb(31 38 135 / 15%);  
  border: 1px solid var(--background-modifier-border);  
}  
  
/*----------------------------------------------------------------  
图标大小  
----------------------------------------------------------------*/  
#editingToolbarModalBar2 .editingToolbarCommandItem {  
  margin: 2px;  
  padding: 5px 6px;  
  margin-left: 3px;  
  margin-right: 3px;  
  border-radius: 3px;  
}  
#editingToolbarModalBar2 [class^=editingToolbarCommandsubItem] {  
  margin: 2px;  
  padding: 5px 6px;  
  margin-left: 3px;  
  margin-right: 3px;  
  border-radius: 3px;  
}  
#editingToolbarModalBar2 [class^=editingToolbarCommandsubItem] >.subitem button.menu-item{  
  margin: 2px;  
  padding: 5px 6px;  
  margin-left: 3px;  
  margin-right: 3px;  
  border-radius: 3px;  
}  
  
/*----------------------------------------------------------------  
悬浮效果  
----------------------------------------------------------------*/  
#editingToolbarModalBar2 button.editingToolbarCommandItem:hover {  
  background-color: var(--interactive-accent-hover);  
}  
:is(#editingToolbarModalBar2, #editingToolbarPopoverBar) button[class^=editingToolbarCommandsubItem]>.subitem button.menu-item:hover{  
  background-color: var(--interactive-accent-hover);  
}  
  
/* 隐藏右下角状态栏图标 */  
/* .editingToolbar-statusbar-button{  
  display: none  
} */
```

常用操作放在 following 模式的工具栏中，不常用及带子菜单的则放在 fixed 模式的工具栏中

> [!tip] 类似插件
> - 除了这个工具栏外，还可以选择安装 [Enhanced-editing](https://github.com/obsidian-canzi/Enhanced-editing) 插件，提供更多选项。适合喜欢工具栏操作，而非 [[../../Markdown|Markdown]] 编辑的用户
> 
> - 另一款类似且在维护的插件👉 [obsidian-note-toolbar](https://github.com/chrisgurney/obsidian-note-toolbar)


### 页面预览 / obsidian-hover-editor

[obsidian-hover-editor](https://github.com/nothingislost/obsidian-hover-editor) 插件将自带的 `页面预览` 核心插件扩展为完整的编辑器实例

**特点：**

- 功能完整的页面预览窗口
- 窗口可固定不消失
- 边缘吸附

**实践：**

> [!fail]+ 缺陷
> 此插件完整加载整个文档，导致比官方的部分加载速度要慢很多，我只在全文预览中使用+吸附模式
> - 加载有点慢[Preview is too slow when there is too much file content](https://github.com/nothingislost/obsidian-hover-editor/issues/265)
> - 设置里选择阅读视图时没法自动跳转，大文档才发现有此问题

### 列表增强 / obsidian-outliner

[obsidian-outliner](https://github.com/vslinko/obsidian-outliner) 插件提供了增强列表操作的快捷操作

**特点：**

- 列表操作增强

**实践：**

### 自动补全 / obsidian-various-complements-plugin

[obsidian-various-complements-plugin](https://github.com/tadashi-aikawa/obsidian-various-complements-plugin) 插件提供自动补全功能

**特点：**

- 自动补全
- 可添加字典

**实践：**

按需修改配置。输入时会自动弹出候选

**自动添加别名**：当自动补全选择的是文件时，其行为与官方类似，将自动添加别名。借用 `Insert an alias that is transformed from the displayed internal link` 功能，将 `before` 设置为 `.+/(.+)`，将 `after` 设置为 `$1`。原理是匹配最后一个 `/` 后的内容，然后作为别名。


### 链接增强 / obsidian-auto-link-title

[obsidian-auto-link-title](https://github.com/zolrath/obsidian-auto-link-title) 插件会自动将粘贴的网页链接转为 [[../../Markdown|Markdown]] 链接并自动获取链接标题

**特点：**

- 自动处理粘贴的链接
- 可设置域名黑名单

**实践：**

非常实用的插件

### 链接格式转换 / wikilinks-to-mdlinks-obsidian

[wikilinks-to-mdlinks-obsidian](https://github.com/agathauy/wikilinks-to-mdlinks-obsidian) 插件可自动将 wiki 链接和 markdown 链接进行互换

**特点：**

- 链接转换

**实践：**

选中链接，输入命令转换即可

使用 [[Obsidian插件推荐#自定义命令 / obsidian-commander|obsidian-commander]] 将命令添加到右键菜单

> [!error] 问题
> - 中文会被编码
> - 链接是相对链接

### 自定义命令 / obsidian-commander

[obsidian-commander](https://github.com/phibr0/obsidian-commander) 插件可将命令添加到界面，如：侧边栏、标题栏、状态栏、右键菜单、文件菜单

**特点：**

- 添加、隐藏命令
- 重命名命令
- 修改图标、颜色

**实践：**

安装启用后在界面上添加删除，部分位置不会显示添加符号，此时可以在插件配置界面操作

标签页上的标题栏（页首）中可以添加：收拢侧边栏 ([[Obsidian插件推荐#工具栏 / obsidian-editing-toolbar|Editing Toolbar]])、移至新窗口、禅模式 ([[Obsidian插件推荐#打字机模式 / obsidian-typewriter-mode|Typewriter Mode]])、打字机模式 ([[Obsidian插件推荐#打字机模式 / obsidian-typewriter-mode|Typewriter Mode]])

> [!tip]
> 左侧工具栏可以使用自带的 `工具栏` 隐藏命令，不同工作区可==分别设置==
> 
> 而此插件的配置则是==全局==，不受工作区影响

### 自定义斜杠命令 / obsidian-slash-commander

[obsidian-slash-commander](https://github.com/alephpiece/obsidian-slash-commander) 插件能够自定义斜杠命令

**特点：**

- 自定义斜杠命令

**实践：**

需要关闭自带的斜杠命令核心插件

斜杠命令感觉用的不多啊，按需选择

### Canvas 增强 / obsidian-advanced-canvas

[obsidian-advanced-canvas](https://github.com/Developer-Mike/obsidian-advanced-canvas) 插件增强了 `Canvas` 核心插件的编辑体验

**特点：**

- 更多样式
- 演示模式
- 可折叠组

**实践：**

~~越简单越好不是吗，总有一天要长得和 [[Obsidian插件推荐#画板 / obsidian-excalidraw-plugin&白板|excalidraw]] 一样~~

内容多的话比较卡

### 虚拟双链 / Obsidian-virtual-linker

[obsidian-virtual-linker](https://github.com/vschroeter/obsidian-virtual-linker) 插件自动为文本生成虚拟双链

**特点：**

- 双链

**实践：**

不用点击自带的出链列表就可以直接在文章上看到，更加直观

## 文件分享

### 块 ID 生成 / obsidian-copy-block-link

[obsidian-copy-block-link](https://github.com/mgmeyers/obsidian-copy-block-link) 插件可快速生成块ID

**特点：**

- 生成块 ID 链接至剪贴板，免去手动输入

**实践：**

安装启用后，在块位置右键选择生成块 ID 即可，第一个是链接，第二个是嵌入的链接

### 幻灯片 / obsidian-advanced-slides&幻灯片

[obsidian-advanced-slides](https://github.com/MSzturc/obsidian-advanced-slides) 增强自带的演示功能

**特点：**

- 支持实时预览
- 有些官方幻灯片没有的小功能

**实践：**

安装后会在左侧功能区显示切换按钮

使用此插件制作幻灯片的同时进行预览调整，使用自带的演示功能全屏演示

更多功能见插件文档

> [!info] 其他插件
> [obsidian-marp-plugin](https://github.com/JichouP/obsidian-marp-plugin) 插件将 Marp 引入了 Obsidian 
> - 支持导出为 PPT
> - 没法直接在 obsidian 中开始演示
> - 对图片及 [[../../Markdown|Markdown]] /HTML 语法支持差

### 文档时间提示 / obsidian-old-note-admonitor

[obsidian-old-note-admonitor](https://github.com/tadashi-aikawa/obsidian-old-note-admonitor) 插件用于提示当前文档多久未更新

**特点：**

- 文档更新时间提示

**实践：**

安装并启用，设置提示时间与排除的文件路径

提示信息：`本文档最后更新于 ${numberOfDays} 天前，请注意文章时效性！`

### 文档导出 / obsidian-better-export-pdf&PDF

将 Obsidian 中的文档导出到外部，包括但不限于：PDF、HTML、[[../../Markdown|Markdown]]……

> [!info]
> 目前并没有发现比较完美的导出方法/插件

[obsidian-better-export-pdf](https://github.com/l1xnan/obsidian-better-export-pdf) 是一个 Obsidian PDF 导出增强插件，与官方的 PDF 导出功能相比，增加了导出预览、导出书签大纲和给 PDF 添加页码、合并导出……等重磅功能

**特点：**

- 导出 PDF 等格式
- PDF 带大纲书签、元数据
- 支持页边距、页眉页脚、文档属性、链接跳转
- 目录、多文件合并导出

**实践：**

官方的 PDF 导出没法添加书签、保留链接……效果非常一般。推荐使用最近才发现的 `obsidian-better-export-pdf` 插件

此外还可以查看👉 [[../../导入与导出Markdown|导入与导出Markdown]]

> [!note] 类似插件
> 如果除了导出 PDF 外还有其他需求，可以尝试使用 Pandoc 导出： [GitHub - mokeyish/obsidian-enhancing-export: This is an enhancing export plugin base on Pandoc for Obsidian (https://obsidian.md/ ). It's allow you to export to formats like Markdown、Markdown (Hugo https://gohugo.io/ )、Html、docx、Latex etc.](https://github.com/mokeyish/obsidian-enhancing-export)
> 


### 网络发布 / obsidian-digital-garden&Hexo

[obsidian-digital-garden](https://github.com/oleeskild/obsidian-digital-garden) 插件支持将 Obsidian 中的文章发布到网上并且尽可能与 Obsidian 中的文章一致

**特点：**

- 原模原样：尽可能保留 Obsidian 特色的同时，将文章发布出去

**实践：**

详细设置见插件文档，有相应说明及示例网站。其原理就是静态网站，只是相比其他静态网站技术，此插件专门针对 obsidian 做了相应修改

此外还可以采用其他[[../../Markdown生成静态站点的方案与步骤|静态网站方案]]，比如[[../网站/博客/使用Obsidian、Hexo、MkDocs搭建个人博客|使用Obsidian、Hexo、MkDocs搭建个人博客]]：
- 使用 [link-to-server](https://github.com/moelody/link-to-server) 插件，用于开启反向代理，向外部提供 Obsidian 中文件信息。搭配 [hexo-link-obsidian](https://github.com/moelody/hexo-link-obsidian) 插件处理接受到的文档，从而实现 Obsidian 到 Hexo。支持图片导出，链接转换，但部分 Obsidian 语法不支持

> [!info] 其他插件
> 从单个文件、画布页面或整个库导出 html，且支持各插件样式：[GitHub - KosmosisDire/obsidian-webpage-export: Export html from single files, canvas pages, or whole vaults. Direct access to the exported HTML files allows you to publish your digital garden anywhere. Focuses on flexibility, features, and style parity.](https://github.com/KosmosisDire/obsidian-webpage-export)

> [!info] Hexo 插件
> - [GitHub - lifeodyssey/obsidian-hexo-auto-update](https://github.com/lifeodyssey/obsidian-hexo-auto-update)
> - [GitHub - yy4382/obsidian-static-site-export: Export specific notes to general md for static site generation, such as Hexo, Hugo, or Astro](https://github.com/yy4382/obsidian-static-site-export)

### Mkdocs 静态站点 / obsidian-enveloppe

[obsidian-enveloppe](https://github.com/Enveloppe/obsidian-enveloppe) 插件支持将 Obsidian 中的文章发布到 Github，并且可以选择配置 Mkdocs

**特点：**

- 原模原样：尽可能保留 Obsidian 特色的同时，将文章发布出去

**实践：**

> [!tip]+ 对比
> 此插件相较于 [[Obsidian插件推荐#网络发布 / obsidian-digital-garden&Hexo|obsidian-digital-garden]]，前者像是技术性博客，后者更接近 Obsidian，更像笔记

详细实践过程见 [[../网站/博客/Obsidian 结合 MkDocs|Obsidian 结合 MkDocs]]

## 外观美化

### 横幅

提供横幅功能

**特点：**

- 横幅可拖动
- 多样式
- 可指定图片源

**实践：**

在 front matter 中填写 banner，选择图片即可。可以在日记模板中使用

> [!attention] 缺乏维护
> [obsidian-banners](https://github.com/noatpad/obsidian-banners) 开发者虽然更新了测试版用于适应新版本 Obsidian 带来的变化，但开发目前又停滞了，新版本也未发布

> [!info]+ 类似插件
> [GitHub - jparkerweb/pixel-banner: 🚩 Plugin for Obsidian that allows you to automatically add beautiful banner images to your notes from various sources.](https://github.com/jparkerweb/pixel-banner)


### Emoji / iconic

[iconic](https://github.com/gfxholo/iconic) 可自定义图标和颜色并支持规则

**特点：**

- 添加 Emoji
- Emoji 面板
- 自定义图标和颜色并支持规则

**实践：**

> [!NOTE]
> [obsidian-emoji-toolbar](https://github.com/oliveryh/obsidian-emoji-toolbar) 是一个提供插入 Emoji 表情面板的插件
> 
> `obsidian-emoji-toolbar` 可以搭配 [[Obsidian插件推荐#工具栏 / obsidian-editing-toolbar|obsidian-editing-toolbar]] 使用，不过此插件存在焦点问题，当前需要下载 [GitHub - PKM-er/Blue-topaz-example](https://github.com/PKM-er/Blue-topaz-example) 中修复后的插件使用

> [!failure] obsidian-iconize 停止维护
> [obsidian-iconize](https://github.com/FlorianWoelki/obsidian-iconize) 插件可为任何地方插入 Emoji
> 
> [Project Deprecation and End of Maintenance](https://github.com/FlorianWoelki/obsidian-iconize/discussions/646)
> 
> ~~`obsidian-iconize` 每次更新后 bug 都比较多。目前是文本插入 Emoji 使用 `obsidian-emoji-toolbar` 插件，其他使用 `obsidian-iconize`~~

### 链接图标 / obsidian-link-favicon

[obsidian-link-favicon](https://github.com/joethei/obsidian-link-favicon) 插件在链接前添加对应的网站图标

**特点：**

- 为链接添加图标

**实践：**

安装启用，然后选择对应的图标提供方即可

主要是用于快速识别链接来源

### 图片工具 / obsidian-image-toolkit

[obsidian-image-toolkit]( https://github.com/sissilab/obsidian-image-toolkit ) 插件用于增强 Obsidian 中图片处理

**特点：**

- 图片预览、缩放、旋转……

**实践：**

> [!note] 类似插件
>  [obsidian-image-converter](https://github.com/xRyul/obsidian-image-converter) 支持：转换、压缩、调整大小、注释标记……


### 文件计数 / file-explorer-note-count

[file-explorer-note-count](https://github.com/ozntel/file-explorer-note-count) 插件用于统计库中各文件夹下的文件数量

**特点：**

- 文件数量统计

**实践：**

### 选项卡历史 / pane-relief

[pane-relief](https://github.com/pjeby/pane-relief) 插件增强了选项卡历史

**特点：**

- 选项卡历史
- 焦点锁定

**实践：**

焦点锁定可防止侧边栏窗格窃取焦点，右下角状态栏切换

### CSS 调整 / obsidian-style-settings

[obsidian-style-settings](https://github.com/mgmeyers/obsidian-style-settings) 插件允许修改主题、插件的 CSS 代码

**特点：**

- 个性化设置

**实践：**

安装启用即可。支持的主题或插件，可在此插件的配置界面调整 CSS 样式

### 主题切换 / obsidian-theme-picker

[obsidian-theme-picker](https://github.com/kenset/obsidian-theme-picker) 插件允许快速切换主题及亮暗模式

**特点：**

- 主题切换
- 亮暗模式切换

**实践：**

安装启用即可。此时右下角状态栏会显示 `Change Theme` 和亮暗切换图标

### 主页 / obsidian-homepage

[obsidian-homepage](https://github.com/mirnovov/obsidian-homepage) 插件可在启动 Obsidian 后打开指定的笔记、画布或工作区。

**特点：**

- 主页

**实践：**

不能打开指定链接

### 标签着色 / obsidian-colored-tags

[obsidian-colored-tags](https://github.com/pfrankov/obsidian-colored-tags) 插件可为标签随机上色

**特点：**

- 标签随机上色

**实践：**

标签指定颜色的话要用👉[GitHub - code-of-chaos/obsidian-colored\_tags\_wrangler: Obsidian Plugin : Assign colors to tags. Has integrations with other plugins, like Kanban.](https://github.com/code-of-chaos/obsidian-colored_tags_wrangler)

## 目录

### 自动目录 / obsidian-plugin-dynamic-toc

[obsidian-plugin-dynamic-toc](https://github.com/fnumatic/obsidian-plugin-dynamic-toc) 插件用于自动生成文档目录并与大纲保持一致

**特点：**

- 目录自动更新
- 多种指定目录方式

**实践：**

安装并启用后选择创建 TOC 的方式即可

可使用  `[TOC删除中文]` 样式来指定生成目录

> [!failure] 问题
> 使用自带的 PDF 导出功能，目录会生成在文档的末尾并且无法点击，[[Obsidian插件推荐#文档导出 / obsidian-better-export-pdf&PDF|obsidian-better-export-pdf]] 正常

> [!danger] 最新动态
> [插件原作者已不再更新](https://github.com/Aidurber/obsidian-plugin-dynamic-toc)，新的维护者未在社区上线此插件，因此需要使用 [[Obsidian插件推荐#Beta 插件 / obsidian42-brat|obsidian42-brat]] 进行安装和更新，*当然也可以选择手动安装更新*
> 
> `0.0.37` 版本的实时阅览模式有问题，与 [[Obsidian插件推荐#文本格式化 / easy-typing-obsidian|easy-typing]] 冲突，无法使用，目前仍旧使用旧插件的 `0.0.27` 版本

> [!tip] 类似插件
> 如果需要一次性生成目录而非插件渲染，可以考虑使用 [obsidian-plugin-toc](https://github.com/hipstersmoothie/obsidian-plugin-toc)
> 
> 如果要通过代码渲染目录，可以考虑使用 [obsidian-automatic-table-of-contents](https://github.com/johansatge/obsidian-automatic-table-of-contents)，缺点是其他 [[../../Markdown|Markdown]] 编辑器无法识别

### 侧边目录 / obsidian-floating-toc-plugin

> [!attention] 缺乏维护
> 此插件缺乏维护，在大文档中性能低下（10k 词，36k 字符）。实践中提到的定位问题可以改成用 [[Obsidian插件推荐#大纲 / obsidian-quiet-outline|obsidian-quiet-outline]]
> 
> 2025年3月19日发现恢复更新并[优化大文档下性能表现](https://github.com/PKM-er/obsidian-floating-toc-plugin/releases/tag/2.5.0)，未确认是否可用

[obsidian-floating-toc-plugin](https://github.com/cumany/obsidian-floating-toc-plugin) 插件提供文档侧边目录的功能

**特点：**

- 侧边目录
- 自动定位

**实践：**

安装并启用，配置侧边目录位置和样式

自带的 `大纲` 功能无法自动定位当前位置，插件生成的目录在顶部，对于确认当前位置都不太方便，而此插件则填补这块不足之处

感觉特别适合小屏幕设备

### 大纲 / obsidian-quiet-outline

[obsidian-quiet-outline](https://github.com/guopenghui/obsidian-quiet-outline) 插件提供了一个新的大纲视图

**特点：**

- 大纲视图
- 自动定位
- 自动展开折叠
- 搜索、正则……

**实践：**

安装启用，关闭自带的 `大纲` 核心插件

相对于自带的插件，此插件能够实时定位当前位置，而不只是装饰

### 文件夹查看 / quick-explorer

[quick-explorer](https://github.com/pjeby/quick-explorer) 可以用来快速查看和操作文件夹

**特点：**

- 直接在标题栏操作文件
- 支持键盘上下左右快速切换

**实践：**

左键查看文件夹，右键则是命令菜单

在 `obsidian-style-settings` 中隐藏此插件的底部状态栏，此时插件功能通过文档顶部标题栏实现，Obsidian 原来的点击在文件列表定位当前文件/文件夹的功能则失效

> [!note] 快捷键
> 设置 `Ctrl+Q` 快捷键，快速打开当前文件夹

### 最近文件 / recent-files-obsidian

[recent-files-obsidian](https://github.com/tgrosinger/recent-files-obsidian) 插件在侧边栏添加了一个最近打开文件的视图

**特点：**

- 最近文件

**实践：**

安装启用，配置排除文件路径

### 搜索增强 / better-search-views

[better-search-views](https://github.com/ivan-lednev/better-search-views) 插件改善了搜索视图，为其带来了上下文

**特点：**

- 搜索结果带上下文
- 搜索结果带面包屑

**实践：**


### 垂直标签 / obsidian-vertical-tabs

[obsidian-vertical-tabs](https://github.com/oxdc/obsidian-vertical-tabs) 插件为标签页引入了新的垂直方案

**特点：**

- 可分组
- 不同于自带的堆叠标签页功能

**实践：**

浏览器样式的标签页过大将导致标题展示不全，通过新开一个选项卡展示所有标题

## 其他特殊功能

### 库活跃历史热力图 / obsidian-activity-history

[obsidian-activity-history](https://github.com/Darakah/obsidian-activity-history) 是一个实现类似 Github 活跃热力图的插件

**特点：**

- 监控指定库活跃情况（大小）

**实践：**

> [!error] 警告
> 不推荐深究此插件，除非你有能力且迫切需要制作类似 HoemPage 的页面
> 
> 此插件已停止维护，所用的可视化库也已停止维护
> 
> - ! 2025年2月6日发现作者连 Github 号都销了🥲

[[../../ActivityHistory|ActivityHistory]]

> [!info] 数据源
> 此插件记录的是整个 Obsidian 库大小变化。
> 
> 另一个插件 [[Obsidian插件推荐#字数统计增强 / better-word-count|better-word-count]] 则是记录文字变化，不过此数据并没有利用上，仅仅躺在那儿

> [!note] 类似插件
> - 此外还有一个 [heatmap-calendar-obsidian](https://github.com/Richardsl/heatmap-calendar-obsidian) 插件可用，可以记录各种事件（锻炼/学习/……）的热力图，不过在使用前需要明确你的需求以及是否有更好的专用软件实现此功能，需要结合 [[Obsidian插件推荐#数据查询 / obsidian-dataview|dataview]] 使用
> 
> - [obsidian-contribution-graph](https://github.com/vran-dev/obsidian-contribution-graph) 插件则是另一个新秀，同样需要结合 [[Obsidian插件推荐#数据查询 / obsidian-dataview|dataview]] 使用。不过此插件还提供了一个人性化的配置界面，应付简单使用是完全没问题的
> 
> 上面这些插件都是利用的**外部数据**，但是像库大小变化、字数变化等等则没有数据来源/集成，因此是没法实现基于这些数据的图表的
> 
> - 记录点击次数： [GitHub - decaf-dev/obsidian-view-count: Add view count tracking to your Obsidian vault](https://github.com/decaf-dev/obsidian-view-count)


### 活动状态监控 / aw-watcher-obsidian

[aw-watcher-obsidian](https://github.com/LordGrimmauld/aw-watcher-obsidian) 是一个用于将 obsidian 中的活动发送到 [[../../时间记录|ActivityWatch]] 的插件

**特点：**

- 详细记录 obsidian 的文档编辑状况

**实践：**

直接安装启用即可，状态栏中会显示连接状态

有在使用 ActivityWatch 的用户可以安装此插件，大致效果如下：![[../_assets/img/Pasted image 20230319151045.png|../../../../../../900其他/920Image/csimg/c/s/i/m/g/Pasted image 20230319151045.png]]

### 插件更新管理 / obsidian-plugin-update-tracker

[obsidian-plugin-update-tracker](https://github.com/swar8080/obsidian-plugin-update-tracker) 是一个管理社区插件更新的插件，相比官方拥有更多实用功能

**特点：**

- 查看更新日志
- 忽略特定插件更新
- 禁止禁用插件更新

**实践：**

安装启用后，状态栏中会显示插件更新状态

对插件的更新情况掌握更全面（<font color="#00b050">大家都是好人</font>👍）

### 打字机模式 / obsidian-typewriter-mode

插件支持打字机样式

**特点：**

- 打字机模式，使光标保持在编辑器中间
- 禅模式，专注模式，调低非编辑行透明度

**实践：**

建议搭配 [[Obsidian插件推荐#自定义命令 / obsidian-commander|commander]] 使用，将两个命令添加到顶部标题栏

> [!note] 替代插件
> [obsidian-typewriter-mode](https://github.com/davisriedel/obsidian-typewriter-mode)
> - ~~此插件同样与表格存在冲突~~**已解决**
> - 支持记录光标位置

> [!info] 隐私
> [privacy-glasses](https://github.com/jillalberts/privacy-glasses) 插件可以对文档内容进行模糊，适用于不想外人偷窥到内容的场景。使用前请确认是否真的有这需求

> [!attention] 缺乏维护
> 由于[cm-typewriter-scroll-obsidian](https://github.com/deathau/cm-typewriter-scroll-obsidian) 长期无人维护，与后来官方出的表格样式冲突异常👉 [Conflict with Obsidian's new Table View](https://github.com/deathau/cm-typewriter-scroll-obsidian/issues/50)
> 
> 添加如下代码使其能够使用（但不完善）。推荐操作表格时把打字机模式关了，弄完再开
> ```css
> /* source: https://github.com/deathau/cm-typewriter-scroll-obsidian/issues/50 */
> table th .cm-content.cm-lineWrapping,
> table td .cm-content.cm-lineWrapping {
>   padding-top: 0px !important;
>   padding-bottom: 0px !important;
> }
> ```

### 标签增强 / tag-wrangler

[tag-wrangler](https://github.com/pjeby/tag-wrangler) 插件增强自带的 `标签列表` 核心插件

**特点：**

- 标签具有菜单
- 标签嵌套
- 允许重命名
- ……

**实践：**


### 字数统计增强 / better-word-count

[better-word-count](https://github.com/lukeleppan/better-word-count) 插件除了统计当前页面的总字数外，还能实现自带的 `字数统计` 核心插件所没有的所选文本字数统计功能

**特点：**

- 文档字数统计
- 所选文字字数统计
- 库字数统计
- 今日字数统计
- 数据存储

**实践：**

关闭自带的 `字数统计` 核心插件，开启统计数据，调整前后缀使用


### 查找快捷键 / obsidian-keyboard-analyzer

[obsidian-keyboard-analyzer](https://github.com/cogscides/obsidian-keyboard-analyzer) 插件提供了一个查看所有快捷键分布的视图

[obsidian-key-promoter](https://github.com/joethei/obsidian-key-promoter) 插件在鼠标操作按钮会弹出该操作的快捷键提示

**特点：**

- 查看快捷键组合

**实践：**

用于记忆/查找快捷键还是挺方便的。

> [!warning] 缺陷
> `obsidian-key-promoter` 的提示功能就如其文档所说的，很可能显示一大堆没用的，影响观感，所以还是不太建议使用此插件

### 多列 / obsidian-columns

[multi-column-markdown](https://github.com/ckRobinson/multi-column-markdown) 插件支持多列，包括与 Pandoc 兼容的语法

[obsidian-columns](https://github.com/tnichols217/obsidian-columns) 插件支持多列，包括标注语法、代码块语法

**特点：**

- 支持多列

**实践：**

在 Obsidian 中支持多列。由于语法是自定义的，所以如果直接导出到其他平台极大可能不支持

> [!attention] 注意
> `obsidian-columns` 已长时间未更新 

`obsidian-columns` 在结合 [[Obsidian插件推荐#数据查询 / obsidian-dataview|dataview]] 使用时，如果采用的是代码块语法，需要在其外面套一层 [[Obsidian插件推荐#标注块 / obsidian-admonition&标注|obsidian-admonition]] 的 Admonition 语法（不是 Callout），否则阅读模式不会显示，如下所示👇

``````ad-info
`````col

````col-md
```dataview去掉
table WITHOUT ID file.link AS "三天内创建的笔记"
from ""
where date(today) - file.ctime <=dur(3 days)
sort file.ctime desc
limit 5
```
````

````col-md
```dataview去掉
table WITHOUT ID file.link AS "最近编辑"
from !"模板" and !"kanban"
where !contains(file.name,"数据库")
sort file.mtime desc
limit 5
```
````

`````
``````

如果采用的是标注语法，则可以正常显示，不用添加额外的 Admonition。就是没代码块语法设置详细
> [!col]
> > [!col-md]
> > ```dataview去掉
> > table WITHOUT ID file.link AS "三天内创建的笔记"
> > from ""
> > where date(today) - file.ctime <=dur(3 days)
> > sort file.ctime desc
> > limit 5
> > ```
>
> > [!col-md]
> > ```dataview去掉
> > table WITHOUT ID file.link AS "最近编辑"
> > from !"模板" and !"kanban"
> > where !contains(file.name,"数据库")
> > sort file.mtime desc
> > limit 5
> > ```

> [!note] 语法差异的影响
> - ~~代码块语法的列数是“动态”的，如果宽度过窄会调整成一列，而标注语法则始终保持一致。~~两者对最窄宽度的阈值不一样，设置里可以改
> - 代码块语法比标注语法的设置更多，但标注语法不依赖 Admonition 插件

### Beta 插件 / obsidian42-brat

[obsidian42-brat](https://github.com/TfTHacker/obsidian42-brat) 用于部署测试版或未在社区插件库中上架的插件/主题

**特点：**

- 部署测试版或未上架插件/主题

**实践：**

安装并启用后，添加插件/主题的 Github 链接即可

### URI 增强 / obsidian-advanced-uri

[obsidian-advanced-uri](https://github.com/Vinzent03/obsidian-advanced-uri) 允许通过打开 URI 来控制 Obsidian 功能

**特点：**

- 链接增强

**实践：**

> [!error] 警告
> 类似 Onenote 的页面链接。除非你有强烈需求，否则不建议使用

安装并启用，修改配置中的 `UID filed`，比如改成 `abbrlink`。然后文件菜单，点击复制 `COPY Advanced URI` 即可

比如有两个库，这时就可以通过 URI 来实现*跨库访问*。当然，你也可以使用 Obsidian 自带的 `复制 Obsidian 链接` 来实现类似的功能

### 自动更新元数据时间 / obsidian-frontmatter-modified-date

[obsidian-frontmatter-modified-date](https://github.com/alangrainger/obsidian-frontmatter-modified-date) 插件实现当编辑文档时自动更新时间

**特点：**

- 自动更新元数据时间，包括：创建、更新
- 可排除文件/文件夹
- 更新范围可控，因为仅更新当前编辑的文件，不会对其余文件进行改动

**实践：**

字段适用各种博客系统：
- `date`：创建时间，在 [[../../../../../../900其他/910Template/1.QuickAdd通用模板|1.QuickAdd通用模板]]里，创建文件时直接添加
- `updated`：更新时间，修改文件后自动添加并更新
- 使用 Momentjs，格式为：`YYYY-MM-DDTHH:mm:ssZ`

> [!note]+ 搭配插件
> [[Obsidian插件推荐#文档时间提示 / obsidian-old-note-admonitor|obsidian-old-note-admonitor]]


> [!info]+ 类似插件
> - [GitHub - dsebastien/obsidian-update-time: Obsidian plugin that updates front matter to include creation and last update times](https://github.com/dsebastien/obsidian-update-time)
> - [GitHub - beaussan/update-time-on-edit-obsidian](https://github.com/beaussan/update-time-on-edit-obsidian)

## 候选插件

候选插件并未使用过，但可能在某方面有特长，存在使用的可能性，因此记录备用

### 清理

**介绍：**

清除库中未使用的图片、文件……

**相关链接：**

清除库中未使用的图片： [oz-clear-unused-images-obsidian](https://github.com/ozntel/oz-clear-unused-images-obsidian)

查找库中没有反向链接的孤立文件：[find-unlinked-files](https://github.com/Vinzent03/find-unlinked-files)


### 评论/注释

**介绍：**

创建内联 html 注释

**相关链接：**

创建内联 html 注释： [obsidian-reading-comments](https://github.com/BumbrT/obsidian-reading-comments)

改进自带的评论逻辑及样式： [GitHub - MrGVSV/obsidian-better-comment-toggle](https://github.com/MrGVSV/obsidian-better-comment-toggle)

### 光标位置

**介绍：**

记住光标位置，两个插件都还不太完善

**相关链接：**

[obsidian-remember-cursor-position](https://github.com/dy-sh/obsidian-remember-cursor-position)

[obsidian-remember-file-state](https://github.com/ludovicchabant/obsidian-remember-file-state)


### 文件夹注释

**介绍：**

用于给文件夹添加注释说明，其实就是创建一个与文件夹同名的文件，然后隐藏

**相关链接：**

以前用的 [obsidian-folder-note-plugin](https://github.com/xpgo/obsidian-folder-note-plugin)，但后来没更新了

后面发现类似的👉 [obsidian-folder-notes](https://github.com/LostPaul/obsidian-folder-notes)，~~但功能目前看来还不太完善~~ *已安装，还未深入使用*


### 关系图谱

**介绍：**

图形化展示库中文件关系

**相关链接：**

关系图谱相关插件：
- Obsidian 自带的核心插件
- [GitHub - HEmile/juggl: An interactive, stylable and expandable graph view for Obsidian. Juggl is designed as an advanced 'local' graph view, where you can juggle all your thoughts with ease.](https://github.com/HEmile/juggl)

下面这些都有点依赖 dataview 的内联字段
- [GitHub - zsviczian/excalibrain: A graph view to navigate your Obsidian vault](https://github.com/zsviczian/excalibrain)
- [GitHub - SkepticMystic/breadcrumbs: Add structured hierarchies to your Obsidian vault](https://github.com/SkepticMystic/breadcrumbs)


### 双链 / obsidian 42-strange-new-worlds&双链

[obsidian42-strange-new-worlds](https://github.com/TfTHacker/obsidian42-strange-new-worlds) 插件用于直接在文档中显示关联条数，查看链接、块引用和嵌入何时与 Vault 中的其他文件关联

**特点：**

- 文档中直观显示文档间的连接
- 双链

**实践：**

> [!attention] 缺陷
> ~~使用自带的 `导出PDF` 功能时会将关联条数也导出。使用时也要注意样式是否兼容调整过~~自带的 PDF 导出不存在此问题了，但 [[Obsidian插件推荐#文档导出 / obsidian-better-export-pdf&PDF|better-export-pdf]] 存在此问题🙃

### Abbrlink

**特点：**

- 为 Markdown 文件添加永久链接

**实践：**

- Quickadd 模板可以自动生成
- 插件生成： [obsidian-plugin-abbrlink](https://github.com/Hoshino-Yumetsuki/obsidian-plugin-abbrlink)

## 不推荐插件

> [!error] 警告
> **警惕插件陷阱**，需要明确需求，筛选过合适的软件后，才可考虑这部分插件

### 文件列表 / file-tree-alternative

[file-tree-alternative](https://github.com/ozntel/file-tree-alternative) 提供了不同于自带的 `文件列表` 功能，可以为文件夹和文件提供独立视图

**特点：**

- 新的文件夹及文件管理视图
- 聚焦文件夹，同时隐藏其他文件夹

**实践：**

~~首先要习惯这种新的视图~~多了一种新的视图，但打开逻辑还是差不太多

> [!attention] 缺乏维护
> 2025年3月19日，9 个月未维护


### Task / obsidian-tasks

[obsidian-tasks](https://github.com/obsidian-tasks-group/obsidian-tasks) 插件允许集中管理库中的 Tasks

**特点：**

- Task 管理
- 跟踪整个库的任务

**实践：**

需要仔细考虑 Obsidian 管理 Tasks 是否能满足自己的工作流，起到正面作用。否则不要使用

### 类 Notion 界面 / makemd

[makemd](https://github.com/Make-md/makemd) 插件界面做了**极大的调整**，包括新的斜杠命令。如果喜欢这个样式可以尝试使用

**特点：**



**实践：**


### PDF 注释 / obsidian-annotator

> [!tip] 官方路线图
> 根据 [Obsidian Roadmap - Obsidian](https://obsidian.md/roadmap/) 来看，PDF 注释功能已在计划中，目前处于等待上游支持的阶段
> 
> 2025 年 3 月 19 日仍是等待上游支持

[obsidian-annotator](https://github.com/elias-sundqvist/obsidian-annotator) 插件允许注释 PDF 和 EPUB 文件。该插件基于 [Hypothesis](https://web.hypothes.is/)，但经过修改，使注释存储在本地 Markdown 文件中，而不是存储在互联网上。

**特点：**

- MD 和 Annotation 模式切换
- 添加注释，支持 Markdown [格式](https://web.hypothes.is/help/formatting-annotations-with-markdown/)
- 支持 PDF、EPUB
- 本地存储，不上传至网络
- ……

**实践：**

```yaml
---
annotation-target: mypdf.pdf
---
```

最后在选项中选择 `Annotator` 即可

PDF 文字的识别利用的是 [[../../../../../630日常类/PDF处理#对PDF进行OCR优化|OCR处理]]，所以识别不一定准确，主要是中文 PDF，还存在上下偏移的情况

如果要使用外部文件，应该可以改成下面的地址：`file:///C:/TEST/书籍/mypdf.pdf`

> [!tip]
> 旧版本可以按照上述方法使用，新版本未验证

> [!todo] 类似插件
> 另一个貌似更好的插件👉 [GitHub - RyotaUshio/obsidian-pdf-plus: The most Obsidian-native PDF annotation & editing tool ever.](https://github.com/RyotaUshio/obsidian-pdf-plus)

> [!info] 相近插件
> [obsidian-better-pdf-plugin](https://github.com/MSzturc/obsidian-better-pdf-plugin) 插件可在 Markdown 中显示 PDF 页面

### 语言工具 / obsidian-languagetool-plugin

[obsidian-languagetool-plugin](https://github.com/Clemens-E/obsidian-languagetool-plugin)集成了[LanguageTool](https://languagetool.org/)以提供高级语法和拼写检查

**特点：**

- 高级语法和拼写检查

**实践：**


### 小说文本项目 / longform

[longform](https://github.com/kevboh/longform) 插件提供了一个组织编写小说/剧本/……的一个人性化操作界面

**特点：**

- 创建项目
- 创建场景
- 场景可嵌套
- 整合场景并输出
- 使用元数据组织文件

**实践：**

此插件通过元数据来管理项目及场景，适用于一切可组合在一起的文档，而不仅仅是小说

> [!warning] 不足
> - 当前插件并没有看到有模板选项
> - 缺失目录，不过好像可以通过合并时添加步骤来实现

### RSS 订阅 / obsidian-rss

[obsidian-rss](https://github.com/joethei/obsidian-rss) 插件支持在 Obsidian 中阅读 RSS 

**特点：**

- RSS 订阅
- 分类/收藏
- 同步
- 结合 Obsidian 操作

**实践：**

配置订阅地址，只建议配置可能会摘抄的订阅地址。

### 思维导图 / obsidian-markmind

[obsidian-markmind](https://github.com/MarkMindCkm/obsidian-markmind) 插件可以提供思维导图的功能

**特点：**

- 思维导图

**实践：**

闭源，基本模式免费，其他收费，暂不考虑

### 展示所有文件 / dashboard-navigator-for-obsidian

[dashboard-navigator-for-obsidian](https://github.com/drbap/dashboard-navigator-for-obsidian) 插件能够查看整个库不同文件类型的总数量并且能够搜索

**特点：**

- 不是目录形式的管理，而是全部扁平化

**实践：**

> [!NOTE] 类似插件
> - 仪表板：[Components，一个没有上架却是 T0 级的 Obsidian 插件\_哔哩哔哩\_bilibili](https://www.bilibili.com/video/BV1ufUoY6Exz)
> 	- [Vran 的 Obsidian 插件作品集 - 飞书云文档](https://wxycbt0cjk.feishu.cn/wiki/GczJwNXb1iNbookQkbscMXOhnO4)
>  -  [GitHub - decaf-dev/obsidian-vault-explorer: Explore your Obsidian vault in visual format](https://github.com/decaf-dev/obsidian-vault-explorer)

### 日历日记 / obsidian-calendar-plugin&obsidian-periodic-notes

> [!tldr]
> 养不成习惯，还是算了。工作上的则还是用专业软件吧

> [!warning] 缺乏维护
> 两款软件目前开发已处于停滞状态，如有其他需要可以选择其他社区插件

[obsidian-calendar-plugin](https://github.com/liamcain/obsidian-calendar-plugin) 插件用于创建一个日历视图，可搭配日记插件使用

[obsidian-periodic-notes](https://github.com/liamcain/obsidian-periodic-notes) 用于编写日记

**特点：**

- 日历日记
- 日历点击跳转/创建日记
- 日历中的点代表字数多少，可以在配置界面设置多少字数显示一个点

**实践：**

安装启用后，设置日记模板和新日记存放目录即可

[[../../../../../../900其他/910Template/912Plan/Daily Note Template|日记模板]]：
````markdown
---
tags: [日记]
banner: "[[random.jpg]]"
---
# Day Planner

📆  [[<% tp.date.now("YYYY-MM-DD", "P-1D") %>]]  –  [[<% tp.date.now("YYYY-MM-DD", "P+1D") %>]]

---


````

> [!important] 日程计划
> 最早就开始使用的 [obsidian-day-planner](https://github.com/ivan-lednev/obsidian-day-planner) 插件复活啦，日程规划这下更加直观

> [!warning] 关于日历计数问题
> 别纠结这个问题，此功能可以认为已缺失
> 
> 由于模板自带一定长度的文本，所以需要修改此插件 `main.js` 中的如下代码：` const numDots = wordCount / wordsPerDot; ` 修改为 ` const numDots = (wordCount-15) / wordsPerDot; `，根据自己的模板修改减去的数字： `15`
> 
> 另外，只要创建了日记，默认至少一个点，最多五个。

> [!tip] 完整日历
> 如果需要更完整的日历，可以在以下插件选个喜欢的：
> - [obsidian-fantasy-calendar](https://github.com/fantasycalendar/obsidian-fantasy-calendar)
> - [obsidian-full-calendar](https://github.com/davish/obsidian-full-calendar)

> [!info] 日历年表
> [obsidian-chronology](https://github.com/Canna71/obsidian-chronology) 插件提供了日历结合文档创建/编辑时间点的功能，同时在日期上直观的显示数量。日历比较简陋，除此之外可以认为比 `obsidian-calendar-plugin` 更实用。属实是让人纠结
> 
> 类似的插件还有[oz-calendar](https://github.com/ozntel/oz-calendar)

### 日记集成 Memos / Obsidian-Memos

[Obsidian-Memos](https://github.com/Quorafind/Obsidian-Memos) 插件在 Obsidian 中提供了类似 [memos](https://github.com/usememos/memos) 的全新界面来管理日记内容

> [!attention]
> 新版本更名为 Thino，且**闭源**。貌似数据也可能不再存储到日记文件中，前景不明，暂不考虑。而且真没这习惯

**特点：**

- memos 风格界面
- 统一管理日记

**实践：**


### 其他

**介绍：**



**相关链接：**

- 小部件： [GitHub - rafaelveiga/obsidian-widgets: Add cool widgets to your notes or your dashboard in Obsidian](https://github.com/rafaelveiga/obsidian-widgets)
- 时间及编辑时间：[GitHub - DynamicPlayerSector/timethings: Show clock, track time spent editing a note, and track the last time a note has been edited.](https://github.com/DynamicPlayerSector/timethings)
- 故事时钟，不明觉厉：[GitHub - jonzfisher/obsidian-chronostory: Obsidian plugin for creating a storyclock](https://github.com/jonzfisher/obsidian-chronostory)



## 不再使用/被替代/过时/缺乏维护

### 看板 / obsidian-kanban


> [!missing] 不再维护
> 被官方功能取代


> [!info] 官方路线
> 根据 [Obsidian Roadmap - Obsidian](https://obsidian.md/roadmap/) 来看，新核心插件 Base/数据库将在后续支持 Kanban 视图
> 


> [!attention] 考虑中
> Github 已将近一年没有 Commit。而且突然发现孤立于 Obsidian 的看板有必要存在吗？虽然是 all-in-one 了，但专业性、易用性、跨平台等等好像都不是太好。而且分散于整个 Obsidian 仓库，容易消失在时间的漫漫长河中。
> 
> 此插件的最大优势是能够直接利用 Obsidian 资源。外部工具则需要手动添加或者考虑结合其他插件（不过好像都半死不活，Obsidian 要寄了吗？）
>  
> 想了下应该在 Obsidian 中嵌入专业的看板工具，这个看板工具应该一统所有的看板。目前看好飞书多维表格、Trello

^6028ce

[obsidian-kanban](https://github.com/mgmeyers/obsidian-kanban) 插件提供创建看板的功能

**特点：**

- 看板

**实践：**

> [!error] 联动
> ~~后续需要关注能否与 [[Obsidian插件推荐#项目管理 / obsidian-projects|obsidian-projects]] 结合使用~~


### 文件夹数据库 / obsidian-db-folder

> [!missing] 不再维护
> 缺乏维护，并且我的场景下存在性能问题。此外官方已推出类似功能的核心插件

[obsidian-db-folder](https://github.com/RafaelGB/obsidian-db-folder) 插件提供了类似 Notion 的数据库

**特点：**

- 多种数据来源的数据库，如：文件夹、标签、链接、[[Obsidian插件推荐#数据索引查询 / obsidian-dataview|dataview]] 语句
- 基于文件元数据
- 可以创建*关联对象*，多表关联不是问题
- 行列自定义公式计算

**实践：**

详细用法见插件文档。会在选定的文件夹下创建一个单独的 [[../../../../../620计算机技术/625Markdown/Markdown|Markdown]] 管理文件

> [!error] 警告
> 此插件可能存在性能问题，加载稍慢。当时排查出是另一款插件问题，具体哪款忘了

> [!tip]
> 可结合以下插件使用：
> -  [[Obsidian插件推荐#项目管理 / obsidian-projects|obsidian-projects]] 
> - [[Obsidian插件推荐#数据查询 / obsidian-dataview|obsidian-dataview]]

### 项目管理 / obsidian-projects

> [!fail] 已过时
> 被官方功能取代

[obsidian-projects](https://github.com/marcusolsson/obsidian-projects) 插件允许可视化管理笔记，就是把一堆有相同特征的笔记组织起来，类似 Notion

**特点：**

- 默认有：表格、看板、日历、画廊视图（带图片的字段需要**开启富文本**）
- 可集成其他插件，比如增加 [[Obsidian插件推荐#文件夹数据库 / obsidian-db-folder|数据库视图]]
- 可根据文件夹、标签、[[Obsidian插件推荐#数据索引查询 / obsidian-dataview|dataview]] 语句创建项目

**实践：**

在一个界面中管理不同的项目，项目可根据 Inbox（目录）、 TODO （标签）、[[Obsidian插件推荐#数据查询 / obsidian-dataview|dataview]]、[[Obsidian插件推荐#文件夹数据库 / obsidian-db-folder|db-folder]] 来创建

详细用法见插件文档。无需创建额外文件，~~数据存哪儿的目前不明~~👉 [数据存储在插件配置 data.json 中](https://github.com/marcusolsson/obsidian-projects/discussions/377)

使用介绍： [Obsidian Projects: A Better Way to Manage Text-Based Projects in Obsidian | by Prakash Joshi Pax | Medium](https://beingpax.medium.com/obsidian-projects-a-better-way-to-manage-text-based-projects-in-obsidian-18c2a991069c)


> [!tldr] 效果展示
> ![[../../../../../../100兴趣爱好/110影视/111动漫/动漫鉴赏/御宅文化研究#动画管理]]


> [!faq] 问题
> ~~目前可以认为包含了 [[Obsidian插件推荐#文件夹数据库 / obsidian-db-folder|db-folder]] 的功能，后续看两者发展侧重~~
> 
> 目前来看，projects 的 table 界面更加原始，而 db-folder 则更接近 Notion 的使用体验，推荐使用后者的视图
> 
> - 但是创建的数据库名无法修改，只能通过修改 Projects 配置文件，指向重命名后的数据库，然后重启解决
> 
> - 2025 年 3 月 1 日，此插件打开后的页面不能固定，否则配合 Db-folder 使用时会弹出新标签页的奇怪 bug

### 元数据显示 / 文档属性

> [!fail] 已过时
> 被官方功能取代

> [!tip] 官方路线图
> 根据 [Obsidian Roadmap | Trello](https://trello.com/b/Psqfqp7I/obsidian-roadmap) 来看，~~官方正在进行元数据增强的工作~~
> 
> <span style="background:#affad1">已推出 Properties 功能</span>：New editor for file properties with support for internal links, stored in YAML

[obsidian-metatable](https://github.com/arnau/obsidian-metatable) 插件增强元数据的显示

**特点：**

- 元数据格式化为属性，而不是源码，更加美观
- 支持修改文档属性类型、文本

**实践：**

批量修改文档属性可以通过 [[Obsidian插件推荐#项目管理 / obsidian-projects|obsidian-projects]] 来筛选修改

> [!help] 其他插件
> 使用到元数据的插件还有 [metadatamenu](https://github.com/mdelobelle/metadatamenu)，此插件可以预设类型和值，比较复杂，一般人感觉不咋用得上，不推荐

> [!note] 自动更新文档修改时间
> 详见 [[Obsidian插件推荐#自动更新元数据时间 / obsidian-frontmatter-modified-date|frontmatter-modified-date]]
> - [GitHub - conorzhong/obsidian-auto-front-matter](https://github.com/conorzhong/obsidian-auto-front-matter)
> - [GitHub - muratagawa/update-time-updater: Obsidian plugin to update the 'update time' element when saving or manually.](https://github.com/muratagawa/update-time-updater)

### 类 Notion 数据库 / obsidian-dataloom

> [!missing] 不再维护
> 2025年3月12日：[DataLoom is no longer maintained](https://github.com/decaf-dev/obsidian-dataloom/issues/958)

[obsidian-dataloom](https://github.com/trey-wallis/obsidian-dataloom) 插件提供了类似 Notion 的数据库概念

**特点：**

- 表格是最漂亮的，外观最接近 Notion 的
- 支持从文件夹和元数据添加数据
- 可以*无缝*嵌入到 [[../../../../../620计算机技术/625Markdown/Markdown|Markdown]]，就是长宽固定了

**实践：**

个人觉得可以认为是超大号表格。比表格功能多，又比前面的数据库插件简单，但也因此不上不下

![[../../../../../../100兴趣爱好/160音乐/169工具/音乐软件对比.loom|音乐软件对比]]

### 脚注增强 / better-fn&obsidian-footnotes

> [!fail] 已过时
> 随着 [Obsidian 1.8.3](https://obsidian.md/changelog/2025-01-30-desktop-v1.8.3/) 发布更新，完善了脚注功能，这两款插件功能被完美替代

[better-fn](https://github.com/aidenlx/better-fn) 插件允许预览脚注，单击持久化，双击跳转

[obsidian-footnotes](https://github.com/MichaBrugger/obsidian-footnotes) 插件允许快速插入脚注

**特点：**

- 预览脚注
- 脚注跳转
- 快速插入脚注

**实践：**

安装并启用两个插件，其中 `obsidian-footnotes` 绑定 `alt+6` 快捷键，用于快速插入脚注

`better-fn` 长期未更新，使用 [PR中的实时预览代码](https://github.com/chu-shen/better-fn/releases/tag/1.1.1)编译后，现在实时阅览模式按住 `CTRL` 后再悬停即可预览


### 网页提取 / obsidian-extract-url

> [!fail] 已过时
> 推荐使用[[../Obsidian使用#剪贴|官方浏览器剪贴插件]]

[obsidian-extract-url](https://github.com/trashhalo/obsidian-extract-url) 插件可将 URL 提取为 Markdown 

**特点：**

- URL 提取为 Markdown

**实践：**

安装启用后，粘贴链接然后选择相应命令转换即可得到对应的 Markdown 文档

### 浏览网页 / Obsidian-Surfing

> [!fail] 已过时
> 官方自己出了个 `Web Viewer` 插件实现直接浏览网页的基础功能


[Obsidian-Surfing](https://github.com/PKM-er/Obsidian-Surfing) 插件允许在 Obsidian 中浏览网页

**特点：**

- 在 Obsidian 中浏览网页

**实践：**

可以搭配飞书文档等等外部管理工具使用。不过真的有必要吗，存疑

> [!tip]
> 2025 年 2 月 28 日，嘿，还真可以，飞书多维表格直接替代 Kanban 插件


