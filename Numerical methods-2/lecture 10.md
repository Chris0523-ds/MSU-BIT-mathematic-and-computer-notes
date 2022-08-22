
### 2.5.1 处理矩阵不等式的规则 (Правила действий с матричными неравенствами)
==注意：以下的矩阵 $A>0$ 等价于矩阵是正定矩阵，即任意$(Ax,x)>0$==
#### 引理 2.5.1
如果 $A$ 是实对称矩阵（即 $A^{T}=A$），则存在正交矩阵 $Q$（即 $Q^{T}=Q^{-1}$）使得 $A =Q^{T} \Lambda Q$，其中 $\Lambda=$ $\operatorname{diag}\left[\lambda_{1}, \lambda_{2}, \ldots, \lambda_{m} \right]$是一个对角矩阵，其主对角线包含矩阵$A$的特征值。
#### 引理 2.5.2
如果$A^{T}=A$，则不等式 $A \geq 0 (A>0)$ 等价于其所有特征值的非负性（正性）。
#### 证明 
令 $A \mu_{k}=\lambda_{k} \mu_{k}, k=1,2, \ldots, \lambda_{m} .$ 假设 $A \geq 0$，我们得到
$$
0 \leq\left(A \mu_{k}, \mu_{k}\right)=\lambda_{k}\left(\mu_{k}, \mu_{k}\right) \Rightarrow \lambda_{k } \geq 0
$$
假设 $\lambda_{k} \geq 0$，由引理 $2.5 .1$，我们得到任何 $v \in H$
$$
(A v, v)=\left(Q^{T} \Lambda Q v, v\right)=(\Lambda Q v, Q v)=\sum_{k=1}^{m} \lambda_{k } w_{k}^{2} \geq 0
$$
其中$w=Q v$。

#### 引理 2.5.3 
如果 $A^{T}=A>0$，则 $A^{-1}>0$ 存在。
#### 证明
根据引理 $2.5 .2$，矩阵$A$的所有特征值 $\lambda_{k}$ 都是正的，因此 $\operatorname{det}A\neq 0$ 并且存在一个矩阵 $A^{- 1}$，其正性来自其所有特征值的正性 ​​​$\lambda_{k}^{-1}\left(A \mu_{k}=\lambda_{k} \mu_{k} \Rightarrow A^ {-1} \mu_{k} =\lambda_{k}^{-1} \mu_{k}\right)$。

#### 引理 2.5.4
对于对称矩阵 $A$ 和任意数 $\rho>0$，矩阵不等式 $-\rho E \leq A \leq \rho E$ 和 $A^{2} \leq \rho^{2} E$ 是等价的。
#### 证明
令$\lambda_{k}-$为矩阵 $A$ 的特征值。考虑矩阵 $B=\rho E-A$，其中 $B^{T}=B \geq 0$。由引理 $2.5.2$，最后一个不等式等价于矩阵$B$的特征值$b_{k}=\rho-\lambda_{k}$的非负性，因此$\lambda_{k} \geq-\rho$。类似地，证明了$\lambda_{k} \geq-\rho$。
因此不等式 $-\rho E \leq A \leq \rho E$ 和 $\lambda_{k}^{2} \leq \rho^{2}$ 是等价的。
由于 $\lambda_{k}^{2} $ 是矩阵$A^{2}\left(A \mu_{k}=\lambda_{k} \mu_{k} \Rightarrow A^{ 2} \mu_{k}=\lambda_{k}^{2} \mu_{k}\right)$ 的特征值，通过考虑矩阵$C=\rho^{2} E-A^{2}$，其特征值为$\rho^{ 2}-\lambda_{k}^{2} \geq 0$，我们得到等价的不等式 $A^{2} \leq \rho^{2} E$。

#### 引理 2.5.5
如果$A^{T}=A \geq 0(A>0)$，则存在矩阵 $B$ 使得$B^{2}=A$, $B^{T}=B \geq 0 (B>0)$。

