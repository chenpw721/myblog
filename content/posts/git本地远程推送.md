+++
title = 'git 本地远程推送'
date = 2024-09-06T21:48:59+08:00
draft = false
tags = ["git"]
categories = ["记录笔记"]
+++

## GitHub 本地配置

### 配置本地 Git 全局设置
<!--more-->
`git config --global user.name "your_github_username"`
`git config --global user.email "your_github_email@outlook.com"`

### 创建一个 GitHub 本地仓库

```bash
cd e:\NoteBook                  # 新建一个文件夹, 使用cd进入
git init                        # 仓库初始化
git add *                       # 把本地仓库中的内容全添加
git commit -m "first commit"    # 提交内容, "first commit"是描述, 不会写就随便填
git branch -M main              # 
git remote add origin git@github.com:RestorerOfTheWorld/NoteBook.git
git push -u origin main         # 把本地仓库推送到GitHub仓库上
```

> 新建后，以后可以用下面的命令把日常更新的内容推送到 GitHub 仓库中去

```bash
git add . 
git commit -m "commit"
git push
```

### 更新同步本地/远程 URL

> 如果更新了 GitHub 用户名可以使用下面的命令把本地 Git 的用户名同步成 GitHub 上的

```bash
git remote -v
git remote set-url origin new_url
git pull origin main
```

## Git 下载

Windows 下载：`winget install Git.Git`

## Linux 下载

- Debian/Ubuntu：`sudo apt install git`

- CentOS/Fedora：`sudo yum install git 或 sudo dnf install git`

- Arch/Manjaro：`sudo pacman -S git`

- MacOS 下载：`brew install git`
