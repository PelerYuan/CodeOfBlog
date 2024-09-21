---
layout: linux
title: 临时扩大swap大小
author: Peler
date: 2024-09-21 12:55:13
tags:
    - Linux system settings
    - 中文
categories: Linux
---

最近在跑虚拟机，内存压力有点大。临时创建 swap 分区可以分担压力。

## 创建 Swap 文件
创建一个大小为 2GB 的 Swap 文件：

```bash
sudo fallocate -l 2G /swapfile
```

如果 fallocate 不可用，可以使用以下命令：

```bash
sudo dd if=/dev/zero of=/swapfile bs=1M count=2048
```

## 设置 Swap 文件权限
```bash
sudo chmod 600 /swapfile
```

## 格式化 Swap 文件
```bash
sudo mkswap /swapfile
```

## 启用 Swap 文件
```bash
sudo swapon /swapfile
```

## 将 Swap 文件添加到 fstab
编辑 /etc/fstab 文件，添加如下行：

```bash
/swapfile none swap sw 0 0
```

## 验证 Swap 状态
```bash
swapon --show
```

## 调整 Swap 优先级（可选）
```bash
sudo swapon --priority 10 /swapfile
```