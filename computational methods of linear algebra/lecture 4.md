# Возмущение собственных значений матрицы; Локализация собственных значений
## 矩阵特征值的扰动，特征值的局部化
## Возмущение собственных значений 
令$\lambda(A)$ 为矩阵$A$ 的谱，即其所有特征值的集合。
### 引理 4.1
设 $\mu \in \lambda(A+\Delta A)$， 但是 $\mu \notin \lambda(A)$。 那么 $\frac{1}{\left\|(A-\mu I)^{-1}\right\|_{2}} \leqslant\|\Delta A\|_{2}$ 
### 证明 
$\mu \notin \lambda(A) \Rightarrow \exists(A-\mu I)^{-1}$。
$$
\begin{gathered}
(A+\Delta A)-\mu I=(A-\mu I)+\Delta A-\text { вырожденная } \Rightarrow \\
\Rightarrow I+(A-\mu I)^{-1} \Delta A-\text { вырожденная } \Rightarrow\left\|(A-\mu I)^{-1} \Delta A\right\|_{2} \geqslant 1 \Rightarrow \\
\Rightarrow\left\|(A-\mu I)^{-1}\right\|_{2} \cdot\|\Delta A\|_{2} \geqslant 1 .
\end{gathered}
$$
### 定理 4.1 
令 $A$ 可对角化，即 $\exists P：P^{-1} A P=\operatorname{diag}\left(\lambda_{1}, \ldots, \lambda_{n}\right)=\Lambda$。 如果$\mu \in \lambda(A+\Delta A)$, 则
$$
\min_{i=1, \ldots, n}\left|\mu-\lambda_{i}\right| \leqslant\left\|P^{-1}\right\|_{2} \cdot\|P\|_{2} \cdot\|\Delta A\|_{2} 。
$$
### 证明
若$\mu \in \lambda(A)$，则$\min_{i=1, \ldots, n}\left|\mu-\lambda_{i}\right|=0$，不等式显然成立。。
如果 $\mu \notin \lambda(A)$ 那么 $\mu \notin \lambda(\Lambda)$，但是 $\mu \in \lambda\left(\Lambda+P^{-1} \Delta A P\right)$。 
由引理 $4.1$ 得：
$$
\min _{i=1, \ldots, n}\left|\mu-\lambda_{i}\right|=\frac{1}{\left\|(\Lambda-\mu I)^{-1 }\right\|_{2}} \leqslant\left\|P^{-1} \Delta A P\right\|_{2} \leqslant\left\|P^{-1}\right\|_ {2} \cdot\|P\|_{2} \cdot\|\Delta A\|_{2} \text {. }
$$
换而言之，频谱对小扰动的敏感性由特征向量矩阵 $P$ 的条件数表征。
### 定理 4.2 
令$P^{-1} A P=J$ 为矩阵 $A$ 的若当形式，且满足 $\mu \in \lambda(A+\Delta A)$。 那么存在 $\lambda \in \lambda(A)$ 使得
$$
\frac{|\mu-\lambda|^{m}}{1+|\mu-\lambda|+\ldots+|\mu-\lambda|^{m-1}} \leqslant\left\|P^ {-1}\right\|_{2} \cdot\|P\|_{2} \cdot\|\Delta A\|_{2}，
$$
这其中 $m$ 对应于 $\lambda$ 的若尔当块的最大阶数。

如果具有最大若尔当块阶数 $m$ 的矩阵的扰动有阶数 $\varepsilon$，那么扰动矩阵的任何特征值都可能与原始矩阵的某个特征值相差 $|\varepsilon|^{\frac{1}{m}}$ 的阶数大小。
## Непрерывность корней алгебраического многочлена(代数多项式的根的连续性)
考虑具有复系数的次数为 $z$ 的多项式 $P(z)$：
$$
P(z)=z^{n}+a_{n-1} z^{n-1}+\ldots+a_{1} z+a_{0} 。
$$
令多项式序列
$$
P_{s}(z)=z^{n}+a_{n-1, s} z^{n-1}+\ldots+a_{1, s} z+a_{0, s}
$$
具有复系数 $a_{i, s}$ 收敛到 $P(z): \lim _{s \rightarrow \infty} a_{i, s}=a_{i}, \forall i$。 

主要问题是：对于大的 $s$，$P_{s}(z)$ 的根与 $P(z)$ 的根是什么样的关系？
### 引理 4.2 (о локализации корня)
对于 $n$ 的任意多项式 $P(z)$ 和任意复数 $z_{0}$，至少有一个 $P(z)$ 的根在以下圆内：
$$
\left|z-z_{0}\right| \leqslant \sqrt[n]{\left|P\left(z_{0}\right)\right|} 。
$$

