## 光谱距离
讲座的主要目的是估计矩阵光谱之间的“距离”：扰动和未扰动。
### 定义 6.1
设 $A, B \in \mathbb{C}^{n \times n}$, 和 $\left\{\lambda_{i}\right\},\left\{\mu_{j}\right\} -$ 这些矩阵的光谱。 $A$ 和 $B$ 之间的 Hausdorff 谱距离：
$$
\operatorname{hd}(A, B)=\max \left\{\max _{i} \min _{j}\left|\lambda_{i}-\mu_{j}\right|, \max _ {j} \min _{i}\left|\lambda_{i}-\mu_{j}\right|\right\} \text {. }
$$
==min是找对应，max是算距离==
### 定义 6.2
令$\lambda(A)=\left[\lambda_{1}, \ldots, \lambda_{n}\right]^{T}, \lambda(B)=\left[\mu_{1}, \ldots , \mu_{n}\right]^{T}$.
矩阵之间的频谱 $p$-距离：
$$
d_{p}(A, B)=\min _{P}\left\{\|\lambda(A)-P \lambda(B)\|_{p}: P-\text { матрица перестановки }\right\} .
$$
### 定理 6.1
有效估计：$\operatorname{hd}(A, B) \leqslant\left(\|A\|_{2}+\|B\|_{2}\right)^{1-\frac{1} {n}} \cdot\|A-B\|_{2}^{\frac{1}{n}}$。
### 证明
让向量 $x_{1}、\ldots、x_{n}$ 形成酉矩阵 $X$ 和 $B x_{1}=\mu x_{1}$ 的列。如果$\lambda_{1}, \ldots, \lambda_{n}-$是$A$的特征值，那么
$$
\begin{aligned}
\left(\min _{i}\left|\lambda_{i}-\mu\right|\right)^{n} \leqslant \prod_{i=1}^{n}\left|\lambda_{i}-\mu\right|=|\operatorname{det}((A-\mu I) X)| & \leqslant \prod_{i=1}^{n}\left\|(A-\mu I) x_{i}\right\|_{2} \leqslant \\
\leqslant\left\|(A-B) x_{1}\right\|_{2} \cdot \prod_{i=2}^{n}\left\|(A-\mu I) x_{i}\right\|_{2} \leqslant\|A-B\|_{2} \cdot\left(\|A\|_{2}+\|B\|_{2}\right)^{n-1} .
\end{aligned}
$$

### 定理 6.2
谱 $\infty$-距离满足以下估计：
$$
d_{\infty}(A, B) \leqslant(2 n-1) \operatorname{hd}(A, B) 。
$$
### 证明
令$\lambda_{i}-$为$A$的特征值。考虑圈子
$$
D_{i}=\left\{z:\left|z-\lambda_{i}\right| \leqslant \operatorname{hd}(A, B)\right\}, \quad D_{i}(\tau)=\left\{z:\left|z-\lambda_{i}\right| \leqslant\varepsilon(\tau)\right\},
$$
其中有
$$
\varepsilon(\tau)=\left(\|A\|_{2}+\max _{t \in[0,1]}\|A+t(B-A)\|_{2}\right)^{1-\frac{1}{n}} \cdot\|\tau(B-A)\|_{2}^{\frac{1}{n}}, \quad \tau \in[0,1]
$$
根据定理$6.1$，矩阵$A+\tau(B-A)$的所有特征值都包含在圆的并集$D_{i}(\tau)中，i=1，\ldots，n$。类比Gershgorin圆，如果$m$个圆$D_{i}(\tau)$与其他圆隔离，那么它们的并集正好包含矩阵$A+\tau(B-A)$的$m$个特征值。

