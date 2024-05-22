### **第七章 非线性方程组求根**

**埃金特加速方法**

$\hat{x}_k=x_k-\frac{(x_{k+1}-x_k)^2}{x_{k+2}-2x_{k+1}+x_k}$

**斯特芬森迭代法**

- $y_k=\phi(x_k)$
- $z_k=\phi(y_k)$
- $x_{k+1}=x_k-\frac{{(y_k-x_k)}^2}{z_k-2y_k+x_k}$

**牛顿法**

$x_{k+1}=x_k-\frac{f(x_k)}{f'(x_k)}$

**带参数 m 的牛顿法**

$x_{k+1}=x_k-m\frac{f(x_k)}{f'(x_k)}$

$x^*为f(x)=0的m重根$

$x_{k+1}=x_k-\frac{f(x_k)f'(x_k)}{{[f'(x_k)]}^2-f(x_k)f''(x_k)}$

**简化牛顿法和下山法**

(1)构造选代公式
$$x_{k+1}=x_{k}-Cf(x_{k})\quad C\neq0,k=0,1,2,\cdots.$$
迭代函数$\varphi(x)=x-Cf(x)$.若$\left|\varphi^\prime(x)\right|=\left|1-Cf^{\prime}(x)\right|<1$, 即$0<Cf^\prime(x)<2$ 时
在根x"附近成立，迭代法局部收敛。当取$C=\frac1{f^{\prime}(x_0)}$ 时，迭代公式

称为简化牛顿法。
$$x_{k+1}=x_k-\frac{f(x_k)}{f^{\prime}(x_0)}$$

(2) 将牛顿法与下山法结合起来使用。牛顿法的计算结果 $\overline{x}_{k+1}=x_{k}-\frac{f(x_{k})}{f^{\prime}(x_{k})}$ 与前一步的近似值 $x_k$ 的适当加权平均作为新的改进值
$$x_{k+1}=\lambda\overline{x}_{k+1}+(1-\lambda)x_{k},\quad x_{k+1}=x_{k}-\lambda\frac{f(x_{k})}{f^{\prime}(x_{k})},\quad k=0,1,2,\cdots,$$
加入下山因子的迭代公式称为牛顿下山法。选择下山因子时从 $\lambda=1$ 开始，逐次将 $\lambda$ 折半直到满足 $\left|f(x_{k+1})\right|<\left|f(x_{k})\right|$。


**弦截法**

$单点弦截法：x_{k+1}=x_k-\frac{f(x_k)}{f(x_k)-f(x_0)}(x_k-x_0)$

$两点弦截法：x_{k+1}=x_k-\frac{f(x_k)}{f(x_k)-f(x_{k-1})}(x_k-x_{k-1})$
