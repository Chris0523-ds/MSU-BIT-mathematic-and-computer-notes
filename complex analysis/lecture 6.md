## 1.复变量函数的积分
令 L 是一条可修正的曲线，其参数方程为
$$
z=\lambda(t)=x(t)+i y(t), \quad \alpha \leqslant t \leqslant \beta
$$
### 直线可求长性的必要条件
令 $\lambda(t)-$ 为分段平滑曲线，即 $x(t)$ 和 $y(t)-$ 是分段平滑函数。 那么$\lambda(t)$ 是**可化直(спрямляема)** 的。
为了明确起见，我们在$L$ 上选择一个对应于参数增加的方向。 那么点$z_{0}=\lambda(\alpha)$ 称为曲线$L$ 的起点，点 $\lambda(\beta)$ 称为曲线终点。 具有相反方向的相同曲线将用$-L$ 表示。
令
$$
T：t_{0}=\alpha<t_{1}<t_{2}<\cdots<t_{n}=\beta
$$
是段 $[\alpha, \beta]$ 的任意划分 **(разбиение)**，
$$
\delta=\max _{1 \leqslant k \leqslant n}\left\{t_{k}-t_{k-1}\right\}
$$
是这个划分的直径。 划分 $T$ 对应于曲线 $L$ 的划分 $T_{\ell}$ 成弧
$$
T_{\ell}: \ell_{1}, \ell_{2}, \ldots, \ell_{n} \text {. }
$$
弧 $\ell_{k}$ 开始于点 $z_{k-1}=\lambda\left(t_{k-1}\right)=x_{k-1}+i y_{k-1}$,并在点 $z_{k}=\lambda\left(t_{k}\right)$ 处结束。

