# lecture 5
## 指数函数
我们已经知道这个函数是解析函数甚至整个（即整个复平面中的解析）函数的第一个重要示例。对于 $z=x+iу $ 它的值表示为 $e^{z}$ 或 exp z 并由公式给出
$$
e^{z}=e^{x}(\cos y+i \sin y)
$$
当 $ \operatorname{dom} e^{z}=\mathbb{C}$ 时，指数的值域与 $w$ 的所有变量平面不重合。事实上，从上面的公式中可以明显看出，对于所有的 $z \in \mathbb{C}$，$e^{z} \neq 0$。让我们证明所有 $w \neq 0$ 都属于域 $\operatorname{im} e^z$。从复等式以三角形式写出 $w$ 和所需的原像 $z$
$$
|w|(\cos \arg w+i \sin \arg w)=e^{x}(\cos y+i \sin y)
$$
中，我们得出两个关系
$$
e^{x}=|w|, \quad y \in \operatorname{Arg} w
$$

首先唯一地定义 $x$ ：
$$
x=\ln |w|
$$
因此，任何非零 $w$ 都有一组可数的原像，由公式描述
$$
z=\ln |w|+i \operatorname{Arg} w
$$
这些数字 $z$ 中的每一个都称为 $w$ 的（自然）对数。它们都位于与横坐标$\ln|w|$ 相同的垂直线上，它们之间的距离是$2\pi$ 的整数倍。
从公式
$$
e^{z}=e^{x}(\cos y+i \sin y) 。
$$
可以看出，将数字 $2 \pi$ 添加到参数 $z$ 的虚部不会改变 $e^{z}$ 的值。因此，复指数是周期 $2 \pi i$ 的周期函数。
由于 $\left(e^{z}\right)^{\prime}=e^{z}$ 和 $e^{z}$ 无处消失，因此指数函数在 $\mathbb{C}$ 中的任何点都具有局部共形性（引理 2.5）。同时，由于周期性，如果在其定义的整个域上考虑$e^{z}$，它的运动在全局意义上将不是共形的。让我们证明任何水平条
$$
g: \phi_{0}<y<\phi_{1}
$$
宽度 $h=\phi_{1}-\phi_{0} \leqslant 2 \pi$ 是复数指数的单叶域。实际上，相同数 $w$ 的两个对数不能在这样的带中。
让我们找出在 $e^{z}$ 的作用下，条带 $g$ 会变成什么。我们将 $g$ 视为水平线族的并集
$$
I_{\phi}: z=t+i \phi, \quad-\infty<t<\infty, \quad \phi_{0}<\phi<\phi_{1}。
$$
在指数的作用下，直线 $I_{\phi}$ 变成了一条射线
$$
L_{\phi}: w=e^{t}(\cos \phi+i \sin \phi),
$$
从点 $w=0$ 出现并以角度 $\phi$ 向实轴倾斜。 因此，在平面 $w$ 上的条带 $g$ 的图像是开口 $h$ 的扇形 $G$，顶点在 $w=0$ 点。 该扇区的边界射线由方程给出
$$
\operatorname{Arg} w=\phi_{0}+2 k \pi \text { 和 } \operatorname{Arg} w=\phi_{1}+2 k \pi 。
$$
在带 $g$ 上，指数函数一对一地作用并且在每个点 $z \in g$ 处是共形的。 这意味着图表的有效性
$$
g \underset{\text { 保形 }}{\stackrel{\exp z}{\longrightarrow}} G
$$
现在让我们看看指数如何作用在平行于虚轴的线上。让
$$
I_{c}: z=c+i t, \quad-\infty<t<\infty
$$
这是一个直线。它的图像将是一个圆圈
$$
\gamma_{c}: w=e^{c}(\cos t+i \sin t)
$$
此外，当点 z 描述线 $I_{c}$ 一次，因为 $t$ 从 $-\infty$ 到 $\infty$ 变化时，点 $w$ 描述了无限多的圆 $\gamma_{c}$次正向。 $I_{c}$ 行上长度为 $2\pi$ 的每一段对应于一轮 $\gamma_{c}$。
任务。
证明一条直线，不平行于实轴和虚轴，被指数映射成对数螺旋（极坐标方程$\rho=C e^{k \phi}$给出的曲线，其中$C> 0$ 和 $k-$ 是常量）。
## 三角函数和双曲线函数（тригонометрические и гиперболические функции）
欧拉公式
$$
e^{i z}=\cos z+i \sin z
$$
我们将定义八个这样的函数：正弦和余弦
$$
\begin{aligned}
\cos z=\frac{e^{i z}+e^{-i z}}{2}, & \sin z=\frac{e^{i z}-e^{-i z}}{2 i} \ \ 
\operatorname{ch} z=\frac{e^{z}+e^{-z}}{2}, & \operatorname{sh} z=\frac{e^{z}-e^{-z} }{2} \tag{4.10}
\end{aligned}
$$
和切线和余切线
$$
\operatorname{tg} z=\frac{\sin z}{\cos z}, \quad \operatorname{ctg} z=\frac{\cos z}{\sin z}, \quad  z= \frac{\operatorname{sh} z}{\operatorname{ch} z}, \quad \operatorname{cth} z=\frac{\operatorname{ch} z}{\operatorname{sh} z} \tag{4.11}
$$
函数 $(4.10)$ 是指数的线性组合，是整函数并从它们继承周期性。此外，双曲正弦和余弦具有相同的周期 $2 \pi i$。三角函数是根据 $iz $ 参数的指数定义的，因此正弦和余弦的周期为 $2 \pi$。
显然，对于实参的实数值，复双曲函数与同名实函数重合。对于复杂的三角函数也是如此，我们将检查函数 $\cos z$。令 $z=x \in \mathbb{R}$，则
$$
\cos z=\frac{e^{i x}+e^{-i x}}{2}=\frac{1}{2}(\cos x+i \sin x+\cos x-i \sin x)=\cos x
$$
让我们找出三角正弦和余弦对于位于实轴外的值 $z=x+i y$ 的行为。可以证明
$$
|\cos z|=\sqrt{\operatorname{ch}^{2} y-\sin ^{2} x}, \quad|\sin z|=\sqrt{\operatorname{sh}^{2} y+ \sin ^{2}x}
$$
在这两种情况下，均采用非负平方根。从这里我们推断
$$
\begin{aligned}
&\operatorname{ch} y \geqslant|\cos z| \geqslant \sqrt{\operatorname{ch}^{2} y-1}=|\operatorname{sh} y| \\
&\text { ch } y=\sqrt{\operatorname{sh}^{2} y+1} \geqslant|\sin z| \geqslant|\operatorname{sh} y|
\end{aligned}
$$
这些оценки显示：
(1) 函数 $\cos z$ 和 $\sin z$ 不会在实轴之外的任何地方消失；
(2) 当我们远离实轴时，两个函数的模数都无限增长。

