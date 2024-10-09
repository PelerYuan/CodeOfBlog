---
layout: post
title: Git报错修复
author: Peler
date: 2024-10-09 23:18:46
tags:
    - 中文
categories: Git/GitHub
---

今天写程序写到一半电脑突然崩了，打开后出现以下报错：

```bash
$ git status
...
error: object file .git/objects/49/94e3dfafebc1125a6f397f9c08886074ed755f is empty error: object file .git/objects/29/00a127b31bdbd7873e7947c436bea1ff3c3b34 is empty error: object file .git/objects/2d/f7e40a27fa2ea19d4b63f453ceac9a034f5789 is empty error: object file .git/objects/c3/5120fed1d1524893cf56e5a924c62b3fedf9ee is empty error: object file .git/objects/1c/31ebbb0a773718c964581bd8f181551fac8bd2 is empty error: object file .git/objects/1c/31ebbb0a773718c964581bd8f181551fac8bd2 is empty error: object file .git/objects/1c/31ebbb0a773718c964581bd8f181551fac8bd2 is empty fatal: bad object HEAD
```

解决方案如下：

```bash
find .git/objects/ -type f -empty | xargs rm
git fetch -p
git fsck --full
```