### **第五章 解线性方程组直接方法**

#### LU分解

$$\begin{aligned}&U=A^{(n)}=L_{n-1}\cdots L_{2}L_{1}A\\&L=L_{1}^{-1}L_{2}^{-1}\cdots L_{n-1}^{-1}=\begin{bmatrix}1\\m_{21}&1\\m_{31}&m_{32}&1\\\vdots&\vdots&\vdots&\ddots\\m_{n1}&m_{n2}&m_{n3}&\cdots&1\end{bmatrix}\\&\begin{cases}Ly&=b\\Ux&=y\end{cases}\end{aligned}$$