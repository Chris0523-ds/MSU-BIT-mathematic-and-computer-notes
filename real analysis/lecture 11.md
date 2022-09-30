## Модуль непрерывности функции и его основные свойства

令 $f$ 和 $g$ 是周期为 $2\pi$且在任何有限区间上可积的函数，并且令 $x$ 是任意点。令有一个函数
$$
F_{x}(t)=f(x+t) g(t)
$$

它的值取决于作为参数的 $x$。

### 引理 2

函数 $F$ 的连续性积分模在 $[-\pi, \pi]$ 上关于 $x$ 一致趋于 0，如 $\delta \rightarrow 0+0$，即
$$
\widehat{\omega}(\delta, F) \stackrel{[-\pi, \pi]}{\rightrightarrows} 0 \text { по x }  \text { при } \delta \rightarrow 0+0
$$

### 证明

首先，让我们估计 $\hat{\omega}(\delta, F)$ 中包含的差 $|F(t+h)-F(t)|$ 的绝对值：
$$
\begin{aligned}
&|F(t+h)-F(t)|=|f(x+t+h) g(t+h)-f(x+t) g(t)|=\\
=&|f(x+t+h) g(t+h)-f(x+t) g(t+h)+f(x+t) g(t+h)-f(x+t) g(t)| \leqslant \\
& \leqslant|g(t+h)| \cdot|f(x+t+h)-f(x+t)|+|f(x+t)| \cdot|g(t+h)-g(t)|
\end{aligned}
$$
由于可积性，$f$ 和 $g$ 是有界的，因此
$$
|g(t+h)|,|f(x+t)| \leqslant M 。
$$
另请注意
$$
\begin{aligned}
& \int_{-\pi}^{\pi}|f(x+t+h)-f(x+t)| d t=\{y=x+t\}=\\
=& \int_{-\pi+t}^{\pi+t}|f(y+h)-f(y)| d y=\int_{-\pi}^{\pi}|f(y+h)-f(y)| d y .
\end{aligned}
$$
那么对于 $\forall x$
$$
\widehat{\omega}(\delta, F)=\sup_{\substack{t, t+h \in[-\pi, \pi] \\|h|<\delta}}\int_{-\pi}^{\pi}|F(t+h)-F(t)| d t \leqslant M \widehat{\omega}(\delta, f)+M \widehat{\omega}(\delta, g) .
$$
由引理 1 ($f$ 和 $g$ 不依赖于 $x$) , $\widehat{\omega}(\delta, f) \underset{\delta \rightarrow 0+0}{\longrightarrow} 0$ 和 $\widehat{\omega}(\delta, g) \underset{\delta \rightarrow 0+0}{\longrightarrow} 0$。

### 引理 3

令 $f$ 是周期为 $2\pi$ 的函数，且在任意有限区间上可积。 那么其三角傅里叶级数的系数满足不等式
$$
\sqrt{a_{n}^{2}+b_{n}^{2}} \leqslant \frac{1}{2 \pi} \widehat{\omega}\left(\frac{\pi}{n }, f\right) 。
$$

### 证明

注意上面不等式左边是复数$a_{n}+i b_{n}$的模，所以我们需要复数的一些性质。 我们提醒您，根据欧拉公式
$$
e^{i \varphi}=\cos \varphi+i \sin \varphi
$$
特别是 $e^{i \pi}=-1$。
现在考虑 $a_{n}+i b_{n}$ ：
$$
\begin{aligned}
a_{n}+i b_{n}=\frac{1}{\pi} \int_{-\pi}^{\pi} f(t) \cos n t d t+\frac{i}{\pi} \int_{-\pi}^{\pi} f(t) \sin n t d t =\\
=\underbrace{\frac{1}{\pi} \int_{-\pi}^{\pi} f(t) e^{i n t} d t}_{I_{1}}=\left\{t=y+\frac{\pi}{n}\right\}=-\frac{1}{\pi} \int_{-\pi-\frac{\pi}{n}}^{\pi-\frac{\pi}{n}} f\left(y+\frac{\pi}{n}\right) e^{i n y} d y=\\
=\underbrace{-\frac{1}{\pi} \int_{-\pi}^{\pi} f\left(y+\frac{\pi}{n}\right) e^{i n y} d y}_{I_{2}}
\end{aligned}
$$
因为 $f$ 是 $2 \pi$-periodic，所以$e^{iny}$ 根据欧拉公式具有相同的周期。
现在让我们将 $a_{n}+i b_{n}$ 表示为 $l_{1}$ 和 $I_{2}$ 的一半：
$$
a_{n}+i b_{n}=\frac{1}{2 \pi} \int_{-\pi}^{\pi} e^{i n t}\left(f(t)-f\left( t+\frac{\pi}{n}\right)\right) d t 。
$$
即：
$$
\left|a_{n}+i b_{n}\right| \leqslant \frac{1}{2 \pi} \int_{-\pi}^{\pi}\left|e^{i n t}\right| \cdot\left|f(t)-f\left(t+\frac{\pi}{n}\right)\right| d t \leqslant \frac{1}{2 \pi} \widehat{\omega}\left(\frac{\pi}{n}, f\right),
$$
因为 $\left|e^{\text {int }}\right|=1$。

