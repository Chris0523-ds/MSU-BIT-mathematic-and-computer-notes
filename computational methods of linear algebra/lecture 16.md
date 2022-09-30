## 变分类型的迭代方法（Итерационные методы вариационного типа）
考虑迭代法的形式为
$$
B \frac{x^{(k+1)}-x^{(k)}}{\tau_{k+1}}+A x^{(k)}=b 。
$$
在前面讨论的方法中，参数 $\tau_{k}$ 是使用边界 $\gamma_{1} \leqslant \lambda_{\min }(A)$ 和 $\gamma_{2} \geqslant \lambda_{ \max }(A)$ 作为矩阵 $A$ 的特征值。
现在我们将从误差最小化条件中选择这些参数
$$
\left\|x^{(k+1)}-x^{*}\right\|_{D}
$$
对于给定的误差
$$
\left\|x^{(k)}-x^{*}\right\|_{D} 。
$$
这里$D$是一个固定的对称正定矩阵，
$$
\|v\|_{D}=\sqrt{\langle D v, v\rangle} 。
$$
对于不同的矩阵 $B$ 和 $D$，我们得到不同的迭代方法。
这些方法的收敛速度不高于切比雪夫方法。 它们的优点是不必知道矩阵 $A$ 的频谱值的边界。
## 最小残差法（Метод минимальных невязок）
令$A$ 是对称的、正定矩阵。令 $r^{(k)}=\left(A x^{(k)}-b\right)$ 是在第 $k$ 次迭代时的残差。误差 $z^{(k)}$ 和残差 $r^{(k)}$ 的关系可以用 $A z^{(k)}=r^{(k)}$ 表示。
让我们将显式 $(B=I)$ 迭代方法重写为 $x^{(k+1)}=x^{(k)}-\tau_{k+1} r^{(k)}$。
最小残差法是一种迭代方法，其中参数 $\tau_{k+1}$ 从给定范数的最小条件 $\left\|r^{(k+1)}\right\|$ 中选择$\left\|r^{(k)}\right\|$。让我们获得迭代参数 $\tau_{k+1}$ 的显式表达式。
$$
A x^{(k+1)}=A x^{(k)}-\tau_{k+1} A r^{(k)} \Rightarrow r^{(k+1)}=r^{ (k)}-\tau_{k+1} A r^{(k)},
$$
也就是说，残差满足与误差 $z^{(k)}=x^{(k)}-x^{*}$ 相同的方程。让我们将等式的两边都提升为一个标量平方：
$$
\left\|r^{(k+1)}\right\|^{2}=\left\|r^{(k)}\right\|^{2}-2 \tau_{k+1}\left\langle r^{(k)}, A r^{(k)}\right\rangle+\tau_{k+1}^{2}\left\|A r^{(k)}\right\|^{2} .
$$
$\left\|r^{(k+1)}\right\|$ 的最小值在 $\tau_{k+1}=\tau_{k+1}^{*}=\frac{\left\langle A r^{(k)}, r^{(k)}\right\rangle}{\left\|A r^{(k)}\right\|^{2}}$。
在最小残差法中，从第 $k$ 次迭代到第 $k+1$ 次迭代可以描述如下： 
1) 通过找到的值 $x^{(k)}$，计算残差向量 $r^{(k)}=A x^{(k)}-b$
2) 按指定公式求$\tau_{k+1}=\tau_{k+1}^{*}$
3) 根据迭代法的主方程，计算$x^{(k+1)}$

