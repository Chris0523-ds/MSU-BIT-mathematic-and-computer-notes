# 第1讲 线性代数和数学分析的一些参考资料
## 度量空间(матрическое пространство)
在解决线性代数的计算问题时，我们需要各种对象的“接近度”概念。接近程度通常使用度量（距离）来描述。
### 定义 1.1
令 $M$ 为非空集，$\rho(x, y)$ 为为所有 $x, y \in M$ 定义的非负函数，并具有以下性质：
- $\rho(x, y) \geqslant 0, \forall x, y \in M$, and $\rho(x, y)=0 \Leftrightarrow x=y$;
- $\rho(x, y)=\rho(y, x), \forall x, y \in M$（对称симметричность）；
- $\rho(x, z) \leqslant \rho(x, y)+\rho(y, z), \forall x, y, z \in M$（三角不等式неравенство треугольника）。
那么函数$\rho(x, y)$ 称为**度量(метрикой)** ($x$ 和 $y$ 之间的距离)，集合 $M$ 是**度量空间(метрическое пространство)**。

例子：
- 在集合 $\mathbb{R}$ 上，度量可以引入为 $\rho(x, y)=|x-y|$;
- 在空间 $\mathbb{R}^{n}$ 中，度量可以引入为 $\rho_{\alpha}(x, y)=\left(\sum_{i=1}^{n}\left|x_{i}-y_{i}\right|^{\alpha}\right)^{\frac{1}{\alpha}}, \alpha \geqslant 1$。对于 $\alpha=2$，我们得到欧几里得度量。
- 在空间 $C[a, b]$ 中，度量是 $\rho(x, y)=\max _{t \in[a, b]}|x(t)-y(t)|$。

## 通过度量空间的极限 (Предельный переход в метрическом пространстве)
### 定义 1.2 
一个序列 $\left\{x_{n}\right\}, x_{n} \in M$ 是收敛的，如果 $\exists x \in M: \lim _{n \rightarrow \infty} \rho\left(x_{n}, x\right)=0$。此外，点$x$ 称为序列$\left\{x_{n}\right\}$ 的极限。名称：$x=\lim _{n \rightarrow \infty} x_{n}$。
### 定义 1.3 
序列$\left\{x_{n}\right\}，x_{n}\in M$，称为柯西序列，若满足：
$$
\forall \varepsilon>0  \exists N: \forall n, m \geqslant N \Rightarrow \rho\left(x_{n}, x_{m}\right) \leqslant \varepsilon 。
$$
### 定义 1.4 
如果一个度量空间 $M$ 中的任何柯西序列是收敛的（即满足序列收敛的柯西准则），则称该度量空间是**完备的（полным）**。

### 定义 1.5 
如果集合 $X \subset M$ 包含其所有极限点，则称它是**闭集（замкнутым）**，即 $\forall\left\{x_{n}\right\}, x_{n} \in X, \exists \lim _{ n \rightarrow \infty} x_{n}=x \Rightarrow x \in X$。 （这里 $x-$ 是 $X$ 的极限点。）

集合 $X$ 的闭包 $\bar{X}$ 是其所有极限点的并集。

### 定义 1.6 
数值函数 $f(x), x \in M$ 在点 $x_{0}$ 处被称为连续函数，如果 $\forall\left\{x_{n}\right\}, x_{n} \neq x_{ 0}, \exists \lim _{n \rightarrow \infty} x_{n}=x_{0} \Rightarrow \exists \lim _{n \rightarrow \infty} f\left(x_{n}\right)= f\left(x_{0}\right)$。

## 度量空间的紧致性（Компактность в метрическом пространстве）
### 定义 1.7。
如果 $\forall\left\{x_{n}\right\}$，$x_{n} \in X, \Rightarrow$ 子序列 $\left\{x_{n_{k}}\right\}: \exists \lim _{k \rightarrow \infty} x_{n_{k} }= x \in X$，则称闭集 $X\subset M$ 是**紧集компактным**。

