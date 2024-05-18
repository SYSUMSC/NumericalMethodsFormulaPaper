### **第五章 解线性方程组直接方法**

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

**矩阵的 1-范数**：又称列范数，每一列中元素的绝对值之和的最大值 $\Vert \mathbf{A}\Vert_{1}=\displaystyle \max_{1\leqslant j\leqslant n}\left\{\sum_{i=1}^n|a_{ij}|\right\}$

**矩阵的 2-范数**：又称谱范数 $\Vert\mathbf{A}\Vert_2=\displaystyle \sqrt{\lambda_{max}}$，其中 $\lambda_{max}$ 是矩阵 $\mathbf{A^T A}$ 最大特征值

**矩阵的无穷范数**：又称行范数，每一行中元素的绝对值之和的最大值 $\Vert \mathbf{A}\Vert_{\infin}=\displaystyle \max_{1\leqslant i\leqslant n}\left\{\sum_{j=1}^n|a_{ij}|\right\}$

**矩阵的F-范数**：$\Vert \mathbf{A}\Vert_F=\displaystyle \sqrt{\sum_{i=1}^n\sum_{j=1}^n a_{ij}^2}$

**谱半径** $\rho(\mathbf{A})=\max|\lambda_i|$，对矩阵的任何一种相容范数都有 $\rho(\mathbf{A})\leqslant \Vert \mathbf{A} \Vert$