下面考虑最小残差法的收敛速度不低于具有最优参数 $\tau$ 的简单迭代法。
### 定理 16.1 
令 $A$ 为对称正定矩阵。 对于最小残差法的误差，估计
$$
\left\|A\left(x^{(n)}-x^{*}\right)\right\| \leqslant \rho_{0}^{n}\left\|A\left(x^{(0)}-x^{*}\right)\right\|, n=0,1, \ldots,
$$
其中
$$
\rho_{0}=\frac{1-\xi}{1+\xi}, \quad \xi=\frac{\lambda_{\min }(A)}{\lambda_{\max }(A)} .
$$
## 最小修正法（Метод минимальных поправок） 
考虑隐式迭代法
$$
x^{(k+1)}=x^{(k)}-\tau B^{-1} r^{(k)}, r^{(k)}=A x^{(k)} -b 。
$$
向量 $w^{(k)}=B^{-1} r^{(k)}$ 称为第 $k+1$ 次迭代的校正。 修正满足与隐式方法误差$z^{(k)}=x^{(k)}-x^{*}$相同的方程：
$$
B \frac{w^{(k+1)}-w^{(k)}}{\tau_{k+1}}+A w^{(k)}=0 。
$$
令矩阵 $B$ 是正定的对称矩阵。 **最小修正法**是一种隐式迭代法，其中参数 $\tau_{k+1}$ 对于给定的 $w^{(k)}$从最小条件$\left\|w^{(k+1)}\right\|_{B}=\left\langle B w^{(k+1)}, w^{(k+1)}\right\rangle^{1 / 2}$中选取。 在$B=I$的情况下，最小修正法与最小残差法是一致的。 
让我们重写修正方程：
$$
\begin{gathered}
w^{(k+1)}=w^{(k)}-\tau_{k+1} B^{-1} A w^{(k)} \\
\left\|w^{(k+1)}\right\|_{B}^{2}=\left\|w^{(k)}\right\|_{B}^{2}-2 \tau_{k+1}\left\langle A w^{(k)}, w^{(k)}\right\rangle+\tau_{k+1}^{2}\left\langle B^{-1} A w^{(k)}, A w^{(k)}\right\rangle .
\end{gathered}
$$

如果 $\tau_{k+1}=\tau_{k+1}^{*}=\frac{\left\langle A w^{(k)}, w^{(k)}\right\rangle} {\left\langle B^{-1} A w^{(k)}, A w^{(k)}\right\rangle}$，那么修正 $\left\|w^{(k+1)}\right\|_{B}$ 将是最小的。
在最小修正方法中，每次迭代需要：
1) 求解线性方程组 $B w^{(k)}=r^{(k)}$ 并找到修正 $w^{(k )}$ 
2) 求解线性方程组 $B v^{(k)}=A w^{(k)}$ 并找到向量 $v^{(k)}=B^{-1} A w^ {(k)} $
3) 计算$\tau_{k+1}$。

最小修正法的收敛速度由广义特征值问题$A x=\lambda B x$的谱边界决定。
### 定理 16.2
令 $A, B$ 为对称正定矩阵， $\lambda_{\min }\left(B^{-1} A\right), \lambda_{\max }\left(B^{-1} A\right)$ 是广义问题的最小和最大特征值。对于最小修正法的误差，满足估计：
$$
\begin{gathered}
\left\|A\left(x^{(n)}-x^{*}\right)\right\|_{B^{-1}} \leqslant \rho_{0}^{n} \cdot\left\|A\left(x^{(0)}-x^{*}\right)\right\|_{B^{-1},}, n=0,1, \ldots \\
\rho_{0}=\frac{1-\xi}{1+\xi}, \xi=\frac{\lambda_{\min }\left(B^{-1} A\right)}{\lambda_{\max }\left(B^{-1} A\right)}
\end{gathered}
$$

## 最速下降法（Метод скорейшего спуска）
再次考虑显式迭代法，从最小条件 $\left\|z^{(k+1)}\right\|_{A}$ 中选择迭代参数 $\tau_{k+1}$ 对于给定的向量 $z ^{(k)}$，其中 $z^{(k)}=x^{(k)}-x^{*}$。 误差 $z^{(k)}$ 满足方程
$$
z^{(k+1)}=z^{(k)}-\tau_{k+1} A z^{(k)} .
$$
因此，
$$
\left\|z^{(k+1)}\right\|_{A}^{2}=\left\|z^{(k)}\right\|_{A}^{2}- 2 \tau_{k+1}\left\langle A z^{(k)}, A z^{(k)}\right\rangle+\tau_{k+1}\left\langle A^{2} z ^{(k)}, A z^{(k)}\right\rangle 。
$$

