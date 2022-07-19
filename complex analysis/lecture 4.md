# lecture 4
## 1.线性分数函数的对称性守恒
一对点 $z_{1}$ 和 $z_{2}$ 关于直线 $\ell$ 的对称性可以等价地定义如下：任何通过 $z_{1}$ 和$z_{2}$的直线和圆，必须与 $\ell$ 正交（参见幻灯片“关于直线的对称性（Симметрия относительно прямой）”）。这个定义几乎可以逐字转移到一对点关于圆对称的情况。
### Определение
点 $z_{1}$ 和 $z_{2}$ 相对于圆 $\gamma$ 是对称的，如果通过 $z_{1}$ 和 $z_{2}$ 的任何圆和直线与 $\gamma$ 正交。
让 $\gamma$ 由方程 $|z-a|=R$ 给出。从关于 $\gamma$ 的对称性定义可以推导出 $z_{1}$ 和 $z_{2}$ 必须位于从圆心 $a$ 发出的同一条射线上，并且其中一个点必须在内部，而另一个在 $\gamma$ 之外。设 $Г$ 是通过 $z_{1}$ 和 $z_{2}$ 的任意圆。根据从 $a$ 到 $Γ$ 得出的平面切线和正割定理，从 $a$ 到 $z_{1}$ 和 $z_{2}$ 的距离的乘积必须等于半径 $R$ 的平方。
以上所有内容都可以描述如下：
$$
z_{2}=a+\frac{R^{2}}{z_{1}-a}
$$
如果 $z_{1}$ 在这个等式中趋向于 $a$，那么 $z_{2} \rightarrow \infty$，它解释了以下约定：关于 $\gamma$ 与中心 $a$ 对称的点是无穷远处的点 $\infty$。
### Теорема
==在任意线性分数变换$w=L(z)$的作用下，关于直线或圆 $\gamma$ 对称的点 $z_{1}$ 和 $z_{2}$ , 到关于直线或圆 $\Gamma=L(\gamma)$ 对称的点 $w_{1}$ 和 $w_{2}$。==
### Доказательство
令 $\Delta$ 为通过 $w_{1}$ 和 $w_{2}$ 的直线或圆。这条线 $\delta=L^{-1} \Delta$ 的逆像是通过 $z_{1}$ 和 $z_{2}$ 的直线或圆。由于 $z_{1}$ 和 $z_{2}$ 关于 $\gamma$ 是对称的，因此 $\delta$ 与 $\gamma$ 正交。由于线性分数变换$w=L(z)$ 是共形的，$\Delta$ 与 $Γ$ 正交，这意味着$w_{1}$ 和$w_{2}$ 关于 $Γ$ 是对称的。
### Пример
构造一个线性分数变换 $w=L(z)$，将圆 $|z|<R$ 转换为圆 $|w|<R$ 使得第一个圆的给定点$\alpha$ 到第二个圆的中心$w=0$。
让我们考虑两种可能的情况。
### Пример
情形$1：\alpha=0$。点 $\alpha=0-$ 是所需线性分数变换的不动点。由于圆$\gamma:|z|=R$ 必须进入圆$\Gamma:|w|=R$，那么，根据对称守恒的性质，与零对称的点$\infty$对于两个圆，也必须是固定的。这意味着解是形式为 $w=\mu z$ 的整线性函数。为了使圆的半径不因变换而改变，必须满足条件$|\alpha|=1$。所以，这种情况的答案是：$w=e^{i \psi} z$，其中 $\psi-$ 是区间 $0 \leqslant \psi<2 \pi$ 中的任意数。
情形$2$：$\alpha \neq 0$。点 $\alpha^{*}=R^{2} / \bar{\alpha}$ 通过点 $\alpha$ 相对于圆 $\gamma$ 是对称的。由于点 $\alpha$ 必须到圆 $\Gamma$ 的中心 $w=0$，那么根据对称守恒的性质，点 $\alpha^{*}$ 必须到无限远平面 $w$ 的点。 这确定了一个标量因子所需的线性分数函数。
$$
w=\lambda \frac{z-\alpha}{z-\alpha^{*}}=\lambda \frac{z-\alpha}{z-\frac{R^{2}}{\bar{\alpha}}}=\mu \frac{z-\alpha}{R^{2}-\bar{\alpha} z}
$$
其中满足
$$
\mu=-\lambda \bar{\alpha}
$$

