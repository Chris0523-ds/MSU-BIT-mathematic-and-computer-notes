# Лекция 9
## 1.Теорема вейштрасса
### Определение
在下文中，我们将需要泛函级数的正态收敛的概念，它概括了一致收敛的概念。级数 $\sum_{n=1}^{\infty} u_{n}(z)$ 被称为正常收敛于 $\mathrm{G}$（到函数 $f)$ 如果这个级数一致地收敛 $ (to f)$ 在每个紧集 $\mathrm{K} \subset \mathrm{G}$ 上。
### Теорема (维尔斯特拉斯第一引理)。
令级数 $\sum_{n=1}^{\infty} u_{n}(z)$, 其中 $u_{n}(z) \in \mathcal{A}(G), n=1,2 , \ldots$ 在域 $G$ 中正常收敛到函数 $f$。那么：
- 级数和 $f \in \mathcal{A}(\mathrm{G})$ 
- 级数 $\sum_{n=1}^{\infty} u_{n}(z)$ 逐项任意次可微，即
$$
f^{(k)}(z)=\sum_{n=1}^{\infty} u_{n}^{(k)}(z) \quad \forall k \in \mathbb{N}, \quad z \in G
$$
- 所有级数（8.1）在域 G 中**标准收敛(сходиться нормально)**。
在下面的内容中不需要定理的第三个断言。因此，我们只证明前两个断言。
### Доказательство（断言1）
让我们证明 $f$ 的级数和在每个点 $z_{0} \in \mathrm{G} $ 的某个邻域是解析的，这意味着它在整个域 $\mathrm{G}$ 中是解析的。
我们固定一个任意点 $z_0$ $\in \mathrm{G}$。令 $\overline{\mathrm{K}}-$ 为以$z_{0}$ 为圆心的闭圆，它与 $\mathrm{G}$ 的边界一起属于 $\mathrm{G}$。(在解析函数的无限微分定理证明中讨论了这种圆存在的原因。) 假设，级数 $\sum_{n=1}^{\infty} u_{n}(z )$ 在圆 $ \overline{\mathrm{K}}$ 内一致收敛。根据一致收敛级数的连续性定理，它的和 $f$ 在 $\overline{\mathrm{K}}$ 上连续。
令 $L$ 是位于 $\overline{\mathrm{K}}$ 内的任意轮廓（即不接触边界圆）。根据一致收敛级数的相同积分定理，可以逐项积分：
$$
\oint_{L} f(z) d z=\sum_{n=1}^{\infty} \oint_{L} u_{n}(z) d z
$$
在简单连通域（圆 $\bar{K}$ 的内部）中，解析函数 $u_{n}(z)$ 的等高线积分消失；因此，
$$
\oint_{L} f(z) d z=0
$$
因此，在圆 $\overline{\mathrm{K}}$ 中连续的函数 $f$ 在该圆内具有 C 属性。根据 Maurer 定理，$f$ 实际上在 $\bar{K}$ 内部是解析的，这证明了 Weierstrass 定理的第一个断言。
### Доказательство（断言2）
### Теорема (维尔斯特拉斯第二引理)。
让函数 $u_{n}(z), n=1,2, \ldots$ 在由轮廓 $\Gamma$（简单或复合）界定的域 $\mathbf{G}$ 中是解析的。如果这些函数在边界轮廓 $\Gamma$ 上保持连续性并且级数 $\sum_{n=1}^{\infty} u_{n}(z)$ 一致收敛于 $Γ$，那么它一致地收敛于封闭域 $\overline {\mathbf{G}}=\mathbf{G} \cup \Gamma$。
在某些情况下，第二个 Weierstrass 定理简化了对第一个定理条件的验证。 其理由将在域图像定理的证明之后给出。
## 2.степенные ряды
函数级数的具体类中最重要的是幂级数类
$$
\sum_{n=0}^{\infty} c_{n}\left(z-z_{0}\right)^{n} \tag{8.3}
$$
级数 (8.3) 的收敛域由 Cauchy-Hadamard 定理的复杂版本描述，其证明与实定理的证明本质上没有区别。 因此我们将限制它的表述。
令我们有
$$
R=\frac{1}{\overline{\lim }_{n \rightarrow \infty} \sqrt[n]{\left|c_{n}\right|}}
$$
### теорема (коши-адамар)。
如果 $R=0$，则级数 $(8.3)$ 至少在点 $z_0$ 收敛。 如果 $R>0$，那么级数 $(8.3)$ 对于 $\left|z-z_{0}\right|<R$ 绝对收敛并且对于 $\left|z-z_{0}\right|>R$ 发散。
### Определение
数 $R$ 称为收敛半径，圆 $K_{R}:\left|z-z_{0}\right|<R-$ 称为级数 $(8.3)$ 的收敛圆。 数 $R$ 的公式称为 Cauchy-Hadamard 公式。
在下文中，我们将仅考虑 $R>0$ 的幂级数。 满足该条件的幂级数在其收敛圆 $\mathrm{K}_{R}$ 中确定函数 $f(z)-$ 的和
$$
f(z)=\sum_{n=0}^{\infty} c_{n}\left(z-z_{0}\right)^{n} \tag{8.4}
$$
我们的任务是设置函数 $f$ 的性质。 为此，我们证明以下引理。
### лемма
级数 $(8.3)$ 在圆 $\mathrm{K}_{R}$ 中正常收敛。
### Доказательство
$$
\mathbf{K} \subset \overline{\mathbf{K}}_{r} \subset \mathbf{K}_{R}
$$
如果 $R=\infty$，这很明显。令$R$ 为有限数。不相交的闭集 $\mathrm{K}$ 和 $\gamma_{R}:\left|z-z_{0}\right|=R$ 彼此之间的距离为 $\delta$。那么，作为想要的圆$\overline{\mathbf{K}}_{r}$，我们可以取一个半径为$r=R-\delta$的圆。
根据 Cauchy-Hadamard 定理，级数 (8.3) 绝对收敛于圆 $\mathrm{K}_{R}$ 的内点 $z_{0}+r$，即非负级数收敛
$$
\sum_{n=0}^{\infty}\left|c_{n}\right| r^{n}
$$
这个级数可以作为盘 $\overline{\mathbf{K}}_{r}$ 中考虑的级数 $(8.3)$ 的 Weierstrass 大数，更重要的是，在紧集 K 上。因此，级数 $(8.3)$ 一致地收敛于任何这样的紧集，这证明了引理。

