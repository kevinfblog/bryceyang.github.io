---
layout: post
title: 高等数学 导数
date: 2018-05-28 11:24:00.000000000 +9:00
tag: Math
---

### 3.1 导数概念
#### 3.1.2 导数的定义
**定义:** 设函数 `$y=f(x)$`在点`$x_0$`的某个邻域内有定义,自变量`$x$`在`$x_0$`处取得的增量`$\Delta x$`,相应的函数的增量 `$\Delta y = f(x_0 + \Delta x) - f(x_0)$`,若极限
`$
\lim_{x_0\rightarrow\Delta x} \frac{\Delta y}{\Delta x} = \lim_{x_0\rightarrow\Delta x} \frac{f(x_0 + \Delta x) - f(x_0)}{\Delta x}
$`
存在,我们称函数`$f(x)$`在`$x_0$`处可导,并将该极限值称为函数`$f(x)$`在点`$x_0$`处的导数,记作 `$f'(x_0)$`或 `$y'\mid_{x=x_0}, \frac{dy}{dx} \mid_{x=x_0}$`
即
`$
f'(x_0) = \lim_{x_0\rightarrow\Delta x}\frac{f(x_0 + \Delta x) - f(x_0)}{\Delta x}
$`
如果`$f(x)$`在开区间 `$(a,b)$` 内任一点 `$x$` 处可导,则称函数在开区间 `$(a,b)$` 内可导,此时将上面公式中`$x_0$`换成`$x$`得到的就是`$f'(x)$`,称他是`$f(x)$`的**导函数**,即
`$
f'(x_0) = \frac{dy}{dx} = \lim_{x_0\rightarrow\Delta x}\frac{f(x_0 + \Delta x) - f(x_0)}{\Delta x}
$`
显然,函数下`$x_0$`的导数值`$f'(x_0)$`就是导函数`$f'(x)$`在点`$x_0$`的函数值,即
`$
f'(x_0) = f'(x)\mid_{x=x_0},x_0\in(a,b)
$`

#### 3.1.3 导数的几何意义
1. `$f'(x)$`可以表示曲线`$f(x)$`在点`$(x_0, f(x_0))$`,处***切线的斜率(`$k_T$`)***.即`$f'(x_0)=\tan(\alpha)$`,其中角度`$\alpha$`是**x轴正方向到切线的夹角**
2. ***法线的斜率(`$k_N$`)*** 为
`$
k_N = \tan(\beta) = \tan(\frac{\pi}{2} + \alpha) = -\cot(\alpha) = \frac{-1}{f'(x_0)}
$`


---
#### 补充:导数的物理意义

可以表示距离公式在某一时间点的瞬时速度
距离公式 `$s = f(t)$`的导函数`$f'(t_0)$`可以表示物体在`$t_0$`时刻的瞬时速度
---


#### 3.1.4 函数在一点的左右导数
有时候为了方便,常记 `$\Delta x = x - x_0$`, 显然`$\Delta x \rightarrow 0$`等价于`$x\rightarrow x_0$`,于是我们便得到倒数定义的有一种常用的等价形式:
`$
f'(x_0) = \lim_{x\rightarrow x_0}\frac{f(x) - f(x_0)}{x-x_0}
$`
当我们讨论比值 `$\frac{f(x) - f(x_0)}{x-x_0}$`在`$x_0$`处的左右极限时,就产生了左右导数的概念.

**定义:**
1. 设函数`$f(x)$`在`$x_0$`的某个*右半邻域*有定义,若*右极限*`$\lim_{x\rightarrow x_0^+}\frac{f(x) - f(x_0)}{x - x_0}$`存在,记为`$f'_+(x_0)$`,并称他是函数`$f(x)$`在`$x_0$`的**右导数**
2. 设函数`$f(x)$`在`$x_0$`的某个*左半邻域*有定义,若*左极限*`$\lim_{x\rightarrow x_0^-}\frac{f(x) - f(x_0)}{x - x_0}$`存在,记为`$f'_-(x_0)$`,并称他是函数`$f(x)$`在`$x_0$`的**左导数**
3. 左右导数统称为**单侧导数**
 

