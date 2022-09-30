# 求特征值和向量的问题(Проблема поиска собственных значений и векторов)
## Проблема собственных значений
特征值问题是一组与计算特征值（谱）和特征向量有关的问题。

需要找到矩阵$A\in\mathbb{C}^{n\times n}$的所有特征值。最简单的想法：找到特征多项式的系数并将问题归结为计算该多项式的根。要获得特征多项式的系数，可以构造**прямый метод**，该方法需要 $\mathcal{O}\left(n^{3}\right)$ 时间复杂度的算术运算。
使用特征多项式的想法并不总是好的。其问题在于特征值可以对矩阵元素的小扰动弱敏感，但对其特征多项式的系数的小扰动非常敏感。也就是说，“好”任务被简化为“坏”任务。
特别困难的是特征值对矩阵元素的小扰动高度敏感的情况。
解决光谱问题的一种流行方法是研究所谓的谱图 **(спектральных портретов)**。 对于给定的矩阵 $A$ 和参数 $\varepsilon>0$，下面集合被称为谱图 **(спектральных портретов)**：
$$
S(\varepsilon)=\left\{\lambda \in \mathbb{C}: f(\lambda)=\sigma_{\min }(A-\lambda I) \leqslant \varepsilon\right\} .
$$
若 $\tilde{\lambda}$ 是矩阵 $A$ 的特征值, 那么 $\sigma_{\min }(A-\tilde{\lambda} I)=0$, 因此 $\tilde{\lambda} \in S(\varepsilon)$.

对于一些简单的矩阵形状，特征值问题很容易解决：如对角矩阵 **(диагональной)**、三对角矩阵 **(трёхдиагональной)**、三角形或近似三角形矩阵 **(треугольной или почти треугольной)**。三角或对角矩阵的特征值等于它的对角元素。

许多求解特征值问题的数值方法都是基于使用相似变换将矩阵简化为指定的简单形式之一，如使用 $B=P^{-1} A P$。令 $\eta$ 和 $y$ 是矩阵 $B$ 的特征值和特征向量。那么$\eta y=B y=P^{-1} A P y \Rightarrow \eta(P y)=A(P y)$。因此，$\eta$ 和$P y-$ 是矩阵$A$ 的特征值和特征向量。
换而言之，我们这里用到这样一个结论：==**相似变换不会改变矩阵的特征值。**==

## Устойчивость проблемы собственных значений
假设矩阵 $A$ 的特征向量构成一个基底。 令 $\lambda_{i}$ 为 $A$ 的简单特征值，$x_{i}$ 为对应的特征向量。

如果我们稍微改变矩阵 $A$ 的元素，那么特征值和相应特征向量的扰动满足线性化方程，最多为二阶小量
$$
A \cdot \Delta x_{i}+\Delta A \cdot x_{i} \approx \Delta \lambda_{i} \cdot x_{i}+\lambda_{i} \cdot \Delta x_{i} 。
$$
让我们在未扰动的特征向量中展开 $\Delta x_{i}$：
$$
\Delta x_{i}=\sum_{j=1}^{n} \xi_{i j} x_{j} 。
$$
扰动特征向量 $x_{i}+\Delta x_{i}$ 被定义为一个因子。让我们选择这个因子使得 $\xi_{i i}=0$。

