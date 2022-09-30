# 线性方程组求解的微扰理论
## 微扰理论（Теория возмущений）
线性代数中出现的主要问题之一是从已知的 $x$ 中找到（计算）某个映射 $f(x)$ 的值。 通常计算算法会给出一些误差（error）。 因此提出以下问题：在小扰动 $x$ 下，$f(x)$ 计算的结果可以改变多少？
### 举例
令 $f(x)-$ 是一个可微函数 $x，\Delta x$ 是参数 $x$ 的一个小扰动。 然后 $f(x+\Delta x) \approx f(x)+f^{\prime}(x) \Delta x$。 假设 $x \neq 0, f^{\prime}(x) \neq 0$。 然后我们可以引入以下衡量问题对干扰的敏感性的方法：
$$
\frac{f(x+\Delta x)-f(x)}{\|f(x)\|} \approx\left(\frac{f^{\prime}(x)}{\|f(x)\|}\|x\|\right) \frac{\Delta x}{\|x\|} .
$$
即，该问题敏感性的相对度量（条件数）可以称为
$$
\text { cond } f(x)=\frac{\left\|f^{\prime}(x)\right\|}{\|f(x)\|}\|x\| .
$$
接下来，我们讨论线性方程组$A x=f$ 解的扰动估计。此时误差可能出现在等式的右边部分和矩阵中：
$$
f \rightarrow f+\Delta f, A \rightarrow A+\Delta A, \quad \Delta f, \Delta A-\text {微量}
$$
## 矩阵级数
设 $A_{k} \in \mathbb{C}^{n \times n}, k=1,2, \ldots .$ 考虑矩阵级数
$$
\sum_{k=0}^{\infty} A_{k}
$$
### 定义 3.1。
矩阵级数称为收敛的，如果存在一个矩阵 $A \in \mathbb{C}^{n \times n}$，使得:
$$
\exists \lim _{N \rightarrow \infty}\left\|S_{N}-A\right\|=0, S_{N}=\sum_{k=0}^{N} A_{k} 。
$$
### 定理 $3.1$（关于矩阵级数收敛的充分条件）
若数列 $\sum_{k=0}^{\infty}\left\|A_{k}\right\|$ 收敛，则矩阵级数 $\sum_{k=0}^{\infty} A_{k}$ 也收敛。

级数 $\sum_{k=0}^{\infty} F^{k}$ 是诺依曼级数。如果 $\|F\|<1$，则级数 $\sum_{k=0}^{\infty}\left\|F^{k}\right\|$ 收敛 $\Rightarrow$ 诺伊曼级数收敛. （我们使用不等式： $\left\|F^{k}\right\| \leqslant\|F\|^{k}$。）

### 定义 3.2
矩阵 $F$ 的最大特征值绝对值被称之为谱半径。用符号$\rho(F)$来表示。
### 定义 3.3
==如果$\rho(F)<1$，则称矩阵 $F$ 是收敛的。==
### 引理 3.1 
具有矩阵 $F \in \mathbb{C}^{n \times n}$ 的诺伊曼级数是收敛的 $\Leftrightarrow $ 矩阵 $F$ 是收敛的。
## 逆矩阵

### 引理 3.2 
如果矩阵 $F$ 满足 $\|F\|<1$，则矩阵 $A=I-F$ 是可逆的，并且
$$
(I-F)^{-1}=\sum_{k=0}^{\infty} F^{k} ; \quad\left\|(I-F)^{-1}\right\| \leqslant \frac{\|I\|}{1-\|F\|} .
$$
## 线性系条件数
考虑一个具有非奇异矩阵 $A$ 的系统 $A x=f, f \neq \theta$。 考虑扰动系统$(A+\Delta A)\tilde{x}=f+\Delta f$。 
问题： $\tilde{x}$ 与 $x$ 的值有多大不同？
假设 $\left\|A^{-1} \Delta A\right\|<1$。然后
$\tilde{x}-x=(A+\Delta A)^{-1}(f+\Delta f)-A^{-1} f=\left((A+\Delta A)^{-1}-A^{-1}\right) f+(A+\Delta A)^{-1} \Delta f=$
$$
=\left(\left(I+A^{-1} \Delta A\right)^{-1}-I\right)\left(A^{-1} f\right)+\left(I+A^{-1} \Delta A\right)^{-1}\left(A^{-1} \Delta f\right)=
$$

$$
=\left(\sum_{k=1}^{\infty}\left(-A^{-1} \Delta A\right)^{k}\right)\left(A^{-1} f\right)+\left(\sum_{k=0}^{\infty}\left(-A^{-1} \Delta A\right)^{k}\right)\left(A^{-1} \Delta f\right) .
$$
将 $\|\tilde{x}-x\|$ 除以 $\|x\|=\left\|A^{-1} f\right\|$ 并估计解的相对误差：
$$
\begin{gathered}
\frac{\|\tilde{x}-x\|}{\|x\|} \leqslant\left\|A^{-1} \Delta A\right\| \sum_{k=0}^{\infty}\left\|A^{-1} \Delta A\right\|^{k}+\frac{\left\|A^{-1}\right\|\|\Delta f\|\|A\|}{\|f\|} \sum_{k=0}^{\infty}\left\|A^{-1} \Delta A\right\|^{k}= \\
\quad=\frac{\left\|A^{-1}\right\| \cdot\|A\|}{1-\left\|A^{-1} \Delta A\right\|}\left(\frac{\|\Delta A\|}{\|A\|}+\frac{\|\Delta f\|}{\|f\|}\right) .
\end{gathered}
$$
这里需要使用不等式 $\|f\| \leqslant\|A\| \cdot\|x\|$。
### 定义 3.4
$\operatorname{cond}A=\left\|A^{-1}\right\| \cdot\|A\|$ ——矩阵 $A$ 的条件数。
条件数表征解 $x$ 对矩阵和右侧的小扰动的敏感性。 对于退化矩阵，$cond A=\infty$。

