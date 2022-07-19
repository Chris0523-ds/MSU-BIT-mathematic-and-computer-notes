如果虚数不为0，则表示复数的点与原点不同。在这种情况下，要确定复数，连同笛卡尔坐标 $x$ 和 $y$，还可以使用极坐标 - 半径矢量 $r>0$ 和极角 $\Phi$（仅定义向上为 $2 \pi )$ 的任意整数倍。符号：$r=|z|, \quad \Phi=\operatorname{Arg} z .$
数$z\neq 0$的参数值中只有一个，在半区间$(-\pi,\pi]$。称为参数的主值. 符号：$\arg z$. 所以，
$$
-\pi<\arg z=\varphi \leqslant \pi, \quad \operatorname{Arg} z=\arg z+2 \pi n, \quad n \in \mathbb{Z}
$$

## множества точек на плоскости
与**область** 一词通常用作**открытное множество**一词的同义词的分析相比，在 TFKT 中，集合不仅是开集，而且是连通集。因此，开圆 $|z-a|<r$ 或圆环 $R_{2}<|z-a|<R_{1}$ 是区域(**область**)，而闭合圆 $|z-a| \leqslant r$ 或设置 $|z| \neq 1-$ 不是。
最后一个示例中的断开集是两个连通子集（连通分量）的并集：圆 $|z|<1$ 和区域 $|z|>1$。平面 $\mathbb{C}$ 上的集合 $\mathbf{M}_{1}$ 和 $\mathbf{M}_{2}$ 之间的距离由下式给出
$$
\rho\left(M_{1}, M_{2}\right)=\inf _{z_{1} \in M_{1}, z_{2} \in M_{2}}\left|z_{1 }-z_{2}\right| .
$$

### теорема
设闭集 $\mathrm{M}_{1}$ 和 $\mathrm{M}_{2}$ 是不相交的，并且其中至少有一个是有界的。 那么距离 $\rho\left(\mathbf{M}_{1}, \mathbf{M}_{2}\right)$ 为正。

==让我们举一个例子来说明有界要求在这个定理中的作用。 令 $\mathbf{M}_{1}-$ 为实轴的点集，$\mathbf{M}_{2}-$ 双曲线 $y=\frac{1}{x}$ 的点集。 这些集合是闭合的并且不相交，但是它们之间的距离等于零，这与前面的定理不矛盾，因为两个集合都没有边界。==
## функции комплексного переменного. предел. непрерывность
### Определение
令 $E$ 为复平面的任意子集，并为每个 $z \in \mathbf{E}$ 分配一个或多个数字 $w$ .在这种情况下，我们说在 $E$ 上给出了复变量 $z$ 的函数，并用 $w=f(z)$ 之类的符号写出这个事实。
例子。
单值函数
$$
\operatorname{Re} z, \operatorname{Im} z,|z|, \arg z, \bar{z}, z^{n}(n \in \mathbb{N})
$$
多值函数
$$
\sqrt[n]{z}(n \in \mathbb{N}), \operatorname{Arg} z
$$
我们把 $z=x+i y, w=u+i v$, 其中 $x, y, u, v \in \mathbb{R}$。那么在 $\mathrm{E}$ 上设置 $w=f(z)$ 等价于将 $\mathrm{E}$ 设置为两个实函数的欧几里得平面的子集 $u=u(x, y)$ 和 $v= v(x, y)$。
符号：
**$\operatorname{dom} f-$ 函数 $f$ 的定义域； $\operatorname{im} f-$ 这个函数值的范围； $f(E)-$是 $f$ 在集合 $E$ 上取值的集合。**
定义。
令 E $\subset \operatorname{dom} f$，令 $z_o$ 为 $E$ 的极限点。
$$
\lim _{z \rightarrow z_{0}} f(z)=A
$$
方法：
$$
\forall \varepsilon>0 \exists \delta(\varepsilon)>0: \forall z,\left|z-z_{0}\right|<\delta(\varepsilon) \Longrightarrow|f(z)-A| <\varepsilon
$$
设$z=x+i y, z_{0}=x_{0}+i y_{0}, f(z)=u+i v, A=B+i C$
### теорема
复数关系
$$
\lim _{z \rightarrow z_{0}} f(z)=A
$$
等价于两个实数极限关系
$$
\lim _{\substack{x \rightarrow x_{0} \\ y \rightarrow y_{0}}} u(x, y)=B, \quad \lim _{\substack{x \rightarrow x_{0} \\ y \rightarrow y_{0}}} v(x, y)=C .
$$
让 $g$ 和 $h$ 定义在同一个集合 $\mathbf{E}$ 上，并且
$$
\lim _{z \rightarrow z_{0}} g(z)=A_{1}, \quad \lim _{z \rightarrow z_{0}} h(z)=A_{2}
$$
那么 $\lim _{z \rightarrow z_{0}}(g(z) \pm h(z))=A_{1} \pm A_{2}, \quad \lim _{z \rightarrow z_{0 }}(g(z) \cdot h(z))=A_{1} \cdot A_{2}$。
如果 $A_{2} \neq 0$，那么
$$
\lim _{z \rightarrow z_{0}} \frac{g(z)}{h(z)}=\frac{A_{1}}{A_{2}}
$$
### Определение
令$E \subset \operatorname{dom} f$，令$z_{0} \in E$ 为$E$ 的极限点。函数 $f(z)$ 在点 $z_{0}$ 是连续的，如果
$$
\lim _{z \rightarrow z_{0}} f(z)=f\left(z_{0}\right)
$$
### Определение
如果 $f(z)$ 在 E 的每个点上是连续的，则称 $f$ 在 $E$ 上是连续的。
特奥佩玛。
函数 $f(z)=u+i v$ 在点 $z_{0}=x_{0}+i y_{0}$ 是连续的当且仅当
$$
\lim _{\substack{x \rightarrow x_{0} \\ y \rightarrow y_{0}}} u(x, y)=u\left(x_{0}, y_{0}\right), \quad \lim _{\substack{x \rightarrow x_{0} \\ y \rightarrow y_{0}}} v(x, y)=v\left(x_{0}, y_{0}\right) .
$$
推论：
令 $g(z)$ 和 $h(z)$ 在 $z_{0}$ 点是连续的。那么它们的和、差和乘积在该点也是连续的。如果 $h\left(z_{0}\right) \neq 0$，则商也是连续的。
### 推论 $2 .$
令函数 $w=f(z)$ 在集合 $\mathbf{E}$ 和 $f(\mathrm{E}) \subset \mathbf{F}$ 上是连续的。令函数 $\zeta=g(w)$ 在集合 $\boldsymbol{F}$ 上是连续的。那么复函数（叠加 $\zeta=g[f(z)] \equiv G(z)$ 在 $E .$ 上是连续的

令函数 $w=f(z)$ 在有界闭集 E（紧集）上是连续的。则满足以下三个条件：
###推论 3（魏尔斯特拉斯定理 1）。
函数 $w=f(z)$ 在 $E$上有界。
###推论 4（韦杰斯特拉斯第二定理的复杂版本）。
函数 $w=f(z)$ 的模在 E 上达到其上限和下限。
### 推论 5 (TEOPEMA KAHTOPA)。
函数 $w=f(z)$ 在 $E$ 上一致连续。