直到使用圆的半径不应因变换而改变的条件。从这个条件我们将获得关于系数 $\mu$ 的信息。令 $z=R e^{i \phi}-$ 为圆 $|z|=R$ 上的任意点。对于这一点的图像$w$，我们有
$$
\begin{aligned}
|w|=|\mu| &\left|\frac{R e^{i \phi}-\alpha}{R^{2}-\bar{\alpha} Re^{i \phi}}\right|=\frac{|\mu|}{R}\left|\frac{R e^{i \phi}-\alpha}{R-\bar{\alpha} e^{i \phi}}\right|=\\
&=\frac{|\mu|}{R}\left|\frac{R-\alpha e^{-i \phi}}{R-\bar{\alpha} e^{i \phi}}\right|=\frac{|\mu|}{R} 。
\end{aligned}
$$
由于结果 $w$ 必须是圆 $|w|=R$ 的一个点，我们要求
$$
\frac{|\mu|}{R}=R
$$
那些。 $|\mu|=R^{2}$。因此，变换的形式 $w=R^{2} e^{i \psi} \frac{z-\alpha}{R^{2}-\bar{\alpha} z} $是问题的解。
请注意，对于模数小于 1 的各种数 $\alpha$ 的函数 $L_{\alpha}(z)=\frac{z-\alpha}{1-\bar{\alpha} z}$ 称为莫比乌斯变换并执行单位圆到自身的保形映射。

## 2.茹科夫斯基(жуковского)函数
$$
w=\lambda(z)=\frac{1}{2}\left(z+\frac{1}{z}\right) \tag{4.1}
$$

$$
\operatorname{dom} \lambda=z \neq 0 .
$$
对于任何给定的 $w$，公式 $(4.1)$ 可以看作是 $z$ 中的二次方程：
$$
z^{2}-2 w z+1=0 \tag{4.2}
$$

这个方程在$\mathbb{C}$中总是可解的。它遵循
$$
\operatorname{im} \lambda=\mathbb{C} 。
$$

在其域 $\lambda(z)$ 中的每一处都有一个连续导数
$$
\lambda^{\prime}(z)=\frac{1}{2}\left(1-\frac{1}{z^{2}}\right) 。
$$

因此 $\lambda(z)$ 在 $z \neq 0$ 中是解析函数。任何地方，除了点$z=\pm 1$，导数都是非零的，并且根据局部共形的充分条件定理，==$\lambda(z)$ 具有局部共形性。== 可以证明（问题）在点 $z=\pm 1$ 处失去了保形属性。至于全局共形性，由于在函数 $\lambda(z)$ 的作用中缺乏一对一的相互作用而受到阻碍：方程 $(4.2)$ 表明，在典型情况下，每个 $w$ 都有两个逆像$z_{1}$ 和 $z_{2 }$ 通过 $z_{1} z_{2}=1$ 关联。
在这方面，我们介绍了几个一般性质的定义。
### Определение
令$w=f(z) \in A(G)$。如果 $f\left(z_{1}\right) \neq f\left(z_{2}\right)$ 对于 $G$ 的任意两个不同点 $z_{1}$ 和 $z_{2}$，那么$f$在这个域中称为**单叶的(однолистной)**，否则称为**多叶的(многолистной)**.。
### Определение
如果任意点 $w \in \operatorname{im} f$ 的原像数有一个典型值，那么更具体的说法是：**双叶的，可数叶的(двулистная, счетнолистная)** 函数。
### Определение
如果 $f(z)$ 在 $G$ 中是**多叶的**，但在其子域 $g$ 中是**单叶的**，则 $g$ 称为 $f$ 的**单叶域(областью однолистности)**

