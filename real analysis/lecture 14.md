
## Разложение функции в интеграл фурье
### 定义
我们会说函数 $f \in L_{1}(\mathbb{R})$ 可以在点 $x$ 处被展开为傅里叶积分，若满足以下条件：
$$
\begin{gathered}
\exists \lim _{\lambda \rightarrow+\infty} \frac{1}{2 \pi} \int_{-\lambda}^{\lambda} e^{-i x y} \widehat{f}(y) d y=\lim _{\lambda \rightarrow+\infty} \frac{1}{2 \pi} \int_{-\lambda}^{\lambda} e^{-i x y}\left(\int_{-\infty}^{+\infty} e^{i \xi y} f(\xi) d \xi\right) d y= \\
=\frac{1}{2 \pi} v . p . \int_{-\infty}^{+\infty} e^{-i x y} \widehat{f}(y) d y
\end{gathered}
$$
事实上，傅里叶积分只不过是从傅里叶图像中恢复函数 $f$ 的傅里叶逆变换。
### 引理
如果 $f \in L_{1}(\mathbb{R})$ 并且具有指数 $\alpha_{1}$ 在左侧点 $x$ 和指数 $\alpha_{2}$ 在右侧点 $x$ 的 Hölder 条件，
$\left(\alpha_{1}, \alpha_{2} \in[0,1]\right)$，则有极限
$$
\lim _{\lambda \rightarrow+\infty} \frac{1}{2 \pi} \int_{-\lambda}^{\lambda} e^{-i x y} \widehat{f}(y) d y,\tag{1}
$$
等于 $\frac{1}{2}(f(x-0)+f(x+0))$。
## 正向和反向傅里叶变换（Прямое и обратное преобразование Фурье）
将函数 $f(x)=\frac{f(x-0)+f(x+0)}{2}$ 展开为傅里叶积分：
$$
f(x)=\frac{1}{2 \pi} v.p. \int_{-\infty}^{+\infty} e^{-i y x} \widehat{f}(y) d y,
$$
从傅里叶图像恢复函数的过程称为**傅里叶逆变换(обратным преобразованием Фурье)**。
在这种情况下，傅里叶图像的表达式
$$
\widehat{f}(y)=v.p. \int_{-\infty}^{+\infty} e^{i y x} f(x) d x
$$
称为**直接傅里叶变换(прямым преобразованием Фурье)**。
对于一个重要的特殊情况，当函数 $f$ 是偶数时，这些公式采用以下形式：
$$
\widehat{f}(y)=2 \int_{0}^{+\infty} \cos (y x) f(x) d x, \quad f(x)=\frac{1}{\pi} \int_ {0}^{+\infty} \cos (y x) \widehat{f}(y) d y
$$
并且被称为**直接和反余弦傅里叶变换(прямым и обратным косинус-преобразованиями Фурье)**。
对于另一种特殊情况，当函数 $f$ 为奇数时，我们有以下形式：
$$
\widehat{f}(y)=2 \int_{0}^{+\infty} \sin (y x) f(x) d x, \quad f(x)=\frac{1}{\pi} \int_ {0}^{+\infty} \sin (y x) \widehat{f}(y) d y 。
$$
并且被称为**直接和逆傅里叶正弦变换(прямым и обратным синус-преобразованиями Фурье)**。