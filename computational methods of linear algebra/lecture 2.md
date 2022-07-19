# 来自线性代数的一些资料（续）
## 欧几里得(酉)空间 (Евклидово (унитарное) пространство)
令 $V$ 是一个实数或复数向量空间，对于每对向量 $x, y$ 定义一个数 $\langle x, y\rangle$ 使得
1. $\langle x, x\rangle \geqslant 0, \forall x \in V ;\langle x, x\rangle=0 \Leftrightarrow x=\theta$;
2. $\langle x, y\rangle=\overline{\langle y, x\rangle}$;
3. $\langle\alpha x, y\rangle=\alpha\langle x, y\rangle, \forall \alpha \in \mathbb{C}(\mathbb{R})$;
4. $\langle x+y，z\rangle=\langle x，z\rangle+\langle y，z\rangle$

数 $\langle x, y\rangle-$ 是向量 $x$ 和 $y$ 的标量积。
具有内积的实空间称为**欧几里得的(евклидовым)**，具有内积的复空间称为**酉空间的(унитарным)**。
如果 $\langle x, y\rangle=0$，则向量 $x, y$ 是正交的。
令 $e=\left\{e_{1}, \ldots, e_{n}\right\}$ 为 $\mathrm{V}$的基， $x_{1}, \ldots, x_{n} $ 和 $y_{1}, \ldots, y_{n}$ 是向量 $x, y$ 在此基上的坐标。基 $e$ 是**正交的(ортонормированным)**,当且仅当
$$
\langle x, y\rangle=x_{1} \overline{y_{1}}+\ldots+x_{n} \overline{y_{n}}, \forall x, y \in V 。
$$
标量积生成向量的范数（长度）：$\|x\|=\sqrt{\langle x, x\rangle}$。
### 定理 2.1
为了使线性空间 $V$ 中的范数由某个标量积生成，满足平行四边形恒等式是必要且充分的：$\|x+y\|^{2}+\|x-y\| ^{2}=2\ |x\|^{2}+2\|y\|^{2}, \forall x, y \in V$。
## 等距矩阵 (Изометричные матрицы)
### 定义 2.1
定义 2.1。矩阵 $Q \in \mathbb{C}^{n \times n}$ 被称为在空间 $\mathbb{C}^{n}$的 **(保范矩阵сохраняющей норму)** $\|\cdot\|$  （或关于范数的等距），若满足：
$$
\|Q x\|=\|x\|, \forall x \in \mathbb{C}^{n} 。
$$
示例：$Q$ - 置换矩阵（行或列置换的恒等矩阵）。

让我们研究矩阵 $Q$ 的结构，它保留了向量的 $p$-范数。令 $\|\cdot\|=\|\cdot\|_{p}-$ $p$-norm, $x=e_{i}-i$- 单位矩阵 $\Rightarrow\left\|Q e_{i}\right\|=1$。即 $Q$ 的每一列的 $p$-norm 等于 1。此外，我们使用 Hölder 不等式：
$$
\left\|Q^{T} y\right\|_{q}=\max _{x \neq \theta} \frac{\left|y^{T} Q x\right|}{\|x \|_{p}}=\max _{x \neq \theta} \frac{\left|y^{T} Q x\right|}{\|Q x\|_{p}}=\max _{z \neq \theta} \frac{\left|y^{T} z\right|}{\|z\|_{p}}=\|y\|_{q}，
$$
因此，矩阵 $Q$ 的任何行的 $q$-norm 都等于 1 。
令 $p<2, q>2, \frac{1}{p}+\frac{1}{q}=1$。对于矩阵 $Q$ 的任意列 $q_{i}$ 和任意行 $\tilde{q}_{j}^{T}$
$$
\left\|q_{i}\right\|_{2} \leqslant\left\|q_{i}\right\|_{p}=1,\left\|\tilde{q}_{j} ^{T}\right\|_{2} \geqslant\left\|\tilde{q}_{j}^{T}\right\|_{q}=1, \quad \sum_{i=1 }^{n}\left\|q_{i}\right\|_{2}^{2}=\sum_{j=1}^{n}\left\|\tilde{q}_{j} \right\|_{2}^{2} 。
$$
这只有在 $\left\|q_{i}\right\|_{2}=\left\|\tilde{q}_{j}\right\|_{2}=1, \forall i , j \Rightarrow\left\|q_{i}\right\|_{p}=\left\|q_{i}\right\|_{2}=1, \forall i \Rightarrow$ 在列 $q_ {i}$ 恰好有 1 个元素，模 1 。其余元素为零。对于行也是如此， $p>2$ 也是如此。
因此，对于 $p \neq 2 Q=P \operatorname{diag}\left(d_{1}, \ldots, d_{n}\right)$，其中 $P$ 是置换矩阵，$\left|d_ { i}\right|=1, \forall i$。
## p=2 的等距矩阵 (Изометричные матрицы при p=2)
令$p=2$。那么$V$ 是一个欧几里得（酉）空间。
令$Q$ 为等距矩阵。
标量积可以用相应的范数表示：
- 在 $V=\mathbb{R}^{n}$ 的情况下:$\langle x, y\rangle=\frac{1}{2}\left(\|x+y\|^{2}-\| x \|^{2}-\|y\|^{2}\right)$;
- 在 $V=\mathbb{C}^{n}$ 的情况下: $\langle x, y\rangle=\frac{1}{2}\left(\left(\|x+y\|^{2}- \|x\|^{2}-\|y\|^{2}\right)+i\left(\|x+i y\|^{2}-\|x\|^{2}-\ |i y\|^{2}\right)\right)$
所以等距矩阵**保留(сохранить)** 标量积：
$$
\langle Q x, Q y\rangle=\langle x, y\rangle, \forall x, y \in V 。
$$
如果 $x=e_{i}, y=e_{j}$, 那么 $\left\langle q_{i}, q_{j}\right\rangle=\delta_{i j} \Rightarrow$ 的 $Q$ 列形式正交系统：$Q^{*} Q=I$。因此，矩阵$Q$是**酉(унитарной)** 的：$Q^{*}=Q^{-1}$。
即在2-норма 的情况下，酉矩阵 $Q$ 是等距的。
### замечание 
如果 $Q$ 是酉矩阵，那么 $Q^{-1}-$ 也是酉矩阵。
### 引理 $2.2$（теорема шура）
对于任何具有特征值$\lambda_{1}, \ldots, \lambda_{n}$ 的矩阵$A \in \mathbb{C}^{n \times n}$，存在这样一个酉矩阵 $Q$ 满足：
- $Q^{*} A Q$ - 上三角矩阵；
- $\operatorname{diag}\left(Q^{*} A Q\right)=\operatorname{diag}\left(\lambda_{1}, \ldots, \lambda_{n}\right)$。

