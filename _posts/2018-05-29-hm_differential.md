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

#### 4.2 未定式极限的计算(罗必塔法则)

##### 定义:
&ensp;&ensp;函数$f(x)$与$g(x)$同时趋于零或同时趋于无穷大时,极限$lim\frac{f(x)}{g(x)}$可能存在,也可能不存在.通常,我们称这种极限形式为**未定式**,并记作$\frac{0}{0}$,或者$\frac{\infty}{\infty}$  
##### 4.2.1 两个无穷小之比的极限($\frac{0}{0}$型)
&ensp;&ensp;1. $x\rightarrow x_0$的情形  
&ensp;&ensp;**定理4.2.1** 如果函数$f(x)$与$g(x)$满足:  
&ensp;&ensp;(1) 当$x\rightarrow x_0$时,函数$f(x),g(x)$均趋于零;  
&ensp;&ensp;(2) 两个函数在$x_0$的去心邻域内可导,且$g'(x)\neq0$;  
&ensp;&ensp;(3) 两个函数的导数之比的极限$\lim_{x\rightarrow x_0}\frac{f'(x)}{g'(x)}$存在(或无穷大),  
则  
$$\lim_{x\rightarrow x_0}\frac{f(x)}{g(x)}=\lim_{x\rightarrow x_0}\frac{f'(x)}{g'(x)}\tag{}$$  
&ensp;&ensp;2. $x\rightarrow\infty$的情形  
&ensp;&ensp;**定理4.2.1** 如果函数$f(x)$与$g(x)$满足:  
&ensp;&ensp;(1) 在区间$(a,+\infty)$内连续,且$\lim_{x\rightarrow+\infty}f(x)=\lim_{x\rightarrow+\infty}g(x)=0$;  
&ensp;&ensp;(2) 在区间$(a,+\infty)$内可导,且$g'(x)\neq0$;  
&ensp;&ensp;(3) $\lim_{x\rightarrow+\infty}\frac{f'(x)}{g'(x)}$存在(或无穷大)  
则  
$$\lim_{x\rightarrow+\infty}\frac{f(x)}{g(x)}=\lim_{x\rightarrow+\infty}\frac{f'(x)}{g'(x)}\tag{}$$  

##### 4.2.2 两个无穷大之比的极限($\frac{\infty}{\infty}$型)
&ensp;&ensp;1. $x\rightarrow x_0$的情形  
&ensp;&ensp;**定理4.2.3** 如果函数$f(x)$与$g(x)$满足:  
&ensp;&ensp;(1) 两个函数在$x_0$的某个去心邻域内有定义,且$\lim_{x\rightarrow x_0}(fx)=\infty,\lim_{x\rightarrow x_0}g(x)=\infty$;  
&ensp;&ensp;(2) 两个函数在上述去心邻域内可导,且$g'(x)\neq0$;  
&ensp;&ensp;(3) $\lim_{x\rightarrow x_0}\frac{f'(x)}{g'(x)}$存在(或无穷大)  
则  
$$\lim_{x\rightarrow x_0}\frac{f(x)}{g(x)}=\lim_{x\rightarrow x_0}\frac{f'(x)}{g'(x)}\tag{}$$    
&ensp;&ensp;2. $x\rightarrow\infty$的情形  
&ensp;&ensp;**定理4.2.4** 如果函数$f(x)$与$g(x)$满足:  
&ensp;&ensp;(1) 两个函数当$x>a>0$时有定义,且当$x\rightarrow+\infty$时,都趋向于无穷大;  
&ensp;&ensp;(2) 两个函数的导数当$x>a>0$存在时,且$g'(x)\neq0$;  
&ensp;&ensp;(3) $\lim_{x\rightarrow+\infty}\frac{f'(x)}{g'(x)}$存在(或无穷大)  
则  
$$\lim_{x\rightarrow+\infty}\frac{f(x)}{g(x)}=\lim_{x\rightarrow+\infty}\frac{f'(x)}{g'(x)}\tag{}$$  

