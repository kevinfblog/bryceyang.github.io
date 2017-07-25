---
layout: post
title: 推导正交投影(Orthographic Projection)
date: 2017-07-25 13:52:00.000000000 +9:00
tag: Math
---

>
> 推导正交投影
>

定义六个面
* left
* right
* bottom
* top
* near
* far

然后三个轴分开考虑

---
> x轴
>
>![图1](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/orthographic_projection_1.png)是椎体的x范围在[l,r],我们要变换到[-1,1]
> * 1 减去l变换到[0, r-l]![图2](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/orthographic_projection_2.png)
> * 2 乘以2/(r-l)变换到[0, 2]![图3](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/orthographic_projection_3.png)
> * 3 减去1变换到[-1,1]![图4](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/orthographic_projection_4.png)
> * 4 进一步简化![图5](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/orthographic_projection_5.png)
> * 5 展开![图6](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/orthographic_projection_6.png)
> * 最终![图7](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/orthographic_projection_7.png)

---
> y方向同理![图8](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/orthographic_projection_8.png)
---
> 最后推导z方向
> z方向取值范围在[0,1]![图9](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/orthographic_projection_9.png)
> * 1 减去n变换到[0,f-n]![图10](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/orthographic_projection_10.png)
> * 2 除以f-n变换到[0,1]![图11](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/orthographic_projection_11.png)
> * 3 展开![图12](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/orthographic_projection_12.png)
> * 最终![图13](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/orthographic_projection_13.png)
---
 
 即:![图14](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/orthographic_projection_14.png)
 
 ![图15](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/orthographic_projection_15.png)
