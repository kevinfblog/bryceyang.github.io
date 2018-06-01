---
layout: post
title: 高等数学 不定积分
date: 2018-05-30 11:24:00.000000000 +9:00
tag: Math
---
# 5 不定积分  
## 5.1 不定积分的概念和性质  
### 5.1.1 原函数和不定积分的概念
&emsp;&emsp;**定义5.1.1**&emsp;已知$f(x)$是定义在某一个区间内的函数,如果存在函数$F(x)$,使得对该区间内的任意一点$x$,都有  
$$F'(x)=f(x)\quad or\quad dF(x)=f(x)dx$$  
则称在该区间内的函数$F(x)$是函数$f(x)$的**原函数**  
&emsp;&emsp;**注1:** 这里要指出的是,一个函数的原函数是与区间有关的,例如,在$(-\infty,0)$内,由于$[\ln(-x)]'=-\frac{1}{x}$,故$\ln(-x)$是$-\frac{1}{x}$的原函数;而在$(0,+\infty)$内,由于$(\ln x)'=\frac{1}{x}$,故$\ln x$是$\frac{1}{x}$的原函数.  
&emsp;&emsp;**注2:** 我们知道初等函数在其定义区间内是连续的,因此它的元杉树一定存在.但要指出,初等函数在其定义区间内的原函数不一定是初等函数,例如:  
$$y=e^{-x^2},y=\frac{\sin x}{x},y=\frac{1}{\ln x},y=\frac{1}{\sqrt{1+x^4}}, \cdots$$  
&emsp;&emsp;**定义5.1.2** 函数$f(x)$的全体原函数称为$f(x)$的不定积分,记作:  
$$\int f(x)dx$$  
其中$\int$称为**积分号**,$f(x)$称为**被积函数**,$f(x)dx$称为**被积表达式**,$x$称为**积分变量**,$dx$称为**积分变元**.  
$$\int f(x)dx=F(x)+C\quad(C为任意常数)\tag{5.1.1}$$  
&emsp;&emsp;**定理5.1.1**  对不定积分运算有下列两个基本等式:  
&emsp;&emsp;(1)$[\int f(x)dx]'=f(x)或d[\int f(x)dx]=f(x)dx$,
&emsp;&emsp;(2)$\int F'(x)dx=F(x)+C或\int dF(x)=F(x)+C$.

### 5.1.2 基本积分表
1. $\int x^\mu dx=\frac{x^{\mu+1}}{\mu+1}+C(\mu为常数,\mu\neq-1),特别地\int dx=x+C$;  
2. $\int\frac{dx}{x}=\ln |x|+C$;  
3. $\int \frac{dx}{1+x^2}=\arctan x+C$;  
4. $\int \frac{dx}{1-x^2}=\arcsin x+C$;  
5. $\int \cos xdx=\sin x+C$  
6. $\int \sin xdx=-\cos x+C$;
7. $\int \frac{dx}{\cos^2x}=\int \sec^2 xdx=\tan x+C$;
8. $\int \frac{dx}{\sin^2x}=\int \csc^2xdx=-\cot x+C$;
9. $\int \sec x\tan xdx=\sec x+C$;
10. $\int \csc x \cot x dx=-\csc x+C$;
11. $\int e^xdx=e^x+C$;
12. $\int a^xdx=\frac{a^x}{\ln a}+C(a>0,a\neq1)$

### 5.1.3 不定积分的性质
1. 函数的和的不定积分等于各个函数的不定积分的和,即:  
$$\int [f(x) + g(x)]dx=\int f(x)dx+\int g(x)dx$$
推广到多个函数,即:
$$\int[f_1(x)+f_2(x)+\cdots+f_n(x)]dx=\int f_1(x)dx + \int f_2(x)dx+\cdots+\int f_n(x)dx$$
用$\sum$的形式写出为:  
$$\int[\sum_{k=1}^nf_k(x)]dx=\sum_{k=1}^n\int f_k(x)dx$$
2. 被积函数中不为零的常数因子可以提到积分号外面来,即:  
$$\int kf(x)dx=k\int f(x)dx\quad(k为常数,且k\neq0)\tag{5.1.3}$$
