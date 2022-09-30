## $Q R$-分解
### 定义 9.1
设$A \in \mathbb{C}^{n \times n}$。 $A=Q R$ 的分解，其中 $Q$ 是酉矩阵，而$R$  是上三角矩阵。这称为矩阵 $A$ 的 $QR$ 分解。
推论：由于$R=Q^{*} A$，则$\max _{i, j}\left|r_{i j}\right| \leqslant \max _{i, j} q_{i}^{*} a_{j} \leqslant\left\|a_{j}\right\|_{2} \leqslant \sqrt{n} \max _ {i, j}\left|a_{i j}\right|$.
### 定理 9.1 
对于任何方阵$A$，都存在 $QR$ 分解。
## 反射矩阵
### 定义 9.2 
矩阵$H=H(u)=I-2 u u^{*}$，其中$\|u\|_{2}=1$，称为反射矩阵或Householder矩阵。
反射矩阵最简单的性质：
- 矩阵 $H$ 是酉矩阵：$H H^{*}=\left(I-2 u u^{*}\right)\left(I-2 u u^{*}\right)^{*}=I- 4 u u^{*}+4 u\left(u^{*} u\right) u^{*}=I$。
- 矩阵 $H$ 是埃尔米特矩阵：$H^{*}=H$。
- $H u=-u, H v=v, \forall v \perp u$。

### 定理 9.2
对于任意长度相同的向量 $a, b \in \mathbb{C}^{n}$，存在一个数 $\gamma$ 和一个反射矩阵 $H$，使得
$$
H a=\gamma b, \quad|\gamma|=1 。
$$
使用反射消除元素
对于任何 $a \in \mathbb{C}^{n}$ 都存在一个反射矩阵 $H$ 使得
$$
H a=\gamma\left[\|a\|_{2}, 0, \ldots, 0\right]^{T}, \quad|\gamma|=1 。
$$
在这种情况下，矩阵 $H$ 由向量 $u=\frac{v}{\|v\|_{2}}$ 定义，其中 $v=\left[a_{1}-\gamma\ |a\|_ {2}, a_{2}, \ldots, a_{n}\right]^{T}$。如果 $a_{1} \neq 0$，则取 $\gamma=-\frac{a_{1}}{\left|a_{1}\right|}$。
### 定理 9.3
对于任何矩阵 $A \in \mathbb{C}^{n \times n}$ 存在反射矩阵 $H_{1}, \ldots, H_{n-1}$ 使得矩阵 $R=H_{n - 1} \ldots H_{1}A$ 是上三角形。
这里矩阵 $H_{i}$ 使用向量 $u_{i}$ 定义，其前 $i-1$ 分量为零：
$$
u_{i}^{T}=[0, \ldots, 0, *, \ldots, *] 。
$$
这样的向量指定了一个反射矩阵，它不会改变参数的第一个 $i-1$ 坐标。此外，让向量 $u_{i}$ 被选择，以便它取消（清零）矩阵 $H$ 的第 $n$ 列的编号为 $i+1、i+2、\ldots$ 的元素${i-1} \ldots H_{1}A$。结果将是一个上三角矩阵。

酉矩阵的乘积是酉矩阵。因此 $Z=H_{n-1} \ldots H_{1}-$ 是酉的，$A=Q R, Q=Z^{*}$。我们已经获得了 $Q R$ 展开的等价推导。
## 旋转矩阵
### 定义 9.3
如果矩阵 $G_{k l} \in \mathbb{R}^{n \times n}$ 在位于编号为 $k$ 和 $l$ 的行和列上与单位矩阵仅相差 $2 \times 2$ 子矩阵，则称为旋转矩阵或 Givens 矩阵
$$
M(\varphi)=\left[\begin{array}{cc}
\cos (\varphi) & -\sin (\varphi) \\
\sin (\varphi) & \cos (\varphi)
\end{array}\right],
$$
矩阵$G_{k l}$ 是正交的：$G_{k l} G_{k l}^{T}=I$。
如果向量 $\left[a_{1}, a_{2}\right]^{T} \in \mathbb{R}^{2}$ 非零，并且
$$
\cos (\varphi)=\frac{a_{1}}{\sqrt{a_{1}^{2}+a_{2}^{2}}}, \quad \sin (\varphi)=-\frac{a_{2}}{\sqrt{a_{1}^{2}+a_{2}^{2}}}，
$$
那么对应的旋转矩阵允许我们排除向量的第二个分量：
$$M(\varphi)\left[a_{1}, a_{2}\right]^{T}=[\alpha, 0]^{ T}, \alpha= \sqrt{a_{1}^{2}+a_{2}^{2}}$$

这个想法是基于使用旋转消除元素的方法得到矩阵$A$的$Q R$分解：将左边的矩阵$A$乘以旋转矩阵$G_{k l}$，可以得到0 在位于第 $k$  或第 $l$ 行和第 $k$ 或第 $l$ 列的任何位置。这意味着矩阵 $A$ 可以使用从左边乘以旋转矩阵序列的方法简化为上三角形式 $R$：
$$
G_{n, n-1} \ldots G_{n 1} \ldots G_{31} G_{21} A=R \text {. }
$$
这里矩阵 $G_{i j}$ 将位置 $(i, j)$ 处的元素设置为零。
## 改进的 Gram-Schmidt 方法 
### 常规算法:
对于 $j=1, \ldots, k$ : 
$$
p_{j}=a_{j}
$$
对于 $i=1, \ldots, j-1$ : 
$$ 
p_{j}=p_{j}-q_{i}\left(q_{i}^{*} a_{j}\right)\\
q_{j}=\frac{p_{j}}{\left\|p_{j}\right\|_{2}}
$$
### 修改后的算法:
对于每个 $j=1, \ldots, k$ ：
$$
p_{j}^{(0)}=a_{j}
$$
对于每个 $m=1,2, \ldots, M$ ：
对于每个 $i=1, \ldots, j-1$ ：
$$
p_{j}^{(m)}=p_{j}^{(m-1)}-q_{i}\left(q_{i}^{*} p_{j}^{(m-1)}\right) \\
q_{j}= \frac{p_{j}^{(M)}}{\left\|p_{j}^{(M)}\right\|_{2}}
$$