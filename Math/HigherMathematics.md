# 俩个重要极限

* $$\lim _{x->0} \frac{\sin x}{x} = 1~~~~\lim _{x->\infty}(1+\frac{1}{x})^x = e $$

# 泰勒&等价无穷小

$$
\begin{aligned}
&泰勒公式 \\
&\ln(1+x)=x-\frac{x^2}{2}+\frac{x^3}{3}-\frac{x^4}{4}+(-1)^n\frac{x^{n+1}}{n+1}+o(x^{n+1}) \\
&(1+x)^a = 1+ax+\frac{a(a-1)}{2!}x^2+···+\frac{a(a-1)···(a-n+1)}{n!}x^n+o(x^n) \\
&\tan x = x + \frac{1}{3}x^3+··· \\
&e^x = 1+x+\frac{x^2}{2!}+\frac{x^3}{3!}+···+\frac{x^n}{n!}+o(x^n) \\
&\sin x = x - \frac{x^3}{3!}+\frac{x^5}{5!}+···+(-1)^n\frac{x^{2n+1}}{(2n+1)!}+o(x^{2n+1}) \\
&\cos x = 1 -\frac{x^2}{2!}+\frac{x^4}{4!}+···+ (-1)^n\frac{x^{2n}}{(2n)!}+o(x^{2n})
\end{aligned}

$$
* 皮亚诺余项：局部，一个点，o()表示
* 拉格朗日余项：整体，一个区间，$R_n(x)=\frac{f^{n+1}(\xi)}{(n+1)!}(x-x_0)^{n+1}$

$$
\begin{aligned}
    &\ln (1+x) \sim x \\
    &e^x-1 \sim x \\
    &\log _a(1+x) \sim \frac{x}{\ln a} \\
    &(1+x)^a-1 \sim ax \\
    &1-(1-x)^a \sim ax \\
    &x-\arctan x \sim \frac{1}{3}x^3 \sim \tan x-x \\
    &x-\sin x \sim \frac{1}{6}x^3 \sim \arcsin x-x \\
    &1-\cos x \sim \frac{1}{2}x^2 \sim \tan x-\sin x \\
    &x-\ln (1+x)\sim \frac{1}{2}x^2
\end{aligned}
$$
 
# 积分

$$
\begin{aligned}
    &\int \ln x dx = x\ln x-x+C \\
    &\int a^x \ln a dx = a^x+C \\
    &\int \frac{1}{x \ln a}dx = \log _a x+C \\
    &\int \sec ^2 xdx = \tan x+C \\
    &\int -\csc ^2 xdx = \cot x+C \\
    &\int \tan x dx = -\ln |cosx|+C \\
    &\int \cot x dx = \ln |sinx|+C \\
    &\int \sec x \tan x dx = \sec x+C \\
    &\int -\csc x \cot xdx = \csc x+C\\
    &\int \sec x dx = \ln |secx + tanx|+C \\
    &\int \csc x dx = \ln |cscx - cotx|+C \\
    &\int \frac{dx}{a^2+x^2} = \frac{1}{a} \arctan \frac{x}{a}+C \\
    &\int \frac{dx}{x^2-a^2} = \frac{1}{2a}\ln |\frac{x-a}{x+a}|+C \\
    &\int \frac{dx}{\sqrt{a^2-x^2}} = \arcsin \frac{x}{a}+C \\
    &\int \frac{dx}{\sqrt{a^2+x^2}} = \ln (x+\sqrt{x^2+a^2})+C \\
    &\int \frac{dx}{\sqrt{x^2-a^2}} = \ln |x-\sqrt{x^2-a^2}|+C \\

\end{aligned}
$$
$$
\begin{aligned}
    &\int_0^\frac{\pi}{2}\cos^n(x)dx=\int_0^\frac{\pi}{2}\sin^n(x)dx\\
    &=\frac{n-1}{n}\cdot \frac{n-3}{n-2}\cdot ...\cdot \frac{4}{5}\cdot \frac{2}{3}  (n为奇数)\\
    &=\frac{n-1}{n}\cdot \frac{n-3}{n-2}\cdot ...\cdot \frac{3}{4} \cdot \frac{1}{2} \cdot \frac{\pi}{2}(n为偶数)
\end{aligned}
$$

# 积分注意事项：
* $\frac{dp}{p}=\frac{dx}{x}左右积分就写出\ln p = \ln x +\ln c$
* $弧微分L=∫ \sqrt{r^2+(\frac{dr}{dθ})^2}dθ$

   - 当积分中包含 $\sqrt{a^2 - x^2}$ 时,常见的换元：$x = a \cos θ$ 或 $x = a \sin θ$，然后使用三角恒等式来替换。

   - 当积分中包含 $\sqrt{x^2 + a^2}$常见的换元：$x = a \tan θ$，然后使用三角恒等式来替换。



# 积分中值定理

* $f(\xi) =\frac{1}{a-b} \int ^a_bf(x)dx$

# 极限类型

* $1^\infty$ 型 化为 $\lim _{x->\infty}(1+f(x))^{g(x)}$ 求$\lim _{x->\infty}g(x)f(x)$ 结果$e^{\lim _{x->\infty}g(x)f(x)}$
* 极限时可以算出来的非零因数就算出来，算出含有x的表达式也可以只要不是零
* 遇到$f(g(x))-f(w(x))$这样的表达式可以使用拉格朗日中值定理$f'(c) = (f(b)-f(a))/(b-a)$
* 
# 微分方程

一阶线性齐次微分方程 $y'+P(x)y=0$

$$
\begin{aligned}
    y=Ce^{-\int P(x) dx}
\end{aligned}
$$

一阶线性非齐次微分方程 $y'+P(x)y=Q(x)$

$$
\begin{aligned}
    y=e^{-\int P(x) dx}(C+\int Q(x) e^{\int P(x) dx}dx)
\end{aligned}
$$

# 多元函数极值
$$
f(x,y) \\
\begin{cases}
    f'_x(x,y)=0 \\
    f'_y(x,y)=0
\end{cases} \\
AC-B>0 \\
A=f'_{xx},B=f'_{xy},C=f'_{yx} \\
A>0极小值 \\
A<0极大值 \\
注意：AC-B<0 说明不是极值，>0无法判断
$$
# 平面&旋转曲面

* $Ax+By+Cz+D=0$,平面的法线垂直于哪个坐标轴，哪个坐标轴对应的系数就为0，平面过原点D=0.
* f(x,y)=0。绕x旋转，$y=\pm \sqrt{y^2+z^2}$，带入后如果$\pm还在就平方消掉$


| 正负惯性指数	| 曲面 |
|--------------|-----|
|3个+|       椭球面|
|2+1-|	    单叶双曲面|
|2-1+|	    双叶双曲面|
|2+10|	    椭圆柱面|
|1+1-10|	双曲柱面|


# 双叶双曲面

* $\frac{x^2}{a^2}-\frac{y^2}{b^2}-\frac{z^2}{c^2}=1$


# 
# 草稿
$$
\begin{aligned}
    \lim _{d->0} \frac{f(a+d)-f(a-d)}{d}存在但是不能推出f'(a)存在，f(x)可能在x=a处无定义
\end{aligned}

$$

$
f(x_1,x_2,x_3,x_4)=2x_1x_2-6x_1x_3-6x_2x_4+2x_3x_4
$用正交变换化二次型为标准型