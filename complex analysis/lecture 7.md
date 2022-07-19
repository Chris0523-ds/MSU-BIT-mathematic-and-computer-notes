## первообразная и неопределенный интеграл
### Определение
设 $f \in \mathcal{C}(\mathrm{G})$。若对所有 $ z \in G$ 满足 $\Phi^{\prime}(z)=f(z)$ ，则$\Phi \in \mathcal{A}(\mathrm{G})$ 在这个域中被称为 $f$ 的原函数。 给定区域中函数 $f$ 的所有原函数的集合称为它在该区域中的不定积分。

假设域 $G$ 中函数 $f$ 的某个原函数$F$是已知的，当然，通过给它加上常数，我们会得到新的原函数。 让我们证明，与在实数域的情况一样，可以通过这种方式获得函数 $f$ 的整个不定积分。
### Интегрирование функций комплексного переменного
让与 $F$ 一起，还有一个函数 $f$ 的原函数 $\Phi$。
令有
$$
\omega(z)=\Phi(z)-F(z), \forall z \in G
$$
从这里
$$
\omega^{\prime}(z)=\Phi^{\prime}(z)-F^{\prime}(z)=f(z)-f(z)=0 \quad \forall z \in G
$$
这意味着在表示 $\omega(z)=u(x, y)+iv(x, y)$ 中，函数 $u$ 和 $v$ 的所有偏导数在域 $G$ 中恒等于零。 因此，$v$ 和 $v$ 都是实常数，$\omega(z)=C-$  是复数常数。 因此，可得到结论：
$$
\Phi(z)=F(z)+C \tag{4.11}
$$
为了建立原函数存在的条件，我们回顾了一些关于曲线积分不相关于积分路径选择的实际分析结果。
### Теорема (независимость криволинейного интеграла от пути интегрирования).
设 $G$ 是变量 $x$ 和 $y$ 的笛卡尔平面上的域，其中函数 $P(x, y)$ 和 $Q(x, y)$ 是连续的。以下三个条件是等价的：
- 对于任何闭合曲线 $L \subset G$
$$
\oint_{L} P d x+Q d y=0
$$
- 对于任何点 $A, B \in G$ 的积分值 
$$
\int_{L} P d x+Q d y
$$
不依赖于连接点 $A$ 和 $B$ 的（分段平滑）曲线 $L \subset \mathrm{G}$。
- 在 $G$ 中有一个函数 $U(x, y)$ 连续可微，使得
$$
d U=P d x+Q d y
$$
由此可知
$$
\int_{A B} P d x+Q d y=U(B)-U(A)
$$
这个函数 $U$ 被称为**势能(потенциалом)** ，并被定义为一个常数。 特别是，可以选择$U(A)=0$ 的势,使得积分 $(6.2)$ 变成点 $B$ 的函数。 在一般情况下，等式$(6.2)$是牛顿-莱布尼茨公式的（曲线）版本。
### Теорема
现在让 $\mathrm{G}$ 是平面 $\mathbb{C}$ 上的域公式,且$f \in \mathcal{C}(G)$。考虑到复积分和实积分之间的联系，可以写出公式：
$$
\int_{L} f(z) d z=\int_{L} u(x, y) d x-v(x, y) d y+i \int_{L} v(x, y) d x+u(x , y) d y
$$
我们得出结论，以下三个陈述是等价的：
- 对于任意等高线$L\subset G$ 满足 $C$ 属性 **(C-свойство)**
$$
\oint_{L} f(z) d z=0
$$
- 积分
$$
F(z)=\int_{z_{0}}^{z} f(\zeta) d \zeta \tag{6.4}
$$
其中点 $z_{0}\in G$ 是固定的，并且 $G$ 中的 z 变化不取决于连接 $z_{0}$ 和 $z$ 的路径的选择，前提是该路径位于该区域中 $\mathrm{G}$。
- 有函数 $U(x, y)$ 和 $V(x, y)$（势）在 $G$ 中连续可微（作为变量 $x$ 和 $y$ 平面上的域），使得：
$$
d U=u d x-v d y, \quad d V=v d x+u d y \tag{6.5}
$$
特别是可以选择满足条件的势：
$$
U\left(x_{0}, y_{0}\right)=V\left(x_{0}, y_{0}\right)=0 \tag{6.6}
$$
### теорема（o первообразной）。
令 $f \in \mathcal{C}(\mathrm{G})$，并令 $f$ 在 $\mathrm{G}$ 中具有 $C$ 属性 **(C-свойство)**。后者正确地将积分 $(6.4)$ 定义为仅与上极限 $z$ 相关的函数。 那么：
(A) $F \in \mathcal{A}(\mathrm{G})$;
(B) $F^{\prime}(z)=f(z)$  $\forall z \in G$。
### доказательство
我们令有 $\zeta=\xi+i \eta$。 对于 $F(z)$ 积分的实部和虚部，我们在考虑条件 $(6.6)$ 的情况下选择势能 $U(x, y)$ 和 $V(x, y)$，即
$$
\int_{z_{0}}^{z} u d \xi-v d \eta=U(x, y), \quad \int_{z_{0}}^{z} v d \xi+u d \eta= V(x, y)
$$
从公式 $(6.5)$ 我们推导出
$$
U_{x}^{\prime}=u, \quad U_{y}^{\prime}=-v, \quad V_{x}^{\prime}=v, \quad V_{y}^{\prime}=u。
$$
因此，函数 $U(x, y)$ 和 $V(x, y)$ 满足 Cauchy-Riemann 条件。 此外，这些函数是连续可微的。 因此 $F(z)$ 在 $G$ 中有一个连续导数，这证明了定理的第一个断言。
我们计算这个导数得到：
$$
F^{\prime}(z)=U_{x}^{\prime}+i V_{x}^{\prime}=u+i v=f(z) \quad \forall z \in G 。
$$
回到描述函数 $f(z)$ 的不定积分的公式 $(6.1)$，我们可以将其中的 $F(z)$ 替换为刚刚找到的反导数：
$$
\Phi(z)=\int_{z_{0}}^{z} f(\zeta) d \zeta+C \tag{6.7}
$$
让我们找出这个公式中常数 $C$ 的含义。 在等式两边设置 $z=z_{0}$ $(6.7)$，我们有
$$
C=\Phi\left(z_{0}\right)
$$
现在 $(6.7)$ 可以重写为
$$
\int_{z_{0}}^{z} f(\zeta) d \zeta=\Phi(z)-\Phi\left(z_{0}\right)
$$
这不过是复杂版本的牛顿-莱布尼茨公式。