**定理:**
函数`$f(x)$`在`$x_0$`处可到的**充分必要条件**是`$f(x)$`在`$x_0$`出的左右导数**存在且相等**,其相等的值就是`$f(x)$`在`$x_0$`处的导数,既有
`$
f'(x_0) = f'_+(x_0) = f'_-(x_0)
$`
由该定理知,如果`$f(x)$`在`$x_0$`处的左右导数中有一个不存在,或者虽然都存在但不相等,则`$f(x)$`在`$x_0$`处不可导.

#### 3.1.5 函数在一点的可导性与连续性的关系
**定理:**
1. 如果函数`$y=f(x)$`在点`$x_0$`处可导,则函数在`$x_0$`处**必连续**.
2. 如果函数`$y=f(x)$`在点`$x_0$`处连续,则函数在`$x_0$`处**不一定可导**.


### 3.2 基本初等函数的求导公式与求导法则

#### 3.2.1基本初等函数求导公式之一
1. `$y = c$`则`$(c)'  =0$`
2. `$y = x^n$`则`$(x^n)' = nx^{n-1}$`其中`$n \in (0, +\infty]$`
3. `$y = x^\mu$`则`$(x^\mu)' = \mu x^{\mu-1}$`其中`$\mu$`为任意实数
    1. `$y = \sqrt{x}$`则`$(\sqrt{x})' = \frac{1}{2\sqrt{x}}$`
    2. `$y = \frac{1}{x}$`则`$(\frac{1}{x})' = -\frac{1}{x^2}$`
4. 
    1. `$y = \sin{x}$`则`$(\sin x)' = \cos x$`
    2. `$y = \cos{x}$`则`$(\cos x)' = -\sin x$`
5.
    1. `$y = a^x$`则`$(a^x)' = a^x \cdot \ln a$`其中`$(a>0,a\neq 1);$`
    2. `$y=e^x$`则`$(e^x)' = e^x$`
6. 
    1. `$y=\log_{a}x$`则`$(\log_{a}x)'=\frac{1}{x \ln{a}}$`其中`$(a>0,a\neq 1);$`
    2. `$y=\ln{x}$`则`$(\ln{x})'=\frac{1}{x}$`

#### 3.2.2 函数的和 差 积 商的求导法则

##### 1. 函数和 差的求导法则
设函数`$u=u(x)$`及`$v=v(x)$`有导数`$u'=\frac{du(x)}{dx}$`及`$v'=\frac{dv(x)}{dx}$`则有

`$(u\pm v)'=u'\pm v'$`或`$\frac{d}{dx}(u\pm v)=\frac{du}{dx}\pm \frac{dv}{dx}$`

##### 2. 常数乘函数的求导法则
设函数`$u=u(x)$`可导,记`$\frac{du(x)}{dx}=u'$`,`$c$`实常数,则有`$(cu)'=cu'$`,或者`$\frac{d}{dx}(cu)=c\frac{du}{dx}$` 

该法则表明:**求一个常数与一个可导函数乘机的导数时,常数因子可以提到求导记号的外面去.**

将1 2法则综合自来有:
`$
(c_1u+c_2v)'=c_1u'+c_2v'
$`
##### 3 函数乘积的求导法则
设函数`$u=u(x)$`与`$v=v(x)$`可导,则有

