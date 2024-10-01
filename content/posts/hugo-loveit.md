+++
title = 'Hugo Loveit'
date = 2024-09-07T21:44:02+08:00
draft = false
tags = ["hugo", "theme", "loveit"]
categories = ["记录笔记"]
+++


## 安装 hugo

`scoop install hugo-extended`
<!--more-->
> hugo-extended 是扩展版 (建议),hugo 是标准版

### scoop 安装

[scoop 安装教程](https://gitee.com/scoop-installer/scoop)

```powershell
# 脚本执行策略更改, 在有管理员权限的powershell中执行
Set-ExecutionPolicy RemoteSigned -scope CurrentUser
# 输入Y或A，同意
Y

# 自定义安装目录（注意将目录修改为合适位置), 我的软件安装盘是E盘，GlobalScoopApps是scoop软件安装目录
irm scoop.201704.xyz -outfile 'install.ps1'

.\install.ps1 -ScoopDir 'E:\Scoop' -ScoopGlobalDir 'E:\GlobalScoopApps'
```

> 切换分支到 develop, 更新 scoop

```powershell
scoop config scoop_branch develop

scoop update
```

> scoop 安装、删除软件

```powershell
scoop install <软件名>

scoop uninstall <软件名>
```

[第三方软件库](https://gitee.com/scoop-installer)

## 创建站点

> 创建一个网站 my-blog

`hugo new site my-blog`

> git 初始化 my-blog

`git init my-blog`

## 导入主题

`git clone https://github.com/dillonzq/LoveIt.git themes/LoveIt`

## 创建一个新主题

> 创建一个主题

`hugo new theme my-theme`

> 第一次运行，在站点的 hugo.toml 里写入

`theme = "my-theme"`

> 运行

`hugo server`

> 按住 ctrl 单击`http://localhost:1313/`

## 创建文档

`hugo new posts/hello-world.md`

## 修改文章头

> 修改根目录下的`archetypers/default.md`, 之后创建的文章就能生效

## 使用 vscode 开发 hugo 主题

[hugo 主题开发插件](https://gohugo.io/tools/editors/)
