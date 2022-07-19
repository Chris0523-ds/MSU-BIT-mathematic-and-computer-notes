## 解决问题的直接方法(прямые методы)
数学问题的解决可以表示为基于一些基本操作集制定的算法。如果需要有限数量的基本操作来解决问题，那么这种方法称为**直接方法**。

示例：如果将算术运算 $(+,-, \cdot, \div)$ 视为基本运算，则方程 $x^{2}=2$ 无法使用有限次数的运算求解。如果我们加上“一个数的平方根”运算，那么就会有解决问题的直接方法。

评论。使用算术运算和根提取，不可能构造一个直接的方法来找到一个任意次数的多项式的根 $\geqslant 5 \Rightarrow$ 没有直接的方法来计算一个任意阶矩阵的特征值$\geqslant 5 .$

有解决线性方程组 $A x=b$ （在一般情况下，对于没有任何细节的密集矩阵） 的直接方法。作为基本运算，我们将使用算术运算，有时还会使用提取平方根的运算。求解线性方程组的最简单直接方法是高斯方法和使用旋转或反射变换的方法。这些方法与获得系数矩阵的$L U$-分解或$Q R$-分解有关。
## LU-分解
### 定义 8.1
如果矩阵 $A$ 的所有前导子矩阵（包括 $A$ 本身）都是非退化的，则称矩阵 $A$ 是**严格正则**的。
$$
A=\left(\begin{array}{ccc}
a_{11} & a_{12} & \ldots \\
a_{21} & a_{22} & \ldots \\
\ldots & \ldots & \ldots
\end{array}\right) \Rightarrow a_{11} \neq 0,\left|\begin{array}{ll}
a_{11} & a_{12} \\
a_{21} & a_{22}
\end{array}\right| \neq 0, \ldots \operatorname{det}(A) \neq 0 .
$$
矩阵 $A$ 的 $L U$ 分解是 $A=L U$ 形式的等式，其中
* 矩阵 $L$ - 下三角矩阵，对角线为 1 ；
* 矩阵 $U$ 是一个非退化的上三角矩阵。

有时 $L U$ 分解以不同的方式定义：矩阵 $L$ 是非退化下三角矩阵，$U$ 是具有单位对角线的上三角矩阵。
1) $L=\left(\begin{array}{cccc}1 & 0 & \ldots & 0 \\ l_{21} & 1 & \ldots & 0 \\ \ldots & \ldots & \ldots & \ldots \\ l_{n 1} & l_{n 2} & \ldots & 1\end{array}\right) U=\left(\begin{array}{cccc}u_{11} & u_{12} & \ldots & u_{1 n} \\ 0 & u_{22} & \ldots & u_{2 n} \\ \ldots & \ldots & \ldots & \ldots \\ 0 & 0 & \ldots & u_{n n}\end{array}\right) \quad$

第二种表达： 
1) $L=\left(\begin{array}{cccc}l_{11} & 0 & \ldots & 0 \\ l_{21} & l_{22} & \ldots & 0 \\ \ldots & \ldots & \ldots & \ldots \\ l_{n 1} & l_{n 2} & \ldots & l_{n n}\end{array}\right) U=\left(\begin{array}{cccc}1 & u_{12} & \ldots & u_{1 n} \\ 0 & 1 & \ldots & u_{2 n} \\ \ldots & \ldots & \ldots & \ldots \\ 0 & 0 & \ldots & 1\end{array}\right)$

