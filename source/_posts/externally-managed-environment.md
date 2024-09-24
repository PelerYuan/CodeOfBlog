---
layout: post
title: sudo apt install python3-pyside6
author: Peler
date: 2024-09-24 20:37:50
tags:
    - pip
    - pyqt/pyside
    - English
categories: Python
---

Today, apt running `sudo apt install pyqt5-dev-tools`, I wanted to install `PyQt5`:

```bash
pip install pyqt5
```

The error occured:

```
error: externally-managed-environment

× This environment is externally managed
╰─> To install Python packages system-wide, try apt install
    python3-xyz, where xyz is the package you are trying to
    install.
    
    If you wish to install a non-Debian-packaged Python package,
    create a virtual environment using python3 -m venv path/to/venv.
    Then use path/to/venv/bin/python and path/to/venv/bin/pip. Make
    sure you have python3-full installed.
    
    If you wish to install a non-Debian packaged Python application,
    it may be easiest to use pipx install xyz, which will manage a
    virtual environment for you. Make sure you have pipx installed.
    
    See /usr/share/doc/python3.12/README.venv for more information.

note: If you believe this is a mistake, please contact your Python installation or OS distribution provider. You can override this, at the risk of breaking your Python installation or OS, by passing --break-system-packages.
hint: See PEP 668 for the detailed specification.
```

I tried to reinstall python and pip, but that didn't work.

Then, by asking ChatGPT, here's the solution:

1. Using --break-system-packages
The reason why this error occured is that pip thinks your packages are controlled by the system. So use this command can help cancel this setting:

```bash
pip install pyqt5 --break-system-packages
```

2. Installing System-Wide Packages with apt
Simply using apt is fine:

```bash
sudo apt install python3-pyqt5
```
