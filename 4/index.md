# **第四章 数值积分微分**

## **数值积分**

**左矩形公式** $I \approx \left(b-a\right) f(a) $  **右矩形公式** $I \approx \left(b-a\right) f(b) $

**中点矩形公式** $I \approx \left(b-a\right) \displaystyle f\left(\frac{a+b}{2}\right) $

**插值型求积公式** $I\approx I_n = \displaystyle \int_a^b L_n(x)dx=\sum_{k=0}^n A_k f(x_k)$ , 其中 $\displaystyle A_k=\int_a^b l_k(x)dx$ 

余项 $\displaystyle R[f]=\int_a^b\frac{f^{(n+1)}(\xi)}{(n+1)!}\omega_{n+1}(x)dx$ ，至少有n次代数精度

形如 $I_n=\sum^{n}A_kf(x_k)$ 的积分公式至少有 $n$ 次代数精度的充要条件是：它是插值型的

**牛顿-柯特斯公式**:  $I\approx I_{n}=\displaystyle (b-a)\sum_{k=0}^{n}\mathbf{C}_{k}^{(n)}f(x_{k})$

其中 $h=\displaystyle \frac{b-a}n, x_k=a+kh$

若n为偶数，则n阶N-C公式至少有n+1次代数精度

**柯特斯系数**： $\mathbf{C}_{k}^{(n)}=\displaystyle \frac{(-1)^{n-k}}{k!(n-k)!\cdot n}\int_{0}^{n}\prod_{j=0,j\neq k}^{n}(t-j)dt $

$\displaystyle \sum_{k=0}^n C_k^{(n)}=1$ 恒成立

**梯形公式** $I_1=\displaystyle \frac{b-a}{2}[f(a)+f(b)]$  余项 $R[f]=\displaystyle -\frac{(b-a)^3}{12}f''(\eta)$

**辛普森公式** $I_2=\displaystyle\frac{b-a}{6}[f(a)+4f(\frac{a+b}2)+f(b)]$ 

余项 $R[f]=\displaystyle-\frac{(b-a)^5}{2880}f^{(4)}(\eta)$

**柯特斯公式** $I_4=\displaystyle\frac{b-a}{90}[7f(x_0)+32f(x_1)+12f(x_2)+32f(x_3)+7f(x_4)]$ 误差 $R[f]=\displaystyle -\frac{(b-a)^7}{1935360}f^{(6)}(\eta), \eta\in(a, b)$

**复化的梯形公式** $I\approx T_n = \displaystyle \frac h2[f(a)+2\sum_{k=1}^{n-1}f(x_k)+f(b)]$

余项： $R_{n}[f]=\displaystyle -\frac{b-a}{12}h^{2}f^{''}(\eta),\eta\in(a,b)$

**复化的辛普森公式** $I\approx S_{n}=\displaystyle \frac{h}{6}[f(a)+4\sum_{k=0}^{n-1}f(x_{k+\frac{1}{2}})+2\sum_{k=1}^{n-1}f(x_{k})+f(b)], x_{k+\frac 1 2}=\frac{x_k+x_{k+1}}{2}$

余项： $R_{n}[f]=\displaystyle -\frac{b-a}{180}\biggl(\frac{h}{2}\biggr)^{4}f^{(4)}(\eta),\eta\in(a,b)$

**递推型梯形公式** $T_{2n}=\displaystyle \frac{1}{2}T_{n}+\frac{h}{2}\sum_{k=0}^{n-1}f(x_{k+\frac{1}{2}})$

进一步可定义 $S_n=\displaystyle \frac{4T_{2n}-T_n}{4-1}, C_n=\displaystyle \frac{4^2S_{2n}-S_n}{4^2-1}$

**龙贝格求积公式** $R_n=\displaystyle \frac{4^3C_{2n}-C_n}{4^3-1}$

有 $\displaystyle \lim_{n\rightarrow \infin} T_n, S_n, C_n, R_n=I$，收敛速度从左到右依次加快

**高斯-勒让德求积公式** $\displaystyle \int_{-1}^{1}1*f(x)\mathrm{d}x\approx\sum_{k=0}^{n}A_{k}f(x_{k}).$ 其中 $x_k$ 为勒让德多项式的零点

| n   | $x_k$          | $A_k$       | n   | $x_k$          | $A_k$       |
| --- | -------------- | ----------- | --- | -------------- | ----------- |
| 1   | $0.000000$     | $2.000000$  | 5   | $\pm0.9061798$ | $0.2369269$ |
| 2   | $\pm0.5773503$ | $1.000000$  |     | $\pm0.5384693$ | $0.4786287$ |
| 3   | $\pm0.7745967$ | $0.5555556$ |     | $0.000000$     | $0.5688889$ |
|     | $0.000000$     | $0.8888889$ | 6   | $\pm0.9324695$ | $0.1713245$ |
| 4   | $\pm0.8611363$ | $0.3478548$ |     | $\pm0.6612094$ | $0.3607616$ |
|     | $\pm0.3399810$ | $0.6521452$ |     | $\pm0.2386192$ | $0.4679139$ |

