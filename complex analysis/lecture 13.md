# lecture 13
## 1.вычеты и их приложения
本章考虑的一般情况如下：在域 $\mathbf{G}$ 中定义了一个函数 $f$，除了一定数量的孤立奇异点外，它是解析的。初始部分的任务是学习如何有效地计算 $f$ 在属于 G 的轮廓上的积分。要存在这样的积分，轮廓必须不通过函数的奇异点。对此，我们将通过以下协议。
### СОГЛАШЕНИЕ О КОНТУРАХ.
下面考虑的所有轮廓都不通过函数 $f$ 的奇异点。
在解决等高线积分的有效计算问题中，留数的概念起主要作用。令 $z_{0}-$ 为函数 $f$ 的孤立奇异点。在这一点的某个去心邻域 $D$ 中，$f$ 可以用 Laurent 级数表示
$$
\sum_{n=-\infty}^{\infty} c_{n}\left(z-z_{0}\right)^{n} \tag{11.1}
$$
### Определение
级数的系数 $c_{-1}$称之为函数 $f$ 关于点 $z_{0}$（或点 $\left.z_{0}\right)$ 的留数。对于这个数字，我们将使用符号 $\operatorname{res}\left[f(z), z_{0}\right]$
令 $\gamma:\left|z-z_{0}\right|=\rho$ 是在 $D$ 中画的一个圆。那么余数 $c_{-1}$ 可以写成一个积分：
$$
\operatorname{res}\left[f(z), z_{0}\right]=\frac{1}{2 \pi i} \oint_{\gamma^{+}} f(z) d z \tag{11.2}
$$
余数在轮廓积分计算中的作用由以下推论解释。
### Tеорема (о вычетах)。
让轮廓 $Γ$ 通过域 $G$，并在里面包含函数 $f$ 的孤立奇异点$z_{1}, z_{2}, \ldots, z_{n}$。 然后
$$
\oint_{\Gamma^{+}} f(z) d z=2 \pi i \sum_{k=1}^{n} \operatorname{res}\left[f(z), z_{k}\right ] \tag{11.3}
$$
### доказательство(略)
### замечание
在整个域 $\mathbf{G}$ 中，$f$ 可以有无限个孤立的奇异点。 然而，只有有限数量的它们可以进入$Γ$。 否则，$Γ$ 内的无限奇异点集将有一个极限点，该极限点也是奇异的，但不是孤立奇异点。 本章开头给出的描述排除了这种非孤立奇点的存在。
公式 $(11.3)$ 表明，为了有效地计算轮廓积分，必须学会计算关于函数 $f$ 的孤立奇异点的留数。这些点等于 0，因为相应的 Laurent 级数不包含负幂 $z-z_{k}$ 的项。不幸的是，没有方便的方法来找到基本奇异点的残差。但是对于应用中最常见的奇异点类型，即极点，有计算残差的简单公式。
让我们从简单极点（即 1 阶极点）的情况开始推导出这些公式。 设 $z_0$ 是函数 $f$ 的这样一个极点。 在点 $z_{0}$ 的去心邻域中表示 $f$ 的 Laurent 级数具有以下形式
$$
f(z)=\frac{c_{-1}}{z-z_{0}}+c_{0}+c_{1}\left(z-z_{0}\right)+\cdots
$$
其中
$$
f(z)\left(z-z_{0}\right)=c_{-1}+c_{0}\left(z-z_{0}\right)+c_{1}\left(z-z_ {0}\right)^{2}+\cdots 
$$
右侧的数列之和在 $z_{0}$ 处具有极限值 $c_{-1}$。 所以
$$
c_{-1}=\operatorname{res}\left[f(z), z_{0}\right]=\lim _{z \rightarrow z_{0}}\left[f(z)\left(z -z_{0}\right)\right] \tag{11.4}
$$
对于一个简单的极点 $z_{0}$，还有另一个计算留数的公式。它假设 $f$ 在点 $z_{0}$ 的邻域中通过解析函数的比率以一种或另一种方式表示
$$
f(z)=\frac{\varphi(z)}{\psi(z)} \tag{11.5}
$$
使得 $\varphi\left(z_{0}\right) \neq 0$，而 $\psi\left(z_{0}\right)=0$，但是 $\psi^{\prime}\left( z_{0}\right) \neq 0$（即 $z_{0}-$ 是 $\psi(z)$ 的简单零，因此是 $f)$ 的简单极点。
将分数 $(11.5)$ 代入式 $(11.4)$ 并利用函数 $\psi$ 在 $z-z_{0}$ 的幂中的展开，我们得到
$$
c_{-1}=\lim _{z \rightarrow z_{0}} \frac{\varphi(z)\left(z-z_{0}\right)}{\psi^{\prime}\left(z_{0}\right)\left(z-z_{0}\right)+\frac{1}{2} \psi^{\prime \prime}\left(z_{0}\right)\left(z-z_{0}\right)^{2}+\cdots}=\frac{\varphi\left(z_{0}\right)}{\psi^{\prime}\left(z_{0}\right)} .
$$
因此，计算关于简单极点 $z_{0}$ 的残差的第二个公式具有以下形式:
$$
\operatorname{res}\left[f(z), z_{0}\right]=\frac{\varphi\left(z_{0}\right)}{\psi^{\prime}\left(z_{0}\right)} \tag{11.6}
$$
让我们转到任意阶 $m$ 的极点 $z_0$ 的情况。在这样一个极点的邻域中，$f$ 具有形式的 Laurent 展开式
$$
f(z)=\frac{c_{-m}}{\left(z-z_{0}\right)^{m}}+\frac{c_{-m+1}}{\left(z- z_{0}\right)^{m-1}}+\cdots+\frac{c_{-1}}{z-z_{0}}+c_{0}+c_{1}\left(z-z_ {0}\right)+\cdots
$$
其中有
$$
f(z)\left(z-z_{0}\right)^{m}=c_{-m}+c_{-m+1}\left(z-z_{0}\right)+\cdots+ c_ {-1}\left(z-z_{0}\right)^{m-1}+\cdots 。
$$
将此关系微分 $m-1$ 次，我们有
$$
\frac{d^{m-1}\left[f(z)\left(z-z_{0}\right)^{m}\right]}{d z^{m-1}}=(m-1) ! c_{-1}+m(m-1) \cdots 2 c_{0}\left(z-z_{0}\right)+\cdots
$$
==将两个部分都作为 $z \rightarrow z_{0}$ 传递到极限，我们最终得到==
$$
c_{-1}=\operatorname{res}\left[f(z), z_{0}\right]=\frac{1}{(m-1) !} \lim _{z \rightarrow z_{0 }} \frac{d^{m-1}\left[f(z)\left(z-z_{0}\right)^{m}\right]}{d z^{m-1}} \tag{11.7}
$$
如果我们同意函数 $f$ 的零阶导数就是这个函数本身并且 $0 !=1$，那么即使对于 $m=1$，公式 $(11.7)$ 也是有意义的，变成公式 $(11.4)$。