因此，与同名的实函数不同，复函数 $\cos z$ 和 $\sin z$ 在复平面上是没有界的。尽管如此，基本的三角恒等式仍然有效：
$$
\cos ^{2} z+\sin ^{2} z=1, \quad \forall z \in \mathbb{C}
$$
T.K.
$$
\begin{gathered}
\cos ^{2} z+\sin ^{2} z=\left(\frac{e^{i z}+e^{-i z}}{2}\right)^{2}+\left(\frac {e^{i z}-e^{-i z}}{2 i}\right)^{2}= \\
=\frac{e^{2 i z}+2+e^{-2 i z}}{4}-\frac{e^{2 i z}-2+e^{-2 i z}}{4}=\frac{4}{4}=1
\end{gathered}
$$
实际关于三角学的其他事实仍然有效：加法定理、归约公式等。它们中的每一个都可以根据复杂函数的定义轻松验证。然而，我们将在后面讨论的唯一性定理提供了一种通用方法，用于检查将函数的定义从实轴扩展到复平面时，原始函数满足的关系对其复泛化继续成立。
公式（4.10）暗示了关系
$$
\operatorname{ch} z=\cos i z, \quad \operatorname{sh} z=-i \sin i z
$$
他们解释了为什么三角函数和双曲函数的性质如此相似。
至于函数（4.11），无论在哪里定义，它们都是分析函数。 因此，ctg $z$ 仅在 $\sin z$ 消失的点 $z=k \pi$ 处未定义。 这些函数也是周期性的，双曲正切和余切的周期为 $\pi i$，而三角函数的周期为 $\pi$。
用于微分实函数的公式仍然有效。 例如，对于 $\cos z$，我们有
$$
(\cos z)^{\prime}=\left(\frac{e^{i z}+e^{-i z}}{2}\right)^{\prime}=\frac{1}{2} i\left(e^{i z}-e^{-i z}\right)=-\sin z
$$
所有函数 (4.10) 和 (4.11) 都可以由先前研究的函数的组合表示：线性分数函数、Zhukovsky 函数和指数函数。因此，对于$\cos z$，引入一个中间变量$t=e^{iz}$，我们得到
$$
w=\cos z=\frac{1}{2}\left(t+\frac{1}{t}\right)
$$
使用这种情况，可以为这些函数中的每一个找到单叶域。
任务。
令 $g$ 为 $z$ 平面上的一条垂直条带：
$$
g: 0<x<\pi
$$
a G 是变量 $w$ 的平面，沿射线 $(\infty,-1]$ 和 $[1,\infty)$ 沿实轴进行切割。证明图表的有效性
$$
g \underset{\text { 保形 }}{\underset{\cos z}{\longrightarrow}} \mathrm{G} 。
$$