如果$m$个圆$D_{i}(1)$与其他圆隔离，那么对应的圆$D_{i}$的并集正好包含$m$个特征值​​​$\mu_{i}$（因为高清 $ \left.(A, B) \leqslant \varepsilon(1)\right)$。
设矩阵$B$的圆和特征值的枚举$\mu_{i}$为
$$
\mu_{i} \in \bigcup_{1 \leqslant k \leqslant m} D_{k}, i=1, \ldots, m \text {. }
$$
然后 $\left|\mu_{i}-\lambda_{j}\right| \leqslant(1+2(m-1)) \operatorname{hd}(A, B), \forall i, j=1, \ldots, m$。最坏情况 $m=n$。

==正规矩阵定义：$A^{H} A=A A^{H}$==
==正交矩阵和酉矩阵: $A^*=A^{-1}$==
==埃尔米特矩阵：$A^*=A$==
### 定理 6.3
对于正规矩阵 $A$ 和 $B$，下列不等式成立：
$$
d_{2}(A, B) \leqslant\|A-B\|_{E} 。
$$
证明。矩阵 $A, B$ 是正规的 $\Rightarrow$，有酉矩阵 $P$ 和 $Q$ 使得 **(对于正规矩阵，存在矩阵$P$可让它对角化)**
$$
D_{A}=\operatorname{diag}\left(\lambda_{i}\right)=P^{*} A P, \quad D_{B}=\operatorname{diag}\left(\mu_{i}\right)=Q^{*} B Q .
$$
令 $Z=P^{*} Q, Z^{*} Z=I$。我们使用欧几里得范数和引理 $5.2$ 的酉不变性：
$$
\|A-B\|_{E}^{2}=\left\|D_{A}-Z D_{B} Z^{*}\right\|_{E}^{2}=\left\|D_{A}\right\|_{E}^{2}+\left\|D_{B}\right\|_{E}^{2}-2 \operatorname{Re} \operatorname{tr}\left(Z D_{B} Z^{*} D_{A}^{*}\right) .
$$
为了获得下界，我们写
$$
\gamma=2 \operatorname{Retr}\left(Z D_{B} Z^{*} D_{A}^{*}\right)=\sum_{i=1}^{n} \sum_{j= 1}^{n} s_{i j} \alpha_{i j}, \quad s_{i j}=\left|z_{i j}\right|^{2}, \alpha_{i j}=2 \operatorname{Re} \lambda_{i}^{*} \mu_{j} 。
$$
对于固定的 $\alpha_{i j}$，泛函 $\gamma=\gamma(S)$ 在矩阵集合 $S=\left(s_{i j}\right)$ 上是线性的。我们感兴趣的是它的最大值在具有非负元素且所有行和列总和等于 1 的矩阵集合 $S$ 上（$P$ 和 $Q 的单一性的结果）$。这样的矩阵称为双重随机矩阵。

### 引理 $6.1$（Birkhoff 定理）
任何双随机矩阵 $S$ 都可以表示为有限数量的置换矩阵 $P_{k}$ 的凸组合：
$$
S=\sum_{k=1}^{m} \nu_{k} P_{k}, \quad \nu_{1}+\ldots+\nu_{m}=1, \quad \nu_{1}, \ ldots，\nu_{m} \geqslant 0 。
$$
根据 Birkhoff 定理，$\gamma(S)$ 在其中一个置换矩阵上达到最大值：
$$
\gamma(S) \leqslant \max _{k=1, \ldots, m} \gamma\left(P_{k}\right)=\gamma(\Pi), \quad \Pi-\text { 置换矩阵. }
$$
然后
$$
\begin{aligned}
&\|A-B\|_{E}^{2}=\left\|D_{A}\right\|_{E}^{2}+\left\|D_{B}\right\|_{E}^{2}-2 \operatorname{Re} \operatorname{tr}\left(Z D_{B} Z^{*} D_{A}^{*}\right) \geqslant \\
&\geqslant\left\|D_{A}\right\|_{E}^{2}+\left\|\Pi D_{B} \Pi^{*}\right\|_{E}^{2}-2 \operatorname{Retr}\left(\Pi D_{B} \Pi^{*} D_{A}^{*}\right)=\left\|D_{A}-\Pi D_{B} \Pi^{*}\right\|_{E}^{2} \geqslant d_{2}^{2}(A, B) .
\end{aligned}
$$
这里考虑到矩阵П是酉的。引理 $5.2$ 也被使用。

