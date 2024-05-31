# **第七章 非线性方程组求根**

**二分法的误差**： 

$| x_k-x^*|\leqslant(b_k-a_k)/2=(b-a)/2^{k+1}\quad (k=0,1,2\dots)$

**不动点**：给定初始值 $x_0$ ，如果对任意 $x_0\in [a, b]$ ，由迭代公式 $x_{k+1}=\phi(x_k)$ 得到的迭代序列 $\{x_k\}$ 存在极限 $\displaystyle \lim_{k\rightarrow\infin}x_k=x^*$ ，则称该迭代公式收敛， $x^*$ 就称为不动点

**不动点的存在性**

设迭代函数 $\phi(x)\in C[a,b]$ ,并且

- $\forall x\in [ a, b]$ ,都有 $\phi(x)\in[a,b]$

- $\exists0\leq L<1$ , 使得 $\forall x,y\in[a,b]$ ,都有 $|\phi(x)-\phi(y)|\leq L| x-y|$

那么 $\phi(x)$ 在 $[a,b]$ 上存在唯一的不动点 $x^*$

上述定理的第二个条件可用 $\left|\phi^{\prime}(x)\right|\leq L<1$ 代替。

误差估计：
- $|x_k-x^*|\leqslant\displaystyle \frac{L^k}{1-L}| x_1-x_0 | $
- $|x_{k}-x^{*}|\leqslant\displaystyle \frac{L}{1-L}| x_{k}-x_{k-1}|$

**局部收敛性**

设 $\phi(x)$ 有不动点 $x^*$ ，如果存在 $x^*$ 的某个邻域 $\Delta:|x-x^*|\leqslant \delta$ ，对任意的 $x_0\in \Delta$ ，迭代公式产生的序列 $\{x_k\}$ 满足 $x_i\in \Delta$ ，且收敛到 $x^*$ ，则称该迭代公式局部收敛 

若 $\phi^\prime(x)$ 在 $x^*$ 的某邻域内连续，且 $|\phi^{\prime}(x^{*})|<1$ ,则迭代法是局部收敛的.

**收敛阶**

误差 $e_k=x_k-x^*$ , 若 $\displaystyle \lim_{k\to\infty}\frac{e_{k+1}}{e_k^p}=C$ , $C\ne 0$ , 则称迭代过程为 $p$ 阶收敛的

如果迭代函数在不动点 $x^*$ 附近有 $p$ 阶连续导数且 $\phi^{\prime}(x^*)=\phi^{\prime\prime}(x^*)=\cdots=\phi^{(p-1)}(x^*)=0,\quad\phi^{(p)}(x^*)\neq0$ ,那么迭代过程在 $x^*$ 附近是 $p$ 阶收敛的

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
