---
layout: post
title: 向量点成
date: 2017-07-25 10:27:00.000000000 +9:00
tag: Math
---
>
> dot(点成 & 内积 & 点积)
>
> 结果是一个float,表示两个向量的夹角
> 公式: u * v = u1v1 + u2v2 + u3v3 = |u| * |v| * cos(u, v)

* 如果结果 == 0, 两个向量互相 == 90°
* 如果结果 >  0, 两个向量夹角 <  90°
* 如果结果 <  0, 两个向量夹角 >  90°

>
> 例子
>

![图1](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/vectordot_1.png)

图(a)中向量AC投影到v

图(b)定义了![mip_0](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/vectordot_mip_0.png)由向量v顺时针旋转90°得到.从c向L做垂线,可以将c分解成沿v方向的部分Kv和垂直v方向的部分![mip_1](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/vectordot_mip_1.png),其中K M是特定的常数.即:
* 1 ![图2](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/vectordot_2.png)

给定c和v,我们想得到K和M.求出这两个值后,我们可以说c到v的正交投影是Kv并且点C到直线的距离是![mip_2](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/vectordot_mip_2.png)求解含量个未知数的两个方程的方法是消去一个未知数,即:让等式两边都点乘v
* 2 ![图3](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/vectordot_3.png)

![mip_3](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/vectordot_mip_3.png)结果是0所以
* 3 ![图4](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/vectordot_4.png)

即:
* 4 ![图5](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/vectordot_mip_4.png)

同理:让等式(1)两边同时点乘![mip_0](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/vectordot_mip_0.png)可以得到
* 5 ![图6](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/vectordot_mip_5.png)

合并以上结果
* 6 ![图7](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/vectordot_mip_6.png)
