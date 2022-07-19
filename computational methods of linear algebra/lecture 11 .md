## 求解线性方程组的迭代方法
考虑线性方程组
$$
A x=b, \quad A=\left(a_{i j}\right) \in \mathbb{R}^{n \times n}, \operatorname{det} A \neq 0, x \in \mathbb{ R}^{n}, b \in \mathbb{R}^{n} 。
$$
求解线性方程组的任何迭代方法的主要目标是构造这样一个序列 $\left\{x^{(k)}\right\}, k=1,2, \ldots$，其中 $x^{( k)} \rightarrow x^{*}$ 为 $k \rightarrow \infty$ 和 $A x^{*}=b$
假设$a_{i i} \neq 0, \forall i=1, \ldots, n$。 让我们将系统转换为以下形式：
$$
x_{i}=-\sum_{j=1}^{i-1} \frac{a_{i j}}{a_{i i}} x_{j}-\sum_{j=i+1}^{n } \frac{a_{i j}}{a_{i i}} x_{j}+\frac{b_{i}}{a_{i i}}, i=1,2, \ldots, n 。
$$
迭代法举例如下：
- Метод Якоби:
$$
x_{i}^{(k+1)}=-\sum_{j=1}^{i-1} \frac{a_{i j}}{a_{i i}} x_{j}^{(k)}-\sum_{j=i+1}^{n} \frac{a_{i j}}{a_{i i}} x_{j}^{(k)}+\frac{b_{i}}{a_{i i}}, i=1,2, \ldots, n, k=0,1, \ldots, k^{*}, \forall x^{(0)} .
$$
- Метод Зейделя:
$$
x_{i}^{(k+1)}=-\sum_{j=1}^{i-1} \frac{a_{i j}}{a_{i i}} x_{j}^{(k+1)}-\sum_{j=i+1}^{n} \frac{a_{i j}}{a_{i i}} x_{j}^{(k)}+\frac{b_{i}}{a_{i i}}, i=1,2, \ldots, n, k=0,1, \ldots, k^{*}, \forall x^{(0)} .
$$

## 矩阵符号
让我们将矩阵 $A$ 表示为三个矩阵的总和：
$$
A=A_{1}+D+A_{2}, D=\operatorname{diag}\left(a_{11}, a_{22}, \ldots, a_{n n}\right),
$$
矩阵 $A_{1}$ 是零对角线的下三角形，$A_{2}-$ 是零对角线的上三角形。那么 SL​​AE 可以改写为以下形式：
$$
x=-D^{-1} A_{1} x-D^{-1} A_{2} x+D^{-1} b 。
$$
矢量符号中的 Jacobi 方法如下所示：
$$
x^{(k+1)}=-D^{-1} A_{1} x^{(k)}-D^{-1} A_{2} x^{(k)}+D^{ -1}b，
$$
或者
$$
D x^{(k+1)}+\left(A_{1}+A_{2}\right) x^{(k)}=b \Leftrightarrow D\left(x^{(k+1)} -x^{(k)}\right)+A x^{(k)}=b 。
$$
Seidel 方法具有以下矩阵形式：
$$
x^{(k+1)}=-D^{-1} A_{1} x^{(k+1)}-D^{-1} A_{2} x^{(k)}+D^{-1} b,
$$
或者
$$
\left(D+A_{1}\right) x^{(k+1)}+A_{2} x^{(k)}=b \Leftrightarrow\left(D+A_{1}\right)\left(x^{(k+1)}-x^{(k)}\right)+A x^{(k)}=b .
$$
如果 Jacobi 或 Seidel 方法收敛，则它会收敛到原始方程组的解。

## 加速迭代方法
通常，为了加快收敛速度​​，迭代方法中会引入数值参数，这可能取决于迭代次数。例如，对于 Jacobi 和 Seidel 方法，可以引入迭代参数 $\tau_{k+1}$：
$$
\begin{gathered}
D \frac{x^{(k+1)}-x^{(k)}}{\tau_{k+1}}+A x^{(k)}=b, \\
\left(D+A_{1}\right) \frac{x^{(k+1)}-x^{(k)}}{\tau_{k+1}}+A x^{(k)}=b .
\end{gathered}
$$
Jacobi 和 Seidel 的上述方法是指一步迭代方法，当找到 $x^{(k+1)}$ 时，只需要记住前一次迭代 $x^{(k)}$。有时也使用多步迭代的方法，其中$x^{(k+1)}$根据值定义$x^{k}, \ldots, x^{(k-l)}$ .
一步迭代法的典型形式是：
$$
B^{(k+1)} \frac{x^{(k+1)}-x^{(k)}}{\tau_{k+1}}+A x^{(k)}=b , k=0,1, \ldots, k^{*}
$$
这里的矩阵 $B^{(k+1)}$ 定义了一个特定的方法，$\tau_{k+1}-$ 迭代参数。假设有矩阵$\left(B^{(k+1)}\right)^{-1}$，$x^{(k+1)}$可以由
$$
B^{(k+1)} x^{(k+1)}=F^{(k)}, F^{(k)}=\left(B^{(k+1)}-\tau_ {k+1} A\right) x^{(k)}+\tau_{k+1} b 。
$$
## 显式和隐式方法
如果 $B^{(k)}=I$，则称为显式​​迭代方法。否则，该方法被称为隐式。只有当每个矩阵 $B^{(k)}$ 比矩阵 $A$ 更容易求逆时，才有意义使用隐式迭代方法。例如，在 Seidel 方法中，矩阵 $B^{(k)}$ 是三角形的，因此很容易可逆。隐式方法的优点是收敛速度更快。

如果 $B^{(k+1)} \equiv B, \tau_{k+1} \equiv \tau$，则迭代方法称为平稳的。否则，该方法称为非平稳方法。
例子：
- 简单迭代法（显式、静止法）：
$$
\frac{x^{(k+1)}-x^{(k)}}{\tau}+A x^{(k)}=b 。
$$
- 迭代 Richardson 方法（显式、非平稳）：
$$
\frac{x^{(k+1)}-x^{(k)}}{\tau_{k+1}}+A x^{(k)}=b 。
$$
- 上放松法：
$$
\left(D+\omega A_{1}\right) \frac{x^{(k+1)}-x^{(k)}}{\omega}+A x^{(k)}=b .
$$
## 迭代方法的收敛
考虑以规范形式编写的一步平稳迭代方法：
$$
B \frac{x^{(k+1)}-x^{(k)}}{\tau}+A x^{(k)}=b, k=0,1,2, \ldots,
$$
其中给出了向量 $x^{(0)}$。 如果 $\left\|x^{(k)}-x^{*}\right\|$ $\rightarrow 0$ 为 $k \rightarrow \infty$,则迭代方法收敛。我们将在任何地方使用欧几里得向量范数 $\|\cdot\|_{2}$。 令 $z^{(k)}=x^{(k)}-x^{*}-$ 为方法在第 $k$ 次迭代时的误差。 它满足方程
$$
B \frac{z^{(k+1)}-z^{(k)}}{\tau}+A z^{(k)}=0, \quad k=0,1,2, \ldots , z^{(0)}=x^{(0)}-x^{*} 。
$$