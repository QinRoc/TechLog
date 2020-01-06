---
layout: draft
title: VisualStudioCode中PlantUML使用
date: 2019-04-01
updated:
thumbnail:
comments: true
tags: [VisualCode]
categories:
permalink: true
toc: true
---

## 1. 准备

### 1.1 插件

- [VisualStudioCode的插件介绍页](https://marketplace.visualstudio.com/items?itemName=jebbs.plantuml)
- [插件GitHub](https://github.com/qjebbs/vscode-plantuml)

### 1.2 graphviz环境

1. 下载[Windows环境graphviz包](https://graphviz.gitlab.io/_pages/Download/Download_windows.html)
2. 解压zip包/安装
3. 设置环境变量：Path中增加bin目录路径
4. 验证

`dot -v` 命令验证：

```cmd
dot - graphviz version 2.38.0 (20140413.2041)
libdir = "c:\Program\Document\graphviz-2.38\release\bin"
Activated plugin library: gvplugin_dot_layout.dll
Using layout: dot:dot_layout
Activated plugin library: gvplugin_core.dll
Using render: dot:core
Using device: dot:dot:core
The plugin configuration file:
        c:\Program\Document\graphviz-2.38\release\bin\config6
                was successfully loaded.
    render      :  cairo dot fig gd gdiplus map pic pov ps svg tk vml vrml xdot
    layout      :  circo dot fdp neato nop nop1 nop2 osage patchwork sfdp twopi
    textlayout  :  textlayout
    device      :  bmp canon cmap cmapx cmapx_np dot emf emfplus eps fig gd gd2 gif gv imap imap_np ismap jpe jpeg jpg metafile pdf pic plain plain-ext png pov ps ps2 svg svgz tif tiff tk vml vmlz vrml wbmp xdot xdot1.2 xdot1.4
    loadimage   :  (lib) bmp eps gd gd2 gif jpe jpeg jpg png ps svg
```

## 2.语法

[PlantUML Document](http://plantuml.com/zh/sitemap-language-specification)
[](http://plantuml.com/zh/)

## 3. 问题

1. No @startuml found

>`@startuml` 需要和 `@enduml配对`
