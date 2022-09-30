# lecture 6
## 线性空间理论
在本节中，我们将去年引入的内积、范数等概念以及一些不等式推广到函数和无限空间的情况。
### 定义
一个线性空间 $\mathcal{L}$ 称为欧几里得空间，如果 $\forall f, g \in L$ 存在一个映射（称为内积）$(f, g): \mathcal{L} \times \mathcal{L} \mapsto$ 满足条件：
(1) 对称性：$\forall f, g \in \mathcal{L} \Rightarrow(f, g)=(g, f)$。
(2) 线性：$\forall f, g \in \mathcal{L}, \forall \alpha, \beta \in \Rightarrow(\alpha f \pm \beta g, h)=\alpha(f, h) \pm\beta(g, h)$。
(3) 正定性：$\forall f \in \mathcal{L} \Rightarrow(f, f) \geqslant 0$, 且 $(f, f)=0 \Leftrightarrow f \equiv 0 .$
### 定义
线性空间 $\mathcal{L}$ 称为**伪欧几里得空间**，如果可以在其上引入满足条件 1 和 2 的内积，但 $(f, f)=0$ 的情况对于非零元素也出现。
### 推论
任何欧几里得空间都是伪欧几里得空间，任何在伪欧几里得空间中为真的陈述在欧几里得空间中也为真。
#### 示例 1 .
$\widehat{C}[a, b]$ 是在 $[a, b]$ 上的分段连续函数空间，在点 $x_{1}, x_{2}\ldots , x_{n} \in[a, b]$ 处具有有限数量的第一类不连续点,。 在这些点上，我们将函数的值定义为
$$
f\left(x_{i}\right)=\frac{f\left(x_{i}-0\right)+f\left(x_{i}+0\right)}{2}
$$
我们引入标量积如下：
$$
(f, g)_{\widehat{\mathcal{C}}}=\int_{a}^{b} f(x) g(x) d x 。
$$
让我们证明具有这种内积的给定空间是欧几里得空间。
(1)对称性：
$$
(f, g)_{\widehat{\mathcal{C}}}=(g, f)_{\widehat{\mathcal{C}}}, ~\text{因为} \int_{a}^{b} f(x) g(x) d x=\int_{a}^{b} g(x) f(x) d x \text {. }
$$
(2) 线性：
$$
\begin{aligned}
&(\alpha f \pm \beta g, h)_{\widehat{\mathcal{C}}}=\int_{a}^{b}(\alpha f(x) \pm \beta g(x)) h(x) d x= \\
&=\alpha \int_{a}^{b} f(x) h(x) d x \pm \beta \int_{a}^{b} g(x) h(x) d x=\alpha(f, h)_{\hat{\mathrm{C}}} \pm \beta(g, h)_{\widehat{\mathcal{C}}} .
\end{aligned}
$$
(3) 正定性：
$$(f, f)_{\widehat{\mathcal{c}}}=\int_{a}^{b} f^{2}(x) d x \geqslant 0$$ 注意 $( f , f)_{\widehat{\mathcal{C}}}=0 \Leftrightarrow f \equiv 0$。
实际上，段 $[a, b]$ 被点 $x_{1}, \ldots, x_{n}$ 分成 $n+1$ 个段，函数 $f$ 在这些点上是连续的，如果为两端的值，则分别取左右界限的值。
在去年的课程中，我们证明了如果 $f(x) \in C[a, b]$ 且 $f(x) \geqslant 0$ 在 $[a, b]$ 上，且 $\exists x_{0 } \in[a, b]: f\left(x_{0}\right)>0$，则：
$$
\int_{a}^{b} f(x) d x>0
$$ 
那么 
$$\int_{x_{i-1}}^{x_{i}} f^{2}(x) d x=0 \Leftrightarrow f(x) \equiv 0 ~в~ \left[x_{i-1 }, x_{i}\right]
$$
那么满足
$$
f\left(x_{i}-0\right)=f\left(x_{i}+0\right)=0 \Rightarrow f\left(x_{i}\right)=0
$$
即有：
$$
\int_{a}^{b} f^{2}(x) d x=0 \Leftrightarrow f(x) \equiv 0~ в ~[a, b] .
$$

