+++
title = 'C语言指针'
date = 2024-09-17T15:56:04+08:00
draft = false
+++

>   [C语言指针网课](https://www.bilibili.com/video/BV1bo4y1Z7xf/?spm_id_from=333.999.0.0&vd_source=3c84cc8e3ab554e59e1e8c49f4140c19)

&用于获取变量的地址，*变量定义时用于声明指针变量，

```c
#include<stdio.h>
int main(void){
    int a = 5;
    int *p;
    p = &a; //指针变量p指向普通变量a的地址
    print("*p = ", *p); //解引用
    print("p = ", p);
    print("&p = ", &p);
    return 0;
}
```

>   void类型的指针可以存储其他类型变量的地址，但不能解引用获取值