#### 证明
令$\lambda_{k}-$为矩阵$A$的特征值，$k=1,2,\ldots,m$。根据引理 $2.5 .1,2.5 .2$，存在矩阵 $Q$ 使得 $A=Q^{T} \Lambda Q$，其中 $\Lambda=\operatorname{diag}\left[\lambda_{ 1}, \lambda_{2}, \ldots, \lambda_{m}\right], \lambda_{k} \geq 0$。我们令矩阵 $\Lambda^{1 / 2}=\operatorname{diag}\left[\sqrt{\lambda_{1}}, \sqrt{\lambda_{2}}, \ldots, \sqrt{\lambda_{m}}\right]$.。那么矩阵 $B=Q^{T} \Lambda^{1 / 2} Q$ 具有在引理的陈述中指出的性质：
$$
\begin{gathered}
B^{2}=Q^{T} \Lambda^{1 / 2} Q Q^{T} \Lambda^{1 / 2} Q=Q^{T} \Lambda Q=A \\
B^{T}=\left(Q^{T} \Lambda^{1 / 2} Q\right)^{T}=Q^{T}\left(Q^{T} \Lambda^{1 / 2}\right)^{T}=Q^{T} \Lambda^{1 / 2} Q=B \\
(B v, v)=\left(\Lambda^{1 / 2} Q v, Q v\right)=\sum_{k=1}^{m} \sqrt{\lambda_{k}} w_{k}^{2} \geq 0 \forall v \in H
\end{gathered}
$$
其中$w=Q v$。
#### 引理 2.5.6
令 $A^{T}=A$ 和 $C-$ 是一个非奇异矩阵。 那么不等式 $A \geq 0(A>0)$ $u C^{T} A C \geq 0\left(C^{T} A C>0\right)$ 是等价的。
#### 证明
让我们证明 $A \geq 0(A>0)$ 意味着 $C^{T} A C \geq 0\left(C^{T} A C>0\right)$ ，反之亦然。
1. 如果 $A \geq 0$ 对任何 $v \in H$ 我们有 $\left(C^{T} A C v, v\right)=(A C v, C v) \geq 0$，因为 $ C v \in H$。 所以 $C^{T} A C \geq 0$
2. 现在让 $C^{T} A C \geq 0$。 由于 $C^{-1}$ 存在，$v \in H$ 的任何元素都可以表示为 $w=C v$。 那么$(A v, v)=(A C w, C w)=\left(C^{T} A C w, w\right) \geq 0$，即$A \geq 0$。

#### 引理 2.5.7 
令 $A^{T}=A, B^{T}=B$ 和 $C$ 是一个非退化矩阵。 那么不等式 $A \geq B(A>B) u C^{T} A C \geq C^{T} B C\left(C^{T} A C>C^{T} B C\right)$ 是等价的.
### 证明 
根据引理 $2.5 .6$
$$
A-B \geq 0 \Rightarrow C^{T}(A-B) C \geq 0 \Rightarrow C^{T} A C \geq C^{T} B C
$$
#### 引理 2.5.8
令$A^{T}=A>0，\alpha$ 和 $\beta$ 是任意实数。 那么不等式 $\alpha A \geq \beta E$ 和 $\alpha E \geq \beta A^{-1}$ 是等价的。

#### 证明
根据引理$2.5 .5$，有矩阵$A^{1 / 2}=\left(A^{1 / 2}\right)^{T}>0, A^{-1 / 2}=\left(A^{-1 / 2}\right)^{T}>0$ 。使用引理 $2.5 .7$，我们得到
$$
\begin{gathered}
\alpha A \geq \beta E \Rightarrow \alpha A^{-1 / 2} A A^{-1 / 2} \geq \beta A^{-1 / 2} E A^{-1 / 2} \Rightarrow \\
\alpha A^{-1 / 2} A^{1 / 2} A^{1 / 2} A^{-1 / 2} \geq \beta A^{-1} \Rightarrow \alpha E \geq \beta A^{-1}
\end{gathered}
$$
#### 引理 2.5.9 
令 $A^{T}=A>0, B^{T}=B>0, \alpha $ 和 $ \beta-$ 为任意实数。 那么不等式 $\alpha A \geq \beta B$ 和 $\alpha B^{-1} \geq \beta A^{-1}$ 是等价的。
#### 证明 
使用引理 $2.5 .7,2.5 .8$, 我们得到
$$
\begin{gathered}
\alpha A \geq \beta B \Rightarrow \alpha B^{-1 / 2} A B^{-1 / 2} \geq \beta E \\
\alpha E \geq \beta\left(B^{-1 / 2} A B^{-1 / 2}\right)^{-1} \Rightarrow \alpha E \geq \beta B^{1 / 2} A^{-1} B^{1 / 2} \\
\alpha B^{-1 / 2} E B^{-1 / 2} \geq \beta A^{-1} \Rightarrow \alpha B^{-1} \geq \beta A^{-1}
\end{gathered}
$$
