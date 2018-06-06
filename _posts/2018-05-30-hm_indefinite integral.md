---
layout: post
title: 高等数学 不定积分
date: 2018-05-30 11:24:00.000000000 +9:00
tag: Math
---
# 5 不定积分 
## 5.1 不定积分的概念和性质 
### 5.1.1 原函数和不定积分的概念

  定义5.1.1 已知$f(x)$是定义在某一个区间内的函数,如果存在函数$F(x)$,使得对该区间内的任意一点$x$,都有 
$$F'(x)=f(x)\quad or\quad dF(x)=f(x)dx$$ 
则称在该区间内的函数$F(x)$是函数$f(x)$的原函数 
  注1: 这里要指出的是,一个函数的原函数是与区间有关的,例如,在$(-\infty,0)$内,由于$[\ln(-x)]'=-\frac{1}{x}$,故$\ln(-x)$是$-\frac{1}{x}$的原函数;而在$(0,+\infty)$内,由于$(\ln x)'=\frac{1}{x}$,故$\ln x$是$\frac{1}{x}$的原函数. 
  注2: 我们知道初等函数在其定义区间内是连续的,因此它的元杉树一定存在.但要指出,初等函数在其定义区间内的原函数不一定是初等函数,例如: 
$$y=e^{-x^2},y=\frac{\sin x}{x},y=\frac{1}{\ln x},y=\frac{1}{\sqrt{1+x^4}}, \cdots$$ 
  定义5.1.2 函数$f(x)$的全体原函数称为$f(x)$的不定积分,记作: 
$$\int f(x)dx$$ 
其中$\int$称为积分号,$f(x)$称为被积函数,$f(x)dx$称为被积表达式,$x$称为积分变量,$dx$称为积分变元. 
$$\int f(x)dx=F(x)+C\quad(C为任意常数)\tag{5.1.1}$$ 
### 5.1.2 基本积分表

$\int x^\mu dx=\frac{x^{\mu+1}}{\mu+1}+C(\mu为常数,\mu\neq-1),特别地\int dx=x+C$; 
$\int\frac{dx}{x}=\ln |x|+C$; 
$\int \frac{dx}{1+x^2}=\arctan x+C$; 
$\int \frac{dx}{1-x^2}=\arcsin x+C$; 
$\int \cos xdx=\sin x+C$ 
$\int \sin xdx=-\cos x+C$; 
$\int \frac{dx}{\cos^2x}=\int \sec^2 xdx=\tan x+C$; 
$\int \frac{dx}{\sin^2x}=\int \csc^2xdx=-\cot x+C$; 
$\int \sec x\tan xdx=\sec x+C$; 
$\int \csc x \cot x dx=-\csc x+C$; 
$\int e^xdx=e^x+C$; 
$\int a^xdx=\frac{a^x}{\ln a}+C(a>0,a\neq1)$ 
### 5.1.3 不定积分的性质

函数的和的不定积分等于各个函数的不定积分的和,即: 
$$\int [f(x) + g(x)]dx=\int f(x)dx+\int g(x)dx$$ 
推广到多个函数,即: 
$$\int[f_1(x)+f_2(x)+\cdots+f_n(x)]dx=\int f_1(x)dx + \int f_2(x)dx+\cdots+\int f_n(x)dx$$ 
用$\sum$的形式写出为: 
$$\int[\sum_{k=1}^nf_k(x)]dx=\sum_{k=1}^n\int f_k(x)dx$$ 
被积函数中不为零的常数因子可以提到积分号外面来,即: 
$$\int kf(x)dx=k\int f(x)dx\quad(k为常数,且k\neq0)\tag{5.1.3}$$



## 5.2 换元积分法

求$\int e^{2x}dx$. 如果将被积表达式视为一个微分,即$e^{2x}dx=\frac{1}{2}e^{2x}d(2x)$,所求积分便可化为$\frac{1}{2}\int e^{2x}d(2x)$,并令$u=2x$,则上式就变成了$\frac{1}{2}\int e^udu$,积分得$\frac{1}{2}\int e^udu=\frac{1}{2}e^u+C$,在将$u=2x$代回,得$\int e^{2x}dx=\frac{1}{2}e^{2x}+C$.完整的计算过程是  

$$

\begin{eqnarray}

\int e^{2x}dx &=& \frac{1}{2}\int e^{2x}(2x)'dx \\

                    &=&\frac{1}{2}\int e^{2x}d(2x) \\

                    &=&\frac{2}{2}\int e^udu|_{u=2x} \\

                    &=&[\frac{1}{2}e^u+C]_{u=2x} \\

                    &=&\frac{1}{2}e^{2x}+C

\end{eqnarray}

$$  

这样的得到的积分方法称为**换元积分法**,简称**换元法**.换元法有两类,**第一换元法**和**第二换元法**  

### 5.2.1 第一换元法

**定理5.2.1** 设$F(u)$是$f(u)$的原函数,$u=\varphi(x)$可导,则$F[\varphi(x)]$是$f[\varphi(x)]\varphi '(x)$的原函数.既有换元积分公式  

$$\int f[\varphi(x)]\varphi '(x)dx=\int f(u)du |_{u=\varphi(x)}=F[\varphi(x)]+C \tag{5.2.1}$$

有时候第一换元法也叫做**"凑微分"**法.  

**积分方法3**: 凑微分发.设$F(x)$是$f(x)$的原函数,$\varphi(x)$可导,则有:  

