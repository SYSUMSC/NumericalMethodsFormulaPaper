### 第四章：数值积分微分

左矩形公式 $I = \frac{b-a}{n} f(a) $

右矩形公式 $I = \frac{b-a}{n} f(b) $

中点矩形公式 $I = \frac{b-a}{n} f\left(\frac{a+b}{2}\right) $

梯形公式 $I = \frac{b-a}{n} \left(\frac{f(a) + f(b)}{2} + \sum_{k=1}^{n-1}f(a+k\cdot h)\right), \quad h=\frac{b-a}{n} $

辛普森公式（Simpson） $I = \frac{b-a}{n} \left(\frac{f(a) + 4f\left(\frac{a+b}{2}\right) + f(b)}{6}\right), \quad n \text{ 为偶数} $

牛顿-柯斯特公式

$I_{n}=(b-a)\sum_{k=0}^{n}\mathbf{C}_{k}^{(n)}f(x_{k}),\quad\mathbf{C}_{k}^{(n)}=\frac{h}{b-a}\int_{0}^{n}\prod_{j=0}^{n}\frac{t-j}{k-j}\mathbf{d}t=\frac{\left(-1\right)^{n-k}}{nk!(n-k)!}\int_{0}^{n}\prod_{j=0}^{n}(t-j)\mathbf{d}t. $

复合梯形公式

$I=\int_{a}^{b}f(x)\mathrm{d}x=\sum_{k=0}^{n-1}\int_{x_{k}}^{x_{k+1}}f(x)\mathrm{d}x=\sum_{k=0}^{n-1}\frac{h}{2}[f(x_{k})+f(x_{k+1})]+R_{n}[f]$

$\begin{aligned}R_{n}[f]&=I-T_{n}=\sum_{k=0}^{n-1}\biggl\lfloor-\frac{h^{3}}{12}f^{\prime\prime}(\eta_{k})\biggr\rfloor,\quad\eta_{k}\in(x_{k},x_{k+1})\\&=-\frac{b-a}{12}h^{2}f^{\prime\prime}(\eta),\quad\eta\in(a,b)\end{aligned}$