# VRoot

## Termux PRoot 容器封装 Bash 脚本

### 简介

VRoot 是一款专为 Termux 设计的轻量 PRoot 容器启动脚本。
- 封装了全套常用挂载参数与环境变量，无需手动编写复杂 proot 启动命令。
- 支持多命令容器管理、统一容器目录、低版本 Android DNS 自动适配，兼容新旧使用方式。

### 功能特性

- 内置全套设备目录挂载：包括 dev、sys、proc、sdcard、storage、HOME
- 自动配置容器环境变量：PATH、TERM、LANG、TMPDIR
- 自动兼容 Android 8 以下系统：自动生成 resolv.conf 修复网络
- 支持手动路径启动容器
- 支持统一目录快捷登录容器
- 支持简写命令
- 完全向下兼容传统路径启动方式
- 自动创建容器存放目录

### 安装方法

在 Termux 中执行以下命令：

```bash
git clone https://github.com/你的用户名/VRoot.git
cd VRoot
chmod +x vroot
cp vroot $PREFIX/bin/
```

### 使用方式

vroot 提供三种核心操作命令：
命令   简写   说明
msrfs  [用户名]   -   手动指定任意 RootFS 目录登录容器，用户名可选，默认为 root
login  [用户名]   l   快速登录存放于 ~/.vroot/containers 的容器
help   h   查看帮助信息

### 额外用法
- 直接传入目录路径：vroot  [用户名]，兼容旧版调用逻辑。

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
- 通过 login 管理的容器请放置在此目录。
- 单独执行 vroot login 会列出当前已存在的容器。
