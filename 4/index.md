### 第四章：数值积分微分

左矩形公式 $I = \frac{b-a}{n} f(a) $

右矩形公式 $I = \frac{b-a}{n} f(b) $

中点矩形公式 $I = \frac{b-a}{n} f\left(\frac{a+b}{2}\right) $

梯形公式 $I = \frac{b-a}{n} \left(\frac{f(a) + f(b)}{2} + \sum_{k=1}^{n-1}f(a+k\cdot h)\right), \quad h=\frac{b-a}{n} $

辛普森公式（Simpson） $I = \frac{b-a}{n} \left(\frac{f(a) + 4f\left(\frac{a+b}{2}\right) + f(b)}{6}\right), \quad n \text{ 为偶数} $

牛顿-柯斯特公式

$I_{n}=(b-a)\sum_{k=0}^{n}\mathbf{C}_{k}^{(n)}f(x_{k}),\quad\mathbf{C}_{k}^{(n)}=\frac{h}{b-a}\int_{0}^{n}\prod_{j=0}^{n}\frac{t-j}{k-j}\mathbf{d}t=\frac{\left(-1\right)^{n-k}}{nk!(n-k)!}\int_{0}^{n}\prod_{j=0}^{n}(t-j)\mathbf{d}t. $