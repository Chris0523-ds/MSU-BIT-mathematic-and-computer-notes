# lecture 11
## 问题 $1 .$
1.随机变量$X$均匀分布在段$[-2,2]$上。求$E[X]$和$D[X]$决定：
SW 分布密度 $X$ :
$$
f_{X}=\frac{1}{b-a}=\frac{1}{2-(-2)}=\frac{1}{4}
$$
由于密度关于 $O Y$ 轴对称，SW $E[X]=0$ 的平均值等于$0$。
$$
E[X]=\int_{-2}^{2} \frac{1}{4} \cdot x \cdot d x=\left.\frac{1}{8} \cdot x^{2}\right |_{-2} ^{2}=0
$$
让我们计算方差：
$$
D[X]=\int_{-2}^{2} \frac{1}{4} \cdot(x-0)^{2} \cdot d x=\left.\frac{1}{12} \cdot x^{3}\right|_{-2} ^{2}=\frac{4}{3}
$$
## 任务 2。
生成 N=100 xts 时间序列值。 构造这个时间序列的值的直方图。
```R{.line-numbers}
# N Случайных чисел
library(xts)
set.seed(16)
N<-100
data <- rnorm(N)
# dates как Date класс с началом 2022-01-01
dates <- seq(as.Date("2022-04-01"), length = N, by = "days")
# Создаем объект xts() 
ts1 <- xts(x = data, order.by = dates)
ts2 <- xts(x = data, order.by = dates)
# данные временного ряда ts2
ts2_core <- coredata(ts2)
ts2_core
# class 
class(ts2_core)
# Индекс ts2 (временная шкала)
ts2_index <- index(ts2)
ts2_index
# Класс ts2_index
class(ts2_index)
plot(ts2)
ts3<-ts1+0.2*ts2^2
plot.xts(ts1, col= 'black')
lines(ts2, col = 'blue')
lines(ts3,col = 'red')
bin <- seq(from=-5,to=5,length.out=10)-0.00001
hist(ts1, prob=TRUE, plot=TRUE)
hist(ts1, breaks=bin, prob=TRUE, plot=TRUE, main = 'Histogram ts1 -5 
5')
hist(ts2, prob=TRUE, plot=TRUE)
hist(ts2, breaks=bin, prob=TRUE, plot=TRUE, main = 'Histogram ts2 -5 
5')
bin
```
![s08421205102022.png](img/s08421205102022.png)
## 连续随机变量及其特征
对于连续随机变量$X$，与数学期望、方差和其他特征相关的定义与离散变量的定义相似。
一个随机变量$X$或一个函数，$X$的一个函数$g(X)$，与离散随机变量的相同，求和，用积分代替，函数的概率密度用$f(x)$ 表示而不是 $p(x)$。连续随机变量 $X$ 的数学期望（期望值）：
$$
E[X]=\mu_{X}=\int_{-\infty}^{\infty} x \cdot f(x) d x
$$
$X$ 的函数 $g(X)$ 的数学期望是：
$$
E[g(X)]=\int_{-\infty}^{\infty} g(x) \cdot f(x) d x
$$
连续随机变量 $X$ 的方差等于：
$$
\operatorname{Var}[X]=\sigma_{X}^{2}=E\left[(X-\mu)^{2}\right]=\int_{-\infty}^{\infty}( x-\mu)^{2} \cdot f(x) d x
$$
### 马尔可夫不等式：
如果 $X$ 是一个随机变量并且函数 $g(X) \geq 0$，那么对于任何正的 $K$ ：
$$
P(g(X) \geq K) \leq \frac{E[g(X)]}{K}
$$
### 证明：
让我们引入函数 $I(g(X))=\left\{\begin{array}{cr}1, \text { если } g(X) \geq K \\ 0, \text { если иначе }\end{array}\right.$
然后函数$I(g(X)) \leq \frac{g(X)}{K}$，应用数学期望，我们得到：
$$
E[I(g(X))] \leq \frac{E[g(X)]}{K}
$$
让我们对此改变形式为
$$
\begin{aligned}
E[I(g(X))]=& \sum_{x} I(g(x)) \cdot p(x)=[1 \cdot P(I(g(x))=1)]+[0 \cdot P(I(g(x))=0)] \\
&=P(g(x) \geq K)
\end{aligned}
$$
我们得到：
$$
P(g(x) \geq K) \leq \frac{E[g(X)]}{K}
$$
切比雪夫不等式是从马尔科夫不等式得到的，如果我们取 $g(X)=(X-\mu)^{2}$ 和常数 $K=\sigma^{2} \cdot k^{2}$ ， 然后
$$
P\left((X-\mu)^{2} \geq \sigma^{2} \cdot k^{2}\right) \leq \frac{E\left[(X-\mu)^{2 }\right]}{\sigma^{2} \cdot k^{2}}=\frac{1}{k^{2}}
$$
或者写成另一种形式
$$
P(|X-\mu| \geq \sigma k) \leq \frac{1}{k^{2}}
$$
从这个不等式得出，对于任何具有有限方差的随机变量 $X$，无论 $X$ 的分布如何，事件偏离其均值 $k$ 或大于标准差的概率小于或等于 $\frac{1}{ k^{2}}$。
从这个不等式可以得出
$$
P(|X-\mu| \leq \sigma k) \geq 1-\frac{1}{k^{2}}
$$
IE。随机变量 $X$ 与平均值的标准差在 $k$ 之内的概率大于 $1-\frac{1}{k^{2}}$。切比雪夫不等式可用于估计一些概率。

例子：
考虑应用切比雪夫不等式来估计“老鹰”抛三枚硬币出现的概率。
设 $X$ 是绘制的“老鹰”的数量，那么 Chebyshev 不等式至少保证在与其均值的 $k=2$ 个标准差内找到 $X$ 的概率等于 $1-\frac{1}{k ^{ 2}}=1-\frac{1}{4}=\frac{3}{4}=0.75$。
一个实验由掷硬币 3 次或掷 3 枚硬币组成，基本事件的空间由八个结果组成：
$$
\omega =\{OOO, POO, OPO, OOP, PPO, POP, OPP, PPP\}
$$
随机变量 $X$ - 掉出的“正面”数量，然后是分布密度函数
和分布函数
$$
F(x)=\left\{\begin{array}{cc}
0, & \text { 当 } x<0 \\
\frac{1}{8}, & \text { 当 } 0 \leq x<1 \\
\frac{4}{8}, & \text { 当 } 1 \leq x<2 \\
\frac{7}{8}, & \text { 当 } 2 \leq x<3 \\
1, & \text { 对于 } x \geq 3
\end{array}\right\}
$$
让我们找出 $X$ 在均值的 $k=2$ 标准差内的事件的实际概率：
$$
E[X]=\sum_{x} x \cdot p(x)=0 \cdot \frac{1}{8}+1 \cdot \frac{3}{8}+2 \cdot \frac{3} {8}+3 \cdot \frac{1}{8}=1.5
$$

