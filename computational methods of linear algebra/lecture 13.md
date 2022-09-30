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
其中矩阵 $A_{1}$ 是对角线为零的下三角矩阵，$A_{2}-$ 是对角线为零的上三角矩阵。那么线性方程组可以改写为以下形式：
$$
x=-D^{-1} A_{1} x-D^{-1} A_{2} x+D^{-1} b 。
$$
**Метод Якоби** 以向量表示可以有以下形式：
$$
x^{(k+1)}=-D^{-1} A_{1} x^{(k)}-D^{-1} A_{2} x^{(k)}+D^{ -1}b，
$$
==或者被表示为==
$$
D x^{(k+1)}+\left(A_{1}+A_{2}\right) x^{(k)}=b \Leftrightarrow D\left(x^{(k+1)} -x^{(k)}\right)+A x^{(k)}=b 。
$$
==（右边的形式后面会被反复用到）==
而 **Метод Зейделя** 具有以下矩阵形式：
$$
x^{(k+1)}=-D^{-1} A_{1} x^{(k+1)}-D^{-1} A_{2} x^{(k)}+D^{-1} b,
$$
==或者被表示为==
$$
\left(D+A_{1}\right) x^{(k+1)}+A_{2} x^{(k)}=b \Leftrightarrow\left(D+A_{1}\right)\left(x^{(k+1)}-x^{(k)}\right)+A x^{(k)}=b .
$$
==（右边的形式后面会被反复用到）==
如果 **Метод Якоби**或**Метод Зейделя**是收敛的，则它会收敛到原始方程组的解。

## 加速迭代方法
通常，为了加快收敛速度​​，迭代方法中会引入数值参数，这可能取决于迭代次数。例如，对于**雅可比和塞德尔方法**，可以引入迭代参数 **(итерационные параметры)** $\tau_{k+1}$：
$$
\begin{gathered}
D \frac{x^{(k+1)}-x^{(k)}}{\tau_{k+1}}+A x^{(k)}=b, \\
\left(D+A_{1}\right) \frac{x^{(k+1)}-x^{(k)}}{\tau_{k+1}}+A x^{(k)}=b .
\end{gathered}
$$
上述的雅可比和塞德尔迭代法是指**一步迭代法 (одношаговым итерационным методам)**，当找到 $x^{(k+1)}$ 时，只需要记住前一次迭代 $x^{(k)}$。
有时也使用**多步迭代法(многошаговым итерационным методам)**，其中$x^{(k+1)}$ 根据值$x^{k}, \ldots, x^{(k-l)}$定义。
一步迭代法的典型形式是：
$$
B^{(k+1)} \frac{x^{(k+1)}-x^{(k)}}{\tau_{k+1}}+A x^{(k)}=b , k=0,1, \ldots, k^{*}
$$
这里的矩阵 $B^{(k+1)}$ 定义了一个特定的方法，$\tau_{k+1}$ 是对应的迭代参数。假设有矩阵 $\left(B^{(k+1)}\right)^{-1}$，$x^{(k+1)}$ 可以由以下形式定义：
$$
B^{(k+1)} x^{(k+1)}=F^{(k)}, F^{(k)}=\left(B^{(k+1)}-\tau_ {k+1} A\right) x^{(k)}+\tau_{k+1} b 。
$$
## 显式和隐式方法
如果 $B^{(k)}=I$，则称为**显式​​迭代法(явным)**。否则，该方法被称为**隐式的(неявным)**。
一般来说，只有当每个矩阵 $B^{(k)}$ 比矩阵 $A$ 更容易求逆时，使用隐式迭代方法才有意义。例如在塞德尔方法中，矩阵 $B^{(k)}$ 是含对角线的下三角矩阵 **$D+A_{1}$**，因此很容易找到逆矩阵。==隐式迭代方法的优点是收敛速度更快。==

如果 $B^{(k+1)} \equiv B, \tau_{k+1} \equiv \tau$，则迭代方法称为**平稳的(стационарным)**。否则，该方法称为**非平稳的(нестационарным)**。
例子：
- 简单迭代法（显式平稳迭代法）：
$$
\frac{x^{(k+1)}-x^{(k)}}{\tau}+A x^{(k)}=b 。
$$
- 理查森 **(Ричардсона)** 迭代法（显式非平稳迭代法）：
$$
\frac{x^{(k+1)}-x^{(k)}}{\tau_{k+1}}+A x^{(k)}=b 。
$$
- 上松弛法 **(Метод верхней релаксации)**：
$$
\left(D+\omega A_{1}\right) \frac{x^{(k+1)}-x^{(k)}}{\omega}+A x^{(k)}=b .
$$
## 迭代法的收敛
考虑以规范形式编写的一步平稳迭代方法：
$$
B \frac{x^{(k+1)}-x^{(k)}}{\tau}+A x^{(k)}=b, k=0,1,2, \ldots,
$$
其中给出了向量 $x^{(0)}$。 如果 $\left\|x^{(k)}-x^{*}\right\|$ $\rightarrow 0$ 为 $k \rightarrow \infty$,则迭代方法收敛。我们将在任何地方使用欧几里得向量范数 $\|\cdot\|_{2}$。 令 $z^{(k)}=x^{(k)}-x^{*}$ 是该方法在第 $k$ 次迭代时的误差。 则它必定满足方程：
$$
B \frac{z^{(k+1)}-z^{(k)}}{\tau}+A z^{(k)}=0, \quad k=0,1,2, \ldots , z^{(0)}=x^{(0)}-x^{*} 。
$$