## $L U$-分解的存在性
### 定理 8.1
对于矩阵 $A$ 进行 LU 分解，它必须是严格正则的。
### 证明
需求：如果 $A=L U$，则矩阵 $A$ 以及它的任何前导子矩阵 $B$ 可以表示为两个非退化（下和上）三角矩阵 $\Rightarrow$ 的乘积矩阵 $A, B-$ 是非退化的 $ \Rightarrow A-$ 是严格正则的。
充分性：通过对矩阵 $A$ 大小的归纳证明。让
$$
\begin{gathered}
A=\left[\begin{array}{ll}
a & c^{T} \\
b & D
\end{array}\right], \quad a \neq 0, \quad z=\frac{1}{a} b, A_{1}=D-\frac{1}{a} b c^{T} . \\
\Rightarrow\left[\begin{array}{cc}
1 & 0 \\
-z & I
\end{array}\right]\left[\begin{array}{ll}
a & c^{T} \\
b & D
\end{array}\right]=\left[\begin{array}{ll}
a & c^{T} \\
0 & A_{1}
\end{array}\right],
\end{gathered}
$$
矩阵 $A_{1}$ 是严格正则的。根据归纳假设，$A_{1}$ 有一个 $L U$ 分解：$A_{1}=L_{1} U_{1}$。让
$$
\begin{gathered}
L=\left[\begin{array}{cc}
1 & 0 \\
z & L_{1}
\end{array}\right], \quad U=\left[\begin{array}{cc}
a & c^{T} \\
0 & U_{1}
\end{array}\right] \\
\Rightarrow L U=\left[\begin{array}{cc}
a & c^{T} \\
b & L_{1} U_{1}+\frac{1}{a} b c^{T}
\end{array}\right]=\left[\begin{array}{ll}
a & c^{T} \\
b & D
\end{array}\right]=A .
\end{gathered}
$$
## 定理 8.2
LU 分解是唯一定义的。
### 证明 
如果 $L_{1} U_{1}=L_{2} U_{2}$，那么让
$$
D=L_{2}^{-1} L_{1}=U_{2} U_{1}^{-1} 。
$$
矩阵 $L_{2}^{-1}$ 和 $L_{2}^{-1} L_{1}-$ 是下三角矩阵。 矩阵 $U_{1}^{-1}$ 和 $U_{2} U_{1}^{-1}-$ 是上三角矩阵。 因此 $D-$ 是上下三角形 $\Rightarrow D-$ 对角线。 但是矩阵 $L_{2}^{-1} L_{1}$ 在对角线上有 1 $\Rightarrow D=I \Rightarrow L_{1}=L_{2}$, $U_{1}=U_{ 2}$
## $L U$展开与高斯方法的关系
在代数课程中学习了求解线性方程组$A x=b$ 的高斯方法。它包括两个主要步骤：
1. 直接移动：使用基本变换简化为具有上阶梯（三角）矩阵的系统。
2. 反向移动：求解具有阶梯（三角）矩阵的线性方程组。

令矩阵 $A$ 是非退化的方阵。则对于矩阵高斯方法可以描述如下：
1. 直接方法 ：搜索下三角矩阵 $L$，其对角线为 1，使得 $U x=L^{-1} A x=L^{-1} b -$ 上三角矩阵系统。

2、反向移动：求解线性方程组 $U x=L^{-1} b$，即寻找$x=U^{-1} L^{-1} b$。
即$A=L U$。
如果矩阵$A$的$L U-$分解已知，那么很容易找到矩阵$L^{-1}$和$U^{-1}$。因此，可以求解具有不同右手边 $b$ 的线性方程组：
$$
A x=b, A=L U \Rightarrow x=U^{-1} L^{-1} b 。
$$
## 主项的选择
从所得的舍入误差估计可以看出，高斯算法的“瓶颈”是项 $|\tilde{L}| \cdot|\tilde{U}|$ 在右侧。也就是说，由于三角因子中元素的增长，可能会导致较大的误差。
例子。设$n=2$, $p$为算术基数，$t$为尾数长度。令：
$$
A=\left[\begin{array}{cc}
p^{-t} & 1 \\
1 & 1
\end{array}\right] \Rightarrow \tilde{L}=\left[\begin{array}{cc}
1 & 0 \\
p^{t} & \tilde{L}_{1}
\end{array}\right], \tilde{U}=\left[\begin{array}{cc}
p^{-t} & 1 \\
0 & \tilde{U}_{1}
\end{array}\right]
$$
令 $\mathrm{f}\left(1-p^{t}\right)=-p^{t}\left(p^{t}-\right.$ 是一个很大的数 $)$。那么$\tilde{L}_{1}=1, \tilde{U}_{1}=-p^{t}$,
$$
\tilde{L} \tilde{U}-A=\left[\begin{array}{ll}
0 & 0 \\
0 & 1
\end{array}\right] .
$$
有一个非常大的错误。原因是前导项$a=p^{-t}$ 的值非常小。

