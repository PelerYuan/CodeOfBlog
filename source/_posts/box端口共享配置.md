---
layout: post
title: virtual box端口共享配置.md
author: Peler
date: 2024-09-17 19:11:42
tags:
    - virtual box
    - 中文
categories: Virtual machine
---

## 场景1：主机共享到虚拟机

网络模式选择 NAT, 在虚拟机中直接访问虚拟 IP 即可。

如：
在主机 127.0.0.1:8000 上运行的服务，虚拟机通过 10.0.2.2:8000 访问

## 场景2：虚拟机共享到主机

虚拟机上的服务都要跑到 0.0.0.0, 在网络设置界面选择 NAT, 然后 高级->端口转发，填写对应端口号即可（IP不用填）。

如：
虚拟机在 0.0.0.0:8000 开启服务，主机在127.0.0.1:8000 访问