## 特征值的局部化
矩阵$A$的特征值局部化问题：需要确定它们所在的复平面的那些区域。 区域的计算应该比特征值的数值搜索简单得多。
最简单的估计：矩阵$A$至少有一个特征值$\lambda:|\lambda| \leqslant|\operatorname{det} A|^{1 / n} \quad$ （引理 $4.2$ 的推论）。
另一个简单的估计：
$$
\begin{gathered}
\forall \lambda-\text { c.з. } A \Rightarrow|\lambda| \leqslant\|A\|, \quad \forall\|\cdot\| . \\
\|A\|=\max _{x \neq 0} \frac{\|A x\|}{\|x\|} \geqslant \frac{\left\|A x_{\lambda}\right\|}{\left\|x_{\lambda}\right\|}=|\lambda|, \quad A x_{\lambda}=\lambda \cdot x_{\lambda} .
\end{gathered}
$$
特别是，$|\lambda| \leqslant\|A\|_{2}=\sigma_{1}=\sigma_{\max }(A)$。
如果我们同样考虑矩阵$A^{-1}$，那么我们得到$\sigma_{n}\leqslant|\lambda|$。因此，对于任何矩阵$A$，它的任何特征值$\lambda$都满足以下条件：
$$
\sigma_{n} \leqslant|\lambda| \leqslant \sigma_{1} 。
$$
### 定理 4.4 
设$A \in \mathbb{C}^{n \times n}$。 考虑圆盘
$$
R_{i}=\left\{z \in \mathbb{C}:\left|a_{i i}-z\right| \leqslant r_{i}\right\}, \quad C_{i}=\left\{z \in \mathbb{C}:\left|a_{i i}-z\right| \leqslant c_{i}\right\},
$$
其中：
$$
r_{i}=\sum_{j=1, j \neq i}^{n}\left|a_{i j}\right|, \quad c_{j}=\sum_{i=1, i \neq j }^{n}\left|a_{i j}\right|
$$
那么对于 $\forall \lambda \in \lambda(A)$
$$
\lambda \in \bigcup_{i=1}^{n} R_{i}, \quad \lambda \in \bigcup_{i=1}^{n} C_{i} 。
$$
### 定义 4.1 
圆 $R_{i} ,C_{i}$ 被称为**盖尔圆盘(кругами Гершгорина)**。
### 定理 4.5 
如果 $m$ 个盖尔圆盘形成一个与其他圆隔离的域 $G$，则 $G$ 恰好包含矩阵 $A$ 的 $m$ 个特征值。
### 证明
令 $A(t)=\operatorname{diag}(A)+t \cdot \operatorname{off}(A), t \in[0,1]$。用 $G(t)$ 表示与 $G$ 中的圆具有相同中心的 Gershgorin 圆的并集，并用 $G^{\prime}(t)-$ 表示其他圆的并集。那么 $A(1) \equiv A$,
$$
G(t) \subset G(1)=G, \quad G^{\prime}(t) \subset G^{\prime}(1)=G^{\prime} 。
$$
通过条件 $G \cap G^{\prime}=\emptyset$。因此 $G(t) \cap G^{\prime}(t)=\emptyset, \forall t \in[0,1]$。
由定理 $4.3$，存在连续的 $\lambda_{1}(t), \ldots, \lambda_{m}(t)$ 使得
$$
\begin{gathered}
\left\{\lambda_{1}(0), \ldots, \lambda_{m}(0)\right\}=G(0), \\
\lambda_{1}(t), \ldots, \lambda_{m}(t) \in \lambda(A(t)), \forall t \in[0, \varepsilon) .
\end{gathered}
$$

令 $t_{i}=\sup \left\{t \geqslant 0: \lambda_{i}(t) \in G(t)\right\}$
如果$t_{i}<1$，则$\forall t>t_{i} \lambda_{i}(t) \in G^{\prime}(t)$。但是（从连续性）$\lambda_{i}\left(t_{i}\right) \in G\left(t_{i}\right) \cap$ $G^{\prime}\left(t_{ i}\right) \neq \emptyset$，这是不可能的。矛盾 $\Rightarrow t_{i} \geqslant 1, \forall i=1, \ldots, m$,
$$
\Rightarrow \lambda_{1}(1), \ldots, \lambda_{m}(1) \in G 。
$$
### 推论 
如果盖尔圆盘是成对不相交的，则它们中的每一个都恰好包含一个特征值。