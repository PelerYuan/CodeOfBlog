---
layout: post
title: WSL2.1.5.0, ubuntu22.04 proxy configration
author: Peler
date: 2024-04-04 08:40:38
tags: 
    - WSL 
    - proxy
    - English
categories: Windows configration
---

## WSL2.1.5.0 ubuntu22.04 proxy configration

I have updated WSL to the latest version, and I found all the method on the Internet was complex and not avaliable any more.

After trying for lots of methods, I suddenly heard someone said `put it simple`.

And...

It's really simple! INDEED!

The new version have an excellent adaptation of proxy.

### Solution
1. create .wslconfig in `C:\Users\YOUR_USERNAME` if you can't find it

2. open it and write the code below:
```wslconfig
[wsl2]
networkingMode=mirrored
```

3. open a powershell(better with administration) and restart the WSL by the command below:
```powershell
wsl --shutdown
```

4. then run WSL just by the command:
```cmd
wsl
```

5. if you are in China MainLand, check it with google(make sure you have turned on the proxy on Windows), input the command below in WSL:
```bash
wget www.google.com
```
if you get something like this:
```bash
peler@peler:/mnt/c/Users/peler$ wget www.google.com
--2024-04-04 08:54:08--  http://www.google.com/
Connecting to 127.0.0.1:7890... connected.
Proxy request sent, awaiting response... 200 OK
Length: unspecified [text/html]
Saving to: ‘index.html.6’

index.html.6                      [ <=>                                              ]  19.48K  --.-KB/s    in 0.06s

2024-04-04 08:54:08 (342 KB/s) - ‘index.html.6’ saved [19947]
```

then congratulations!