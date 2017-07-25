---
layout: post
title: 平面方程推导
date: 2017-07-25 9:51:00.000000000 +9:00
tag: Math
---

>
> 平面方程推导
>

向量[origin, ray]在xz平面为y处的交点

---
已知量

* 原点 origin
* 方向 ray
* y坐标

求

* 在xz平面上的交点out

---

```推导过程
out = origin + k * ray                        -> 其中k为常数
out.y = y = origin.y + k * ray.y              -> y为xz的y坐标
k = (y - origin.y) / ray.y                    -> 求解y
out = oragin + (y - origin.y) / ray.y * ray   -> 求解交点out
```