集合 $B_{r}(a)=\{x \in M: \rho(x, a)<r\}$ 称为圆心 $a$ 半径 $r>0$ 的**开球(открытым шаром)**。集合 $B_{r}^{c}(a)=\{x \in M: \rho(x, a) \leqslant r\}$ 称为**封闭球（замкнутым шаром）**。
### 定义 1.8 
一个集合 $X \subset M$ 被称为 **开集(открытым)**，如果
$$
\forall x \in X \exists \varepsilon>0: B_{\varepsilon}(x) \subset X 。
$$
### 定义 1.9 
一个集合 $X \subset M$ 被称为 **有界(ограниченным)**，如果
$$
\exists R>0, \exists a \in X: X \subseteq B_{R}(a) 。
$$
引理 $1.1$（在嵌套球上）。对于任何封闭球序列 $B_{r_{n}}\left(a_{n}\right)$ ，度量空间 M 是 **完备的（полным）** $\Leftrightarrow$ ：
$$
\exists \lim _{n \rightarrow \infty} r_{n}=0, B_{r_{n+1}}\left(a_{n+1}\right) \subset B_{r_{n}}\left(a_{n}\right), \forall n \Rightarrow \exists x^{*} \in B_{r_{n}}\left(a_{n}\right), \forall n .
$$

## 赋范空间 (Нормированное пространство)
考虑一个实数或复数线性（向量）空间 $V$，在其上定义函数 $f(x)=\|x\|$ 使得
1. $\|x\| \geqslant 0, \forall x \in V ;\|x\|=0 \Leftrightarrow x=0$;
2. $\|\alpha x\|=|\alpha| \cdot\|x\|, \forall \alpha \in \mathbb{R}(\mathbb{C}), x \in V$;
3. $\|x+y\| \leqslant\|x\|+\|y\|$。

那这样的函数$\|x\|$是向量$x$的**范数(норма вектора)**，空间$V$称为**赋范的(нормированным)**。
在任何赋范空间中，都可以引入一个度量：
$$
\rho(x, y)=\|x-y\| .
$$
### 定义 1.10 
关于与范数对应的度量是完整的范数空间称为**巴拿赫空间(банаховым пространством)**。

### 定义 1.11 
空间 $V$ 中的两个范数 $\|\cdot\|_{*}$ 和 $\|\cdot\|_{* *}$ 是等价的，如果 $\exists c_{1}, c_{2}>0$:
$$
c_{1}\|x\|_{*} \leqslant\|x\|_{* *} \leqslant c_{2}\|x\|_{*} , \forall x \in V .
$$
###引理 1.2
在任何有限维空间中，任何两个**范数(норма)** 都是等价的。

## $p$-向量的范数（$p$-норма вектора）
令 $V=\mathbb{C}^{n}$ 或 $V=\mathbb{R}^{n}$，以及 $p \geqslant 1(p \in \mathbb{R})$。对于向量 $x=\left(x_{1}, \ldots, x_{n}\right)^{T} \in V$，向量 $x$ 的 $p$-范数是
$$
\|x\|_{p}=\left(\sum_{i=1}^{n}\left|x_{i}\right|^{p}\right)^{1 / p}
$$
### 引理 1.1 
函数 $f(p)=\|x\|_{p}$ 具有以下性质：
$$
\forall x \in V, p_{1}, p_{2}>0:\|x\|_{p_{1}}=1 \Rightarrow \begin{cases}\|x\|_{p_{2 }} \leqslant 1, & p_{2}>p_{1} \\ \|x\|_{p_{2}} \geqslant 1, & p_{2}<p_{1}\end{cases}
$$
### 引理 1.2
令$p, q>1：\frac{1}{p}+\frac{1}{q}=1$。那么对于任何 $a, b \geqslant 0$
$$
a b \leqslant \frac{a^{p}}{p}+\frac{b^{q}}{q}
$$
### 证明
对于 $a=0$ 或 $b=0$，该不等式成立是显而易见的。此外，我们假设$a, b>0$。函数 $f(x)=\ln (x)$ 对于 $x>0$ 是凹函数（因为 $f^{\prime \prime}(x)<0$ ），因此
$$
\forall \lambda \in[0,1] \quad \lambda \ln (x)+(1-\lambda) \ln (y) \leqslant \ln (\lambda x+(1-\lambda) y) 。
$$
现在让 $\lambda=\frac{1}{p}, 1-\lambda=\frac{1}{q}, x=a^{p}, y=b^{q}$。然后
$$
\lambda \ln (x)+(1-\lambda) \ln (y)=\ln (a b) \leqslant \ln (\lambda x+(1-\lambda) y)=\ln \left(\frac{ a^{p}}{p}+\frac{b^{q}}{q}\right) 。
$$

## Hölder 不等式
### 定理 $1.3$（Hölder 不等式）
对于任意 $p, q>1: \frac{1}{p}+\frac{1}{q}=1$, 任意 $x, y \in V=\mathbb{C}^{n}\left (\mathbb{R}^{n}\right)$
$$
\left|\sum_{i=1}^{n} x_{i} y_{i}\right| \leqslant\|x\|_{p} \cdot\|y\|_{q} 。
$$
### 证明
对于 $x=0$ 或 $y=0$，不等式是显而易见的。此外，我们假设 $x, y \neq 0$。

