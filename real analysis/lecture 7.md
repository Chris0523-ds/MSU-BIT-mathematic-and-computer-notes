# lecture 7
## 1.封闭和完备系（замкнутые и полные системы）
### определение
伪欧几里得空间中的正交系 $\left\{\psi_{k}\right\}$ 被称为**封闭(замкнутой)** 的，如果对于这个空间的任意元素 $f$ 并且
$$
\forall \varepsilon>0, \exists~n \in \mathbb{N}, \exists~ c_{1}, \ldots, c_{n}:\left\|f-\sum_{k=1}^{n} c_ {k} \psi_{k}\right\|<\varepsilon
$$
==本质上是满足了第六课提到的贝塞尔恒等式的取等条件。下面会阐述。==
### определение
任意伪欧几里得空间中的正交系统 $\left\{\psi_{k}\right\}$ 称为**完备(полной)** 的，如果   $\forall k \in \mathbb{N} \Rightarrow f \perp \psi_{k}$ 意味着 $f \equiv 0$。即这个空间中与 $\left\{\psi_{k}\right\}$ 的所有元素正交的任何元素都必然为零。
### Теорема (Равенство парсеваля)
如果正交系统的伪欧几里得空间是**闭合(замкнутой)** 的，贝塞尔不等式
$$
\sum_{k=1}^{\infty} f_{k}^{2} \leqslant\|f\|^{2}
$$
可以转化为
$$
\sum_{k=1}^{\infty} f_{k}^{2}=\|f\|^{2},
$$
称为**Равенство парсеваля**。
### доказательство
固定任意 $\varepsilon>0$。然后，根据**封闭性(замкнутой)** 的定义和由于贝塞尔恒等式 $\exists n \in \mathbb{N}, \exists c_{1}, \ldots, c_{n}$ 的不等式：
$$
\|f\|^{2}-\sum_{k=1}^{n} f_{k}^{2} \leqslant\left\|f-\sum_{k=1}^{n} c_{ k} \psi_{k}\right\|^{2}<\varepsilon^{2}=\varepsilon^{\prime}
$$
但随后更多的 $\forall m \geqslant n$ 被满足
$$
\|f\|^{2}-\sum_{k=1}^{m} f_{k}^{2} \leqslant\left\|f-\sum_{k=1}^{n} c_{ k} \psi_{k}\right\|^{2}<\varepsilon^{\prime}
$$
此外，由于贝塞尔不等式$0 \leqslant\|f\|^{2}-\sum_{k=1}^{m} f_{k}^{2}$。
所以我们已经证明了
$$
\forall\varepsilon>0 ~\exists n \in \mathbb{N}: \forall m \geqslant n \Rightarrow 0 \leqslant\|f\|^{2}-\sum_{k=1}^{m} f_ {k}^{2}<\varepsilon^{\prime}
$$
这意味着$\|f\|^{2}=\sum_{k=1}^{\infty} f_{k}^{2}$。
### замечание
对于函数的三角系，贝塞尔恒等式采用以下形式
$$
\frac{a_{0}^{2}}{2}+\sum_{k=1}^{\infty}\left(a_{k}^{2}+b_{k}^{2}\right )=\frac{1}{\pi} \int_{-\pi}^{\pi} f^{2}(x) d x
$$
因为我们稍微改变了三角傅里叶级数的形式，所以这里出现了 $\pi$ 的除法。
### теорема
如果任意伪欧几里得空间 $\mathcal{L}$ 中的正交系统 $\left\{\psi_{k}\right\}$ 是闭合的，则 $\forall f \in \mathcal{L}$，傅里叶级数在 $\mathcal{L}$ 范数中收敛到 $f$，即
$$
\lim _{n \rightarrow \infty}\left\|f-\sum_{k=1}^{n} f_{k} \psi_{k}\right\|_{\mathcal{L}}=0
$$
### доказательство
我们使用贝塞尔恒等式。 将它传入 $n \rightarrow \infty$ 的极限，凭借 Parseval 等式，我们得到：
$$
\left\|f-\sum_{k=1}^{n} f_{k} \psi_{k}\right\|^{2}=\|f\|^{2}-\sum_{k= 1}^{n} f_{k}^{2} \underset{n \rightarrow \infty}{\longrightarrow} 0 。
$$
那么 $\left\|f-\sum_{k=1}^{n} f_{k} \psi_{k}\right\| \underset{n \rightarrow \infty}{\longrightarrow} 0$