由于 $\tilde{L}_{1} \tilde{U}_{1}=\mathrm{fl}\left(D-\frac{1}{a} b c^{T}\right)$，那么为了减少矩阵 $\tilde{L}_{1}$ 和 $\tilde{U}_{1}$ 并使误差更小，应选择尽可能大的前导项 $a$。例如，通过置换矩阵 $A$ 中的行。

如果我们使用矩阵 $A$ 的行的附加排列（以增加前导项），则结果是矩阵的 $L U P$-分解：
$$
P A=L U
$$
其中，$P$ 是置换矩阵。
## $L D L$-分解，乔列斯基分解
### 定理 8.4
如果矩阵 $A \in \mathbb{C}^{n \times n}$ 是严格正则且对称的 $\left(A=A^{T}\right)$，则它有 $L D L^{T} $-分解：$A=L D L^{T}$，其中$L$是单位对角线的下三角形； $D$ -非退化对角线。

下面的定理可以类似地证明：
### 定理 8.5。
如果矩阵 $A \in \mathbb{C}^{n \times n}$ 是严格正则的并且是 Hermitian $\left(A=A^{*}\right)$，那么它有 $L D L^{*} $-分解：$A=L D L^{*}$，其中$L$是单位对角线的下三角形； $D$ 是非退化对角线。

### 定义 8.2
令$C$ 为具有正主对角线的下三角矩阵。 $A=C C^{*}$ 的分解称为 Cholesky 分解。

### 定理 8.6
对于矩阵$A \in \mathbb{C}^{n \times n}$ 有一个Cholesky 分解，它是Hermitian 与正前导小数是必要且充分的。

让我们证明充分性。令 $A=L D L^{T}$ (或 $\left.A=L D L^{*}\right), D=\operatorname{diag}\left(d_{1}, \ldots, d_{n}\right)$。假设 $C=L \operatorname{diag}\left(\sqrt{d_{1}}, \ldots, \sqrt{d_{n}}\right)$。那么$A=C C^{T}$（或$\left.A=C C^{*}\right)$。

## 乔列斯基方法
令 $A$ 是一个实数对称矩阵，具有正前导小数。让我们为其构造 Cholesky 分解。
例子。设$n=3$，
$$
\left[\begin{array}{lll}
a_{11} & a_{21} & a_{31} \\
a_{21} & a_{22} & a_{32} \\
a_{31} & a_{32} & a_{33}
\end{array}\right]=\left[\begin{array}{ccc}
c_{11} & 0 & 0 \\
c_{21} & c_{22} & 0 \\
c_{31} & c_{32} & c_{33}
\end{array}\right] \cdot\left[\begin{array}{ccc}
c_{11} & c_{21} & c_{31} \\
0 & c_{22} & c_{32} \\
0 & 0 & c_{33}
\end{array}\right]
$$
我们依次将第 1 个矩阵的元素乘以第 2 个矩阵的第 1、2、3 列。然后
$$
\begin{gathered}
c_{11}=\sqrt{a_{11}}, \quad c_{21}=\frac{a_{21}}{c_{11}}, \quad c_{31}=\frac{a_{31}}{c_{11}} \\
c_{22}=\sqrt{a_{22}-c_{21}^{2}}, \quad c_{32}=\frac{a_{32}-c_{31} c_{21}}{c_{22}} \\
c_{33}=\sqrt{a_{33}-c_{31}^{2}-c_{32}^{2}}
\end{gathered}
$$
通常，乔列斯基算法如下所示：
对于每个 $k=1, \ldots, n$ ：
- 计算对角线元素：
$$
c_{k k}=\left(a_{k k}-\sum_{j=1}^{k-1} c_{k j}^{2}\right)^{1 / 2}
$$
- 对于每个 $i=k+1, \ldots, n$ ：
$$
c_{i k}=\left(a_{i k}-\sum_{j=1}^{k-1} c_{i j} c_{k j}\right) / c_{k k}
$$
假设这些表达式的求值方式使得任何算术运算的相对误差 $\varepsilon$ 和提取根的运算都由估计值 $|\varepsilon|  \leqslant\eta$ 提供。

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