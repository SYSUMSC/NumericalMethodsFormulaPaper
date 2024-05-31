## **第三章 逼近与拟合**

**范数**：设 $S$ 是实数域上的线性空间， $x\in S$ ，如果存在值域为实数域的函数 $\Vert\cdot\Vert$ ，满足：

- 正定性： $\Vert x\Vert\geqslant0$ ； $\Vert x \Vert=0$ 当且仅当 $x=0$
- 齐次性： $\Vert \alpha x \Vert=\lvert \alpha\rvert\Vert x\Vert, \alpha\in R$

- 三角不等式： $\Vert x+y \Vert \leqslant \Vert x \Vert +\Vert y\Vert, x, y\in S$

就称 $\Vert\cdot\Vert$ 是线性空间 $S$ 上的范数， $S$ 与 $\Vert\cdot \Vert$ 一起称为**赋范线性空间**，记为 $X$

对于 $R^n$ 上的向量 $ \mathbf{x}=(x_1,\cdots,x_n)^T$ ，三种常用范数：

**无穷范数** $\Vert \mathbf{x} \Vert_\infin=\displaystyle \max_{1\leqslant i\leqslant n}|x_i|$

**1-范数** $\Vert \mathbf{x} \Vert_1=\displaystyle \sum_{i=1}^n|x_i|$

**2-范数**： $\Vert \mathbf{x} \Vert_2=\displaystyle \sqrt{\sum_{i=1}^n x_i^2}$

**内积**：设 $X$ 是数域 $K$ 上的线性空间， $\forall u, v\in X$ 。有 $K$ 中的一个数与其对应，记为 $(u, v)$ ，其满足：

- $(u, v)=\overline{(v, u)}$
- $(\alpha u, v)=\alpha(u, v), \forall \alpha \in K$
- $(u+v, w)=(u, w)+(v, w), \forall w\in X$
- $(u, u)\geqslant 0$ ； $(u, u)=0$ 当且仅当 $u=0$

则称 $(u, v)$ 是 $X$ 上 $u, v$ 的内积。定义了内积的线性空间称为**内积空间**

**带权内积**： $(\mathbf{x}, \mathbf{y})=\displaystyle \sum_{i=1}^{n}\rho_i x_i y_i, \rho_i>0$

**带权范数**： $\Vert \mathbf{x}\Vert_2=\sqrt{\displaystyle \sum_{i=1}^n \rho_ix_i^2}, \rho_i>0$

**函数内积**： $(f, g)=\displaystyle \int_a^b\rho(x)f(x)g(x)dx$

**函数范数**： $\Vert f\Vert_2=\sqrt{\displaystyle \int_a^b \rho(x)f^2(x)dx}$

若 $X$ 是一个内积空间， $u_i\in X$ ，称**Gram 矩阵**为：

$$
\mathbf{G}=\begin{bmatrix}
(u_1, u_1) & (u_2, u_1) & \cdots & (u_n, u_1) \\
(u_1, u_2) & (u_2, u_2) & \cdots & (u_n, u_2) \\
\vdots & \vdots & \ddots & \vdots \\
(u_1, u_n) & (u_2, u_n) & \cdots & (u_n, u_n) \\
\end{bmatrix}
$$

Gram 矩阵非奇异的充要条件是 $u_1, u_2, \dots, u_n$ 线性无关

**最佳平方逼近函数**： $S^{*}(x)=\displaystyle \sum_{j=0}^{n}a_j\phi_j(x)$

$\phi=span\{\phi_0(x), \phi_1(x), \dots, \phi_n(x)\}$ 是 $C[a, b]$ 中的一个子集

系数由称为**法方程**的线性方程组确定：

$$
\begin{bmatrix}
(\phi_0, \phi_0) & (\phi_0, \phi_1)  & \dots & (\phi_0, \phi_n) \\
(\phi_1, \phi_0) & (\phi_1, \phi_1)  & \dots & (\phi_1, \phi_n) \\
\vdots  & \vdots & \ddots & \vdots \\
(\phi_n, \phi_0) & (\phi_n, \phi_1)  & \dots & (\phi_n, \phi_n) \\
\end{bmatrix}
\begin{bmatrix}
a_0 \\ a_1 \\ a_2 \\ \vdots \\ a_n
\end{bmatrix}=
\begin{bmatrix}
(f, \phi_0) \\ (f, \phi_1) \\ (f, \phi_2) \\ \vdots \\ (f, \phi_n)
\end{bmatrix}
$$

误差： $(\Vert \delta(x)\Vert_2)^2=(f(x), f(x))-(S^*(x),f(x))=(\Vert f(x)\Vert_2)^2-\displaystyle \sum_{k=0}^na^*_k(\phi_k(x), f(x))$

特别地，如果 $\phi_k(x)=x^k, \rho(x)\equiv 1, f(x)\in C[0, 1]$ ，记 $(f(x), \phi_k(x))=\displaystyle \int_0^1f(x)x^kdx=d_k,\mathbf{a}=(a_0, a_1, \dots, a_n)^T, \mathbf{d}=(d_0, d_m, \dots, d_n)^T$ ，则法方程可以写为 $\mathbf{Ha}=\mathbf{d}$ 。

其中 $\mathbf{H}$ 是**Hilbert 矩阵**：

