## 2.7 平稳迭代法的应用
### 2.7.1 雅可比法 (Метод Якоби)
回想一下，对于线性代数方程组 $A x=f$，雅可比法具有 $L y_{n}+D y_{n+1}+R y_{n}=f$ 的形式。 这里矩阵 $A$ 表示为左三角矩阵、对角矩阵和右三角矩阵的和，其迭代次数为第 $n$ 次。
让我们展示雅可比迭代方法如何应用于模型问题$(2.3)$，在前面的内容中，其性质已经被讨论：
$$
\left\{\begin{array}{l}
\frac{y_{i-1 j}-2 y_{i j}+y_{i+1 j}}{h^{2}}+\frac{y_{i j-1}-2 y_{i j}+y_{i j+1}}{h^{2}}=-f_{i j} \\
y_{i 0}=y_{i N}=y_{0 j}=y_{N j}=0 \\
i, j=1,2, \ldots, N-1 ; h N=1
\end{array}\right.
$$
该问题的雅可比法的实现形式为
$$
\left\{\begin{array}{l}
\frac{y_{i-1 j}^{n}-2 y_{i j}^{n+1}+y_{i+1 j}^{n}}{h^{2}}+\frac{y_{i j-1}^{n}-2 y_{i j}^{n+1}+y_{i j+1}^{n}}{h^{2}}=-f_{i j}, i, j=1,2, \ldots, N \\
\left.y_{i j}\right|_{\gamma_{h}}=0 .
\end{array}\right.
$$
为了进行计算，不需要以显式的形式写出矩阵 $A$ 并将其存储在计算机的内存中，因为明确找到了新迭代的近似解：
$$
y_{i j}^{n+1}=\frac{1}{4}\left(y_{i-1 j}+y_{i+1 j}+y_{i j-1}+y_{i j + 1}\right)+\frac{h^{2}}{4} f_{i j}
$$
接下来以规范形式 $(2.6)$ 编写该方法。为表示 $y_{n}=\left\{y_{i j}^{(n)}\right\}_{i, j=1}^{N}$，我们将恒等式 $y_{n+1}=y_{n}+\left(y_{n+1}-y_{n}\right)$ 代入方程。得到
$$
\frac{y_{n+1}-y_{n}}{\tau}+A y_{n}=f, \tau=\frac{h^{2}}{4} 。
$$
这里 $A=-\Delta_{h}, \Delta_{h}=\left(y_{\bar{x}_{1} x_{1}}+y_{\bar{x}_{2} x_{ 2}}\right)_{i j}$ 是五点差拉普拉斯算子。到此为止，差分算子 $A$ 的性质已经被详细讨论了。特别注意当 $A^{*}=A>0$ 时，该算子的最小和最大特征值为：
$$
\begin{aligned}
&\gamma_{1}=\lambda_{\min }(A)=\frac{8}{h^{2}} \sin ^{2} \frac{\pi h}{2} \\
&\gamma_{2}=\lambda_{\max }(A)=\frac{8}{h^{2}} \cos ^{2} \frac{\pi h}{2}
\end{aligned}
$$
因为从中得到 $\tau=\frac{h^{2}}{4}=2 /\left(\gamma_{1}+\gamma_{2}\right)$，即意味着雅可比法是一种具有最优迭代参数的简单迭代法。 那么根据定理 $(2.6.1)$ 的推论，误差$z_{n}=$$y_{n}-y$满足估计
$$
\left\|z_{n}\right\| \leq \rho^{n}|| z_{0} \|,
$$
其中
$$
\rho=\frac{1-\xi}{1+\xi}, \xi=\frac{\gamma_{1}}{\gamma_{2}}=\operatorname{tg}^{2} \frac{ \pi h}{2} 。
$$
那么收敛速度是：
$$
\ln \frac{1}{\rho}=\ln \left(1+\frac{2 \xi}{1-\xi}\right) \approx \frac{\pi^{2} h^{2}}{2}
$$
以及达到给定精度 $\varepsilon$ 所需的迭代次数：
$$
n_{0}(\varepsilon) \approx \frac{2 \ln (1 / \varepsilon)}{\pi^{2} h^{2}}=O\left(h^{-2}\right) .
$$
从最后的估计可以看出，雅可比法虽然是最简单的，但收敛速度极慢。 目前有些方法需要 $O\left(h^{-1}\right)$ 甚至 $O\left(\ln h^{-1}\right)$ 迭代才能达到相同的精度。