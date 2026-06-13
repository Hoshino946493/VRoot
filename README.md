# VRoot

## English Version

### Introduction

VRoot is a lightweight PRoot container launcher designed specifically for Termux.

- Wraps all common mount parameters and environment variables, no need to manually write complex proot commands
- Supports multiple command container management, unified container directory, automatic DNS adaptation for older Android versions
- Bilingual Chinese/English support with color output

### Project Background

proot-distro v5.0 changed its RootFS source to DockerHub.

In China, that means "unusable".

I didn't want to watch people get driven crazy by proot's complex parameters.

So I wrote VRoot.

A proot wrapper script — typed on a smartwatch.

No parameters to remember. No config to tweak.

`vroot msrfs ~/ubuntu-fs` just works.

If proot-distro is "where the dream ends,"

then VRoot is the ladder I built myself.

### Features

- Built-in device directory mounting: dev, sys, proc, sdcard, storage, HOME
- Automatic container environment variable configuration: PATH, TERM, LANG, TMPDIR
- Automatic compatibility with Android versions below 8: auto-generates resolv.conf for network fixes
- Support manual path container startup
- Support quick login to containers in unified directory
- Support shortcut commands
- Fully backward compatible with legacy path startup methods
- Automatic creation of container storage directory
- Colored output for better user experience
- Bilingual Chinese/English support

### Installation

Run the following commands in Termux:

```bash
git clone https://github.com/Hoshino946493/VRoot.git
cd VRoot
chmod +x vroot
cp vroot $PREFIX/bin/
```

### Usage

VRoot provides three core commands:

| Command | Shortcut | Description |
|---------|----------|-------------|
| msrfs | - | Manually specify any RootFS directory to login, username optional (default: root) |
| login | l | Quick login to containers in ~/.vroot/containers |
| help | h | View help information |

### Additional Usage

- Direct path passing: vroot [path] [username], compatible with legacy calling method.

### Examples

```bash
vroot msrfs ~/ubuntu-fs sensei
vroot msrfs ~/debian-fs
vroot login ubuntu-fs
vroot l debian-fs root
vroot ~/alpine-fs
vroot help
vroot h
```

### Directory Structure

- Script automatically creates working directory: ~/.vroot/containers
- Containers managed via login should be placed in this directory
- Running vroot login alone will list all existing containers

### Language Switching

You will be prompted to select language on first run. To switch later:

# Switch to English
```bash
sed -i 's/vroot_lang=.*/vroot_lang=2/' ~/.vroot/lang.conf
```

# Switch to Chinese

```bash
sed -i 's/vroot_lang=.*/vroot_lang=1/' ~/.vroot/lang.conf
```

Or edit the ~/.vroot/lang.conf file directly.

## Special Thanks

**Philips** - Thanks for making this smartwatch, which somehow became my development platform.

You probably didn't expect someone to write code on it, but here we are.

License: MIT
Author: Hoshino946493

---

## 中文版

### 简介

VRoot 是一款专为 Termux 设计的轻量 PRoot 容器启动脚本。

- 封装了全套常用挂载参数与环境变量，无需手动编写复杂 proot 启动命令
- 支持多命令容器管理、统一容器目录、低版本 Android DNS 自动适配
- 中英双语支持，彩色输出

### 项目背景

proot-distro v5.0 把 RootFS 源换成了 DockerHub。
在国内，这等于“不能用”。

我不想看着别人被 proot 的复杂参数逼疯。
所以我写了 VRoot。

一个在手表上敲出来的 proot 封装脚本。
不用记参数，不用改配置。
vroot msrfs ~/ubuntu-fs 就能跑起来。

如果 proot-distro 是“梦结束的地方”，
那 VRoot 就是我自己重新搭的梯子。

### 功能特性

- 内置全套设备目录挂载：dev、sys、proc、sdcard、storage、HOME
- 自动配置容器环境变量：PATH、TERM、LANG、TMPDIR
- 自动兼容 Android 8 以下系统：自动生成 resolv.conf 修复网络
- 支持手动路径启动容器
- 支持统一目录快捷登录容器
- 支持简写命令
- 完全向下兼容传统路径启动方式
- 自动创建容器存放目录
- 彩色输出，提升用户体验
- 中英双语支持

### 安装方法

在 Termux 中执行以下命令：

```bash
git clone https://github.com/Hoshino946493/VRoot.git
cd VRoot
chmod +x vroot
cp vroot $PREFIX/bin/
```

### 使用方式

vroot 提供三种核心操作命令：

| 命令 | 简写 | 说明 |
|------|------|------|
| msrfs | - | 手动指定任意 RootFS 目录登录容器，用户名可选，默认为 root |
| login | l | 快速登录存放于 ~/.vroot/containers 的容器 |
| help | h | 查看帮助信息 |

### 额外用法

- 直接传入路径：vroot [路径] [用户名]，兼容旧版调用逻辑

### 使用示例

```bash
vroot msrfs ~/ubuntu-fs sensei
vroot msrfs ~/debian-fs
vroot login ubuntu-fs
vroot l debian-fs root
vroot ~/alpine-fs
vroot help
vroot h
```

### 目录说明

- 脚本自动创建工作目录：~/.vroot/containers
- 通过 login 管理的容器请放置在此目录
- 单独执行 vroot login 会列出当前已存在的容器

### 语言切换

首次运行时会提示选择语言。之后如需切换：

# 切换到英文

```bash
sed -i 's/vroot_lang=.*/vroot_lang=2/' ~/.vroot/lang.conf
```

# 切换到中文

```bash
sed -i 's/vroot_lang=.*/vroot_lang=1/' ~/.vroot/lang.conf
```

或直接编辑 ~/.vroot/lang.conf 文件。

## 鸣谢

**飞利浦** - 感谢你们生产了这块手表，让我能在手腕上完成这个项目。

虽然你们可能不知道有人拿手表写代码，但我确实这么干了。

许可证：MIT
作者：Hoshino946493