### Вычет относительно бесконечно удаленной точки
上一节的所有论点都默认 $z_{0}$ 是域的有限点。我们现在考虑扩展复平面上的 $f$ 并假设 $f$ 是域 $\mathrm{D}:|z|>R$ 中的解析函数。 （回想一下，这种形式的任何域都被认为是无限远点的邻域。）在这种情况下，$\infty$ 被认为是函数 $f$ 的孤立奇异点。在环$D$ 中，函数$f$ 由 Laurent 级数表示：
$$
f(z)=\sum_{n=-\infty}^{\infty} c_{n} z^{n} \tag{11.8}
$$
### Определение
级数的系数 $c_{-1}$ 前附加一个减号，称为关于点 $\infty$ 的函数 $f$ 的留数。
### 无限远点的留数
该留数的积分表示为：
$$
\operatorname{res}[f(z), \infty]=\frac{1}{2 \pi i} \oint_{\gamma-} f(z) d z \tag{11.9}
$$
这里 $\gamma-$ 是 $|z|=\rho$ 形式的任意圆，其中 $\rho>R$。
与有限奇异点 $z_0$ 的情况相比，绕圆 $\gamma$ 的方向变化可以通过均匀性要求来解释：在这两种情况下，观察者沿圆的运动必须以这样一种方式发生：奇点的邻域仍然在他的左边。
### теорема (о полной сумме вычетов)
令函数 $f$ 在 $\mathbb{C}$ 中只有有限数量的奇异点 $z_{1}, z_{2}, \ldots, z_{n}$。 我们设置 $z_{0}=\infty$。 然后
$$
\sum_{k=0}^{n} \operatorname{res}\left[f(z), z_{k}\right]=0 \tag{11.10}
$$
### доказательство
让我们构造一个半径 $\rho$ 的圆 $\gamma:|z|=\rho$，使得函数$f$的所有有限奇异点 $z_{1}, z_{2}, \ldots, z_{n}$都被包含在内。 根据Tеорема о вычетах，我们有
$$
\frac{1}{2 \pi i} \oint_{\gamma^{+}} f(z) d z=\sum_{k=1}^{n} \operatorname{res}\left[f(z) , z_{k}\right] \tag{11.11}
$$
见公式$(11.3)$。 另一方面，圆 $\gamma$ 位于无穷远点附近，$f$ 由 Laurent 级数 $(11.8)$ 表示，因此 res $[f( z), \infty]$ 的留数可以用$(11.9)$ 的形式表述。 将 $(11.9)$ 和 $(11.11)$ 相加，我们得到 $(11.10)$。

### Пример $1 .$
Вычислить интеграл
$$
I=\oint_{|z|=2} \frac{d z}{(z-3)\left(z^{5}-1\right)}
$$
## 通过留数计算实变量的积分
实变量 $x$ 的积分有许多类，使用余数技术可以大大简化积分的计算。 在本节中，我们考虑三类这样的积分。
### 1.$\int_{0}^{2 \pi} R(\cos \varphi, \sin \varphi) d \varphi$ 形式的积分

