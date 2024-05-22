### **第九章 常微分方程初值问题的数值解法**

$$
\begin{aligned}&\text{利普希兹条件}|f(x,y_1)-f(x,y_2)|\leq|y_1-y_2|,L>0\\&\text{前向欧拉法:}\frac{y_{n+1}-y_n}{x_{n+1}-x_n}=f(x_n,y_n),\text{即}y_{n+1}=y_n+hf(x_n,y_n)\\&\text{后向欧拉法:}\frac{y_{n+1}-y_n}{x_{n+1}-x_n}=f(x_{n+1},y_{n+1}),\text{即}y_{n+1}=y_n+hf(x_{n+1},y_{n+1})\\&\text{梯形方法:}y_{n+1}=y_n+\frac h2[f(x_n,y_n)+f(x_{n+1},y_{n+1})]\end{aligned}
$$

$\text{改进欧拉法:}\left\{\begin{array}{c}y_p=y_n+hf(x_n,y_n)\\y_c=y_n+hf(x_{n+1},y_p)\\y_{n+1}=(y_p+y_c)/2\end{array}\right.$

$\left.\text{中点公式:}\left\{\begin{array}{c}y_{n+1}=y_n+hK_2\\K_1=f(x_n,y_n)\\K_2=f(x_n+\frac h2,y_n+\frac h2K_1)\end{array}\right.\right.$

$\text{通式显式龙格-库塔法:}\left\{\begin{array}{c}\phi(x_n,y_n,h)=\sum_{i=1}^rc_iK_i\\K_1=f(x_n,y_n)\\K_i=f(x_n+\lambda_ih,y_n+h\sum_{j=1}^{i-1}\mu_{ij}K_j),i=2,\ldots,r\end{array}\right.$

$\text{二阶显式龙格-库塔法:}\begin{cases}&y_{n+1}=y_n+h(c_1K_1+c_2K_2)\\&K_1=f(x_n,y_n)\\&K_2=f(x_n+\lambda_2h,y_n+\mu_{21}hK_1)\end{cases}$

$\text{三阶经典龙格-库塔法:}\begin{aligned}&y_{n+1}=y_n+\frac{h}{6}(K_1+4K_2+K_3)\\&K_1=f(x_n,y_n)\\&K_2=f(x_n+\frac{h}{2},y_n+\frac{h}{2}K_1)\\&K_3=f(x_n+h,y_n-hK_1+2hK_2)\end{aligned}$


$\left.\text{四阶经典龙格-库塔法}\\\left\{\begin{array}{c}y_{n+1}=y_n+\frac{h}{6}(K_1+2K_2+2K_3+K_4)\\K_1=f(x_n,y_n)\\K_2=f(x_n+\frac{h}{2},y_n+\frac{h}{2}K_1)\\K_3=f(x_n+\frac{h}{2},y_n+\frac{h}{2}K_2)\\K_4=f(x_n+h,y_n+hK_3)\end{array}\right.\right.$