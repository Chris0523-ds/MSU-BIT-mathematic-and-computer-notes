# 机器算术的特点（Особенности машинной арифметики)
## Машинные числа
在计算机上解决数学问题时，我们只能使用有限的一组数字。 这些是形式的所谓**Машинные числа**：
$$
a=\pm\left(\frac{d_{1}}{p}+\frac{d_{2}}{p^{2}}+\ldots+\frac{d_{t}}{p^{t }}\right) \cdot p^{\alpha} 。
$$
这里 $p, \alpha, d_{1}, \ldots, d_{t}$ 是整数。
数字 $p>0$ 称为算术基数 **(основанием арифметики)**。
数字 $\left(\frac{d_{1}}{p}+\frac{d_{2}}{p^{2}}+\ldots+\frac{d_{t}}{p^{t}} \right)$ 被称为**尾数(мантиссой)**。
数字 $\alpha$ 称为**机器编号(Машинные числа)** $a$ 的**阶数**。
数字 $d_{i} \in\{0,1, \ldots, p-1\}$ 称为数字的**位数(разрядами)**。
数字 $t$ 称为**尾数的长度(длиной мантиссы)**。

通常假设 $d_{1} \neq 0$ 这被称为**规范系(нормализованные системы)**。此外，还有整数 $L$ 和 $U$ 定义了 $\alpha:L\leqslant \alpha \leqslant U$ 的边界。 特殊的机器编号是 $a=0$。

允许的机器编号集合由参数 $p, t, L, U$ 决定。

## 机器算术公理
在向计算机输入数字时，以及在对机器数字进行运算时，通常会发生数字四舍五入的情况。舍入可被当作是实数到一组机器数的某种映射。

如果 $x$ 是实数，并且 $\mathrm{fl}(x)$ 是对该实数舍入映射的结果，则以下公理成立： $\mathrm{fl}(x)=x(1+\varepsilon) $, 其中 $ \mathrm{fl}(x) \neq 0,|\varepsilon| \leqslant\eta$。我们假设 $\eta$ 是 $|\varepsilon|$ 的上确界。$\varepsilon-$ **相对舍入误差（относительная погрешность округления）**。

如果在对实数进行四舍五入时，选择最接近它的机器数，则 $\eta=\frac{1}{2} p^{1-t}$。让我们展示一下。

令 $a$ 为数字的真值，$\tilde{a}=\mathrm{fl}(a)$ 为对应的机器编码：
$$
a=\pm\left(\frac{d_{1}}{p}+\frac{d_{2}}{p^{2}}+\ldots+\frac{d_{t}}{p^{t }}+\frac{d_{t+1}}{p^{t+1}}+\ldots\right) \cdot p^{\alpha} 。
$$
如果考虑规范系，则尾数的模总是 $\geqslant \frac{1}{p}$，因此 $|a| \geqslant p^{\alpha-1}$.对于通过寻找最近元素的方法舍入尾数的绝对误差，估计是有效的：
$$
|a-\tilde{a}| \leqslant \frac{1}{2} p^{\alpha} \frac{1}{p^{t+1}}\left(1+\frac{1}{p}+\frac{1}{p^{2}}+\ldots\right) \leqslant \frac{1}{2} p^{\alpha-t} . \Rightarrow \frac{|a-\tilde{a}|}{|a|} \leqslant \frac{1}{2} p^{1-t} .
$$
类似地，$\eta=p^{1-t}$ 通过删除数字进行四舍五入。

机器编号为 $a$ 和 $b$ 的操作 $(*)$ 的结果用 $\mathrm{fl}(a * b)$ 表示。 假设如果 $\mathrm{fl}(a * b) \neq 0$，那么 $\mathrm{fl}(a * b)=(a * b)(1+\varepsilon),|\varepsilon | \leqslant\eta$。 这种关系允许人们研究算法中舍入误差影响的主要公理。

仅当操作的结果不是机器数零时，相对误差 $\varepsilon$ 才很小。

有时舍入是通过丢弃“额外”数字来完成的。 在这种情况下，等式 $x=a * b$ 通常不满足 $\mathrm{fl}(a) * \mathrm{fl}(b)=\mathrm{fl}(x)$。 
例如，设 $p=2、t=2、a=0.11、b=0.0001$ 和 $x=a-b=0.1011$。 在这种情况下，$\mathrm{fl}(x)=0.10$，但 $\mathrm{fl}(a)-\mathrm{fl}(b)=0.11$
(数字运算在 2 位“求和器”中执行)。

使用浮点乘法，当两个非零数的零积小于最小非零元素的绝对值$\varepsilon$，可能会出现机器零。 这被称作 **(Машинное эпсилон)**。
**Машинное эпсилон** 是最小的浮点数 $\varepsilon$，满足

$$
1+\varepsilon>1 \text {. }
$$