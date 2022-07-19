# lecture 5
## lecture 3,4 的R语言知识
## 数据类型
R 支持多种基本数据类型和许多派生数据类型。 派生数据类型是使用基本数据类型形成的，其中一些也称为数据结构。
变量是分配给内存位置的名称。 当根据其数据类型声明变量时，系统会为它保留一些内存。
### Numeric
使用 ``numeric(n)`` 命令创建类 ``numeric`` 的对象，其中 ``n`` 是这种类型的元素的数量。 创建一个长度为 ``n`` 的空向量。
```R{.line-numbers}
> x=numeric(5)
> x
[1] 0 0 0 0 0
```
例子2：
```R{.line-numbers}
x=double(1)
x=5
is.double(x)
#[1] TRUE
x=as.integer(x)
is.double(x)
#[1] FALSE
is.integer(x)
#[1] TRUE
```
### Logical
逻辑对象，即 逻辑类型的对象。 此类的对象有两个可能的值：TRUE (true) 和 FALSE (false)，并使用 logical(n) 命令创建，其中 n 是要创建的向量的长度。
```R{.line-numbers}
x=logical(4)
x
[1] FALSE FALSE FALSE FALSE
```
### vector
向量是 R 中的基本数据对象，可以包含相同或不同数据类型的元素。
包含相同数据类型元素的向量称为原子（同质）向量。 原子向量可以有基本的数据类型——字符、整数、复数、布尔值。
可以使用 c( ) 函数创建向量。 一般语法：
``<变量> = c(<逗号分隔的元素>)``
数值类型向量:
```R{.line-numbers}
v <- c(1, 2.6, 3.1)
```
字符类型向量（字符串）
```R{.line-numbers}
v <- c('越南', '中国', '韩国')
```
复合向量
```R{.line-numbers}
v <- c(100, 123.7, '表', 10+2i, '范围')
```
### 在 R 中创建数字序列
如果一个数值序列的元素彼此相差一个（递增序列），或者相差 -1（递减序列），那么您可以只指定所需序列的初始 a 和最终 b 值 - a:b。
```R{.line-numbers}
> x=2:10;
x
[1] 2 3 4 5 6 7 8 9 10
> y=10:2;y
[1] 10 9 8 7 6 5 4 3 2
```
第二个选项是使用 seq() 命令。 用例：
* seq(from, to) - 类似于 a:b
* seq(from, to, by= ) — 设置开始、结束值和步长序列。
```R{.line-numbers}
x=seq(-5,5);x
[1] -5 -4 -3 -2 -1 0 1 2 3 4 5
```
### 数据类
• 向量（vector）—— 是由相同数据类型的元素组成的一维数组。 您可以选择数字、逻辑和字符向量。
• 矩阵（matrix）—— 二维数组，通常是数字。
• 多维数组（array）—— 维数大于二的数组。
• 因子（factor）—— 处理分类数据时使用的结构。
• 列表(list) —— 是可以按编号或名称访问的对象的集合。
• 数据表 (data.frame) —— 是在 R 中工作时最常用的结构。

## R中的数据输入
### 示例1：给变量赋值
控制台输出结果：
```R{.line-numbers}
> 2+2
[1] 4
> a=2+5
> b=a+3
> b
[1] 10
> c<-3
> d<-a+b+c
```
R 语言中的基本数据类型  逻辑 (TRUE & FALSE, T & F) – 逻辑数据类型。
* numeric 是一种允许算术运算的数值类型。
* 整数 (L) - 整数数据，数字数据的一种特殊情况。
* 字符——字符串数据类型。
* complex 是一种用于复数运算的特殊数据类型。

数据存储的对象类型：
* 向量（vector）；
* 矩阵（matrix）；
* 数组（array）；
* 数据表（data frame）；
* 列表（list)

