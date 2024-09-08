+++
title = 'wsl2 安装配置'
date = 2024-09-06T21:48:59+08:00
draft = false
tags = ["wsl2", "配置", "笔记"]
categories = ["记录笔记"]
+++

## 安装 WSL2

- 启用适用于 Linux 的 Windows 子系统
<!-- more -->
`dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart`

- 启用虚拟化

`dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart`

- 启动 Hyper-V

Windows+R 键，调出运行，键入 control，进入控制面板，进入程序，打开启动或关闭 Windows 功能，勾选 Hyper-V，重启

[下载并安装 X64 的 WSL2 linux 内核升级包](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi "把链接拷贝到浏览器上")

设置 WSL 默认版本

`wsl --set-default-version 2`

## 安装 linux

打开 Store 商店，输入 Arch，下载

下载完了，打开，输入用户名，密码

## 配置 Arch

### 换源

切换 Arch linux、Arch linux CN 源

[中科大软件源](https://mirrors.ustc.edu.cn/help/)

```bash
sudo pacman -Syyuu
sudo pacman-key --lsign-key "farseerfc@archlinux.org"
sudo pacman -S archlinuxcn-keyring
sudo pacman -S yay
sudo passwd root # 修改root密码
```

下载 nvim、zsh & ohmyzsh、yay

```bash
cat /etc/shells # 查看zsh是否安装
sudo pacman -S zsh
git clone --depth=1 git@github.com:ryanoasis/nerd-fonts.git
cd nerd-fonts
./install.sh
```

### zsh & ohmyzsh

ohmyzsh 安装：

- 把 oh-my-zsh 项目 Clone 下来：

```bash
git clone https://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh
```

- 复制 .zshrc

```bash
cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
```

- 更改你的默认 Shell

```bash
chsh -s /bin/zsh
```

zsh 插件：

- powerlevel10k(主题)

    `git clone --depth=1 https://gitee.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k`

    把.zshrc 打开，找到 ZSH_THEME，把值改为"powerlevel10k/powerlevel10k"

- auto-suggestion(自动补全)

    `git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions`

    把.zshrc 打开，找到 plugins=(git)，在 git 后面添加 zsh-autosuggestions

- syntax highlighting(语法高亮)

    `git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting`

    把.zshrc 打开，找到 plugins=(git)，在 git 后面添加 zsh-syntax-highlighting

最后`source ~/.zshrc`

### nvim

```bash
sudo pacman -S neovim
git clone git@github.com:ayamir/nvimdots.git
cd nvimdots/scripts
./install.sh
# 如果始终无法安装成功，则执行下条命令
rm -fr ~/.local/share/nvim/site/lazy
```

### nano 编辑器

Ctrl+O 保存，按回车保存当前文件

Ctrl+X 退出

## 迁移 WSL2

```powershell
 wsl --shutdown #关闭所有正在运行的实例
 wsl -l -v #查看STATE是否为Stopped
 wsl --export Ubuntu  D:\Ubuntu_WSL2\Ubuntu.tar #导出Ubuntu到D盘的Ubuntu_WSL2目录并创建一个Ubuntu.tar的归档文件
 wsl --unregister Ubuntu #注销Ubuntu
 wsl --import Ubuntu D:\Ubuntu_WSL2 D:\Ubuntu_WSL2\Ubuntu.tar #把Ubuntu.tar重新注册为linux发行版
 Ubuntu config --default-user chpw #新建一个叫chpw用户
```