#### 示例 2.
伪欧几里得空间的一个例子是段 $[a, b]$ 上黎曼可积函数的空间 $L[a, b]$。 
事实上，前 2 个性质的证明类似；但属性 3 不满足。 
举个例子，考虑一个函数，它除了在一个点等于 1 之外，处处等于 0。这样一个函数（及其平方）的积分等于 0，尽管函数本身并不完全等于$[a, b]$ 上的 0 。

### 定义
如果 $\forall n \in \mathbb{N}$ 在空间 $\mathcal{L}$ 上有 $n$ 个线性无关元素，则称空间 $\mathcal{L}$ 是**无限维**的。
### 陈述（Cauchy-Bunyakovsky 不等式）
$\forall f, g$ 可以满足：
$$
(f, g)^{2} \leqslant(f, f) \cdot(g, g)
$$

### 定义
线性空间 $\mathcal{L}$ 称为赋范空间，如果 $\forall f \in \mathcal{L}$ 映射（称为范数）$\|f\|_{\mathcal{L}}: \mathcal{L} \mapsto \mathbb{R}$ 满足条件：
(1) 三角不等式：$\forall f, g \in \mathcal{L} \Rightarrow\|f+g\| \leqslant\|f\|+\|g\|$。
(2) $\forall f \in \mathcal{L}, \forall \alpha \in \Rightarrow\|f\|=|\alpha| \cdot\|f\|$。
(3) $\forall f \in \mathcal{L} \Rightarrow\|f\| \geqslant 0$，若 $\|f\|=0 \Leftrightarrow f \equiv 0$。
### 定义
线性空间 $L$ 称为**伪赋范空间**，若$\forall f \in \mathcal{L}$ 范数满足公理 1 和 2 ，但 $\|f\|=0$ 可能出现情况 $f \neq 0$。