### Интегральная Формула Коши
设 $f \in \mathcal{A}(\mathrm{G})$, 等高线 $L \subset \mathrm{G}$, 子域 $\mathrm{D} \subset \mathrm{G}$ 对于等高线 $L$ 有界。那么柯西公式对任何点 $z_{0} \in D$ 都有效。
$$
f\left(z_{0}\right)=\frac{1}{2 \pi i} \oint_{L} \frac{f(z) d z}{z-z_{0}} \tag{C}
$$
让我们同意，如果绕过轮廓的方向没有由索引 + 或 - 明确指示，那么绕过是在正方向上进行的。
### Определение
这个公式右边的积分称为柯西积分。公式（C）表达了一个解析函数最重要的性质：知道 $f$ 在轮廓 $L$ 上所取的值，可以唯一地确定该函数在 $L$ 为边界的区域的任何点处的值。
### 柯西形式证明
让我们画圆 $\gamma_{\rho}:\left|z-z_{0}\right|=\rho$ 使其位于 $L$ 内。令 $E$ 为边界为复合轮廓 $L \cup \gamma_{\rho}$ 的区域。 从复合等高线定理我们推导出
$$
\frac{1}{2 \pi i} \oint_{L} \frac{f(z) d z}{z-z_{0}}=\frac{1}{2 \pi i} \oint_{\gamma_ {\rho}} \frac{f(z) d z}{z-z_{0}} \tag{6.8}
$$
让 $\rho$ 趋于零，并注意，根据 (6.8)，右边的积分值不应该依赖于 $\rho .$ 另一方面，我们将证明对于 $ \rho \rightarrow 0$ 这个积分有极限 $f\left(z_{0}\right)$。 从这里可以得出，(6.8) 中的两个积分都等于 $f\left(z_{0}\right)$，这就是柯西公式。
让我们估计一下误差：
$$
\frac{1}{2 \pi i} \oint_{\gamma_{\rho}} \frac{f(z) d z}{z-z_{0}}-f\left(z_{0}\right)
$$
使用众所周知的等式
$$
\oint_{\gamma_{\rho}} \frac{d z}{z-z_{0}}=2 \pi i
$$
重写它的形式
$$
\frac{1}{2 \pi i} \oint_{\gamma_{\rho}} \frac{d z}{z-z_{0}}=1
$$
并将两边乘以 $f\left(z_{0}\right)$ ：
$$
f\left(z_{0}\right)=\frac{1}{2 \pi i} \oint_{\gamma_{\rho}} \frac{f\left(z_{0}\right) d z}{z-z_{0}} .
$$
我们有
$$
\begin{gathered}
\left|\frac{1}{2 \pi i} \oint_{\gamma_{\rho}} \frac{f(z) d z}{z-z_{0}}-f\left(z_{0}\right)\right|=\left|\frac{1}{2 \pi i} \oint_{\gamma_{\rho}} \frac{f(z)-f\left(z_{0}\right)}{z-z_{0}} d z\right| \leqslant \\
\frac{1}{2 \pi} \max _{z \in \gamma_{\rho}} \frac{\left|f(z)-f\left(z_{0}\right)\right|}{\left|z-z_{0}\right|} \text { длина } \gamma_{\rho}=\frac{1}{2 \pi} \max _{z \in \gamma_{\rho}} \frac{\left|f(z)-f\left(z_{0}\right)\right|}{\rho} 2 \pi \rho= \\
=\max _{z \in \gamma_{\rho}}\left|f(z)-f\left(z_{0}\right)\right| .
\end{gathered}
$$
函数 $f$ 在 D 中是解析函数，在点 $z_{0}$;处是连续的； 因此，右侧的最大值趋向于零，因为 $\rho \rightarrow 0$。 这证明了柯西公式。
### замечание
如果（简单或复合）轮廓 $L$ 是域 $G$ 的边界，则柯西公式仍然有效，$f(z) \in A(G)$ 和 $f(z)$ 在 $\partial G=L$ 上是连续的。
### замечание (формула среднего значения)
令 $G$ 为以 $z_{0}$ 为圆心的半径为 $R$ 的圆，满足前文关于函数 $f$ 和边界圆 $L$ 的条件。对$L$取参数化$z=z_{0}+R e^{i \phi}$，由柯西公式得到
$$
f\left(z_{0}\right)=\frac{1}{2 \pi i} \int_{0}^{2 \pi} \frac{f\left(z_{0}+R e^{ i \phi}\right)}{R e^{i \phi}} i R e^{i \phi} d \phi=\frac{1}{2 \pi} \int_{0}^{2 \pi} f\left(z_{0}+R e^{i \phi}\right) d \phi
$$
公式的名称是由于分段上的积分值，与该段的长度有关，对于有限的一组数字，有一个算术平均值的连续模拟。