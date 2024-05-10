### 第四章：数值积分微分

#### 数值积分

左矩形公式 $I = \left(b-a\right) f(a) $

右矩形公式 $I = \left(b-a\right) f(b) $

中点矩形公式 $I = \left(b-a\right) f\left(\frac{a+b}{2}\right) $

插值型求积公式 $I_n = \int_a^b\sum_{k=0}^{n}l_k(x)f_kdx=\sum_{k=0}^n[\int_a^bl_k(x)dx]f_k$ , 余项 $R[f]=\int_a^b\frac{f^{(n+1)}(\xi)}{(n+1)!}\omega_{n+1}(x)dx$

牛顿-柯特斯公式: 将 $[a,b]$ 做 $n$ 等分, 步长 $h=\frac{b-a}n$ , 取 $x_k=a+kh$

$I_{n}=(b-a)\sum_{k=0}^{n}\mathbf{C}_{k}^{(n)}f(x_{k}),\quad\mathbf{C}_{k}^{(n)}=\frac{h}{b-a}\int_{0}^{n}\prod_{j=0,j\ne k}^{n}\frac{t-j}{k-j}\mathbf{d}t=\frac{\left(-1\right)^{n-k}}{nk!(n-k)!}\int_{0}^{n}\prod_{j=0,j\ne k}^{n}(t-j)\mathbf{d}t. $

梯形公式(n=1) $I_1=\frac{f(a)+f(b)}{2}(b-a)$ , 余项 $R[f]=\int_a^b\frac{f''(\xi)}{2}(x-a)(x-b)dx=-\frac{(b-a)^3}{12}f''(\eta)$

辛普森公式(n=2) $I_2=\frac{b-a}{6}[f(a)+4f(\frac{a+b}2)+f(b)]$ , 余项 $R[f]=-\frac{b-a}{180}(\frac{b-a}2)^4f^{(4)}(\eta)$

柯特斯公式(n=4) $I_4=\frac{b-a}{90}[7f(x_0)+32f(x_1)+12f(x_2)+32f(x_3)+7f(x_4)]$

复合梯形公式 $I=\int_{a}^{b}f(x)\mathrm{d}x=\sum_{k=0}^{n-1}\int_{x_{k}}^{x_{k+1}}f(x)\mathrm{d}x=\sum_{k=0}^{n-1}\frac{h}{2}[f(x_{k})+f(x_{k+1})]+R_{n}[f]$

记 $T_n = \sum_{k=0}^{n-1}\frac{h}{2}[f(x_{k})+f(x_{k+1})]=\frac h2[f(a)+2\sum_{k=1}^{n-1}f(x_k)+f(b)]$

$\begin{aligned}R_{n}[f]&=I-T_{n}=\sum_{k=0}^{n-1}\biggl[-\frac{h^{3}}{12}f^{\prime\prime}(\eta_{k})\biggr],\quad\eta_{k}\in(x_{k},x_{k+1})\\&=-\frac{b-a}{12}h^{2}f^{\prime\prime}(\eta),\quad\eta\in(a,b)\end{aligned}$

复合辛普森公式 $I=\sum_{k=0}^{n-1}\frac{h}{6}[f(x_{k})+4f(x_{k+\frac{1}{2}})+f(x_{k+1})]+R_{n}[f]$

记 $S_{n}=\frac{h}{6}[f(a)+4\sum_{k=0}^{n-1}f(x_{k+\frac{1}{2}})+2\sum_{k=1}^{n-1}f(x_{k})+f(b)] $

$\begin{aligned}R_{n}[f]&=-\frac{h}{180}\biggl(\frac{h}{2}\biggr)^{4}\sum_{k=0}^{n-1}f^{(4)}(\eta_{k}),\quad\eta_{k}\in(x_{k},x_{k+1})\\&=-\frac{b-a}{180}\biggl(\frac{h}{2}\biggr)^{4}f^{(4)}(\eta),\quad\eta\in(a,b)\end{aligned}$

变步长的梯形法 $T_{2n}=\frac{1}{2}T_{n}+\frac{h}{2}\sum_{k=0}^{n-1}f(x_{k+\frac{1}{2}})$

复化辛普森公式 $S_n=\frac{4T_{2n}-T_n}{4-1}$

复化科特斯公式 $C_n=\frac{16}{15}S_{2n}-\frac{1}{15}S_n=\frac{4^2S_{2n}-S_n}{4^2-1}$

龙贝格求积公式 $R_n=\frac{64}{63}C_{2n}-\frac{1}{63}C_n=\frac{4^3C_{2n}-C_n}{4^3-1}$

#### 数值微分

向前差商公式 $f'(x)= \frac{f(x+h)-f(x)}h -\frac h2 f''(\xi_1)$

向后差商公式 $f'(x)= \frac{f(x)-f(x-h)}h+\frac h2 f''(\xi_2)$

中心差商公式 $f'(x)\approx \frac{f(x+h)-f(x-h)}{2h}-\frac{h^2}6f'''(\xi_3)$

舍入误差上界 $\delta(f'(a))=\begin{vmatrix}f'(a)-G(a)\end{vmatrix}\leq\frac{\begin{vmatrix}\varepsilon_1\end{vmatrix}+\begin{vmatrix}\varepsilon_2\end{vmatrix}}{2h}\leq\frac{\varepsilon}{h}$ , $\varepsilon=\max\{|\varepsilon_{1}|,|\varepsilon_{2}|\}$

插值型求导误差余项 $f^{\prime}(x)-P_n^{\prime}(x)=\frac{f^{(n+1)}(\xi)}{(n+1)!}\omega_{n+1}^{\prime}(x)+\frac{\omega_{n+1}(x)}{(n+1)!}\frac{\mathrm{d}}{\mathrm{d}x}f^{(n+1)}(\xi)$

$f'(x_k)-P_n'(x_k)=\frac{f^{(n+1)}(\xi)}{(n+1)!}\omega_{n+1}'(x_k)$