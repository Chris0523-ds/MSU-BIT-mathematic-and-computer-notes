## 迭代法的收敛速率
考虑线性方程组 $Ax=b$ 的迭代方法，有近似值序列 $\left\{x^{(k)}\right\}, k=0,1,2, \ldots$
如果迭代法的误差满足以下条件形式：
$$
\left\|x^{(k)}-x^{*}\right\| \leqslant q^{k}\left\|x^{(0)}-x^{*}\right\|, k=0,1,2, \ldots, \quad 0<q<1
$$
那么我们说，该方法以 $q$ 的几何级数收敛。然后我们可以确定迭代次数足以使初始误差减少所需的次数： 对于 $\forall \varepsilon>0$ 寻找 $k \in \mathbb{N}$ 使得 $q^{k}< \varepsilon $，即 $k \geqslant K(\varepsilon)=\frac{\ln (1 / \varepsilon)}{\ln (1 / q)}$。然后满足
$$
\left\|x^{(k)}-x^{*}\right\| \leqslant \varepsilon\left\|x^{(0)}-x^{*}\right\| .
$$
数 $K(\varepsilon)$ 的整数部分称为获得给定精度所需的**最小迭代次数** $\varepsilon。$ 
表达式 $\ln (1 / q)$ 称为迭代法的收敛速度。 收敛速度由线性变换矩阵 $S$ 的性质决定（注：这里关系是：$z^{(k+1)}= Sz^{(k)}$），不依赖于迭代次数 $k$，也不依赖于初始近似 $x^{(0)}$ 的选择，也不依赖于给定的准确度 $\varepsilon$。 不同迭代方法的质量通常通过它们的收敛速度来比较：$\ln (1 / q)$ 越大，方法越好。
## 收敛速度估计
考虑一种平稳的一步迭代法：
$$
B \frac{x^{(k+1)}-x^{(k)}}{\tau}+A x^{(k)}=b 。
$$
直接研究矩阵$S=I-\tau B^{-1} A$的谱是一项艰巨的任务。 我们需要更简单的收敛条件来估计收敛速度。

### 定理 14.1
令 $A, B$ 为对称的正定矩阵，且满足：
$$
\gamma_{1} B \leqslant A \leqslant \gamma_{2} B, \quad \gamma_{1}, \gamma_{2}>0, \gamma_{2}>\gamma_{1}
$$
对于$\tau=\frac{2}{\gamma_{1}+\gamma_{2}}$，迭代过程收敛，且误差满足：
$$
\begin{aligned}
&\left\|x^{(k)}-x^{*}\right\|_{A} \leqslant \rho^{k}\left\|x^{(0)}-x^{*}\right\|_{A}, k=0,1,2, \ldots \\
&\left\|x^{(k)}-x^{*}\right\|_{B} \leqslant \rho^{k}\left\|x^{(0)}-x^{*}\right\|_{B}, k=0,1,2, \ldots
\end{aligned}
$$
其中
$$
\begin{array}{r}
\forall v \in \mathbb{R}^{n},\|v\|_{A}=\sqrt{\langle A v, v\rangle},\|v\|_{B}=\sqrt{\langle B v, v\rangle}, 
\rho=\frac{1-\xi}{1+\xi}, \quad \xi=\frac{\gamma_{1}}{\gamma_{2}}
\end{array}
$$

在证明定理之前，考虑两个辅助引理:

误差 $z^{(k)}=x^{(k)}-x^{*}$ 的方程形式为：
$$
B \frac{z^{(k+1)}-z^{(k)}}{\tau}+A z^{(k)}=0, \quad k=0,1,2, \ldots \Leftrightarrow z^{(k+1)}=S z^{(k)}, S=I-\tau B^{-1} A
$$