#### 4.3 泰勒公式  
#### 4.3.1 一阶泰勒公式  
&ensp;&ensp;**定理 4.3.1** 设$f(x)$在包含点$x_0$的开区间$(a,b)$内有二阶导数,则当$x\in(a,b)$时,函数$f(x)$可表示为  
$$f(x)=f(x_0)+f'(x_0)(x-x_0)+\frac{f''(\xi)'}{2!}(x-x_0)^2\tag{4.3.1}$$  
$\xi$是位于$x_0$与$x$之间某一点.并称式(4.3.1)为$f(x)$在$x_0$处的**一阶泰勒公式**,之中最后一项记作  
$$R_1(\xi,x)=\frac{f''(\xi)}{2!}(x-x_0)^2\tag{}$$  
也常将$R_1(\xi,x$简记为$R_1(x)$,并称他是一阶泰勒公式的**拉格朗日余项**.  
&ensp;&ensp;**推论** 若函数$f(x)$在包含原来点$x_0=0$的开区间$(a,b)$内有二阶导师,则有  
$$f(x)=f(0)+f'(0)x+\frac{f''(\xi)}{x!}x^2\tag{4.3.6}$$    
其中$\xi$在$x_0=0$与$x$之间.有时也记作$\xi=\theta x,0<\theta<1$.称式(4.3.6)为$f(x)$的一阶麦克劳林(Maclaurin)公式  

#### 4.3.2 $n$阶泰勒公式  

&ensp;&ensp;**定理 4.3.2** 设函数$f(x)$在包含点$x_0$的开区间$(a,b)$内有$n+1$阶导数,则当$x\in(a,b)$时,函数$f(x)$可表示为  
$$f(x)=f(x_0)+f'(x_0)(x-x_0)+\frac{f''(\xi)'}{2!}(x-x_0)^2+\cdots+\frac{f^{(n)}(x_0)}{n!}(x-x_0)^n+R_n(x)\tag{4.3.8}$$  

其中$R_n(x)=\frac{f^{(n+1)}(\xi)}{(n+1)!}(x-x_0)^{n+1}$,成为拉格朗日余项,$\xi$是位于$x_0$与$x$之间某一点,并称式(4.3.8)为带有拉格朗日余项的 **$n$阶泰勒公式**.因为当$x\rightarrow x_0$时,余项$R_n(x)$是关于$(x-x_0)^n$的高阶无穷小,谷余项有可以表示为$R_n(x)=o(x-x_0)^n$,这种形式的余项称为皮亚诺(Peano)余项.  

&ensp;&ensp;**推论** 若函数$f(x)$在包含原来点$x_0=0$的开区间$(a,b)$内有直到$n+1$阶导师,则有任意的$x\in(a,b)$,有麦克劳林公式  
$$f(x)=f(0)+\frac{f'(0)}{1!}x+\frac{f''(0)}{2!}x^2+\cdots+\frac{f^{(n)}(0)}{n!}x^n+R_n(x)\tag{4.3.9}$$  
其中$R_n(x)=\frac{f^{(n+1)}(\xi)}{(n+1)!}x^{n+1}$,$\xi$在$x_0$与$x$之间,或$R_n(x)=\frac{f^{(n+1)}(\theta x)}{(n+1)!}x^{n+1},0<\theta<1$称其为拉格朗日余项,并且也有$R_n(x)=o(x^n),(x\rightarrow 0)$,称其为皮亚诺余项.  


#### 4.4 函数的单调性与极值  

##### 4.4.1 函数单调性的判定法及其应用  

&ensp;&ensp;**1. 函数单调性的判定法**  
&ensp;&ensp; **定理 4.4.1** 设函数$y=f(x)$在区间$[a,b]$上连续,在$(a,b)$内可导,则有  
若在$(a,b)$内$f'(x)>0$(或$f(x)<0$),则函数$y=f(x)$在区间$[a,b]$上单调增加(或减少)  
##### 4.4.2 函数的极值与最大最小值问题  
&ensp;&ensp;1. 函数的极值及其求法  
&ensp;&ensp;**定义 4.4.1** 设函数$f(x)$在区间$(a,b)$内有定义,如果存在点$x_0$的一个淋雨,对于该邻域内的任何点$x$,除点$x_0$外,有$f(x)<f(x_0)$(或$f(x)>f(x_0)$)均成立,就称$f(x_0)$是函数$f(x)$的一个极大值(或极小值).极大值与极小值统称函数的极值,使函数取得极值的点$x_0$称为极值点.  
&ensp;&ensp;**定理 4.4.1** (必要条件)设函数$f(x)$在点$x_0$处可导,且在$x_0$处取得极值,则该函数在$x_0$处的导数$f'(x_0)=0$,即在点$(x_0,f(x_0))$处,函数取消的切线平行于$x$轴.  

&ensp;&ensp;使得导数$f'(x)$为零的点$x_0$称函数$y=f(x)$的**驻点**  

&ensp;&ensp;**定理 4.4.2** (由单调性判定极值的第一充分条件) 设函数$f(x)$在点$x_0$的一个邻域内可导,且$x_0$是驻点,即$f'(x_0)=0$.  
&ensp;&ensp;**定理 4.4.3** (由单调性判定极值的第二充分条件) 设函数$f(x)$在点$x_0$处具有二阶导数,且$f'(x_0)=0,f''(x_0)\neq0$,则当$f''(x_0)<0$(或$f''(x_0)>0$)时,函数$f(x)$在$x_0$处取得极大值(或极小值).  

