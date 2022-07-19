# lecture 6
## 利率期限结构的计算（Расчет временной структуры процентных ставок）
什么是利率期限结构？它被定义为零息债券的到期收益率与到期期限之间的比率。
债券、存款证和其他货币市场证券的市场价格决定利率，称为即期市场利率或即期利率。
不同期限的工具对应的即期利率决定了这些期限之间有效的利率值，这种利率称为远期利率。
债券定价公式适用于零息债券。
具有市场收益率的零息债券价格公式为：
$$
P_{t}=\frac{1}{\left(1+y_{t}\right)^{t}} N
$$
$P_t$是债券的现值，$N$是债券的面值（赎回金额），$t$是零息债券的流通周期，$y_t$是市场收益率。
$$
y_{t}=\left(\frac{N}{P_{t}}\right)^{\frac{1}{t}}-1
$$
对于市场收益率$y_{t}$，我们得到零息债券的到期收益率与其到期日之间的等式。
这就是零息票收益率曲线（利率曲线）的定义方式，这条曲线也称为**收益率曲线(кривой доходности)**，或**即期曲线(спотовой кривой)**。
零息债券的到期收益率（YTM）也称为**即期利率(спотовой процентной ставкой)**。
示例：计算债券投资组合的到期收益率
```R{.line-numbers}
# 债券现金流量向量
# 现值估计的短程序
# 价值函数
bval <- function(i, cf,
 t=(seq(along = cf)-1))
 sum(cf / (1 + i)^t)
# Находим доходность к погашению ytm() function using 
uniroot
ytm <- function(cf) 
{
    y <- uniroot(bval, c(0, 1), cf = cf)$root
    t <- length(cf)-1
    c(y,t)
}
cf0 <- c(-95.20,100)
cf1 <- c(-98.79, 5, 105)
cf2 <- c(-96.64, 5, 5, 105)
cf3 <- c(-95.96, 5, 5, 5, 105)
cf4 <- c(-94.97, 5, 5, 5, 5, 105)
cf5 <- c(-93.54, 5, 5, 5, 5, 5, 105)
cf6 <- c(-64.7, 0, 0, 0, 0, 0, 0, 100)
y0<-ytm(cf0)
y0
y1<-ytm(cf1)
y1
bonds<-list(cf0,cf1,cf2,cf3, cf4,cf5,cf6)
N<-length(bonds)
N
res<-NULL
for(i in (1:N))
{
    res<-c(res, ytm(as.vector(bonds[[i]])))
}
dim(res) <-c(2,N)
res
plot(res[2,],res[1,],type='b') 
pr_b<-bondprc(100, 0, 7, 0.064417)
pr_b
```
![s01222606152022.png](img/s01222606152022.png)
## R中的数据输入
国际数据
• 谷歌金融服务：
finance.google.com
• 雅虎金融服务：
finance.yahoo.com
• 国际能源信息署 (EIA) - 国际能源年度 - 国际能源数据和分析：
www.eia.doe.gov/emeu/iea
• 来自世界银行/世界银行数据与研究的数据
econ.worldbank.org
• 来自世界贸易组织的国际贸易和关税数据
(WTO) / 世界贸易组织 (WTO) – 国际贸易和关税数据：
www.wto.org/english/res_e/statis_e/statis_e.htm
• 统一的联合国数据访问系统 联合国数据：
data.un.org
• 货币报价历史 - FXHistory 服务：
www.oanda.com/convert/fxhistory
• 全球财务数据（大部分数据只有付费订阅才能获得）：
www.globalfindata.com
• 经济合作与发展组织 (OECD) 网站 – OECD Online：
www.oecd.org
可以得到的价格数据都是雅虎上的数据。雅虎财经的数据为我们提供了开盘价、高价、低价、收盘价和交易量的数据。
可以以多种方式将 Yahoo Finance 数据导入 R：
* 数据加载到 CSV 文件中并将 CSV 文件加载到 R 中。
* 使用 R 包，例如 quantmod 包和 getSymbols 命令将数据直接提取到 R 中。

注意：第二种方法不太稳定并且可能不可用。
### 例：世界银行
有几个包可以从 R 中访问世界银行数据。
可能最多的是最近的``wbstats``。 它的``wb_search``函数处理查找相关数据集的任务。
fromWB.R 文件：
```R{.line-numbers}
library(tidyverse) 
library(wbstats)
# search for a dataset of interest
#df1_bond<-wb_search(pattern ="bond") %>% head
df1_bond<-wb_search(pattern ="bond")
df1_ed<-wb_search(pattern = "education")
df1_bond %>% head
```
## 即期和远期利率