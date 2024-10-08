## BCH码
### 有限域
#### 有限域的定义
**域**：

一个域（Field）是指可以进行加、减、乘、除运算的一些对象的集合。

对于集合 $G$，定义符号 “+$” 表示一种二元运算，如果满足下面的条件则称该集合为**阿贝尔群**：
- （1）该运算是交换律。即对于任意 $a，b∈G$，有 $a+b=b+a$。
- （2）该运算是结合律。即对于任意 $a，b，c∈G$，有 $(a+b)+c=a+(b+c)$。
- （3）该运算具有可以用“0”表示的幺元（Identity Element）。即对于任意 $a∈G$，有 $a+0=0+a=a$。
- （4）对于任意一个元素 $a∈G$，均存在一个元素 $-a∈G$ 满足 $a+(-a)=(−a)+a=0$，其中元素 $-a$ 称为 $a$ 的加法逆。

因此，一个阿贝尔群通常可以记作 $\{G，+,0\}$。注意：在上面的定义中用了符号 “+” 表示的 “加法” 运算。有时候阿贝尔群也可以改用符号 “·” 表示的 “乘法” 运算来进行定义，这种情况下幺元可以用符号 “1” 来表示，而该群可以记作 $\{G，·,1\}$，此时元素$a ∈ G$的乘法逆则可以表示为$a^{-1}$

**有限域/伽罗华域(Galois Field)**：

对于有限个元素构成的一个集合 $F$，定义了分别用 “+” 和 “·” 表示的加法和乘法两种二元运算，如果满足下列条件则称集合 $F$ 为有限域：
- （1）$\{F，+,0\}$ 是一个阿贝尔群。
- （2）$\{F-\{0\}，·,1\}$ 也是一个阿贝尔群，即集合 $F$ 中的非零元素在乘法运算下也构成一个阿贝尔群。
- （3）乘法满足分配律：$a·(b+c)=a·b+a·c$。

综上，一个有限域常常记作 $\{F，+, · \}$.

显然，由所有实数组成的集合 $\mathbb R$ 在正常的加法和乘法运算下是一个域（但不是有限域）；集合 $F=\{0,1\}$ 在模 2 加法和乘法运算下构成一个有限域，该域称为**二进制域，记作$GF（2）$**。
#### 域的特征和基域
包含 $q$ 个元素的有限域 GF($q$) 存在的充要条件是 $q=p^m$，式中 $p$ 是一个素数，$m$ 是一个正整数。此外还可以证明，如果 GF($q$) 存在，则该域在同构（Isomorphism）意义下是唯一的，这意味着任何两个相同尺寸的有限域在重新命名元素之后可以相互转化。

对于某素数 $p$，当 $q=p$ 时得到的有限域 $GF(q)$ 可以表示成 $GF(p)=\{0,1,2,\cdots,p-1\}$，该域中的两种运算是模 $p$ 加法和乘法，例如 GF(5)=$\{0,1,2,3,4\}$；当 $q=p^m$ 时得到的有限域$GF(q)=GF(p^m)$称为$GF(p)$的扩展域，其中 $m≥2$，而$GF(p)$称为$GF(q)$的基域，$p$ 称为有限域 GF($p^m$) 的特征。
#### 有限域上的多项式
为了便于研究扩展域的结构，下面来定义有限域上的多项式。有限域 GF($p$) 上的 $m$ 阶多项式可以表示为
$$ g(X)=g_mX^m+\cdots+g_2X^2+g_1X+g_0 \tag{5-1} $$
式中，$g_i$ 是取自 GF($p$) 上的元素，$0≤i≤m$，且 $g_m≠0$。定义在有限域 GF($p$) 上的多项式之间的加法和乘法遵循正常的加法和乘法规则，但是多项式系数之间的加法和乘法要按照模 $p$ 计算。

如果式 (5-1) 中的 $g_m=1$，则该多项式称为首一多项式（Monic Polynomial）。