## 正规矩阵（Нормальные матрицы）
### 定义 2.2
如果 $A^{*} A=A A^{*}$，则矩阵 $A$ 称为**正规的(нормальной)**。
特别是 Hermitian（对称）矩阵 $\left(A^{*}=A\right)$ 和酉（正交） $\left(A^{*}=A^{-1}\right)$ 矩阵。

### 定理 2.3
矩阵 $A \in \mathbb{C}^{n \times n}$ 是正规的当且仅当在 $\mathbb{C}^{n}$ 中存在其特征向量的正交基。

### 定理 2.4
一个正规矩阵 A 是 Hermitian 当且仅当它的所有特征值都是实数。

### 定理 2.5
一个正规矩阵是酉的，当且仅当它的所有模特征值都等于 $1 .$

对于任何矩阵 $A \in \mathbb{C}^{n \times n}$，**Hermitian展开式(эрмитово разложение)** 是有效的：
$$
\exists H, K: A=H+i K, H^{*}=H, K^{*}=K 。
$$
## 有符号矩阵 (Знакоопределенные матрицы)
### 定义 2.3
矩阵 $A \in \mathbb{C}^{n \times n}$ 称为**正定矩阵(положительно определенной)**，如果 $\langle x, A x\rangle>0, \forall x \in \mathbb{C}^{n}, x \neq \theta$。如果 $\langle x, A x\rangle<0, \forall x \in \mathbb{C}^{n}, x \neq \theta$，则称矩阵 $A$ 是**负定矩阵(отрицательно определенной)**。

非负定矩阵和非正定矩阵的定义类似。如果 $A$ 是符号定的并且$A=H+i K$ 是Hermitian 展开式，那么$K=0$。
### замечание
符号定义的矩阵 $A$ 不必是对称的。
### 定理 2.6。
矩阵$A \in \mathbb{C}^{n \times n}$是非负（正）定的 $\Leftrightarrow$其所有特征值都是非负（正）的。

### 定理 2.7
如果矩阵 A 是非负（正）定的，那么它的任何**前导子矩阵(ведущая подматрица)** $B$ 也是非负（正）定的。
证明。令 $y=[\tilde{y}, \theta]^{T} \in \mathbb{C}^{n}$。
$$
y^{T} A y=y^{T}\left(\begin{array}{ll}B & * \\ * & *\end{array}\right) y=(\tilde{y})^{T} B \tilde{y} \geqslant 0(>0), \forall \tilde{y}
$$
对于任何矩阵 $A$，矩阵 $A^{*} A$ 总是非负定的：$A^{*} A \geqslant 0$。