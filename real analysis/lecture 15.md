## 多重傅里叶级数（Kратные ряды Фурье）
我们将自己限制在两个变量的情况下。 假设在平面 $\mathbb{R}^{2}$ 上给出一个函数 $f(x ; y)$。 我们假设它在变量 $x$ 和 $y$ 中都有一个等于 $2\pi$ 的周期，并且在平面 $\mathbf{Q}=[-\ π; \pi]\times[-\pi; \pi]$上。
将函数 $f(x ; y)$ 视为关于 $x$ 的函数，我们得到：
$$
f(x ; y) \sim \sum_{n=-\infty}^{+\infty} c_{n}(y) e^{i n x}, \text { 其中 } c_{n}(y)=\frac{1}{2 \pi} \int_{-\pi}^{\pi} f(\xi ; y) e^{-i n \xi}d \xi
$$
反过来，函数 $c_{n}(y)$ 可以扩展为级数形式：
$$
\begin{gathered}
c_{n}(y) \sim \sum_{m=-\infty}^{+\infty} c_{n, m} e^{i m y}, \text { где } \\
c_{n, m}=\frac{1}{2 \pi} \int_{-\pi}^{\pi} c_{n}(\eta) e^{-i m \eta} d \eta=\frac{1}{4 \pi^{2}} \int_{-\pi}^{\pi} \int_{-\pi}^{\pi} f(\xi ; \eta) e^{-i(n \xi+m \eta)} d \xi d \eta .
\end{gathered}
$$
由此能得到形式：
$$
f(x ; y) \sim \sum_{n=-\infty}^{+\infty}\left(\sum_{m=-\infty}^{+\infty} c_{n, m} e^{ i m y}\right) e^{i n x}=\sum_{n, m=-\infty}^{+\infty} c_{n, m} e^{i(n x+m y)}
$$