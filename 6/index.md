# **第六章 线性方程组——迭代法**

**定常迭代法**

对于线性方程组 $\mathbf{Ax=b}$ （ $\mathbf{A}$ 是非奇异矩阵 ），对 $\mathbf{A}$ 进行矩阵分裂： $\mathbf{A=M-N}$，其中 $\mathbf{M}$ 是可选择的非奇异矩阵

于是得到迭代式 $\mathbf{x=M^{-1}Nx+M^{-1}b=Bx+f}\Rightarrow \mathbf{x^{(k+1)}=Bx^{(k)}+f}$

**一阶线性定常迭代法**

即取 $\mathbf{M=I}$ 

**雅可比迭代法**

采用矩阵分裂： $\mathbf{A=M-N=D-(L+U)}$

其中 $\mathbf{D}$ 就是单独提出 $\mathbf{A}$ 的对角线， $\mathbf{L, U}$ 是 $\mathbf{A}$ 除去对角线后的下三角和上三角取负

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

**严格对角占优矩阵**

满足条件 $\sum_{j=1}^n\left|a_{ij}\right|<\left|a_{ii}\right|\quad,\quad i=1,2,\cdots,n$ ，则称矩阵A是严格对角占优矩阵。

雅可比迭代法和高斯-赛格尔迭代法都收敛

**收敛性**

迭代法收敛充要条件： $\rho(\mathbf{B})<1$ ，此时对任意初始向量 $\mathbf{x^{(0)}}=(x_1^{(0)}, x_2^{(0)}, \dots, x_n^{(0)})^T$，会收敛到真实解

用到矩阵分裂时，还要求 $\mathbf{D}$ 非奇异

另一个充分条件：对于迭代法 $\mathbf{x^{(k+1)}=Bx^{(k)}+f}$ 如果有 $\mathbf{B}$ 的某种算子范数 $\Vert\mathbf{B}\Vert=q<1$ ,则迭代法全局收敛，且有
- $\Vert x^*-x^{(k)}\Vert\leq q^k\Vert x^*-x^{(0)}\Vert$
- $\Vert x^*-x^{(k)}\Vert\leq\dfrac{q}{1-q}\Vert x^{(k)}-x^{(k-1)}\Vert$
- $\Vert x^*-x^{(k)}\Vert\leq\dfrac{q^k}{1-q}\Vert x^{(1)}-x^{(0)}\Vert$