令 $y_{j}$ 为矩阵 $A^{*}$ 的对应特征向量：$A^{*} y_{j}=\lambda_{j}^{*} y_{j}$。然后
$$
\begin{gathered}
\left\langle y_{j}, A \cdot \Delta x_{i}\right\rangle=\left\langle A^{*} y_{j}, \Delta x_{i}\right\rangle=\lambda_{j}^{*}\left\langle y_{j}, \Delta x_{i}\right\rangle, \forall j, \\
0=\left\langle y_{j}, A x_{i}\right\rangle-\left\langle A^{*} y_{j}, x_{i}\right\rangle=\left\langle y_{j}, \lambda_{i} x_{i}\right\rangle-\left\langle\lambda_{j}^{*} y_{j}, x_{i}\right\rangle \Rightarrow\left(\lambda_{i}^{*}-\lambda_{j}^{*}\right)\left\langle y_{j}, x_{i}\right\rangle=0, \\
\Rightarrow\left\langle y_{j}, x_{i}\right\rangle=0, \text { если } \lambda_{i} \neq \lambda_{j} .
\end{gathered}
$$
现在我们将近似等式先乘以 $y_{i}$，然后乘以 $y_{j}$ 得到 $j\neq i$，并将 $\Delta x_{i}$ 的展开代入基础 $x_{ 1},\ldots,x_{n}$：
$$
\left\langle y_{i}, x_{i}\right\rangle \Delta \lambda_{i} \approx\left\langle y_{i}, \Delta A \cdot x_{i}\right\rangle, \quad \xi_{i j}\left(\lambda_{j}-\lambda_{i}\right)\left\langle y_{j}, x_{j}\right\rangle \approx\left\langle y_{j}, \Delta A \cdot x_{i}\right\rangle .
$$
矩阵 $\Delta A$ 的扰动可以是任意的。
特征值和特征向量分量的最大误差不超过（直到丢弃的高阶小项的无穷小项）以下值：
$$
\left|\Delta \lambda_{i}\right| \lesssim\left|\chi_{i}\right| \cdot \max _{i, j}\left|(\Delta A)_{i j}\right|, \quad\left|\xi_{i j}\right| \lesssim \frac{\left|\chi_{j}\right| \cdot\left\|x_{i}\right\|_{2}}{\left|\lambda_{i}-\lambda_{j}\right| \cdot\left\|x_{j}\right\|_{2}} \cdot \max _{i, j}\left|(\Delta A)_{i j}\right|,
$$
其中 $\chi_{i}$ 是矩阵**偏斜因子(коэффициент перекоса)**：
$$
\chi_{i}=\frac{\left\|x_{i}\right\|_{2} \cdot\left\|y_{i}\right\|_{2}}{\left\langle x_ {i}, y_{i}\right\rangle}=\frac{1}{\cos \left(\varphi_{i}\right)}, \quad\left|\chi_{i}\right| \geqslant 1,
$$
$\varphi$ - 矩阵 $A$ 和 $A^{*}$ 的相应特征向量之间的角度。

例子：
令矩阵 $A \in \mathbb{C}^{2 \times 2}$ 具有 Jordan 单元的形式：
$$
A=\left[\begin{array}{ll}
a & 1 \\
0 & a
\end{array}\right], x_{1}=\left[\begin{array}{l}
1 \\
0
\end{array}\right], A^{*}=\left[\begin{array}{cc}
a^{*} & 0 \\
1 & a^{*}
\end{array}\right], y_{1}=\left[\begin{array}{l}
0 \\
1
\end{array}\right]
$$
那么$\left\langle x_{1}, y_{1}\right\rangle=0$，偏斜因子为$\infty$。
### 例子：
$$
A=\left[\begin{array}{ccccccc}
20 & 20 & 0 & 0 & \ldots & 0 & 0 \\
0 & 19 & 20 & 0 & \ldots & 0 & 0 \\
0 & 0 & 18 & 20 & \ldots & 0 & 0 \\
\ldots & \ldots & \ldots & \ldots & \ldots & \ldots & \ldots \\
0 & 0 & 0 & 0 & \ldots & 2 & 20 \\
\varepsilon & 0 & 0 & 0 & \ldots & 0 & 1
\end{array}\right], \quad f(\lambda)=\operatorname{det}(A-\lambda I)=\prod_{k=1}^{20}(k-\lambda)-20^{19} \varepsilon=0 .
$$
对于$\varepsilon=0$，多项式的最低系数是$a_{0}=20$!，最小模特征值是$\lambda_{\min}=1$。但当$\varepsilon=20^{-19} \cdot 20 ! \approx 5 \cdot 10^{-7}, a_{0}=0, \lambda_{\min }=0$。
**可以看出，该矩阵的稳定性较差。**
结论：
1.如果对应的偏斜因子较小，则矩阵的特征值相对于矩阵元素的扰动是稳定的。
2.如果偏斜因子很大，则稳定性可能很差。 如果所有偏斜因子都很小，则特征向量在所有矩阵元素上都是稳定的。
## Метод интерполяции характеристического многочлена (特征多项式插值法)
如果找到特征多项式 $f(\lambda)$，则可以近似计算其根（例如，通过切线或弦的方法获得方程的近似解）。