### 引理 14.1
令$A, B$ 为对称正定矩阵，$\rho>0$ 。 矩阵不等式
$$
\frac{1-\rho}{\tau} B \leqslant A \leqslant \frac{1+\rho}{\tau} B
$$
成立，当且仅当对于任何 $z^{(0)}$，迭代方法的误差满足估计 $\left\|z^{(k+1)}\right\|_{A} \leqslant \rho \left\|z^{(k)}\right\|_{A}, k=0,1, \ldots .$
### 证明
令 $w^{(k)}=A^{1 / 2} z^{(k)},\left\|w^{(k)}\right\|=\sqrt{\left\langle w^{(k)}, w^{(k)}\right\rangle}$. 
那么误差估计可以写作 $\left\|w^{(k+1)}\right\| \leqslant \rho\left\|w^{(k)}\right\|$. 
另外， $w^{(k+1)}=\tilde{S} w^{(k)}.$ 其中 $\tilde{S}=A^{1 / 2} S A^{-1 / 2}=I-\tau C, C=A^{1 / 2} B^{-1} A^{1 / 2}$. 
由于矩阵 $\tilde{S}$ 是对称的, 所以
$$
\left\|w^{(k+1)}\right\|^{2}=\left\langle\tilde{S} w^{(k)}, \tilde{S} w^{(k)}\right\rangle=\left\langle\tilde{S}^{2} w^{(k)}, w^{(k)}\right\rangle .
$$
因此，研究的估计等价于不等式：
$
\tilde{S}^{2} \leqslant \rho^{2} I \Leftrightarrow-\rho I \leqslant \tilde{S}
\leqslant \rho I \Leftrightarrow$ $\frac{1-\rho}{\tau} I \leqslant C \leqslant \frac{1+\rho}{\tau} I \Leftrightarrow \frac{1-\rho}{\tau} C^{-1} \leqslant I \leqslant \frac{1+\rho}{\tau} C^{-1} \Leftrightarrow \frac{1-\rho}{\tau} A^{-1 / 2} B A^{-1 / 2} \leqslant I \leqslant \frac{1+\rho}{\tau} A^{-1 / 2} B A^{-1 / 2}$ $\Leftrightarrow \frac{1-\rho}{\tau} B \leqslant A \leqslant \frac{1+\rho}{\tau} B
$
### 引理 14.2
令$A, B$ 为对称正定矩阵，$\rho>0$ 。 矩阵不等式
$$
\frac{1-\rho}{\tau} B \leqslant A \leqslant \frac{1+\rho}{\tau} B
$$
成立，当且仅当对于任何 $z^{(0)}$，迭代方法的误差满足估计 $\left\|z^{(k+1)}\right\|_{B} \leqslant \rho \left\|z^{(k)}\right\|_{B}, k=0,1, \ldots .$
### 证明
令 $w^{(k)}=B^{1 / 2} z^{(k)}, C=B^{-1 / 2} A B^{-1 / 2}$. 那么
$$
\left\|z^{(k+1)}\right\|_{B} \leqslant \rho\left\|z^{(k)}\right\|_{B} \Leftrightarrow\left\|w^{(k+1)}\right\| \leqslant \rho\left\|w^{(k)}\right\| .
$$
另外, $w^{(k+1)}=B^{1 / 2} S B^{-1 / 2} w^{(k)}=(I-\tau C) w^{(k)}$.
$$
\begin{gathered}
\left\|w^{(k+1)}\right\| \leqslant \rho\left\|w^{(k)}\right\| \Leftrightarrow \frac{1-\rho}{\tau} I \leqslant B^{-1 / 2} A B^{-1 / 2} \leqslant \frac{1+\rho}{\tau} I \Leftrightarrow \\
\Leftrightarrow \frac{1-\rho}{\tau} B^{1 / 2} A^{-1} B^{1 / 2} \leqslant I \leqslant \frac{1+\rho}{\tau} B^{1 / 2} A^{-1} B^{1 / 2} \Leftrightarrow \\
\frac{1-\rho}{\tau} A^{-1} \leqslant B^{-1} \leqslant \frac{1+\rho}{\tau} A^{-1} \Leftrightarrow \frac{1-\rho}{\tau} B \leqslant A \leqslant \frac{1+\rho}{\tau} B
\end{gathered}
$$

### 定理证明 $14.1 .$
令
$$
\rho=\frac{1-\xi}{1+\xi}, \xi=\frac{\gamma_{1}}{\gamma_{2}}, \tau=\frac{2}{\gamma_{1}+\gamma_{2}} .
$$
那么
$$
\begin{aligned}
&\frac{1-\rho}{\tau}=\frac{2 \xi}{(1+\xi) \tau}=\frac{\gamma_{1}+\gamma_{2}}{1+\frac{\gamma_{2}}{\gamma_{1}}}=\gamma_{1} \\
&\frac{1+\rho}{\tau}=\frac{2}{(1+\xi) \tau}=\frac{\gamma_{1}+\gamma_{2}}{1+\frac{\gamma_{1}}{\gamma_{2}}}=\gamma_{2}
\end{aligned}
$$
并且定理的证明来自上述引理。

