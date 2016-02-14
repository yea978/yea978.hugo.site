+++
date = "2016-02-14T00:00:00+08:00"
title = "HUGO主题结构，页面与模板对应关系"
description = ""
tags = ["HUGO"]
categories = ["Programing Language"]
keywords = []
+++

简单修改了一下Slender这个Hugo主题，主要添加了分类的页面，在此记录一下相关模板及最后生成页面的对应关系：

涉及模板：

* 首页模板
* 单一内容模板
* 内容列表模板
* 分类模板

原始主题：[Slender](http://crimsonray.github.io/slender/)

参考主题：[spf13](https://github.com/spf13/spf13.com)

<!--more-->
生成静态页面之后，网站的结构如下：

>
```
C:.
├─1
├─about                                       单一内容页
├─page
├─post                                        内容列表页
│  └─programl
│      └─hugo_theme_structure                单一内容页
├─static
│  ├─assets
│  ├─css
│  ├─fonts
│  └─js
├─tags                                        分类：tag
│  └─hugo                                    Taxonomy列表：tag页
├─topics                                      分类：topic
│  └─programing-language	                Taxonomy列表：topic页
└─index.html                                  首页
```

layout目录结构：

>
```
C:.
├─partials
├─taxonomy
│  ├─category.html                             Taxonomy列表模板
│  └─tag.html                                  Taxonomy列表模板
├─_default
│  ├─section.html                              Section列表模板
│  ├─single.html                               单一内容模板
│  └─terms.html                                分类模板
└─index.html                                    首页模板
```

首页模板:
---  
按照以下顺序，首先检查源目录，再检查主题目录，获取模板生成页面：

* /layouts/index.html
* /layouts/_default/list.html
* /layouts/_default/single.html


单一内容模板：
---
Hugo中内容的最主要视图就是单一视图，每一个Markdown文件都会通过单一的模板来渲染。

按照以下顺序，首先检查源目录，再检查主题目录，获取模板生成页面：

* /layouts/**TYPE**-or-**SECTION**/LAYOUT.html
* /layouts/**TYPE**-or-**SECTION**/single.html
* /layouts/_default/single.html

内容列表模板：
---
**Section列表**  如上面的post

按照以下顺序，首先检查源目录，再检查主题目录，获取模板生成页面：

* /layouts/section/**SECTION**.html
* /layouts/_default/section.html
* /layouts/_default/list.html

**Taxonomy列表** 如上面的hugo

按照以下顺序，首先检查源目录，再检查主题目录，获取模板生成页面：

* /layouts/taxonomy/**SINGULAR**.html
* /layouts/_default/taxonomy.html
* /layouts/_default/list.html

分类模板：
---
按照以下顺序，首先检查源目录，再检查主题目录，获取模板生成页面：

* /layouts/taxonomy/**SINGULAR**.terms.html
* /layouts/_default/terms.html