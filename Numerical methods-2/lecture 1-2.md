# lecture 1-2
### 1.1.3 抛物线型方程 (Уравнения параболического типа)
我们将考虑以下等式：
$$
u_{t}=a^{2} u_{x x}+f(x, t), 0<x<l, 0<t<T
$$
其中$u=u(x, t)$。
这个方程在空间上是一维的，描述了热量在长度为 $l$ 的棒中传播的过程。 这里 $u(x, t)$ 是 $t$ 时刻在点 $x$ 处的温度。
如果已知初始时刻杆中的温度，则我们得到初始条件：
$$
u(x, 0)=\varphi(x), 0 \leq x \leq l
$$

如果末端的温度变化过程已知，那么我们得到一些边界条件：
$$
x=l, 0 \leq t \leq T \quad\left\{\begin{array}{l}u(l, t)=\mu_{2}(t)-\text { первое краевое условие; } \\ u_{x}(l, t)=\nu_{2}(t)-\text { второе краевое условие; } \\ u_{x}(l, t)=-\lambda_{2}\left[u(l, t)-\theta_{2}(t)\right]- \\ \text { третье краевое условие }\left(\lambda_{2}>0\right) .\end{array}\right.$$

$$
x=0,0 \leq t \leq T \quad\left\{\begin{array}{l}u(0, t)=\mu_{1}(t)-\text { первое краевое условие; } \\ u_{x}(0, t)=\nu_{1}(t)-\text { второе краевое условие; } \\ u_{x}(0, t)=\lambda_{1}\left[u(0, t)-\theta_{1}(t)\right]- \\ \text { третье краевое условие }\left(\lambda_{1}>0\right)\end{array}\right.
$$
结合这些条件，我们会得到不同类型的问题：
$$
\begin{aligned}
&\text { Первая краевая задача: }\left\{\begin{array}{l}
u_{t}=a^{2} u_{x x}+f(x, t), 0<x<l, 0<t \leq T ; \\
u(0, t)=\mu_{1}(t), 0 \leq t \leq T ; \\
u(l, t)=\mu_{2}(t), 0 \leq t \leq T ; \\
u(x, 0)=\varphi(x), 0 \leq x \leq l .
\end{array}\right. \\
&\text { Вторая краевая задача: }\left\{\begin{array}{l}
u_{t}=a^{2} u_{x x}+f(x, t), 0<x<l, 0<t \leq T ; \\
u_{x}(0, t)=\mu_{1}(t), 0 \leq t \leq T ; \\
u_{x}(l, t)=\mu_{2}(t), 0 \leq t \leq T ; \\
u(x, 0)=\varphi(x), 0 \leq x \leq l .
\end{array}\right. \\
&\text { Задача на полупрямой: }\left\{\begin{array}{l}
u_{t}=a^{2} u_{x x}+f(x, t), x>0,0<t \leq T ; \\
u_{x}(0, t)=\mu(t), 0 \leq t \leq T ; \\
u(x, 0)=\varphi(x), x \geq 0 .
\end{array}\right.
\end{aligned}
$$

$$
\text { Задача Коши: }\left\{\begin{array}{l}
u_{t}=a^{2} u_{x x}+f(x, t),-\infty<x<+\infty, 0<t \leq T ; \\
u(x, 0)=\varphi(x),-\infty<x<+\infty
\end{array}\right.
$$
### 1.1.4 第一边值问题解的存在性
考虑集合 $Q_{T}=\{(x, t):(0, l) \times(0, T]\} .$ 表示 $\Gamma=\bar{Q}_{T} / Q_{ T }-$ 集合 $Q_{T}$ 的边界。
考虑第一个边值问题：
$$
\left\{\begin{array}{l}
u_{t}=a^{2} u_{x x}+f(x, t), 0<x<l, 0<t \leq T \\
u(0, t)=\mu_{1}(t), 0 \leq t \leq T \\
u(l, t)=\mu_{2}(t), 0 \leq t \leq T \\
u(x, 0)=\varphi(x), 0 \leq x \leq l
\end{array}\right.
$$
### 定义 
函数 $u(x, t)$ 如果满足以下条件，则称为热方程 (??) 的第一边值问题的解：
1. $u \in C\left[\bar{Q}_{T}\right]$;
2. $u_{t}, u_{x x} \in C\left[Q_{T}\right]$;
3. $u(x, t)$ 满足等式(??)；
4. $u(x, t)$ 满足 (??) 的边界和初始条件。


### 1.1.5 热量方程的最大值原理

满足热方程的函数 $u(x, t)$ 恰好在该边界处达到其最大值（和最小值）。
#### 定理 1.1.1 (Приниип максимального значения) 
令有
$$
u(x, t) \in C\left(\bar{Q}_{T}\right), u_{t}, u_{x x} \in C\left(Q_{T}\right)
$$
且 $u_{t}=a^{2} u_{x x \quad \quad}$
那么
$$
\left\{\begin{aligned}
\max _{\bar{T}} u(x, t) &=\max _{\Gamma} u(x, t) \\
\min _{\bar{T}} u(x, t) &=\min _{\Gamma} u(x, t)
\end{aligned}\right.
$$

其中 $\Gamma=\{(x, t):\{x \in[0, l], 当  t=0\} \cup\{t \in[0, T],当 x=0, x=l\}\}$.
当应用于边值问题时，最大值原理如下所示。令：
$$
\left\{\begin{array}{l}
u_{t}=a^{2} u_{x x}, 0<x<l, 0<t \leq T \\
u(0, t)=\mu_{1}(t), 0 \leq t \leq T \\
u(l, t)=\mu_{2}(t), 0 \leq t \leq T \\
u(x, 0)=\varphi(x), 0 \leq x \leq l
\end{array}\right.
$$
那么 $\max _{\bar{Q}_{T}} u(x, t)=\max \left\{\max _{t \in[0, T]} \mu_{1}(t) , \max _{t \in[0, T]} \mu_{2}(t), \max _{x \in[0, l]} \varphi(x)\right\}$。
这意味着棒的温度不能高于棒边缘的温度和初始时刻的温度。
### 1.1.6 第一边值问题解的唯一性和稳定性

#### 定理 1.1.2 (唯一性)
让函数 $u_{1}(x, t), u_{2}(x, t)$ 是这样的
$$
u_{i} \in C\left(\bar{Q}_{T}\right), \frac{\partial^{2} u_{i}}{\partial x^{2}}, \frac{\partial u_{i}}{\partial t} \in C\left(Q_{T}\right), i=1,2
$$
此外，它们是相同的第一边值问题（??）的解决方案。
那么$u_{1}(x, t)=u_{2}(x, t)$ in $\bar{Q}_{T}$。
#### 定理 1.1.3（稳定性）
让函数 $u_{1}(x, t), u_{2}(x, t)$ 满足
$$
u_{i} \in C\left(\bar{Q}_{T}\right), \frac{\partial^{2} u_{i}}{\partial x^{2}}, \frac{\partial u_{i}}{\partial t} \in C\left(Q_{T}\right), i=1,2
$$
和
$$
\left\{\begin{array}{l}
\frac{\partial u_{i}}{\partial t}=a^{2} \frac{\partial^{2} u_{i}}{\partial x^{2}}, 0<x<l, 0<t \leq T, i=1,2 \\
u_{i}(0, t)=\mu_{1}^{i}(t), 0 \leq t \leq T, i=1,2 \\
u_{i}(l, t)=\mu_{2}^{i}(t), 0 \leq t \leq T, i=1,2 \\
u_{i}(x, 0)=\varphi_{i}(x), 0 \leq x \leq l, i=1,2
\end{array}\right.
$$
那么可以得到：
$$
\left|u_{1}(x, t)-u_{2}(x, t)\right|=\max \left\{\begin{array}{c}
\max _{t \in[0, T]}\left|\mu_{1}^{1}(t)-\mu_{1}^{2}(t)\right| \\
\max _{t \in[0, T]}\left|\mu_{2}^{1}(t)-\mu_{2}^{2}(t)\right| \\
\max _{x \in[0,1]}\left|\varphi_{1}(x)-\varphi_{2}(x)\right|
\end{array}\right\}
$$
### 1.1.7 一般边值问题解的唯一性
混合或一般边值问题的公式如下：
$$
\left\{\begin{array}{l}
u_{t}=a^{2} u_{x x}+f(x, t), 0<x<l, 0<t \leq T \\
\alpha_{1} u(0, t)-\alpha_{2} u_{x}(0, t)=p(t), 0 \leq t \leq T ; \\
\beta_{1} u(l, t)+\beta_{2} u_{x}(l, t)=q(t), 0 \leq t \leq T ; \\
u_{i}(x, 0)=\varphi_{i}(x), 0 \leq x \leq l .
\end{array}\right.
$$
这里 $\alpha_{1}, \alpha_{2}, \beta_{1}, \beta_{2}$ 是非负常数，要求
$$
\alpha_{1}+\alpha_{2}>0, \beta_{1}+\beta_{2}>0
$$
让我们制定一个关于此类问题解决方案的唯一性的定理。
#### 定理 1.1.4（唯一性）
令 $Q_{T}$ 中的函数 $u_{1}(x, t), u_{2}(x, t)$ 满足以下条件：
$$
u_{i} \in C\left(\bar{Q}_{T}\right), \frac{\partial^{2} u_{i}}{\partial x^{2}}, \frac{ \partial u_{i}}{\partial t} \in C\left(Q_{T}\right), i=1,2,
$$
则它们是同一个任务的解。那么$u_{1}(x, t)=u_{2}(x, t) \forall(x, t) \in \bar{Q}_{T}$。
#### 证明：没有证明。
### 1.1.8 分离变量法（略）
### 1.1.9 椭圆型方程（Уравнения эллиптического типа）
令 $\Omega$ 是 $E^{3}$ 中的某个开放域，以表面 $\Sigma$ 为界。类似地，$D$ 是 $E^{2}$ 中的某个开放域，以曲线 $L$ 为界。
考虑热传导方程：
$$
\begin{aligned}
&u_{t}(x, y, t)=a^{2} \Delta u(x, y, t)+f_{2}(x, y),(x, y) \in D \\
&\Delta u=u_{x x}+u_{y y} \\
&u_{t}(x, y, z, t)=a^{2} \Delta u(x, y, z, t)+f_{2}(x, y, z),(x, y, z ) \in \omega \\
&\Delta u=u_{x x}+u_{y y}+u_{z z}
\end{aligned}
$$
在稳态热过程 $\left(u_{t} \equiv 0\right)$ 的情况下，我们得到椭圆型方程：
$$
\Delta u=-f
$$
在这种情况下，从一般形式中获得两种类型的方程，它们具有名义名称：
$$
\begin{aligned}
&u_{x x}+u_{y y}=-f(x, y)-\text { уравнение Пуассона в } E^{2} ; \\
&u_{x x}+u_{y y}+u_{z z}=-f(x, y, z)-\text { уравнени Пуассона в } E^{3} ; \\
&u_{x x}+u_{y y}=0-\text { уравнение Лапласа в } E^{2} ; \\
&u_{x x}+u_{y y}+u_{z z}=0-\text { уравнение Лапласа в } E^{3} .
\end{aligned}
$$
### 定义
如果 $u \in C^{2}(\Omega)$ 和 $\Delta u \equiv 0$ 在 $\Omega$ 中，则称函数 $u(x, y, z)$ 在 $\Omega$ 中是**调和(гармонической)** 的。
在下文中，考虑空间 $E^{3}$ 中的任务。它们也有自己的名称：
1.内狄利克雷问题
$$
\left\{\begin{array}{l}
\Delta u(x, y, z)=0,(x, y, z) \in \Omega \\
u(x, y, z)=\mu(x, y, z),(x, y, z) \in \Sigma .
\end{array}\right.
$$
2.内诺依曼问题
$$
\left\{\begin{array}{l}
\Delta u(x, y, z)=0, \quad(x, y, z) \in \Omega \\
\frac{\partial u(x, y, z)}{\partial n}=\nu(x, y, z),(x, y, z) \in \Sigma
\end{array}\right.
$$

3.外部狄利克雷问题
$$
\left\{\begin{array}{l}
\Delta u(x, y, z)=0,(x, y, z) \in E^{3} / \bar{\Omega} \\
u(x, y, z)=\mu(x, y, z), \quad(x, y, z) \in \Sigma
\end{array}\right.
$$
4.外部诺依曼问题
$$
\left\{\begin{array}{l}
\Delta u(x, y, z)=0, \quad(x, y, z) \in E^{3} / \bar{\Omega} \\
\frac{\partial u(x, y, z)}{\partial n}=\nu(x, y, z),(x, y, z) \in \Sigma
\end{array}\right.
$$
同样，也可以写成二维的情况。

### 1.1.10 调和函数(гармоническая функция)的最大值原理
#### 定理 1.1.5 (最大值原理)
如果函数 $u \in C(\bar{\Omega})$, 在 $\Omega$ 中是调和的，那么它在域边界处达到最大值（最小值）：
$$
\begin{aligned}
&\max _{M \in \bar{\Omega}} u(M)=\max _{M \in \Sigma} u(M) \\
&\min _{M \in \bar{\Omega}} u(M)=\min _{M \in \Sigma} u(M) .
\end{aligned}
$$
#### 定理 1.1.6
令有函数 $u_{1}(x, y, z), u_{2}(x, y, z)$，那么：
1. $u_{1}(x, y, z), u_{2}(x, y, z) \in C\left(\bar{Q}_{T}\right)$;
2. $u_{1}(x, y, z), u_{2}(x, y, z)-$在 $\Omega$ 中是调和的；
3. $u_{1}(x, y, z) \leq u_{2}(x, y, z),(x, y, z) \in \Sigma$。

那么在 $\Omega$ 中 $u_{1}(x, y, z) \leq u_{2}(x, y, z)$。

### 1.1.11 内狄利克雷问题解的唯一性和稳定性

#### 定义 
如果函数 $u(x, y, z)$ 满足以下三个条件，则称为内狄利克雷问题的解：
$$
\left\{\begin{array}{l}
u \in C(\bar{\Omega}), u \in C^{2}(\Omega) \\
\Delta u(x, y, z)=0,(x, y, z) \in \Omega \\
u(x, y, z)=\mu(x, y, z),(x, y, z) \in \Sigma .
\end{array}\right.
$$
#### 定理 1.1.7（唯一性）
令函数 $u_{1}, u_{2}$ 是同一内部狄利克雷问题的解。那么 $u_{1}=u_{2}$ 在 $\bar{\Omega}$。
#### 证明
#### 定理 1.1.8（稳定性）
设函数 $u_{1}, u_{2}$ 是同一内部狄利克雷问题的解。但有不同的边界条件 $\mu_{1}, \mu_{2}$。那么：
$$
\max _{\bar{\Omega}}\left|u_{1}-u_{2}\right| \leq \max _{\Sigma}\left|\mu_{1}-\mu_{2}\right|
$$
==稳定性是指改变边界条件对方程造成的影响。==