## 最优迭代参数
让我们考虑已证明定理的一些结果。
考虑广义特征值问题
$$
A \mu=\lambda B \mu 。
$$
如果 $\gamma_{1} B \leqslant A \leqslant \gamma_{2} B$，那么对于任何特征向量 $\mu$ 满足：
$$
\gamma_{1}\langle B \mu, \mu\rangle \leqslant\langle A \mu, \mu\rangle=\lambda\langle B \mu, \mu\rangle \leqslant \gamma_{2}\langle B \mu, \mu\rangle 。
$$
那么
$$
\gamma_{1} \leqslant \lambda_{\min }(A, B), \quad \gamma_{2} \geqslant \lambda_{\max }(A, B)\tag{1}
$$
其中 $\lambda_{\min }(A, B), \lambda_{\max }(A, B)$ 是最小和最大的特征值。 因此，$\gamma_{1} B \leqslant$ $A \leqslant \gamma_{2} B$ 保持的最精确常数是 $\gamma_{1}=\lambda_{\min }(A, B )， \gamma_{2}=\lambda_{\max }(A, B)$。

在满足条件（1）的参数集$\gamma_{1}、\gamma_{2}$上，函数的两个变量表示为：
$$
\rho=\frac{1-\xi}{1+\xi}, \quad \xi=\frac{\gamma_{1}}{\gamma_{2}},
$$
在以下点达到最小值：
$$
\tau_{0}=\frac{2}{\lambda_{\min }(A, B)+\lambda_{\max }(A, B)}, \quad \xi=\frac{\lambda_{\min }(A, B)}{\lambda_{\max }(A, B)} 。
$$
这里，$\tau_{0}$ 是**最优迭代参数(оптимальный итерационный параметр)**。
$$
\begin{gathered}
\rho\left(\gamma_{1}, \gamma_{2}\right)=\frac{\gamma_{2}-\gamma_{1}}{\gamma_{2}+\gamma_{1}}, \\
\rho_{\gamma_{1}}^{\prime}=\frac{-2 \gamma_{2}}{\left(\gamma_{2}+\gamma_{1}\right)^{2}}<0, \quad \rho_{\gamma_{2}}^{\prime}=\frac{2 \gamma_{1}}{\left(\gamma_{2}+\gamma_{1}\right)^{2}}>0 .
\end{gathered}
$$
因此，函数 $\rho\left(\gamma_{1}, \gamma_{2}\right)$ 的最小值有
$$
\gamma_{1}=\gamma_{1, \max }=\lambda_{\min }(A, B), \gamma_{2}=\gamma_{2, \min }=\lambda_{\max }(A, B)。
$$

## 简单迭代法的收敛速度
在应用中，当比率 $\frac{\lambda_{\max }(A)}{\lambda_{\min }(A)}$ 非常大时，经常会遇到病态矩阵 $A$ 的问题。 在这种情况下 $\xi$ 接近 0, $\rho$ 接近 1,简单迭代法（对于 $\left.B=I, \tau=\tau_{0}\right)$ 收敛缓慢。让我们估计一下迭代次数 $k_{0}(\varepsilon)$，在 $\xi$ 很小的情况下，要达到给定的准确度 $\varepsilon$，也就是得到估计值
$$
\left\|x^{(k)}-x^{*}\right\| \leqslant \varepsilon\left\|x^{(0)}-x^{*}\right\| .
$$
对于小的 $\xi$，$ \frac{1}{\rho}=\frac{1+\xi}{1-\xi}=(1+\xi)(1+\xi+\bar{o}(\xi) )=1+2 \xi+\bar{o}(\xi)$
$$
\rho^{k}<\varepsilon \Leftrightarrow k \geqslant K(\varepsilon)=\frac{\ln (1 / \varepsilon)}{\ln (1 / \rho)} \approx \frac{\ln ( 1 / \varepsilon)}{2 \xi}=\mathcal{O}\left(\frac{1}{\xi}\right) 。
$$
小 $\xi$ 情况下的简单迭代方法是缓慢收敛的。
有两种方法可以加快迭代方法的收敛速度： 
1) 使用隐式迭代法 $(B \neq I)$； 
2) 保留在显式方法类中，可以根据迭代次数选择$\tau=\tau_{k}$。也使用了这两种方法的组合，即使用带有可变迭代参数的隐式迭代法。