### 引理 1
通过为 $\forall f$ 设置 $\|f\|=\sqrt{(f, f)}$，任何欧几里得（伪欧几里得）空间都可以被赋范化(伪赋范化)。
#### 证明：
非常显然，赋范空间公理3由内积空间公理3生成。
同时公理2也是正确的：
$$
\|\alpha \cdot f\|=\sqrt{(\alpha f, \alpha f)}=|\alpha| \sqrt{(f, f)}=|\alpha| \cdot\|f\|
$$
对于三角不等式，我们有：
$$
\begin{aligned}
&\|f+g\|=\sqrt{(f+g, f+g)}=\sqrt{(f, f)+2(f, g)+(g, g)} \leqslant \\
&\leqslant\{\text { неравенство К-Б } \leqslant  \\
&\leqslant \sqrt{(f, f)+2 \sqrt{(f, f)} \cdot \sqrt{(g, g)}+(g, g)}=\sqrt{(f, f)}+\sqrt{(g, g)}=\|f\|+\|g\|
\end{aligned}
$$
证毕。
## 线性空间理论（延续）
请注意，在空间 $L[a, b]$ 和 $\widehat{C}[a, b]$ 中，三角形不等式具有以下形式：
$$
\sqrt{\int_{a}^{b}(f(x)+g(x))^{2} d x} \leqslant \sqrt{\int_{a}^{b} f^{2}(x ) d x}+\sqrt{\int_{a}^{b} g^{2}(x) d x}
$$
它被称为 **Minkowski 不等式**。
在欧几里得（伪欧几里得）空间中，可以引入两个元素之间夹角的概念：$\phi=(\widehat{f, g})$。 它的余弦定义为
$$
\cos \phi=\frac{(f, g)}{\|f\| \cdot\|g\|}, 0<\phi<\pi
$$
但是请注意，
$$
|\cos \phi|=\frac{|(f, g)|}{\|f\| \cdot\|g\|} \leqslant\{\text { 不等式} K-B\} \leqslant \frac{\|f\| \cdot\|g\|}{\|f\| \cdot\|g\|}=1 。
$$
### 定义
如果 $(f, g)=0$，则两个元素 $f$ 和 $g$ 称为正交。
一个例子是 $|x| \perp \operatorname{sgn} x$ 在 $L[-1,1]$。，
$$
\int_{-1}^{1}|x| \operatorname{sgn} x d x=\int_{-1}^{1} x d x=0
$$
### 定义
元素集$\left\{\psi_{j}\right\} \in L$ 称之为 **ортогональной**, 若 $\forall j \neq k \Rightarrow\left(\psi_{j}, \psi_{k}\right)=0$
==这种系统的一个重要例子是函数 $\{1, \cos k x, \sin k x\}$ 在空间 $L[-\pi, \pi]$ 和 $\widehat{C}[ -\pi,\pi]$。==

### 定义
元素集$\left\{\psi_{j}\right\}\in L$ 称之为 **ортонормированной**，如果 $\left(\psi_{j}, \psi_{k}\right)=\delta_{j}^{ k}-$克罗内克符号，回想一下，它被定义为以下形式：
$$
\delta_{j}^{k}= \begin{cases}1, & j=k \\ 0, & j \neq k\end{cases}
$$
### 举例
这种系统的一个重要例子是系统
$$
\left\{\frac{1}{\sqrt{2 \pi}}, \frac{\cos k x}{\sqrt{\pi}}, \frac{\sin k x}{\sqrt{\pi}}\right\}
$$
转化为 $L[-\pi, \pi]$ 和 $[-\pi, \pi]$，其中 $k=1,2,3, \ldots$，
这称为三角函数系 **(тригонометрической системой функций)**。
## 元素的最佳近似问题
令 $\left\{\psi_{j}\right\}-$ 为任意正交（**ортонормированной**）系。固定 $\forall n \in \mathbb{N}$ 并考虑和 $\sum_{j=1}^{n} c_{j} \psi_{j}, \quad c_{j} \in \mathbb{ R}$。
### 定义
伪欧几里得空间中元素 $g$ 与 $f$ 的偏差为数 $\|f-g\|$。

对此，我们需要找到： $\min _{c_{k}}\left\|f-\sum_{k=1}^{n} c_{k} \psi_{k}\right\|$.
$$
\begin{aligned}
&\left\|f-\sum_{k=1}^{n} c_{k} \psi_{k}\right\|^{2}=\left(f-\sum_{k=1}^{n} c_{k} \psi_{k}, f-\sum_{j=1}^{n} c_{j} \psi_{j}\right)=(f, f)-\left(f, \sum_{k=1}^{n} c_{k} \psi_{k}\right)- \\
&-\left(f, \sum_{j=1}^{n} c_{j} \psi_{j}\right)+\sum_{k=1}^{n} \sum_{j=1}^{n} c_{k} c_{j} \cdot\left(\psi_{k}, \psi_{j}\right)=(f, f)-2 \sum_{k=1}^{n} c_{k}\left(f, \psi_{k}\right)+\sum_{k=1}^{n} c_{k}^{2}= \\
&=\left\{\left(f, \psi_{k}\right)=f_{k}\right\}=\|f\|^{2}+\sum_{k=1}^{n}\left(c_{k}-f_{k}\right)^{2}-\sum_{k=1}^{n} f_{k}^{2}=\left\{\text { при } c_{k}=f_{k}\right\}=\|f\|^{2}-\sum_{k=1}^{n} f_{k}^{2} .
\end{aligned}
$$
## 正交系中的傅里叶级数
### 定义
- 级数 $\sum_{k=1}^{\infty} f_{k} \psi_{k}$ 称为正交系 $\left\{\psi_{k}\right\}$ 中函数 $f$ 的傅里叶级数。
- $f_{k}=\left(f, \psi_{k}\right)-$  傅里叶级数系数​​。
- $\sum_{k=1}^{n} f_{k} \psi_{k}-$傅里叶级数前n项的部分和。
### 定理
任意元素 $f \in L$ 最接近正交系 $\left\{\psi_{k}\right\}$ 中傅里叶级数的前 $n$ 项部分和。

我们还计算了最小偏差本身：
$$
\left\|f-\sum_{k=1}^{n} f_{k} \psi_{k}\right\|^{2}=\|f\|^{2}-\sum_{k= 1}^{n} f_{k}^{2} 。
$$
对于任何正交系统 $\left\{\psi_{k}\right\}$，这个恒等式也满足 $\forall f\in L$。 它被称为贝塞尔恒等式 **(тождеством Бесселя)**。
### 定理
对于任意 $f \in L$ 和任意正交系 $\left\{\phi_{k}\right\}$满足： $\sum_{k=1}^{\infty} f_{k}^{2 } \leqslant\|f\|^{2}$**(贝塞尔不等式)**。
在$L[-\pi, \pi]$ 上关于函数 $f$ 关于函数三角系的傅里叶级数具有形式
$$
\frac{f_{0}}{\sqrt{2 \pi}}+\sum_{k=1}^{\infty}\left(\frac{f_{k}^{\prime}}{\sqrt{\pi}} \cos k x+\frac{f_{k}^{\prime \prime}}{\sqrt{\pi}} \sin k x\right)
$$

$$
f_{0}=\frac{1}{\sqrt{2 \pi}} \int_{-\pi}^{\pi} f(x) d x, \quad f_{k}^{\prime}=\frac{1}{\sqrt{\pi}} \int_{-\pi}^{\pi} f(x) \cos k x d x, \quad f_{k}^{\prime \prime}=\frac{1}{\sqrt{\pi}} \int_{-\pi}^{\pi} f(x) \sin k x d x
$$
==注意：
对于 $\sum_{k=1}^{\infty} f_{k} \psi_{k}$ 的傅里叶级数表达形式，$\sum_{k=1}^{\infty} f_{k}^{\prime} \psi_{k}^{\prime}+f_{k}^{\prime \prime} \psi_{k}^{\prime \prime}$
对于傅里叶级数的系数$f_{k}=\left(f, \psi_{k}\right)$，$f_{k}^{\prime}=\left(f(x), \cos k x \right)$, $f_{k}^{\prime \prime}=\left(f(x), \sin k x \right)$,==
请注意，三角傅里叶级数通常以稍微不同的形式编写。 即：
$$
\begin{gathered}
\frac{a_{0}}{2}+\sum_{k=1}^{\infty}\left(a_{k} \cos k x+b_{k} \sin k x\right) \\
a_{0}=\frac{2 f_{0}}{\sqrt{2 \pi}}=\frac{1}{\pi} \int_{-\pi}^{\pi} f(x) d x,a_{k}=\frac{f_{k}^{\prime}}{\sqrt{\pi}}=\frac{1}{\pi} \int_{-\pi}^{\pi} f(x) \cos k x d x \\
b_{k}=\frac{f_{k}^{\prime \prime}}{\sqrt{\pi}}=\frac{1}{\pi} \int_{-\pi}^{\pi} f(x) \sin k x d x
\end{gathered}
$$
在这种情况下，贝塞尔不等式：
$$
f_{0}^{2}+\sum_{k=1}^{\infty}\left(\left(f_{k}^{\prime}\right)^{2}+\left(f_{k }^{\prime \prime}\right)^{2}\right) \leqslant \int_{-\pi}^{\pi} f^{2}(x) d x
$$
可以表示为：
$$
\frac{a_{0}^{2}}{2}+\sum_{k=1}^{\infty}\left(a_{k}^{2}+b_{k}^{2}\right ) \leqslant \int_{-\pi}^{\pi} f^{2}(x) d x
$$