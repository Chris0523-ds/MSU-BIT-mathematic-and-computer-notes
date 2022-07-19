# lecture 4
上节课内容：久期和现金流估值
## 数据类型
R 支持多种基本数据类型和许多派生数据类型。
## 久期（续）
通过添加泰勒展开的二次项，考虑利率的变化如何影响支付流的现值：
$$
S(i+\Delta i)=S(i)+S^{\prime}(i) \Delta i+\frac{1}{2} S^{\prime \prime}(i)(\Delta i)^ {2}
$$
在 $S^{\prime}(i) \approx 0$ 的条件下，即假设债券投资组合是结构化的，并且该投资组合的收入和支付久期是一致的，不等式 $S^{\prime \prime}(i)>0$ 确保满足 $S(i+\Delta i)> S(i)$。因此，当利率发生变化时，收入总是会增加，而拥有这样一个投资组合的投资者总是会获得收入和“凭空而来的午餐”。
让我们更详细地描述这种方法，即“杠铃”方法。
![s16551006142022.png](img/s16551006142022.png)

投资者出售中期债券并承担形成支付流（负债）$L_{t}$ 的义务，他将收到的资金投资于购买长期和短期债券，形成收入流$A_ {t}$ 。 因此，现金流成本$S(i)=0$，销售所得现金等于购买价格：
$$
\sum_{t>0}^{T} \frac{A_{t}}{(1+i)^{t}}=\sum_{t>0}^{T} \frac{L_{t}} {(1+i)^{t}}
$$
此外，它形成一个投资组合，使收入的持续时间等于支付的持续时间，即实现了平等：
$$
\sum_{t>0}^{T} \frac{t A_{t}}{(1+i)^{t}}=\sum_{t>0}^{T} \frac{t L_{t }}{(1+i)^{t}}
$$
结果是产生正回报的有利可图的投资组合。
$$
\sum_{t>0}^{T} \frac{t^{2} A_{t}}{(1+i)^{t}}>\sum_{t>0}^{T} \frac{ t^{2} L_{t}}{(1+i)^{t}}
$$
相当于$S^{\prime \prime}(i)>0$。因此，不平等程度越大，债券投资组合的利润就越高。投资者将寻求将债券分成两组短期和超长期债券，从短期债券中产生支付流。在这种情况下，无需使用额外资金即可产生利润。资产组合（收入）完全由负债（费用）提供资金，并且该组合获利。
## 价格需求弹性
在经济学中，弹性一词是指变量的相对变化。
例如，一种商品的需求价格弹性为：
$$
\frac{\Delta Q}{Q}=\text { Elast } \cdot \frac{\Delta P}{P}
$$
$\frac{\Delta Q}{Q}$ - 商品需求的相对变化；
$\frac{\Delta P}{P}$ - 产品的相对价格变化。

![s17015206142022.png](img/s17015206142022.png)
弹性表示当一种商品的价格发生变化时，相对需求量的百分比变化。
弹性 Elast 是这些变量的对数导数的比率：
$$
\frac{\Delta y}{y}=\text { Elast } \cdot \frac{\Delta x}{x}
$$
示例：考虑多项式函数 $y(x)=F(x)=x^{\alpha}$ 和指数函数 $y(x)=e^{\alpha x}$ 并求弹性 $Elast$
变量 $y$ 通过变量 $x$，即当 $\frac{\Delta x}{x}$ 变化时，比率 $\frac{\Delta y}{y}$ 变化多少次
$$
\begin{gathered}
\frac{\Delta y}{y}=E \operatorname{last} \cdot \frac{\Delta x}{x} \\
\text { Elast } 1=\frac{d(\ln y)}{d(\ln x)}=\frac{d\left(\ln x^{\alpha}\right)}{d(\ln x)}=\alpha \cdot \frac{d(\ln x)}{d(\ln x)}=\alpha \\
\text { Elast } 2=\frac{d(\ln y)}{d(\ln x)}=\frac{d\left(\ln e^{\alpha x}\right)}{d(\ln x)}=\alpha \cdot \frac{d x}{d(\ln x)}=\alpha x
\end{gathered}
$$
## 麦考利凸出
假设收入流为$A_{t}$，一种固定收益证券。目前市场价格为$A$。
方程解
$$
A=\sum_{t>0}^{T} \frac{A_{t}}{(1+i)^{t}}=\sum_{t>0}^{T} A_{t} d^ {t}
$$
相对于收益率 $i$ 或等效地相对于折扣因子 $d=$ $\frac{1}{1+i}$ 给出到期收益率。
求债券价格相对于贴现因子 $d$ 的弹性
$$
\text { Elast }=\frac{d(\ln A)}{d(\ln d)}=\frac{1}{\mathrm{~A}} \sum_{t>0}^{T} t \cdot A_{t} d^{t}=\frac{1}{\mathrm{~A}} \sum_{t>0}^{T} \frac{t A_{t}}{(1+i)^{t}}
$$
因此，Macaulay 久期与债券价值相对于贴现因子$d$ 的弹性一致。
我们引入符号，令 $r=\ln (1+i)$ 则 $r-$ 称为兴趣幂，
$$
A=\sum_{t>0}^{T} A_{t} e^{-r t}
$$

相对于收益率 $i$ 或等效地相对于折扣因子 $d=$ $\frac{1}{1+i}$ 给出到期收益率。
求债券价格相对于贴现因子 $d$ 的弹性
$$
\text { Elast }=\frac{d(\ln A)}{d(\ln d)}=\frac{1}{\mathrm{~A}} \sum_{t>0}^{T} t \cdot A_{t} d^{t}=\frac{1}{\mathrm{~A}} \sum_{t>0}^{T} \frac{t A_{t}}{(1+i)^{t}}
$$
因此，Macaulay 久期与债券价值相对于贴现因子$d$ 的弹性一致。
我们引入符号，令 $r=\ln (1+i)$ 则 $r-$ 称为兴趣幂，
$$
A=\sum_{t>0}^{T} A_{t} e^{-r t}
$$
然后我们可以使用百分比幂 $r=\ln (1+i)$ 重写持续时间的表达式：
$$
D=\frac{1}{\mathrm{~A}} \sum_{t>0}^{T} \frac{t A_{t}}{(1+i)^{t}}=\frac{ 1}{\mathrm{~A}} \sum_{t>0}^{T} t A_{t} e^{-r t}=-\frac{1}{\mathrm{~A}} \frac{ d}{d r} A=-\frac{d}{d r} \ln A
$$

下列式子表达称为麦考利凸性的数量：
$$
C=\frac{1}{\mathrm{~A}} \frac{d^{2}}{d r^{2}} A=\frac{1}{\mathrm{~A}} \sum_{t >0}^{T} t^{2} A_{t} e^{-r t}
$$
