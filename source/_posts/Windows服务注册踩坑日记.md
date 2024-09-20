---
layout: post
title: Windows服务注册踩坑日记
author: Peler
date: 2024-09-19 22:09:49
tags:
    - Windows service
    - Microshit
    - 中文
categories: SysyncWin 开发踩坑日记
---
{% post_link Windows注册服务 '上一篇文章' %}提到先确保 EXE 文件可以被注册成服务，否则就会出现上个文章所描述的诡异情况。

搞懂了之后回想，Microshit 可以体现在以下几个方面：

1. 不支持的 EXE 被注册成服务不报错
2. 不支持的 EXE 注册成服务后启动报错为权限问题，而不是正确的提示
3. 不支持的 EXE 注册成服务之后无法修改，进行删除等操作
4. 不支持的 EXE 注册成服务之后还会出现各种玄幻而不可控的结果