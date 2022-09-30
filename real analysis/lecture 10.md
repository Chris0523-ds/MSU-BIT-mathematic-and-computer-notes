## 1.Простейшие условия равномерной сходимости
### 定义
我们将说函数 $f$ 在段 $[-\pi,\pi]$ 上具有**分段连续导数**，若 $f^{\prime}$ 存在于该段的除了其中有限数量的点的所有的内部点。这些$f^{\prime}$中有限数量的点也都有有限的左右极限，此外，还存在极限： $\lim _{x \rightarrow-\pi+0} f^ {\prime}( x)$ 和 $\lim _{x \rightarrow \pi-0} f^{\prime}(x)$。
### 定义
我们说函数 $f$ 在 $[-\pi,\pi]$ 上具有阶 $n>1$ 的分段连续导数，如果函数 $f^{(n-1)}$ 具有在这个区间上的分段连续函数。
###定理(一致收敛的简单条件)
令 $f \in \mathcal{C}[-\pi, \pi], f(-\pi)=f(\pi)$ 且 $f$ 有一个分段连续导数。 然后它的三角傅里叶级数在 $[-\pi,\pi]$ 上一致地收敛到它。 此外，下面由绝对值组成的级数也一致收敛：
$$
\frac{\left|a_{0}\right|}{2}+\sum_{n=1}^{\infty}\left(\left|a_{n}\right||\cos n x|+\left|b_{n}\right||\sin n x|\right) .
$$
### 证明
让我们使用 Weierstrass 检验证明一致收敛。
首先，我们注意到
$$
\sum_{n=1}^{\infty}\left(\left|a_{n}\right| \cdot|\cos n x|+\left|b_{n}\right| \cdot|\sin n x| \right) \leqslant \sum_{n=1}^{\infty}\left(\left|a_{n}\right|+\left|b_{n}\right|\right)
$$
让我们建立这个级数的收敛。令 $\alpha_{n}, \beta_{n}-$ 为 $f^{\prime}$ 的傅里叶级数系数​​（在不连续点处任意进一步定义）那么：
$$
\alpha_{n}=\frac{1}{\pi} \int_{-\pi}^{\pi} f^{\prime}(x) \cos n x d x=\left.\frac{f(x) \cdot \cos n x}{\pi}\right|_{-\pi} ^{\pi}+\frac{n}{\pi} \int_{-\pi}^{\pi} f(x) \sin n x d x=n b_{n} 。
$$
同样，我们得到 $\beta_{n}=-n a_{n}$。它遵循
$$
\sum_{n=1}^{\infty}\left(\left|a_{n}\right|+\left|b_{n}\right|\right) \equiv \sum_{n=1}^{ \infty} \frac{\left|\alpha_{n}\right|+\left|\beta_{n}\right|}{n} 。
$$
由于$\left(\left|\alpha_{n}\right|-\frac{1}{n}\right)^{2} \geqslant 0$，扩展括号$\frac{\left|\alpha_{n}\right|}{n} \leqslant \frac{1}{2}\left(\left|\alpha_{n}\right|^{2}+\frac{1}{n^{2}}\right)$。
我们知道，级数 $\sum_{n=1}^{\infty} \frac{1}{n^{2}}$ 收敛。
此外，由Парсеваля不等式可以得到, 级数 $\sum_{n=1}^{\infty}\left(\left|\alpha_{n}\right|^{2}+\left|\beta_{n}\right|^{2}\right)$. 收敛到函数 $f^{\prime}$ 的范数。
所以，使用上面的估算，我们得到级数 $\sum_{n=1}^{\infty} \frac{\left|\alpha_{n}\right|+\left|\beta_{n}\right|}{n}$ 收敛。

## Простейшие условия почленного дифференцирования
现在让我们假设函数 $f$ 满足以下条件（我们将它们表示为条件 $(\star))$ ：
(1) $f(x)$ 和 $f^{(k)}(x)$ 对于 $k=\overline{1, m}$ 在 $[-\pi, \pi]$ 上是连续的。
(2) $f^{(m+1)}(x)$ 在 $[-\pi, \pi]$ 上是分段连续的。
(3) $f(-\pi)=f(\pi), f^{\prime}(-\pi)=f^{\prime}(\pi), \ldots, f^{(m)} (-\pi)=f^{(m)}(\pi)$。
### лемма
让 $f$ 满足条件 $(\star)$。 那么级数 $\sum_{k=1}^{\infty} k^{m}\left(\left|a_{k}\right|+\left|b_{k}\right|\right)$ 收敛。其中 $a_{k}, b_{k}-$ 是函数 $f$ 的傅里叶级数的系数。
### теорема（о почленном дифференцировании ряда фурье）。
让函数 $f$ 满足条件 $(\star)$。 那么这个函数的傅里叶级数可以逐项微分 $m$ 次。因此，通过$m$阶微分得到的级数在$[-\pi,\pi]$ 上一致收敛到相应的导数。
## Модуль непрерывности функции и его основные свойства
设函数 $f$ 在区间 $[-\pi, \pi]$ 上是连续的。
### 定义
我们将函数 $f$ 在 $[-\pi, \pi]$ 上的连续模 **(модулем непрерывности)** 如下表示：
$$
\omega(\delta, f)=\sup _{\substack{x^{\prime}, x^{\prime \prime} \in[-\pi, \pi] \\\left|x^{\prime}-x^{\prime \prime}\right|<\delta}}\left|f\left(x^{\prime}\right)-f\left(x^{\prime \prime}\right )\right|=\sup _{\substack{x, h+x \in[-\pi, \pi] \\|h|<\delta}}|f(x+h)-f(x)| .
$$
此外，假设函数$f$的周期是$2\pi$，并且对于某个 $\delta$ 在区间 $[-\pi-\delta, \pi+\delta]$ 上可积。
### 定义
让我们定义
$$
\sup _{\substack{x, x+h \in[-\pi, \pi] \\|h|<\delta}} \int_{-\pi}^{\pi}|f(x)-f(x+h)| d x=\widehat{\omega}(\delta, f)
$$
是连续模量的积分 **(интегральным модулем непрерывности)**。
根据以上定义可以得到，如果 $f$ 只在 $[-\pi, \pi]$ 上连续，那么根据康托尔定理它是一致连续的，并且它的**连续模量**趋于零，因为 $\delta \rightarrow 0+0$
然而，如果没有额外的假设，关于 $\omega(\delta, f)$ 和 $\widehat{\omega}(\delta, f)$ 趋向于零的速率并不能很好的表达。
### 引理 1
令函数 $f$ 在任何有限段上可积并且周期为 $2\pi$。 那么必然有：$$
\lim _{\delta \rightarrow 0+0} \widehat{\omega}(\delta, f)=0
$$
