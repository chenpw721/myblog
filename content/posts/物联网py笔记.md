+++
title = '物联网 py 笔记'
date = 2024-09-06T21:48:59+08:00
draft = false
tags = ["物联网", "python"]
categories = ["学习笔记"]
+++

## Py 所需包

### Pyinstaller 库
<!--more-->
> 用于打包项目为 exe 程序

安装：`pip install pyinstaller`

用法 (在命令行中输入): 

- 可覆盖原有包：`pyinstaller -F main.py`
- 可更改打包后程序名字为 Test：`pyinstaller -F -n "Test" main.py`

### PyQt5 库

> 用于开发 GUI 界面

安装：

- `pip install pyqt5`
- `pip install pyqtchart`:PyQt5 的 QtChart 包需要单独安装

导入：`import PyQt5`

### socket 库

> 网络编程库，py 自带库无需安装

导入：`import socket`

### requests 库

> 爬虫库

安装：`pip install requests`

导入：`import requests`

### pandas 库

> 数据分析库

安装命令：

- `pip install pandas`
- `pip install openpyxl # pandas依赖`

导入：`pip install pandas`

### pyserial 库

> 串口库

安装：`pip install pyserial`

导入：`import serial`

## 学习笔记
