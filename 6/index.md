# **第六章 线性方程组——迭代法**

**定常迭代法**

对于线性方程组 $\mathbf{Ax=b}$ （ $\mathbf{A}$ 是非奇异矩阵 ），对 $\mathbf{A}$ 进行矩阵分裂： $\mathbf{A=M-N}$，其中 $\mathbf{M}$ 是可选择的非奇异矩阵

于是得到迭代式 $\mathbf{x=M^{-1}Nx+M^{-1}b=Bx+f}\Rightarrow \mathbf{x^{(k+1)}=Bx^{(k)}+f}$

迭代法收敛充要条件： $\lim_{k\to\infty}B^k=0$ 或 $\rho (B)<1$ ,其中 $\rho (B)$ 称为矩阵B的谱半径

设n维矩阵B的n个特征值为 $\lambda_1,\lambda_2,\ldots,\lambda_n$ , $\rho(B)=\displaystyle \max_{1\leq i\leq n}\lvert\lambda_i\rvert $

**一阶线性定常迭代法**
取 $\mathbf{M=I}$ 时，若 $\rho(\mathbf{B})<1$ ，则对任意初始向量 $\mathbf{x^{(0)}}=(x_1^{(0)}, x_2^{(0)}, \dots, x_n^{(0)})^T$，会收敛到真实解

**雅可比迭代法**

采用矩阵分裂： $\mathbf{A=M-N=D-(L+U)}$

则 $\mathbf{x^{(k+1)}=D^{-1}(L+U)x^{(k)}+D^{-1}b=B_J x+f}$

$\mathbf{x^{(k+1)}}$ 可由以下公式得到：

$$
x^{(k+1)}_i=\frac{1}{a_{ii}}\Bigg(b_{i}-\sum_{j=1, j\neq i}^{n}a_{ij}x_{j}^{(k)}\Bigg)
$$

**高斯-赛格尔迭代法**

采用矩阵分裂： $\mathbf{A=M-N=(D-L)-U}$

则 $\mathbf{Dx^{(k+1)}=Lx^{(k+1)}+Ux^{(k)}+b}$

$\mathbf{x^{(k+1)}}$ 可由以下公式得到：

$$
x_i^{(k+1)}=\frac{-1}{a_{ii}}(\sum_{j=1}^{i-1}a_{ij}x_j^{(k+1)}+\sum_{j=i+1}^{n}a_{ij}x_j^{(k)}-b_i)
$$

**逐次超松驰迭代法（SOR）**

引入松弛因子 $\omega, \omega>0$ 采用矩阵分裂： $\displaystyle \mathbf{A=M-N}=\frac 1 \omega(\mathbf{D}-\omega\mathbf{L})-\frac 1 \omega[(1-\omega)\mathbf{D}+\omega\mathbf{U}]$

则 $\mathbf{Dx^{(k+1)}=Dx^{(k)}}+\omega\mathbf{(b+Lx^{(k+1)}+Ux^{(k)}-Dx^{(k)})}$

$\mathbf{x^{(k+1)}=(D-\omega L)^{-1}\{(1-\omega)D+\omega U\}x^{(k)}+\omega(D-\omega L)^{-1}b}$

$\mathbf{x^{(k+1)}}$ 可由以下公式得到：

$$
x_i^{(k+1)}=x_i^{(k)}+\omega\Bigg(b_i-\sum_{j=1}^{i-1}a_{ij}x_j^{(k+1)}-\sum_{j=i}^na_{ij}x_j^{(k)}\Bigg)/a_{ii}
$$

**误差估计**
对于 $x^{(k+1)}=Bx^{(k)}+f$ 如果有 $B$ 的某种算子范数 $\|B\|=q<1$ ,则
1. 迭代法全局收敛
2. $\begin{Vmatrix}x^*-x^{(k)}\end{Vmatrix}\leq q^k\begin{Vmatrix}x^*-x^{(0)}\end{Vmatrix}$
3. $\begin{Vmatrix}x^*-x^{(k)}\end{Vmatrix}\leq\dfrac{q^k}{1-q}\begin{Vmatrix}x^{(1)}-x^{(0)}\end{Vmatrix}$

**严格对角占优矩阵**

满足条件 $\sum_{j=1}^n\left|a_{ij}\right|<\left|a_{ii}\right|\quad,\quad i=1,2,\cdots,n$ ，则称矩阵A是严格对角占优矩阵。

雅可比迭代法和高斯-赛格尔迭代法都收敛