### **第五章 解线性方程组直接方法**

#### LU分解

$$\begin{aligned}&U=A^{(n)}=L_{n-1}\cdots L_{2}L_{1}A\\&L=L_{1}^{-1}L_{2}^{-1}\cdots L_{n-1}^{-1}=\begin{bmatrix}1\\m_{21}&1\\m_{31}&m_{32}&1\\\vdots&\vdots&\vdots&\ddots\\m_{n1}&m_{n2}&m_{n3}&\cdots&1\end{bmatrix}\\&\begin{cases}Ly&=b\\Ux&=y\end{cases}\end{aligned}$$

**平方根法**

设A为对称正定矩阵, 则有唯一分解A=LU, 且$u_{kk}>0$

则有 $A{=}LDM{=}LDL^\mathrm{T}$

$$\begin{aligned}D=&\begin{pmatrix}\sqrt{u_{11}}&&&&\\&\sqrt{u_{22}}&&&\\&&\ddots&&\\&&&\sqrt{u_{m}}\end{pmatrix}\begin{pmatrix}\sqrt{u_{11}}&&&\\&\sqrt{u_{22}}&&\\&&\ddots&\\&&&\sqrt{u_{nm}}\end{pmatrix}\\&=D^{\frac12}D^{\frac12}\end{aligned}$$

Cholesky分解：$A=LD^\frac12D^\frac12L^\mathrm{T}=(LD^\frac12)(LD^\frac12)^\mathrm{T}=GG^\mathrm{T}$


#### 向量范数

$$\begin{aligned}
&\left\|x\right\|_{\infty}=\max_{1\leq i\leq n}\left|x_{i}\right| \\
&\left\|x\right\|_1=\sum_{i=1}^n\left|x_i\right| \\
&\left\|x\right\|_2=(\sum_{i=1}^nx_i^2)^{\frac12} 
\end{aligned}$$

#### 矩阵范数

$$\begin{aligned}
&\left\|A\right\|_{\infty}=\max_{1\leq i\leq n}\sum_{j=1}^{n}\left|a_{ij}\right| \\
&\left\|A\right\|_1=\max_{1\leq j\leq n}\sum_{i=1}^n\left|a_{ij}\right| \\
&\left\|A\right\|_{2}=\sqrt{\lambda_{\max}\left(A^{\mathrm{T}}A\right)} \\
&\left\|A\right\|_{\mathrm{F}}=\sqrt{\sum_{i,j=1}^{n}a_{ij}^{2}}
\end{aligned}$$

**谱半径**  $\rho(A)=\max_{1\leq i\leq n}\left|\lambda_i\right|$