# **第七章 非线性方程组求根**

**k次二分法的误差**： 

$\mid x_k-x^*\mid\leq(b_k-a_k)/2=(b-a)/2^{k+1}\quad (k=0,1,2\dots)$

**不动点的存在性与迭代法的收敛性**

设迭代函数$\phi(x)\in C[a,b]$ ,并且

(1) $\forall x\in [ a, b]$ ,都有 $\phi(x)\in[a,b]$

(2) $\exists0\leq L<1$ , 使得 $\forall x,y\in[a,b]$ ,都有$\mid\phi(x)-\phi(y)\mid\leq L\mid x-y\mid$

那么 $\phi(x)$ 在 $[a,b]$ 上存在唯一的不动点 $x^*$

上述定理的条件(2)可用 $\left|\phi^{\prime}(x)\right|\leq L<1$ 代替。

误差估计：
1. $|x_k-x^*|\le\frac{L^k}{1-L}| x_1-x_0 | $
2. $|x_{k}-x^{*}|\leq\frac{L}{1-L}| x_{k}-x_{k-1}|$

**局部收敛性**

设$x^*$为迭代函数 $\phi(x)$的不动点，$\phi^\prime(x)$在$x^*$ 的某邻域内连续，且$\mid\phi^{\prime}(x^{*})\mid<1$,则迭代法是局部收敛的.

**收敛阶**

误差 $e_k=x_k-x^*$ , 若 $\lim_{k\to\infty}\frac{e_{k+1}}{e_k^p}=C$ , $C\ne 0$ , 则称迭代过程为 $p$ 阶

如果 $\phi^{\prime}(x^*)=\phi^{\prime\prime}(x^*)=\cdots=\phi^{(p-1)}(x^*)=0,\quad\phi^{(p)}(x^*)\neq0$ ,那么迭代过程在 $x^*$ 附近是 $p$ 阶收敛的

**斯特芬森迭代法**：

$$
x_{k+1}=\psi(x_k),\psi(x)=x-\frac{[\phi(x)-x]^2}{\phi(\phi(x))-2\phi(x)+x}
$$

**牛顿法**： $x_{k+1}=\displaystyle x_k-\frac{f(x_k)}{f'(x_k)}$

**简化牛顿法**： $x_{k+1}=\displaystyle x_k-\frac{f(x_k)}{f'(x_0)}$

**牛顿下山法**： $x_{k+1}=\displaystyle x_k-\lambda\frac{f(x_k)}{f'(x_k)}$

每一次迭代从 $\lambda=1$ 开始试算，不断令 $\lambda$ 减半直到满足 $|f(x_{k+1})|<|f(x_k)|$

**重根情形下的牛顿法**：若 $f(x)=(x-x^*)^m h(x)$

改为 $x_{k+1}=x_k-\displaystyle m\frac{f(x_k)}{f'(x_k)}$ ，仍然是平方收敛的

**单点弦截法（割线法）**：$x_{k+1}=x_k-\displaystyle \frac{f(x_k)}{f(x_k)-f(x_0)}(x_k-x_0)$

**两点弦截法**： $x_{k+1}=x_k-\displaystyle \frac{f(x_k)}{f(x_k)-f(x_{k-1})}(x_k-x_{k-1})$

可取两端点为初始值