使用隐式方法时，通过选择矩阵$B$，可以增加$\xi=\frac{\lambda_{\min }\left(B^{-1} A\right)}{\lambda_{ \max }\left (B^{-1} A\right)}$ 与 $\frac{\lambda_{\min }(A)}{\lambda_{\max }(A)}$ 比的大小。
## 对于非对称矩阵 $B$ 的误差估计
现在让我们放弃矩阵 $B$ 对称的要求。
### 引理 14.3
令 $D$ 为任意对称正定矩阵。 如果 $\exists B^{-1}$，则满足矩阵不等式，
$$
\left\|z^{(k+1)}\right\|_{D} \leqslant \rho\left\|z^{(k)}\right\|_{D}, k=0,1 , \ldots
$$
当且仅当
$$
\rho^{2} D \geqslant S^{T} D S
$$
其中$S=I-\tau B^{-1} A, z^{(k+1)}=S z^{(k)}$。
### 证明 
不等式 $\left\|z^{(k+1)}\right\|_{D} \leqslant \rho\left\|z^{(k)}\right\|_{D}$ 等价于以下不等式：
$$
\left\langle D S z^{(k)}, S z^{(k)}\right\rangle \leqslant \rho^{2}\left\langle D z^{(k)}, z^{( k)}\right\rangle \Leftrightarrow \rho^{2}\left\langle D z^{(k)}, z^{(k)}\right\rangle \geqslant\left\langle S^{T} D S z^{(k)}, z^{(k)}\right\rangle, k=0,1, \ldots
$$
由于 $z^{(0)}-$ 是任意的，因此仅当 $\rho^{2} D \geqslant S^{T} D S$ 时，才可以满足指示的不等式。
反转：
$$
\left\|z^{(k+1)}\right\|_{D}^{2}=\left\langle D z^{(k+1)}, z^{(k+1)} \right\rangle=\left\langle S^{T} D S z^{(k)}, z^{(k)}\right\rangle \leqslant \rho^{2}\left\langle D z^{ (k)}, z^{(k)}\right\rangle=\rho^{2}\left\|z^{(k)}\right\|_{D}^{2}
$$
### 定理 14.2 
令$A$ 为对称正定矩阵，$B-$ 为非奇异矩阵。 如果矩阵不等式
$$
\frac{B^{T}+B}{2}-\frac{\tau}{2} A \geqslant \frac{1-\rho^{2}}{2 \tau} B^{T} A ^{-1} B，
$$
有一些常数 $\rho \in(0,1)$ 不取决于 $k$，则迭代方法收敛并且误差满足估计
$$
\left\|x^{(k)}-x^{*}\right\|_{A} \leqslant \rho^{k}\left\|x^{(0)}-x^{*} \right\|_{A} 。
$$
### 证明
让我们证明对于 $D=A$ 满足引理 $14.3$ 的条件：
$$
\begin{gathered}
\rho^{2} D \geqslant S^{T} D S \Leftrightarrow \rho^{2} A \geqslant\left(I-\tau A\left(B^{-1}\right)^{T}\right) A\left(I-\tau B^{-1} A\right) \Leftrightarrow \\
\Leftrightarrow \tau A\left(\left(B^{-1}\right)^{T}+B^{-1}\right) A \geqslant\left(1-\rho^{2}\right) A+\tau^{2} A\left(B^{-1}\right)^{T} A B^{-1} A .
\end{gathered}
$$ 
然后我们得到等价的不等式
$$
\tau\left(B+B^{T}\right) \geqslant\left(1-\rho^{2}\right) B^{T} A^{-1} B+\tau^{2} A .
$$
除以 $2\tau$ 并从定理中获得所需的不等式。从引理可以得出 $\left\|z^{(k+1)}\right\|_{A} \leqslant \rho\left\|z^{(k)}\right\|_{A } $ 和 $\rho \in(0,1)$。因此，$\left\|z^{(k)}\right\|_{A} \rightarrow 0$ 为 $k \rightarrow \infty$，即该方法收敛。