## 傅里叶积分
### 定义
我们会说函数 $f$ 属于类 $L_{1}(\mathbb{R})$,若满足以下条件：
(1) $f$ 在任意有限区间上是黎曼可积的；
(2) 下面的反常积分收敛：
$$
\int_{\mathbb{R}}|f(x)| d x 。
$$
### 举例
- $f(x)=e^{-|x|} \in L_{1}(\mathbb{R})$;
- $f(x)=e^{-x^{2}} \in L_{1}(\mathbb{R})$
- $f(x)=\left\{\begin{array}{cc}1 / x^{2}, & |x|>1, \\ 0, & |x| \leqslant 1\end{array} \in L_{1}(\mathbb{R})\right.$

## 傅立叶像上的基本引理（Основная лемма об образе Фурье）.
如果 $f \in L_{1}(\mathbb{R})$，则对于该类收敛的积分
$$
\widehat{f}(y)=\text { v.p. } \int_{-\infty}^{\infty} e^{i x y} f(x) d x,
$$
被称为函数 $f$ 的 **像或傅里叶变换(образом или преобразованием Фурье)**。 此外，$\widehat{f}(y)$ 对 $\forall y \in \mathbb{R}$ 是连续的，并且 $\exists \lim _{|y| \rightarrow \infty}|\widehat{f}(y)|=0$。
### 证明
（这个太长了，直接跳过了）
### 推论
令$f \in L_{1}(\mathbb{R})$，那么：
$$
\lim _{\lambda \rightarrow+\infty} \int_{-\infty}^{+\infty} \sin (\lambda x) f(x) d x=\lim _{\lambda \rightarrow+\infty} \int_ {-\infty}^{+\infty} \cos (\lambda x) f(x) d x=0
$$
在文献中，傅里叶变换 $\widehat{f}(y)$ 有时也表示为 $[\widehat{f}(x)](y)$，$y$ 称为虚变量。

傅里叶变换在微分方程理论以及许多其他数学分支中起着重要作用。 例如它的离散模拟，即所谓的离散傅里叶变换，它在信号处理中也起着关键作用，在图像、视频、音乐等处理中的许多算法中都有使用。