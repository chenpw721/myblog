+++
title = 'Pwsh 安装配置'
date = 2024-10-01T15:52:06+08:00
draft = false
+++

## pwsh 的安装

pwsh 的安装：
```powershell
# 显示当前powershell版本号
$PSVersionTable.PSVersion

# 显示当前最新的可用的版本 正常版和预览版
winget search Microsoft.PowerShell

# 使用 Winget 安装 PowerShell
winget install --id Microsoft.Powershell --source winget
```

## 使用 pwsh(Powershell7)
win+R 键，打开运行，输入 pwsh，即可

## pwsh 配置

添加自动补全 (无需 Tab 键):
```powershell
# 已输入过的命令：
Set-PSReadLineOption -PredictionSource History

# 没有输入过的命令：
Set-PSReadLineOption -ShowToolTips

# 在pwsh的属性、快捷方式、目标，用下行代码替代，可永久使用智能提示
"C:\Program Files\PowerShell\7\pwsh.exe" -noe -c "&{  Set-PSReadLineOption -PredictionSource History -ShowToolTips}" -WorkingDirectory ~
```

设置快捷键：
: 点击终端标题栏的下三角键
: 点击**设置**，找到**操作**
: 找到**新建标签页**，修改快捷键为*Ctrl+Alt+T*，**保存**即可

> `Get-PSReadlineOption`可以查看历史命令的保存路径

### 安装、使用 oh-my-posh

```powershell
# 安装oh-my-posh
winget install oh-my-posh

# 添加ohmyposh到启动文件中
notepad $PROFILE # 使用记事本打开启动文件
oh-my-posh init pwsh | Invoke-Expression # 把这行代码添加其中保存

Get-PoshThemes # 查看已有的主题

oh-my-posh init pwsh --config "$env:POSH_THEMES_PATH/neko.omp.json" | Invoke-Expression # 把没加--config参数的替换为这行, 添加一个叫neko的主题
```

把`C:\Users\chpw2\AppData\Local\Programs\oh-my-posh\themes`这个路径添加为名叫`POSH_THEMES_PATH`的新建环境变量

## 安装字体

[Firacode 字体文件下载地址](https://github.com/ryanoasis/nerd-fonts/releases/download/v3.2.1/FiraCode.zip)

安装好**Firacode**字体后在终端设置里修改字体，保存退出

## 安装 scoop

具体查看[scoop](https://gitee.com/scoop-installer)

```powershell
# 脚本执行策略更改，默认自动同意
Set-ExecutionPolicy RemoteSigned -scope CurrentUser -Force

# 执行安装命令（默认安装在用户目录下，如需更改请执行“自定义安装目录”命令）
iwr -useb scoop.201704.xyz | iex


## 自定义安装目录（注意将目录修改为合适位置)
irm scoop.201704.xyz -outfile 'install.ps1'

.\install.ps1 -ScoopDir 'E:\Scoop' -ScoopGlobalDir 'E:\GlobalScoopApps'

# 切换分支到develop
scoop config scoop_branch develop

# 重新拉取git
scoop update

# 基本语法
scoop bucket add <别名> <git地址>
scoop bucket rm <别名>

scoop bucket add dorado https://gitee.com/scoop-installer/dorado
scoop bucket add scoopet https://gitee.com/scoop-installer/scoopet
scoop bucket add scoopcn https://gitee.com/scoop-installer/scoopcn
scoop bucket add scoop-zapps https://gitee.com/scoop-installer/scoop-zapps
scoop bucket add echo https://gitee.com/scoop-installer/echo-scoop
scoop bucket add aki https://gitee.com/scoop-installer/aki-apps
scoop bucket add siku https://gitee.com/scoop-installer/siku
scoop bucket add lemon https://gitee.com/scoop-installer/scoop-lemon
scoop bucket add cluttered https://gitee.com/scoop-installer/Cluttered-bucket
scoop bucket add iszy https://gitee.com/scoop-installer/scoop-iszy
scoop bucket add tomato https://gitee.com/scoop-installer/tomato
scoop bucket add muggle https://gitee.com/scoop-installer/scoop-muggle

# 查看已知bucket
scoop bucket known
```

## 安装 neovim

```powershell
# 安装必备软件
scoop install neovim neovide git lazygit gcc ripgrep fd unzip tree-sitter luarocks

# 下载安装LazyVim配置
git clone git@github.com:LazyVim/starter $env:LOCALAPPDATA\nvim --depth=1

# 为'nvim'设置别名为'vim'
Set-Alias -Name vim -Value 'nvim'
```

### nodejs 安装

[nodejs 安装方法](https://nodejs.org/zh-cn/download/package-manager):

```powershell
# installs fnm (Fast Node Manager)
winget install Schniz.fnm
# configure fnm environment
fnm env --use-on-cd | Out-String | Invoke-Expression
# download and install Node.js
fnm use --install-if-missing 20
# verifies the right Node.js version is in the environment
node -v # should print `v20.17.0`
# verifies the right npm version is in the environment
npm -v # should print `10.8.2`
```
