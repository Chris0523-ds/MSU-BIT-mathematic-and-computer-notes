## 特征值和向量的小扰动
假设矩阵 $A$ 只有简单的（成对不同的）特征值，并且扰动矩阵的形式为
$$
A(\varepsilon)=A+A_{1} \varepsilon+\mathcal{O}\left(\varepsilon^{2}\right)
$$
令 $P$ 是 $A$ 的特征向量矩阵，$\Lambda=P^{-1} A P$ 是对角特征值矩阵 $A$。让我们放
$$
\Omega(\varepsilon)=P^{-1} A(\varepsilon) P=\Lambda+\Omega_{1} \varepsilon+\mathcal{O}\left(\varepsilon^{2}\right), \quad \ Omega_{1}=P^{-1} A_{1} P 。
$$
矩阵$\Omega(\varepsilon)$ 与$A(\varepsilon)$ 具有相同的特征值。对于小的 $\varepsilon$，矩阵 $\Omega(\varepsilon)$ 的 Gershgorin 圆不会相交，这意味着矩阵 $\Omega(\varepsilon)$ 具有简单（不同的）特征值。
令 $\Lambda(\varepsilon)$ 和 $Z(\varepsilon)$ 为特征值和特征向量矩阵 $\Omega(\varepsilon)$ ：
$$
\begin{aligned}
&\Lambda(\varepsilon)=Z^{-1}(\varepsilon) \Omega(\varepsilon) Z(\varepsilon), \Lambda(\varepsilon)-\text { диагональная, } \\
&\Lambda(\varepsilon)=\Lambda+\Lambda_{1} \varepsilon+\tilde{\Lambda}(\varepsilon), \Lambda(0)=\Lambda, \tilde{\Lambda}(\varepsilon)=\bar{o}(\varepsilon) \\
&Z(\varepsilon)=I+Z_{1} \varepsilon+\tilde{Z}(\varepsilon), Z(0)=I, \tilde{Z}(\varepsilon)=\bar{o}(\varepsilon)
\end{aligned}
$$
对于小的 $\varepsilon>0 \operatorname{diag} Z(\varepsilon) \neq 0$。矩阵 $Z(\varepsilon)$ 被定义为列归一化。因此，可以认为
$$
\operatorname{diag} Z(\varepsilon)=I, \operatorname{diag} Z_{1}=0, \operatorname{diag} \tilde{Z}(\varepsilon)=0 。
$$
将上述矩阵展开式代入 $\Omega(\varepsilon) Z(\varepsilon)=Z(\varepsilon) \Lambda(\varepsilon)$ ：
$$
\left(\Lambda+\Omega_{1} \varepsilon+\mathcal{O}\left(\varepsilon^{2}\right)\right)\left(I+Z_{1} \varepsilon+\tilde{Z}(\varepsilon)\right)=\left(I+Z_{1} \varepsilon+\tilde{Z}(\varepsilon)\right)\left(\Lambda+\Lambda_{1} \varepsilon+\tilde{\Lambda}(\varepsilon)\right) \text {. } \tag{1}
$$
让我们扩展括号并只写出 $\varepsilon$ 中的线性项：
$$
\left(\Lambda Z_{1}-Z_{1} \Lambda+\Omega_{1}-\Lambda_{1}\right) \varepsilon+\ldots=0 。
$$
因此，对于小的 $\varepsilon$
$$
\Lambda Z_{1}-Z_{1} \Lambda=\Lambda_{1}-\Omega_{1} \Rightarrow \Lambda_{1}=\operatorname{diag} \Omega_{1}, \Lambda Z_{1} -Z_{1} \Lambda=-\operatorname{off} \Omega_{1} \text {. }
$$
让我们回到关系（1）：
$$
\left(\Lambda+\Omega_{1} \varepsilon+\mathcal{O}\left(\varepsilon^{2}\right)\right)\left(I+Z_{1} \varepsilon\right)-\left( I+Z_{1} \varepsilon\right)\left(\Lambda+\Lambda_{1} \varepsilon\right)=\mathcal{O}\left(\varepsilon^{2}\right) 。
$$
对于$\varepsilon>0$,
$$
\left\|\left(I+Z_{1} \varepsilon\right)^{-1}\right\|=\mathcal{O}(1) \Rightarrow\left(I+Z_{1} \varepsilon\right)^{-1}\left(\Lambda+\Omega_{1} \varepsilon+\mathcal{O}\left(\varepsilon^{2}\right)\right)\left(I+Z_{1} \varepsilon\right)-(\Lambda+\Lambda \varepsilon)=\mathcal{O}\left(\varepsilon^{2}\right) .
$$
因此，矩阵$\Lambda+\Omega_{1} \varepsilon+\mathcal{O}\left(\varepsilon^{2}\right)$的特征值可达$\mathcal{O}\left(\varepsilon ^{2 }\right)$ 与 $\Lambda+\Lambda_{1} \varepsilon$ 的对角元素一致。所以$\tilde{\Lambda}=\mathcal{O}\left(\varepsilon^{2}\right)$。
矩阵 $\tilde{Z}$ 满足关系
$$
\left(\Lambda+\Omega_{1} \varepsilon+\mathcal{O}\left(\varepsilon^{2}\right)\right) \tilde{Z}-\tilde{Z}\left(\Lambda+\Lambda 1 \varepsilon+\mathcal{O}\left(\varepsilon^{2}\right)\right)=\mathcal{O}\left(\varepsilon^{2}\right), \operatorname{diag} \tilde{ Z}=0
$$
这是一个关于 $\tilde{Z}$ 的元素的线性方程组，它具有非退化（对于小 $\varepsilon$ ）方阵。所以$\tilde{Z}=\mathcal{O}\left(\varepsilon^{2}\right)$。
### 定理 5.1
令$P^{-1} A P=\Lambda-$ 是一个对角矩阵，具有矩阵$A$ 的成对不同特征值。那么，对于 的小值，矩阵 $A(\varepsilon)=A+A_{1} \varepsilon+$ $\mathcal{O}\left(\varepsilon^{2}\right)$ 是可对角化的：
$$
P^{-1}(\varepsilon) A(\varepsilon) P(\varepsilon)=\Lambda(\varepsilon)，
$$
因此
$$
\begin{gathered}
\Lambda(\varepsilon)=\Lambda+\Lambda_{1} \varepsilon+\mathcal{O}\left(\varepsilon^{2}\right), P(\varepsilon)=P\left(I+Z_{1} \varepsilon+\mathcal{O}\left(\varepsilon^{2}\right)\right) \\
\Lambda_{1}=\operatorname{diag}\left(P^{-1} A_{1} P\right)
\end{gathered}
$$
并且矩阵 $Z_{1}$ 由方程唯一被确定
$$
\operatorname{diag} Z_{1}=0, \Lambda Z_{1}-Z_{1} \Lambda=-\operatorname{off}\left(P^{-1} A_{1} P\right) 。
$$
结果。矩阵 $A(\varepsilon)$ 的特征值 $\lambda_{i}(\varepsilon)$ 具有以下形式
$$
\lambda_{i}(\varepsilon)=\lambda_{i}+q_{i}^{T} A_{1} p_{i} \varepsilon+\mathcal{O}\left(\varepsilon^{2}\right ),
$$
其中 $q_{i}^{T}-$ 行矩阵 $P^{-1}$。除了，
$$
\left|q_{i}^{T} A_{1} p_{i}\right| \leqslant\left\|A_{1}\right\|_{2} \cdot\left\|q_{i}\right\|_{2} \cdot\left\|p_{i}\right\| _{2}=\left\|A_{1}\right\|_{2} \cdot s\left(\lambda_{i}\right) 。
$$
数 $s\left(\lambda_{i}\right)$ 称为特征值 $\lambda_{i}$ 的 **条件化 (обусловленностью)**。这个数字表征了到特征值 $\lambda_{i}$ 是倍数的矩阵的距离。
### 定理 5.2
令矩阵 A 有一个简单的特征值 $\lambda_{i}$，条件为 $s\left(\lambda_{i}\right)$。那么存在一个矩阵$A+\Delta A$，其中$\lambda_{i}-$是一个多重特征值，$and$
$$
\|\Delta A\|_{2} \leqslant \frac{\|A\|_{2}}{\sqrt{s^{2}\left(\lambda_{i}\right)-1}}
$$
### 证明
假设矩阵 $A$ 简化为上三角形式（根据 Schur 定理，定理 $2.2$ ）
$$
A=\left[\begin{array}{cc}
\lambda_{i} & z^{T} \\
0 & B
\end{array}\right]
$$
然后
令 $\tilde{B}=B+\frac{v z^{T}}{\|v\|_{2}^{2}} \Rightarrow \lambda_{i}-$ 矩阵的特征值 $\tilde{B}$。现在让
$$
\Delta A=\left[\begin{array}{cc}
0 & 0 \\
0 & \frac{v z^{T}}{\|v\|_{2}^{2}}
\end{array}\right] \Rightarrow\|\Delta A\|_{2} \leqslant \frac{\left\|z^{T}\right\|_{2}}{\|v\|_{2}} \leqslant \frac{\|A\|_{2}}{\|v\|_{2}}=\frac{\|A\|_{2}}{\sqrt{s^{2}\left(\lambda_{i}\right)-1}} .
$$
数 $\lambda_{i}$ 是重数 $\geqslant 2$ 的矩阵 $A+\Delta A$ 的特征值。
### 对扰动的分析
让级数 $A(\varepsilon)=\sum_{k=0}^{\infty} A_{k} \varepsilon^{k}$ 收敛于所有 $\varepsilon:|\varepsilon|<\varepsilon_{0} $ .令矩阵 $A_{0}$ 只有简单的特征值。那么对于足够小的 $\varepsilon$ 矩阵 $A(\varepsilon)$ 可以通过 $P(\varepsilon)$ 对角化：
$$
\begin{gathered}
P^{-1}(\varepsilon) A(\varepsilon) P(\varepsilon)=\Lambda(\varepsilon) \\
\Lambda(\varepsilon)=\sum_{k=0}^{\infty} \Lambda_{k} \varepsilon^{k}, P(\varepsilon)=\sum_{k=0}^{\infty} P_{k} \varepsilon^{k} .
\end{gathered}
$$
求矩阵 $\Lambda_{k}, P_{k}$。令 $Z_{k}=P_{0}^{-1} P_{k}, \Omega_{k}=P_{0}^{-1} A_{k} P_{0}$。然后
$$
\left(\Lambda_{0}+\Omega_{1} \varepsilon+\ldots\right)\left(I+Z_{1} \varepsilon+\ldots\right)=\left(I+Z_{1} \varepsilon+\ ldots\right)\left(\Lambda_{0}+\Lambda_{1} \varepsilon+\ldots\right) \text {. }
$$
使 $\varepsilon^{k}$ 处的系数相等：
$$
\Lambda_{0} Z_{k}-Z_{k} \Lambda_{0}=\Lambda_{k}-\Phi_{k}, \quad \Phi_{k}=\sum_{i=1}^{k -1}\left(\Omega_{i} Z_{k-i}-Z_{k-i} \Omega_{i}\right)+\Omega_{k}
$$
最后，
$$
\Lambda_{k}=\operatorname{diag} \Phi_{k}, \quad \Lambda_{0} Z_{k}-Z_{k} \Lambda_{0}=-\operatorname{off} \Phi_{k} .
$$
知道 $i \leqslant k-1$ 的 $\Lambda_{i}, Z_{i}$，我们可以得到 $\Lambda_{k}, Z_{k}$。
## Hadamard 不等式
### 定理 5.3
令 $A=\left[\begin{array}{lll}a_{1} & \ldots & a_{n}\end{array}\right] \in \mathbb{C}^{n \times n}， \operatorname{det} A \neq 0 .$ 然后
$$
|\operatorname{det}(A)| \leqslant\left\|a_{1}\right\|_{2} \cdot \ldots \cdot\left\|a_{n}\right\|_{2} .
$$
证明。 Gram-Schmidt 正交化过程应用于向量 $a_{1}、\ldots、a_{n}$。结果，将获得向量$b_{1}、\ldots、b_{n}$的正交系统。令 $B=$ $\left[\begin{array}{lll}b_{1} & \ldots & b_{n}\end{array}\right]-$ 为正交矩阵。从 Gram-Schmidt 过程图可以看出
$$
\exists C=\left(c_{i j}\right)-\text { 上三角矩阵 : } A=B C,
$$
$$
\begin{gathered}
c_{i j}=\left\langle a_{j}, b_{i}\right\rangle, 1 \leqslant i \leqslant j ; \quad c_{i j}=0, j \leqslant i \leqslant n, \\
\forall i=1, \ldots, n a_{i}=\sum_{j=1}^{i}\left\langle a_{i}, b_{j}\right\rangle b_{j}, \quad\left\|a_{i}\right\|_{2}^{2}=\sum_{j=1}^{i}\left|\left\langle a_{i}, b_{j}\right\rangle\right|^{2} .
\end{gathered}
$$
$$
|\operatorname{det} A|^{2}=\operatorname{det}\left(A^{*} A\right)=\operatorname{det}\left(C^{*} B^{*} B C\right)=\operatorname{det} C^{*} C=|\operatorname{det} C|^{2}=\prod_{i=1}^{n}\left|\left\langle a_{i}, b_{i}\right\rangle\right|^{2} \leqslant \prod_{i=1}^{n} \sum_{j=1}^{i}\left|\left\langle a_{i}, b_{j}\right\rangle\right|^{2}=\prod_{i=1}^{n}\left\|a_{i}\right\|_{2}^{2} \text {. }
$$
结果。 Hadamard 不等式变为等式 $\Leftrightarrow$
$$
\left|\left\langle a_{i}, b_{i}\right\rangle\right|^{2}=\sum_{j=1}^{i}\left|\left\langle a_{i}, b_{j}\right\rangle\right|^{2}, \forall i \Leftrightarrow a_{i}=\left\langle a_{i}, b_{i}\right\rangle b_{i}, \forall i .
$$