从这些定义的角度来看，茹科夫斯基函数在其定义域中是双叶的。 它的单叶域是单位圆 $|z|<1$， 域 $|z|>1$，以及每个半平面 $\operatorname{Im} z>0$ 和 $\operatorname{Im} z<0$。 让我们在 $\lambda(z)$ 的作用下找到它们的图像。 在这种情况下，在扩展复平面上，我们通过设置来补充茹科夫斯基函数的定义域：
$$
\lambda(0)=\lambda(\infty)=\infty
$$
让我们从单位圆 $k$ 开始，将其视为一个圆族的并集
$$
\gamma_{r}: z=r(\cos t+i \sin t), 0 \leqslant t \leqslant 2 \pi \tag{4.3}
$$
其中 $r$ 在区间 $(0,1)$ 内变化。我们通过将 $\lambda(z)$ 应用于方程 $(4.3)$ 的两个部分来获得圆形图像方程 $\gamma_{r}$：
$$
\Gamma_{r}: w=\frac{1}{2}\left(z+\frac{1}{z}\right)=\frac{1}{2}\left(\frac{1}{r }+r\right) \cos t-i \frac{1}{2}\left(\frac{1}{r}-r\right) \sin t \tag{4.4}
$$
这是具有半轴的椭圆的参数方程
$$
a=\frac{1}{2}\left(\frac{1}{r}+r\right), \quad b=\frac{1}{2}\left(\frac{1}{r} -r\right)
$$
虚数单位前面的减号表示如果点 $z$ 绕正方向的圆$\gamma_{r}$，那么它的图像 $w$ 绕椭圆$\Gamma_{r}$负方向。
椭圆 $\Gamma_{r}$ 的焦距为
$$
c=\sqrt{a^{2}-b^{2}}=1
$$
并且不依赖于 $r$。因此，该族 $(4.4)$ 的所有椭圆在点 1 和 -1 处都有共同的焦点。这样的椭圆被称为**共焦的**。

如果 $r \rightarrow 0$，则 $a, b \rightarrow \infty$，即$G_r$ 无限扩展。对于 $r \rightarrow 1$，我们有 $a \rightarrow 1, b \rightarrow 0$，即$G_r$，扁平化，倾向于在极限处与实轴的段 $[-1,1]$ 重合。 （这个段其实就是单位圆 $|z|=1$ 的图像。)

对 $r \in(0,1)$ 取所有椭圆 $\Gamma_{r}$ 的并集，我们得到域 $G$，这是变量$w=u+i v$ 的平面，其中的区间$-1 \leqslant u \leqslant 1, v=0$ 被删除。由于$\lambda(z)$ 在圆 $k$ 中是单等的，并且在这个圆的每个点上都是局部共形的，所以一般结论如下：
$$
|z|<1 \underset{\text {conformally}}{\overset{\lambda(z)}{\longrightarrow}} G
$$

用 $k_{1}$ 表示单位圆的上半部分，即区域 $|z|<1，\operatorname{Im} z>0$，而 $k_{2}$ 表示该单位圆的下半部分。
区域 $|z|>1, \operatorname{Im} z<0$ 将由 $K_{1}$ 表示，区域 $|z|>1, \operatorname{Im} z>0-$ 将由$K_{2}$表示。回想一下，点 $w$ 的两个原像 $z_{1}$ 和 $z_{2}$ 通过关系 $z_{1} z_{2}=1$ 相关联。因此可以得出
$$
\lambda\left(k_{1}\right)=\lambda\left(K_{1}\right), \quad \lambda\left(k_{2}\right)=\lambda\left(K_{2} \right) \tag{4.5}
$$