### 示例 2 创建向量并分配值
```R{.line-numbers}
> # создаем числовой вектор
> y<- c(33, 4, 7)
> y
[1] 33 4 7
> is.vector(y)
[1] TRUE
> x <- 1 : 7
> x
[1] 1 2 3 4 5 6 7
> # Используем функцию seq()
> z <- seq(from = 1, to = 7, by = 2)
> z
[1] 1 3 5 7
> x<- seq(1, 10, length = 10)
> x
[1] 1 2 3 4 5 6 7 8 9 10
```
### 示例3 矩阵：符号，按行和列输入值
```R{.line-numbers}
> ma <-matrix(letters[1:12], nrow =4, 
+ dimnames =list(c('row1', 'row2', 'row3','row4'),
+ c('c1', 'c2', 'c3')))
> ma
      c1  c2  c3
row1 "a" "e" "i"
row2 "b" "f" "j"
row3 "c" "g" "k"
row4 "d" "h" "l"
> 
> mrb <-rbind(c(3, 5, 7), c(4, 6, 8))
> mrb
    [,1] [,2] [,3]
[1,] 3    5    7
[2,] 4    6    8
> 
> mrb <-cbind(c(3, 5, 7), c(4, 6, 8))
> mrb
    [,1] [,2]
[1,]  3   4
[2,]  5   6
[3,]  7   8
```
### 示例 4 表 - 数据框
```R{.line-numbers}
> #set.seed(0)
> options(digits =1)
> df <-data.frame(id = LETTERS[1:6],
+ age =runif(6, 24, 30),
+ height =rnorm(6, 170, 2))
> df
  id age height
1 A  28   170
2 B  26   170
3 C  28   168
4 D  28   168
5 E  27   168
6 F  27   173
> df$height
[1] 170 170 168 168 168 173
> is.vector(df$height)
[1] TRUE
> df$age
[1] 28 26 28 28 27 27
```
在 R 中，有几种方法可以指定向量：
1.创建所需类型（逻辑、数字、符号、复数）和给定大小的零向量，然后为元素分配除零以外的值；
2. 设置必要元素的向量。
### 1.函数：
矢量（模式=“数据类型”，长度）
其参数是向量的类型（数字 - numeric、逻辑 - logical、复杂 - complex、符号 - character），用引号指定，向量的长度是正整数。
```R{.line-numbers}
> v5 <- vector(mode = "numeric" ,length = 10)
> v5
[1] 0 0 0 0 0 0 0 0 0 0
> typeof(v5)
[1] "double"
>
```
### 2.函数 c（ombine):
```R{.line-numbers}
v6= c(1,2,3,5,6)
```
要设置向量，请使用函数 c(...) — 直接设置其元素。 这可以使用 ``c()`` 连接函数来完成。 该函数的参数是向量的元素。
### 举例：
让我们使用 scan() 函数创建一个数字向量 y。
```R{.line-numbers}
>v6=scan()
```
之后，按 Enter 键。 控制台会提示
```R{.line-numbers}
1：
```
之后，您可以通过在键盘上键入数据（数字）来输入它们。空格分隔数字：
```R{.line-numbers}
1:2 2
```
按 Enter 表示换行:
```R{.line-numbers}
3: 3 5 6 7
7:
```
双击 Enter 键完成输入。 将显示一条有关已读取矢量元素数量的消息。
```R{.line-numbers}
> v6 = scan()
1: 1
2: 2
3: 3
4: 4
5: 5
6: 6
7: 
Read 6 items
>
```
### 向量函数
R 有许多用于处理向量的有用函数，允许您避免使用循环：
• ``length()`` 是向量的长度。
• ``max()`` 和 ``min()`` - 查找给定的最大和最小元素
向量。
• ``mean()`` — 向量的算术平均值。
• ``range()`` - 由两个元素组成的向量 - 最小值和最大值
其参数（向量）的值。
• ``sum()`` — 矢量元素的总和
• ``prod()`` — 矢量分量的乘积。乙
• ``sort()`` - 返回一个与原始向量长度相同的向量，其中包含元素
按升序排序（默认），或按降序 - ``sort(x,decreasing=T)``(或 ``sort(x,dec=T)``)

### 累积（累积）函数
R中的累积函数包括以下函数：
• ``cumsum(x)`` — 参数 x 上的累积和（向量元素的连续相加）；
• ``cumprod(x)`` - 累积积；
• ``cummax(x)`` — 累积最大值（x 个元素的连续最大值）；
• ``cummin(x)`` — 累积最小值（向量元素上的连续最小值）。
### 表格（数据框）
Tables（数据框）（data frames）——R中最重要的数据类型之一，允许你将各种类型的数据组合在一起。
数据表是一个二维表，其中（与数字矩阵不同）不同的列可以包含不同类型的数据（但一列中的所有数据属于同一类型）。
您可以使用 ``data.frame()`` 函数创建数据框：

## 货币时间价值
### 计算债券的未来价值(будущей стоимости)
1.计算一年后和两年后 100 美元的未来价值，假设每年 10% 的市场/替代收益率。
```R{.line-numbers}
# Настоящая стоимость pv
pv <- 100
# Ставка доходности r
r <- 0.1
# Будущая стоимость fv1
fv1 <- pv* (1 + r)
print(fv1)
## [1] 110
# Будущая стоимость fv2
fv2 <- pv*(1+r)*(1+r)
print(fv2)
## [1] 121
```

