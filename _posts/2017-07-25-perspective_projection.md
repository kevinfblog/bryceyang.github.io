---
layout: post
title: 推导透视投影(Perspective Projection)
date: 2017-07-25 16:52:00.000000000 +9:00
tag: Math
---

>
> 推导透视投影
>

---
> 距离表示法

 ![图1](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/perspective_projection_1.png)
 
 * 1 把点(x,y,z)投引导近平面n所以他的x坐标的范围在[l,r],y坐标在[b,t]
 * 2 从原点到(x,y,z)连线 然后 做(x,y,z)到z的垂线. (0,0,z)到(x,y,z)的距离是L 根据勾股定理可以求出L的长度 ![图2](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/perspective_projection_2.png)
 * 3 根据相似三角形可以求出L2的长度![图3](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/perspective_projection_3.png)
 * 4 展开![图4](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/perspective_projection_4.png)
 * 5 在展开![图5](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/perspective_projection_5.png). 所以 黑点处的x坐标就是x*(n/z)  y坐标就是y* (n/z)
 * 6 把x y映射到视椎体(根据正交投影中的推到方式)有![图6](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/perspective_projection_6.png)
 * 7 根据上面 x坐标就是x*(n/z)  y坐标就是y* (n/z) 有![图7](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/perspective_projection_7.png)
 * 8 然后乘以z![图8](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/perspective_projection_8.png)
 

> 目标是把结果写成
>
> ![图9](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/perspective_projection_9.png)
> 才能写进矩阵
>
> 办法写一个变换矩阵把(x, y, z)映射到(x'z, y'z, z'z)然后，把各部分除以点z，得到(x', y', z')。
>
> 因为z到z'不依赖x y所以需要一个公式 z'z = pz + q  (其中p q是常数).当z=n时z'=0 z=f时z'=1. 
>
>所以:
* 1 要把[n,f]映射到[0,1]把第一组值(当z=n时z'=0)带入z'z = pz + q有![图10](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/perspective_projection_10.png)
* 2 第二组(z=f时z'=1)带入有![图11](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/perspective_projection_11.png)
* 3 带入q求p有![图12](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/perspective_projection_12.png)
* 4 根据上面q = -pn求q有![图15](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/perspective_projection_15.png)
* 5 最后带入p q到z'z = pz + q有![图13](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/perspective_projection_13.png)
* 6 同理xy有![图14](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/perspective_projection_14.png)
* 7 考虑其次坐标有![图16](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/perspective_projection_16.png)

即:

![图17](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/perspective_projection_17.png)

最后:

![图18](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/perspective_projection_18.png)

---
>
> 角度表示法
>

![图19](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/perspective_projection_19.png)
* 1 根据三角形有![图20](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/perspective_projection_20.png)
* 2 这个表达式可以取代投影矩阵中的高度, 定义r为宽比高的aspect, 使用横纵比r代替宽度cot(a/2) = (n  / (h/2)) 各自除以r有![图21](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/perspective_projection_21.png)
* 3 r = w/h 有![图22](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/perspective_projection_22.png)
* 4 有了用垂直可视范围角度a和横纵比r构成的透视投影矩阵
![图23](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/perspective_projection_23.png)
