## Теорема фейера
### 定义(第二课)
$$
J(y)=\int_{a}^{+\infty} f(x, y) d x \tag{1}
$$
在 $\forall y \in[c, d]$ 上收敛的反常积分 $(1)$ 在 $[c, d]$ 上对于参数 $y$ 中称为**一致收敛**，如果
$$
\forall \varepsilon>0 \exists A(\varepsilon)>a: \forall R \geqslant A(\varepsilon) \text { and } \forall y \in[c, d] \Rightarrow\left|\int_{R }^{+\infty} f(x, y) d x\right|<\varepsilon 。
$$
可以表示为：$\int_{a}^{+\infty} f(x, y) d x \stackrel{[c, d]}{\rightrightarrows}$
### Теорема (фейера)
函数 $f(x) \in C[-\pi, \pi]$ и $f(-\pi)=f(\pi)$, 当且仅当 $\sigma_{n}(x, f) \stackrel{[-\pi, \pi]}{\rightrightarrows} f(x), n \rightarrow \infty$.
### 初步推论
假设$f(x)=1$。 考虑其傅里叶级数的部分和，为此我们计算系数：
$$
a_{0}=\frac{1}{\pi} \int_{-\pi}^{\pi} d x=2, \quad a_{k}=\frac{1}{\pi} \int_{- \pi}^{\pi} \sin k x d x=0, \quad b_{k}=\frac{1}{\pi} \int_{-\pi}^{\pi} \cos k x d x=0 。
$$
那么$S_{n}(x, f)=\frac{a_{0}}{2}=1 \Rightarrow \sigma_{n}(x, f)=1$。 由此可见
$$
\frac{1}{\pi n} \int_{-\pi}^{\pi} \frac{\sin ^{2} \frac{n t}{2}}{2 \sin ^{2} \frac{t}{2}} d t=1 \tag{1}
$$

$$
\frac{1}{\pi} \int_{-\pi}^{\pi} \frac{\sin \left(n+\frac{1}{2}\right) t}{2 \sin \frac{t}{2}} d t =1 \tag{2}
$$
**必要性：**
设 $\sigma_{n}(x, f) \stackrel{[-\pi, \pi]}{\rightrightarrows} f(x), n \rightarrow \infty$。因为$\forall n \in \mathbb{N}$ $\sigma_{n}(x, f) \in \mathcal{C}[-\pi, \pi]$，然后 $f \in \mathcal{C } [-\pi,\pi]$
此外，$\sigma_{n}(-\pi, f) \rightarrow f(-\pi), \sigma_{n}(\pi, f) \rightarrow f(\pi)$，并且从 $ 的周期性\sigma_{n}(x, f)$ 意味着 $\sigma_{n}(-\pi, f)=\sigma_{n}(\pi, f)$。

**充分性：**
首先，我们将 $2 \pi$ 周期函数 $f(x)$ 扩展到。我们得到一个在 上一致连续的函数。修复任意 $\varepsilon>0$。那么，由于均匀连续性
$$
\exists \delta(\varepsilon)>0: \forall t: 0<|t|<\delta(\varepsilon) \Rightarrow|f(x+t)-f(x)|<\varepsilon 。
$$
我们需要证明
$$
\forall \varepsilon>0 \exists N(\varepsilon): \forall n \geqslant N, \forall x \in[-\pi, \pi] \Rightarrow\left|\sigma_{n}(x, f)- f(x)\right|<\varepsilon
$$
我们使用 $(1)$ 写出 $f(x)$， 作为
$$
f(x)=f(x) \cdot 1=f(x) \frac{1}{\pi n} \int_{-\pi}^{\pi} \frac{\sin ^{2} \frac{n t}{2}}{2 \sin ^{2} \frac{t}{2}} d t .
$$
由此我们得到
$$
\begin{aligned}
&\left|\sigma_{n}(x, f)-f(x)\right|=\frac{1}{\pi n}\left|\int_{-\pi}^{\pi}(f(x+t)-f(x)) \Phi_{n}(t) d t\right| \leqslant \\
&\leqslant \frac{1}{\pi n} \int_{-\pi}^{\pi}|f(x+t)-f(x)| \Phi_{n}(t) d t= \\
&=\frac{1}{\pi n} \int_{-\delta}^{\delta}|f(x+t)-f(x)| \Phi_{n}(t) d t+\frac{1}{\pi n} \int_{\delta<|t|<\pi}|f(x+t)-f(x)| \Phi_{n}(t) d t .
\end{aligned}
$$
我们将第一个积分表示为 $I_{1}$，将第二个积分表示为 $I_{2}$，并分别评估它们。 让我们从 $I_{1}$ 开始。 使用一致连续性，
$$
\left|I_{1}\right| \leqslant \frac{\varepsilon}{2} \cdot \frac{1}{\pi n} \int_{-\delta}^{\delta} \Phi_{n}(t) d t{ }^{\Phi_ {n}(t) \geqslant 0} \leqslant \frac{\varepsilon}{2} \cdot \underbrace{\frac{1}{\pi n} \int_{-\pi}^{\pi} \Phi_ {n}(t) d t}_{=1}=\frac{\varepsilon}{2}
$$
现在评估 $I_{2}$ ：
$$
\left|I_{2}\right|=\frac{1}{\pi n} \int_{\delta<|t|<\pi}|f(x+t)-f(x)| \Phi_{n}(t) d t \mid
$$
由于 $f(x) \in C[-\pi, \pi]$ （并使用周期性扩展），$\exists M>0: \forall x \in \Rightarrow|f(x)| \leqslant M$。 那么：
$$
|f(x+t)-f(x)| \leqslant|f(x+t)|+|f(x)| \leqslant 2M
$$
让我们估计 Fejér 核：
$$
\left|\sin ^{2} \frac{nt}{2}\right| \leqslant 1
$$

