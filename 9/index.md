# **第九章 常微分方程**
**一阶常微分方程初值问题**

$$
\left\{
\begin{align*}
&y'=f(x, y), x\in [x_0, b] \\
&y(x_0)=y_0
\end{align*}
\right.
$$

**利普希兹条件**： $|f(x,y_1)-f(x,y_2)|\leqslant{L|y_1-y_2|}, L>0$

**前向欧拉法**： $y_{n+1}=y_n+hf(x_n,y_n) $ ，局部截断误差 $T_{n+1}=\displaystyle \frac{h^2}{2}y''(x_n)+O(h^3)$

**后向欧拉法**： $y_{n+1}=y_n+hf(x_{n+1},y_{n+1})$ ，局部截断误差 $T_{n+1}=\displaystyle -\frac{h^2}{2}y''(x_n)+O(h^3)$

**梯形方法**： $ y_{n+1}=\displaystyle y_n+\frac{h}{2}[f(x_n,y_n)+f(x_{n+1},y_{n+1})]$ ，局部截断误差 $T_{n+1}=\displaystyle -\frac{h^3}{12}y'''(x_n)+O(h^4)$

**改进欧拉法（Heun 法）**

$$
\left\{
\begin{align*}
y_p&=y_n+hf(x_n,y_n) \\
y_c&=y_n+hf(x_{n+1},y_p) \\
y_{n+1}&=\frac{y_p+y_c}{2}
\end{align*}
\right.
$$

**r 级显式龙格-库塔公式**

$$
\left\{
\begin{align*}
&y_{n+1}=y_n+h\phi(x_n, y_n, h)=y_n+h\sum_{i=1}^r c_i K_i \\
&K_1=f(x_n,y_n) \\
&K_i=f(x_n+\lambda_i h,y_n+h\sum_{j=1}^{i-1} \mu_{ij} K_j), \quad i=2,\ldots,r
\end{align*}
\right.
$$

**二阶 R-K 公式（中点公式）**

$$
\left\{
\begin{align*}
&y_{n+1}=y_n+hK_2 \\
&K_1=f(x_n,y_n) \\
&K_2=f(x_n+\frac{h}{2},y_n+\frac{h}{2}K_1)
\end{align*}
\right.
$$

**三阶 R-K 公式（库塔公式）**

$$
\left\{
\begin{align*}
&y_{n+1}=y_n+\frac{h}{6}(K_1+4K_2+K_3),\\
&K_1=f(x_n,y_n)\\
&K_2=f\Big(x_n+\frac{h}{2},y_n+\frac{h}{2}K_1\Big)\\
&K_3=f(x_n+h,y_n-hK_1+2hK_2)
\end{align*}
\right.
$$

**四阶 R-K 公式**

$$
\left\{
\begin{align*}
&y_{n+1}=y_n+\frac{h}{6}(K_1+2K_2+2K_3+K_4) \\
&K_1=f(x_n,y_n) \\
&K_2=f(x_n+\frac{h}{2}, y_n+\frac{h}{2} K_1) \\
&K_3=f(x_n+\frac{h}{2}, y_n+\frac{h}{2} K_2) \\
&K_4=f(x_n+h, y_n+h K_3)
\end{align*}
\right.
$$

**线性多步法**： $ y_{n+k}=\displaystyle \sum_{i=0}^{k-1}\alpha_i y_{n+i}+h\sum_{i=0}^k\beta_i f_{n+i}, f_{n+i}=f(x_{n+i}, y_{n+i}) $

$\beta_k \neq 0$ 隐式 $k$ 步法；否则为显示多步法

**局部截断误差**： $ T_{n+k}=c_{p+1}h^{p+1}y^{(p+1)}(x_n)+O(h^{p+2}) $

**阿当姆斯显式公式**

| 步数 $k$ | 阶数 $p$ | 公式                                                                          | $c_{p+1}$         |
| --- | --- | ----------------------------------------------------------------------------- | ----------------- |
| 1   | 1   | $y_{n+1} = y_n + h f_n$                                                       | $\displaystyle \frac{1}{2}$     |
| 2   | 2   | $\displaystyle y_{n+2} = y_{n+1} + \frac{h}{2} (3f_{n+1} - f_n)$                            | $\displaystyle \frac{5}{12}$    |
| 3   | 3   | $\displaystyle y_{n+3} = y_{n+2} + \frac{h}{12} (23f_{n+2} - 16f_{n+1} + 5f_n)$             | $\displaystyle \frac{3}{8}$     |
| 4   | 4   | $\displaystyle y_{n+4} = y_{n+3} + \frac{h}{24} (55f_{n+3} - 59f_{n+2} + 37f_{n+1} - 9f_n)$ | $\displaystyle \frac{251}{720}$ |

**阿当姆斯隐式公式**

| 步数 $k$ | 阶数 $p$ | 公式                                                                                            | $c_{p+1}$         |
| --- | --- | ----------------------------------------------------------------------------------------------- | ----------------- |
| 1   | 2   | $\displaystyle y_{n+1} = y_n + \frac{h}{2} (f_{n+1} + f_n)$                                                   | $\displaystyle -\frac{1}{12}$   |
| 2   | 3   | $\displaystyle y_{n+2} = y_{n+1} + \frac{h}{12} (5f_{n+2} + 8f_{n+1} - f_n)$                                  | $\displaystyle -\frac{1}{24}$   |
| 3   | 4   | $\displaystyle y_{n+3} = y_{n+2} + \frac{h}{24} (9f_{n+3} + 19f_{n+2} - 5f_{n+1} + f_n)$                      | $\displaystyle -\frac{19}{720}$ |
| 4   | 5   | $\displaystyle y_{n+4} = y_{n+3} + \frac{h}{720} (251f_{n+4} + 646f_{n+3} - 264f_{n+2} + 106f_{n+1} - 19f_n)$ | $\displaystyle -\frac{3}{160}$  |

**米尔尼方法** $y_{n+4}=\displaystyle y_{n}+\frac{4h}{3}(2f_{n+3}-f_{n+2}+2f_{n+1}) $

局部截断误差 $ T_{n+4}=\displaystyle \frac{14}{45}h^5y^{(5)}(x_n)+O(h^6) $

**辛普森方法** $y_{n+2}=\displaystyle y_n+\frac h 3 (f_n+4f_{n+1}+f_{n+2}).$

局部截断误差 $ T_{n+2}=\displaystyle -\frac{h^5}{90}y^{(5)}(x_n)+O(h^6). $

**汉明方法** $y_{n+3}=\displaystyle \frac 1 8 (9y_{n+2}-y_n)+\frac{3h}8(f_{n+3}+2f_{n+2}-f_{n+1})$

局部截断误差 $ T_{n+3}=\displaystyle -\frac{h^5}{40}y^{(5)}(x_n)+O(h^6). $
