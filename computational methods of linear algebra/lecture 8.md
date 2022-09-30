## 解决问题的直接方法(прямые методы)
数学问题的解决可以表示为基于一些基本操作集制定的算法。如果需要有限数量的基本操作来解决问题，那么这种方法称为**直接方法(прямый метод)**。

示例：如果将算术运算 $(+,-, \cdot, \div)$ 视为基本运算，则方程 $x^{2}=2$ 无法使用有限次数的运算求解。如果我们加上“一个数的平方根”运算，那么就会有解决问题的直接方法。

评论。使用算术运算和根提取，不可能构造一个直接的方法来找到一个任意次数的多项式的根 $\geqslant 5 \Rightarrow$ 没有直接的方法来计算一个任意阶矩阵的特征值$\geqslant 5 .$

有解决线性方程组 $A x=b$ （在一般情况下，对于没有任何细节的密集矩阵） 的直接方法。作为基本运算，我们将使用算术运算，有时还会使用提取平方根的运算。求解线性方程组的最简单直接方法是高斯方法和使用旋转或反射变换的方法。这些方法与获得$L U$-分解或$Q R$-分解的系数矩阵有关。
## $LU$-分解
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
* 矩阵 $L$ 是下三角矩阵，对角线为 1 ；
* 矩阵 $U$ 是一个非退化的上三角矩阵。

有时 $L U$ 分解以不同的方式定义：矩阵 $L$ 是非退化下三角矩阵，$U$ 是具有单位对角线的上三角矩阵。
1）
$L=\left(\begin{array}{cccc}1 & 0 & \ldots & 0 \\ l_{21} & 1 & \ldots & 0 \\ \ldots & \ldots & \ldots & \ldots \\ l_{n 1} & l_{n 2} & \ldots & 1\end{array}\right) U=\left(\begin{array}{cccc}u_{11} & u_{12} & \ldots & u_{1 n} \\ 0 & u_{22} & \ldots & u_{2 n} \\ \ldots & \ldots & \ldots & \ldots \\ 0 & 0 & \ldots & u_{n n}\end{array}\right) \quad$

第二种表达： 
2）
$L=\left(\begin{array}{cccc}l_{11} & 0 & \ldots & 0 \\ l_{21} & l_{22} & \ldots & 0 \\ \ldots & \ldots & \ldots & \ldots \\ l_{n 1} & l_{n 2} & \ldots & l_{n n}\end{array}\right) U=\left(\begin{array}{cccc}1 & u_{12} & \ldots & u_{1 n} \\ 0 & 1 & \ldots & u_{2 n} \\ \ldots & \ldots & \ldots & \ldots \\ 0 & 0 & \ldots & 1\end{array}\right)$

## $L U$-分解的存在性
### 定理 8.1
对于矩阵 $A$ 进行 $LU$分解，它必须是严格正则的。
### 证明
必要性：如果 $A=L U$，则矩阵 $A$ 以及它的任何前导子矩阵 $B$ 可以表示为两个非退化（下和上）三角矩阵 $\Rightarrow$ 的乘积矩阵 $A, B-$ 是非退化的 $ \Rightarrow A-$ 是严格正则的。
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
对于任意矩阵，$LU$ 分解是唯一定义的。
### 证明 
如果 $L_{1} U_{1}=L_{2} U_{2}$，那么让
$$
D=L_{2}^{-1} L_{1}=U_{2} U_{1}^{-1} 。
$$
矩阵 $L_{2}^{-1}$ 和 $L_{2}^{-1} L_{1}-$ 是下三角矩阵。 矩阵 $U_{1}^{-1}$ 和 $U_{2} U_{1}^{-1}-$ 是上三角矩阵。 因此 $D-$ 是上下三角形 $\Rightarrow D-$ 对角线。 但是矩阵 $L_{2}^{-1} L_{1}$ 在对角线上有 1 $\Rightarrow D=I \Rightarrow L_{1}=L_{2}$, $U_{1}=U_{ 2}$
## $L U$展开与高斯方法的关系
在代数课程中学习了求解线性方程组$A x=b$ 的高斯方法。它包括两个主要步骤：
1. **正行程(прямой ход)**：使用基本变换简化为具有上三角阶梯的矩阵系。
2. **回程(обратный ход)**：求解具有阶梯（三角）矩阵的线性方程组。

