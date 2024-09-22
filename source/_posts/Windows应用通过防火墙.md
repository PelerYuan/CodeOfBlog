---
layout: post
title: Windows应用通过防火墙
author: Peler
date: 2024-09-22 23:44:42
tags:
    - Windows firewall
    - Microshit
    - 中文
categories: SysyncWin 开发踩坑日记
---

今天又是吐槽 Windows 的一天……

```bat
cd "%~dp0"

:: 设置程序路径
set "ProgramPath=%~dp0..\SysyncWinClient.exe"

:: 删除现有规则（如果存在相同的规则名）
netsh advfirewall firewall delete rule name="AllowYourAppInbound"
netsh advfirewall firewall delete rule name="AllowYourAppOutbound"

:: 为程序添加防火墙入站规则（允许所有端口和协议）
netsh advfirewall firewall add rule name="AllowYourAppInbound" dir=in action=allow program="%ProgramPath%" enable=yes profile=domain,private,public

:: 为程序添加防火墙出站规则（允许所有端口和协议）
netsh advfirewall firewall add rule name="AllowYourAppOutbound" dir=out action=allow program="%ProgramPath%" enable=yes profile=domain,private,public

:: 提示成功

echo firewall setting success

pause
```

这是让指定程序通过 firewall 的脚本。

但是我一开始没有正常运行。

为什么？

因为我把
```bat
set "ProgramPath=%~dp0..\SysyncWinClient.exe"
```
写成了
```bat
set "ProgramPath=%~dp0\..\SysyncWinClient.exe"
```

由于 `%~dp0` 已经在末尾有一个 `\`，所以最终结果就变成：`C:\xxx\\..\SysyncWinClient.exe`。

之前我写脚本的时候注意到了，但是可以完美运行：
```bat
cd "%~dp0"
.\nssm install SysyncWin "%~dp0\..\SysyncWinClient.exe"
.\nssm start SysyncWin
.\allow_firewall.bat
pause
```
所以我就没太在意这里，Microshit 输出的信息也是 `OK`，我就以为这个路径没问题。

可就是运行不了。

于是我又额外开了端口，等等等等……

最后一想，换了一个无效路径，发现还是输出 `OK`，没报错。

我就知道是 Microshit 发力了。

然后，抱着试一试的态度，改了以下路径：

**成了？！？**

### Micro really shit