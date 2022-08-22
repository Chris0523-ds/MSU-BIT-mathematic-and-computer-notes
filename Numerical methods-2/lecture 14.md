### 2.8.4 模型问题的应用
让我们讨论交替三角形迭代法在模型问题$(2.3)$中的应用。
$$
\begin{aligned}
&-\Delta_{h} y_{i j}=f_{i j}, x_{i j} \in \omega_{h} \\
&\left.y\right|_{\gamma_{h}}=0
\end{aligned}
$$

和前面一样，我们将考虑这个差分问题的算子 $A=-\Delta_{h}$ 作用于空间 $H=\left\{y\left(x_{i j}\right) ； x_{i j} \in \Omega_{h},\left.y\right|_{\gamma_{h}}=0\right\}$。其带有标量积：
$$
(y, v)=\sum_{i, j=1}^{N-1} y_{i j} v_{i j} h^{2}
$$
回想一下前面显示的 $A^{*}=A>0$。
为了应用交替三角迭代法，需要将算子表示为 $A=R+R^{*}$ 的形式，其中 $R$ 是具有下三角矩阵的算子，并找到常数$\delta, \Delta$，确定方法参数。
我们以形式表示运算符 $A$
$$
A y_{i j}=\frac{1}{h}\left(y_{\bar{x}_{1}}+y_{\bar{x}_{2}}\right)_{i j}- \frac{1}{h}\left(y_{x_{1}}+y_{x_{2}}\right)_{i j} 。
$$
那么引入算子：
$$
\begin{aligned}
&R y_{i j}=\frac{1}{h}\left(y_{\bar{x}_{1}}+y_{\bar{x}_{2}}\right)_{i j} \\
&U y_{i j}=-\frac{1}{h}\left(y_{x_{1}}+y_{x_{2}}\right)_{i j}, x_{i j} \in \omega_{h} \\
&\left.y\right|_{\gamma_{h}}=0
\end{aligned}
$$

得到$A=R+U$，其中 $R$ 和 $U$ 分别是具有下三角矩阵和上三角矩阵的算子 (例如，当引入连续编号的网格节点$\Omega_{h}$时，以自然顺序逐列或逐行排列)。
### 引理 2.8.2
算子 $U$ 与算子 $R$ 是共轭的。
### 证明（略）
因此，获得了所需的表示 $A=R+R^{\star}$。剩下的就是确定常数 $\delta$ 和 $\Delta$。如前所述，作为常数 $\delta$，可以取运算符 $A$ 的最小特征值，即
$$
\delta=\lambda_{\min }(A)=\frac{8}{h^{2}} \sin ^{2} \frac{\pi h}{2} 。
$$
求 $\Delta$，使得
$$
\left.4 R^{*} R \leq \Delta A \Rightarrow 4\left(R^{*} R y, y\right) \leq \Delta(A y, y)\right) \Rightarrow 4\ |R y\|^{2} \leq \Delta(A y, y) 。
$$
前面已经表明(参见引理 2.2.2):
$$
(A y, y)=\sum_{i=1}^{N} \sum_{j=1}^{N-1} y_{\bar{x}_{1}, i j}^{2} h ^{2}+\sum_{i=1}^{N-1} \sum_{j=1}^{N} y_{\bar{x}_{2}, i j}^{2} h^{ 2} 。
$$
另一方面，由算子$R$ 的定义可以得到：
$$
\|R y\|^{2}=\frac{1}{h^{2}} \sum_{i, j=1}^{N-1}\left(y_{\bar{x}_{ 1}}+y_{\bar{x}_{2}}\right)_{i j}^{2} h^{2} \leq \frac{2}{h^{2}} \sum_{i , j=1}^{N-1}\left(y_{\bar{x}_{1}}^{2}+y_{\bar{x}_{2}}^{2}\right) _{i j} h^{2} \leq \frac{2}{h^{2}}(A y, y) 。
$$
其中
$$
\Delta=\frac{8}{h^{2}}>\lambda_{\max }(A)=\frac{8}{h^{2}} \cos ^{2} \frac{\pi h }{2}
$$
通过定理$ 2.8 .1 $，选择该方法的参数
$$
\omega=\frac{2}{\sqrt{\delta \Delta}}, \tau=\frac{2}{\gamma_{1}+\gamma_{2}},
$$

其中
$$
\gamma_{1}=\frac{\delta}{2(1+\sqrt{\xi})}, \quad \gamma_{2}=\frac{\delta}{4 \sqrt{\xi}}, \quad \xi=\frac{\delta}{\Delta}=\sin ^{2} \frac{\pi h}{2},
$$

