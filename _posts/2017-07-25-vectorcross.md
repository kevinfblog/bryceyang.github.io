---
layout: post
title: 向量叉乘
date: 2017-07-25 12:00:00.000000000 +9:00
tag: Math
---
>
> corss(叉乘 & 叉积)
>
> 结果是一个新向量，表示两个向量的法向量（按照右手法则确定方向）
>
> 公式: 
>
> ![图1](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/vectorcross_1.png)

```
|    x1    |    |    x2    |

|    y1    | X  |    y2    | = 

|    z1    |    |    z2    |

向量a·向量b=a1a2+b1b2+c1c2 

向量a×向量b= 

| i j k| 

|a1 b1 c1| 

|a2 b2 c2|

=(b1c2-b2c1,c1a2-a1c2,a1b2-a2b1) 

（i、j、k分别为空间中相互垂直的三条坐标轴的单位向量）。

叉乘的意义就是通过两个向量来确定一个新的向量，该向量与前两个向量都垂直
```
