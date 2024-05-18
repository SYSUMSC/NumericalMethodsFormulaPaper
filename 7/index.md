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

**弦截法**

$单点弦截法：x_{k+1}=x_k-\frac{f(x_k)}{f(x_k)-f(x_0)}(x_k-x_0)$

$两点弦截法：x_{k+1}=x_k-\frac{f(x_k)}{f(x_k)-f(x_{k-1})}(x_k-x_{k-1})$