### 定理 13.1
令 $A$ 为正定的对称矩阵，$\tau>0$，且满足不等式$B-0.5\tau A>0$。 那么该迭代法收敛。 
### 证明 
让我们证明 $\left\|z^{(k)}\right\| \rightarrow 0$ 为 $k \rightarrow \infty$。 从迭代方法的方程我们得到：
$$
z^{(k+1)}=\left(I-\tau B^{-1} A\right) z^{(k)} \Rightarrow A z^{(k+1)}=\left( A-\tau A B^{-1} A\right) z^{(k)}
$$
那么：
$$
\begin{aligned}
\left\langle A z^{(k+1)}, z^{(k+1)}\right\rangle=\left\langle A z^{(k)}, z^{(k)}\right\rangle &-\tau\left\langle A B^{-1} A z^{(k)}, z^{(k)}\right\rangle-\\
&-\tau\left\langle A z^{(k)}, B^{-1} A z^{(k)}\right\rangle+\tau^{2}\left\langle A B^{-1} A z^{(k)}, A B^{-1} A z^{(k)}\right\rangle .
\end{aligned}
$$
根据矩阵 $A$ 的对称性，我们有：
$$
\left\langle A B^{-1} A z^{(k)}, z^{(k)}\right\rangle=\left\langle A z^{(k)}, B^{-1}A z^{(k)}\right\rangle 。
$$
因此
$$
\begin{gathered}
\left\langle A z^{(k+1)}, z^{(k+1)}\right\rangle=\left\langle A z^{(k)}, z^{(k)}\right\rangle-2 \tau\left\langle(B-0.5 \tau A) B^{-1} A z^{(k)}, B^{-1} A z^{(k)}\right\rangle . \\
B-0.5 \tau A>0 \Rightarrow\left\langle A z^{(k+1)}, z^{(k+1)}\right\rangle<\left\langle A z^{(k)}, z^{(k)}\right\rangle .
\end{gathered}
$$
由此可以得到序列 $J_{k}=\left\langle A z^{(k)}, z^{(k)}\right\rangle$ 是单调递减的，并且从以零为下界（因为 $A>0$ ）即：$\exists \lim _{k \rightarrow \infty} J_{k}=J^{*}$。
另外：
$$
\begin{aligned}
B-0.5 \tau A>0 \Rightarrow \exists \delta &>0:\left\langle(B-0.5 \tau A) B^{-1} A z^{(k)}, B^{-1} A z^{(k)}\right\rangle \geqslant \delta\left\|B^{-1} A z^{(k)}\right\|^{2} \\
& \Rightarrow J_{k+1}-J_{k}+2 \delta \tau\left\|B^{-1} A z^{(k)}\right\|^{2} \leqslant 0 .
\end{aligned}
$$
若$k \rightarrow \infty$ ，则必定 $ \exists \lim _{k \rightarrow \infty}\left\|w^{(k)}\right\|=0, w^{(k )}= B^{-1} A z^{(k)}$。矩阵 $A, B$ 是可逆的，所以在 $k \rightarrow \infty$时，$z^{(k)}=A^{-1} B w^{(k)} \rightarrow \theta$ 。
## 迭代法的收敛——雅可比迭代法
在雅可比方法中
$$
D\left(x^{(k+1)}-x^{(k)}\right)+A x^{(k)}=b, \quad B=D, \tau=1 。
$$
### 定理 13.2
令矩阵 $A$ 是对称的、正定的、且行对角线占优的：
$$
a_{i i}>\sum_{j \neq i}\left|a_{i j}\right|, \forall i=1,2, \ldots, n 。
$$
那么雅可比方法收敛。
### 证明：
收敛条件 $B-0.5 \tau A>0$ 可以表示为形式： $A<2 D$。 让我们证明它是从定理的条件得出的。 
令$\langle A x, x\rangle=\sum_{i, j=1}^{n} a_{i j} x_{i} x_{j}$。
$$
\Rightarrow\langle A x, x\rangle \leqslant \frac{1}{2} \sum_{i, j=1}^{n}\left|a_{i j}\right| x_{i}^{2}+\frac{1}{2} \sum_{i, j=1}^{n}\left|a_{i j}\right| x_{j}^{2}=\frac{1}{2} \sum_{i, j=1}^{n}\left|a_{i j}\right| x_{i}^{2}+\frac{1}{2} \sum_{i, j=1}^{n}\left|a_{j i}\right| x_{i}^{2}
$$