让函数 $w=f(z)$ 定义在曲线 $L$ 的点上。在每个段$t_{k-1} \leqslant t \leqslant t_{k}$中选择一个任意值$\tau_{k}$，我们得到弧$\ell_{k}$上的一个点$\zeta_{k}=\lambda\left(\tau_{k}\right)$。让我们设置 $\Delta z_{k}=z_{k}-z_{k-1}$ 并组成复积分和
$$
S\left(t_{k}, \tau_{k}\right)=\sum_{k=1}^{n} f\left(\zeta_{k}\right) \Delta z_{k} \tag{4.2}
$$
对应于划分 $T_{\ell}$。
### Определение
如果 $\delta \rightarrow 0$ 有一个和极限 $S\left(t_{k}, \tau_{k}\right)$，独立于分区的顺序和该分区弧上点 $\zeta_{1}、\zeta_{2}、\ldots、\zeta_{n}$ 的选择，则该极限由符号表示
$$
\int_{L} f(z) d z
$$
并且被称为函数 $f$ 沿曲线 $L$（在所选方向上）的积分 **（интегралом от функции $f$ вдоль кривой $L$）**。在这种情况下，$f$ 被认为是关于 $L$ 的可积的。
### Теорема
令 $L$ 是一条没有奇异点的分段平滑曲线。如果函数 $w=f(z)=u(x, y)+i v(x, y)$ 被定义并且沿 $L$ 连续，那么 $f$ 关于 $L$ 是可积的并且
$$
\int_{L} f(z) d z=\int_{L} u(x, y) d x-v(x, y) d y+i \int_{L} v(x, y) d x+u(x , y) d y
\tag{4.3}
$$
### Доказательство
将因子 
$$
\Delta z_{k}=\Delta x_{k}+i \Delta y_{k}, f\left(\zeta_{k}\right)=  u\left(\xi_{k}, \eta_{k}\right)+i v\left(\xi_{k}, \eta_{k}\right)=u_{k}+i v_{k}
$$ 代入积分和 $(4.2)$，将其重写为
$$
S\left(t_{k}, \tau_{k}\right)=\sum_{k=1}^{n}\left(u_{k} \Delta x_{k}-v_{k} \Delta y_ {k}\right)+i \sum_{k=1}^{n}\left(v_{k} \Delta x_{k}+u_{k} \Delta y_{k}\right) \tag{4.4}
$$
这个数的实部和虚部是第二类曲线积分 $\int_{L} u d x-v d y$ 和 $\int_{L} v d x+u d y$ 的积分和。在曲线 $L$ 和函数 $f$ 上的定理中施加的条件下，两个积分都存在。通过在关系式 (4.4) 中传递到 $\delta\rightarrow 0$ 处的极限来获得等式 (4.3)。
### 复积分的性质
让我们对复积分的性质做一个简短的总结。 其中第一个是实曲线积分性质的直接结果。
* $\int_{-L} f(z) d z=-\int_{L} f(z) d z$
* $\int_{L}\left(c_{1} f_{1}(z)+c_{2} f_{2}(z)\right)=c_{1} \int_{L} f_{ 1}(z) d z+c_{2} \int_{L} f_{2}(z) d z$;
* 设曲线 $L=L_{1}+L_{2}+\cdots+L_{q}$ 由弧 $L_{j}$ 组成，使得 $L_{j}$ 的终点与$L_ {j+1}(j=1,2, \ldots, q-1)$ 的开头。 然后
$$
\int_{L_{1}+L_{2}+\cdots+L_{q}} f(z) d z=\sum_{j=1}^{q} \int_{L_{j}} f(z) dz
$$
在接下来的内容中，我们经常需要估计积分的值。因此，我们写出以下оценка
*
$$
\left|\int_{L} f(z) d z\right| \leqslant \int_{L}|f(z)| d\sigma \tag{4.5}
$$
其中右侧是第一类实曲线积分；
证明:
在估计复积分和
$$
\left|S\left(t_{k}, \tau_{k}\right)\right| \leqslant \sum_{k=1}^{n}\left|f\left(\zeta_{k}\right)\right|\left|\Delta z_{k}\right|
$$
我们将段 $\left|\Delta z_{k}\right|$ 的长度替换为第 $k$ 个部分弧 $\sigma_{k}$ 的长度。结果，我们获得了估计$(4.5)$中曲线积分的积分和。传递到 $\delta\rightarrow 0$ 的极限给出了这个估计本身。
我们设置$M=\sup_{z \in L}|f(z)|$。在大多数情况下，比 $(4.5)$ 更简单的估计对我们来说就足够了；
*
$$
\left|\int_{L} f(z) d z\right| \leqslant M \cdot \text {длина L} \tag{4.6}
$$
与实曲线积分的情况一样，复积分的计算是通过对积分曲线进行参数化并传递到关于参数的线性积分来执行的。 令 $z=\lambda(t), \alpha \leqslant t \leqslant \beta,-$ 为曲线 L 的参数方程。像往常一样，假设函数 $\lambda$ 是分段平滑的。 然后
$$
\int_{L} f(z) d z=\int_{\alpha}^{\beta} f[\lambda(t)] \lambda^{\prime}(t) d t \tag{4.7}
$$
### пример
让我们通过公式 $(4.7)$ 计算一个简单但重要的积分:
$$
I=\int_{|z-a|=\rho} \frac{d z}{z-a}
$$
引入积分圆的参数化
$$
z=\lambda(t)=a+\rho e^{it}, \quad 0 \leqslant t \leqslant 2 \pi
$$
并利用微分 $d z=i \rho e^{it} d t$ 之间的关系，我们得到
$$
I=\int_{0}^{2 \pi} \frac{i \rho e^{i t}}{\rho e^{i t}}d t=i \int_{0}^{2 \pi}d t= 2 \pi i
$$
请注意，此结果不取决于积分圆的半径 $\rho$，也不取决于其中心 $a$ 的位置。
## 柯西积分引理
### Определение
一条曲线 $L: z=\lambda(t), \alpha \leqslant t \leqslant \beta$，如果它的起始点和终止点重合，则称其为闭合曲线，即$\lambda(\alpha)=\lambda(\beta)$。
### Определение
如果点 $z_{0} \in L$ 是这样的
$$
z_{0}=\lambda\left(t_{1}\right)=\lambda\left(t_{2}\right), \quad\left\{t_{1}, t_{2}\right\} \neq\{\alpha, \beta\}
$$
则 $z_{0}$ 称为曲线 L 的**多重点(кратной точкой)**。
### Определение
没有多重点的曲线称为简单曲线或若尔当曲线。
### Определение
闭合的若尔当曲线称为**等高线(контур)**。函数 $f(z)$ 在等高线 $Γ$ 上的积分通常称为路径积分 **(контурным интегралом)** ，用符号表示
$$
\oint_{\Gamma} f(z) 。
$$
### теорема (Жордана)
任何闭合的若尔当曲线 $Г$ 将平面 $\mathbb{C}$ 分成两个不同的区域，这是一个共同的边界。在这种情况下，其中一个区域是有界的，它被称为 G 的内部 **(внутренностью)** ，并表示为 $\operatorname{im} \Gamma$（来自内部）。第二个区域是非有界的，称为 $Г$的外部 **(внешностью)** ，记为 $\operatorname{ext} \Gamma$（代表exterior）。
### Определение
绕过等高线 Г 的正方向是区域  $\operatorname{int}Г$ 保持在沿移动的观察者的左侧。在这种情况下，等高线积分的符号是
$$
\oint_{\Gamma+} f(z)
$$
如果沿 G 的运动发生在相反的方向，那么他们写作
$$
\oint_{\Gamma^{-}} f(z) 。
$$
### Определение
如果对于属于 $G$ 的任何等高线 $\gamma$ 满足 $\gamma$ 的内部也属于 $G$，则称域 $G$ 是**单连通**的。如果其中的至少一个等高线不满足此条件，则域 $G$ 称为**多连通的**。
### теорема (грина)
设域$D$ 以等高线 $C$ 为界，函数$P(x, y)$ 和$Q(x, y)$ 在闭域$\bar{D}$ 中是连续的并且在$D$上有连续偏导数$\frac{\partial Q}{\partial x}$ 和 $\frac{\partial P}{\partial y}$。那么格林公式是有效的，可写作
$$
\int_{C^{+}} P d x+Q d y=\iint_{\bar{D}}\left(\frac{\partial Q}{\partial x}-\frac{\partial P}{\partial y}\right) d x d y
$$
前提是右边的二重积分存在（至少作为反常二重积分）。
**我们由此得到积分柯西引理，该定理被认为是 TFKT 课程的核心：**
### теорема（积分柯西定理）。
令$f(z)=u(x, y)+i v(x, y) \in \mathcal{A}(\mathrm{G})$。 如果 $C$ 是属于域 $\operatorname{G}$ 及其内部的任何等高线(контур)，则
$$
\oint_{C} f(z) d z=0 \tag{4.8}
$$
### доказательство
根据等式$(4.3)$，
$$
\oint_{C} f(z) d z=\oint_{C} u d x-v d y+i \oint_{C} v d x+u d y
$$
格林公式（主定理）可以应用于右侧的两个积分，假设 $D$ 是轮廓 $C$ 的内部：
$$
\begin{gathered}
\oint_{C} u d x-v d y=\iint_{\bar{D}}\left(-v_{x}^{\prime}-u_{y}^{\prime}\right) d x d y \\
\oint_{C} v d x+u d y=\iint_{\bar{D}}\left(u_{x}^{\prime}-v_{y}^{\prime}\right) d x d y 。
\end{gathered}
$$
由于даламбера-эйлера条件，双积分的被积函数完全等于 0。 这意味着左侧的复积分为零。