### 引理 6.2
令矩阵为 $M$ 和 $N$是正规矩阵，$\Omega$ 为对角矩阵。那么 
$$\operatorname{tr}\left((M \Omega-\Omega N)(M-N)^{*}+(M-N)(M \Omega-\Omega N)^{*}\right)=2 \operatorname {tr}\left(\Omega\left((M-N)(M-N)^{*}\right)^{.}\right.$$

### 证明
设 $M=\left(m_{i j}\right), \Omega=\operatorname{diag}\left(w_{1}, \ldots, w_{n}\right), M \Omega M^{*} =\left(a_{i j}\right), \Omega M^{*}=$$\left(b_{i j}\right)$。从 $M$ 的正态性我们得到： $M M^{*}=M^{*} M \Rightarrow$
$$
\sum_{i=1}^{n} m_{k i} \bar{m}_{j i}=\sum_{i=1}^{n} \bar{m}_{i k} m_{i j} \Rightarrow \sum_{i=1}^{n}\left|m_{k i}\right|^{2}=\sum_{i=1}^{n}\left|m_{i k}\right|^{2}, \quad a_{i j}=\sum_{k=1}^{n} m_{i k} w_{k} \bar{m}_{j k}, \Rightarrow \operatorname{tr} M \Omega M^{*}=\sum_{i=1}^{n} \sum_{k=1}^{n} w_{k}\left|m_{i k}\right|^{2} .
$$
$$
b_{i j}=\sum_{k=1}^{n} w_{i} m_{i k} \bar{m}_{j k} \Rightarrow \operatorname{tr} \Omega M M^{*}=\sum_ {i=1}^{n} \sum_{k=1}^{n} w_{i}\left|m_{i k}\right|^{2}=\sum_{i=1}^{n} \sum_{k=1}^{n} w_{k}\left|m_{k i}\right|^{2}=\sum_{i=1}^{n} \sum_{k=1}^{ n} w_{k}\left|m_{ik}\right|^{2} 。
$$
表明$\operatorname{tr} M \Omega M^{*}=\operatorname{tr} \Omega M M^{*}$。类似于 $\operatorname{tr} M M^{*} \Omega=\operatorname{tr} \Omega M M^{*}=\operatorname{tr} M \Omega^{*}$。对于正规矩阵 $N$ 以及对于正规矩阵 $M-N$，可以证明类似的关系。注意 $\forall A \operatorname{tr}(A \Omega)=\operatorname{tr}(\Omega A)$（我们使用 $\Omega$ 是对角矩阵的事实）。现在考虑基本关系：
$$
\begin{aligned}
&\operatorname{tr}\left((M \Omega-\Omega N)(M-N)^{*}+(M-N)(M \Omega-\Omega N)^{*}\right)= \\
&=\operatorname{tr}\left(M \Omega M^{*}-\Omega N M^{*}-M \Omega N^{*}+\Omega N N^{*}+M \Omega M^{*}-M N^{*} \Omega-N \Omega M^{*}+N N^{*} \Omega\right)= \\
&=\operatorname{tr}\left((M-N) \Omega(M-N)^{*}-\Omega N M^{*}+M \Omega M^{*}-M N^{*} \Omega+N N^{*} \Omega\right)= \\
&=\operatorname{tr}\left((M-N) \Omega(M-N)^{*}+\Omega\left(-N M^{*}+M M^{*}-M N^{*}+N N^{*}\right)\right)= \\
&=\operatorname{tr}\left((M-N) \Omega(M-N)^{*}+\Omega(M-N)(M-N)^{*}\right)=2 \operatorname{tr}\left(\Omega(M-N)(M-N)^{*}\right) .
\end{aligned}
$$