这里 $R$ 是两个变量的有理函数。 在积分学课程中，这种类型的积分在各种三角代换的帮助下被简化为有理分数的积分。
我们将这样做：通过改变变量 $z=e^{i \varphi}$ 我们将把原始积分转换为单位圆上的轮廓积分。为了进行这种替换，我们需要关系
$$
\begin{gathered}
\cos \varphi=\frac{1}{2}\left(e^{i \varphi}+e^{-i \varphi}\right)=\frac{1}{2}\left(z+\frac{1}{z}\right) \\
\sin \varphi=\frac{1}{2 i}\left(z-\frac{1}{z}\right), \quad d z=i e^{i \varphi} d \varphi \\
d \varphi=\frac{d z}{i z}
\end{gathered}
$$
这种换元的结果是积分
$$
\frac{1}{i} \oint_{|z|=1} R\left[\frac{1}{2}\left(z+\frac{1}{z}\right), \frac{1} {2 i}\left(z-\frac{1}{z}\right)\right] \frac{d z}{z}
$$
积分符号下的变量 z 的有理函数在整个复平面上具有有限数量的极点。因此，要计算这个积分，可以同时使用теорему о вычетах和теорему о полной сумме вычетов两个引理。
#### Пример $2 .$
Вычислить интеграл
$$
I=\int_{0}^{2 \pi} \frac{d \varphi}{5+3 \cos \varphi}
$$
### 2.$\int_{-\infty}^{\infty} f(x) d x$ 形式的积分
为了将余数技术应用于这种类型的积分，我们假设被积函数 f 解析地延续到复平面的上半平面或下半平面。 为明确起见，设上半平面$\pi_{+}：\operatorname{lm} z>0$。 它在实轴上的闭合用 $\bar{\pi}_{+}$ 表示。
#### Теорема
令从实轴延伸到上半平面的函数$f$满足以下条件：
(1) $f$ 在$\pi_{+}$ 中具有有限数量的奇异点$z_{1}, z_{2}, \ldots, z_{n}$ 并且在实轴的点处是连续的；
(2) 对于 $\bar{\pi}_{+}$ 中所有足够大的 $z$，以下估计成立：
$$
|f(z)| \leqslant \frac{M(z)}{|z|} \tag{11.15}
$$
这里 $M(z)$ 是复变量 $z$ 的非负函数，随着 $z \rightarrow \infty$ 趋于零并保持在闭合的上半平面中。
那么积分 $I=\int_{-\infty}^{\infty} f(x) d x$ 至少在**главная часть** 意义上存在并且
$$
\text { (v.p.) } \int_{-\infty}^{\infty} f(x) d x=2 \pi i \sum_{k=1}^{n} \operatorname{res}\left[f( z), z_{k}\right] \tag{11.16}
$$
#### замечание
条件 (11.15) 的含义是对于 $z \rightarrow \infty$ 并保持在闭合的上半平面内，函数 $f$ 的下降至少比函数 $\frac{1}{z}$ 稍微快一点。
#### Пример $3 .$
Вычислить интеграл
$$
I=\int_{-\infty}^{\infty} \frac{d x}{\left(x^{2}+1\right)^{3}}
$$
### 3.$\int_{-\infty}^{\infty} e^{i a x} f(x) d x$ 形式的积分
被积函数中指数因子的存在将使我们大大削弱对函数 $f$ 在无穷大处衰减率的要求。让我们首先证明一个重要的辅助断言，称为 Jordan 引理。
#### Леммой Жордана
让函数$f$ 在闭域$|z| \geqslant R_{0}中连续, \operatorname{lm} z \geqslant 0$, 当 $z \rightarrow \infty$ 留在半平面 $\bar{\pi}_{+}$ 时趋于零。那么对于所有 $a>0$ 积分
$$
J=\int_{\gamma_{R}} e^{i a z} f(z) d z \tag{11.18}
$$
当 $R \rightarrow \infty$ 时趋于零。这里 $\gamma_{R}-$ 是一个半圆 $|z|=R, \operatorname{lm} z \geqslant 0$。
我们现在指出积分形式 $\int_{-\infty}^{\infty} e^{i a x} f(x) d x$ 可以使用留数计算。
### теорема
设一个从实轴延伸到上半平面的函数 $f$ 满足定理 $7.1$ 的条件 1 并且趋向于零，因为 $z \rightarrow \infty$ 保持在闭合的上半平面上。 那么对于所有 $a>0$ 积分 $I=\int_{-\infty}^{\infty} e^{i a x} f(x) d x$ 至少在главная часть的意义上存在并且
$$
\text { (v.p.) } \int_{-\infty}^{\infty} e^{i a x} f(x) d x=2 \pi i \sum_{k=1}^{n} \operatorname{res} \left[e^{i a z} f(z), z_{k}\right] \tag{11.21}
$$
####  $4 .$
Вычислить интеграл Лапласа
$$
I=\int_{-\infty}^{\infty} \frac{\cos \alpha x}{x^{2}+a^{2}} d x
$$
Константы $\alpha$ и а считать положительными.