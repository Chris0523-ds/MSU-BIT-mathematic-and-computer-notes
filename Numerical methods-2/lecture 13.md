### 2.8.1 赛德尔法
回想一下，对于线性代数方程组 $A x=f$，塞德尔方法的形式为 $L y_{n+1}+D y_{n+1}+R y_{n}=f$。 这里矩阵 $A$ 表示为左三角矩阵、对角矩阵和右三角矩阵的和 $A=L+D+R$，$n$ 是迭代次数。
模型问题（2.3）的 Seidel 方法的实现形式为
$$
\begin{aligned}
&\frac{y_{i-1 j}^{n+1}-2 y_{i j}^{n+1}+y_{i+1 j}^{n}}{h^{2}}+\frac{y_{i j-1}^{n+1}-2 y_{i j}^{n+1}+y_{i j+1}^{n}}{h^{2}}=-f_{i j} ; \\
&\left.y_{i j}^{n+1}\right|_{\gamma_{h}}=0 .
\end{aligned}
$$
### замечание
尽管塞德尔法是隐式迭代法，但在新的迭代中求值并不难，因为它归结为对三角矩阵求逆。可以按以下索引更改顺序执行计算：$(1,1),(1,2), \ldots,(1, N-1),(2,1),(2,2), \ldots ,(2 , N-$ $1), \ldots,(N-1,1),(N-1,2), \ldots,(N-1, N-1)$。那么方程中只有$y_{i j}^{(n+1)}$的值是未知的。带有索引 $(n+1)$ 的剩余值要么是从边界条件中知道的，要么会更早地计算出来。

我们将方法带入规范形式。 为此，方便首先考虑该方法的一维模拟
$$
\frac{y_{i-1}^{(n+1)}-2 y_{i}^{(n+1)}+y_{i+1}^{(n)}}{h^{2 }}=-f_{i} ; y_{0}^{(n+1)}=y_{N}^{(n+1)}=0
$$

我们将方程改写为
$$
y_{\bar{x} x, i}^{(n)}+\frac{y_{i-1}^{(n+1)}-y_{i-1}^{(n)}-2 y_{i}^{(n+1)}+y_{i+1}^{(n)}}{h^{2}}=-f_{i} 。
$$

引入算子
$$
\begin{aligned}
&A^{(1)} y_{i}=-y_{\bar{x} x, i} \\
&R^{(1)} y_{i}=\frac{1}{h} y_{\bar{x}, i} ; i=1,2, \ldots, N-1 \\
&y_{0}=y_{N}=0
\end{aligned}
$$

将方法写成如下形式
$$
\left(\frac{1}{h^{2}} E+R^{(1)}\right)\left(y_{n+1}-y_{n}\right)+A^{(1 )} y_{n}=f
$$
同样，对于模型问题，Seidel 方法采用以下形式
$$
\begin{aligned}
B & \frac{y_{n+1}-y_{n}}{\tau}+A y_{n}=f \\
A &=-\Delta_{h}, \\
B &=\frac{2}{h^{2}} E+R, \\
\tau &=1 \\
R y_{i j} &=\frac{1}{h}\left(y_{\bar{x}_{1}}+y_{\bar{x}_{2}}\right)_{i j}, x_{i j} \in \omega_{h} ; \\
\left.y_{i j}\right|_{\gamma_{h}} &=0 .
\end{aligned}
$$
由此可得（例如，参见 [2]），为达到 Seidel 方法的给定精度 $\varepsilon$ 所需的迭代次数
$$
n_{0}(\varepsilon) \approx \frac{\ln (1 / \varepsilon)}{\pi^{2} h^{2}}=O\left(h^{-2}\right)
$$
这个迭代次数大概是雅可比方法的两倍；但是，收敛速度仍然很低。
### 2.8.2 交替三角迭代法
### 2.8.3 代数理论
众所周知，平稳迭代法被简化为形式：
$$
B \frac{y_{n+1}-y_{n}}{\tau}+A y_{n}=f,
$$
之后研究了它们的收敛性。可以优化它的结构，即通过运算符 $B$ 的特殊选择来构造一个新方法。