如果 $\tau_{k+1}=\frac{\left\langle A z^{(k)}, A z^{(k)}\right\rangle}{\left\langle A^{2} z ^{(k)}, A z^{(k)}\right\rangle} $，那么误差 $\left\|z^{(k+1)}\right\|_{A}$ 将是最小的。
$z^{(k)}$ 的值是未知的，但是我们知道 $A z^{(k)}=r^{(k)}=A x^{(k)}-b$。 因此$\tau_{k+1}=\frac{\left\langle r^{(k)}, r^{(k)}\right\rangle}{\left\langle A r^{(k) } , r^{(k)}\right\rangle}$ 
结果，我们得到一个**显式的最速下降法(явный метод скорейшего спуска)**
如定理 16.1 所示，可以证明最速下降法与具有最优参数 $\tau=\tau_{0}$ 的简单迭代法的收敛速度相同。 对于最速下降法的误差，满足以下估计：
$$
\left\|x^{(n)}-x^{*}\right\|_{A} \leqslant \rho_{0}^{n}\left\|x^{(0)}-x^ {*}\right\|_{A}, n=0,1, \ldots, \rho_{0}=\frac{1-\xi}{1+\xi}, \xi=\frac{\lambda_ {\min }(A)}{\lambda_{\max }(A)} 。
$$

**隐式最速下降法(Неявным методом скорейшего спуска)** 以如下形式表示：
$$
B \frac{x^{(k+1)}-x^{(k)}}{\tau_{k+1}}+A x^{(k)}=b,
$$
其中参数 $\tau_{k+1}$ 是从最小条件 $\left\|z^{(k+1)}\right\|_{A}$ 中选择的。 这其中误差 $z^{(k)}=x^{(k)}-x^{*}$ 满足方程
$$
z^{(k+1)}=z^{(k)}-\tau_{k+1} B^{-1} A z^{(k)} 。
$$
即有：
$$
\begin{gathered}
\left\|z^{(k+1)}\right\|_{A}^{2}=\left\|z^{(k)}\right\|_{A}^{2}-2 \tau_{k+1}\left\langle A z^{(k)}, B^{-1} A z^{(k)}\right\rangle+\tau_{k+1}^{2}\left\langle A B^{-1} A z^{(k)}, B^{-1} A z^{(k)}\right\rangle \Rightarrow \\
\Rightarrow\left\|z^{(k+1)}\right\|_{A}^{2}=\left\|z^{(k)}\right\|_{A}^{2}-2 \tau_{k+1}\left\langle r^{(k)}, w^{(k)}\right\rangle+\tau_{k+1}^{2}\left\langle A w^{(k)}, w^{(k)}\right\rangle .
\end{gathered}
$$
如果 $\tau_{k+1}=\frac{\left\langle r^{(k ) }, w^{(k)}\right\rangle}{\left\langle A w^{(k)}, w^{(k)}\right\rangle}$，误差 $\left\|z^{(k+1)}\right\|_{A}$ 将是最小的。
此外，对于最速下降的隐式方法，满足以下估计：
$$
\left\|x^{(n)}-x^{*}\right\|_{A} \leqslant \rho_{0}^{n}\left\|x^{(0)}-x^ {*}\right\|_{A}, n=0,1, \ldots, \rho_{0}=\frac{1-\xi}{1+\xi}, \xi=\frac{\lambda_ {\min }\left(B^{-1} A\right)}{\lambda_{\max }\left(B^{-1} A\right)} 。
$$

## 共轭梯度法（Метод сопряжённых градиентов）
共轭梯度法是一种两步迭代法，即找到一个新的迭代$x^{(k+1)}$，使得前两次迭代 $x^{(k)}$ 和 $x^{( k-1)}$ 被使用。显然，这增加了所需的内存量。但同时，通过正确选择参数，收敛速度将高于一步法。特别是所考虑的共轭梯度法在任何初始近似值的有限迭代中收敛。