令矩阵 $A$ 是非退化的方阵。则对于矩阵高斯方法可以描述如下：
1.正行程：搜索下三角矩阵 $L$，其对角线为 1，使得 $U x=L^{-1} A x=L^{-1} b $ 是上三角矩阵系。
2.回程：求解线性方程组 $U x=L^{-1} b$，即寻找 $x=U^{-1} L^{-1} b$。
即$A=L U$。
如果矩阵 $A$ 的 $LU$ 分解已知，那么很容易找到矩阵 $L^{-1}$和 $U^{-1}$。因此，可以求解具有不同右手边 $b$ 的线性方程组：
$$
A x=b, A=L U \Rightarrow x=U^{-1} L^{-1} b 。
$$
## $L U$ 分解的舍入错误
### 定理 8.3 
令$A$ 是一个可以用机器算术表示的 n 阶实数严格正则矩阵，那么对于实际计算的矩阵 $\tilde{L},\tilde{U}$，以下不等式成立：
$$
|\tilde{L} \tilde{U}-A| \leqslant 3 n \eta(|A|+|\tilde{L}| \cdot|\tilde{U}|)+\mathcal{O}\left(\eta^{2}\right) .
$$
## 选择主项 (Выбор ведущего члена)
从所得的舍入误差估计可以看出，高斯算法的“瓶颈”是在右侧的项 $|\tilde{L}| \cdot|\tilde{U}|$。也就是说，由于三角因子中元素的增长，可能会导致较大的误差。
例子。设 $n=2$, $p$ 为算术基数，$t$ 为尾数长度。令：
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
令 $\mathrm{f}\left(1-p^{t}\right)=-p^{t}\left(p^{t}-\right.$ 是一个很大的数$)$。那么$\tilde{L}_{1}=1, \tilde{U}_{1}=-p^{t}$,
$$
\tilde{L} \tilde{U}-A=\left[\begin{array}{ll}
0 & 0 \\
0 & 1
\end{array}\right] .
$$
有一个非常大的错误。原因是前导项 $a=p^{-t}$ 的值非常小。

由于 $\tilde{L}_{1} \tilde{U}_{1}=\mathrm{fl}\left(D-\frac{1}{a} b c^{T}\right)$，那么为了减少矩阵 $\tilde{L}_{1}$ 和 $\tilde{U}_{1}$ 并使误差更小，应选择尽可能大的前导项 $a$。例如，通过置换矩阵 $A$ 中的行。

如果我们使用矩阵 $A$ 的行的附加排列（以增加前导项），则结果是矩阵的 $L U P$-分解：
$$
P A=L U
$$
其中，$P$ 是置换矩阵。
## $L D L$-Разложение,Разложение Холецкого
### 定理 8.4
如果 $A \in \mathbb{C}^{n \times n}$ 是严格正则且对称的矩阵 $\left(A=A^{T}\right)$，则它有 $LDL^{T} $ 分解：$A=L D L^{T}$，其中 $L$ 是具有单位对角线的下三角形；$D$ 是非退化对角线。

### 定理 8.5
如果矩阵 $A \in \mathbb{C}^{n \times n}$ 是严格正则的埃尔米特矩阵 $\left(A=A^{*}\right)$，那么它有 $L D L^{*} $分解：$A=L D L^{*}$，其中 $L$ 是单位对角线的下三角形，$D$ 是非退化对角线。

### 定义 8.2
令 $C$ 为主对角线为正的下三角矩阵。 $A=C C^{*}$ 的分解称为**Cholesky分解(разложением Холецкого)**。

### 定理 8.6

对于矩阵$A \in \mathbb{C}^{n \times n}$ 有一个Cholesky 分解，那么它相关的**必要且充分条件**是$A$是埃尔米特矩阵且有正的前导子式。

让我们证明充分性。令 $A=L D L^{T}$ (或 $\left.A=L D L^{*}\right), D=\operatorname{diag}\left(d_{1}, \ldots, d_{n}\right)$。假设 $C=L \operatorname{diag}\left(\sqrt{d_{1}}, \ldots, \sqrt{d_{n}}\right)$。那么$A=C C^{T}$（或$\left.A=C C^{*}\right)$。

## 乔列斯基方法
令 $A$ 是一个实数对称矩阵，具有正前导子式。让我们为其构造 Cholesky 分解。
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

