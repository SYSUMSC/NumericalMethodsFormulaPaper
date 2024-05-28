# **第四章 数值积分微分**

## **数值积分**

**左矩形公式** $I \approx \left(b-a\right) f(a) $

**右矩形公式** $I \approx \left(b-a\right) f(b) $

**中点矩形公式** $I \approx \left(b-a\right) \displaystyle f\left(\frac{a+b}{2}\right) $

**插值型求积公式** $I\approx I_n = \displaystyle \int_a^b L_n(x)dx=\sum_{k=0}^n A_k f(x_k)$ , 其中 $\displaystyle A_k=\int_a^b l_k(x)dx$ 

余项 $\displaystyle R[f]=\int_a^b\frac{f^{(n+1)}(\xi)}{(n+1)!}\omega_{n+1}(x)dx$

**牛顿-柯特斯公式**:  $I\approx I_{n}=\displaystyle (b-a)\sum_{k=0}^{n}\mathbf{C}_{k}^{(n)}f(x_{k})$

其中 $h=\displaystyle \frac{b-a}n, x_k=a+kh$

**柯特斯系数**： $\mathbf{C}_{k}^{(n)}=\displaystyle \frac{(-1)^{n-k}}{k!(n-k)!\cdot n}\int_{0}^{n}\prod_{j=0,j\neq k}^{n}(t-j)dt $

$\displaystyle \sum_{k=0}^n C_k^{(n)}=1$ 恒成立

**梯形公式** $I_1=\displaystyle \frac{b-a}{2}[f(a)+f(b)]$ 

余项 $R[f]=\displaystyle -\frac{(b-a)^3}{12}f''(\eta)$

**辛普森公式** $I_2=\displaystyle\frac{b-a}{6}[f(a)+4f(\frac{a+b}2)+f(b)]$ 

余项 $R[f]=\displaystyle-\frac{(b-a)^5}{2880}f^{(4)}(\eta)$

**柯特斯公式** $I_4=\displaystyle\frac{b-a}{90}[7f(x_0)+32f(x_1)+12f(x_2)+32f(x_3)+7f(x_4)]$

误差 $R[f]=\displaystyle -\frac{(b-a)^7}{1935360}f^{(6)}(\eta), \eta\in(a, b)$

**复化的梯形公式** $I\approx T_n = \displaystyle \frac h2[f(a)+2\sum_{k=1}^{n-1}f(x_k)+f(b)]$

余项： $R_{n}[f]=\displaystyle -\frac{b-a}{12}h^{2}f^{''}(\eta),\eta\in(a,b)$

**复化的辛普森公式** $I\approx S_{n}=\displaystyle \frac{h}{6}[f(a)+4\sum_{k=0}^{n-1}f(x_{k+\frac{1}{2}})+2\sum_{k=1}^{n-1}f(x_{k})+f(b)], x_{k+\frac 1 2}=\frac{x_k+x_{k+1}}{2}$

余项： $R_{n}[f]=\displaystyle -\frac{b-a}{180}\biggl(\frac{h}{2}\biggr)^{4}f^{(4)}(\eta),\eta\in(a,b)$

**递推型梯形公式** $T_{2n}=\displaystyle \frac{1}{2}T_{n}+\frac{h}{2}\sum_{k=0}^{n-1}f(x_{k+\frac{1}{2}})$

进一步可定义 $S_n=\displaystyle \frac{4T_{2n}-T_n}{4-1}, C_n=\displaystyle \frac{4^2S_{2n}-S_n}{4^2-1}$

**龙贝格求积公式** $R_n=\displaystyle \frac{4^3C_{2n}-C_n}{4^3-1}$

有 $\displaystyle \lim_{n\rightarrow \infin} T_n, S_n, C_n, R_n=I$，收敛速度从左到右依次加快

**高斯-勒让德求积公式** $\displaystyle \int_{-1}^{1}1*f(x)\mathrm{d}x\approx\sum_{k=0}^{n}A_{k}f(x_{k}).$ 其中 $x_k$ 为勒让德多项式的零点

**高斯-拉盖尔求积公式** $\displaystyle \int_{0}^{\infin}e^{-x}*f(x)\mathrm{d}x\approx\sum_{k=0}^{n}A_{k}f(x_{k}).$ 其中 $x_k$ 为拉盖尔多项式的零点

**高斯-赫尔米特求积公式** $\displaystyle \int_{-\infin}^{\infin}e^{-x^2}*f(x)\mathrm{d}x\approx\sum_{k=0}^{n}A_{k}f(x_{k}).$ 其中 $x_k$ 为赫尔米特多项式的零点

## **数值微分**

**向前差商公式** $f'(x)\approx\displaystyle  \frac{f(x+h)-f(x)}h$


误差： $\displaystyle-\frac h2 f''(\xi)$

**向后差商公式** $f'(x)\approx\displaystyle \frac{f(x)-f(x-h)}h$

误差： $\displaystyle\frac h2 f''(\xi)$

**中心差商公式** $f'(x)\approx\displaystyle \frac{f(x+h)-f(x-h)}{2h}$

误差： $\displaystyle-\frac{h^2}6f'''(\xi)$

**舍入误差上界** $\delta(f'(a))=\displaystyle f'(a)-G(a)\leqslant\frac{|\varepsilon_1|+|\varepsilon_2|}{2h}\leqslant\frac{\varepsilon}{h}$ , $\varepsilon=\max\{|\varepsilon_{1}|,|\varepsilon_{2}|\}$

其中 $\varepsilon_1, \varepsilon_2$ 分别是 $f(a+h), f(a-h) $ 的舍入误差

**插值型求导公式**： $f'(x)=L_n'(x)$

余项 $R[f']|_{x=x_k}=\displaystyle \frac{f^{(n+1)}(\xi)}{(n+1)!}\omega_{n+1}'(x_k)$