已证明的引理允许我们将第一个 Weierstrass 定理应用于等式$(8.4)$。 结果，我们得到以下结果：
- 级数 $(8.3)$ 的和 $f(z)$ 在其收敛圆 $K_{R}$ 内是解析的。
- 等式 $(8.4)$ 可以逐项进行多次微分，这给出
$$
f^{(k)}(z)=\sum_{n=k}^{\infty} c_{n} n(n-1) \ldots(n-k+1)\left(z-z_{0 }\right)^{n-k} \tag{8.5}
$$
将 Cauchy-Hadamard 公式应用于 $(8.5)$ 表明所有微分级数与原始级数 $(8.3)$ 具有相同的收敛半径。
### замечание（о единственности）。
收敛幂级数的系数由其和 $f(z)$ 唯一确定。
实际上，在 $(8.4)$ 和 $(8.5)$ 中设置 $z=z_{0}$，我们得到
$$
c_{0}=f\left(z_{0}\right), \quad c_{k}=\frac{f^{(k)}\left(z_{0}\right)}{k !}, k=1,2, \ldots \tag{8.6}
$$
### Определение
对于某个解析函数 $f(z)$，其系数由公式 $(8.6)$ 表示的幂级数称为该函数的泰勒级数。
### пример
该系列的所有系数$c_{n}$
$$
\sum_{n=0}^{\infty}\left(z-z_{0}\right)^{n} \tag{8.7}
$$
等于 1 ，所以它的收敛半径也等于 1。该系列的和 $f(z)$ 定义为 $\left|z-z_{0}\right|<1$ 并且等于
$$
f(z)=\lim _{n \rightarrow \infty} S_{n}(z)=\lim _{n \rightarrow \infty} \frac{1-\left(z-z_{0}\right) ^{n}}{1-\left(z-z_{0}\right)}=\frac{1}{1-\left(z-z_{0}\right)} 。
$$
我们将以非标准方式使用这个众所周知的公式，即用几何级数 $(8.7)$ 替换右侧的分数。
结果表明，具有正收敛半径的幂级数 $\left(z-z_{0}\right)$ 在其收敛圆内定义了一个解析函数 - 它的和。
考虑相反的问题：在圆 $\left|z-z_{0}\right|<r$ 中的解析函数是否可以在这个圆中表示为幂级数 $\left(z- z_{0}\right)$ ?
泰勒定理对这个问题给出了肯定的回答。
### теорема(тейлор)
令 $f \in \mathcal{A}(\mathrm{G})$ 和 $z_{0} \in G$ 是与 $G$ 的边界 $Γ$ 距离 $r$ 的点。那么在圆 $\mathrm{K}_{r}:\left|z-z_{0}\right|<r$ 中，函数 $f$ 可以用 $z-z_{0 }$的幂级数来表示，且这个表述是唯一的。
### Доказательство
表示的唯一性来自前面 **замечание(о единственности)** 。让我们证明这种表示的存在。

