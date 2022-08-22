# lecture 3
## 1.1 泊松方程的狄利克雷问题的差分逼近
考虑域 $G=\left\{0<x_{1}<l_{1}, 0<x_{2}<l_{2}\right\}$ 中泊松方程的狄利克雷问题(带有边 $l_{1}$ 和 $l_{2}$ 的矩形)：
$$
\left\{\begin{array}{l}
\Delta u(x)=-f(x), x=\left(x_{1}, x_{2}\right) \in G \\
u(x)=\mu(x), x \in \partial G
\end{array}\right. \tag{1.1}
$$
这里，和以前一样，$\Delta u=\frac{\partial^{2} u}{\partial x_{1}^{2}}+\frac{\partial^{2} u}{\partial x_{2}^{2}}$ 可以用来表示拉普拉斯算子。
### замечание 
问题 (1.1) 在 $\bar{G}=G \cup \partial G$ 中连续且对于 $f(x)=0$ 非定值的解（拉普拉斯方程的狄利克雷问题）在边界 $\partial G$ 上达到其最大模值。这种说法通常被称为**最大原则(принципом максимума)**。

让我们在 $\bar{G}$ 中引入==均匀差分网格 (равномерную разностную сетку)== $\Omega_{h}=\omega_{h} \cup \gamma_{h}$ ：
$$
\begin{aligned}
&x_{i j}=\left(x_{1, i}, x_{2, j}\right): x_{1, i}=i h_{1}, x_{2, j}=j h_{2} ; h_{1} N_{1}=l_{1}, h_{2} N_{2}=l_{2} \\
&\omega_{h}=\left\{x_{i j} ; i=1,2, \ldots, N_{1}-1: j=1,2, \ldots, N_{2}-1\right\} \\
&\gamma_{h}=\left\{x_{i 0}, x_{i N_{2}}, x_{0 j}, x_{N_{1} j}: i=1,2, \ldots, N_{1}-1 ; j=1,2, \ldots, N_{2}-1\right\} .
\end{aligned}
$$
这里 **$\omega_{h}-$是在内部点的集合，$\gamma_{h}-$是网格的边界节点集合。**
和以前一样，我们将使用以下符号表示：
$$
\begin{aligned}
&y_{\bar{x}_{1} x_{1}, i j}=\frac{y_{i-1 j}-2 y_{i j}+y_{i+1 j}}{h_{1}^{2}} \\
&y_{\bar{x}_{2} x_{2}, i j}=\frac{y_{i j-1}-2 y_{i j}+y_{i j+1}}{h_{2}^{2}}
\end{aligned}
$$
**注：这里是用泰勒公式$f(x)=\sum_{k=0}^{n} \frac{f^{k}\left(x_{0}\right)\left(x-x_{0}\right)}{\underline{k !}}$递推得到的，取的是前两项。**

其中 $y_{i j}=y\left(x_{i j}\right)$ 是在 $\Omega_{h}$ 上定义的网格函数，并将问题 $(1.1)$ 与差分方案进行比较：
$$
\left\{\begin{array}{l}
\Delta_{h} y_{i j}=-f\left(x_{i j}\right), x_{i j} \in \omega_{h} \\
y_{i j}=\mu\left(x_{i j}\right), x_{i j} \in \gamma_{h}
\end{array}\right.\tag{1.2}
$$

这里和以前一样，$\Delta_{h} y_{i j}=\left(y_{\bar{x}_{1} x_{1}}+y_{\bar{x}_{2} x_{ 2 }}\right)_{i j}$ 是五点差拉普拉斯算子。

我们将方程 $\Delta_{h} y_{i j}=-f\left(x_{i j}\right)$ 写为
$$
\left(\frac{2}{h_{1}^{2}}+\frac{2}{h_{2}^{2}}\right) y_{i j}=\frac{y_{i-1 j}+y_{i+1 j}}{h_{1}^{2}}+\frac{y_{i j-1}+y_{i j+1}}{h_{2}^{2} }+f_{i j}, x_{i j} \in \omega_{h}
$$
让我们介绍一下符号：
$x=x_{i j}-$模板中心节点；
$\mathrm{Ш}(x)=\left\{x, x_{i \pm 1 j}, x_{i j \pm 1}\right\}——$方程模板；
$\mathrm{Ш'}(x)=\mathrm{Ш}(x) /\{x\}——$节点的邻域；
$A(x)=\frac{2}{h_{1}^{2}}+\frac{2}{h_{2}^{2}}, B\left(x, x_{i \pm 1 j}\right)=\frac{1}{h_{1}^{2}}, B\left(x, x_{i j \pm 1}\right)=\frac{1}{h_{2}^ {2}}，F(x)=f\left(x_{i j}\right)$。
在这种表示法中，方程可以写成以下形式：
$$
A(x) y(x)=\sum_{\xi \in Ш^{\prime}(x)} B(x, \xi) y(\xi)+F(x), x \in \omega_ {H}
$$
边界节点处的方程可以类似地写成：
$$
A(x) y(x)=F(x), x \in \gamma_{h}
$$
其中$\mathrm{Ш}^{\prime}(x)=0, A(x)=1, F(x)=\mu(x)$。
#### Замечание 
满足系数为正的条件：
$$
A(x)>0, B(x, \xi)>0, D(x)=A(x)-\sum_{\xi \in \mathrm{Ш}^{\prime}(x)} B( x, \xi) \geq 0, x \in \Omega_{h}
$$
在这种形式（以下称为规范形式）中，可以编写来自相当广泛类别的差分形式，因此建议在不考虑特定类型的系数的情况下进行进一步研究。

### 1.1.1 最大值原则

#### 定义
差分网格 $\Omega_{h}$ 是 $n$ 维欧几里得空间中的非空有限点集。
**别忘了上面的表达方式：$\Omega_{h}=\omega_{h} \cup \gamma_{h}$**

#### 定义
网格节点 $x \in \Omega_{h}$ 的模板 $Ш_{h}(x)$ 是包含 $x$ 的 $\Omega_{h}$ 的任何子集。一个节点 $x$ 的邻域是一个集合 $Ш'_h(x)=Ш_h(x) /\{x\}$。

#### 定义
让函数 $A(x), B(x, \xi), F(x)$ 为所有 $x, \xi \in \Omega_{h}$ 定义。规范表示法的差分形式是关于定义在 $\Omega_{h}$ 上的未知网格函数 $y(x)$ 的线性代数方程组，
$$
A(x) y(x)=\sum_{\xi \in Ш_{h}^{\prime}(x)} B(x, \xi) y(\xi)+F(x), x \in \Omega_{h} \tag{1.3}
$$
如果每个节点 $x \in \Omega_{h}$ 只有一个模板且只有一个方程。

#### 定义
如果 $Ш_{h}(x) \neq 0$，则节点 $x \in \Omega_{h}$ 称为内部节点。否则，该节点称为边界节点。
注意：这里的定义意味着：**认为边界节点没有任何邻节点。**
####定义
一个网格 $\Omega_{h}$ 被称为**连通的(связной)**，如果
$$
\begin{gathered}
\forall x^{\prime}, x^{\prime \prime} \in \Omega_{h}: Ш_{h}^{\prime}\left(x^{\prime}\right) \neq 0, \exists x_{i} \in \Omega_{h}, i=1,2, \ldots, m: \\
x_{1} \in Ш_{h}^{\prime}\left(x^{\prime}\right), x_{2} \in Ш_{h}^{\prime}\left(x_{1}\right), \ldots, x_{m} \in Ш_{h}^{\prime}\left(x_{m-1}\right), x^{\prime \prime} \in Ш_{h}^{\prime}\left(x_{m}\right)
\end{gathered}
$$
==（套娃邻域）==

#### Замечание
连通性意味着可以根据给定的模板从任意内部网格节点走到任何其他网格节点。如果内部节点集为空，则网格是不连通的形式，方案 $(1.3)$ 分解为独立方程 $A(x) y(x)=$ $F(x), x \in \Omega_ {h}$。

定义线性算子 $L$ 形式为：
$$
L y(x)=A(x) y(x)-\sum_{\xi \in \mathrm{Ш}_{h}^{\prime}(x)} B(x, \xi) y(\xi), x \in \Omega_{h}
$$
这里我们假设有
$$
D(x)=A(x)-\sum_{\xi \in \mathrm{Ш}_{h}^{\prime}(x)} B(x, \xi)
$$
那上面的式子可以写成形式：
$$
L y(x)=D(x) y(x)+\sum_{\xi \in \mathrm{Ш}_{h}^{\prime}(x)} B(x, \xi)(y( x)-y(\xi)),
$$
差分形式 **(разностную схему)** 可以被写成
$$
L y(x)=F(x), x \in \Omega_{h} 。
$$
#### 定义 
节点 $x \in \Omega_{h}$ 系数为正，若满足以下条件：
$$
A(x)>0, B(x, \xi)>0 \forall \xi \in Ш_{h}^{\prime}(x), D(x) \geq 0 \tag{1.4}
$$
此外，我们将假设 $\Omega_{h}=\omega_{h} \cup \gamma_{h}$，其中 $\omega_{h} \neq 0-$ 是内部网格节点的集合，$\gamma_ {h}$ 是边界节点集，其也可能为空集。
#### 引理 1.1.1 (Принцип максимума)
设函数 $y(x)$ 在连通网格 $\Omega_{h}$ 上被定义并且不是常数，并且所有 $x \in \omega_{h}$ 都满足$(1.4)$系数为正的条件。那么如果对于任何 $x \in \omega_{h}$，有 $Ly(x) \leq 0 (Ly(x) \geq 0)$，那么 $y(x)$ 不能在 $\Omega_{h}$ 上的所有值中取 $\omega_{h}$ 上的 **最大正数(最小负数)** 值。
### 1.1.2 最大值原则的推论(Следствия принципа максимума)
在下文中，我们假设网格 $\Omega_{h}$ 是连通的并且条件
$$
\exists x_{0} \in \Omega_{h}: D\left(x_{0}\right)>0 \tag{1.5}
$$
#### 定理 1.1.2 (Монотонность оператора L)
让条件 $(1.5)$ 和条件 $(1.4)$ 对所有 $x \in \Omega_{h}$ 成立。那么如果 $L y(x) \leq 0$ $(L y(x) \geq 0)$ 对于任何 $x \in \Omega_{h}$成立，则 $y(x) \leq 0$ $(y(x) \geq 0)  $ 对于任何 $x \in \Omega_{h}$。

证明。 
1.在 $\Omega_{h}$ 上令 $y(x) \neq$ const 。假设$\exists x \in \Omega_{h}: y(x)>0$，则
$$\exists x^{\prime} \in \Omega_{h}: y\left(x^{\prime}\right)=\max _{x \in \Omega_{h}} y(x)>0 .
$$

如果 $x^{\prime}$ 是在内部的，则这与最大原则相矛盾。如果这个节点是在边界上，那么
$$
L y\left(x^{\prime}\right)=A\left(x^{\prime}\right) y\left(x^{\prime}\right) \leq 0
$$

其中 $A\left(x^{\prime}\right)>0$，因此 $y\left(x^{\prime}\right) \leq 0$，这与不等式 $y\left(x^ { \prime}\right)>0$。

2.在 $\Omega_{h}$ 上设 $y(x)=$ const。
那么

$$
\begin{gathered}
L y\left(x_{0}\right)=D\left(x_{0}\right) y\left(x_{0}\right)+\sum_{\xi \in \mathrm{W}_{h}^{\prime}\left(x_{0}\right)} B\left(x_{0}, \xi\right)\left(y\left(x_{0}\right)-y(\xi)\right)= \\
=D\left(x_{0}\right) y\left(x_{0}\right) \leq 0,
\end{gathered}
$$
**(我个人其实更喜欢张颖钦的证明，这里也贴上了)**
![s23151205122022.png](img/s23151205122022.png)
并假设 $D\left(x_{0}\right)>0, y\left(x_{0}\right) \leq 0$。也就是说，在 $\Omega_{h}$ 上 $y(x) \equiv y\left(x_{0}\right) \leq 0$。

#### 定义
满足网格 $\Omega_{h}$ 的所有节点的系数 (1.4) 为正的条件的差分方案 (1.3) 称为单调。否则，该电路称为非单调的。
#### 定理 1.1.4 (Теорема сравнения)
让条件 (1.5) 和条件 (1.4) 对所有 $x \in \Omega_{h}$ 成立。那么如果 $|F(x)| \leq \bar{F}(x)$ 对于任何 $x \in \Omega_{h}$, mo $|y(x)| \leq \bar{y}(x)$ 对于任何 $x \in \Omega_{h}$，其中
$$
\begin{aligned}
&y(x)-\text { решение задачи } L y(x)=F(x), x \in \Omega_{h} \\
&\bar{y}(x)-\text { решение задачи } L \bar{y}(x)=\bar{F}(x), x \in \Omega_{h}
\end{aligned}
$$
#### 证明
考虑辅助函数
$$
v(x)=\bar{y}(x)+y(x), w(x)=\bar{y}(x)-y(x) \\
$$

$$
\begin{aligned}
\left\{\begin{array} { l } 
{ L v ( x ) = \overline { F } ( x ) + F ( x ) \geq 0 , } \\
{ L w ( x ) = \overline { F } ( x ) - F ( x ) \geq 0 , }
\end{array} \quad \forall x \in \Omega _ { h } \Rightarrow \left\{\begin{array}{l}
v(x) \geq 0 \\
w(x) \geq 0
\end{array}\right.\right.
\end{aligned}
$$
后一种系统等价于不等式 $-\bar{y}(x) \leq y(x) \leq \bar{y}(x)$。

令网格 $\Omega_{h}$ 的边界节点集非空，即$\gamma_{h} \neq 0$。那么差分格式 (2.3) $L y(x)=F(x), x \in \Omega_{h}$ 可以写成第一边值问题的形式
$$
\left\{\begin{array}{l}
L y(x)=F(x), x \in \omega_{h} \\
y(x)=\mu(x), x \in \gamma_{h}
\end{array}\right.
$$
其中 $\mu(x)=F(x) / A(x), x \in \gamma_{h}\left(A(x)>0 \forall x \in \Omega_{h}\right)$。
在条件 (1.4) $\forall x \in \Omega_{h}$ 下，自动满足第一个边值问题的条件 (2.5)，因为$D(x)=1>0$, $ \forall x \in \gamma_{h}$。

#### Следствие. (Существование и единственность решения краевой задачи)
让所有 $x \in \omega_{h}$ 满足条件 $(1.4)$。则边值问题有唯一解。

#### Следствие. (Теорема сравнения для краевой задачи).
让所有 $x \in \omega_{h}$ 满足条件 $(1.4)$。那么如果 $|F(x)| \leq \bar{F}(x)$ 对于任何 $x \in \omega_{h},|\mu(x)| \leq \bar{\mu}(x)$ 对于任何 $x \in \omega_{h}$，然后 $|y(x)| \leq \bar{y}(x)$ 对于任何 $x \in \Omega_{h}$，其中
$$
\begin{aligned}
&y(x)-\text { решение задачи } L y(x)=F(x), x \in \omega_{h} ; y(x)=\mu(x), x \in \gamma_{h} \\
&\bar{y}(x)-\text { решение задачи } L \bar{y}(x)=\bar{F}(x), x \in \omega_{h} ; \bar{y}(x)=\bar{\mu}(x), x \in \gamma_{h}
\end{aligned}
$$
#### Cледствие (Устойчивость краевой задачи по граничным условиям)
让所有 $x \in \omega_{h}$ 满足条件 $(1.4)$。那么对于问题的解
$$
L y(x)=0, x \in \omega_{h} ; y(x)=\mu(x), x \in \gamma_{h}
$$
满足估计值  $\max _{x \in \omega_{h}}|y(x)| \leq \max _{x \in \gamma_{h}}|\mu(x)|$。
==最后一个Cледствие直接来自最大原则。==