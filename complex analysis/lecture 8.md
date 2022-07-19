# Лекция 8
## Интегралы,зависящие от параметра
### Теорема
设函数 $f(x, y)$ 在矩形 $\Pi=\{a \leqslant x \leqslant b, c \leqslant y \leqslant d\}$ 上是连续的并且有一个连续导数 $f_{y} ^{\prime}(x, y)$。 然后积分
$$
I(y)=\int_{a}^{b} f(x, y) d x
$$
是 $y$ 在 $[c, d]$ 上的可微函数，它的导数可以使用лейбница规则计算
$$
I^{\prime}(y)=\int_{a}^{b} f_{y}^{\prime}(x, y) d x
$$
### Теорема
令函数 $f\left(x, y_{1}, \ldots, y_{m}\right)$ 在平行六面体 $\Pi_{m}=\left\{a \leqslant x \leqslant b  c_{i } \leqslant y_{i} \leqslant d_{i}(i=1,2, \ldots, m)\right\}$上是连续的，并具有连续导数 $f_{y_{i}}^{\prime}\left(x, y_{1}, \ldots, y_{m}\right), i=1,2, \ldots, m$。 然后积分
$$
I\left(y_{1}, \ldots, y_{m}\right)=\int_{a}^{b} f\left(x, y_{1}, \ldots, y_{m}\right) d x
$$
对于变量 $y_{1}, \ldots, y_{m}$ 在域 $c_{i} \leqslant y_{i} \leqslant d_{i}(i=1,2, \ldots, m)$中有连续的偏导数，它们可以用莱布尼茨法则去计算。
$$
I_{y_{i}}^{\prime}\left(y_{1}, \ldots, y_{m}\right)=\int_{a}^{b} f_{y_{i}}^{\prime}\left(x, y_{1}, \ldots, y_{m}\right) d x, i=1,2, \ldots, m .
$$
### Теорема
让函数 $P\left(x, y, z_{1}, \ldots, z_{m}\right)$ 和 $Q\left(x, y, z_{1}, \ldots, z_{m} \right)$ 在集合 $\left\{(x, y) \in L, \quad c_{i}<z_{i}<d_{i}(i=1,2, \ldots, m )\right \}$ 并对其有连续导数
$$
P_{z_{i}}^{\prime}\left(x, y, z_{1}, \ldots, z_{m}\right), Q_{z_{i}}^{\prime}\left(x, y, z_{1}, \ldots, z_{m}\right), i=1,2, \ldots, m .
$$
那么曲线积分
$$
I\left(z_{1}, \ldots, z_{m}\right)=\int_{L} P d x+Q d y
$$
在区域 $c_{i}<z_{i}<d_{i}(i=1,2, \ldots , m)$ ，可以使用莱布尼茨规则计算
$$
\begin{aligned}
I_{z_{i}}^{\prime}\left(z_{1}, \ldots, z_{m}\right)=\int_{L} P_{z_{i}}^{\prime}\left (x, y, z_{1}, \ldots, z_{m}\right) d x+Q_{z_{i}}^{\prime}\left(x, y, z_{1}, \ldots, z_{m}\right) d y \\
i=1,2, \ldots, m
\end{aligned}
$$
在下文中，我们将考虑形式的复积分
$$
F(z)=\int_{L} \phi(z, \zeta) d \zeta \tag{7.1}
$$
在以下假设下：
(1) $L-$ 是对于变量 $\zeta=\xi+i \eta$在域上的曲线, 并且 $z$ 在变量 $z=x+i y$ 的平面上的某个区域 $\mathrm{G}$ 上发生变化。
(2) 对于 $\zeta\in L$ 的任何固定值，函数 $\phi(z, \zeta)-$ 在域 $G$ 中是解析的。
(3) 函数$\phi(z, \zeta)$ 和$\phi_{z}^{\prime}(z, \zeta)$ 在变量 $z$ 和 $\zeta$ 的集合中是连续的。
### Теорема (об интеграле с параметром).
若可以满足假设 1-3。那么： 1) 积分 $F(z) \in A(G) ； 2)$ 导数 $F^{\prime}(z)$ 可以使用莱布尼茨规则计算：
$$
F^{\prime}(z)=\int_{L} \phi_{z}^{\prime}(z, \zeta) d \zeta \tag{7.2}
$$
### Доказательство
让我们以代数形式表示 $\phi(z, \zeta)$ 和 $F(z)$：
$$
\begin{gathered}
\phi(z, \zeta)=u(x, y, \xi, \eta)+i v(x, y, \xi, \eta) \\
F(z)=U(x, y)+i V(x, y)= \\
=\int_{L} u(x, y, \xi, \eta) d \xi-v(x, y, \xi, \eta) d \eta+i \int_{L} v(x, y, \xi, \eta) d \xi+u(x, y, \xi, \eta) d \eta .
\end{gathered}
$$
假设 1-3 意味着函数 和 $v$ 在所有四个（实）参数的总和中是连续的，并且在 $x$ 和 $y$ 中具有偏导数，它们在所有四个参数中也是连续的。
由此我们推断：函数$U(x, y)$ 和$V(x, y)$ 是连续的，并且在域G 中具有连续的偏导数，可以使用莱布尼茨规则计算：
$$
\begin{gathered}
U_{x}^{\prime}(x, y)=\int_{L} u_{x}^{\prime} d \xi-v_{x}^{\prime} d \eta, \quad U_{ y}^{\prime}(x, y)=\int_{L} u_{y}^{\prime} d \xi-v_{y}^{\prime} d \eta, \\
V_{x}^{\prime}(x, y)=\int_{L} v_{x}^{\prime} d \xi+u_{x}^{\prime} d \eta=\int_{L }-u_{y}^{\prime} d \xi+v_{y}^{\prime} d \eta=-U_{y}^{\prime}(x, y), \\
V_{y}^{\prime}(x, y)=\int_{L} v_{y}^{\prime} d \xi+u_{y}^{\prime} d \eta=\int_{L } u_{x}^{\prime} d \xi-v_{x}^{\prime} d \eta=U_{x}^{\prime}(x, y) 。
\end{gathered}
$$
因此，函数 $U(x, y)$ 和 $V(x, y)$ 的连续偏导数满足域 $\mathrm{G}$ 中的 Cauchy-Riemann 条件。根据定理 2.4，这意味着 $F(z) \in \mathcal{A}(\mathrm{G})$。
求导数 $F^{\prime}(z)$ ：
$$
F^{\prime}(z)=U_{x}^{\prime}+i V_{x}=\int_{L} u_{x}^{\prime} d \xi-v_{x}^{ \prime} d \eta+i \int_{L} v_{x}^{\prime} d \xi+u_{x}^{\prime} d \eta 。
$$
与此同时满足
$$
\phi_{z}^{\prime}(z, \zeta)=u_{x}^{\prime}+i v_{x}^{\prime}
$$
由此可知
$$
\int_{L} \phi_{z}^{\prime}(z, \zeta) d \zeta=\int_{L} u_{x}^{\prime} d \xi-v_{x}^{\prime} d \eta+i \int_{L} v_{x}^{\prime} d \xi+u_{x}^{\prime} d \eta 。
$$
这证明了公式$（7.2）$
## бесконечная дифференцируемость аналитической функции
从已证明的定理中，我们提取出最重要的推论。域 $G$ 中的函数分析，由在该域中具有连续导数的适度要求定义，实际上具有 $G$ 中所有阶的导数。
### Теорема(о бесконечной дифференцируемости аналитической функции)
设 $f \in \mathcal{A}(\mathrm{G})$。 然后在每个点 $z \in \mathrm{G}$ 函数 $f$ 具有所有阶的导数。 如果等高线$L$和它的内部都属于$G$，$z$是这个轮廓的一个内部点，那么导数$f^{(n)}(z)$可以通过公式计算：
$$
f^{(n)}(z)=\frac{n !}{2 \pi i} \oint_{L} \frac{f(\zeta)}{(\zeta-z)^{n+1} }d\zeta \tag{7.3}
$$
### доказательство 暂略
## следствие теоремы о бесконечной дифференцируемости
### 推论 $1 .$
从公式 (7.3) 可以明显看出，导数 $f^{\prime}(z)$ 又具有域 $G$ 中所有阶的导数。 这尤其意味着解析函数的导数本身就是解析函数。
### 推论 $2 .$ (теорема марера).
令 $f \in \mathcal{C}(\mathrm{G})$ 和 $f$ 在 $G$ 中具有 C 属性,则$f \in \mathcal{A}(\mathrm{G} )$。
### Доказательство
该定理的条件与теорема o первообразной的条件一致，根据该定理，$\mathrm{G}$ 包含一个解析函数 $F$，使得
$$
F^{\prime}(z)=f(z) \quad \forall z \in G
$$
根据推论 $1，f(z)$ 本身必须是 G 中的解析函数。
### 推论 $3 .$ 刘维尔定理（теорема лиувиляя）
一个在整个复平面上有界的整函数 $f$ 是一个常数。
### Доказательство
设 $z_o$ 为复平面的任意点，$\gamma_{R}$ 为半径为 $R$ 的圆，圆心为 $z_{0}$。我们将 $f^{\prime}\left(z_{0}\right)$ 的值写为该圆上的柯西型积分：
$$
f^{\prime}\left(z_{0}\right)=\frac{1}{2 \pi i} \oint_{\gamma_{R}} \frac{f(\zeta)}{\left(\zeta-z_{0}\right)^{2}} d \zeta
$$
因为$f(z)$ 是一个整函数，所以这个等式中的半径$R$ 可以取任意大。令$M>0$，界定$f(z)$在整个平面上的值：
$$
|f(z)| \leqslant M \quad \forall z \in G 。
$$
从等式 (7.8) 我们推导出 $\left|f^{\prime}\left(z_{0}\right)\right|$ 的以下估计：
$$
\left|f^{\prime}\left(z_{0}\right)\right| \leqslant \frac{1}{2 \pi} \max _{\zeta \in \gamma_{R}} \frac{|f(\zeta)|}{\left|\zeta-z_{0}\right|^{2}} \text { длина } \gamma_{R} \leqslant \frac{M}{R^{2}} R=\frac{M}{R} .
$$
在 $R \rightarrow \infty$ 我们有
$$
f^{\prime}\left(z_{0}\right)=0 。
$$
由于 $z_{0}-$ 是平面中的任意点，因此函数 $f$ 实际上是一个常数。