$$
\Rightarrow\langle A x, x\rangle \leqslant \sum_{i, j=1}^{n}\left|a_{i j}\right| x_{i}^{2}=\sum_{i=1}^{n} x_{i}^{2}\left(\sum_{j \neq i}\left|a_{i j}\right|+ a_{i i}\right)<2 \sum_{i=1}^{n} a_{i i} x_{i}^{2}=2\langle D x, x\rangle, \forall x \neq \theta .
$$ 

因此，$A<2D.$
## 迭代法的收敛——上松弛法
在上松弛法中
$$
\left(D+\omega A_{1}\right) \frac{x^{(k+1)}-x^{(k)}}{\omega}+A x^{(k)}=b, \quad B=D+\omega A_{1}, \tau=\omega .
$$
### 定理 13.3
令$A$ 是对称的正定矩阵。那么当满足$\omega \in(0,2)$时，上松弛迭代法收敛。特别是 $\omega=1$时，塞德尔迭代法收敛。
### 证明
因为$A_{1}=A_{2}^{T}$，那么
$$
\langle A x, x\rangle=\langle D x, x\rangle+\left\langle A_{1} x, x\right\rangle+\left\langle A_{2} x, x\right\rangle=\langle D x, x\rangle+2\left\langle A_{1} x, x\right\rangle 。
$$
收敛条件采用以下形式：
$$
\begin{aligned}
\langle B x, x\rangle-0.5 \omega\langle A x, x\rangle=\left\langle\left(D+\omega A_{1}\right) x, x\right\rangle-0.5 \omega(\langle D x, x\rangle+&\left.2\left\langle A_{1} x, x\right\rangle\right)=(1-0.5 \omega)\langle D x, x\rangle>0
\end{aligned}
$$
如果 $\omega \in(0,2)$。此处使用以下属性：如果 $A>0$，则 $D>0$。
## 迭代法收敛——简单迭代法
在简单迭代法中
$$
\frac{x^{(k+1)}-x^{(k)}}{\tau}+A x^{(k)}=b, \quad B=I 。
$$
1.令 $A$ 是对称的正定矩阵。 则该方法的收敛条件为：
$$
I-0.5 \tau A>0 。
$$
2.令 $\lambda_{i}, i=1,2, \ldots, n,$ 是矩阵$A$的特征值。 如果矩阵$I-0.5 \tau A$的所有特征值都是正的，则该方法收敛。 这等价于不等式 $1-0.5 \tau \lambda_{\max }>0$。 即收敛条件也可以写做：
$$
\tau<\frac{2}{\lambda_{\max }(A)} 。
$$
**让我们证明这个条件不仅是充分条件，而且是必要条件。**
令$x^{(0)}=x^{*}+\mu,\mu$ 是特征值 $\lambda_{\max}$ 对应的特征向量 $A\mu=\lambda_{\max } \mu$。 那么$z^{(0)}=\mu$,
$$
z^{(k)}=(I-\tau A)^{k} z^{(0)}=(I-\tau A)^{k} \mu \Rightarrow z^{(k)}=\left(1-\tau \lambda_{\max }\right)^{k} \mu,\left\|z^{(k)}\right\|=\left|1-\tau \lambda_{\max }\right|^{k}\|\mu\| .
$$
如果 $\tau=2\left(\lambda_{\max }\right)^{-1}$ ，那么 $\left\|z^{(k)}\right\|=\|\mu\| \nrightarrow 0$。 
如果 $\tau>2\left(\lambda_{\max }\right)^{-1}$，那么 $\left\|z^{(k)}\right\| \rightarrow \infty$。
## 平稳迭代法的收敛准则
考虑平稳的迭代过程
$$
B \frac{x^{(k+1)}-x^{(k)}}{\tau}+A x^{(k)}=b, \quad B \frac{z^{(k+ 1 )}-z^{(k)}}{\tau}+A z^{(k)}=\theta \Leftrightarrow z^{(k+1)}=S z^{(k)} 。
$$
显而易见，迭代过程的收敛性取决于矩阵$S=I-\tau B^{-1} A$的性质。
### 定理 13.4 
迭代方法对于任何初始近似 $x^{(0)}$是收敛的，当且仅当 $\forall s$ 是 $S=I-\tau B^{-1} A$ 的特征值时，可推出 $|s|<1$。
（证明略）