余项为 $R[f]=\frac{2^{2n+1}(n!)^4}{[(2n)!]^3(2n+1)}f^{(2n)}(\eta)\:,\eta\in(-1,1)$

**高斯-拉盖尔求积公式** $\displaystyle \int_{0}^{\infin}e^{-x}*f(x)\mathrm{d}x\approx\sum_{k=0}^{n}A_{k}f(x_{k}).$ 其中 $x_k$ 为拉盖尔多项式的零点

| $ n $ | $ x_k $ | $ A_k$ |
|:-----:|:-------:|:------:|
|   2   | 0.5858864376 | 0.8535533905 |
|       | 3.4142135623 | 0.1464466094 |
|   3   | 0.4157745567 | 0.7110930099 |
|       | 2.2942803602 | 0.2785177335 |
|       | 602899450829 | 0.0103892565 |
|   4   | 0.3225476896 | 0.6031541043 |
|       | 1.7457611011 | 0.3574186924 |
|       | 4.5366202969 | 0.0388879085 |
|       | 9.3950709123 | 0.0005392947 |
|   5   | 0.2635603197 | 0.5217556105 |
|       | 1.4134030591 | 0.3986668110 |
|       | 3.5964257710 | 0.0759424497 |
|       | 7.0858100058 | 0.0036117587 |
|       | 12.6408008442 | 0.0002337000 |
|   6   | 0.2228466041 | 0.4589646793 |
|       | 1.1889321016 | 0.4170008307 |
|       | 2.9927363260 | 0.1133733820 |
|       | 5.7751435691 | 0.0103991795 |
|       | 9.8374674183 | 0.0002610172 |
|       | 15.9828739806 | 0.0000089895 |


**高斯-赫尔米特求积公式** $\displaystyle \int_{-\infin}^{\infin}e^{-x^2}*f(x)\mathrm{d}x\approx\sum_{k=0}^{n}A_{k}f(x_{k}).$ 其中 $x_k$ 为赫尔米特多项式的零点

| $ n $ | $ x_k $ | $ A_k$ |
|:-----:|:-------:|:------:|
|   2   | $\pm0.7071067811$ | 0.8862269254 |
|   3   | $\pm1.2247448713$ | 0.2954089751 |
|       | 0 | 1.8163590006 |
|   4   | $\pm0.5246476232$ | 0.8049140900 |
|       | $\pm1.6506801238$ | 0.0813128354 |
|   5   | $\pm0.9585724646$ | 0.3936193231 |
|       | $\pm2.0201828704$ | 0.0199532421 |
|       | 0 | 0.9453087204 |
|   6   | $\pm0.4360774119$ | 0.7246295952 |
|       | $\pm1.3358490704$ | 0.1570673203 |
|       | $\pm2.3506049736$ | 0.0045300099 |
|   7   | $\pm0.8162878828$ | 0.4256072526 |
|       | $\pm1.6735516287$ | 0.0545155828 |
|       | $\pm2.6519613563$ | 0.0009171812 |
|       | 0 | 0.8102646175 |


## **数值微分**

**向前差商公式** $f'(x)\approx\displaystyle  \frac{f(x+h)-f(x)}h$ 误差： $\displaystyle-\frac h2 f''(\xi)$

**向后差商公式** $f'(x)\approx\displaystyle \frac{f(x)-f(x-h)}h$ 误差： $\displaystyle\frac h2 f''(\xi)$

**中心差商公式** $f'(x)\approx\displaystyle \frac{f(x+h)-f(x-h)}{2h}$ 误差： $\displaystyle-\frac{h^2}6f'''(\xi)$

**舍入误差上界** $\delta(f'(a))=\displaystyle f'(a)-G(a)\leqslant\frac{|\varepsilon_1|+|\varepsilon_2|}{2h}\leqslant\frac{\varepsilon}{h}$ , $\varepsilon=\max\{|\varepsilon_{1}|,|\varepsilon_{2}|\}$

其中 $\varepsilon_1, \varepsilon_2$ 分别是 $f(a+h), f(a-h) $ 的舍入误差

**插值型求导公式**： $f'(x)=L_n'(x)$

余项 $R[f']|_{x=x_k}=\displaystyle \frac{f^{(n+1)}(\xi)}{(n+1)!}\omega_{n+1}'(x_k)$