如果定义在 GF($p$) 上的 $m$ 阶多项式不能分解为同一个域上的两个低阶多项式的乘积，则该多项式为不可约多项式（Irreducible Polynomial）。例如在有限域 GF(2) 上，$X^2+X+1$ 是一个不可约多项式，而 $X^2+1$ 则不是一个不可约多项式，因为 $X^2+1=(X+1)^2$。

同时满足首一和不可约性质的多项式称为素多项式（Prime Polynomial）。

有限域 GF($p$) 上的 $m$ 阶多项式会有 $m$ 个根（有些可能是重根），但是这些根不一定会在 GF($p$) 上，而可能在 GF($p$) 的某个扩展域上。
#### 扩展域的结构
对于有限域 GF($p$) 上的多项式，根据定义可知阶小于 $m$ 的多项式一共有 $p^m$ 个，其中包括 $g(X)=0$ 和 $g(X)=1$ 两个特殊多项式。

假设 $g(X)$ 是一个 GF($p$) 上的 $m$ 阶素多项式，下面考虑一个由 GF($p$) 上所有阶小于 $m$ 的多项式组成的集合，该集合中元素之间的运算遵循正常的加法和模 $g(X)$ 的多项式乘法，可以证明，这样得到的多项式集合构成了一个有限域 GF($p^m$)，显然该域是 GF($p$) 的一个扩展域。

【例 5-1】 利用有限域 GF(2)上的素多项式 $X^2+X+1$ 来构造扩展域 GF($2^2$)=GF(4)。

【解】 显然，GF(2)上阶小于 2 的所有多项式为：0，1，X 和 X+1。这些元素构成的集合便是有限域 GF(4)，即
$$ GF(4)=\{0,1,X,X+1\} \tag{5-2} $$
GF(4) 元素之间的加法和乘法运算规则分别如表 5-2 和表 5-3 所示。注意在表 5-3 中两个多项式的相乘结果是模 X^2+X+1 之后的余式。
表 5-3  GF(4) 的加法
| + | 0 | 1 | X | X+1 |
| --- | --- | --- | --- | --- |
| 0 | 0 | 1 | X | X+1 |
| 1 | 1 | 0 | X+1 | X |
| X | X | X+1 | 0 | 1 |
| X+1 | X+1 | X | 1 | 0 |

| . | 0 | 1 | X | X+1 |
| --- | --- | --- | --- | --- |
| 0 | 0 | 0 | 0 | 0 |
| 1 | 0 | 1 | X | X |
| X | 0 | X | X+1 | 1 |
| X+1 | 0 | X+1 | 1 | X |

此外，从表 5-3 的结果可以发现：GF(4) 中的所有非零元素均可表示成 X 的某次幂，即$X=X^1，X+1=X^2，1=X^3$。

当计算扩展域中元素之间加法的时候，使用多项式形式或向量形式比较简便；而当计算元素之间乘法的时候，使用矩阵形式比较简便。例如$X^2+X+1$和$X^2+1$两个元素，相加的结果为$(X^2+X+1)+(X^2+1)=X$，而这两个元素对应的矩阵形式分别为 $X^5$和$X^6$，于是这两个元素之间的相乘结果为$(X^2+X+1)(X^2+1)=X^5X^6=X^{11}=X^4=X^2+X$。
#### 本原元素和本原多项式
对于任意一个非零元素 $\beta \in GF(q)$，满足等式 $\beta^i=1$ 的最小整数 $i$ 称为元素 $\beta$ 的阶。可以证明，等式 $\beta^{q-1}=1$ 一定成立，所以元素 $\beta$ 的阶的最大值等于 $q-1$。

**本原元素**:如果 GF(q) 的某个非零元素的阶为 $q-1$，则称该元素为本原元素。

本原元素最重要的特性是其每次幂可以生成所在有限域的所有非零元素。此外，本原元素不是唯一的。

有限域 GF($p$) 上阶为 m 的素多项式可能会有多个，所以会有多个构造扩展域 GF($p^m$) 的方法，但是这些扩展域均是同构的。为了分析方便，通常希望 X 是 GF($p^m$) 的一个本原元素，这样的话很容易通过求 X 的各次幂来找到该域中的所有非零元素。