为了快速找到特征多项式，通常使用插值法。 一个 $n$ 次的多项式 $f(\lambda)$ 由它在 $\lambda_{k}$ 的不同 $n+1$ 个点上的值唯一确定。 因此，计算矩阵 $A-\lambda_{k} I$ 的 $n+1$ 个行列式就足够了，然后使用牛顿插值公式唯一地恢复多项式：
$$
\begin{gathered}
\lambda_{0}<\lambda_{1}<\lambda_{2}<\ldots<\lambda_{n}-\text { 插值节点} \\
f(\lambda)=f\left(\lambda_{0}\right)+\sum_{k=1}^{n}\left(\lambda-\lambda_{0}\right)\left(\lambda-\lambda_{1}\right) \ldots\left(\lambda-\lambda_{k-1}\right) \Delta f\left(\lambda_{0}, \lambda_{1}, \ldots, \lambda_{k}\right),
\end{gathered}
$$
其中 $\Delta f\left(\lambda_{0}, \lambda_{1}, \ldots, \lambda_{k}\right)-$ 是划分的差：
$$
\begin{gathered}
\Delta f\left(\lambda_{0}, \lambda_{1}\right)=\frac{f\left(\lambda_{1}\right)-f\left(\lambda_{0}\right)}{\lambda_{1}-\lambda_{0}}, \\
\Delta f\left(\lambda_{0}, \lambda_{1}, \lambda_{2}\right)=\frac{\Delta f\left(\lambda_{1}, \lambda_{0}\right)-\Delta f\left(\lambda_{1}, \lambda_{2}\right)}{\lambda_{2}-\lambda_{0}},
\end{gathered}
$$
仅对小的 $n$ 使用插值方法是有意义的。
## Характеристический многочлен трёхдиагональной матрицы(三对角矩阵的特征多项式)
令矩阵 $A=\left(a_{i j}\right) \in \mathbb{C}^{n \times n}-$ 为三对角矩阵。那么它的特征多项式可以不用插值公式就可以有效地计算出来，也不需要多次计算矩阵行列式。令 $D_{k}(\lambda)$ 为 $k$ 阶矩阵 $A-\lambda I$ 的主子式。那么$D_{n}(\lambda)=f(\lambda)$。
对于 $k=3, \ldots, n$，根据最后一行扩展行列式 $D_{k}(\lambda)$：
$$
D_{k}(\lambda)=\left(a_{k k}-\lambda\right) D_{k-1}(\lambda)-a_{k, k-1} B_{k, k-1}( λ) 。
$$
让我们将行列式 $B_{k, k-1}(\lambda)$ 扩展为最后一列：
$$
B_{k, k-1}(\lambda)=a_{k-1, k} D_{k-2}(\lambda) 。
$$
最后，
$$
D_{k}(\lambda)=\left(a_{k k}-\lambda\right) D_{k-1}(\lambda)-a_{k, k-1} a_{k-1, k} D_ {k-2}(\lambda) 。
$$
所以计算$D_{1}(\lambda), D_{2}(\lambda)$并使用递推关系计算$D_{n}(\lambda)$就足够了。
## Метод обратной итерации для поиска собственных векторов (求特征向量的反向迭代法)
令 $\lambda_{i}$ 为 $A$ 的特征值，$\tilde{\lambda}_{i}$ 为近似值。那么可以得到 $\operatorname{det}\left(A-\tilde{\lambda}_{i} I\right) \neq 0$，但是这个行列式的值很小。
这意味着不可能从线性方程组 $\left(A-\tilde{\lambda}_{i} I\right) x=\theta$ 中搜索到对应的特征向量，因为这个系统有唯一解 $x=\theta$。

