### 第一章 数值分析与科学计算引论

绝对误差 $e_p = |x - x^{*}|$ 

绝对误差限 $\hat{\epsilon}=\frac{1}{2}\times10^{m-n+1}$ （近似数具有 n 位有效数字）

相对误差 $e_r = \left|\frac{x-x'}{p}\right|$

相对误差限 $\varepsilon_{\mathrm{r}}=\frac{\varepsilon}{\mid x\mid}\geq\frac{\mid x-x^{*}\mid}{\mid x\mid}=\mid e_{\mathrm{r}}\mid $

条件数 $C_{_p}= \left|\frac{xf'(x)}{f(x)}\right| \approx \left|\frac{f(x)-f(\tilde{x})}{f(x)}\right|/\left|\frac{\Delta x}{x}\right|$

四则运算误差限

$\epsilon(\hat{p_1}+\hat{p_2})<=\epsilon(\hat{p_1})+\epsilon(\hat{p_2})$

$\epsilon(\hat{p_1}\hat{p_2})\approx|\hat{p_1}|\epsilon(\hat{p_2})+|\hat{p_2}|\epsilon(\hat{p_1})$

$\epsilon(\frac{\hat{p_1}}{\hat{p_2}})\approx\frac{|\hat{p_1}|\epsilon(\hat{p_2})+|\hat{p_2}|\epsilon(\hat{p_1})}{|\hat{p_2}|^2}$

函数误差限 $\epsilon(f(\hat{p}))\approx|f\prime(\hat{p})|\epsilon(\hat{p})$

有效数字与相对误差限关系：

$\text{近似数}\hat{p}=\pm10^m\times(a_1+a_2\times10^{-1}+\ldots+a_i\times10^{-(i-1)})$

设$\hat{p}$有n位有效数字,则其相对误差限: $|\frac{p-\hat{p}}p|<=\epsilon_r<=\frac{10^{1-n}}{2a_1}\$

Horner's Method(秦九韶算法) 

$P_n(x)=\sum_{i=0}^na_ix^i, b_n=a_n,b_k=a_k+cb_{k+1}\Rightarrow b_0=P(c)$