$$
\mathbf{H}=\begin{bmatrix}
1 & \frac 1 2  & \dots & \frac{1}{n+1} \\
\frac 1 2 & \frac 1 3  & \dots & \frac{1}{n+2} \\
\vdots  & \vdots & \ddots & \vdots \\
\frac{1}{n+1} & \frac{1}{n+2}  & \dots & \frac{1}{2n+1} \\
\end{bmatrix}
$$

**Harr 条件**：设 $\phi_0(x), \dots, \phi_n(x)\in C[a, b]$ 的任意线性组合在点集 $\\{x_0, \dots, x_m\\}, m\geqslant n$ 上至多只有 $n$ 个不同的零点。则称 $\phi_0(x), \dots, \phi_n(x)$ 在这个点集上满足 Haar 条件。

**最小二乘函数**： $s^{*}(x)=\displaystyle \sum_{j=0}^{n}a_j\phi_j(x)$

取 $\phi_k(x)=x^k$ ，满足 Haar 条件，对应法方程的系数矩阵非奇异，解存在。系数 $a_k$ 可由下面的法方程解出：

$$
\begin{bmatrix}
\sum\rho_i & \sum\rho_ix_i  & \dots & \sum\rho_ix_i^n \\
\sum\rho_ix_i & \sum\rho_ix_i^2  & \dots & \sum\rho_ix_i^{n+1} \\
\vdots  & \vdots & \ddots & \vdots \\
\sum\rho_ix_i^n & \sum\rho_ix_{n+1}  & \dots & \sum\rho_ix_i^{2n} \\
\end{bmatrix}
\begin{bmatrix}
a_0 \\ a_1 \\ a_2 \\ \vdots \\ a_n
\end{bmatrix}=
\begin{bmatrix}
\sum\rho_iy_i \\ \sum\rho_ix_iy_i \\ \sum\rho_ix_i^2y_i \\ \vdots \\ \sum\rho_ix_i^ny_i
\end{bmatrix}
$$

误差： $(\Vert \mathbf{\delta} \Vert_2)^2=\displaystyle \sum_{i=0}^m\rho(x_i)[s^{*}(x_i)-f(x_i)]^2$

**施密特（Schmite）正交化过程**：若 $f_0(x), f_1(x), \dots, f_n(x)$ 为 $C[a, b]$ 上的一组线性无关函数，则由它们可以得到 $C[a, b]$ 上一组两两**正交**的函数 $g_n(x)=f_n(x)-\displaystyle \sum_{i=0}^{n-1}\frac{(f_n, g_i)}{(g_i, g_i)}g_i(x)$

**规范正交组**： $e_k(x)=\displaystyle \frac{1}{\Vert g_k \Vert_2}g_k(x)$

**正交多项式**：多项式空间 $P_n$ 中一组线性无关函数 $\{x^k\}$ 经过施密特正交化过程得到的一组多项式 $\{p_i(x)\}$

若 $\{p_i(x)\}$ 是 $[a, b]$ 上权函数为 $\rho(x)$ 的正交多项式，则它们具有以下性质：

- $p_k(x)$ 是首项系数不为 0 的 $k$ 次多项式
- $\{p_i(x)\}$ 是多项式空间 $P_n$ 上的一组正交基
- $p_n(x)=0$ 在 $[a, b]$ 上有 $n$ 个单根

- $p_n(x)$ 与任一不高于 $n-1$ 次的多项式正交

下面给出由不同的权函数，得到的不同正交多项式：

**Legendre 多项式**，$t \in [-1, 1]$，$\rho(t)=1$

$ P_0(t)=1, \quad P_1(t)=t, \quad (k+1)P_{k+1}(t)=(2k+1) tP_k(t)-kP_{k-1}(t) $

**Chebyshev 多项式1**，$t \in [-1, 1]$，$\rho(t)=\displaystyle \frac{1}{\sqrt{1-t^2}}$

$ P_0(t)=1, \quad P_1(t)=t, \quad P_{k+1}(t)=2tP_k(t)-P_{k-1}(t) $

**Chebyshev 多项式2**，$t \in [-1, 1]$，$\rho(t)=\sqrt{1-t^2}$

$ P_0(t)=1, \quad P_1(t)=2t, \quad P_{k+1}(t)=2tP_k(t)-P_{k-1}(t) $

**Laguerre 多项式**，$t \in [0, \infty)$，$\rho(t)=e^{-t}$

$ P_0(t)=1, \quad P_1(t)=1-t, \quad P_{k+1}(t)=(2k+1-t)P_k(t)-k^2P_{k-1}(t) $

**Hermite 多项式**，$t \in (-\infty, \infty)$，$\rho(t)=e^{-t^2}$

$ P_0(t)=1, \quad P_1(t)=2t, \quad P_{k+1}(t)=2tP_k(t)-2kP_{k-1}(t) $

如果拟合的时候，用的是正交多项式 $\{p_i(x)\}$ ，可以直接写出最佳平方逼近函数 $S^*(x)=\displaystyle \sum_{k=0}^{n}\frac{ (f, p_k)}{(p_k, p_k)}p_k(x)$，注意此时的积分区域为定义域，非定义域需做出相应变换

对于一般的积分，有： $\displaystyle \int_a^b P(s)ds= \frac{b-a}{2}\int_{-1}^{1} P(t) dt,\ s=\frac{b-a}{2}+\frac{b+a}{2}$

对于 Legendre 多项式，有： $\displaystyle \int_{-1}^1 P_j(t)P_k(t)dt =\frac{2}{2k+1},\ j= k$
