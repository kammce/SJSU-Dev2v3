# SJSU-Dev2

[![Discord](https://img.shields.io/discord/800515757871726622?color=7389D8&logo=discord&logoColor=ffffff&labelColor=6A7EC2)](https://discord.gg/tSmCgeyM)

Cross MCU firmware framework written by students, alumni, and faculty of
San Jose State University. Designed for the original purpose of helping students
develop firmware for the SJTwo board.

## [📖 Full Documentation & Guides BROKEN](http://sjsu-dev2v3.readthedocs.io/en/latest/?badge=latest)

## 💻 Operating System Supported

- Linux (Intel & ARM)
- Mac OSX
- Windows

## ✅ Prerequisite

- [Python 3.9+](https://www.python.org/downloads/)
- [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

## 🚀 Quick Start

To download and setup the environment, simply copy and paste this into a
terminal:

```bash
python3 -m pip install sammy-sjsu-dev2 nxpprog pyocd
```

If you find that git is not installed on your machine follow these steps to
**[install GIT](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)**.

If python 🐍 isn't installed you can find the installer here:
**[install Python](https://www.python.org/downloads/)**.

## 🆕 Creating a new Project

To create an SJSU-Dev2v3 project simply run the following command:

```bash
python3 -m sammy start new_project
cd new_project
```

Here you should find the following directories:

- `packages`: contains library and tools
- `library`: symlinks to all of the library source
- `.sj2` hidden project directory

## 🛠️ Building an Application

To build a project simply use the `sammy build` command which will build a
main.cpp file if it exists in the directory.

```bash
python3 -m sammy build
```

You can also specify a path to a specific source file you want to build.

```bash
python3 -m sammy build main.cpp
python3 -m sammy build blinker.cpp
python3 -m sammy build demos/i2c_scan.cpp
```

## 📥 Programming a Device

From within a project, run:

[update this later!]

### For LPC devices

```bash
# Linux
python3 -m nxpprog --device /dev/ttyUSB0 build/lpc40xx/lpc40xx.main.cpp.bin

# OSX
python3 -m nxpprog --device /dev/tty.SLABtoSerial build/lpc40xx/lpc40xx.main.cpp.bin

# Windows
python3 -m nxpprog --device COM3
```

## 🔎 Debugging Device [NOT CURRENTLY WORKING]

If you are using a JTAG or SWD device with your MCU, you can debug the device
with a similiar command to programming:

```bash
python3 -m pyocd gdbserver --target lpc4088

# On a new terminal window
python3 -m sammy gdb --platform lcp40xx main.cpp
```