2.假设 r（利率）等于 0.1，计算 pv1 和 pv2 的现值，其中 fv1 是一年的未来值，fv2 是两年的未来值。
```R{.line-numbers}
# Вычисление pv1
pv1 <- fv1 / (1 + r)
# Вычисление pv2
pv2 <- fv2/((1+r)*(1+r))
# Печать результатов pv1 and pv2
pv1
## [1] 100
pv2
## [1] 100
```
### 程序——bondprc 价格收益率函数
```R{.line-numbers}
# Справедливая стоимость - function
bondprc <- function(p, r, ttm, y) {
 cf <- c(rep(p * r, times=ttm - 1), p * (1 + r))
 # print(cf)
 cf <- data.frame(cf)
 # cf
 cf$t <- as.numeric(rownames(cf))
 cf$pv_factor <- 1 / (1 + y)^cf$t
 cf$pv <- cf$cf * cf$pv_factor
 sum(cf$pv)
}
# 1 летние
p1<-bondprc(100, 0.05, 1, 0.07)
p1
# 2 летние
p2<-bondprc(100, 0.05, 2, 0.07)
p2# 3 летние
p3<-bondprc(100, 0.055, 3, 0.07)
p3
# 5 летние
p5<-bondprc(100, 0.055, 5, 0.07)
p5
n=2
years=1:n
price_n<-numeric(length=n)
for(j in years) price_n[j]<-bondprc(100,0.0,j,0.06)
# Generate prc_yld
prc_yld <- seq(0.02, 0.4, 0.01)
# Convert prc_yld to data frame
prc_yld <- data.frame(prc_yld)
# Calculate bond price given different yields
for (i in 1:nrow(prc_yld)) {
 prc_yld$price[i] <- bondprc(100, 0.10, 20, prc_yld$prc_yld[i]) 
}
print(prc_yld$price)
# Plot P/YTM relationship
plot(prc_yld$prc_yld, prc_yld$price,
 type = "l",
 col = "blue",
 main = "Price/YTM Relation")
```
### 输入参数
$p$是面值，$r$是票面利率，$𝑡𝑡𝑚$是到期时间，$𝑦$是市场收益率。
```R{.line-numbers}
# Справедливая стоимость - function
bondprc <- function(p, r, ttm, y) 
{
    cf <- c(rep(p * r, times = ttm - 1), p * (1 + r))
    # print(cf)
    cf <- data.frame(cf)
    # cf
    cf$t <- as.numeric(rownames(cf))
    cf$pv_factor <- 1 / (1 + y)^cf$t
    cf$pv <- cf$cf * cf$pv_factor
    sum(cf$pv) 
}
```
## 到期收益率
### 任务1
使用 4.29% 的收益率对 5% 息票债券进行评估，使用收益率来评估面值 100 美元、票面利率 5% 的 5 年期债券。 使用 bondprc 函数：
```R{.line-numbers}
# Справедливая цена облигации
bondprc(p = 100, r = 0.05, ttm = 5, y = 0.0429)
[1] 103.1352
```
### 价格/收益关系
由于收益率变化导致的价格变化可能会因收益率上升或下降而有显着差异。
假设债券面值为 100 美元，票面利率为 10%，期限为 20 年。
```R{.line-numbers}
# Расчет prc_yld
prc_yld <- seq(0.02, 0.4, 0.01) #0.02,0.03,0.04...0.40
# Convert prc_yld to data frame
prc_yld <- data.frame(prc_yld)
# Вычислим
for (i in 1:nrow(prc_yld)) {
 prc_yld$price[i] <- bondprc(100, 0.10, 20, prc_yld$prc_yld[i]) 
}
print(prc_yld$price)
## [1] 230.81147 204.14232 181.54196 162.31105 145.87968 
131.78204 119.63629
## [8] 109.12855 100.00000 92.03667 85.06111 78.92575 
73.50748 68.70334
## [15] 64.42695 60.60563 57.17803 54.09224 51.30420 
48.77640 46.47681
## [22] 44.37799 42.45640 40.69175 39.06651 37.56550 
36.17551 34.88507
## [29] 33.68412 32.56386 31.51656 30.53540 29.61436 
28.74811 27.93191
## [36] 27.16154 26.43322 25.74360 25.08964
# Plot P/YTM relationship
plot(prc_yld, prc_yld$price,
 type = "l",
 col = "blue",
 main = "Price/YTM Relationship")
```
![s23562206142022.png](img/s23562206142022.png)
### 任务 2
要估计债券的收益率，假设债券的市场价格为 95.79 美元。 债券面值为 100 美元，票面利率为 5%，期限为 5 年。
该债券的到期收益率是多少？
将债券的收益率与其他可比证券的收益率进行比较，看看投标价格是太高还是太低。
使用 ``bondprc()``函数使用 5%、6% 和 7% 的收益率计算价格。
```R{.line-numbers}
# Value bond using 5% yield
bondprc(p = 100, r = 0.05, ttm = 5, y = 0.05)
## [1] 100
# Value bond using 7% yield
bondprc(p=100, r=0.05,ttm=5, y=0.07)
## [1] 91.79961
# Value bond using 6% yield
bondprc(p=100, r=0.05,ttm=5,y=0.06)
## [1] 95.78764
```
因此该检查确定了上限和下限，估计收率在6%。
### 任务 3
计算到期收益率 YTM (YieldBonds.R) 的 uniroot 函数。
根据条件，债券价格为95.79美元，面值为100美元，票面利率为5%，期限为5年。
```R{.line-numbers}
# Денежный поток
cf <- c(-95.79, 5, 5, 5, 5, 105)
# Денежный поток
cf1 <- c(-100, 5, 5, 5, 5, 105)
# оценка стоимости облигации
bval <- function(i, cf,t=seq(along = cf)-1)
sum(cf / (1 + i)^t)
# Create ytm() function using uniroot
ytm <- function(cf) 
{
    uniroot(bval, c(0, 1), cf = cf)$root
}
# расчет доходности с помощью функции yield
ytm(cf)
## [1] 0.05999554
```
持续时间和凸度
当利率上升时，债券价格下跌。 因此，人们非常关注特定债券的价格对利率变化的敏感程度。
### 任务1
假设到期收益率为 10%，计算 10% 面值 100 美元、10% 票息、20 年期债券的价格变化。
```R{.line-numbers}
# Расчет PV01
abs(bondprc(p=100, r=0.10, ttm=20, y=0.1001)-bondprc(p=100, r=0.10, ttm=20, y=0.10))
## [1] 0.08507756
```
### 任务 2
计算债券的大致久期
计算面值为 100 美元、票面利率为 10%、期限为 20 年、到期收益率为 10%、预期收益率变化为 1% 的债券的大致久期。
```R{.line-numbers}
# Сегодняшняя цена облигации
px <- bondprc(p = 100, r = 0.1, ttm = 20, y = 0.1)
px
## [1] 100
# Цена облигации если доходность увеличилась на 1%
px_up <- bondprc(p=100, r=0.1, ttm=20, y=0.11)
px_up
## [1] 92.03667
# Цена облигации если доходность уменьшилась на 1%1%
px_down <- bondprc(p=100, r=0.1, ttm=20, y=0.09)
px_down
## [1] 109.1285
# Calculate approximate duration
duration <- (px_down - px_up) / (2 * 100 * 0.01)
duration
## [1] 8.545937
```
### 使用久期评估对债券价格的影响
如果债券的久期已知，则可以估计债券价格的变化，假设收益率有一些预期变化。 使用持续时间的百分比变化，回忆一下公式：
$$
D=\frac{\Delta P}{P}=\frac{-\Delta i}{(1+i) P} \sum_{t=1}^{n} \frac{t \mathrm{C}_{t}}{(1+i)^{t}}+\frac{n N}{(1+i)^{n}}
$$
其中 $D$ 是持续时间，$Δ𝑖$是收益率的变化。
如果预期收益率下降 1%，则根据久期估算百分比变化 (duration_pct_change)。
```R{.line-numbers}
# Оценка изменения
duration_pct_change <- -duration*(-0.01)
duration_pct_change
## [1] 0.08545937
# процентное изменение
duration_bond_change <- duration_pct_change*100
duration_bond_change
## [1] 8.545937
```
## 凸度
债券凸度的近似计算：
```R{.line-numbers}
# Вычисление выпуклости convexity
convexity <- (px_up + px_down - 2 * px) / (px * (0.01)^2)
convexity
## [1] 116.5218
```
估计久期函数：
```R{.line-numbers}
# Справедливая стоимость - function
bondprc_dur <- function(p, r, ttm, y) {
 cf <- c(rep(p * r, times=ttm - 1), p * (1 + r))
 # print(cf)
 cf <- data.frame(cf)
 # cf
 cf$t <- as.numeric(rownames(cf))
 cf$pv_factor <- 1 / (1 + y)^cf$t
 cf$pv <- cf$cf * cf$pv_factor
 cf$discont<-cf$pv*cf$t
 bpv=sum(cf$pv)
 tbpv=sum(cf$discont)/p
 tbpv_mac=sum(cf$discont)/bpv
 tbpv_mod=sum(cf$discont)*(1 / (1 + y))
 
 
 list(bpv,tbpv, tbpv_mac, tbpv_mod)
}
# 1 летние
p1<-bondprc_dur(100, 0.05, 1, 0.07)
p1
# 2 летние
p2<-bondprc_dur(100, 0.05, 2, 0.07)
p2# 3 летние
p3<-bondprc_dur(100, 0.055, 3, 0.07)
p3
# 5 летние
p5<-bondprc_dur(100, 0.055, 5, 0.07)
p5
```