在 $L[-\pi, \pi]$ 中满足：
$$
\left\|f-\sum_{k=1}^{n} f_{k} \psi_{k}\right\|_{L}=\sqrt{\int_{-\pi}^{\pi} \left(f(x)-\sum_{k=1}^{n} f_{k} \psi_{k}(x)\right)^{2} d x},
$$
因此，$L[-\pi,\pi]$ 范数中的收敛只不过是这个函数的傅里叶级数的平均收敛。

### теорема
在欧几里得空间 $\mathcal{L}$ 中，每个**封闭**正交系 $\left\{\psi_{k}\right\}$ 都是**完备的**。
==这里阐述了封闭和完备正交系之间的关系。==
### доказательство
考虑一个任意的 $f \in \mathcal{L}$。 设 $\forall k \in \mathbb{N} \Rightarrow f \perp \psi_{k}$，即 $\forall k \in \mathbb{N} \Rightarrow f_{k}=\left(f, \psi_{k}\right)=0$。 
由于系统的封闭性，贝塞尔恒等式是有效的，即 $\|f\|^{2}=\sum_{k=1}^{\infty} f_{k}^{2}=0$。 
那么欧几里得空间中的正定性意味着$f \equiv 0$。

### теорема
对于欧几里得空间 $\mathcal{L}$ 中的一个完备正交系，两个不同的元素 $f$ 和 $g$ 对于这个系统的所有数字不能具有相同的傅立叶系数。
### доказательство
令$\forall k \in \mathbb{N} \Rightarrow f_{k}=g_{k}$。 那么$(f-g)_{k}=0$，因此元素$(f-g)$与系统$\left\{\psi_{k}\right\}$的所有元素正交。 
然后从前面的定理得出 $(f-g) \equiv 0 \Leftrightarrow f \equiv g$。
## 2.封闭三角系及其性质
令 $f$ 为周期 $2 \pi$ 在 $\mathbb{R}$ 上可积的周期函数。
### лемма（равенство интеглалов от периодической функции）
对于 $f$，周期长度的任意段上的积分是恒定的，即
$$
\forall \alpha \in \mathbb{R} \Rightarrow \int_{-\pi-\alpha}^{\pi-\alpha} f(x) d x=\int_{-\pi}^{\pi} f (x) d x
$$
### Доказательство
$$
\begin{gathered}
\int_{-\pi-\alpha}^{\pi-\alpha} f(x) d x=\int_{-\pi-\alpha}^{-\pi} f(x) d x+\int_{-\pi}^{\pi} f(x) d x+\int_{\pi}^{\pi-\alpha} f(x) d x= \\
=\{t=x+2 \pi\}= \\
\int_{\pi-\alpha}^{\pi} \underbrace{f(t-2 \pi)}_{=f(t)} d t+\int_{-\pi}^{\pi} f(x) d x+\int_{\pi}^{\pi-\alpha} f(x) d x=\int_{-\pi}^{\pi} f(x) d x .
\end{gathered}
$$

让 $f$ 的周期为 $2 \pi$。 回想一下三角傅里叶级数
$$
S_{n}(x, f)=\frac{a_{0}}{2}+\sum_{k=1}^{n}\left(a_{k} \cos k x+b_{k} \sin k x\right)
$$
### утверждение
以下恒等式可以满足：
$$
S_{n}(x, f)=\frac{1}{\pi} \int_{-\pi}^{\pi} f(x+t) \underbrace{\frac{\sin \left(n+\frac{1}{2}\right) t}{2 \sin \frac{t}{2}}}_{\text {Ядро Дирихле }} d t .
$$
### определение 
我们将三角傅里叶级数的 Cesar 均值称为表达式：
$$
\sigma_{n}(x, f)=\frac{S_{0}(x, f)+S_{1}(x, f)+\cdots+S_{n-1}(x, f)}{n}
$$
### утверждение
以下恒等式可以满足：

$$
\sigma_{n}(x, f)=\frac{1}{n \pi} \int_{-\pi}^{\pi} f(x+t) \cdot \underbrace{\frac{\sin ^{2} \frac{t n}{2}}{2 \sin ^{2} \frac{t}{2}}}_{\text {Ядро Фейера }} d t .
$$