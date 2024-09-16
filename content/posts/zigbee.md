+++
title = 'Zigbee'
date = 2024-09-14T09:30:17+08:00
draft = false
+++

> [zigbee 无线网络实验实训手册](/ZigBee无线网络实验实训手册V3.00.pdf)

## 必备知识

![](/img/img1.png)

## 所需软件

软件：
: IAR
: SmartRF flash programmer
: ZigBee 仿真器驱动
: WSN 综合监控软件

## 所需硬件

硬件：
: Zigbee 蓝色节点盒及其充电器
: CCDEBUG 仿真器
: 一台 PC

## 控制 LED 灯

![](/img/img3.png)

### GPIO 初始化函数

```c
/*初始化程序*/
void Initial(void){
    P1DIR |= 0x03;//P10、P11 定义为输出
    RLED = 1;
    YLED = 1;//LED
}

/*延时函数*/
void Delay(uint n){
    uint tt;
    for(tt = 0; tt < n; tt++);
    for(tt = 0; tt < n; tt++);
    for(tt = 0; tt < n; tt++);
    for(tt = 0; tt < n; tt++);
    for(tt = 0; tt < n; tt++);
}
```

