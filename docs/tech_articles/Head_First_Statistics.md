

# 第一章 信息图形化

有一个问题，为什么要把数据图形化，直接观察数据不可以吗？

```
答：如果数据比较简单，仅仅是查询并得到一个结果，是可以直接读取数据的。
但如果想要清晰地看出数据隐含的趋势，给你一堆数据恐怕会看的头昏眼花。
图形可以有效地发现数据隐含的模式和趋势，能快速了解数据的动向。
```

## 频数

频数就是在一个特定区间内统计对象的数目。    

例如，一个班有35个男生，25个女生，那么，男生的频数就是35，女生的频数就是25。

## 频数密度

频数密度是指分组数据中的频数的密集度。  

计算公式为：

$$
频数密度=\frac{频数}{组距}
$$

## 累积频数

到某个特定数值为止的总频数。

# 第二章 集中趋势的度量

## 平均数

### 均值

所有数字加起来除以总个数。

计算公式为：

$$
\mu=\frac{\sum x}{n}
$$

### 中位数

一组数据按顺序排列后最中间的值。

### 众数

众数是频数最多的类别。

## 异常值

与其他值相比明显偏大或偏小的值。

## 全距/极差

极差可以简单的比较数据集的分散程度。    

极差只能给出数据集的宽度，不能看出数据在上下界的分布情况。

## 四分位数

把一批数据按顺序排列，等距分为四份，两份之间称为四分位数。

- 最小的称为`下四分位数`，简称`Q1`

- 中间的称为`中位数`，简称`Q2`

- 最大的称为`上四分位数`，简称`Q3`

### 四分位距

$$
四分位距=上四分位数-下四分位数
$$

假设一组数据集，包含n个数值，求上四分位数和下四分位数。

$$
下四分位数位置=\frac{n}{4}
$$

$$
上四分位数位置=\frac{3n}{4}
$$

```
如果结果不是整数，就向上取整。
四分位距取得是中间两份数据集，也是整个数据集的一半数据。
```

为什么要使用四分位距？

```
使用全距数据容易受异常值的影响，而取四分位距是可以排除异常值的一种方法。
```

## 方差

```text
定义：数值与均值的距离的平方数的均值。
```

计算公式：

$$
\sigma^2=\frac{\sum (x-\mu)^2}{n}
$$

方差虽然可以描述数据集的离散程度，但并不是特别直观。
标准差可以解决这个问题。

## 标准差

$$
\sigma=\sqrt{\frac{\sum (x-\mu)^2}{n}}
$$

方差速算公式推导：

$$
\begin{aligned}
\sigma
    &=\frac{\sum (x-\mu)^2}{n}\\
    &=\frac{(\sum x^2 - 2x\mu + \mu^2)}{n}\\
    &=\frac{\sum x^2}{n} - \frac{\sum 2x\mu}{n} + \frac{\sum \mu^2}{n}\\
    &=\frac{\sum x^2}{n} - \frac{2\mu\sum x}{n} + \frac{\cancel{\sum} \mu^2}{\cancel{n}}\\
    &=\frac{\sum x^2}{n} - 2\mu^2 + \mu^2\\
    &=\frac{\sum x^2}{n} - \mu^2\\
\end{aligned}
$$

## 标准分z

假设某组数据集的均值为$\mu$, 标准差为$\sigma$ , 某数值x的标准分为：

$$
z=\frac{x-\mu}{\sigma}
$$

```
标准分可以比较不同数据集的数值。
```

# 第三章 概率计算

## 单个事件的概率

事件A发生的概率：

$$
P(A)=\frac{n(A)}{n(S)}

$$

```text
n(A)：事件A可能发生的次数
n(S)：所有事件可能发生的总次数
```

S被称为`样本空间`，或`概率空间`。   

A的对立事件通常记作“`A'`”

## 两个事件的概率

事件A或B发生的概率：

$$
P(A \cup B)=P(A) + P(B) - P(A \cap B)

$$

A、B同时发生的概率：

$$
P(A \cap B)=P(A) * P(B | A)

$$

## 已有条件下的事件概率

已知B发生的情况下A发生的概率：

$$
P(A | B)=\frac{P(A \cap B)}{P(B)}
$$

P(A | B)与$P(A \cap B)$的区别： 
$P(A \cap B)$没有任何假设的前提，而P(A | B)是在B已发生发情况下，两个的概率空间不一样。

