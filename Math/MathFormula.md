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
|3个+       椭球面
|2+1-|	    单叶双曲面
|2-1+|	    双叶双曲面
|2+10|	    椭圆柱面
|1+1-10|	双曲柱面|


# 双叶双曲面

* $\frac{x^2}{a^2}-\frac{y^2}{b^2}-\frac{z^2}{c^2}=1$

# 施密特正交化

$$

\begin{aligned}

&\beta _1 = \alpha _1 \\

&\beta _2 = \alpha _2 - \frac{(\alpha _2,\beta _1)}{(\beta _1,\beta _1)}\beta _1 \\
\end{aligned}

$$
# 行列式

* 交换两行行列式变号
* a倍的一行加到另一行上值不变
* 一行乘a等于行列式乘a

# 秩

* 一个矩阵的秩等于其列向量组中线性无关的列向量的最大数量
* 矩阵的秩等于其列空间的维度等于行空间维度（与第一条类似）
* 满秩则可逆
* r阶子式不为零，r+1阶子式全为零
* 非零矩阵秩一定大于等于1
* 增广矩阵秩一定不小于原矩阵秩
* $r(A+B)<=r(A)+r(B)$
* $r(AB)<=\min (r(A),r(B))$
* $r(kA)=r(A)$
* n阶方阵A和B，AB=0则$r(A)+r(B)<=n$，因为B的列空间被A映射到零空间，所以B的列空间的维度不能超过零空间的维度。则,$r(A) + r(B) ≤ n + (n - r(A)) = 2n - r(A) ≤ n$

# 秩-零度定理

* $r(A)+r(B)<=n$，列空间维度加零空间维度等于列数
* 列空间：矩阵的列空间是由矩阵的列向量所张成的向量空间。（它是矩阵的所有列向量线性组合所构成的空间。但我们知道起作用的向量是那些线性无关的向量）---->列空间的维度等于矩阵的秩（Rank）表示线性独立的列向量的最大数量。
* 零空间（Null Space）：矩阵的零空间是由使矩阵乘以这些向量得到零向量的所有向量组成的向量空间。Ax=0的解集就是零空间。

# 特征值

* 一个n阶方阵一定有n个特征值，但特征值可以是重根
* 属于不同特征值的特征向量一定线性无关
* 特征值相乘等于行列式
* 特征值相加等于矩阵迹等于矩阵主对角线和
* 矩阵可逆的充要条件是特征值全不为零
* $\lambda 是 A 的特征值，f(\lambda) 是 f(A) 的特征值$
![Alt text](image.png)

# 相似矩阵

* 相似矩阵的 行列式，秩，可逆性，特征值相同。
* 矩阵相似于对角化充要条件：有N个线性无关的特征向量

# 可逆矩阵

* 矩阵的特征向量是线性无关的
* 矩阵的特征值都不为零
* 矩阵的特征向量可以用来构建矩阵的逆 A⁻¹ = P * Λ⁻¹ * P⁻¹
* $AA^*=|A|E$

# 实对称矩阵

* 实对称矩阵对应于不同特征值的特征向量一定正交
* 实对称矩阵一定可以相似于对角型，也就是说一定有N个线性无关的特征向量

# 正交矩阵

* 列向量是单位向量且两两正交
* $Q^T Q = E$
* 正交矩阵的行列式的绝对值为 1
* 单位矩阵也是正交矩阵
* 交换两行的单位矩阵也是正交矩阵

# 正定矩阵

* 正定矩阵一定是实对称矩阵
* 特征值决定它的正定性
* 所有的特征值都是正数。
* 所有的主子式（行列式去掉某些行和列后的子矩阵的行列式）都是正数。
* 矩阵的各个主子式都是正数，即矩阵的顺序从1到 n 的所有主子式都是正数。
* $\forall x != 0,必有x^TAx>0$

# 正定性验证

*  A是正定矩阵，当且仅当 A 的 n 个顺序主子式(严格)为正。
*  A是正定矩阵，当且仅当 A 的 n 个顺序主子式以如下方式交替出现：$|A_1|<0,|A_2|>0,|A_3|<0···$

# 合同矩阵

* $A = P^T B P$
* 两个矩阵有相同的正惯性指数和负惯性指数
* 合同的充要条件是 具有相同的 正负惯性指数
* 合同是一种特殊的等价

