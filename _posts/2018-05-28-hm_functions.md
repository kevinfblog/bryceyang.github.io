---
layout: post
title: 高等数学 函数
date: 2018-05-28 11:24:00.000000000 +9:00
tag: Math
---

## 1.1 邻域


> 设 `$x_0$` `$a$` 是两个实数, 且 `$a > 0$1`, 则满足不等式  
> `$x_0 - a < x < x_0 + a$`, 即 `$-a < x - x_0 < a $`
> 的实数`$x$`的全体成为点`$x_0$`的`$a$`邻域. 记作`$U(x_0,a)$`  
> 点`$x$`成为此**邻域的中心**  
> `$a$`成为此邻域的**半径**  


```math
U(x_0, a) = (x_0 - a, x_0 + a)  
```

> `$U(x_0,a)$`去点中心`$x_0$`后的数集为`$x_0$`的**去心`$a$`邻域**

#### 绝对值表示
```math
U(x_0, a) = \{x | |x - x_0| < a\}
```

也就是
```math
\begin{array}{l}
\quad\quad|x - x_0| < a \\\\
-a < x - x_0 < a \\\\
\quad x_0 - a < x < x_0 + a
\end{array}
```

> 推导自:  
> |a| <= k <=> -k <=a <= k  
> -a < x - x0 < a 减x得  
> -a - x > x0 > a - x 乘-1得  
> x + a < x0 < x - a

即
```math
\{x| |x - x_0| < a\} = (x_0 - a, x_0 + a) = U(x_0, a)
```

## 1.3 函数的几种特性

#### 1.3.1 有界性
> **定义:** 设函数`$y=f(x)$`在数集`$A$`上有定义,如果存在常数`$M>0$`,是的对任意`$x\in A$`,有  
> 
```math
|f(x)| <= M
```
>
> 则称函数`$$`在`$A$`上**有界**,否则**无界**

例如:`$y = \sin(x)$` 在定义域`$(-\infty,+\infty)$`内有界,这是因为对任意`$x\in(-\infty,+\infty)$`总有`$|sin x| <= 1$`.
再如: `$y = \frac{1}{x}$`在定义域`$(-\infty,0)\cup(0,\infty)$` 内无界,  
这是因为对任意实数`$M>0$`,总存在点`$x_0 = \frac{1}{2M} > 0$`,显然`$x\in(-\infty,0)\cup(0,+\infty)$`  
使得`$|\frac{1}{x_0}| = 2M > M$`

#### 1.3.2 单调性
**定义:** `$x_1 < x_2$` `$f(x_1) < f(x_2)$` or `$f(x_1) <= f(x_2)$` **单调增加(不减)**  
**定义:** `$x_1 < x_2$` `$f(x_1) > f(x_2)$` or `$f(x_1) >= f(x_2)$` **单调减少(不增)**

#### 1.3.3 奇偶性
**定义:** `$f(-x)=f(x)$` **偶函数**  
**定义:** `$f(-x)=-f(x)$` **奇函数**  

**推论:**  
- 若`$f(x),g(x)$`同为**偶函数**或同为**奇函数**,则`$f(x)\cdot g(x)$`必为**偶函数**.
- 若`$f(x),g(x)$`一个为**奇函数** ,一个为**偶函数**,则则`$f(x)\cdot g(x)$`必为**奇函数**.
- 若`$f(x),g(x)$`同为**偶函数**,则`$f(x)\pm g(x)$`必为**偶函数**.
- 若`$f(x),g(x)$`同为**奇函数**,则`$f(x)\pm g(x)$`必为**奇函数**.
- 若`$f(x),g(x)$`一个为**奇函数** ,一个为**偶函数**,则`$f(x)\pm g(x)$`必为**非奇非偶函数**.
- 设`$f(x)$`是定义在对称于原点的区间上的函数,则`$f(x)+f(-x)$`必为**偶函数**.

#### 1.3.4 周期性
**定义:** 设函数`$y=f(x)$`在`$(-\infty,+\infty)$`内有定义,如果存在`$T>0$`,使得对任意`$x\in(-\infty,+\infty)$`有
```math
f(x+T)=f(x)
```

