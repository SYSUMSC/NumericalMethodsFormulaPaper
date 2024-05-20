### **第六章 解线性代数方程组的迭代法**
**迭代法及其收敛性**

- $x=B_0x+f$
- $x^{k+1}=B_0x^{k}+f$

**雅可比迭代**

$\sum_{j=0}^{n}a_{ij}x_j=b_i$

$Ax=b$，A为非奇异阵且$a_{ij}≠0$，将A分裂为$A=D-L-U$

$x_i=\frac{1}{a_ii}(b_i-\sum_{j=1,j≠i}^{n}a_{ij}x_j)$ 

简记为 $x=B_0x+f$

其中 $B_0=D^{-1}(L+U)，f=D^{-1}b$

雅可比迭代公式

$x^{(0)}=\left(x_{1}^{(0)},x_{2}^{(0)},...,x_{n}^{(0)}\right)^{T}$

$x^{k+1}=\frac{1}{a_{ii}}\Bigg(b_{i}-\sum_{(i=1)}^{n}a_{ij}x_{j}^{(k)}\Bigg)$


高斯-赛格尔迭代

$x^0$同上

$\mathrm{x}_{\mathrm{i}}^{(k+1)}=\frac{1}{a_{ii}}\Bigg(b_{i}-\sum_{(j=1)}^{i-1}a_{ij}x_{j}^{(k+1)}-\sum_{(j=i+1)}^{n}a_{ij}x_{j}^{(k)}\Bigg)(\mathrm{k}=0,1,2,...;\mathrm{i}=1,2,...,\mathrm{n})$

或改写为

$$
\begin{aligned}&\begin{cases}x^{(k+1)}=x_i^{(k)}+\Delta x_i\big(k=0,1,2,...;i=1,2,...,n\big),\\\Delta x_i=\frac{1}{a_{ii}}\Big(b_i-\sum_{(j=1)}^{i-1}a_{ij}x_i^{(k+1)}-\sum_{(j=i)}^{n}a_{ij}x_j^{(k)}\Big).\end{cases}\end{aligned}
$$

$$
\begin{gathered}
\mathrm{x}^{(\mathrm{k}+1)}=Gx^{(k)}+f, \\
\mathrm{G=(D-L)^{-1}}U,F=(D-L)^{-1}b. 
\end{gathered}
$$

逐次超松驰(SOR)迭代法

$$
\begin{cases}x^{(0)}=(x_1^{(0)},\cdots,x_n^{(0)})^\mathrm{T},\\x_i^{(k+1)}=x_i^{(k)}+\omega\Bigg(b_i-\sum_{j=1}^{i-1}a_{ij}x_j^{(k+1)}-\sum_{j=i}^na_{ij}x_j^{(k)}\Bigg)/a_{ii},\\(i=1,2,\cdots,n),\\\text{松弛因子 }\omega>0.\end{cases}
$$