---
title: foobar2000歌单导入导出
aliases: 
author: chushen
tags:
  - 音乐
  - 歌单
  - foobar2000
  - 数据迁移
  - 网易云音乐
categories:
  - 教程
  - 音乐
description: foobar2000中歌单导入导出方法介绍。主要包含foobar2000的SQLite插件在导入导出中的应用
date: 2022-08-16 12:53
abbrlink: 20220816125305
share: true
updated: 2025-03-20T13:42:30+08:00
---

[TOC]

# foobar2000歌单导入导出



## 导入

### 一些方法

- 导入fpl/m3u/m3u8
- 使用[[../../../音乐管理软件foobar2000#播放记录|Last.fm]]插件导入[XSPF](https://www.xspf.org/)，元数据必须包括`title`和`creator`，格式参照下面：

	```xml
	<?xml version="1.0" encoding="UTF-8"?>
	<playlist version="1" xmlns="http://xspf.org/ns/0/">
		<trackList>
	          <track>
	              <location>https://music.163.com/song?id=544000653</location>
	              <title>Is This Love</title>
	              <album>THE IDOLM@STER MASTER SPECIAL 03</album>
	              <creator>我那覇響</creator>
	            </track>
		</trackList>
	</playlist>
	```


### m3u

#### 利用m3u路径匹配

> [!tldr]
> 此脚本<mark style="background: #FF5582A6;">效果不好</mark>，对音乐的规范性有要求，因为它是按照歌曲名及歌手来匹配音乐路径的，准确率低，不推荐使用

`m3u`在`foobar2000`中是绝对路径，可以扫描本地音乐然后导入👉[[./网易云歌单导入导出#lx-music|网易云歌单导入导出 > lx-music]]

然后可以使用此脚本匹配本地音乐，生成`m3u8`👉[GitHub - LuckyPuppy514/txt-to-m3u: 一个用于把洛雪音乐txt歌单转m3u歌单的 Powershell 脚本](https://github.com/LuckyPuppy514/txt-to-m3u)

### SQLite导入

#### 前言

本文的导入导出工具都存在各种各样的问题。~~为了提高准确度和效率~~，采用[[../../../音乐管理软件foobar2000#sqlite|音乐管理软件foobar2000 > sqlite]]编写SQL进行处理。

SQL编辑器👇：

![[../../_assets/img/Pasted image 20220810214137.png|../../../900其他/920Image/csimg/c/s/i/m/g/Pasted image 20220810214137.png]]

> [!danger] 注意事项
> 为了在创建播放列表后更新数据库，需要开启下面的选项（说明见`AdvancedOptions.html`）：
> ![[../../_assets/img/Pasted image 20220526145448.png|../../../900其他/920Image/csimg/c/s/i/m/g/Pasted image 20220526145448.png]]
> 
> **注意！！！**：此插件在使用时存在极大的闪退风险。因此在使用前请先退出foobar2000（自动保存更新数据，如：歌曲等级），然后重新打开使用。再确认导入的歌单大致符合要求后，重来一遍上述操作。

#### 准备歌曲

> [!tip]
> - 歌曲名中`'`需转义，改为`''`

首先将需[[./网易云歌单导入导出#导出到本地|导入的歌曲标题]]复制出来，标题之间以这三个符号(`','`)分隔，首尾添加`'`

#### 建表

首先创建虚拟表`Import_From_NetEase`和标题表：
```sql
CREATE VIRTUAL TABLE Import_From_NetEase USING MetaDB_Module(no_multivalue_split, playlist);

-- 其他可选操作👇
-- 创建包含标题名的表
CREATE TABLE NetEase_Titles(titleName);
-- 插入得到的标题
INSERT INTO NetEase_Titles VALUES ('Is This Love'),('遠い音楽');
	
-- 清空表（导入其他标题前执行）
DELETE FROM NetEase_Titles;
-- 删除表（完工退出时执行）
DROP TABLE NetEase_Titles;
```

#### 列表插入匹配歌曲

插入完全匹配歌曲。用[[foobar2000歌单导入导出#准备歌曲|foobar2000歌单导入导出 > 准备歌曲]]步骤的结果替换下面的`'菫','黒の剣巫'`：
```sql
INSERT INTO Import_From_NetEase (path,subsong, playlist_name)
SELECT a.path,a.subsong,
    '需要插入的播放列表，可自动创建'
FROM MediaLibrary a
WHERE title IN('菫','黒の剣巫');

-- 其他过滤条件，比特率大于320，专辑以THE IDOLM@STER开头
--bitrate>320 AND album LIKE 'THE IDOLM@STER%' AND
```

#### 其他操作

1. 插入`播放列表b`中不存在的`播放列表a`的歌曲到`待插入的列表`
	```sql
	INSERT INTO Import_From_NetEase (path,subsong, playlist_name)
	SELECT a.path,a.subsong,
	    '待插入的列表'
	FROM Playlist a
	WHERE playlist_name = '播放列表a'
	    AND a.title NOT IN(
	        SELECT b.title
	        FROM Playlist b
	        WHERE b.playlist_name = '播放列表b'
	    );
	```
2. 输出未匹配到的歌曲
	```sql
	SELECT a.titleName
	FROM NetEase_Titles a
	WHERE a.titleName NOT IN(
	        SELECT b.title
	        FROM Playlist b
	        WHERE b.playlist_name = '播放列表'
	    );
	```

## 导出

### 一些方法

- 保存为fpl（二进制）
- 保存为m3u（部分字符不支持），仅文件名
- 保存为m3u8，仅文件名
- 使用[[../../../音乐管理软件foobar2000#播放记录|Last.fm]]插件导出为[XSPF](https://www.xspf.org/)，包括：`title`、`creator`、`album`、`trackNum`、`duration`。编码方式貌似有问题，存在乱码问题
- 其他插件（未验证）：[GitHub - Chocobo1/foo_xspf_1: Import & export XSPF playlist in foobar2000](https://github.com/Chocobo1/foo_xspf_1)

### SQLite导出

执行SQL后，在结果上右键复制即可

```sql
SELECT distinct b.title
FROM Playlist b
WHERE b.playlist_name = '播放列表'
```

然后使用 [[../../../Excel操作#两列去除重复项|Excel两列去除重复项]]筛选未匹配歌曲啥的~~