我们固定圆 $K_{r}$ 的任意点 $z$ 并构造一个辅助圆 $\gamma_{\rho}:\left|\zeta-z_{0}\right|=\rho$ 使得 $ \gamma_{\rho} \subset K_{r}$ 和 $z \in$ int $\gamma_{\rho}$（参见幻灯片“泰勒定理”）。让我们用圆 $\gamma_{\rho}$ 上的柯西积分来表示 $f(z)$ 的值：
$$
f(z)=\frac{1}{2 \pi i} \oint_{\gamma_{\rho}} \frac{f(\zeta) d \zeta}{\zeta-z}
$$
由于 $\frac{\left|z-z_{0}\right|}{\left|\zeta-z_{0}\right|}<1$ 对于任何点 $\zeta \in \gamma_{\rho} $，则被积函数 $\frac{1}{\zeta-z}$ 可以替换为无限几何级数：
$$
\begin{gathered}
\frac{1}{\zeta-z}=\frac{1}{\zeta-z_{0}-\left(z-z_{0}\right)}=\frac{1}{\zeta-z_{0}} \cdot \frac{1}{1-\frac{z-z_{0}}{\zeta-z_{0}}}= \\
\frac{1}{\zeta-z_{0}} \cdot \sum_{n=0}^{\infty} \frac{\left(z-z_{0}\right)^{n}}{\left(\zeta-z_{0}\right)^{n}}=\sum_{n=0}^{\infty} \frac{\left(z-z_{0}\right)^{n}}{\left(\zeta-z_{0}\right)^{n+1}} .
\end{gathered}
$$
将这些关系的极值部分乘以 $f(\zeta)$，我们有
$$
\frac{f(\zeta) d \zeta}{\zeta-z}=\sum_{n=0}^{\infty} f(\zeta) \frac{\left(z-z_{0}\right )^{n}}{\left(\zeta-z_{0}\right)^{n+1} \tag{8.8}}
$$
这个等式右边的级数均匀地收敛在圆 $\gamma_{\rho}$ 上。例如，这可以从它被一个收敛的数值级数大化的事实中看出
$$
\max _{\zeta \in \gamma_{\rho}}|f(\zeta)| \sum_{n=0}^{\infty} \frac{\left|z-z_{0}\right|^{n}}{\rho^{n+1}}
$$
因此，等式 (8.8) 在圆 $\gamma_{\rho}$ 上的逐项积分是合法的：
$$
\oint_{\gamma_{\rho}} \frac{f(\zeta) d \zeta}{\zeta-z}=\sum_{n=0}^{\infty} \oint_{\gamma_{\rho}} \frac{f(\zeta) d \zeta}{\left(\zeta-z_{0}\right)^{n+1}}\left(z-z_{0}\right)^{n}
$$
两边除以$2 \pi i$，然后左边的积分变成柯西积分，得到$f(z)$。 假设
$$
c_{n}=\frac{1}{2 \pi i} \oint_{\gamma_{\rho}} \frac{f(\zeta) d \zeta}{\left(\zeta-z_{0}\right)^{n+1}}, \quad n=0,1,2, \ldots \tag{8.9}
$$
我们得到
$$
f(z)=\sum_{n=0}^{\infty} c_{n}\left(z-z_{0}\right)^{n} \tag{8.10}
$$
系数 $c_{n}$ 不依赖于 $z$。 事实上，积分 (8.9) 只不过是一个 Cauchy 型积分，其值为
$$
\frac{f^{(n)}\left(z_{0}\right)}{n !}
$$
因此，对于圆 $\mathrm{K}_{r}$ 的任何点 $z$，等式 (8.10) 给出了 $f$ 通过 $z-z_{0}$ 的幂的表示。 这证明了泰勒定理。
### Пример
将函数 $f(z)=\frac{1}{1+z^{2}}$ 展开为幂级数：
* (A) $z$；
* (B) $z-1$