$$
\left|\frac{1}{2 \sin ^{2} \frac{t}{2}}\right| \leqslant\left|\frac{1}{2 \sin ^{2} \frac{\delta}{2}}\right|$$.
可以得到
$$
\left|I_{2}\right| \leqslant \frac{2 M}{\pi} \cdot \frac{1}{2 \sin ^{2} \frac{\delta}{2}} \cdot \frac{1}{n} \int_{ \delta<|t|<\pi} d t=\frac{\text { const }}{n} 。
$$
这意味着我们总是可以选择 $n$ 使得这个表达式不超过 $\frac{\varepsilon}{2}$。 结果，我们得到 $\left|\sigma_{n}(x, f)-f(x)\right|<\frac{\varepsilon}{2}+\frac{\varepsilon}{2}=\varepsilon$。
## Теорема вейерштрасса
### 定义
我们将 $\sin$ 和 $\cos$ 的有限线性组合称为三角多项式，即
$$
T(x)=a_{0}+\sum_{k=1}^{n}\left(a_{k} \cos k x+b_{k} \sin k x\right) 。
$$
### 引理 (вейерштрасса)
令 $f(x) \in \mathrm{C}[-\pi, \pi]$ 和 $f(-\pi)=f(\pi)$。那么：
$$
\forall \varepsilon>0,~ \exists T(x): \forall x \in[-\pi, \pi] \Rightarrow|f(x)-T(x)|<\varepsilon .
$$
### 证明
遵循费耶定理，必须考虑到 $\sigma_{n}(x, f)$ 也是三角多项式。
$$
\forall \varepsilon>0,~ \exists n \in \mathbb{N}: \forall x \in[-\pi, \pi] \Rightarrow\left|\sigma_{n}(x, f)-f(x)\right|<\varepsilon .
$$
### 定理（关于用代数多项式逼近一个连续函数）
如果 $f \in C[a, b]$，那么
$$
\forall \varepsilon>0 \exists P(x): \forall x \in[a, b] \Rightarrow|P(x)-f(x)|<\varepsilon,
$$
其中 $P(x)$ 是代数多项式。
### 证明
令
$$t=\pi \frac{x-a}{b-a}$$
因此，我们制造映射 $[a, b] \rightarrow[0, \pi]$
那么 $$x=t \frac{b-a}{\pi}+a$$ 且有
$$
f(x)=f\left(t \frac{b-a}{\pi}+a\right)=\varphi(t)
$$ .
让我们将 $\varphi(t)$ 从 $[0, \pi]$ 均匀地扩展到 $[-\pi, \pi]$。 然后 $\varphi(-\pi)=\varphi(\pi)$ 被满足。 
因此，由前面的 Weierstrass 定理对 $\forall \varepsilon>0 $, $\exists T(t)-$ 三角多项式使得
$$
\forall t \in[-\pi, \pi] \Rightarrow|\varphi(t)-T(t)|<\frac{\varepsilon}{2} 。
$$
反过来，==三角多项式 $T(t)$ 可以通过泰勒级数 $Q_{n}(t)$ 的部分和来任意准确地近似==，它是一个代数多项式。令$\left|T(t)-Q_{n}(t)\right|<\frac{\varepsilon}{2}$，那么：
$$
\left|\varphi(t)-Q_{n}(t)\right| \leqslant|\varphi(t)-T(t)|+\left|T(t)-Q_{n}(t)\right|<\frac{\varepsilon}{2}+\frac{\varepsilon}{2}=\varepsilon
$$
由于$t=\pi \frac{x-a}{b-a}$，那么我们可以得到一个关于$x$的代数多项式：$Q_{n}(t)=Q_{n}\left(\pi \frac{ x-a}{b-a }\right)=P(x)$。
最后，返回到 $f(x)$，使用映射 $\varphi(t)\mapsto f(x)$，我们得到
$$
\forall \varepsilon>0, \quad \forall x \in[a, b], \exists P(x)-\text { алг. мн-н : }|f(x)-P(x)|<\varepsilon 。
$$
## Замкнутость тригонометрической системы
### теорема
三角函数系统在伪欧几里得空间 $L[-\pi,\pi]$ 中是封闭的，在欧几里得空间 $\widehat{C}[-\pi,\pi]$ 中更是如此。
（证明省略）