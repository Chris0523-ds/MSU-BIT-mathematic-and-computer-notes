## 切比雪夫多项式
考虑以下辅助问题：在所有前导系数为 1 的次数为 $n$ 的多项式中，我们需要找到一个多项式 $T_{n}(x)$，其值 $\max_{x\in[-1, 1]}\left |T_{n}(x)\right|$ 将是最小的。具有此性质的多项式称为**在区间 $[-1,1]$ 上偏离零最小的多项式**或**切比雪夫多项式**。令有多项式：
$$
T_{n}(x)=2^{1-n} \cos (n \arccos (x)) 
$$
让我们首先考虑函数
$$
P_{n}(x)=\cos (n \arccos (x)), x \in[-1,1] 。
$$
展开后有形式：
$$
\cos ((n+1) \arccos (x))+\cos ((n-1) \arccos (x))=2 \cos (n \arccos (x)) \cdot \cos (\arccos (x) ))=2 x P_{n}(x) 。
$$
于是
$$
P_{n+1}(x)-2 x P_{n}(x)+P_{n-1}(x)=0, \quad P_{0}(x)=1, P_{1}(x )=x 。
$$
于是可以通过归纳证明 $P_{n}(x)$ 是 $n$ 次多项式，其前导系数 $2^{n-1} \Rightarrow T_{n}(x)$ 是 $n$ 次多项式，前导系数系数为1。

接下来我们讨论该多项式的性质。显然，以下点是多项式 $T_{n}(x)$ 的根：
$$
x_{k}=\cos \frac{(2 k+1) \pi}{2 n}, k=0,1, \ldots, n-1,
$$
以下点是该多项式的极值点
$$
x_{k}^{\prime}=\cos \frac{k \pi}{n}, k=0,1, \ldots, n,
$$
因此：
$$
T_{n}\left(x_{k}^{\prime}\right)=(-1)^{k} 2^{1-n}, k=0,1, \ldots, n 。
$$
最终我们可以得到：
$$
\max _{x \in[-1,1]}\left|T_{n}(x)\right|=2^{1-n} 。
$$
让我们证明，在所有前导系数为 1 的次数为 $n$ 的多项式中，多项式 $T_{n}(x)$ 在段 $[-1,1]$ 上与零的偏差较小，即
$$
\max _{x \in[-1,1]}\left|T_{n}(x)\right|=\min \left\{\max _{x \in[-1,1]}\left |Q_{n}(x)\right|: Q_{n}(x)=x^{n}+\ldots\right\} \text {. }
$$
令 $Q_{n}(x)$ 是任何次数为 $n$ 且前导系数为 1 的多项式。令
$$
\left\|Q_{n}\right\|=\max _{x \in[-1,1]}\left|Q_{n}(x)\right| .
$$

### 引理 15.1 
假设有一个点集
$$
-1 \leqslant x_{n}^{\prime}<x_{n-1}^{\prime}<\ldots<x_{1}^{\prime}<x_{0}^{\prime} \leqslant 1
$$
该点集满足条件
$$
\left|Q_{n}\left(x_{k}^{\prime}\right)\right|=\left\|Q_{n}\right\|, k=0,1, \ldots, n,
$$
其中，数字 $Q_{n}\left(x_{l}^{\prime}\right)$ 的符号是交替的。 那么在所有前导系数为 1 的,次数为 $n$ 的多项式中，多项式 $Q_{n}(x)$ 与零的偏差最小。
（证明略）
## 切比雪夫多项式在任意区间的情形
 