### **第二章 插值**

**多项式插值**： $P(x)=a_0+a_1x+\dots+a_nx^n $

其系数由以下线性方程组确定：

$$
\begin{bmatrix}
1 & x_0 & x_0^2 & \dots & x_0^n \\
1 & x_1 & x_1^2 & \dots & x_1^n \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
1 & x_n & x_n^2 & \dots & x_n^n \\
\end{bmatrix}
\begin{bmatrix}
a_0 \\ a_1 \\ a_2 \\ \vdots \\ a_n
\end{bmatrix}=
\begin{bmatrix}
f(x_0) \\ f(x_1) \\ f(x_2) \\ \vdots \\ f(x_n)
\end{bmatrix}
$$

$x_i$互异 -> $\mathrm{det}\boldsymbol{A}\not=0$ -> 线性方程解唯一 -> $P(x)$存在则唯一

**拉格朗日插值**： $L_n(x)=\displaystyle \sum_{k=0}^{n}y_kl_k(x) $

其中 $l_k(x)=\displaystyle \frac{\omega_{n+1}(x)}{(x-x_k)\omega_{n+1}'(x_k)} $

$\omega_{n+1}(x)=(x-x_0)(x-x_1)\dots(x-x_n) $

$\omega_{n+1}^{'}(x_k)=(x_k-x_0)(x_k-x_1)\dots(x_k-x_{k-1})(x_k-x_{k+1})\dots(x_k-x_n) $

余项： $R_n(x)=\displaystyle \frac{f^{(n+1)}(\xi)}{(n+1)!}\omega_{n+1}(x),\xi \in (a, b) $​

截断误差限：$|R_n(x)|\le \frac{M_{n+1}}{(n+1)!}|\omega_{n+1}(x)|$, 其中$M_{n+1}=\max_{a \leq x \leq b} \left| f^{(n+1)}(x) \right|$

**一阶均差**： $f[x_0, x_1]=\displaystyle \frac{f(x_1)-f(x_0)}{x_1-x_0} $

**二阶均差**： $f[x_0, x_1, x_2]=\displaystyle \frac{f[x_1,x_2]-f[x_0,x_1]}{x_2-x_0} $

**k 阶均差**： $f[x_0, x_1,\dots,  x_k]=\displaystyle \frac{f[x_1,x_2, \dots,x_k]-f[x_0,\dots,x_{k-1}]}{x_k-x_0} $

$f[x_0,x_1, \dots, x_k]=\displaystyle \sum_{j=0}^{k}\frac{f(x_j)}{(x_j-x_0)\dots(x_j-x_{j-1})(x_j-x_{j+1})\dots(x_j-x_k)} $

$f[x_0, x_1, \dots, x_n]=\displaystyle \frac{f^{(n)}(\xi)}{n!},\xi\in[a, b] $

**牛顿插值公式**： $N_n(x)=a_0+a_1(x-x_0)+a_2(x-x_0)(x-x_1)+\dots+a_n(x-x_0)\dots(x-x_n) $

其中 $a_i=f[x_0, x_1, \dots, x_i] $

余项： $R_n(x)=f[x,x_0, \dots, x_n]\cdot(x-x_0)\cdots(x-x_n) $

**重节点均差**： $f[x_0, x_0]=\displaystyle \lim_{x_1\rightarrow x_0}[x_0, x_1]=f'(x_0) $

**n 阶重节点均差**： $f[x_0, x_0, \dots, x_0]=\displaystyle \lim_{x_i\rightarrow x_0}f[x_0, x_1, \dots, x_n]=\frac{1}{n!}f^{(n)}(x_0) $

**泰勒插值多项式**： $P_n(x)=\displaystyle f(x_0)+f'(x_0)(x-x_0)+\dots+\frac{f^{(n)}(x_0)}{n!}(x-x_0)^n $

余项： $R_n(x)=\displaystyle \frac {f^{(n+1)}(\xi)}{(n+1)!}(x-x_0)^{n+1}, \xi\in(a, b) $，也与之前余项在 $x_i\rightarrow x_0 $ 时的结果一致。

**三次埃尔米特插值多项式**：

已知 $f(x_0), f(x_1), f(x_2), f'(x_1) $

则 $P(x)=f(x_0)+f[x_0, x_1]\cdot(x-x_0)+f[x_0, x_1, x_2]\cdot(x-x_0)(x-x_1)+A(x-x_0)(x-x_1)(x-x_2) $

其中 $A=\displaystyle \frac{f'(x_1)-f[x_0,x_1]-(x_1-x_0)f[x_0,x_1,x_2]}{(x_1-x_0)(x_1-x_2)} $

余项： $R(x)=\displaystyle \frac{1}{4!}f^{(4)}(\xi)(x-x_0)(x-x_1)^2(x-x_2)$，$\xi$ 在 $x_0, x_1, x_2$ 限定的范围内

**分段线性插值**： $I_h(x)=\displaystyle \frac{x-x_{k+1}}{x_k-x_{k+1}}f(x_k)+\frac{x-x_k}{x_{k+1}-x_k}f(x_{k+1}) $, 其中 $x_k\leqslant x\leqslant x_{k+1}, k=0, 1,\dots, n-1 $

**三次样条插值函数**： $S_i(x)=a_i(x-x_i)^3+b_i(x-x_i)^2+c_I(x-x_i)+d_i, x\in [x_i, x_{i+1}] $

记 $h$ 为小区间长度， $M_i=S''(x_i), y_i=f(x_i)$ ，在区间 $[x_i, x_{i+1}]$ 上的 $S(x)$ 为

- $a_i=\displaystyle \frac{M_{i+1}-M_i}{6h} $
- $b_i=\displaystyle \frac{M_i}{2} $
- $c_i=\displaystyle \frac{y_{i+1}-y_i}{h}-\frac{(M_{i+1}+2M_i)h}{6} $
- $d_i=y_i $

其中 $M_i$ 根据条件解线性方程组得到： $M_i+4M_{i+1}+M_{i+2}=\displaystyle \frac{6(y_i-2y_{i+1}+y\_{i+2})}{h^2}, 1\leqslant i\leqslant n-2 $
