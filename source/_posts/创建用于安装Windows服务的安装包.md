---
layout: post
title: 创建用于安装Windows服务的安装包要踩的坑.md
author: Peler
date: 2024-09-21 01:01:31
tags:
    - Windows service
    - Microshit
    - Installer
    - 中文
categories: SysyncWin 开发踩坑日记
---

## 创建安装包使用的软件

Inno Setup（图形界面引导，非常好用）

## 坑

1. 即使服务有很高的权限，也不能把安装目录放到默认的 `C:\Program Files` 或 `C:\Program Files(x86)` 里，偶发性出现 log 文件读取不了（权限不足）的情况。推荐放到 `C:\XXX`
2. 即使服务有很高的权限，并且从一定角度理注册服务之后服务程序和原先的 EXE 程序关系不大，但实际情况并非如此。今天尝试运行服务后不成功，打开原 EXE 程序后提示防火墙选项，选择允许之后服务正常。