为了搜索特征向量，使用反向迭代方法：我们固定任何向量 $b$ 并考虑线性方程组：
$$
\left(A-\tilde{\lambda}_{i} I\right) x=b
$$
设一个 $n$ 阶的矩阵 $A$ 有 $n$ 个线性无关的特征向量 $x_{j}$ (例如，矩阵是正规矩阵):
$A x_{j}=\lambda_{j} x_{ j}，\forall j=1，\ldots，n$。 让我们以 $x_{j}$ 为基底分解 $x$ 和 $b$ ：
$$
x=\sum_{j=1}^{n} \xi_{j} x_{j}, b=\sum_{j=1}^{n} \beta_{j} x_{j} \Rightarrow \sum_{ j=1}^{n}\left(\xi_{j}\left(\lambda_{j}-\tilde{\lambda}_{i}\right)-\beta_{j}\right) x_{j }=0
$$
因此：
$$
\xi_{j}=\frac{\beta_{j}}{\lambda_{j}-\tilde{\lambda}_{i}}, \forall j 。
$$
接下来，考虑两种可能的情况：
### 第一种情况：
$\lambda_{i}$ 是一个简单特征值 **(простое собственное значение)**。那么在所有 $\xi_{j}, j=1, \ldots, n$ 中，只有一个非常大 $\Rightarrow$ 向量 $\frac{x}{\|x\|_{2}}$几乎与 $\frac{x_{i}}{\left\|x_{i}\right\|_{2}}$ 重合。

### 第二种情况：
$\lambda_{i}$ 是一个多重特征值：$\lambda_{1}=\lambda_{2}=\ldots=\lambda_{p}, 1<p \leqslant$ $n$。在这种情况下，特征向量 $x_{1}、\ldots、x_{p}$ 定义不明确。它们的任意线性组合也是对应于$\lambda_{1}$的特征向量。
系数 $\xi_{1}、\xi_{2}、\ldots、\xi_{p}$ 会很大。其余系数很小。这意味着找到的向量 $x$ 是 $x_{1}、\ldots、x_{p}$ 的线性组合，即所需的特征向量。
### 示例：
令 $A=J_{4}(0)$ 为 4 阶若尔当块，其特征值 $\lambda=0$。令$\tilde{\lambda}=\varepsilon, b=[1,1,1,1]^{T}$。然后在该方法的一次迭代之后，我们得到：
$$
\left[\begin{array}{llll}
\varepsilon & 1 & 0 & 0 \\
0 & \varepsilon & 1 & 0 \\
0 & 0 & \varepsilon & 1 \\
0 & 0 & 0 & \varepsilon
\end{array}\right] \cdot\left[\begin{array}{l}
x_{1} \\
x_{2} \\
x_{3} \\
x_{4}
\end{array}\right]=\left[\begin{array}{c}
\varepsilon x_{1}+x_{2} \\
\varepsilon x_{2}+x_{3} \\
\varepsilon x_{3}+x_{4} \\
\varepsilon x_{4}
\end{array}\right]=\left[\begin{array}{l}
1 \\
1 \\
1 \\
1
\end{array}\right] \Rightarrow\left\{\begin{array}{l}
x_{4}=\varepsilon^{-1} \\
x_{3}=-\varepsilon^{-2}+\varepsilon^{-1} \\
x_{2}=\varepsilon^{-3}-\varepsilon^{-2}+\varepsilon^{-1} \\
x_{1}=-\varepsilon^{-4}+\varepsilon^{-3}-\varepsilon^{-2}+\varepsilon^{-1}
\end{array}\right.
$$
将解乘以 $-\varepsilon^{4}$，我们得到 $x_{1}=1+\mathcal{O}(\varepsilon), x_{2}=\mathcal{O}(\varepsilon), x_ {3}=\mathcal{O}\left(\varepsilon^{2}\right), x_{4}=$$\mathcal{O}\left(\varepsilon^{3}\right)$，即$ x=e_{1}+\mathcal{O}(\varepsilon), e_{1}=[1,0,0,0]^{T}$。