## 辅助утверждение
### 引理 5.1
对于任何矩阵 $A \in \mathbb{C}^{n \times m}$
$$
\|A\|_{E}^{2}=\operatorname{tr}\left(A A^{*}\right) \text {. }
$$
### 证明 
令$A=\left(a_{i j}\right), A A^{*}=\left(b_{i j}\right)$。然后
$$
\forall i, j \quad b_{i j}=\sum_{k=1}^{m} a_{i k} \bar{a}_{j k} \Rightarrow b_{i i}=\sum_{k=1} ^{m} a_{i k} \bar{a}_{i k}=\sum_{k=1}^{m}\left|a_{i k}\right|^{2} \Rightarrow \operatorname{tr} \left(A A^{*}\right)=b_{11}+\ldots+b_{n n}=\sum_{i=1}^{n} \sum_{k=1}^{m}\left| a_{ik}\right|^{2}=\|A\|_{E}^{2} 。
$$
### 引理 5.2
对于任意矩阵 $A, B \in \mathbb{C}^{n \times m}$
$$
\|A-B\|_{E}^{2}=\|A\|_{E}^{2}+\|B\|_{E}^{2}-2 \operatorname{Re} \operatorname {tr}\left(B A^{*}\right) 。
$$
### 证明
欧几里得矩阵范数 $\|\cdot\|_{E}$ 对应于标量积。最后
$$
\|A-B\|_{E}^{2}=\langle A-B, A-B\rangle=\langle A, A\rangle+\langle B, B\rangle-\langle B, A\rangle-\langle A, B \rangle=\|A\|_{E}^{2}+\|B\|_{E}^{2}-\langle B, A\rangle-\overline{\langle B, A\rangle} .
$$
让我们写出矩阵 $A=\left(a_{i j}\right)$ 和 $B=\left(b_{i j}\right)$ 的内积的定义：
$$
\langle B, A\rangle=\sum_{i=1}^{n} \sum_{k=1}^{m} b_{i k} \bar{a}_{i k} 。
$$
同时，如果$B A^{*}=\left(c_{i j}\right)$，则
$$
c_{i j}=\sum_{k=1}^{m} b_{i k} \bar{a}_{j k} \Rightarrow \operatorname{tr}\left(B A^{*}\right)=\sum_ {i=1}^{n} \sum_{k=1}^{m} b_{i k} \bar{a}_{i k}=\langle B, A\rangle \quad \Rightarrow\langle B, A \rangle+\overline{\langle B, A\rangle}=2 \operatorname{Retr}\left(B A^{*}\right) 。
$$
### 矩阵的欧几里得范数的酉不变性
引理 5.1 的推论。矩阵范数 $\|\cdot\|_{E}$ 具有酉不变性。
设$A \in \mathbb{R}^{n \times m}$。对于任何酉矩阵 $U \in \mathbb{R}^{n \times n}, V \in \mathbb{R}^{m \times m}$
$$
\|U A V\|_{E}^{2}=\operatorname{tr}\left((U A V)^{*}(U A V)\right)=\operatorname{tr}\left(V^{*}\left(A^{*} A\right) V\right) .
$$
令 $V=\left(v_{i j}\right),\left(A^{*} A\right)=\left(a_{i j}\right), V^{*}\left(A^{ *} A\right) V=\left(c_{i j}\right)$。然后
$$
\begin{gathered}
c_{i i}=\sum_{j=1}^{m} \bar{v}_{j i} \sum_{k=1}^{m} a_{j k} v_{k i}=\sum_{j=1}^{m} \sum_{k=1}^{m} a_{j k} \bar{v}_{j i} v_{k i}, \\
\sum_{i=1}^{m} c_{i i}=\sum_{j=1}^{m} \sum_{k=1}^{m} a_{j k} \sum_{i=1}^{m} \bar{v}_{j i} v_{k i}=\sum_{j=1}^{m} \sum_{k=1}^{m} a_{j k}\left\langle v_{k}^{T}, v_{j}^{T}\right\rangle=\sum_{j=1}^{m} a_{j j}
\end{gathered}
$$
最后，
$$
\operatorname{tr}\left(V^{*}\left(A^{*} A\right) V\right)=\operatorname{tr}\left(A^{*} A\right)=\| A\|_{E}^{2}
$$