进一步，我们假设算子$A$是自伴随且正定的，即$A^{*}=A>0$，或者，同样的，方程组 $(2.4)$ 的矩阵$Ay=f$ 是对称的正定矩阵。让我们介绍一个线性算子$R$，它的矩阵形式为：
$$
R=\left[r_{i j}\right] ; r_{i j}=\left\{\begin{array}{l}
a_{i j}, i>j \\
0.5 a_{i j}, i=j ; \quad i, j=1,2, \ldots, m \\
0, i<j
\end{array}\right.
$$
矩阵 $R$ 是一个下三角矩阵，由它转置而来的上三角矩阵 $R^{T}$ 与 $R$ 相伴随的算子 $R^{*}$ 的矩阵。 让我们将算子 $A$ 表示为 $A=R+R^{*}$ 的形式，那么：
$$
0<(A v, v)=\left(\left(R+R^{*}\right) v, v\right)=2(R v, v) \forall v \in H, v \neq 0, R, R^{*}>0
$$
对于交替三角迭代法，算子 $B$ 被定义为乘积：
$$
B=\left(E+\omega R^{*}\right)(E+\omega R)
$$
其中 $E$ 是单位算子，$\omega>0$ 是数字参数。 那么算子的选择由以下情况决定：

1.使用中间值 $y_{n+1 / 2}$，其中
$$
\left(E+\omega R^{*}\right)(E+\omega R) y_{n+1}=(B-\tau A) y_{n}+\tau f,
$$
新迭代的解决方案很容易通过两个步骤找到：
$\left(E+\omega R^{*}\right) y_{n+1 / 2}=\varphi_{n}=(B-\tau A) y_{n}+\tau f-$ 上三角矩阵系； 
$(E+\omega R) y_{n+1}=y_{n+1 / 2}-$ 下三角矩阵系。

2. $B^{*}=B>0$，因为
$$
\begin{gathered}
B=\left(E+\omega R^{*}\right)(E+\omega R)=E+\omega A+\omega^{2} R^{*} R \Rightarrow B^{*}=B, \\
(B v, v)=((E+\omega R) v,(E+\omega R) v)>0 \Rightarrow B>0,
\end{gathered}
$$

因此，我们可以使用先前获得的收敛估计。

### 引理 2.8.1 
假设存在正数 $\delta$ 和 $\Delta$， 使得满足算子不等式 $A \geq \delta E, 4 R^{*} R \leq \Delta A$ 。 那么算子 $A=R+R^{*} u(\omega)=$ $\left(E+\omega R^{*}\right)(E+\omega R)$ 满足不等式
$$
\gamma_{1} B \leq A \leq \gamma_{2} B
$$
其中：
$$
\gamma_{1}=\left(\frac{1}{\delta}+\omega+\frac{\omega^{2} \Delta}{4}\right)^{-1}, \gamma_{2} =\frac{1}{2 \omega}
$$
### 证明
$$
\begin{gathered}
B(\omega)=E+\omega A+\omega^{2} R^{*} R \leq\left(\frac{1}{\delta}+\omega+\frac{\omega^{2} \Delta}{4}\right) A \\
B(\omega)-B(-\omega)=2 \omega A \Rightarrow B(\omega) \geq 2 \omega A
\end{gathered}
$$
因为 $B(-\omega) \geq 0$。
==（证毕）==
上述引理表明可以把找到常数 $\gamma_{1}$ 和 $\gamma_{2}$ 简化为找到常数 $\delta$ 和 $\Delta$。如果不等式 $A \geq \delta E, 4 R^{*} R \leq \Delta A$ 成立，对于任意 $v \in$ $H, v \neq 0$ 我们有：
$$
\begin{gathered}
\delta\|v\|^{2} \leq(A v, v)=\frac{(A v, v)^{2}}{(A v, v)}=\frac{4(R v, v)^{2}}{(A v, v)} \leq \frac{4\|R v\|^{2}\|v\|^{2}}{(A v, v)}= \\
\frac{4\left(R^{*} R v, v\right)^{2}\|v\|^{2}}{(A v, v)} \leq \frac{\Delta(A v, v)\|v\|^{2}}{(A v, v)}=\Delta\|v\|^{2} .
\end{gathered}
$$

这意味着 $\delta \leq \Delta$。作为常数$\delta$，可以取算子$A$ 的最小特征值$\lambda_{\min }(A)$。此外可以注意到，既然 $(A v, v) \leq \Delta\|v\|^{2}$, $\Delta \geq \lambda_{\max }(A)$被满足。其中 $\lambda_{ \max } (A)$是算子 $A$ 的最大特征值。


### 定理 2.8.1 
假设 $A=R+R^{*}$，且存在为正的常数 $\delta$ 和 $\Delta$,对该常数满足不等式 $A \geq \delta E, 4 R^{*} R \leq \Delta $。 令
$$
\omega=\frac{2}{\sqrt{\delta \Delta}}, \tau=\frac{2}{\gamma_{1}+\gamma_{2}},
$$

其中
$$
\gamma_{1}=\frac{\delta}{2(1+\sqrt{\xi})}, \gamma_{2}=\frac{\delta}{4 \sqrt{\xi}}, \xi=\frac{\delta}{\Delta} .
$$

那么必有交替三角形迭代法收敛，且其误差估计满足：
$$
\left\|y_{n}-y\right\|_{A} \leq \rho^{n}\left\|y_{0}-y\right\|_{A},
$$
其中
$$
\rho=\frac{1-\sqrt{\xi}}{1+3 \sqrt{\xi}}
$$
（证明略）