### Cледствие
令 G 为单连通域，$f(z) \in A(G)$。那么等式 $(4.8)$ 对任何轮廓 $C \subset G$ 都成立。

让我们举一个例子来说明推论中单连通需求的作用。 圆环$D$：$1<|z|<3$是一个双连通集，函数$f(z)=\frac{1}{z}$在其中解析。 $f(z)$ 在环内的圆 $|z|=2$ 上的积分是 $2 \pi i$（参见本章示例 1）。 同时，根据我们对积分定理的表述，$\frac{1}{z}$ 的积分在属于 $D$ 的每个轮廓及其内部都等于0。

现在我们的任务是在两个方向上推广柯西定理。
* 1.让域 $G$ 以轮廓 $C$ 为界。解析函数在区域边界上的等高线积分是否为零？下面的陈述回答了这个问题。
### теорема (обобщённая теорема коши).
令 $G$ 为由等高线 $C$ 界定的区域。如果函数 $f(z) \in \mathcal{A}(\mathrm{G})$ 在域边界上保持连续性，则
$$
\oint_{C} f(z) d z=0
$$
* 我们推广柯西定理的另一个方向是将其扩展到某些类别的非单连通域。我们先介绍一下复合轮廓的概念。
### Определение
**复合等高线(Составным контуром)** 是普通（简单）等高线的并集 $C=C_{0} \cup C_{1} \cup \cdots \cup C_{n}$ 使得：
- 轮廓 $C_{0}$，称为外部，包含所有其他（内部）轮廓 $C_{1}、\ldots、C_{n}$；
- 每个轮廓 $C_{1}, \ldots, C_{n}$ 位于任何其他内部轮廓的外部。
### Определение
一个多重连通域 $G$，其边界是复合轮廓 $C=C_{0} \cup C_{1} \cup \cdots \cup C_{n}$ 将被称为 **$(n+1)$-связный**。绕过复合边界轮廓的正方向使得沿边界移动的观察者看到 $G$ 在他的左边。这对应于以通常的逆时针方向遍历外轮廓并顺时针遍历内轮廓。

### Tеорема（о составном контуре）。
令 $G$ 为由复合轮廓 $C=C_{0} \cup C_{1} \cup \cdots \cup C_{n}$ 包围的区域。 如果函数 $f(z) \in A(G)$ 在域边界上保持连续性，则
$$
\oint_{C^{+}} f(z) d z=\oint_{C_{0}^{+}} f(z) d z+\oint_{C_{1}^{-}} f(z) d z+\cdots+\oint_{C_{n}^{-}} f(z) d z=0 \tag{4.9}
$$
### замечание
等式 $(4.9)$经常被如下式子代替：
$$
\oint_{C_{0}^{+}} f(z) d z=\oint_{C_{1}^{+}} f(z) d z+\cdots+\oint_{C_{n}^{+}} f(z)dz \tag{4.10}
$$
### пример
设 $Г$ 是包含点 $z_{0}=0$ 内的任意（简单）轮廓。函数 $f(z)=\frac{1}{z}$ 对 $Г$ 的积分是多少？
为了回答这个问题，我们构造了一个小半径 $\rho$ 的圆 $\gamma:|z|=\rho$，使得 $\gamma$ 属于轮廓 $G$ 的内部。我们应用函数 $\frac {1}{z}$ 公式 $(4.10)$ 中的复合等高线定理。 我们有
$$
\oint_{\Gamma^{+}} \frac{d z}{z}=\oint_{\gamma^{+}} \frac{d z}{z}
$$
我们都知道正确的积分：它等于$2 \pi i$。 左积分的值是相同的。