令$\tilde{x}=\frac{x}{\|x\|_{p}}, \tilde{y}=\frac{y}{\|y\|_{q}}$。那么$\|\tilde{x}\|_{p}=\|\tilde{y}\|_{q}=1$。将引理 $1.2$ 与 $a=\tilde{x}_{i}$, $b=\tilde{y}_{i}, i=1, \ldots, n$ 一起使用：
$$
\left|\tilde{x}_{i}\right| \cdot\left|\tilde{y}_{i}\right| \leqslant \frac{\left|\tilde{x}_{i}\right|^{p}}{p}+\frac{\left|\tilde{y}_{i}\right|^{q}}{q} .
$$
让我们为不同的 $i=1, \ldots, n$ 添加这些不等式：
$$
\frac{1}{\|x\|_{p}\|y\|_{q}}\left|\sum_{i=1}^{n} x_{i} y_{i}\right| \leqslant \sum_{i=1}^{n}\left|\tilde{x}_{i}\right| \cdot\left|\tilde{y}_{i}\right| \leqslant \sum_{i=1}^{n}\left(\frac{\left|\tilde{x}_{i}\right|^{p}}{p}+\frac{\left|\tilde{y}_{i}\right|^{q}}{q}\right)=\frac{\left\|\tilde{x}_{i}\right\|_{p}^{p}}{p}+\frac{\left\|\tilde{y}_{i}\right\|_{q}^{q}}{q}=1 .
$$
### замечание 
在 $\mathbb{R}^{n}$ 中，如果 $\exists \alpha>0$，Hölder 不等式变为等式：
$$
\left|x_{i}\right|^{p}=\alpha\left|y_{i}\right|^{q}, x_{i} y_{i} \geqslant 0, \forall i=1, \ldots, n 。
$$
## 闵可夫斯基不等式 (Неравенство Минковского)
### 定理 $1.4$ (闵可夫斯基不等式)
对于任意 $p>1，任意 x x, y \in V=$ $\mathbb{C}^{n}\left(\mathbb{R}^{n}\right)$
$$
\|x+y\|_{p} \leqslant\|x\|_{p}+\|y\|_{p} 。
$$
### 证明
我们两次使用 Hölder 不等式（这里是 $(p-1) q=p)$ ：
$$
\begin{aligned}
&\sum_{i=1}^{n}\left|x_{i}\left\|x_{i}+\left.y_{i}\right|^{p-1} \leqslant\right\| x\left\|_{p} \cdot\left(\sum_{i=1}^{n}\left(\left|x_{i}+y_{i}\right|^{p-1}\right)^{q}\right)^{\frac{1}{q}}=\right\| x \|_{p} \cdot\left(\|x+y\|_{p}\right)^{p / q}\right. \\
&\sum_{i=1}^{n}\left|y_{i}\left\|x_{i}+\left.y_{i}\right|^{p-1} \leqslant\right\| y\left\|_{p} \cdot\left(\sum_{i=1}^{n}\left(\left|x_{i}+y_{i}\right|^{p-1}\right)^{q}\right)^{\frac{1}{q}}=\right\| y \|_{p} \cdot\left(\|x+y\|_{p}\right)^{p / q}\right.
\end{aligned}
$$
тогда
$$
\|x+y\|_{p}^{p}=\sum_{i=1}^{n}\left|x_{i}+y_{i}\right|^{p} \leqslant \sum_ {i=1}^{n}\left(\left|x_{i}\right|+\left|y_{i}\right|\right)\left|x_{i}+y_{i}\right |^{p-1} \leqslant\left(\|x+y\|_{p}\right)^{p / q}\left(\|x\|_{p}+\|y\| _{p}\right) 。
$$
剩下的就是将不等式除以 $\left(\|x+y\|_{p}\right)^{p / q}$。
### замечание
Minkowski 不等式是来自向量 $p$-范数范数定义的三角不等式。
## 向量的 p 范数 (p-норма вектора)
向量的 $p$-范数的特殊情况：
- $p=2 \Rightarrow$ 是向量 $\|x\|_{2}$ 的欧几里得范数。 Hölder 不等式变成了 Cauchy-Bunyakovsky 不等式。
- $p=1 \Rightarrow$
$$
\|x\|_{1}=\sum_{i=1}^{n}\left|x_{i}\right|
$$
这是指定"манхэттенское"距离的规范。
- 取极限案例：
$$
\|x\|_{\infty}=\max _{i=1, \ldots, n}\left|x_{i}\right|=\lim _{p \rightarrow \infty}\|x\| _{p} 。
$$
这是指定切比雪夫距离的规范。
## 矩阵范数(матричные нормы)
在固定大小的矩阵空间中，矩阵的范数可以作为向量范数引入，将矩阵视为元素排列在一个表中的向量。
例子：
$$
A=\left(a_{i j}\right) \in \mathbb{R}^{n \times m} \Rightarrow\|A\|_{v e c, p}=\left(\sum_{i=1} ^{n} \sum_{j=1}^{m}\left|a_{i j}\right|^{p}\right)^{1 / p}, p \geqslant 1 。
$$
然而，除了向量范数的通常属性之外，矩阵范数还使用了一个附加的**乘法属性(свойство мультипликативности)**:
$$
\|A B\| \leqslant\|A\| \cdot\|B\| .
$$
一个例子是欧几里得范数 **(норма Фробениуса)** $(p$-norm of a matrix for $p=2)$ ：
$$
\begin{gathered}
\|A\|_{E}=\left(\sum_{i=1}^{n} \sum_{j=1}^{m}\left|a_{i j}\right|^{2}\right)^{1 / 2}, A \in \mathbb{C}^{n \times m} . \\
\text { 若 } A=\left[a_{1}, \ldots, a_{m}\right] \in \mathbb{C}^{n \times m}, B=\left[b_{1}, \ldots, b_{m}\right]^{T} \in \mathbb{C}^{m \times k}, \text { то } A B=a_{1} b_{1}^{T}+\ldots+a_{m} b_{m}^{T}, \\
\|A B\|_{E} \leqslant\left\|a_{1} b_{1}^{T}\right\|_{E}+\ldots+\left\|a_{m} b_{m}^{T}\right\|_{E}=\left\|a_{1}\right\|_{2} \cdot\left\|b_{1}\right\|_{2}+\ldots+\left\|a_{m}\right\|_{2} \cdot\left\|b_{m}\right\|_{2} \leqslant\|A\|_{E} \cdot\|B\|_{E} .
\end{gathered}
$$
## 矩阵的算子范数(Операторные нормы матриц)
考虑矩阵空间$A \in \mathbb{C}^{n \times m}$。让范数 $\|\cdot\|_{*}$ 以 $\mathbb{C}^{n}$ 给出，范数 $\|\cdot\| _{* *}$。让我们定义矩阵 $A$ 的范数：
$$
\|A\|_{* * *}=\max _{x \neq 0} \frac{\|A x\|_{*}}{\|x\|_{* *}}=\max _{x:\|x\|_{* *}=1}\|A x\|_{*} 。
$$
这是一个算子（从属）范数。执行 **(一致性属性свойство согласованности)**：
$$
\|A x\|_{*} \leqslant\|A\|_{* * *} \cdot\|x\|_{* *} 。
$$
例子：
$$
\|A\|_{p}=\max _{x \neq 0} \frac{\|A x\|_{p}}{\|x\|_{p}} 。
$$
这是矩阵范数，因为对于 $A B \neq 0$
$$
\|A B\|_{p}=\max _{x \neq 0, B x \neq 0} \frac{\|A B x\|_{p}}{\|B x\|_{p}} \frac{\|B x\|_{p}}{\|x\|_{p}} \leqslant \max _{B x \neq 0} \frac{\|A B x\|_{p}}{\|B x\|_{p}} \cdot \max _{x \neq 0} \frac{\|B x\|_{p}}{\|x\|_{p}} \leqslant\|A\|_{p} \cdot\|B\|_{p} .
$$
在代数的过程中，证明了从属范数$\left(A \in \mathbb{C}^{n \times m}\right)$的性质：
- $\|A\|_{1}=\max _{j=\overline{1, m}} \sum_{i=1}^{n}\left|a_{i j}\right|$;
- $\|A\|_{\infty}=\max _{i=\overline{1, n}} \sum_{j=1}^{m}\left|a_{i j}\right|$;
- $\|A\|_{2}$ 等于矩阵 $A$ 的最大奇异值，即$\sqrt{|\lambda|}$ 的最大值，其中 $\lambda$ 是 $A A^{*}$ 和 $A^{*} A$ 的特征值。$\|A\|_{2}-$ 是**谱范数(спектральная норма)**。