令$A$ 矩阵系，$B$ 为对称的正定矩阵。考虑以下一类隐式两步迭代方法：
$$
B \frac{\left(x^{(k+1)}-x^{(k)}\right)+\left(1-\alpha_{k+1}\right)\left(x^{(k)}-x^{(k-1)}\right)}{\tau_{k+1} \alpha_{k+1}}+A x^{(k)}=b, k=1,2, \ldots
$$
这里 $\alpha_{k+1}, \tau_{k+1}-$ 是迭代参数。要开始计算，需要设置两个初始近似值 $x^{(0)}$ 和 $x^{(1)}$。我们任意设置初始近似值$x^{(0)}$，并使用一步公式计算向量$x^{(1)}$(对于$k=0, \alpha_{1}=1$):
$$
B \frac{x^{(1)}-x^{(0)}}{\tau_{1}}+A x^{(0)}=b 。
$$
如果找到参数$\alpha_{k+1}、\tau_{k+1}$，那么新的近似$x^{(k+1)}$用前面两个值$​​​​x^{(k)}$ 和 $x^{(k-1)}$ 来表示。即可以表示为公式
$$
x^{(k+1)}=\alpha_{k+1} x^{(k)}+\left(1-\alpha_{k+1}\right) x^{(k-1)}-\tau_{k+1} \alpha_{k+1} w^{(k)},
$$
其中 $w^{(k)}=B^{-1} r^{(k)}, r^{(k)}=A x^{(k)}-b$。

## 最小化共轭梯度法的误差（Минимизация погрешности в методе сопряжённых градиентов） 
误差 $z^{(k)}=x^{(k)}-x^{*}$ 满足方程 
$$
z^{(k+1)}=\alpha_{k+1}\left(I - \tau_{k+1} B^{-1} A\right) z^{(k)}+\left(1-\alpha_{k+1}\right) z^{(k-1)} , k=1,2, \ldots, \quad z^{(1)}=\left(I-\tau_{1} B^{-1} A\right) z^{(0)} .
$$
令 $v^{(k)}=A^{1 / 2} z^{(k)}$, $\left\|v^{(k)}\right\|=\left\|z^{(k )}\right\|_{A}$, $C=A^{1 / 2} B^{-1} A^{1 / 2}$。 函数 $v^{(k)}$ 满足方程：

$$
v^{(k+1)}=\alpha_{k+1}\left(I-\tau_{k+1} C\right) v^{(k)}+\left(1-\alpha_{k +1}\right) v^{(k-1)}, k=1,2, \ldots, \quad v^{(1)}=\left(I-\tau_{1} C\right) v ^{(0)} 
$$
令 $A$ 和 $B$ 是满足不等式 $\gamma_{1} B \leqslant A \leqslant \gamma_{2} B, \gamma_{2}>\gamma_{1}>0$ 的对称正定矩阵，那么 $C=C^{T}>0$，$\gamma_{1} I \leqslant C \leqslant \gamma_{2} I$。 
所以，如果我们依次找到向量 $v^{(1)}, v^{(2)}, \ldots, v^{(k-1)}$，必然可以得到： $v^{( k)}= P_{k}(C) v^{(0)}$，其中 $P_{k}(C)$ 是满足条件 $P_{k}(0)=I$ 的算子 $C$ 中的 $k$ 次矩阵多项式。

有必要选择迭代参数 $\tau_{k},\alpha_{k}$，使得对于任何 $n=1,2，\ldots$ $\left\|v^{(n)}\right\|=\left\|z^{(n)}\right\|_{A}$将是最小值。

参数 $\tau_{1}$ 是从给定向量 $v^{(0)}$ 中 $\left\|v^{(1)}\right\|$ 最小的条件中找到的，类似于最陡的下降法：$\tau_ {1}=\frac{\left\langle C v^{(0)}, v^{(0)}\right\rangle}{\left\|C v^{(0) }\right\|^ {2}}$。 请注意，选择 $\tau_{1}$ 满足等式 $\left\langle C v^{(1)}, v^{(0)}\right\rangle=0$，其中 $\alpha_{1}=1$。