其满足常数的误差估计：
$$
\rho=\frac{1-\sqrt{\xi}}{1+3 \sqrt{\xi}}=\frac{1-\sin \frac{\pi h}{2}}{1+3 \ sin \frac{\pi h}{2}} \approx\left(1-\frac{\pi h}{2}\right)\left(1-3 \frac{\pi h}{2}\right ) \ 约 1-2 \pi h 。
$$
因此达到给定精度所需的最小迭代次数 $\varepsilon$，
$$
n_{0}(\varepsilon)=\frac{\ln (1 / \varepsilon)}{(1 / \rho)} \approx \frac{\ln (1 / \varepsilon)}{-\ln (1-2 \pi h)} \approx \frac{\ln (1 / \varepsilon)}{2 \pi h}=O\left(h^{-1}\right)
$$
### замечание 
回想一下雅可比和塞德尔方法，小 $h$ 的迭代次数估计为 $O\left(h^{-2}\right)$。 也就是说，交替三角形迭代方法提供了一个数量级的更快收敛。

接下来，我们描述在新的迭代中寻找值 $y_{i j}^{(n+1)}$的算法。 回想一下，迭代分两个阶段进行。
$$
\begin{aligned}
&\left(E+\omega R^{*}\right) y_{n+1 / 2}=\varphi_{n} \\
&(E+\omega R) y_{n+1}=y_{n+1 / 2}
\end{aligned}
$$
其中 $\varphi_{n}=(B-\tau A) y_{n}+\tau f$。考虑到算子 $R$ 和 $R^{*}$ 的定义，方程采用的索引形式为：
$$
\begin{aligned}
&y_{i j}^{(n+1 / 2)}-\frac{\omega}{h}\left(y_{x_{1}}+y_{x_{2}}\right)_{i j}^{(n+1 / 2)}=\varphi_{i j}^{(n)} \\
&y_{i j}^{(n+1)}+\frac{\omega}{h}\left(y_{\bar{x}_{1}}+y_{\bar{x}_{2}}\right)_{i j}^{(n+1)}=y_{i j}^{(n+1 / 2)}
\end{aligned}
$$
因此，在第一阶段，方程组被求解为：
$$
\left\{\begin{array}{l}
\left(1+\frac{2 \omega}{h^{2}}\right) y_{i j}^{(n+1 / 2)}=\frac{\omega}{h^{2}}\left(y_{i+1 j}^{(n+1 / 2)}+y_{i j+1}^{(n+1 / 2)}\right)+\varphi_{i j}^{(n)} \\
y_{N j}^{(n+1 / 2)}=y_{i N}^{(n+1 / 2)} ; i, j=1,2, \ldots, N-1
\end{array}\right.
$$
第二阶段——方程组
$$
\left\{\begin{array}{l}
\left(1+\frac{2 \omega}{h^{2}}\right) y_{i j}^{(n+1)}=\frac{\omega}{h^{2}}\left(y_{i+1 j}^{(n+1)}+y_{i j+1}^{(n+1)}\right)+y_{i j}^{(n+1 / 2)} \\
y_{0 j}^{(n+1)}=y_{i 0}^{(n+1)} ; i, j=1,2, \ldots, N-1 .
\end{array}\right.
$$
由于两个矩阵系在相应的网格节点 $\Omega_{h}$ 的连续枚举下都是三角的，因此很容易找到系统的解。为了解决第一个系统，可以按照以下更改索引的顺序进行计算：$(N-1, N-1),(N-1, N-2), \ldots,(N-$ $1,1 ),(N-2 , N-1),(N-2, N-2), \ldots,(N-2,1), \ldots,(1,1)$。那么方程中只有 $y_{i j}^{(n+1 / 2)}$ 的值是未知的。带有索引 $(n+1 / 2)$ 的剩余值要么是从边界条件中知道的，要么会更早地计算出来。为了解决第二个系统，计算以索引更改的相反顺序进行：$(1,1),(1,2), \ldots,(1, N-1),(2,1),( 2,2), \ldots,(2, N-1), \ldots,(N-$$1, N-1)$。

### 2.8.5 带切比雪夫迭代参数的交替三角法
如前所述，迭代方法的收敛速度可以通过使用取决于迭代次数的可变迭代参数$\tau=\tau_{n}$来提高。 对于固定迭代次数为 $n$ 的情况，可以指定一组迭代参数$\tau_{1}、\tau_{2}、\ldots、\tau_{n}$，提供对收敛速度的最佳估计，不管初始近似值的选择。
### 引理 2.8.3 
函数 $T_{n}(x)=\cos (n \arccos z)$，其中$z-$是复变量，对于 $n=1,2，\ldots,n$ 是对于 $z^{n}$ 系数为 $2^{n-1}$ 的 $n$ 阶多项式，其具有实零：
$$
Z_{i}=\cos \frac{(2 l-1) \pi}{2 n} ; l=1,2, \ldots, n
$$
### 定义
函数 $T_{n}(z)$ 称为**切比雪夫多项式**。
评论。对于实数 $x$，多项式 $T_{n}(x)=\cos (n \arccos x)$ 被定义在 $|x| \leq 1 $。对于所有 $x$，多项式 $T_{n}(x)$ 可以在 $n=1,2, \ldots$ 上由递归公式 $T_{n+1}(x)=2xT_{n}(x)-T_{n-1}( x)$定义，其中 $T_{0}(x)=1，T_{1}(x)=x$。
此外，由于任何复数的恒等式
$$
\cos (n \arccos z)=0.5\left(\left(z-\sqrt{z^{2}-1}\right)^{n}+\left(z+\sqrt{z^{2}-1}\right)^{n}\right)
$$
可以为 $|x|\geq 1$ 给出 $T_{n}(x)$ 的显式表达式。
接下来，多项式 $T_{n}(x)$ 最重要的性质如下。在所有前导系数等于 $2^{n-1}$ 的 $n$ 次多项式中，值 $\max _{-1 \leq x \leq 1}\left|T_{n}(x)\right |$ 是最小的（例如，参见 [4]）。
### 定理 2.8.2 
令$A^{\star}=A>0, B^{\star}=B>0, \gamma_{1} B \leq A \leq \gamma_{2} B$, 其中$\gamma_{2} >\gamma_{1}>0$。 那么对于给定的迭代次数 $n$ 和以下的参数选择：
$$
\tau_{k}=\frac{\tau_{0}}{1+\rho_{0} t_{k}}, T_{k}=\cos \frac{(2 k-1) \pi}{2 n} ; k=1,2, \ldots, n ; \text { ддe }
$$

$$
\tau_{0}=\frac{2}{\gamma_{1}+\gamma_{2}}, \rho_{0}=\frac{1-\eta}{1+\eta}, \eta=\frac{\gamma_{1}}{\gamma_{2}} ;
$$
对于达到给定精度 $\varepsilon$ 所需的最小迭代次数 $n_{0}(\varepsilon)$，该方法
$$
B \frac{y_{k+1}-y_{k}}{\tau_{k+1}}+A y_{k}=f ; \quad k=0,1, \ldots, n-1 ;
$$
对于小的 $\eta$，满足近似估计
$$
n_{0}(\varepsilon) \approx \frac{\ln (2 / \varepsilon)}{2 \sqrt{\eta}} 。
$$

迭代次数 $n_{0}(\varepsilon)$ 的估计不依赖于应用迭代参数 $\tau_{k}$ 的阶数，但是，这个阶数显着影响计算稳定性。 在该方法的实际应用中，使用了一种特殊的构造迭代参数有序集的算法（见[7]），保证了计算的稳定性。
让我们使用这个定理来估计模型问题的具有切比雪夫迭代参数的交替三角法的迭代次数。 在这种情况下：
$$
\begin{gathered}
A=R+R^{\star}, B=\left(E+\omega R^{\star}\right)(E+\omega R), \omega=\frac{2}{\sqrt{\delta \Delta}} \\
\gamma_{1}=\frac{\delta}{2(1+\sqrt{\xi})}, \gamma_{2}=\frac{\delta}{3 \sqrt{\xi}}, \xi=\frac{\delta}{\Delta}, \delta=\frac{8}{h^{2}} \sin ^{2} \frac{\pi h}{2}, \Delta=\frac{8}{h^{2}} .
\end{gathered}
$$
这样，
$$
\eta=\frac{2 \sqrt{\xi}}{1+\sqrt{\xi}}=\frac{2 \sin (\pi h / 2)}{1+\sin (\pi h / 2)} \approx \pi h
$$
并且迭代次数 $n_{0}(\varepsilon)$ 满足近似估计
$$
n_{0}(\varepsilon) \approx \frac{\ln (2 / \varepsilon)}{2 \sqrt{\pi h}}=O\left(h^{-1 / 2}\right) 。
$$
总之，我们提出了对所考虑的迭代方法达到给定精度 $\varepsilon$ 所需的最小迭代次数 $n_{0}(\varepsilon)$ 的近似（对于 $h \rightarrow 0$ ）估计：
$n_{0}(\varepsilon) \approx \frac{2}{\pi^{2} h^{2}} \ln \frac{1}{\varepsilon}-$ 用于 Jacobi 方法；
$n_{0}(\varepsilon) \approx \frac{1}{\pi^{2} h^{2}} \ln \frac{1}{\varepsilon}-$ 用于 Seidel 方法；
$n_{0}(\varepsilon) \approx \frac{1}{2 \pi h} \ln \frac{1}{\varepsilon}-$ 用于 PTIM；
$n_{0}(\varepsilon) \approx \frac{}{2 \sqrt{\pi h}} \ln \frac{2}{\varepsilon}-$ 用于带有切比雪夫参数的 PTIM。

这里，缩写PTIM是交替三角迭代法的缩写。