# 等价矩阵

* 一个矩阵经过一系列初等变换
* 具有相同的秩，相同的行空间。
* 不同的特征值和特征向量
* 不同的行列式

# 齐次方程解的存在

* Ax=0有非零解，|A|=0，A不满秩
* Ax=0只有零解，|A|!=0，A满秩
* 值得注意的是Ax=0其中的x不是我们简单的一个值，而是一个个向量，这些向量可以组成矩阵例如 AB=0
* 

# 分块矩阵

* 加，减，乘，数乘，与自己杜撰的算法一致
* 转置对大矩阵转置块矩阵也转置
* 求逆
$$
\begin{pmatrix}
A & 0 \\
0 & B \\
\end{pmatrix}^{-1} = 
\begin{pmatrix}
    A^{-1} & 0 \\
    0 & B^{-1}
\end{pmatrix} \\

\begin{pmatrix}
0 & A \\
B & 0 \\
\end{pmatrix}^{-1} = 
\begin{pmatrix}
    0 & B^{-1} \\
    A^{-1} & 0
\end{pmatrix} \\

\begin{pmatrix}
A & 0 \\
E & B \\
\end{pmatrix}^{-1} = 
\begin{pmatrix}
    A^{-1} & 0 \\
    0 & B^{-1}
\end{pmatrix} \\

\begin{pmatrix}
    A & E \\
    0 & B \\
\end{pmatrix}^{-1} =
\begin{pmatrix}
    A^{-1} & -A^{-1}EB^{-1} \\
    0 & B^{-1}
\end{pmatrix} \\

\begin{pmatrix}
    A & \\
      & B & \\
      &   & C\\
\end{pmatrix}^{-1} =
\begin{pmatrix}
    A^{-1} & \\
      & B^{-1} & \\
      &   & C^{-1} \\
\end{pmatrix}
$$

# 伴随矩阵

* 代数余子式行按列排
* $A^{-1}=\frac{A^*}{|A|}$

# 二次型

二次型多种表达形式：
* 若$f(x)=x^TAx$ 其中x为列向量，A为实对称矩阵
* A被称为f(x)的矩阵
* 还可以写成多项式形式：$a_{11}x_{1}^2+a_{12}x_1x_2+···+a_{nn}x_n^2$
* 当多项式只有平方项$a_{11}x_{1}^2+···+a_{nn}x_n^2$则成为标准型

性质：
* 二次型的标准型不唯一，规范性唯一
* 二次型具有相同的规范性：正惯性指数相等，负惯性指数相等
* 有$P^TAP=D，D为标准型，则C^TAC=diag(1···-1···0)其中C=PM，M=diag(\frac{1}{\sqrt{k_1}},\frac{1}{\sqrt{k_2}},\frac{1}{\sqrt{k_3}},···)$
* 当$f(x)=2x_1x_2+2x_1x_3-6x_2x_3$这样只有交叉项时可用$x_1=z_1+z_2,x_2=z_1-z_2,x_3=z_3,x_4=z_4···$替换然后配方

* 使用矩阵合同变换法化标准型：通过f(x)的各项系数除2，放到对应下标位置得到矩阵A，通过$
\begin{pmatrix}
    A\\
    E
\end{pmatrix}
$列变换和行变换交替对应进行。直到A变成对角型D，E变成P。则$P^TAP=D$


# 特别理解

* $\alpha 是非零列向量则 \alpha \alpha^T一定是非零对称矩阵$
* $A^3=0说明A^3的特征值为0$，矩阵经过一定的运算特征值也做同样的运算，所以A的特征值也是0
* 变限定积分与x的无穷小比较。$\int ^{g(x)} _0f(t)dt$,f(x)是x的n阶无穷小，g(x)是x的m阶无穷小。则原式是x的m(n+1)阶无穷小
* 函数具有一阶连续导数那么原函数平滑且连续
* 向量可以线性表出通常可以理解为方程组有解
* 对称定积分在加法中如果有奇函数则该项为0


# 
# 草稿
$$
\begin{aligned}
    \lim _{d->0} \frac{f(a+d)-f(a-d)}{d}存在但是不能推出f'(a)存在，f(x)可能在x=a处无定义
\end{aligned}

$$

$$
\int rd \theta \int \sqrt{r^2+2'^2}d\theta

$$