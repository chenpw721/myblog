+++
title = 'ssh 使用教程'
date = 2024-09-06T21:48:59+08:00
draft = false
tags = ["ssh", "操作方法"]
categories = ["记录笔记"]
+++

## SSH 密码登录

`ssh root@172.16.124.24 #用户名@主机名`
<!--more-->
## SSH 免密登录

`ssh-keygen -t rsa # 生成密钥`
`scp C:\Users\Admin\.ssh\id_rsa.pub root@172.16.124.24:/root/.ssh/id_rsa.pub.windows # 把密钥文件拷贝到linux服务器上的.ssh文件下并改名`
> 接下来进入 linux 服务器把密钥文件的内容复制到 anthorized_keys 文件里

```bash
ssh root@172.16.124.24 
cd ~/.ssh
cat id_rsa.pub.windows >> authorized_keys
接下来登录linux服务器就不需要输入密码了

ssh root@172.16.124.24
```

## github SSH 下载 密钥生成

```bash
#linux没有的话下载openssh
ssh-keygen -t ed25519 -C "your_name@email.com"
cat ~/.ssh/id_ed25519.pub
```

> 请在 git bash 或 powershell 中操作
>
> 登录 github，点击头像，点击设置，找到 SSH and GPG keys 选项，点击 SSH keys 右边的 New SSH key 按钮，标题给个恰当的密钥名字，把 cat ~/.ssh/id_ed25519.pub 的输出全部复制进 Key 里面，单击 Add SSH key，接着输入你的 github 登录密码
>
> `ssh -T git@github.com #在终端中输入`
>
> 末尾出现下面的代表成功
>
> Hi your_name! You've successfully authenticated, but GitHub does not provide shell access.
>
> 可以使用 ssh 下载方式了
>
> `git clone --depth=1 git@github.com:ryanoasis/nerd-fonts.git`
>
> --depth=1: 只下载最近一次的提交版本，可以避免把所有的历史提交记录下载下来
