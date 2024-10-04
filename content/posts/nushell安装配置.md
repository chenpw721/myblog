+++
title = 'Nushell安装配置'
date = 2024-10-03T19:43:23+08:00
draft = false
tags = ["windows", "terminal"]
categories = ["记录笔记"]
+++

> windows11使用wezterm+nushell+starship
> 
> 安装字体[JetBrains Mono](https://download.jetbrains.com/fonts/JetBrainsMono-2.304.zip)

## wezterm

[wezterm windows下载地址](https://github.com/wez/wezterm/releases/download/20240203-110809-5046fc22/WezTerm-20240203-110809-5046fc22-setup.exe)

[wezterm配置](https://github.com/KevinSilvester/wezterm-config.git)

## nushell

[nushell windows下载地址](https://github.com/nushell/nushell/releases/download/0.98.0/nu-0.98.0-x86_64-pc-windows-msvc.msi)

使用nu切换盘符: `cd 盘符:/`

## starship

[starship windows下载地址](https://github.com/starship/starship/releases/download/v1.20.1/starship-i686-pc-windows-msvc.msi)

在nushell里使用starship：
```bash
mkdir ~/.cache/starship
starship init nu | save -f ~/.cache/starship/init.nu
```
在[starship themes](https://starship.rs/zh-CN/presets/)查看主题

这里使用[pastel-powerline](https://starship.rs/zh-CN/presets/pastel-powerline)主题输入下行代码即可:

`starship preset pastel-powerline -o ~/.config/starship.toml`

添加以下语句后重开一个终端就能出现效果了(使用`echo $nu.env-path`查看文件路径)

```bash
# 启动starship
use ~/.cache/starship/init.nu

# 定义别名和目录常量
alias vim = nvim
```

## wezterm快捷键

[wezterm使用配置](https://github.com/KevinSilvester/wezterm-config.git)

> super -> alt
> 
> super_rev -> ctrl+alt

### 窗格

`super+\`: 垂直分割当前窗格
`super_rev+\`: 水平分割当前窗格
`super+w`: 关闭当前窗格
`super_rev+h/j/k/l`: 光标在左/下/上/右移动
`super_rev+p`: 与选定窗格交换
`super+Enter`: 切换光标所在窗格的缩放状态

### 标签页

`super+[`: 向左查看标签页
`super_rev+[`: 向左移动标签页
`super+]`: 向右查看标签页
`super_rev+]`: 向右移动标签页

`super+T`: 新建一个标签页
`super_rev+T`: 新建一个`wsl:ubuntu`标签页

`super+W`: 关闭一个标签页
`super_rev+W`: 关闭一个标签页

### 光标在命令行中移动

`super+->`: 移动至行尾
`super+<-`: 移动至行首
`super+backspace`: 清除整行

### 窗口

`super+n`: 新建一个窗口

### 重命名

`super+0`: 重命名当前标签页
`super_rev+0`: 撤销重命名

### 背景图片

`super+/`: 随机选择背景图片
`super+,`: 下一张图片
`super+.`: 上一张图片
`super_rev+/`: 列表选择图片
`super+b`: 切换有/无背景图片模式

