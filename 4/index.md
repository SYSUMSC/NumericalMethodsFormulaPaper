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

**辛普森公式** $I_2=\displaystyle\frac{b-a}{6}[f(a)+4f\left(\frac{a+b}2\right)+f(b)]$

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
| 0   | $0.000000$     | $2.000000$  | 4   | $\pm0.9061798$ | $0.2369269$ |
| 1   | $\pm0.5773503$ | $1.000000$  |     | $\pm0.5384693$ | $0.4786287$ |
| 2   | $\pm0.7745967$ | $0.5555556$ |     | $0.000000$     | $0.5688889$ |
|     | $0.000000$     | $0.8888889$ | 5   | $\pm0.9324695$ | $0.1713245$ |
| 3   | $\pm0.8611363$ | $0.3478548$ |     | $\pm0.6612094$ | $0.3607616$ |
|     | $\pm0.3399810$ | $0.6521452$ |     | $\pm0.2386192$ | $0.4679139$ |

余项为 $R[f]=\frac{2^{2n+1}(n!)^4}{[(2n)!]^3(2n+1)}f^{(2n)}(\eta)\:,\eta\in(-1,1)$

**高斯-拉盖尔求积公式** $\displaystyle \int_{0}^{\infin}e^{-x}*f(x)\mathrm{d}x\approx\sum_{k=0}^{n}A_{k}f(x_{k}).$ 其中 $x_k$ 为拉盖尔多项式的零点

| $ n $ | $ x_k $ | $ A_k$ | $ n $ | $ x_k $ | $ A_k$ |
|:-----:|:-------:|:------:|:-----:|:-------:|:------:|
|   2   | 0.5858864 | 0.8535534 |   5   | 1.4134031 | 0.3986668 |
|       | 3.4142136 | 0.1464466 |       | 3.5964258 | 0.0759424 |
|   3   | 0.4157746 | 0.7110930 |       | 7.0858100 | 0.0036118 |
|       | 2.2942804 | 0.2785177 |       | 12.6408008 | 0.0002337 |
|       | 602899450829 | 0.0103893 |   6   | 0.2228466 | 0.4589647 |
|   4   | 0.3225477 | 0.6031541 |       | 1.1889321 | 0.4170008 |
|       | 1.7457611 | 0.3574187 |       | 2.9927363 | 0.1133734 |
|       | 4.5366203 | 0.0388879 |       | 5.7751436 | 0.0103992 |
|       | 9.3950709 | 0.0005393 |       | 9.8374674 | 0.0002610 |
|   5   | 0.2635603 | 0.5217556 |       | 15.9828740 | 0.0000090 |


**高斯-赫尔米特求积公式** $\displaystyle \int_{-\infin}^{\infin}e^{-x^2}*f(x)\mathrm{d}x\approx\sum_{k=0}^{n}A_{k}f(x_{k}).$ 其中 $x_k$ 为赫尔米特多项式的零点

| $ n $ | $ x_k $ | $ A_k$ | $ n $ | $ x_k $ | $ A_k$ |
|:-----:|:-------:|:------:|:-----:|:-------:|:------:|
|   2   | $\pm0.7071068$ | 0.8862269 |   6   | $\pm0.4360774$ | 0.7246296 |
|   3   | $\pm1.2247449$ | 0.2954090 |       | $\pm1.3358491$ | 0.1570673 |
|       | 0 | 1.8163590 |       | $\pm2.3506050$ | 0.0045300 |
|   4   | $\pm0.5246476$ | 0.8049141 |   7   | $\pm0.8162879$ | 0.4256073 |
|       | $\pm1.6506801$ | 0.0813128 |       | $\pm1.6735516$ | 0.0545156 |
|   5   | $\pm0.9585725$ | 0.3936193 |       | $\pm2.6519614$ | 0.0009172 |
|       | $\pm2.0201829$ | 0.0199532 |       | 0 | 0.8102646 |
|       | 0 | 0.9453087 | | | |


## **数值微分**

**向前差商公式** $f'(x)\approx\displaystyle  \frac{f(x+h)-f(x)}h$ 误差： $\displaystyle-\frac h2 f''(\xi)$

**向后差商公式** $f'(x)\approx\displaystyle \frac{f(x)-f(x-h)}h$ 误差： $\displaystyle\frac h2 f''(\xi)$

**中心差商公式** $f'(x)\approx\displaystyle \frac{f(x+h)-f(x-h)}{2h}$ 误差： $\displaystyle-\frac{h^2}6f'''(\xi)$

**舍入误差上界** $\delta(f'(a))=\displaystyle f'(a)-G(a)\leqslant\frac{|\varepsilon_1|+|\varepsilon_2|}{2h}\leqslant\frac{\varepsilon}{h}$ , $\varepsilon=\max\{|\varepsilon_{1}|,|\varepsilon_{2}|\}$

其中 $\varepsilon_1, \varepsilon_2$ 分别是 $f(a+h), f(a-h) $ 的舍入误差

**三点前向** $f^{\prime}(x_i)\approx\displaystyle\frac{-f(x_{i+2})+4f(x_{i+1})-3f(x_i)}{x_{i+2}-x_i}$

**三点中间** $f'(x_i) \approx \displaystyle\frac{f(x_{i+1}) - f(x_{i-1})}{x_{i+1} - x_{i-1}}$

**三点后向** $f^{\prime}(x_i)\approx\displaystyle\frac{3f(x_i)-4f(x_{i-1})+f(x_{i-2})}{x_i-x_{i-2}}$

**插值型求导公式**： $f'(x)=L_n'(x)$

余项 $R[f']|_{x=x_k}=\displaystyle \frac{f^{(n+1)}(\xi)}{(n+1)!}\omega_{n+1}'(x_k)$