如果在上面的分析中，我们考虑的是它们的上半部分（不包括其中的点 $-r$ 和 $r$）而不是完整的圆 $\gamma_{r}$，那么它们将被映射到下半部分椭圆 $\Gamma_{r}$ 的一半。这些半椭圆的并集是半平面 $\operatorname{Im}w<0$。
结果，我们得到 $k_{1} \frac{\lambda(z)}{\text {conformally }} \operatorname{Im} w<0$
类似地 $k_{2} \underset{\text {conformally }}{\stackrel{\lambda(z)}{\longrightarrow}} \operatorname{Im} w>0$。 由于 $(4.5)$，我们有 $K_{1} \underset{\text { conformally }}{\stackrel{\lambda(z)}{\longrightarrow}} \operatorname{Im} w<0$ 和 $K_{2} \underset{\text { conformally }}{\stackrel{\lambda(z)}{\longrightarrow}} \operatorname{Im} w>0$。

现在让我们使用表示找到上半平面 $P_{+}=\operatorname{Im} z>0$ 的图像
$$
P_{+}=k_{1} \cup K_{2} \cup \gamma_{1}，
$$
其中$\gamma_{1}$是上单位半圆$|z|=1，\operatorname{Im} z>0$，茹科夫斯基函数映射到实轴区间$-1<u<1$。由于域 $k_{1}$ 和 $K_{2}$ 的图像是已知的，我们得出以下结论：
上半平面 $P_{+}$ 在 $\lambda(z)$ 作用下的共形图像是变量 $w$ 的平面，沿射线 $(\infty,- 1]$ 和 $[1, \infty)$ 。同一区域是下半平面 $\operatorname{Im} z<0$ 的图像。


对于同心圆族 $\gamma_{r} ,0<r<1$，单位圆的半径族是正交的。让我们找到这样一个半径的图像
$$
r_{\alpha}: z=t(\cos \alpha+i \sin \alpha), 0<t<1  \tag{4.6}
$$
首先假设 $0<\alpha<\frac{\pi}{2}$。我们有
$$
R_{\alpha}: w=\frac{1}{2}\left(z+\frac{1}{z}\right)=\frac{1}{2}\left(\frac{1}{t }+t\right) \cos \alpha-i \frac{1}{2}\left(\frac{1}{t}-t\right) \sin \alpha
$$
我们用一对实方程替换这个复杂的参数方程
$$
u=\frac{1}{2}\left(\frac{1}{t}+t\right) \cos \alpha, \quad v=-\frac{1}{2}\left(\frac{ 1}{t}-t\right) \sin \alpha   \tag{4.7}
$$
我们对两个等式求平方，然后将它们中的第一个除以 $\cos ^{2} \alpha$，将第二个除以 $\sin ^{2} \alpha$。将这些比率相互减去，我们得到
$$
\frac{u^{2}}{\cos ^{2} \alpha}-\frac{v^{2}}{\sin ^{2} \alpha}=1  \tag{4.8}
$$

这是具有半轴 的双曲线的规范方程 $|\cos \alpha|$ 和 $|\sin \alpha|$ 公式 $(4.7)$ 表明，对于 $0<\alpha<\frac{\pi}{2}$ 的范围， $u$ 的值为正，而 $v$ 的值为负。因此，半径 $r_{\alpha}$ 的图像是位于第四象限的双曲线 $(4.8)$ 的半分支。
其余三个半分支是对应于角度 $\pi-\alpha、\pi+\alpha$和$2\pi-\alpha$ 的半径图像。这些半径与初始半径 $r_{\alpha}$ 相对于坐标轴和原点对称。
双曲线 $(4.8)$ 的焦距为
$$
c=\sqrt{\cos ^{2} \alpha+\sin ^{2} \alpha}=1
$$
并且不依赖于$\alpha$，即该族$(4.8)$的所有双曲线都是共焦的：它们在点 1 和 -1 处具有共同的焦点。此外，它们与族的椭圆共焦$(4.4)$。
由于映射 $w=\lambda(z)$ 在单位圆的每个内点处是共形的，==因此$(4.4)$ 和 $(4.8)$ 族是正交的，如图是Zhukovskii函数的共形作用所示的单位圆。==

![s21163404252022.png](img/s21163404252022.png)