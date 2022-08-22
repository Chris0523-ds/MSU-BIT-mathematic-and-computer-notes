# 第2章 求解网格方程的方法
## 2.2 模型问题(Модельная задача)
### 2.2.1 矩形泊松方程的狄利克雷差分问题算子
解决二维差分边值问题的方法将通过**差分形式(разностную схему)** 的示例进行说明，即矩形 $G=\left\{0<x_{1}<l_{1}, 0<x_{2}<l_{2}\right\}$ 中具有齐次边界条件近似泊松方程狄利克雷问题的差分近似：

$$
\left\{\begin{array}{l}
\Delta u(x)=-f(x), x=\left(x_{1}, x_{2}\right) \in G \\
u(x)=\mu(x), x \in \partial G
\end{array}\right.\tag{2.1}
$$
其中，和以前一样，$\Delta u=\frac{\partial^{2} u}{\partial x_{1}^{2}}+\frac{\partial^{2} u}{\partial x_{2}^{2}}$ 是拉普拉斯算子。

与第 2 章一样，我们将均匀差分网格 $\Omega_{h}=\omega_{h} \cup \gamma_{h}$ 引入 $\bar{G}=G \cup \partial G$ ：
$$
\begin{aligned}
&x_{i j}=\left(x_{1, i}, x_{2, j}\right) \\
&x_{1, i}=i h_{1}, x_{2, j}=j h_{2} ; h_{1} N_{1}=l_{1}, h_{2} N_{2}=l_{2} \\
&\omega_{h}=\left\{x_{i j} ; i=1,2, \ldots, N_{1}-1 ; j=1,2, \ldots, N_{2}-1\right\} \\
&\gamma_{h}=\left\{x_{i 0}, x_{i N_{2}}, x_{0 j}, x_{N_{1} j} ; i=1,2, \ldots, N_{1}-1 ; j=1,2, \ldots, N_{2}-1\right\}
\end{aligned}
$$
并考虑**差分形式（разностную схему）**
$$
\left\{\begin{array}{l}
\Delta_{h} y_{i j}=-f\left(x_{i j}\right), x_{i j} \in \omega_{h} \\
y_{i j}=0, x_{i j} \in \gamma_{h}
\end{array}\right.\tag{2.2}
$$
这里和以前一样，
$$
\Delta_{h} y_{i j}=\left(y_{\bar{x}_{1} x_{1}}+y_{\bar{x}_{2} x_{2}}\right)_ {i j}
$$
是五点差分拉普拉斯算子。


问题 $(2.2)$ 生成一个线性算子$A$，定义如下：
$$
A y_{i j}=-\Delta_{h} y_{i j}=-\left(y_{\bar{x}_{1} x_{1}}+y_{\bar{x}_{2} x_{2}}\right)_{i j}, x_{i j} \in \omega_{h} ;\left.y\right|_{\gamma_{h}}=0
$$

我们引入一个有限维线性空间
$$
H=\left\{y\left(x_{i j}\right): x_{i j} \in \Omega_{h},\left.y\right|_{\gamma_{h}}=0\right\}
$$

该网格函数在网格 $\Omega_{h}$ 上定义，并在 $\gamma_{h}$ 上变为 0。让我们在 $H$ 中定义标量积和范数：
$$
\begin{aligned}
&(y, v)=\sum_{i=1}^{N_{1}-1} \sum_{j=1}^{N_{2}-1} y_{i j} v_{i j} h_{1} h_{2} \\
&\|y\|=\sqrt{(y, y)}, y, v \in H
\end{aligned}
$$
差分问题$(2.2)$可以写成
$$
A y=f ; y, f \in H ; A: H \rightarrow H .
$$
我们的下一个目标是在引入的空间 $H$ 中建立算子 $A$ 的性质。

### 引理 2.2.1（分部积分形式的差分模拟） 
对于在均匀网格上定义的任意函数 $y$ 和 $v$，步长 $h$ 满足恒等式：
$$
\sum_{i=1}^{N} y_{\bar{x}, i} v_{i} h=y_{N} v_{N}-y_{0} v_{0}-\sum_{i= 0}^{N-1} y_{i} v_{x_{i}} h
$$
### 证明：
$$
\begin{gathered}
\sum_{i=1}^{N} y_{\bar{x}, i} v_{i} h=\sum_{i=1}^{N} y_{i} v_{i} h-\sum_{i=1}^{N} y_{i-1} v_{i} h= \\
=y_{N} v_{N}-y_{0} v_{0}+\sum_{i=0}^{N-1} y_{i} v_{i} h-\sum_{i=0}^{N-1} y_{i} v_{i+1} h= \\
=y_{N} v_{N}-y_{0} v_{0}-\sum_{i=0}^{N-1} y_{i} v_{x_{i}} h .
\end{gathered}
$$
### 引理 2.2.2（格林公式的差分模拟）
对于任何 $u,v \in H$ 下列等式成立：
$$
(A y, v)=\sum_{i=1}^{N_{1}} \sum_{j=1}^{N_{2}-1}\left(y_{\bar{x}_{1 }} v_{\bar{x}_{1}}\right)_{i j} h_{1} h_{2}+\sum_{i=1}^{N_{1}-1} \sum_{j =1}^{N_{2}}\left(y_{\bar{x}_{2}} v_{\bar{x}_{2}}\right)_{i j} h_{1} h_{ 2}
$$

### 证明
$$
\begin{gathered}
(A y, v)=-\sum_{i=1}^{N_{1}-1} \sum_{j=1}^{N_{2}-1}\left(y_{\bar{x}_{1} x_{1}} v\right)_{i j} h_{1} h_{2}-\sum_{i=1}^{N_{1}-1} \sum_{j=1}^{N_{2}-1}\left(y_{\bar{x}_{2} x_{2}} v\right)_{i j} h_{1} h_{2}= \\
=-\sum_{i=1}^{N_{1}-1} h_{2} \sum_{j=1}^{N_{2}-1}\left(y_{\bar{x}_{1} x_{1}} v\right)_{i j} h_{1}-\sum_{i=1}^{N_{1}-1} h_{1} \sum_{j=1}^{N_{2}-1}\left(y_{\bar{x}_{2} x_{2}} v\right)_{i j} h_{2}=
\end{gathered}
$$

（由于引理 $2.2 .1$ 的推论，考虑到 $\left.v\right|_{\gamma_{h}}=0$）
$$
=\sum_{i=1}^{N_{1}} h_{2} \sum_{j=1}^{N_{2}-1}\left(y_{\bar{x}_{1}} v_{\bar{x}_{1}}\right)_{i j} h_{1}+\sum_{i=1}^{N_{1}-1} h_{1} \sum_{j=1 }^{N_{2}}\left(y_{\bar{x}_{2}} v_{\bar{x}_{2}}\right)_{i j} h_{2} 。
$$

### 定理 2.2.1
算子 $A$ 在空间 $H$ 中是自伴随且正定的。
### 证明 
引理 $2.2 .2$
$$
(A y, v)=(A v, y)=(y, A v)
$$
对于任何 $y, v \in H$，因此 $A^{*}=A$。另外，
$$
(A y, y)=\sum_{i=1}^{N_{1}} \sum_{j=1}^{N_{2}-1} y_{\bar{x}_{1}, i j}^{2} h_{1} h_{2}+\sum_{i=1}^{N_{1}-1} \sum_{j=1}^{N_{2}} y_{\bar{x}_{2}, i j}^{2} h_{1} h_{2}, \forall y \in H
$$
$(A y, y) \geq 0$。 假设等式$(A y, y)=0$，我们得到
$$
\begin{gathered}
y_{\bar{x}_{1}, i j}=0, i=1,2, \ldots, N_{1} ; j=1,2, \ldots, N_{2}-1 ;\left(\left.y\right|_{\gamma_{h}}=0\right) \rightarrow \\
y_{N_{1} j}=y_{N_{1}-1 j}=\ldots=y_{1 j}=y_{0 j}=0 ; j=1,2, \ldots, N_{2}-\left.1 \rightarrow y\right|_{\Omega_{h}}=0 .
\end{gathered}
$$

因此，对于来自 $H$ 的所有 $y \neq 0$，$(A y, y)>0$。
### 推论
算子$A$的特征值是实数，而且是正数。不同特征值对应的特征空间是正交的。
为了求算子$A$的特征值和特征函数，我们首先考虑一维算子
$$
\left\{\begin{array}{l}
\left(A^{(1)} y\right)_{i}=-y_{\bar{x} x, i} ; i=1,2, \ldots, N-1 \\
y_{0}=y_{N}=0
\end{array}\right.
$$
活动在下面的空间内：
$$
\begin{aligned}
&H^{(1)}=\left\{y\left(x_{i}\right) ; x_{i} \in \Omega_{h}^{(1)}, y_{0}=y_{N}=0\right\} \\
&\Omega_{h}^{(1)}=\left\{x_{i}=i h ; i=0,1, \ldots, N ; h N=l\right\}
\end{aligned}
$$
且有标量积和范数
$$
\begin{aligned}
&(y, v)_{H^{(1)}}=\sum_{i=1}^{N-1} y_{i} v_{i} h ; \\
&\|y\|_{H^{(1)}}=\sqrt{(y, y)_{H^{(1)}}} ; \quad y, v \in H^{(1)} .
\end{aligned}
$$
考虑算子 $A^{(1)}$ 的特征值问题：
$$
\begin{aligned}
&y_{\bar{x} x, i}+\lambda y_{i}=0 ; \quad i=1,2, \ldots, N ; h N=l . \\
&y_{0}=y_{N}=0 ;
\end{aligned}
$$

### 引理 2.2.3 
算子$A^{(1)}$的特征值和特征函数有以下形式：
$$
\lambda_{k}=\frac{4}{h^{2}} \sin ^{2} \frac{\pi k}{2 N} ; y_{k, i}=\sin \frac{\pi k i}{N} ; k=1,2, \ldots, N-1 ; i=0,1, \ldots, N
$$
### 证明 
通过类比对应的微分特征值问题，我们将寻找以下形式的解决方案
$$
y_{i}=\sin (\alpha i) ; i=0,1, \ldots, N 。
$$
将 $y_{i}=\sin (\alpha i)$ 代入方程
$$
y_{i-1}-2\left(1-\lambda h^{2}\right) y_{i}+y_{i+1}=0 ; i=1,2, \ldots, N-1 ;
$$

我们得到 $2 \sin (\alpha i) \cos \alpha-2\left(1-\lambda h^{2}\right) \sin (\alpha i)=0$，因此
$$
\cos \alpha=1-\frac{\lambda h^{2}}{2}, \lambda=\frac{4}{h^{2}} \sin ^{2} \frac{\alpha}{ 2} 。
$$

由于$y_{0}=\sin (\alpha 0)=0$，所以还需要考虑边界条件$y_{N}=0$；
$$
\sin (\alpha N)=0 \rightarrow \alpha_{k}=\frac{\pi k}{N} ; k=1,1, \ldots, N-1
$$
### 引理 2.2.4
算子 $A^{(1)}$ 的特征函数
$$
\mu_{k}\left(x_{i}\right)=\sqrt{\frac{2}{l}} \sin \frac{\pi k i}{N}=\sqrt{\frac{2}{l}} \sin \frac{\pi k x_{i}}{l} ; k=1,2, \ldots, N-1 ; i=0,1, \ldots, N
$$

在空间 $H^{(1)}$ 中形成一个正交基。
### 引理 2.2.5 （算子 $A^{(1)}$ 的频谱估计）
$$
\frac{9}{l^{2}} \leq \lambda_{1}<\lambda_{2}<\cdots<\lambda_{N-1}<\frac{4}{h^{2}}
$$
### 证明
不等式 $\lambda_{k}<\lambda_{k+1}(k=1,2, \ldots, N-2)$ 是$(0, \pi / 2)$上正弦增加的推论。
$$
\lambda_{\max }=\lambda_{N-1}=\frac{4}{h^{2}} \sin ^{2} \frac{\pi(N-1)}{2 N}<\frac{4}{h^{2}} .
$$

引入符号 $\alpha=\frac{\pi}{2 N}$ 并考虑到 $h N=l$，我们得到：
$$
\lambda_{\min }=\lambda_{1}=\frac{4}{h^{2}} \sin ^{2} \frac{\pi}{2 N}=\frac{\pi^{2 }}{l^{2}}\left(\frac{\sin \alpha}{\alpha}\right)^{2} \geq \frac{\pi^{2}}{l^{2}} \left(\frac{6}{\pi} \frac{1}{2}\right)^{2}=\frac{9}{l^{2}} 。
$$

这里我们考虑$\alpha \leq \frac{\pi}{6}$，因为不失一般性我们可以假设$N \geq 3$，以及函数$\frac{\sin \alpha}{\alpha}$ 在 $ \left [0; \frac{\pi}{6}\right]$ 上递减。
==（证毕）==
接下来，考虑运算符 $A$ 的特征值问题：
$$
\begin{gathered}
y_{\overline{x_{1}} x_{1}, i j}+y_{\overline{x_{2}} x_{2}, i j}+\lambda y_{i j}=0, x_{i j} \in \omega_{h} ; \\
y_{i j}=0, x_{i j} \in \gamma_{h} .
\end{gathered}
$$
### 定理 2.2.2
算子$A$ 的特征值和特征函数有以下形式：
$$
\begin{gathered}
\lambda_{k}=\lambda_{k_{1}, k_{2}}=\lambda_{1, k_{1}}+\lambda_{2, k_{2}} \\
\mu_{k}=\mu_{k_{1}, k_{2}}\left(x_{i j}\right)=\mu_{1, k_{1}}\left(x_{1, i}\right) \mu_{2, k_{2}}\left(x_{2, j}\right) \\
\lambda_{1, k_{1}}=\frac{4}{h_{1}^{2}} \sin ^{2} \frac{\pi k_{1} h_{1}}{2 l_{1}} ; \mu_{1, k_{1}}=\sqrt{\frac{2}{l_{1}}} \sin \frac{\pi k_{1} x_{1, i}}{l_{1}} ; i=0,1, \cdots, N 1 \\
\lambda_{2, k_{2}}=\frac{4}{h_{2}^{2}} \sin ^{2} \frac{\pi k_{2} h_{2}}{2 l_{2}} ; \mu_{2, k_{2}}=\sqrt{\frac{2}{l_{2}}} \sin \frac{\pi k_{2} x_{2, j}}{l_{2}} ; j=0,1, \cdots, N 1 \\
k_{1}=1,2, \cdots, N_{1}-1 ; k_{2}=1,2, \cdots, N_{2}-1
\end{gathered}
$$
### 定理 2.2.3 (对算子 A 的频谱的估计)
$$
\frac{9}{l_{1}^{2}}+\frac{9}{l_{2}^{2}} \leq \lambda_{k} \leq \frac{4}{h_{1} ^{2}}+\frac{4}{h_{2}^{2}} 
$$
### 证明 
考虑到引理 2.2.5 的断言:
$$
\gamma_{1}=\lambda_{\min }(A)=\lambda_{11}=\frac{4}{h_{1}^{2}} \sin ^{2} \frac{\pi h_{1}}{2 l_{1}}+\frac{4}{h_{2}^{2}} \sin ^{2} \frac{\pi h_{2}}{2 l_{2}} \geq \frac{9}{l_{1}^{2}}+\frac{9}{l_{2}^{2}},
$$

$$
\gamma_{2}=\lambda_{\max }(A)=\lambda_{N_{1}-1 N_{2}-1}=\frac{4}{h_{1}^{2}} \cos ^{2} \frac{\pi h_{1}}{2 l_{1}}+\frac{4}{h_{2}^{2}} \cos ^{2} \frac{\pi h_{2}}{2 l_{2}}<\frac{4}{h_{1}^{2}}+\frac{4}{h_{2}^{2}}
$$