则称`$f(x)$`为**周期函数**,`$T$`为其**周期**.

#### 1.4 反函数与复合函数
**定义:** `$y=f(x)$`定义域为`$D$`,值域为`$Z$`.如果对任意`$y\in Z$`,有唯一去顶的`$x\in D$`与之对应,且满足`$y=f(x)$`,则称此`$x$`关于`$y$`的函数为函数`$y=f(x)$`的反函数,记作 `$x=f^{-1}(y)$`  
**定理:** 函数`$y=f(x)$`,在其定义区间`$D$`内单调增加(或减少),其值域为`$Z$`,则必然灿在反函数`$x=f^{-1}(y)$`,在他的`$Z$`内也单调增加(或减少)
#### 1.5.1 基本初等函数
**基本初等函数如下**
名称 | 符号 | 图形 | 定义域 | 简单性质
---|---|---|---|---
常数函数 |`$y=c$`|![y=c](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/gs_1.5_1.png)|`$(-\infty,+\infty)$`|偶函数
幂函数 | `$y = x ^ a$` | ![y=x^a](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/gs_1.5_2.png) | 定义域随`$a$`不同而不同,但在`$(0,+\infty)$`上均有定义|在`$(-\infty,+\infty)$`内,当`$a>0$`是,单调增加,当`$a<0$`时,单调减少|
指数函数|`$y=a^x(a > 0, a \neq 1$`)|![y=a^x](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/gs_1.5_3.png)|`$(-\infty,+\infty)$`|`$a^x>0. a > 1$`,单调增加;`$0 < a < 1$`单调减少|
对数函数|`$y=\log a X$`|![y=loga X](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/gs_1.5_4.png)|`$(0,+\infty)|a>1$`,单调增加;`$0 < a < 1$`,单调减少|
三角函数|`$y=\sin x$`|![y=sin(x)](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/gs_1.5_5.png)|`$(-\infty,+\infty)$`|有界函数 `$|\sin x| \leq 1$`.以`$2\pi$`为周期的周期函数.奇函数|
||`$y=\cos x$`|![y=cos(x)](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/gs_1.5_6.png)|`$(-\infty,+\infty)$`|有界函数 `$|\cos x| < 1$`.以`$2\pi$`为周期的周期函数.偶函数|
||`$y=\tan x$`|![y=tan(x)](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/gs_1.5_7.png)|`$x\neq k\pi+\frac{\pi}{2} | k=0,\pm1,\pm2,\cdots,(-\infty,+\infty)$`|以`$\pi$`为周期的周期函数.奇函数;在`$(-\pi/2,\pi/2)$`内,单调增加|
||`$y=\cot x$`|![y=cot(x)](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/gs_1.5_8.png)|`$x\neq k\pi | k=0,\pm1,\pm2,\cdots,(-\infty,+\infty)$`|以`$\pi$`为周期的周期函数.奇函数;在`$(0,\pi)$`内,单调减少|
|反三角函数|`$y=\arcsin x$`|![y=arcsin(x)](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/gs_1.5_9.png)|`$[-1,1]$`|有界函数 `$|\arcsin x| \leq\frac{\pi}{2}$`;单调增加;奇函数|
||`$y=\arccos x$`|![y=arccos(x)](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/gs_1.5_10.png)|`$[-1,1]$`|有界函数 `$0\leq\arccos x\leq\pi$`;单调减少|
||* `$y=\arctan x$`|![y=arctan(x)](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/gs_1.5_11.png)|`$(-\infty,+\infty)$`|有界函数 `$|\arctan x| < \frac{\pi}{2}$`;单调增加;奇函数|
||* `$y=arccot\ x$`|![y=arccot(x)](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/gs_1.5_12.png)|`$(-\infty,+\infty)$`|有界函数 `$0 < arccot\ x < \pi$`;单调减少|
#### 1.5.2 初等函数
**定义:** 由**基本初等函数**经过有限次四则运算和有有限次复合构成并可以用一个式子表示的函数称为**初等函数**