$$\int f[\varphi(x)]\varphi '(x)dx=\int f[\varphi(x)]d\varphi(x)=F[\varphi(x)]+C$$  

**常用凑微分积分公式1:** 设$F(x)$是$f(x)$的原函数,$u=ax+b$,则有  

$$\int f(ax+b)dx=\frac{1}{a}\int f(ax+b)d(ax+b)=\frac{1}{a}F(ax+b)+C$$  

**常用凑微分积分公式2:** 设$F(x)$是$f(x)$的原函数,$u=a+bx^\mu$,则有  

$$
\begin{eqnarray}
\int f(a+bx^\mu)x^{\mu-1}dx &=& \frac{1}{b\mu}\int f(a+bx^\mu)d(a+bx^\mu) \\
                                             &=& \frac{1}{b\mu}F(a+bx^\mu)+C\quad(b\neq0,\mu\neq0,-1)
\end{eqnarray}
$$  

**常用凑微分积分公式3:** 设$F(x)$是$f(x)$的原函数,$u=\sin ax$则有:  

$$\int f(\sin ax)\cos axdx=\frac{1}{a}\int f(\sin ax)d(\sin ax)=\frac{1}{a}F(\sin ax)+C\quad(a\neq0)$$  

**常用凑微分积分公式4:** 设$F(x)$是$f(x)$的原函数,$u=\cos ax$则有:  

$$\int f(\cos ax)\sin axdx=-\frac{1}{a}\int f(\cos ax)d(\cos ax)=-\frac{1}{a}F(\cos ax)+C\quad(a\neq0)$$  

**常用凑微分积分公式5:** 设$F(x)$是$f(x)$的原函数,$u=\ln ax$,则有:  

$$\int f(\ln ax)\frac{1}{x}dx=\int f(\ln ax)d(\ln ax)=F(\ln ax)+C\quad(a\neq0)$$  

**常用凑微分积分公式6:** 设$F(x)$是$f(x)$的原函数,$u=e^{ax}$,则有:  

$$\int f(e^{ax})e^{ax}dx=\frac{1}{a}\int f(e^{ax})d(e^{ax})=\frac{1}{a}F(e^{ax})+C\quad(a\neq0)$$  

**常用凑微分积分公式7:** 设$F(x)$是$f(x)$的原函数,$u=\arcsin x$ 则有:  

$$\int f(\arcsin x)\frac{1}{\sqrt{1-x^2}}dx=\int f(\arcsin x)d(\arcsin x)=F(\arcsin x)+C$$  

**常用凑微分积分公式8:** 设$F(x)$是$f(x)$的原函数,$u=\tan ax$,则有:  

$$\int f(\tan ax)\sec^2axdx=\frac{1}{a}\int f(\tan ax)d(\tan ax)=\frac{1}{a}F(\tan ax)+C\quad(a\neq0)$$  

**常用凑微分积分公式9:** 设$F(x)$是$f(x)$的原函数,$u=\csc ax$则有:  

$$\int f(\csc ax)\cot ax\csc axdx=-\frac{1}{a}\int f(\csc ax) d(\csc ax)=-\frac{1}{a}F(\csc ax) +C\quad(a\neq0)$$  

  

**积分方法4:** 分项凑微分法.  

**例5.2.10** 求$\int\sin 3x\cos 2xdx$  

**解:**利用积化和差公式分项,有  

$$
\begin{array}{l}
\int\sin 3x\cos 2xdx &=& \frac{1}{2}\int(\sin 5x+\sin x)dx=\frac{1}{2}\int\sin 5xdx+\frac{1}{2}\int\sin xdx\\
                                &=& \frac{1}{10}\sin 5xd(5x)-\frac{1}{2}\cos(x)\\
                                &=& -\frac{1}{10}\cos 5x-\frac{1}{2}\cos(x)+C
\end{array}
$$  

**注:**对于形如$\int\sin ax\sin bxdx,\int\cos ax\cos bxdx$的不定积分都可以用例5.2.10的方法计算,其中$a,b$为常数.  



### 5.2.2 第二换元法

第一换元法的表示式为  
$$\int f[\varphi(x)]\varphi'(x)dx=\int f(u)du|_{u=\varphi(x)}=F(u)|_{u=\varphi(x)}$$  
其中$f(u)$的原函数容易求出,如果第一个等式左边的原函数容易求出,我们可以把等式写成  
$$\int f(u)du|_{u=\varphi(x)}=\int f[\varphi(x)]\varphi'(x)dx$$  
求出右边的不定积分,再将$u=\varphi(x)$的反函数$x=\varphi^{-1}(u)$代入,即得左边的不定积分,实际上这就是第二换元法.习惯上,上式左边的积分变量用$x$,右边的积分变量用$t$,函数$\varphi$用$\phi$,于是上式可化为  
$$\int f(x)dx |_{x=\phi(t)}=\int f[\phi(t)]\phi'(t)dt|_{t=\phi^{-1}(x)}$$  

**定理5.2.2** 设$x=\varphi(t)$是单调,可导函数,且$\varphi '(t)\neq0$,又$\Phi(t)$是$f[\varphi(t)]\varphi '(t)$的原函数,则$\Phi[\varphi^{-1}(x)]$是$f(x)$的原函数,既有积分换元公式  

$$\int f(x)dx=[\int f[\varphi(t)]\varphi'(t)dt]_{t=\varphi^{-1}(x)}=\Phi[\varphi^{-1}(x)]+C\tag{5.2.2}$$
