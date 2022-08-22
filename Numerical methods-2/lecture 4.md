## 1.2 lecture 4
### 1.2.1 泊松方程狄利克雷差分问题的稳定性和收敛性
让我们回到差分问题$(1.2)$的研究上来：
$$
\left\{\begin{array}{l}
-\Delta_{h} y=f(x), x \in \omega_{h} \\
y=\mu(x), x \in \gamma_{h}
\end{array}\right. \tag{1.2}
$$
前面已经证明，对于线性算子
$$
L y(x)=-\Delta_{h} y(x)=A(x) y(x)-\sum_{\xi \in \mathrm{W}_{h}^{\prime}(x) } B(x, \xi) y(\xi), x \in \omega_{h}
$$

$$
A(x)=\frac{2}{h_{1}^{2}}+\frac{2}{h_{2}^{2}}, B\left(x, x_{i \pm 1 j}\right)=\frac{1}{h_{1}^{2}}, B\left(x, x_{i j \pm 1}\right)=\frac{1}{h_{2}^{2}} ; 
$$
对于$\forall x \in \Omega_{h}$，满足系数 $(1.4)$ 为正的条件。
根据上一节的第一个推论，这意味着问题 $(1.2)$ 的解的存在性和唯一性。我们将此解表示为 $y(x)=y_{\mu}(x)+y_{F}(x)$，其中:
$y_{\mu}(x)-$ 问题 $L y_{\mu}(x)=0, x \in \omega_{h}$ 的解，满足 $y_{\mu}(x)=\mu(x), x \in \gamma_{h}$;
$y_{F}(x)-$ 问题 $L y_{F}(x)=F(x), x \in \omega_{h}$的解，满足 $y_{F}(x)=0, x \in \gamma_{h}$。

#### 定理 1.2.1（Устойчивость по граничным условиям）
$$
\left\|y_{\mu}(x)\right\|_{C\left(\Omega_{h}\right)} \leq\|\mu(x)\|_{C\left(\gamma_{h}\right)}
$$
#### 证明 
由定理的第三个推论 $1.1 .4$ 可以得到：
$$
\max _{x \in \omega_{h}}\left|y_{\mu}(x)\right| \leq \max _{x \in \gamma_{h}}|\mu(x)| \Rightarrow \max _{x \in \Omega_{h}}\left|y_{\mu}(x)\right| \leq \max _{x \in \gamma_{h}}|\mu(x)|
$$
因为 $y_{\mu}(x)=\mu(x), x \in \gamma_{h}$。
#### 定理 1.2.2（Устойчивость по правой части）.
$$
\left\|y_{F}(x)\right\| \leq \frac{l_{1}^{2}+l_{2}^{2}}{4}\|F(x)\|_{C\left(\omega_{h}\right)}
$$
#### 定理 1.2.3（Устойчивость разностной задачи Дирихле）
差分问题 $(1.2)$ 的解 $y(x)$ 满足估计
$$
\|y(x)\|_{C\left(\Omega_{h}\right)} \leq\|\mu(x)\|_{C\left(\gamma_{h}\right)}+ \frac{l_{1}^{2}+l_{2}^{2}}{4}\|F(x)\|_{C\left(\omega_{h}\right)}
$$
#### 定理 1.2.4（Dirichlet 差分问题的收敛性） 
令 $u$ 为微分问题 $(1.1)$ 的解，令 $y$ 为差分问题 $(1.2)$ 的解。 
那么 $\|y-u\|_{C\left(\Omega_{h}\right)} \leq M\left(h_{1}^{2}+h_{2}^{2}\right)$，其中 $M$ 是一个独立于 $h_{1}, h_{2}$ 的常数。

#### 定理 1.2.5
在线性差分算子具备**近似性(аппроксимации)** 和**稳定性(устойчивости)** 的前提下，可以得到其**收敛性(сходимость)**。