---
layout: post
title: Windows注册服务
author: Peler
date: 2024-09-18 23:16:05
tags:
    - Windows service
    - 中文
categories: Powershell/CMD
---

## 没事别用 Powershell 和 CMD

能用 Powershell 别用 CMD, 能不用 Powershell 就千万别用。

今天尝试用 Powershell 注册服务，崩溃了。

要运行服务没权限（管理员也没用），要删除显示成功，实际上服务管理器里刷新之后还有。

结果重启服务管理器之后就好了……

之后又注册服务，显示已经有服务了。查询又没有……

……

***能用 Powershell 别用 CMD, 能不用 Powershell 就千万别用。***

***能用 Powershell 别用 CMD, 能不用 Powershell 就千万别用。***

***能用 Powershell 别用 CMD, 能不用 Powershell 就千万别用。***

## 关于注册服务

有一点很重要：确保你的 EXE 程序可以被注册为服务！！！

否则，使用 NSSM（也许过一天写一个博客）。