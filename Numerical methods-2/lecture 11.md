### 2.6.1 估计对称矩阵 $A$ 和 $B$ 的收敛速度
和以前一样，假设 $y$ 是问题 $(2.4)$ 的精确解，并且 $y_{n}$ 是作为迭代方法 $(2.6)$ 的执行结果获得的近似解。

考虑满足齐次方程的第 $n$ 次迭代的误差 $z_{n}=y_{n}-y$
$$
\begin{aligned}
&B \frac{z_{n+1}-z_{n}}{\tau}+A z_{n}=0, n=0,1, \ldots \\
&z_{0}=y_{0}-y
\end{aligned}
$$
从中可以得到
$$
z_{n+1}=S z_{n}, S=E-\tau B^{-1} A
$$
####  定义
令$A^{T}=A>0$，则泛函$\|y\|_{A}=\sqrt{(A y, y)}$ 称为空间 $H$ 中的算子范数 **(операторной нормой)**。

推论：$\|y\|_{A}=\sqrt{\left(A^{1 / 2} y, A^{1 / 2} y\right)}=\left\|A^{1/2} y\right\|$

#### 引理 2.6.1
令 $A^{T}=A>0, B^{T}=B>0, \rho>0$ 为实数，则不等式
$$
\frac{1-\rho}{\tau} B \leq A \leq \frac{1+\rho}{\tau} B
$$
的充要条件是对于任何 $z_{0} \in H$，误差满足估计
$$
\left\|z_{n+1}\right\|_{A} \leq \rho\left\|z_{n}\right\|_{A}, n=0.1, \ldots
$$
#### 证明
记$v_{n}=A^{1 / 2} z_{n}$，那么：
$$
v_{n+1}=A^{1 / 2} z_{n+1}=A^{1 / 2} S z_{n}=A^{1 / 2} S A^{-1 / 2} v_ {n}=\bar{S} v_{n}
$$
其中$\bar{S}=E-\tau C, C=A^{1 / 2} B^{-1} A^{1 / 2}, C^{T}=C>0$。考虑到上一节证明的引理，我们得到
$$
\begin{gathered}
\left\|z_{n+1}\right\|_{A} \leq \rho\left\|z_{n}\right\|_{A} \Rightarrow\left\|v_{n+1}\right\|_{A} \leq \rho\left\|_{n}\right\|_{A} \Rightarrow\left(\bar{S}^{2} v_{n}, v_{n}\right) \leq \rho^{2}\left(v_{n}, v_{n}\right) \Rightarrow \\
\bar{S}^{2} \leq \rho^{2} E \Rightarrow \rho E \leq \bar{S} \leq \rho E \Rightarrow \frac{1-\rho}{\tau} E \leq C \leq \frac{1+\rho}{\tau} E \Rightarrow \\
\frac{1-\rho}{\tau} C^{-1} \leq E \leq \frac{1+\rho}{\tau} C^{-1} \Rightarrow \\
\frac{1-\rho}{\tau} A^{1 / 2} B A^{-1 / 2} \leq E \leq \frac{1+\rho}{\tau} A^{-1 / 2} B A^{-1 / 2} \Rightarrow \\
\frac{1-\rho}{\tau} B \leq A^{1 / 2} B A^{-1 / 2} \leq \frac{1+\rho}{\tau} B
\end{gathered}
$$
#### 引理 2.6.2
在引理 $(2.6.1)$ 的条件下，我们有估计
$$
\left\|z_{n+1}\right\|_{B} \leq \rho\left\|z_{n}\right\|_{B}, n=0,1, \ldots
$$
#### 证明 
表示$v_{n}=B^{1 / 2} z_{n}$，我们得到$v_{n+1}=\bar{S} v_{n}$，其中$\bar{S}= E -\tau C, C=$ $B^{-1 / 2} A B^{1 / 2}$. 此外，类似于前面的证明
$$
\begin{gathered}
\left\|z_{n+1}\right\|_{B} \leq \rho\left\|z_{n}\right\|_{B} \Rightarrow \frac{1-\rho}{\tau} E \leq C \leq \frac{1+\rho}{\tau} E \Rightarrow \\
\frac{1-\rho}{\tau} B^{1 / 2} E B^{1 / 2} \leq A \leq \frac{1+\rho}{\tau} B^{1 / 2} E B^{1 / 2}
\end{gathered}
$$
#### 定理 2.6.1 
令$A^{T}=A>0, B^{T}=B>0, \gamma_{1} B \leq A \leq \gamma_{2} B$, 其中$\gamma_{1}, \gamma_{2}$ 是实数，满足$\gamma_{2}>\gamma_{1}>0$。 那么对于 $\tau=2 /\left(\gamma_{1}+\gamma_{2}\right)$ 迭代法收敛，并且误差满足估计
$$
\left\|z_{n}\right\|_{A} \leq \rho^{n}\left\|z_{0}\right\|_{A},\left\|z_{n}\right\|_{B} \leq \rho^{n}\left\|z_{0}\right\|_{B}, n=0,1, \ldots
$$
其中 $\rho=\frac{1-\xi}{1+\xi}, \xi=\frac{\gamma_{1}}{\gamma_{2}}$。
#### 证明 
对于不等式 $\gamma_{1} B \leq A \leq \gamma_{2} B$，我们建立：
$$
\gamma_{1}=\frac{1-\rho}{\tau}, \gamma_{2}=\frac{1+\rho}{\tau}, \quad \tau=\frac{2}{\gamma_{1}+\gamma_{2}}，\rho=\frac{\gamma_{2}-\gamma_{1}}{\gamma_{2}+\gamma_{1}}=\frac{1-\ xi}{1+\xi}，\xi=\frac{\gamma_{1}}{\gamma_{2}}。
$$
那么不等式的形式为
$$
\frac{1-\rho}{\tau} B \leq A \leq \frac{1+\rho}{\tau} B 。
$$
根据引理 $(2.6.1)$ 和 $(2.6.2)$，不等式等价于误差估计
$$
\left\|z_{n+1}\right\|_{A} \leq \rho\left\|z_{n}\right\|_{A},\left\|z_{n+1}\right\|_{B} \leq \rho^{n}\left\|z_{n}\right\|_{B}, n=0,1, \ldots
$$
==（证毕）== 
如前所述，矩阵 $A$ 和 $B$ 有时被方便地视为线性有限维空间 $H$ 中的线性算子。 在这种情况下，要求$A^{T}=A>0, B^{T}=B>0$ 意味着算子 $A$ 和 $B$ 是自伴随且正定的，即 $A^{*}=A>0, B^{*}=B>0$。
假设$A^{T}=A>0, B^{T}=B>0$，考虑广义特征值问题 $A \mu=\lambda B \mu$ 等价于寻找特征值​​和矩阵 $B^{-1} A$的特征函数的问题。该问题的方程可以改写为
$$
\left(B^{-1 / 2} A B^{-1 / 2}\right)\left(B^{1 / 2} \mu\right)=\lambda\left(B^{1 / 2} \mu\right) \Rightarrow C \bar{\mu}=\lambda \bar{\mu} 。
$$
这里$C=B^{-1 / 2} A B^{-1 / 2}, \bar{\mu}=B^{1 / 2} \mu$。由于$C^{T}=C>0$，我们得出矩阵 $C$ 的所有特征值 $\lambda_{k}$ (即矩阵 $B^{-1} A$的特征值)，是为正的实数。
从上一小节中证明的陈述可以看出：
$$
\gamma_{1} B \leq A \leq \gamma_{2} B \Rightarrow \gamma_{1} E \leq B^{-1 / 2} A B^{-1 / 2} \leq \gamma_{2} E \Rightarrow \gamma_{1} \leq \lambda_{k} \leq \gamma_{2}, k=1,2, \ldots, m
$$
这意味着 $\gamma_{1}=\lambda_{\min }\left(B^{-1} A\right), \gamma_{2}=\lambda_{\max }\left(B^{- 1 } A\right)-$ 是满足不等式  $\gamma_{1} B \leq A \leq \gamma_{2} B$ 的最精确常数。

