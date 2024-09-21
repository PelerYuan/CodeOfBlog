---
layout: post
title: InnoSetup安装卸载时运行Bat
author: Peler
date: 2024-09-21 18:55:15
tags:
    - Installer
    - Inno Setup
    - Bat
    - 中文
categories: Windows programming
---

```Inno Setup
[Run]
Filename: "{app}\tools\install_service.bat"

[UninstallRun]
Filename: "{app}\tools\remove_service.bat"
```

第一个是在安装后运行脚本，第二个是在写在前运行。

如果脚本需要 admin 权限，则：

```Inno Setup
[Setup]
PrivilegesRequired=admin
```