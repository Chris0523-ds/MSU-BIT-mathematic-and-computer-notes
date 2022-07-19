# лекция 2
## 1.导数参数的几何意义
让我们考虑下一个问题。令函数 $w=f(z)$ 在点 $z_{0}$ 处有一个非零导数 $f^{\prime}\left(z_{0}\right)$。数字 $\arg f^{\prime}\left(z_{0}\right)$ 的几何意义是什么？
让我们首先针对特殊函数依赖的情况分析这个问题。令 $L$ 为具有参数方程 $z=\lambda(t)$ 的连续曲线，其中 $t \in \mathbf{E}=[\alpha, \beta] \subset \mathbb{R}$。在什么情况下，函数 $\lambda$ 在 $t_{0} \in E$ 处有导数？
让我们设置 $\lambda(t)=x(t)+i y(t)$ 并组成**差异关系(разностное отношение)**
$$
\frac{\lambda(t)-\lambda\left(t_{0}\right)}{t-t_{0}}=\frac{x(t)-x\left(t_{0}\right) }{t-t_{0}}+i \frac{y(t)-y\left(t_{0}\right)}{t-t_{0}} 。
$$
对于 $t \rightarrow t_{0}, t \in E$，我们得到：
导数 $\lambda^{\prime}\left(t_{0}\right)$ 当且仅当两个实数导数 $x^{\prime}\left(t_{0}\right)$ 都存在且 $ y^{\prime}\left(t_{0}\right)$。其中
$$
\lambda^{\prime}\left(t_{0}\right)=x^{\prime}\left(t_{0}\right)+i y^{\prime}\left(t_{0}\right )
$$
### Определение
==参数 $t_{0}$ 的值和点 $z_{0}=\lambda\left(t_{0}\right)$ 称为**正则的(регулярными)**,如果导数 $\lambda^{\prime}\left(t_{0}\right)$ 存在且不等于 0。==


如果 $t_{0}$ 是参数的常规值，那么对于充分接近 $t_{0}$ 并且不同于 $t_{0}$ 的所有 $t \in E$，曲线 $L$ 上的点 $z=\lambda(t)$ 与 $z_{0}=\lambda\left(t_{0}\right)$ 不同。数字
$$
\frac{\lambda(t)-\lambda\left(t_{0}\right)}{t-t_{0}}=\frac{z-z_{0}}{t-t_{0}}
$$
被视为复平面上的一个向量，位于连接点 $z_{0}$ 和 z 的线上，即在割线上。该割线相对于实轴倾斜的角度为
$$
\operatorname{Arg} \frac{z-z_{0}}{t-t_{0}}
$$
在 $t \rightarrow t_{0}, t \in E$ 的极限下，我们得到
$$
\operatorname{Arg} \lambda^{\prime}\left(t_{0}\right)
$$
因此，如果对于 $t=t_{0}$ 函数 $z=\lambda(t)$ 有一个非零导数 $\lambda^{\prime}\left(t_{0}\right)$，那么割线通过点 $z_{0}$ 和 $z$ 的曲线 $L$ 在 $t \rightarrow t_{0}$ 处有一个极限位置。 该极限位置是曲线 $L$ 在其点 $z_{0}$ 处的切线。 它以 $\operatorname{Arg} \lambda^{\prime}\left(t_{0}\right)$ 的角度向实轴倾斜。

现在让我们回到问题的一般表述，即函数 $w=f(z)$ 的情况。让我们通过点 $z_o$ 绘制一条平滑曲线:
$\gamma: z=\lambda(t), \alpha \leqslant t \leqslant \beta$，所以 $z_{0}=\lambda\left(t_{0}\right)$ 是这个的正则点曲线，即$\lambda^{\prime}\left(t_{0}\right) \neq 0$。在函数$w=f(z)$的作用下，曲线$\gamma$在变量 $w$ 的平面上转化为曲线 $\Gamma: w=f[\lambda(t)] \equiv \mu(t), \alpha \leqslant t \leqslant \beta$,。此外，$w_{0}=f\left(z_{0}\right)-$ 是曲线 $Γ ~$ 的规则点
$$
\mu^{\prime}\left(t_{0}\right)=f^{\prime}\left(z_{0}\right) \lambda^{\prime}\left(t_{0}\right )
$$
根据复数相乘时加参的规则，我们推导出可以选择参数$\lambda^{\prime}\left(t_{0}\right)$和$\mu^{\prime}\left(t_{0}\right )$，使它们的差等于数 $\arg f^{\prime}\left(z_{0}\right)$。考虑到将前两个参数解释为对应曲线与实轴的切线形成的角度，我们得出了关于数字 $\arg f^{\prime}\left(z_{0}\right)$ 的几何意义的问题的答案。
数字 $\arg f^{\prime}\left(z_{0}\right)$ 是任何平滑曲线通过点 $z_{0}$ 时从 $z$ 平面到 $w$ 平面的旋转角度，这种旋转发生在 $f$ 函数的作用下。

下图说明了这个结论的一个重要结果。 假设曲线 $\gamma_{1}$ 和 $\gamma_{2}$ 在点 $z_{0}$ 的夹角等于 $\varphi$。 当移动到 $w$ 平面时，两条曲线都会旋转并占据右图中 $\Gamma_{1}$ 和 $\Gamma_{2}$ 线的位置。
由于它们将旋转相同的角度 $\arg f^{\prime}\left(z_{0}\right)$，因此它们之间将保持相同的角度 $\varphi$。
![s14164504252022.png](img/s14164504252022.png)
## 2.共形映射
反过来，这个推论将我们引向整个课程的第二个最重要的（在解析函数之后）定义，即保形映射的定义。 我们将提供两个版本 —— **Локальная и Глобальная**。
### Определение
**局部一致性(Локальная конформность)**。 通过保持通过给定点的曲线之间的角度的连续函数的映射被称为在该点是共形的。

函数 $f(z)$ 的映射在所有点 $z_{0}$ 处是共形的，其中 $f^{\prime}\left(z_{0}\right) \neq 0$

### Замечание
局部共形不一定在 $f^{\prime}\left(z_{0}\right)=0$ 处被破坏。一个例子是：一个平面上的极坐标函数，由公式 $f(z)=r^{2}(\cos \varphi+i \sin \varphi)$ 和一个点$z_{0}= 0$。
### Определение
**全局一致性（глобальная конформность）**。让函数 $f$ 将域 $\mathbf{G}$ 一对一映射到 $\mathbf{D}$。此外，如果 $f$ 在 $z \in \mathbf{G}$ 的每个点上是共形的，则称 $f$ 将 $\mathbf{G}$ 映射到 $\mathbf{D}$ 共形。

==这里的意思是：共形映射保持了穿过的曲线间的定向角度。==