## 贝叶斯定理

$$
\begin{aligned}
P(A | B)
    &=\frac{P(A \cap B)}{P(B)}\\
    &=\frac{P(A) * P(B | A)}{P(A) * P(B | A) + P(A') * P(B | A')}\\
\end{aligned}
$$

概率图：

![概率树](https://www.hualigs.cn/image/6092abeff23f5.jpg)

## 独立事件与互斥事件

```text
如果两个事件A和B为独立事件，则说明A与B互不影响彼此的概率。
如果A和B互为互斥事件，则说明两者无交集，也就是P(A∩B)=0。
```

# 第四章 离散概率分布

## 期望

使用期望来预测结果：

$$
E(X)=\sum xP(X=x)
$$

## 概率分布的方差与标准差

### 方差

计算公式：

$$
\begin{aligned}
Var(X)
    &=E(X-\mu)^2\\
    &=\sum (x-\mu)^2 P(X=x)\\
\end{aligned}
$$

### 标准差

计算公式：

$$
\sigma=\sqrt{Var(x)}
$$

## 变量X的线性变化的期望与标准差

假设Y=aX+b,那么E(Y)的计算公式为：

$$
\begin{aligned}
E(Y)
    &=E(aX+b)\\
    &=aE(X)+b\\
\end{aligned}
$$

Y的标准差为：

$$
\begin{aligned}
\sqrt{Var(Y)}
    &=\sqrt{Var(aX+b)}\\
    &=a^2 \sqrt{Var(x)}\\
\end{aligned}
$$

## 独立观测值的期望与方差

期望：

$$
E(X_1 + X_2 + X_3 + …… + X_n)=nE(X)
$$

方差

$$
Var(X_1 + X_2 + X_3 + …… + X_n)=nVar(X)
$$

## 多个独立随机变量的期望与方差

假设有两台游戏机，其中一台玩一局赢钱的期望为E(X)=5，另外一台玩一局赢钱的期望为E(Y)=10，那么两台游戏机各玩一局赢钱的期望应该是E(X+Y)=E(X)+E(Y)=5+10=15。

多个独立随机变量的期望：

$$
E(X+Y)=E(X)+E(Y)
$$

多个独立随机变量的方差：

$$
Var(X+Y)=Var(X)+Var(Y)
$$

如果是两个独立随机变量相减，期望的计算：

$$
E(X-Y)=E(X)-E(Y)
$$

方差：

$$
Var(X-Y)=Var(X)+Var(Y)
$$

```
方差依然是相加的原因在于，两个变量会增大变异性。
```

两个变量的线性变换，期望的计算：

相加

$$
E(aX+bY)=E(aX)+E(bY)
$$

方差：

$$
Var(aX+bY)=a^2Var(X)+b^2Var(Y)
$$

相减，期望计算：

$$
E(aX+bY)=E(aX)-E(bY)
$$

方差：

$$
Var(aX-bY)=a^2Var(X)+b^2Var(Y)
$$

# 第五章 排列与组合

## 计算排列组合的所有可能结果数目：阶乘

假设有n个独立元素，那么这n个元素的排列方式共有：

$$
n! = n * (n-1) * (n-2) * …… * 3 * 2 * 1
$$

也就是共有n!(读作n的阶乘)中方式。

```text
0！是多少呢？
n！的含义是取从n到1的所有正整数相乘，也就是说，0!是取从0到1的正整数相乘，也就是1。
```

## 分组内不计顺序的组合

假设有n个元素，其中k个元素为同一类，排序时忽略顺序，那么排列方式共有：

$$
s = \frac{n!}{k!}
$$

假设有n个元素，其中k个元素为同一类，j个元素为另一类，排序时忽略顺序，那么排列方式共有：

$$
s = \frac{n!}{k!j!}
$$

```text
如何理解公式的意思呢？
假设有4个元素，a,b,c，b、c为同一类，忽略b、c的排列顺序，那么排列结果又一下几种：
1、a b c 
2、a c b
3、b a c
4、b c a 
5、c a b 
6、c b a 

其中，1、2算一种排列，3、5为一种排序，4、6为一种排序，也就是说，原本排序方式共有3！种，去除重复的，
最终只有3种，同一个位置上放b或者c都是一样的，也就是说，a的位置确定好后，b和c的位置也就无所谓了，
那么a总共有3个位置可选。
```

## 从n个元素中选取r个元素进行排列

计算方式：

$$
A^r_n = \frac{n!}{(n-r)!}
$$

## 从n个元素中选取r个元素进行组合

$$
C^r_n = \frac{n!}{r!(n-r)!}
$$

# 第五章 几何分布、二项分布和泊松分布

## 几何分布

假设单次成功概率为p，失败概率为q=1-p，那么，第r次成功的概率为：

$$
P(X=r) = q^{r-1}p
$$

```
公式的意思就是，假设第r次才成功，那么前面的r-1次都是失败的。
```

### 几何分布与不等式

如果说试验r次以上才取得第一次成功，那么公式应该写成：

$$
P(X > r) = q^r
$$

也就是说，前r次必须全部是失败的。

再来看P(X ≤ r)，意思是试验r次或r次以内就能获得第一次成功的概率，可以看出，P(X ≤ r)+P(X > r)=1。

$$
\begin{aligned}
P(X ≤ r)
    &=1-P(X > r)\\
    &=1-q^r\\
\end{aligned}
$$

如果一个变量X的概率符合几何分布，且单词试验成功的概率为p，那么可以记作：

$$
X \sim Geo(p)
$$

### 几何分布的期望与方差

期望的计算公式：

$$
E(X) = \frac{1}{p}
$$

这个公式相对是比较好理解的，假如单次成功的概率是0.2，也就意味着试验5次可能会成功一次，就是1/0.2=5。

如果X ~ Geo(p)，那么方差为：

$$
Var(X) = \frac{q}{p^2}
$$

## 二项分布

假设单次成功的概率为p，失败的概率为q，那么n次试验中，r次成功的概率为：

$$
P(X=r) = C^r_np^rq^{n-r}
$$

其中，$C^r_n = \frac{n!}{r!(n-r)!}$。

记作：

$$
X \sim B(n, p)
$$

二项分布的期望：

$$
E(X) = np
$$

二项分布的方差：

$$
Var(X) = npq
$$

## 泊松分布

已知事件为独立事件，$\lambda$是给定区间内的事件平均发生次数，那么计算特定区间内事件的发生次数r的概率为：

$$
P(X=r) = \frac{e^{-\lambda}\lambda^r}{r!}
$$

期望计算方式：

$$
E(X) = \lambda
$$

方差计算方式为：

$$
Var(X) = \lambda
$$

如果X符合泊松分布，每个区间事件平均发生次数为$\lambda$，那么可以记作：

$$
X \sim Po(\lambda)
$$

## 总结

几何分布、二项分布和泊松分布的使用场景是什么？

```
· 几何分布
    条件：进行一系列独立试验，每次试验成功的概率相同。
    目的：获得第一次成功时共进行了几次试验。
· 二项分布
    条件：进行一系列次数有限的独立试验，每次试验成功的概率相同。
    目的：在n次试验中能成功多少次。
· 泊松分布：
    条件：已知给定区间内的事件平均发生次数，并且是有限的。
    目的：在给定区间内事件发生的次数。
```

|类别|条件|目的|
|-|-|-|
|几何分布|进行一系列独立试验，每次试验成功的概率相同。|获得第一次成功时共进行了几次试验。|
|二项分布|进行一系列次数有限的独立试验，每次试验成功的概率相同。|在n次试验中能成功多少次。|
|泊松分布|已知给定区间内的事件平均发生次数，并且是有限的。|在给定区间内事件发生的次数。|


# 第六章 正态分布

## 单个独立变量的正太分布

几何分布、二项分布、泊松分布都是离散型数据的概率分布情况，如果数据是连续的，我们需要的是某一区间内的概率，就需要用到`概率密度函数`了。

- 概率密度与概率的区别是什么？

  概率密度是表示概率的一种方式，并不是概率本身的大小。概率本身等于概率密度乘区间的宽度。

- 如果要求某个数值的概率，那么一定为0，原因如下：

  如果只有一个数值，那么区间的宽度是0，0乘概率密度，最终还是0。

正态分布在日常生活中是很常见的概率分布，比如一个班级里学生身高的分布、成绩的分布等等。

正态分布的图形具有对称性，对称轴就是X = $\mu$，均值和中位数相等，并且概率密度最大。图形如下：

![](https://www.hualigs.cn/image/6098d8e8cf4a2.jpg)

$\sigma^2$ 表示曲线的分散性，越大曲线就越扁平。

如果连续型数据变量X符合正态分布，均值为$\mu$，标准差为$\sigma$，那么可以记作：

$$
X \sim N(\mu, \sigma^2)
$$

- 如何求正态分布的概率呢？

  - 第一步，确定均值和标准差；

  - 第二步，将正态分布标准化，也就是转换成均值为0，标准差为1的正态分布；

  - 第三步，查询概率表，找到P(X<x)的数值，接着根据需求求出最终结果。

- 如何标准化？

  使用标准分公式：$z = \frac{x-\mu}{\sigma}$，转换成$\frac{x-\mu}{\sigma} \sim N(0, 1)$。

## 两个独立变量的正太分布组合

如果$X \sim N(\mu_x, \sigma^2_x)$且$Y \sim N(\mu_y, \sigma^2_y)$，那么：

$$
X \pm Y \sim N(\mu, \sigma^2) \text{，其中}\mu = \mu_x \pm \mu_y, \sigma^2 = \sigma_x^2 \pm \sigma_y^2
$$

## 线性变换后的正态分布

如果$X \sim N(\mu, \sigma^2)$，线性变换后X变成aX+b，那么：

$$
aX+b \sim N(a\mu+b, a^2\sigma^2)
$$

# 第七章 统计抽样

## 简单随机抽样

简单随机抽样的两大类：重复（放回）抽样和不重复（不放回）抽样。

## 分层抽样

将总体按某种特征分成多个组，每个组称为层，从每个层里进行简单随机抽样。

## 总体均值、方差与样本均值、方差的关系

$$
\hat{\mu}=\overline{x}=\frac{\sum x}{n}，\overline{x}为样本均值，n为样本容量
$$

$$
s^2=\frac{\sum (x-\mu)^2}{n-1}
$$

- 为什么是n-1，而不是n？

  总的来看，总体方差总是比样本方差要大的，为了消除这一点误差，把分母减1，显然会略微增大求得的方差值，和总体方差的实际结果就更加靠近了。

## 样本的分布形态

$$
如果X \sim N(\mu, \sigma^2)，那么\overline X \sim N(\mu, \frac{\sigma^2}{n})
$$

## 中心极限定理

如果X不符合正态分布，那么当n很大的时候，$\overline X$也符合正态分布。一般来说，当n>30，那么$\overline X \sim N(\mu, \frac{\sigma^2}{n})$。

中心极限定理的使用场景：

### 二项分布中使用中心极限定理

假设有一个总体，$X \sim B(n, \sigma^2)$，n>30，那么，$\mu = np, \sigma^2 = npq$，根据中心极限定理，代入样本公式：

$$
\overline X \sim N(np, pq)
$$

### 泊松分布中使用中心极限定理

假设总体符合$X \sim Po(\lambda)$，n>30，在泊松分布中，$\mu = \sigma^2 = \lambda$，那么：

$$
\overline X \sim N(\lambda, \frac{\lambda}{n})
$$

## 置信区间：总体均值所在的区间

如果我们希望总体均值$\mu$有95%的概率处于（a, b）之间，那么（a, b）就是`置信区间`，95%就是`置信水平`。

如何求置信区间呢？

- 第一步，选择总体统计量，也就是想要知道的某个特征的均值，记为$\mu$；

- 第二步，计算样本的均值和方差，求出样本的分布，$\overline X \sim N(\mu, \frac{\sigma^2}{n})$;

- 第三步，确定置信水平，大多数情况下选择95%；

- 第四步，求出置信区间的上下限。

![](https://www.hualigs.cn/image/609a2717ba696.jpg)

看上图，可以用正态分布求置信区间。那么首先，需要对样本的正态分布做一个标准化，$z = \frac{x-\mu}{\sigma}$



![](https://www.hualigs.cn/image/609a28ee2433b.jpg)



![](https://www.hualigs.cn/image/609a295999c28.jpg)

经过转换，得到下式：



![](https://www.hualigs.cn/image/609a29b953d5b.jpg)

$\overline X$就是样本均值，代入即可得到置信水平95%下的置信区间。

计算过程可以简化如下：

$$
误差范围=c*统计量的标准差
$$

$$
置信区间为：统计量 \pm 误差范围
$$

```text
c的数值取决于置信水平，下表是不同置信水平下c的取值：
```

|||
|-|-|
|置信水平|c值|
|90%|1.64|
|95%|1.96|
|99%|2.58|


## t分布

如果总体符合正态分布，$\sigma^2$未知，样本比较小，那么$\overline X$符合t分布。

$$
T \sim t(v),T为检验统计量(标准分），v是自由度，v=n-1
$$

T的计算公式：

$$
T=\frac{\overline X-\mu}{\frac{s}{\sqrt{n}}}
$$

二项分布和泊松分布同样可以用t分布来求置信区间。

# 第八章 假设检验

假设检验的六个步骤：

1. 确定要进行检验的假设；

2. 选择检验统计量；

3. 确定用于做决策的拒绝域；

4. 求出检验统计量的p值，也就是假设为真的情况下，试验结果的可信度；

5. 查看样本结果是否在拒绝域内；

6. 做出决策

## 1、确定要进行检验的假设

原假设我们记作$H_0$，对立的假设称为备择假设，记作$H_1$。

- 原假设和备择假设需要涵盖所有的结果吗？

  答：不需要。

## 2、选择检验统计量

根据实际案例看属于哪一类概率分布。

## 3、确定用于做决策的拒绝域

- 什么是拒绝域？

  与原假设相反的一组极端的数值，如果试验结果落在这个区间，那么就有充足的理由相信原假设不成立，这个区间就被称为拒绝域。

- 如何确定拒绝域？

  拒绝域有一个分界点，称为`临界值`，记作`c`。

- 如何求拒绝域？

  先确定`显著性水平`，显著性水平指的是样本结果不在拒绝域有多大的概率，通常用百分比表示。

### 单尾检验

- **左尾检测**：如果备择假设包含一个`<`符号，那么就是左尾检测；

- **右尾检测**：如果备择假设包含一个`>`符号，那么就是右尾检测；

### 双尾检验

如果备择假设为不等式，也就是包含`≠`，那就是双尾检验。

总结：判断单尾检验还是双尾检验，就看备择假设。

### 显著性水平

看一下显著性水平和置信水平的关系

![](https://www.hualigs.cn/image/609bb58f00653.jpg)

如果样本结果落在了置信水平，那么说明$H_0$成立，原假设成立；如果落在了显著性水平，说明$H_1$成立，原假设不成立。

显著性水平就是**小概率事件**。我们首先假设$H_0$成立，显著性水平为0.05，在此假设情况下，我们的样本或者实验结果却恰好落在了显著性水平内，那么我们就可以认为小概率事件发生了，毕竟该事件发生的概率不到5%。小概率事件一发生，我们就可以认为原假设是错误的。但是，这个时候的原假设一定错误吗？不一定。这个时候原假设依然有概率是正确的，而且这个概率就是小概率事件的概率，并且它又刚好和显著性水平所设置的值相等。也就是说因为这个小概率事件的发生，我们就要做出$H_0$是错误的决策，但是实际上$H_0$还是有小概率成立的。

## 假设检验决策中的两类错误

- 第一类错误：拒绝了事实为真的原假设；

- 第二类错误：接受了事实为假的原假设。

图表所示：

||||
|-|-|-|
||接受$H_0$|接受$H_0$|
|$H_0$真||第一类错误|
|$H_0$假|第二类错误||


### 第一类错误的概率

$$
P(第一类错误) = \alpha, \alpha为显著性水平
$$

### 第二类错误的概率

$$
P(第一类错误) = \beta
$$

- 如何求$\beta$？

# 第九章 $\chi^2$分布

$\chi^2$统计量是用来统计观察频数与期望频数的总差值的大小。

计算公式为：

$$
\chi^2 = \sum \frac{(O-E)^2}{E},O是观察频数，E是期望频数
$$

- $\chi^2$分布的两个主要用途：

  - 检验拟合优度，检验一组给定的数据与指定分布的吻合程度；

  - 检验两个变量的独立性，看两个变量是否存在关联性。

当$\nu$等于1或2时，$\chi^2$分布图如下：



![](https://www.hualigs.cn/image/609cc4e3da1b5.jpg)

$\nu$等于1或2，$\chi^2$的值越小概率越大，观察频数可能接近期望频数。

当$\nu$大于2时，$\chi^2$分布图如下：



![](https://www.hualigs.cn/image/609cc538f0db0.jpg)

$\chi^2$分布可记作：

$$
X^2 \sim \chi^2(\nu)
$$