函数 $f(z)=\frac{1}{1+z^{2}}$ 在整个 $\mathbb{C}$ 平面上解析，除了点 $z=\pm i$。这两个点构成了其分析域的边界。


* 点 $z=0$ 到函数 $f(z)$ 的奇异点的距离为 1 。 根据泰勒定理，$f(z)$ 可以在圆 $|z|<1$ 中展开为 $z$ 的幂。 实际上，对于这样的 $z$，函数 $\frac{1}{1+z^{2}}$ 是无限级数的总和
$$
\sum_{n=0}^{\infty}(-1)^{n} z^{2 n}
$$
* 点 $z=1$ 到函数 $f(z)$ 的奇异点的距离等于 $\sqrt{2}$。 根据泰勒定理，$f(z)$ 可以在 $|z-1|<\sqrt{2}$ 中展开为 $z-1$ 的幂。 为了找到这种展开，我们将 $f(z)$ 表示为简单分数的线性组合。 我们有
$$
\frac{1}{1+z^{2}}=\frac{1}{2 i}\left(\frac{1}{z-i}-\frac{1}{z+i}\right) \text{. }
$$
通过将函数 $\frac{1}{z-i}$ 转化为乘积
$$
\frac{1}{z-i}=\frac{1}{1-i} \cdot \frac{1}{1+\frac{z-1}{1-i}}
$$
我们可以用无限级数替换 $|z-1|<|1-i|=\sqrt{2}$ 处的正确分数
$$
\sum_{n=0}^{\infty}(-1)^{n} \frac{(z-1)^{n}}{(1-i)^{n}} 。
$$
所以，
$$
\frac{1}{z-i}=\sum_{n=0}^{\infty}(-1)^{n} \frac{(z-1)^{n}}{(1-i)^{ n+1}}, \quad|z-1|<\sqrt{2} 。
$$
同理，对于 $|z-1|<|1+i|=\sqrt{2}$ 我们得到分解
$$
\frac{1}{z+i}=\sum_{n=0}^{\infty}(-1)^{n} \frac{(z-1)^{n}}{(1+i) ^{n+1}} 。
$$
将这些级数而不是简单的分数代入函数 $f(z)$ 的表示中，我们最终得到
$$
\frac{1}{1+z^{2}}=\sum_{n=0}^{\infty}(-1)^{n} \frac{1}{2 i}\left[\frac{ 1}{(1-i)^{n+1}}-\frac{1}{(1+i)^{n+1}}\right](z-1)^{n} \tag{8.11}
$$

使用常量 $1+i$ 和 $1-i$ 的极坐标形式：
$$
1+i=\sqrt{2} e^{i \frac{\pi}{4}}, \quad 1-i=\sqrt{2} e^{-i \frac{\pi}{4}}
$$
经过简单的算术，可以证明级数 $(8.11)$ 的系数实际上是实数：
$$
\frac{1}{1+z^{2}}=\sum_{n=0}^{\infty}(-1)^{n} \frac{\sin \left[(n+1) \frac{\pi}{4}\right]}{2^{\frac{n+1}{2}}}(z-1)^{n} \tag{8.12}
$$
Cauchy-Hadamard 公式给出级数 (8.12) 的收敛半径值等于 $\sqrt{2}$。