### 定义
迭代法 $(2.6)$ 的最优迭代参数为：
$$
\tau=\frac{2}{\lambda_{\min }\left(B^{-1} A\right)+\lambda_{\max }\left(B^{-1} A\right)}
$$
满足条件 $\gamma_{1} B \leq A \leq \gamma_{2} B$ 时，最优迭代参数在所有 $\gamma_{1}, \gamma_{2}$ 为正的集合上最小化为$\rho$ 

### 定义 
迭代法 $(2.6)$ 在满足 $B=E$ 的条件时称作求解系 $(2.4)$ 的简单迭代法，即方法
$$
\frac{y_{n+1}-y_{n}}{\tau}+A y_{n}=f, n=0,1, \ldots 。
$$
### 推论
令$A^{T}=A>0，\lambda_{\min}$和$\lambda_{\max}-$分别为矩阵 $A$ 的最小和最大特征值。 那么对于该简单的迭代方法，若参数满足以下条件：
$$
\tau=\frac{2}{\lambda_{\min }\left(B^{-1} A\right)+\lambda_{\max }\left(B^{-1} A\right)}
$$
则有效误差满足：
$$
\left\|z_{n}\right\| \leq \rho\left\|z_{0}\right\|, n=1,2, \ldots ;
$$
其中
$$
\rho=\frac{1-\xi}{1+\xi}, \xi=\frac{\lambda_{\min }(A)}{\lambda_{\max }(A)}
$$

**我们下面分析其他情况。**
在病态矩阵的情况下，$\xi$ 很小。那么收敛速度
$$
\ln \frac{1}{\rho}=\ln \frac{1+\xi}{1-\xi}=\ln \left(1+\frac{2 \xi}{1-\xi}\right) \approx 2 \xi
$$
也很小，则达到给定精度$\varepsilon$所需的迭代次数是很大的(如下)。
$$
n_{0}(\varepsilon)=\frac{\ln (1 / \varepsilon)}{\ln (1 / \rho)} \approx \frac{\ln (1 / \varepsilon)}{2 \xi}=O\left(\frac{1}{\xi}\right),
$$
这意味着简单迭代法收敛缓慢。可以通过以下方式加速收敛。
1.使用隐式 $(B \neq E)$ 方法，前提是满足下面的条件
$$
\frac{\lambda_{\min }\left(B^{-1} A\right)}{\lambda_{\max }\left(B^{-1} A\right)} \geq \frac{\lambda_{\min }(A)}{\lambda_{\max }(A)} 。
$$

如果选择$B=A$，则收敛速度最大。那么因为 $A\left(y_{1}-y_{0 }\right) -A y_{0}=f$，对于 $\gamma_{1}=$ $\lambda_{\min }\left(B^{-1} A\right)=\lambda_{\max }\left(B^{- 1} A\right)=\gamma_{2}=1$ 的情况有 $\rho=0$。且该方法在第一次迭代时就给出方程 $A y=f$ 的精确解。但是，要计算 $y_{1}$ 时需要求 $A$ 的逆矩阵，这与找到 $y=A^{-1} f$ 的精确解是等同的。
2.减少总迭代次数，可以使用可变迭代参数$\tau=\tau_{n}$，它取决于迭代次数。
3.前两种方法结合使用。