**本原多项式**：设 GF($p^m$) 由素多项式 $g(X)$ 生成，如果$X$是$GF(p^m)$的一个本原元素，则称$g(X)$为本原多项式。可以证明，任意阶的本原多项式都存在，所以对于任意的正整数 m 和任意一个素数 p，均可以生成 X 为本原元素的扩展域$GF(p^m)$，也就是说该域中所有的非零元素都可以表示为$X^i，0<=i<p^m-1$。

另一种等价定义：可以证明，GF(p)上的任意 m 阶素多项式 g(X) 可以整除$X^{p^m}+1$。不过，g(X) 也可能整除$X^i+1$，其中$i<p^m-1$。例如，素多项式$X^4+X^3+X^2+X+1$可以整除$X^{2^4}-1 (X^{15}+1)$，也可以整除$X^5+1$。令 i 表示可以使素多项式 g(X) 整除 $X^i+1$ 的最小整数，如果 $i=p^m-1$，则 g(X) 是一个本原多项式。

常用本原多项式：
| m | 本原多项式 |
| --- | --- |
| 2 |$X^2 + X + 1$|
| 3 |$X^3 + X + 1$|
| 4 |$X^4 + X + 1$|
| 5 |$X^5 + X^2 + 1$|
| 6 |$X^6 + X + 1$|
| 7 |$ X^7 + X^3 + 1$|
| 8 |$X^8 + X^4 + X^3 + X^2 + 1$|
| 9 |$X^9 + X^4 + 1$|
| 10 |$X^{10} + X^3 + 1$|
| 11 |$X^{11} + X^2 + 1$|
| 12 |$X^{12} + X^6 + X^4 + X + 1$|
#### 最小多项式和共轭元素
某个域元素的最小多项式是指以其为根的基域上最低阶的首一多项式。设 β 是 GF(2^m) 上的一个非零元素，则 β 的最小多项式$φ_β(X)$是指系数在$GF(2)$上，且满足$φ_β(β)=0$的最低阶首一多项式。显然，$φ_β(X)$是$GF(2)$上的一个素多项式，可以整除$GF(2)$上以 β 为根的所有其他多项式，例如$f(X)$是$GF(2)$上满足$f(β)=0$的任意一个多项式，则其可以表示成$f(X)=a(X)φ_β(X)$。

接下来讨论如何获得某个域元素的最小多项式。


设$β∈GF(2^m)$且$β≠0$，则必定有等式$β^{2^m}-1=1$，但是对于某个整数$l<m$也可能会有等式$β^{2^l}-1=1$。例如，对于$GF(16)$中的一个元素$β=α^5$，显然$β^3=β^{{2^2}-1}=1$，所以对于该元素 β 有$l=2<m$。

可以证明，任意元素 β∈GF(2^m) 的最小多项式可以表示为
$$ φ_β(X)=\prod_{i=0}^{l-1}(X+\beta^{2^i}) \tag{5-4} $$

上式中 l 是满足$β^{{2^l}-1}=1$的最小整数。由上式可知，除了 β 之外$φ_β(X)$的其他所有根均具有$β^{2^i}$形式（$1<i<l$），所有这些根都称为 β 的共轭。可以证明，一个有限域中任意元素的共轭均会具有相同的阶，于是本原元素的共轭也会是本原元素。但是，具有相同阶的元素之间却不一定是有共轭关系。某个有限域中具有共轭关系的所有元素被称为属于同一个共轭类。

求解元素 β∈GF(q) 的最小多项式的步骤如下：

1）确定 β 的共轭类${β, β^2, β^4, …, β^{2^{l-1}}}$，即所有具有$β^{2^i}$ 形式的元素，式中$0≤i≤l-1$，l 是满足$β^{2^l}=β$的最小正整数；

2）使用式（5-4）来确定$φ_β(X)$，该式便是以 β 的共轭类为根的首一多项式。
利用上述步骤获得的最小多项式$φ_β(X)$一定会是系数在$GF(2)$上的素多项式。

### BCH码
#### BCH码的结构