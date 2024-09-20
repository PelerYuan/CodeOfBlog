---
layout: post
title: 使用NSSM创建Windows服务
author: Peler
date: 2024-09-21 01:25:46
tags:
    - Windows service
    - NSSM
    - 中文
categories: Windows configration
---

## 创建服务
使用以下命令创建服务：

```
nssm install 服务名称
```

运行上述命令后，会弹出一个图形界面，要求你配置服务的详细信息。

如果不想要图形界面，直接制定 EXE 文件，则可以：

```
nssm install 服务名称 "可执行文件的完整路径"
```


## 启动服务
配置完成后，可以使用以下命令启动服务：

```
nssm start 服务名称
```

## 停止和删除服务

```
nssm stop 服务名称
```

如果选择 remove 后面加上 confirm，可以直接删除而不需要 GUI 界面确认。

## 查看服务状态

```
sc query 服务名称
```

## 总结
NSSM 非常方便，因为它能够将普通的应用程序注册为服务，并在应用程序崩溃时自动重启。