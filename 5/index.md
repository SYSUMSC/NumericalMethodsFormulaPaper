# **第五章 线性方程组——直接法**

**高斯消元法**：通过基本变换，将增广矩阵转化为阶梯型矩阵：

$$
[\mathbf{A:b}]=\begin{bmatrix}
a_{11}^{(1)} & a_{12}^{(1)} & a_{13}^{(1)} &\cdots & a_{1n}^{(1)} & b_1^{(1)} \\
0 & a_{22}^{(2)} & a_{23}^{(2)} & \cdots &  a_{2n}^{(2)} & b_2^{(2)} \\
0 & 0 & a_{33}^{(3)} & \cdots & a_{3n}^{(3)} & b_2^{(3)} \\
\vdots & \vdots & \vdots & \ddots & \vdots & \vdots \\
0 & 0 & 0 & \cdots &a_{nn}^{(n)} & b_n^{(n)}
\end{bmatrix}
$$

若 $a_{kk}^{(k)}\neq 0$ ，则 $\displaystyle x_n=({b_k^{(k)}-\sum_{j=k+1}^{n}a_{kj}^{(k)}x_j})/({a_{kk}^{(k)}})$

**LU 分解**：高斯消元法的每一步初等变换相当于一个初等矩阵左乘原矩阵，最终得到一个上三角阵 $\mathbf{L_{n-1}\dots L_2L_1A=U}$

所以 $\mathbf{A=L_1^{-1}L_2^{-1}\dots L_{n-1}^{-1}U=LU}$ ，其中 $\mathbf{L}$ 是下三角阵：

$$
\mathbf{L}=\begin{bmatrix}
1 & 0 & 0 &\cdots & 0 \\
m_{21} & 1 & 0 & \cdots &  0 \\
m_{31} & m_{32} & 1 & \cdots & 0 \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
m_{n1} & m_{n2} & m_{n3} & \cdots & 1
\end{bmatrix}
$$

则原方程组等价于 $\mathbf{Ux=y, Ly=b}$ ，这个方程组可按下述过程解出：

$$
y_i=b_i-\sum_{k=1}^{i-1}l_{ik}y_k,\ x_i=(\displaystyle y_i-\sum_{k=i+1}^nu_{ik}x_k)/(u_{ii})
$$

**平方根法**：设 $\mathbf{A}$ 是对称正定矩阵，则一定有唯一分解 $\mathbf{A=LU}$ ，且 $u_{kk}>0$

则有 Cholesky 分解 $\mathbf{A=LU=LDL^T=LD^{1/2} D^{1/2} L^T=G G^T}$，其中

$$
\mathbf{D^{1/2}}=
\begin{bmatrix}
\sqrt{u_{11}} & 0 & 0 & \cdots & 0 \\
0 & \sqrt{u_{22}} & 0 & \cdots & 0 \\
0 & 0 & \sqrt{u_{33}} & \cdots & 0 \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
0 & 0 & 0 & \cdots & \sqrt{u_{nn}}
\end{bmatrix}
$$

Cholesky 分解后，类似 LU 分解的过程得到最终解

**矩阵范数**：如果矩阵 $\mathbf{A}\in R^{n\times n}$ 与某个非负的实值函数 $N(\mathbf{A})=\Vert\mathbf{A}\Vert$ 满足正定性、齐次性、三角不等式以及相容性，则称 $N(\mathbf{A})$ 是一个矩阵范数

**相容性**：$\Vert \mathbf{Ax}\Vert\leqslant \Vert \mathbf{A}\Vert \Vert \mathbf{x}\Vert$。其中 $\Vert \mathbf{A}\Vert$ 矩阵范数， $\Vert \mathbf{Ax}\Vert, \Vert \mathbf{x}\Vert$ 是向量范数。只有满足这个不等式，才说这个矩阵范数和这个向量范数是相容的。

**算子范数（从属矩阵范数）**：$\Vert \mathbf{A}\Vert =\displaystyle \max_{\Vert \mathbf{x}\Vert=1}\{\Vert\mathbf{Ax}\Vert\}=\max_{\mathbf{x\neq 0}}\frac{\Vert \mathbf{Ax\Vert}}{\Vert \mathbf{x} \Vert}$ ，其中 $\Vert\mathbf{Ax}\Vert$ 是某个向量范数。算子范数度量了矩阵 $\mathbf{A}$ 将向量 $\mathbf{x}$ 映射到新向量 $\mathbf{Ax}$ 的"放大"程度。

由不同的向量范数可以导出不同的算子范数：

- **1-范数**：又称列范数，每一列中元素的绝对值之和的最大值 $\Vert \mathbf{A}\Vert_{1}=\displaystyle \max_{1\leqslant j\leqslant n}\left\{\sum_{i=1}^n|a_{ij}|\right\}$

- **2-范数**：又称谱范数 $\Vert\mathbf{A}\Vert_2=\displaystyle \sqrt{\lambda_{max}}$，其中 $\lambda_{max}$ 是矩阵 $\mathbf{A^T A}$ 最大特征值

- **无穷范数**：又称行范数，每一行中元素的绝对值之和的最大值 $\Vert \mathbf{A}\Vert_{\infin}=\displaystyle \max_{1\leqslant i\leqslant n}\left\{\sum_{j=1}^n|a_{ij}|\right\}$

其他种类的范数：

- **F-范数**：$\Vert \mathbf{A}\Vert_F=\displaystyle \sqrt{\sum_{i=1}^n\sum_{j=1}^n a_{ij}^2}$

**谱半径** $\rho(\mathbf{A})=\max|\lambda_i|$，其中 $\lambda_i$ 是 $\mathbf{A}$ 的特征值

对矩阵的任何一种相容范数都有 $\rho(\mathbf{A})\leqslant \Vert \mathbf{A} \Vert$