`$(uv)'=u'v+vu'$`,或`$\frac{d}{dx}[u(x)\cdot v(x)]=v(x)\frac{du(x)}{dx}+u(x)\frac{dv(x)}{dx}$`
推广到任意有限多个函数之积:
`$
(uvw)'=(uv)'w+(uv)w'=(u'v+uv')w+(uv)w'=u'vw+uv'w+uvw'
$`
##### 4 函数商的求导法则
设函数`$u=u(x)$`与`$v=v(x)$`可导,`$v(x)\neq0$`,则有
`$
(\frac{u}{v})'=\frac{u'\cdot v-u\cdot v'}{v^2}
$`
上式中令`$u=1$`,得到一个常用的倒函数求导公式
`$
(\frac{1}{v})'=-\frac{1}{v^2}\cdot v'
$`
#### 3.2.3 基本初等函数求导公式之二
1. `$y=\tan x$`,则`$(\tan x)'=\sec^2x$`
2. `$y=\cot x$`,则`$(\cot x)'=-\csc^2x$`
3. `$y=\sec x$`,则`$(\sec x)'=\sec x\cdot \tan x$`
4. `$y=\csc x$`,则`$(\csc x)'=-\csc x\cdot \cot x$`
#### 3.2.3 反函数的求导法则
**定理3.2.1** 设函数`$x=\varphi(y)$`在某一区间内单调、连续,又在区间内一点`$y$`处的导数`$\varphi'(y)$`存在且不为零,则反函数`$y=f(x)$`在对应点`$x$`处具有导数`$f'(x)$`,并且有
`$
f'(x)=\frac{1}{\varphi'(y)}
$`
这就是说反函数的导数等于直接函数的导数的倒数.
#### 3.2.5 基本初等函数求导公式之三
1. `$y=\arcsin x$`,则`$(\arcsin x)'=\frac{1}{\sqrt{1-x^2}}$`
2. `$y=\arccos x$`,则`$(\arccos x)'=\frac{-1}{\sqrt{1-x^2}}$`
3. `$y=\arctan x$`,则`$(\arctan x)'=\frac{1}{1+x^2}$`
4. `$y=arccot\ x$`,则`$(arccot\ x)'=\frac{-1}{1+x^2}$`
#### 3.2.6 复合函数的求导法则
##### 1.含一次复合的函数的求导公式
**定理 3.2.2** 若函数`$y=f(u)$`在点`$u$`可导,函数`$u=\varphi(x)$`在点`$x$`可导,则复合函数`$y=f[\varphi(x)]$`在点`$x$`也可导,且有等式
`$
\{f[\varphi(x)]\}'=\frac{d}{dx}\{f[\varphi(x)]\}=f'(u)\cdot\varphi'(x)
$`
##### 2.含两次及以上复合函数的求导法则
将定理3.2.2推广到多个则有
`$
y=f\{u[v(x)]\}, y'=f'(u)\cdot u'(v)\cdot v'(x)
$`

#### 3.3 高阶导数
**定义:** 若函数`$y=f(x)$`的导数`$f'(x)$`在`$x$`处仍可导,则把一阶导数的导数`$[f'(x)]$`或`$\frac{d}{dx}[\frac{df(x)}{dx}]$`成为函数`$y=f(x)$`的二阶导数,记作:
`$
[f'(x)]'=f^n(x)'
$`
或者
`$
\frac{d}{dx}[\frac{df(x)}{dx}]=\frac{d^2f(x)}{dx^2}
$`
也常用`$y$`代替`$f(x)$`有`$y''$`或者`$\frac{d^2y}{dx^2}$`.
类似有二阶导数的导数成为三阶导数,记作:`$y'''$`或者`$\frac{d^3y}{dx^3}$`;对于三阶以上的导数,一般改用数字,如`$y^{(4)}$`或`$f^{(4)}$`,便是四阶导数;`$n$`阶导数记作:
`$
y^{(n)}
$`
或者
`$
f^{(n)}(x),\frac{d^ny}{dx^n}
$`
或者
`$
\frac{d^nf(x)}{dx^n}
$`
我们把二阶及以上的导数,统称为高阶导数


>
> 延伸: 由函数及其导数构成的等式称作**微分方程**
>
> 例如: `$y''+y=0$`
>

##### 3.3.2 常见函数的`$n$`阶求导公式
关于`$n$`阶导数,与一阶导数类似,仍满足下列先行性质:设`$c_1$`、`$c_2$`是常数,函数`$u(x)$`与`$v(x)$`为`$n$`阶可导,则有:
`$
[c_1u(x)+c_2v(x)]^{(n)}=c_1[u(x)]^{(n)}+c_2[v(x)]^{(n)}
$`
**公式**
1. 设`$\omega$`与`$\varphi$`是常数,则
    1. `$y=\sin(\omega x+\varphi)$`,有`$\frac{d^n}{dx^n}[\sin(\omega x+\varphi)]=\omega ^n\sin(\omega x + \varphi + \frac{n\pi}{2})$`;
    2. `$y=\cos(\omega x+\varphi)$`,有`$\frac{d^n}{dx^n}[\cos(\omega x+\varphi)]=\omega ^n\cos(\omega x + \varphi + \frac{n\pi}{2})$`;
