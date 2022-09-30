## Условие сходимости тригонометрического ряда Фурье в точке
定义。
我们将说函数 $f$ 满足**具有指数 $\alpha(0<\alpha \leqslant 1)$ 在右侧点 $x$ 的 Hölder 条件**，如果满足以下两个条件：
(1) $\exists f(x+0)<\infty$;
(2) $\exists M, \delta>0:|f(x+t)-f(x+0)| \leqslant M \cdot|t|^{\alpha}~$ $\forall t, 0<t<\delta$.
定义。
我们将说函数 $f$ 满足**具有指数 $\alpha(0<\alpha \leqslant 1)$ 在左侧点 $x$ 的 Hölder 条件**，如果满足以下两个条件：
(1) $\exists f(x-0)<\infty$;
(2) $\exists M, \delta>0:|f(x+t)-f(x-0)| \leqslant M \cdot|t|^{\alpha}~$ $~\forall t,-\delta<t<0$.
### теорема
设$f$是周期为$ 2 \pi$且在任何有限区间上可积的函数，并在点 $x_{0}$ 处满足**指数为 $\alpha_{1}$ $\left(0<\alpha_{ 1} \leqslant 1\right)$ 在右边，指数 $\alpha_{2}\left(0<\alpha_{2} \leqslant 1\right)$ 在左边的Hölder条件**。然后它的三角傅里叶级数在点 $x_{0}$ 收敛到数 $\tilde{f}\left(x_{0}\right)$，其中 $\tilde{f}\left(x_{0} \right )=\frac{f\left(x_{0}-0\right)+f\left(x_{0}+0\right)}{2}$。
### 证明

## равномерная сходимость тригонометрического ряда фурье
考虑函数 $f \in \mathcal{C}[-\pi, \pi]$。
### 定义
我们会说 $f$ 属于**具有指数 $\alpha$ $(0<\alpha \leqslant 1)$ 的 Hölder 类**（并将其表示为 $\left.f \in \mathcal{C}^{\alpha }[ -\pi, \pi]\right)$ 如果 $\omega(\delta, f)=\underline{O}\left(\delta^{\alpha}\right)$，即
$$
\exists M>0, \delta>0: \sup _{\left|x_{1}-x_{2}\right|<\delta}\left|f\left(x_{1}\right)-f\left(x_{2}\right)\right| \leqslant M \delta^{\alpha}
$$
### 评论
从这个定义可以看出
- 如果 $f \in \mathcal{C}^{\alpha}[-\pi, \pi]$ 那么 $\omega(\delta, f)=\bar{o}(1)$ 对于 $\delta \rightarrow 0+0 .$
- 如果 $f$ 有有界导数，即 $\exists M>0:\left|f^{\prime}(x)\right| \leqslant M$，则由拉格朗日定理 $\left|f\left(x^{\prime}\right)-f\left(x^{\prime \prime}\right)\right|=\left|f^{\prime}(\xi)\right| \cdot\left|x^{\prime}-x^{\prime \prime}\right| \leqslant M \delta$，即 $f(x) \in \mathcal{C}^{1}$ 在考虑的区间上。