## 估计解的相对误差
相对误差的最终估计是通过选择右侧及其扰动来实现的，并使用固定的非奇异矩阵 $A$。 让
$$
\begin{gathered}
A=\sum_{k=1}^{n} \sigma_{k} v_{k} u_{k}^{*}-\text { сингулярное разложение, } \\
f=v_{1}, x=\sigma_{1}^{-1} u_{1}, \Delta f=\varepsilon v_{n}, \Delta A=0 .
\end{gathered}
$$
那么：
$$
\begin{gathered}
\operatorname{cond}_{2} A=\left\|A^{-1}\right\|_{2} \cdot\|A\|_{2}=\frac{\sigma_{1}}{\sigma_{n}},\|f\|_{n}=1,\|\Delta f\|_{2}=\varepsilon \\
\|\tilde{x}-x\|_{2}=\left\|A^{-1} \Delta f\right\|_{2}=\left\|\varepsilon \sigma_{n}^{-1} u_{n}\right\|_{2}=\varepsilon \sigma_{n}^{-1} \\
\Rightarrow \frac{\|\tilde{x}-x\|_{2}}{\|x\|_{2}}=\frac{\varepsilon \sigma_{n}^{-1}}{\sigma_{1}^{-1}}=\left\|A^{-1}\right\|_{2} \cdot\|A\|_{2} \cdot \frac{\|\Delta f\|_{2}}{\|f\|_{2}}
\end{gathered}
$$

## 对角优势(Диагональное преобладание)
矩阵 $A=\left\{a_{i j}\right\} \in \mathbb{C}^{n \times n}$ 具有行对角线优势，若满足条件：
$$
\left|a_{i i}\right|>r_{i}=\sum_{j=1, j \neq i}^{n}\left|a_{i j}\right|, i=1, \ldots, n.
$$
矩阵 $A$ 具有列对角线优势，若满足条件：
$$
\left|a_{j j}\right|>c_{j}=\sum_{i=1, i \neq j}^{n}\left|a_{i j}\right|, j=1, \ldots, n.
$$
### 定理 3.2。 
具有行或列对角线优势的矩阵是非退化的。
对于具有对角优势的矩阵，还可以推导出 $\left\|A^{-1}\right\|_{\infty}$ 的估计值：令 $\alpha=\min _{i}\left(\left|a_{i i}\right|-r_{i}\right)$, 且向量$x$满足$\left|x_{k}\right|=\|x\|_{\infty}$。然后
$$
\begin{gathered}
\alpha\|x\|_{\infty}=\alpha\left|x_{k}\right| \leqslant\left|a_{k k} x_{k}\right|-\sum_{j \neq k}\left|a_{k j}\right|\left|x_{j}\right| \leqslant\left|a_{k k} x_{k}\right|-\left|\sum_{j \neq k} a_{k j} x_{j}\right| \leqslant\left|\sum_{j} a_{k j} x_{j}\right| \leqslant \\
\quad \leqslant \max _{k}\left|\sum_{j} a_{k j} x_{j}\right|=\|A x\|_{\infty}, \\
\left\|A^{-1}\right\|_{\infty}=\max _{z \neq 0} \frac{\left\|A^{-1} z\right\|_{\infty}}{\|z\|_{\infty}}=\max _{x=A^{-1} z \neq 0} \frac{\|x\|_{\infty}}{\|A x\|_{\infty}} \leqslant \frac{1}{\alpha}=\frac{1}{\min _{i}\left(\left|a_{i i}\right|-r_{i}\right)} .
\end{gathered}
$$
因此我们得到：$\|A\|_{\infty} \leqslant \max _{i}\left(\left|a_{i i}\right|+r_{i}\right)$。
最后，
$$
\operatorname{cond}_{\infty} A \leqslant \frac{\max _{i}\left(\left|a_{i i}\right|+r_{i}\right)}{\min _{i }\left(\left|a_{i i}\right|-r_{i}\right)} 。
$$
通过转置矩阵处理上个式子，也可以得到估计
$$
\begin{aligned}
\|A\|_{1} \leqslant \max _{j}\left(\left|a_{j j}\right|+c_{j}\right), \quad &\left\|A^{-1}\right\|_{1} \leqslant \frac{1}{\beta}, \beta=\min _{j}\left(\left|a_{j j}\right|-c_{j}\right) \\
\operatorname{cond}_{1} A \leqslant \frac{\max _{j}\left(\left|a_{j j}\right|+c_{j}\right)}{\min _{j}\left(\left|a_{j j}\right|-c_{j}\right)}
\end{aligned}
$$