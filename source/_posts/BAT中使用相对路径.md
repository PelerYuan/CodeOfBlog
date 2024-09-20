---
layout: post
title: BAT中使用相对路径
author: Peler
date: 2024-09-21 01:38:59
tags:
    - Bat
    - Microshit
    - 中文
categories: PowerShell/CMD
---

使用 `%~dp0` 变量获取当前 Bat 文件的位置。

所以比如说访问上级文件夹，就是：

```
%~dp0\..\
```

真是 Microshit，这样写就是不让人看懂的是吧……