### 推论 1
令函数 $f$ 是周期为 $ 2\pi$ 且在任何有限区间可积的函数，并且令 $g(t)$ 在$[-\pi, \pi]$ 上是可积的。 
那么函数 $F_{x}(t)=f(x+t)g(t)$ 的三角傅里叶系数为：
$$
a_{n}(x)=\frac{1}{\pi} \int_{-\pi}^{\pi} f(x+t) g(t) \cos n t d t, \quad b_{n}(x)=\frac{1}{\pi} \int_{-\pi}^{\pi} f(x+t) g(t) \sin n t d t .
$$

在 $[-\pi, \pi]$ 上的 $x$ 中，$n \rightarrow \infty$ 趋向于 0。
### 证明
我们将函数 $g$ 以 $2\pi$为周期性地扩展到实数域。那么根据**引理2**可以得到：
$$
\widehat{\omega}(\delta, F) \stackrel{[-\pi, \pi]}{\rightrightarrows} 0 \text { при } \delta \rightarrow 0+0 .
$$
通过**引理3**可以得到：：
$$
\sqrt{a_{n}^{2}(x)+b_{n}^{2}(x)} \leqslant \frac{1}{2 \pi} \widehat{\omega}\left(\frac {\pi}{n}, F\right) \underset{n \rightarrow \infty}{\longrightarrow} 0 。
$$
考虑到 $\left|a_{n}(x)\right|,\left|b_{n}(x)\right| \leqslant \sqrt{a_{n}^{2}(x)+b_{n}^{2}(x)}$，我们得到了我们需要的。
### 推论 2
令函数 $f$ 以 $2 \pi$ 为周期在任何有限区间上是可积的，并且令$g(t)$ 在$[-\pi, \pi]$ 上是可积的。那么有：
$$
c_{n}(x)=\frac{1}{\pi} \int_{-\pi}^{\pi} f(x+t) g(t) \sin t\left(n+\frac{1 }{2}\right) d t \stackrel{[-\pi, \pi]}{\rightrightarrows} 0 ~ 当 ~ n \rightarrow \infty
$$
### 证明
$$
\sin \left(n+\frac{1}{2}\right) t=\sin \frac{t}{2} \cos n t+\cos \frac{t}{2} \sin n t 。
$$

那么
$$
c_{n}(x)=\frac{1}{\pi} \int_{-\pi}^{\pi} f(x+t) g(t) \sin \frac{t}{2} \cos n t d t+\frac{1}{\pi} \int_{-\pi}^{\pi} f(x+t) g(t) \cos \frac{t}{2} \sin n t d t 。
$$
接下来，我们将推论 1 应用于这些积分，将第一个积分中的函数 $g(t) \cdot \sin t / 2$ 作为 $g(t)$，并将 $g(t) \cdot \cos t /2$ 作用在第二个 。


### 符号 $\widehat{c}_{n}(x), c_{n}^{+}(x), c_{n}^{-}(x)$
我们介绍以下函数：
$$
\begin{aligned}
&\widehat{c}_{n}(x)=\frac{1}{\pi} \int_{\delta \leqslant|t| \leqslant \pi} f(x+t) \frac{\sin \left(n+\frac{1}{2}\right) t}{2 \sin \frac{t}{2}} d t \\
&c_{n}^{+}(x)=\frac{1}{\pi} \int_{\delta \leqslant t \leqslant \pi} f(x+t) \frac{\sin \left(n+\frac{1}{2}\right) t}{2 \sin \frac{t}{2}} d t, \\
&c_{n}^{-}(x)=\frac{1}{\pi} \int_{-\pi \leqslant t \leqslant-\delta} f(x+t) \frac{\sin \left(n+\frac{1}{2}\right) t}{2 \sin \frac{t}{2}} d t .
\end{aligned}
$$

### 推论 3
令函数 $f$ 以 $2 \pi$ 为周期且在任何有限区间上可积，令$\delta$ 为固定数，$0<\delta<\pi$。 那么函数序列 $\widehat{c}_{n}(x), c_{n}^{+}(x), c_{n}^{-}(x)$ 一致趋向于0，当 $x$ 在 $[-\pi, \pi]$ 上且 $n \rightarrow \infty$。
### 证明
使用推论 2，对于函数序列 $\widehat{c}_{n}(x)$，我们取函数 $g(t)= \begin{cases}\frac{1}{2 \sin \frac{t }{2 }}, & \text { 若 } \delta \leqslant|t| \leqslant \pi, \\ 0, & |t|<\delta\end{cases}$
对于 $c_{n}^{+}(x)$ 函数 $g(t)= \begin{cases}\frac{1}{2 \sin \frac{t}{2}}, & \delta \leqslant t \leqslant \pi, \\ 0, & -\pi \leqslant t<\delta .\end{cases}$
对于 $c_{n}^{-}(x)$ 函数 $g(t)= \begin{cases}\frac{1}{2 \sin \frac{t}{2}}, & -\pi \leqslant t \leqslant-\delta, \\ 0, & -\delta<t \leqslant \pi .\end{cases}$
进一步注意，这些函数中的每一个都在 $[-\pi,\pi]$ 上可积。
## Принцип локализации Римана
### Теорема (римана)
令 $f$ 是周期为 $2 \pi$ 且在任何有限区间上可积的函数。 那么它的三角傅里叶级数在任意固定点 $x$ 处的收敛性只取决于它的参数在该点的任意小的 $\delta$-邻域中的值，$\mathrm{U}_{\delta}( x)$。