# лекция 12
## Ряды лорана
### Пример
对于函数 $f(z)=\exp \frac{1}{z}$，点 $z_{0}=0$ 是一个本质奇点。例如，这是因为对于序列 $z_{n}^{\prime}=\frac{1}{n}$ 和 $z_{n}^{\prime \prime}=-\frac {1 }{n}$ 我们有
$$
f\left(z_{n}^{\prime}\right) \rightarrow \infty, \quad f\left(z_{n}^{\prime \prime}\right) \rightarrow 0
$$
即函数 $f$ 在点 0 处没有极限值。
序列 $z_{n}^{\prime}$ 和 $z_{n}^{\prime \prime}$ 可以分别被认为是 $A=\infty$ 和 $A=0$ 的 Cохоцкого 序列。

现在让 $A$ 是一个有限的但不等于0的数。让我们尝试从函数 $f$ 的 $A$ 点构造一个 Sokhotsky A-序列。从方程 $\exp \frac{1}{z}=A$ 我们推导出 $\frac{1}{z}=\operatorname{Ln} A$ 和
$$
z=\frac{1}{\operatorname{Ln} A}=\frac{1}{\ln A+2 k \pi i}, \quad k \in \mathbb{Z}
$$
因此，它是Sochocki A 序列，例如点的序列
$$
z_{n}=\frac{1}{\ln A+2 n \pi i}, \quad n=1,2,3, \ldots
$$
事实上，对于几乎所有的 $A$，我们设法从函数 $f(z)$ 的 A 点构造了 Sokhotsky A 序列，这不是这个例子的特征，而是由遵循定理，我们在没有证明的情况下提出。
### Большая теорема пикара
令 $z_{0}$ 是函数 $f(z)$ 的一个本质奇异点。那么对于任何有限数$A$，除了一个值$A=A_{0}$，存在一个函数$f(z)$的$A$点序列收敛到$z_{0 }$。
在我们的示例中，异常值 $A_{0}$ 是数字 $A=0$。但可能会缺少特殊价值。例如，函数 $f(z)=\sin \frac{1}{z}$ 在其基本奇异点 $z_{0}=0$ 处不存在。