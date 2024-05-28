# **第七章 非线性方程组求根**

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
