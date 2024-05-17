### **第一章 数值分析与科学计算引论**
x* 为准确值，x为x*的一个近似值

**绝对误差** $e_p = |x - x^{*}| $

**相对误差** $e_r = \displaystyle \left|\frac{x-x^*}{x}\right| $

**相对误差限** $\displaystyle\varepsilon_{\mathrm{r}}=\frac{\varepsilon}{\mid x\mid}\geqslant\frac{\mid x-x^{*}\mid}{\mid x\mid}=\mid e_{\mathrm{r}}\mid $

**条件数** $C_p =\displaystyle \left|\frac{f(x)-f(\tilde{x})}{f(x)}\right|/\left|\frac{\Delta x}{x}\right|\approx\left|\frac{xf'(x)}{f(x)}\right|  $

$C_p\geqslant 10$ 就认为问题是病态的

**四则运算误差限**

- $\varepsilon(\hat{p_1}+\hat{p_2})<=\varepsilon(\hat{p_1})+\varepsilon(\hat{p_2}) $

- $\varepsilon(\hat{p_1}\hat{p_2})\approx|\hat{p_1}|\varepsilon(\hat{p_2})+|\hat{p_2}|\varepsilon(\hat{p_1}) $

- $\displaystyle\varepsilon\left(\frac{\hat{p_1}}{\hat{p_2}}\right)\approx\frac{|\hat{p_1}|\varepsilon(\hat{p_2})+|\hat{p_2}|\varepsilon(\hat{p_1})}{|\hat{p_2}|^2} $

**函数误差限** $\varepsilon(f(\hat{p}))\approx|f'(\hat{p})|\varepsilon(\hat{p}) $

若近似数有 $n$ 位有效数字，则可以写为 $\hat{p}=\pm10^m\times(a_1+a_2\times10^{-1}+\ldots+a_i\times10^{-(n-1)})$ 

其绝对误差限为 $|x-x^*|\leqslant\displaystyle \frac{1}{2}\times10^{m-n+1} $

其相对误差限 $\displaystyle|\frac{x-x^*}x|\leqslant\varepsilon_r\leqslant\frac{10^{1-n}}{2a_1}$

**Horner's Method(秦九韶算法)**

$P_n(x)=\displaystyle\sum_{i=0}^na_ix^i$ ，求 $P(x_0)$ 只需求 $b_n$ 

其中 $ b_0=a_0,b_k=a_k+b_{k-1}x_0 $