考虑在第 $k$ 次迭代中出现的误差 $v^{(k)}=P_{k}(C) v^{(0)}$。 我们将多项式 $P_{k}(C)$ 写成如下：
$$
P_{k}(C)=I+\sum_{i=1}^{k} a_{i}^{(k)} C^{i}, a_{i}^{(k)}=a_{i }^{(k)}\left(\alpha_{i}, \tau_{i}\right), i=1,2, \ldots, k 。
$$
那么
$$
\begin{gathered}
v^{(k)}=v^{(0)}+\sum_{i=1}^{k} a_{i}^{(k)} C^{i} v^{(0)}, k=1,2, \ldots \\
\left\|v^{(n)}\right\|^{2}=\sum_{i, j=1}^{n} a_{i}^{(n)} a_{j}^{(n)}\left\langle C^{i} v^{(0)}, C^{j} v^{(0)}\right\rangle+2 \sum_{j=1}^{n} a_{j}^{(n)}\left\langle v^{(0)}, C^{j} v^{(0)}\right\rangle+\left\|v^{(0)}\right\|^{2} .
\end{gathered}
$$
因此 $\left\|v^{(n)}\right\|^{2}$ 是变量 $a_{1}^{(n)}、\ldots、a_{n}^{(n)}$ 中的二次多项式。其导数 $\frac{\partial\left\|v^{(n)}\right\|^{2}}{\partial a_{j}^{(n)}}, j=1,2, \ldots, n$ 等于零。
因此我们得到了关于 $a_{i}^{(n)}$ 的方程组：
$$
\sum_{i=1}^{n} a_{i}^{(n)}\left\langle C^{j} v^{(0)}, C^{i} v^{(0)} \right\rangle+\left\langle C^{j} v^{(0)}, v^{(0)}\right\rangle=0,
$$
其解对应于 $\left\|v^{(n)}\right\|^{2}$ 的最小值。
使用得到的方程，我们现在需要找到参数 $\alpha_{k}, \tau_{k}, k=1,2, \ldots, n$。 请注意，求 $a_{i}^{(n)}$ 的方程可以写成以下形式
$$
\left\langle C^{j} v^{(0)}, v^{(n)}\right\rangle=0, j=1,2, \ldots, n \tag{1}
$$
### 引理 16.1 
条件 $(1)$ 等价于条件 $\left\langle C v^{(j)}, v^{(n)}\right\rangle=0, j=0,1, \ldots, n-1$。

现在，使用引理，有必要从条件 $\left\langle C v^{(j)}, v^{(n)}\right\rangle=0, n=1,2, \ldots, j=0,1, \ldots, n-1 $中找到迭代参数

也就是说，向量 $v^{(0)}, v^{(1)}, \ldots, v^{(k)}, \ldots$ 在标量积$\langle u, v\rangle_ {C}=\langle C u, v\rangle$ 的意义上必须是成对正交的。

假设参数 $\tau_{1}, \tau_{2}, \ldots, \tau_{k}, \alpha_{1}, \alpha_{2}, \ldots, \alpha_{k}$选择为最优结果。那么，让我们使用关系$\left\langle C v^{(j)}, v^{(k+1)}\right\rangle=0, j=0,1, \ldots, k$ 构造最优的 $\tau_{k+1}, \alpha_{k+1}$。
可以证明，如果我们取
$$
\tau_{k+1}=\frac{\left\langle C v^{(k)}, v^{(k)}\right\rangle}{\left\|C v^{(k)}\right\|^{2}}, \quad \alpha_{k+1}=\left(1-\frac{\tau_{k+1}}{\tau_{k}} \cdot \frac{1}{\alpha_{k}} \cdot \frac{\left\langle C v^{(k)}, v^{(k)}\right\rangle}{\left\langle C v^{(k-1)}, v^{(k-1)}\right\rangle}\right)^{-1} .
$$
指定的恒等式将被满足。
注意，也要满足以下的等式关系：
$$
\begin{gathered}
v^{(k)}=A^{1 / 2} z^{(k)}, C=A^{1 / 2} B^{-1} A^{1 / 2}, z^{(k)}=x^{(k)}-x^{*}, A z^{(k)}=A x^{(k)}-b=r^{(k)}, B^{-1} r^{(k)}=w^{(k)} \\
C v^{(k)}=A^{1 / 2} w^{(k)},\left\langle C v^{(k)}, v^{(k)}\right\rangle=\left\langle w^{(k)}, r^{(k)}\right\rangle,\left\langle C v^{(k)}, C v^{(k)}\right\rangle=\left\langle A w^{(k)}, w^{(k)}\right\rangle
\end{gathered}
$$