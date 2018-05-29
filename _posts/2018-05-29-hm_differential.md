---
layout: post
title: 高等数学 微分中值定理与导数的应用
date: 2018-05-29 11:24:00.000000000 +9:00
tag: Math
---

## 4.微分中值定理与导数应用

#### 4.1 微分中值定理

##### 4.1.1 罗尔定理

**定理4.1.1** 设函数$y=f(x)$满足下列条件:  
&ensp;&ensp;(1) 在闭区间$[a,b]$上连续,  
&ensp;&ensp;(2) 在开区间$(a,b)$内可导,
&ensp;&ensp;(3) 在区间端点的函数值相等,即$f(a)=f(b)$,  
则在开区间$(a,b)$内,至少存在一点$\xi$是的函数$f(x)$在该店的导数等于零,既有  
$$f'(\xi)=0\quad(a<\xi<b)\tag{}$$  

**几何意义**  
&ensp;&ensp;(1) 曲线$y=f(x)$在闭区间$[a,b]$上是一条连续的曲弧线;  
&ensp;&ensp;(2) 除端点外的开区间内每一个点处,都有不垂直于$x$轴的切线;  
&ensp;&ensp;(3) 曲线的两个端点处有相同的纵坐标,定理的结论等价于在曲线弧上至少存在一点$(\xi,f(\xi))$,使得过该点所做的切线平行于$x$轴.

#### 4.1.2 拉格朗日中值定理及简单应用

##### &ensp;&ensp;1. 拉格朗日中值定理
&ensp;&ensp;**定理4.1.2** 如果函数$f(x)$满足:  
&ensp;&ensp;(1) 在闭区间$[a,b]$上连续;
&ensp;&ensp;(2) 在开区间$(a,b)$内可导;  
则在开区间$(a,b)$内至少存在一点$\xi$,使得:  
$$f'(\xi)=\frac{f(b)-f(a)}{b-a}\quad(a<\xi<b))\tag{}$$  
或者
$$f(b)-f(a)=f'(\xi)(b-a)\quad(a<\xi<b)\tag{}$$    
##### &ensp;&ensp;2. 用拉格朗日中值定理证明有关不等式或恒等式  
&ensp;&ensp;**推论**  
&ensp;&ensp; 1. 如果函数$f(x)$在$(a,b)$内可到,切在该区间内$f'(x)\equiv0$,则在$(a,b)$内$f(x)$为一常数  
&ensp;&ensp; 2. 在$(a,b)$内任去两点$x_1, x_2\quad(x_1<x_2)$,有:  
$$f(x_2)-f(x_1)=f'(\xi)(x_2-x_1)\quad(\xi\in(x_1,x_2)\subset(a,b))\tag{}$$    
因为一直$f'(x)\equiv0$在$(a,b)$内成立,于是有$f'(\xi)\equiv0$,所以以上等式变为:  
$$f(x_2)-f(x_1)=0\tag{}$$    
即
$$f(x_1)=f(x_2 )\tag{}$$  

##### &ensp;&ensp;3. 由拉格朗日中值定理导出的有限增量公式
&ensp;&ensp; 拉格朗日中值定理还可以变换为另一个形式:设在开区间$(a,b)$内有任意两个点$x$和$x+\Delta x$($\Delta x$可负、可正),设$f(x)$在$(a,b)$内可导,若$\Delta x>0$,经$f(x)$在区间$[x,x+\Delta x]$上使用拉格朗日定理有  
$$f(x+\Delta x)-f(x)=f'(\xi)[(x+\Delta x)-x]\tag{}$$   
其中$\xi\in(x,x+\Delta x)$,将$\xi$写成$x+\frac{\xi-x}{\Delta x}\cdot\Delta x=x+\theta\cdot\Delta x$,这里$\theta=\frac{\xi-x}{\Delta x}$是个真分数,即$0<\theta<1$,于是上面式就变成
$$f(x+\Delta x)-f(x)=f'(x+\theta\cdot\Delta x)\cdot\Delta x\tag{4.1.6}$$  
&ensp;&ensp;若$\Delta x<0$,只要在区间$[x+\Delta x,x]$上使用拉格朗日中值定理,同样可得上式,我们常将上式成为**有限增量公式**.这是由于上式的左边恰是函数的增量$\Delta y$,他等于函数在区间$(x,x+\Delta x)$内(或区间$(x+\Delta x,x)$内)某一点的导数与自变量的增量$\Delta x$的乘积,即  
$$\Delta y=f'(x+\theta\cdot\Delta x)\cdot\Delta x\tag{}$$    
&ensp;&ensp;如果在式(4.1.6)中,令$x=x_0$带入,有  
$$f(x_0+\Delta x)-f(x_0)=f'(x_0+\theta\cdot\Delta x)\cdot\Delta x\tag{}$$  
在上式中,将$x_0+\Delta x=x$看成在区间$(a,b)$内的动点,并且移项后可得到:  
$$f(x)=f(x_0)+f'(x_0+\theta\cdot(x-x_0))\cdot(x-x_0)\tag{4.1.7}$$  
其中$x_0+\theta\cdot(x-x_0)=\xi$是位于$x_0$与$x$之间的某一点.式(4.1.7)就是我们以后将要研究的泰勒中值公式的一个特殊情形.
#### 4.1.3 柯西中值定理  
&ensp;&ensp;**定理 4.1.3** 如果函数$f(x)$与$g(x)$满足:  
&ensp;&ensp;(1) 在闭区间$[a,b]$上连续;  
&ensp;&ensp;(2) 在开区间$(a,b)$内可导,且$g'(x)\neq0,x\in(a,b)$;  
则在区间$(a,b)$内至少存在一点$\xi$,使得  
$$\frac{f(b)-f(a)}{g(b)-g(a)}=\frac{f'(\xi)}{g'(\xi)}\quad\quad(a<\xi<b)\tag{}$$  