2. `$y=a^x(a>0,a\neq1)$`,有
`$
\frac{d^n}{dx^n}(a^x)=a^x(\ln a)^n
$`
3. 设`$a$`为常数,`$y=\frac{1}{x+a}$`,有
`$
\frac{d^n}{dx^n}(\frac{1}{x+a})=\frac{(-1)^n\cdot n!}{(x+a)^{n+1}}
$`

##### 3.3.3 函数乘积的`$n$`阶导数的莱布尼兹公式

首先,由乘积求导法则有
`$
(u\cdot v)'=u'\cdot v + u\cdot v'
$`
上式两边求导一次:
`$
(u\cdot v)^{(2)}=u''v+2u'v'+uv''=u^{(2)}v^{(0)}+2u^{(1)}v^{(1)}+u^{(0)}v^{(0)}
$`
其中`$v^{(0)}=v$`,`$u^{(0)}=u$`,对上式在求导一次,变为

`$
\begin{array}{l}
(u\cdot v)^{(3)}=[u^{(2)}v^{(0)}]'+2[u^{(1)}v^{(1)}]'+[u^{(0)}v^{(2)}]' \\\\
\quad\quad\quad\quad=u^{(3)}v^{(0)}+3u^{(2)}v^{(1)}+3u^{(1)}v^{(2)}+u{(0)}v^{(3)}
\end{array}
$`

依次求导`$n$`次,容易得到按下述规则展开的式子

`$
\begin{array}{l}
(u\cdot v)^{(n)}=u^{(n)}v^{(0)}+nu^{(n-1)}v^{(1)}+\frac{n(n-1)}{1\cdot2}u^{(n-2)}v^{(2)}+\cdots+ \\\\
\quad\quad\quad\quad\quad\frac{n(n-1)\cdots(n-k+1)}{k!}u^{(n-k)}v^{(k)}+\cdots+u^{(0)}v^{(n)}
\end{array}
$`

此式也可以用连加符号`$\sum$`表示为
`$
(u\cdot v)^{(n)}=\sum_{k=0}^nC_n^kv^{(k)}u^{(n-k)}
$`
#### 3.5 函数的微分及其应用
**定义3.5.1** 设函数`$y=f(x)$`在某个区间内有定义,如果在点`$x$`出函数的增量`$\Delta y$`可以表示为

`$
\Delta y=f(x+\Delta x)-f(x)=\varphi(x)\cdot\Delta x+o(\Delta x)
$`

其中函数`$\varphi(x)$`也可以是常数,而且他与`$\Delta x$`无关,当`$\Delta x\rightarrow0$`时`$o(\Delta x)$`是比`$\Delta x$`高阶的无穷小,于是我们称函数`$y=f(x)$`在点`$x$`可微,并将`$\Delta y$`的线性部分`$\varphi(x)\cdot\Delta x$`叫做函数`$y=f(x)$`在点`$x$`的**微分**,记作`$df(x)$`即
`$
dy=df(x)=\varphi(x)\cdot\Delta x
$`
通常我们也把自变量`$x$`的增量`$\Delta x$`记作`$dx$`,于是上式可也写为`$dy=\varphi(x)dx$`

**定理 3.5.1** 函数`$y=f(x)$`在点`$x$`可微的充分必要条件是`$y=f(x)$`在点`$x$`可导,且当函数可微时,有`$dy=f'(x)dx$`成立.

##### 微分的几何意义与物理意义
1. 数学意义:表示微分三角形的斜边
2. 物理意义:当`$y=f(x)$`换为变速运动的位置函数`$s=s(t)$`时,其微分式
`$
ds=s'(t)\Delta t=s'(t)dt
$`
他表示在`$\Delta t$`内,物体以速度`$s'(t)$`做直线运动所做过的路程.