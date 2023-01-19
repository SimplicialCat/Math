#! https://zhuanlan.zhihu.com/p/597957495
# Chevalley-Eilenberg 上同调

# 第一部分 Chevalley-Eilenberg 的原文

Claude Chevalley, Samuel Eilenberg,
_Cohomology Theory of Lie Groups and Lie Algebras_

> 这是一篇重要的文章, 但是写法有些古朴. 我把它整理成现代语言.

## 引言

Lie 群的拓扑与 Lie 代数的联系是这样建立起来的: Lie 群作为微分流形, 其拓扑与 de Rham 上同调有关, 即与微分形式有关; 由所谓"不变积分"的方法可将微分形式化为 $G$-不变微分形式,
而 $G$-不变微分形式完全由单位元一点处的切空间决定; 这个切空间便是 Lie 代数.

- [Chevalley-Eilenberg 上同调](#chevalley-eilenberg-上同调)
- [第一部分 Chevalley-Eilenberg 的原文](#第一部分-chevalley-eilenberg-的原文)
  - [引言](#引言)
  - [第一章 具有群作用的流形](#第一章-具有群作用的流形)
    - [1 流形上的微分形式](#1-流形上的微分形式)
    - [2 等变形式](#2-等变形式)
    - [3 平均法](#3-平均法)
    - [4 微分形式在圈上积分](#4-微分形式在圈上积分)
    - [5 de Rham 定理](#5-de-rham-定理)
    - [6 定理 2.1-2.3 的证明](#6-定理-21-23-的证明)
    - [7 二重不变性](#7-二重不变性)
  - [第二章 局部化](#第二章-局部化)
    - [8 可迁作用的情形](#8-可迁作用的情形)
    - [9 左不变微分形式的局部化](#9-左不变微分形式的局部化)
    - [10 等变 $V$-值微分形式的局部化](#10-等变-v-值微分形式的局部化)
    - [11 右平移不变性](#11-右平移不变性)
    - [12 双不变微分形式](#12-双不变微分形式)
    - [13 齐性空间](#13-齐性空间)
  - [第三章 Lie 代数的上同调环](#第三章-lie-代数的上同调环)
    - [14](#14)
    - [15 与 Lie 群的联系](#15-与-lie-群的联系)
    - [16 半单 Lie 代数](#16-半单-lie-代数)
    - [17 酉法](#17-酉法)
    - [18 Hopf 定理](#18-hopf-定理)
    - [19 不变上链](#19-不变上链)
    - [20 Lie 代数表示的双线性型](#20-lie-代数表示的双线性型)
    - [21 Lie 代数的 2 阶与 3 阶上同调](#21-lie-代数的-2-阶与-3-阶上同调)
    - [22 相对上同调](#22-相对上同调)
  - [第四章 关联于 Lie 代数表示的上同调](#第四章-关联于-lie-代数表示的上同调)
    - [23 定义](#23-定义)
    - [24 半单代数的情形](#24-半单代数的情形)
    - [25](#25)
- [第二部分 同调代数](#第二部分-同调代数)
  - [Lie 代数的基础知识](#lie-代数的基础知识)
    - [泛包络代数](#泛包络代数)
    - [左 g-模](#左-g-模)
    - [Casimir 元素](#casimir-元素)
  - [同调代数的基础知识](#同调代数的基础知识)
    - [消解](#消解)
    - [Ext 函子](#ext-函子)
  - [上同调的同调代数定义](#上同调的同调代数定义)
  - [域 $K$ 的 Koszul 消解](#域-k-的-koszul-消解)
  - [半单 Lie 代数的表示完全可约](#半单-lie-代数的表示完全可约)


## 第一章 具有群作用的流形

### 1 流形上的微分形式

略

> 注. 本文讨论 $C^k$ 可微的流形与微分形式, 但我不知道有什么必要考虑不光滑的情形.

### 2 等变形式

设
$\tau \colon G\to \operatorname{Diffeo}(M)$ 是 Lie 群 $G$ 在微分流形 $M$ 上的作用,
$\rho\colon G\to GL(V)$ 是 $G$ 的一个有限维表示.

我们称 $M$ 上的 $V$-值微分形式 $\omega\in\Omega^\bullet(M,V)$ 为**等变微分形式**
(equivariant differential form),
是指对任意 $g\in G$,
$$
\rho_g\cdot \omega = \tau_g^* \omega.
$$

容易说明, 若 $\omega$ 等变,
则 $d\omega$ 等变.
此时称 $d\omega$ **等变恰当**(equivariantly exact).
等变恰当 $q$-形式的空间商掉等变的闭 $q$-形式称为等变上同调
$E^q(M,\rho)$.
对于 $V=\mathbb R$,
$\rho$ 为平凡表示的情形,
记 $E^q(M,\rho)=E^q(M)$.

两个等变形式的外积仍然等变;
因此 $\oplus_{q\geq 0}E^q(M)$ 构成一个环.

等变微分形式构成微分形式空间的子空间,
从而有自然的映射
$$
\pi\colon E^q(M,\rho) \to H_{\mathrm{dR}}^{q}(M,V);
$$

下面我们陈述三个重要的定理,
其证明将在第 6 节给出.

**定理 2.1**

当 $G$ 为紧 Lie 群时
$\pi$ 为单射.

对于紧 Lie 群 $G$,
表示 $\rho$ 总可分解为不可约分量,
此时 $V$-值微分形式唯一地分解到每个不可约分量上,
从而只须考虑 $\rho$ 本身不可约的情形.

下面总假设 $G$ 是连通紧 Lie 群.

**定理 2.2**

若 $\rho$ 为非平凡不可约表示, 则
$$
E^q(M,\rho) = 0.
$$

**定理 2.3**

若 $\rho$ 为平凡表示, $V=\mathbb R$, 则
$$
E^q(M)\simeq H_{\mathrm{dR}}^q(M).
$$

### 3 平均法

紧 Lie 群上有 Haar 测度 $dg$.

对微分形式 $\omega\in\Omega^\bullet(M,V)$,
$g\in G$,
记
$$
\omega^g = \rho(g^{-1})\cdot \tau_g^* \omega.
$$
$g\mapsto \omega^g$ 是 $G$ 到 $\Omega^\bullet(M,V)$ 的连续映射, 从而存在积分
$$
\overline{\omega}:=\int_G \omega^g \,dg.
$$
$\overline{\omega}$ 满足如下性质:
- $d\overline{\omega}=\overline{d\omega}$;
- $\overline{\omega}$ 是等变形式;
- 若 $\omega$ 是等变形式, 则 $\omega = \overline{\omega}$.

> 注. 本文作者将微分形式的拉回 $T^*\omega$ 写成 $\omega T$, 类似函数复合的样子, 我认为很有道理, 因为 $M$ 上的微分形式可以看成 $M$ 到 "微分形式的模空间" $\Omega^q$ 的一个态射, 而这个态射与光滑映射的复合即是微分形式的拉回. 然而这种记号在现代似乎被抛弃了.

### 4 微分形式在圈上积分

对同调类 $a\in H_q(M)$ 与闭形式 $\omega\in\Omega^q(M,V)$,
积分
$$
\int_a \omega
$$
是良定义的,
因为对任意 $(q+1)$-链 $c\in C_{q+1}(M)$,
$$
\int_{\partial c} \omega = \int_{c} d\omega =0.
$$

对光滑映射 $\varphi\colon M_1\to M_2$
有 "换元积分公式"
$$
\int_a \varphi^*\omega = \int_{\varphi_*a}\omega
$$
($a\in H_q(M_1)$, $\omega\in\Omega^q(M_2,V)$).

### 5 de Rham 定理

de Rham 定理说的是
$H_{\mathrm{dR}}^\bullet (M)$
作为分次环同构于奇异上同调
$H^\bullet (M)$.

$H^q(M)$ 与 $H_q(M)$ 对偶.

> 注. 我猜作者用的是 $\mathbb R$ 系数同调. 本文作者之一 Eilenberg 是奇异同调的建立者.

对给定的闭形式 $\omega\in \Omega^q(M)$,
$a\mapsto \int_a\omega$ 是 $H_q(M)$ 上的线性函数,
故存在唯一的上同调类
$f\in H^q(M)$,
使得微分形式在同调类上的积分可表达为上同调类与同调类的配对:
$$
\int_a\omega = \left<f,a\right>.
$$

由此有如下的结论:
若闭形式 $\omega$ 在所有同调类上的积分为 $0$,
则 $\omega$ 为恰当形式.

由前面的结论,
我们得到不变
$E^q(M,\rho)$ 同构于 $H^q(M)$
的若干次直和,
次数等于 $\rho$ 所含的平凡表示的个数.

### 6 定理 2.1-2.3 的证明

首先注意到,
如果一个等变微分形式 $\omega$ 是恰当的,
那么它是等变恰当的.
(注意, 这不是一句废话.)
这是因为, 设 $\omega = d\theta$,
则
$$
d\overline{\theta}=\overline{d\theta}=\overline{\omega}=\omega.
$$
这证明了定理 2.1.

为了证明定理 2.2, 2.3, 我们需要这样一个命题:

**命题**
若连通 Lie 群 $G$ 作用在 $M$ 上,
则对任意同调类 $a\in H_q(M)$,
$(\tau_g)_* a = a$.

这是显然的.

**定理 2.2 的证明**

设 $\omega$ 为闭等变 $V$-值微分形式.
由于
$\rho(g)\cdot \omega = \tau_g^*\omega$,
对任意同调类 $a\in H_q(M)$,
$$
\begin{aligned}
  \rho(g)\cdot \int_a \omega&=\int_a \rho(g)\cdot\omega \\&=\int_a \tau_g^*\omega\\&=\int_{(\tau_g)_*a}\omega=\int_a\omega.
\end{aligned}
$$
由于 $\rho$ 是非平凡不可约表示,
这说明
$$
\int_a\omega=0.
$$
由第 5 节的结论,
这说明 $\omega$ 为恰当形式;
由定理 2.1,
$\omega$ 为等变恰当形式.
这证明了
$$
E^q(M,\rho)=0.
$$

**定理 2.3 的证明**

设 $\omega\in \Omega^q(M)$ 为闭形式.
我们断言 $\omega - \overline{\omega}$
是恰当形式,
从而 (结合定理 2.1 证明的单射性) 证明
$$
E^q(M)\simeq H_{\mathrm{dR}}^q(M).
$$

对任意 $a\in H_q(M)$,
$$
\begin{aligned}
  \int_a \overline{\omega}&=
  \int_a\int_G \tau_g^* \omega\,dg\\
  &=\int_G \int_a\tau_g^{*}\omega \,dg\\
  &=\int_G \int_{(\tau_g)_* a}\omega\,dg\\
  &=\int_G \int_a \omega\,dg=\int_a\omega,
\end{aligned}
$$
所以
$\omega - \overline{\omega}$
是恰当形式.


### 7 二重不变性

设 $G$, $H$ 两个群作用在流形 $M$ 上.
设 $V=\mathbb R$.
若 $\omega$ 在 $G$ 和 $H$ 的作用下都不变,
则称其为二重不变形式.
由二重不变形式可类似地定义上同调环
$\widetilde{E}^\bullet (M)$.

**定理 7.1**
若 $G$ 与 $H$ 的作用交换,
则
$\widetilde{E}^\bullet(M)\simeq H^\bullet_{\mathrm{dR}}(M)$.

**证明.** 在定理 2.3 中将 $G$ 替换为 $G\times H$. $\square$

## 第二章 局部化

### 8 可迁作用的情形

设紧 Lie 群 $G$ 可迁作用于流形 $M$,
且设 $\tau\colon G\to \operatorname{Diffeo}(M)$ 为单射.

设 $m_0\in M$,
$H$ 为 $G$ 中固定 $m_0$ 的元素构成的子群,
于是 $M$ 等同于右陪集空间 $G/H$.

首先考虑 $H$ 是平凡群的情形,
即 $G$ 左作用于自身.

设 $\mathfrak{g}$ 为 $G$ 的 Lie 代数,
即单位元 $e$ 处的切空间,
则 $G$ 上的 $q$ 阶微分形式 $\omega$ 对应 $\mathfrak{g}$ 上的反对称 $q$-线性形式 $\omega_e$.
若 $\omega$ 是不变微分形式 (这里的不变应理解为左不变, 因为 $G$ 左作用于自身),
则 $\omega_e=0$ 推出 $\omega=0$.

由 $\omega$ 到 $\omega_e$ 的过程称为局部化.

### 9 左不变微分形式的局部化

设 $V=\mathbb R$,
$\rho$ 为平凡表示.
由微分形式外微分的无坐标表达式, 以及 $\omega$ 的左不变性,
可得

**定理 9.1**

$\omega\mapsto \omega_e$ 建立了分次代数同构
$$
E^\bullet (G) \to \wedge^\bullet \mathfrak{g}^*,
$$
且对于 $\omega\in\Omega^q(G)$,
$X_0,\cdots,X_q\in \mathfrak{g}$,
$$
\begin{aligned}
  &(d\omega)_e (X_0,X_1,\cdots,X_q)\\
  &=  \sum_{k<\ell}
  (-1)^{k+\ell+1} \omega_e([X_k,X_\ell],X_0,\cdots,\widehat{X_k},\cdots,\widehat{X_\ell},\cdots,X_q).
\end{aligned}
$$

> 注. 原文中定理 9.1 (以及后文的定理 10.1) 的等式右端还有一个系数 $\dfrac{1}{q+1}$,
> 这是由于古今对于微分形式外积的系数采取的约定不同. 我采用了现代的约定. 参见 Wikipedia, [Exterior derivative](https://en.wikipedia.org/wiki/Exterior_derivative), "In terms of invariant formula" 部分.

### 10 等变 $V$-值微分形式的局部化

设 $\rho\colon G\to GL(V)$
为 $G$ 的群表示,
则 $\rho_*\colon\mathfrak{g}\to\mathfrak{gl}(V)$
为 $\mathfrak{g}$ 的 Lie 代数表示.

**定理 10.1**

$\omega\mapsto \omega_e$ 建立了分次代数同构
$$
E^\bullet (G,\rho) \to \wedge^\bullet \mathfrak{g}^*\otimes V,
$$
且对于 $\omega\in\Omega^q(M)$,
$X_0,\cdots,X_q\in \mathfrak{g}$,
$$
\begin{aligned}
  &(d\omega)_e (X_0,X_1,\cdots,X_q)\\
  &=
  \sum_{k=0}^q(-1)^k \rho_*(X_k)\omega_e(X_0,\cdots,\widehat{X_k},\cdots,X_q)
  \\ &\quad+
  \sum_{k<\ell}
  (-1)^{k+\ell+1} \omega_e([X_k,X_\ell],X_0,\cdots,\widehat{X_k},\cdots,\widehat{X_\ell},\cdots,X_q).
\end{aligned}
$$

### 11 右平移不变性

给定 $h\in G$,
我们考虑右平移变换
$R_h\colon G\to G$,
$g\mapsto gh$.

设 $\rho\colon G\to GL(V)$ 为群表示, $\omega$ 为等变 $V$-值微分形式. 那么
$$
R_h^* \tau_g^*\omega = \tau_g^*R_h^*\omega =\rho(g)\cdot R_h^*\omega.
$$

记共轭运算为 $C_h\colon G\to G$,
$g\mapsto hgh^{-1}$,
则
$$
R_h^*\omega =\rho(h) R_h^* \tau_{h^{-1}}\omega =\rho(h) \cdot C_{h^{-1}}^*\omega.
$$
这说明,
$$
\omega = R_h^*\omega
$$
当且仅当
$$
C_h^*\omega = \rho(h)\cdot\omega.
$$

取 $h=e$ 处的微分, 即得如下结论.

**定理 11.1**

设 $H\subset G$ 是连通的闭子群,
$\mathfrak{h}\subset\mathfrak{g}$ 为对应的 Lie 子代数.

设 $\omega$ 为关于表示 $\rho$ 的 $V$-值等变微分形式,
则
$\omega = R_h^*\omega$ $\forall h\in H$
当且仅当
$$
\rho_*(Y)\omega(X_1,\cdots,X_q)=
\omega([X_1,Y],X_2,\cdots)+\cdots+\omega(\cdots,X_{q-1},[X_q,Y])\,\forall Y\in\mathfrak{h}.
$$

> Lie 括号等于向量场的 Lie 导数. 由张量的 Leibniz 法则, 上式的右端与 Lie 导数 $\mathcal L_Y \omega$ 有关.

### 12 双不变微分形式

左不变且右不变的微分形式称为双不变微分形式.
由定理 11.1,
左不变微分形式 $\omega$ 是双不变微分形式当且仅当
$$
\omega([X_1,Y],X_2,\cdots)+\cdots+\omega(\cdots,X_{q-1},[X_q,Y])=0\,\forall Y\in\mathfrak{g}.
$$

这导致了一个重要结论: **双不变微分形式一定是闭形式**.
对于双不变微分形式 $\omega$, 我们来计算
$(d\omega)_e$.
$$
\begin{aligned}
  &(d\omega)_e(X_0,\cdots,X_q)\\
  &=\sum_{0 \leq i<j \leq q}(-1)^{i+j+1}\omega_e([X_i,X_j],\cdots)\\
  &=\frac{1}{2}\sum_{j=0}^{q} \sum_{i\neq j}
  \epsilon_{ij}\omega_e([X_i,X_j],\cdots),
\end{aligned}
$$
其中 $\epsilon_{ij}$ 是一个正负号,
当 $i<j$ 时等于 $(-1)^{i+j+1}$,
反之则等于 $(-1)^{i+j}$.
对于固定的 $j$,
上式中的求和等于 $0$,
这说明 $(d\omega)_e=0$,
从而 $\omega$ 是闭形式.
例如当 $q=2$ 时,
将形如
$$
\omega_e([X,Y],Z)+\omega_e(X,[Z,Y]) = 0
$$
的 $3$ 个等式相加 (再除以 $2$) 可得
$$
\begin{aligned}
  (d\omega)_e(X,Y,Z)
  =\omega_e([X,Y],Z)+\omega_e([Y,Z],X)+\omega_e([Z,X],Y)=0.
\end{aligned}
$$

> 注. 双不变微分形式一定是闭形式这个结论有更简单的证法: 考虑 $\varphi\colon g\mapsto g^{-1}$,
> 对任意双不变 $k$-形式 $\alpha$ 有 $\varphi^*\alpha = (-1)^{k}\alpha$. 因此
> $$(-1)^{q+1}(d\omega)=\varphi^*(d\omega)=d\varphi^*\omega=(-1)^q d\omega,$$
> 从而 $d\omega =0$.

### 13 齐性空间

现在我们回头看齐性空间 $M=G/H$,
其中 $H$ 是 $G$ 的闭子群.
记 $\pi\colon G\to M$ 为投影.

以 $L_g,R_g$ 分别记 $G$ 上的左右平移,
$\tau_g$ 为 $G$ 在 $M$ 上的作用,
则有
$$
\pi\circ L_g = \tau_g \circ \pi,\  \pi\circ R_h = \pi\ (g\in G, h\in H).
$$

我们希望刻画 $G$ 上怎样的微分形式可表示为 $\pi^*\omega$.

**命题**

对于 $\alpha\in\Omega^q(G,V)$,
存在 $\omega\in \Omega^q(M,V)$
使得 $\alpha = \pi^*\omega$
当且仅当如下两个条件成立:
- 对任意 $X_1,\cdots,X_q\in T_gG$, 只要对某个 $i$ 有 $\pi_*X_i=0$, 就有 $\alpha(X_1,\cdots,X_q) = 0$;
- 对任意 $h\in H$, $R_h^*\alpha = \alpha$.

**证明**

略

## 第三章 Lie 代数的上同调环

### 14
 
设 $\mathfrak{g}$ 为 (零特征) 域 $K$ 上的 Lie 代数.

> 似乎零特征的事实只用在了边缘算子的分母上, 而这个分母在现代约定中不出现.

参照第 9 节的公式,
定义链复形
$$
C^\bullet(\mathfrak{g})=\operatorname{Hom}(\wedge^\bullet \mathfrak{g},K),
$$

> 对于 $\mathfrak{g}$ 有限维的情形, 也可以写 $C^\bullet (\mathfrak{g}) = \wedge^\bullet \mathfrak{g}^*$.

其**上边缘** (coboundary)
算子 $\delta\colon C^q (\mathfrak{g}) \to C^{q+1} (\mathfrak{g})$ 定义为
$$
\begin{aligned}
  &\delta f(X_1,\cdots,X_{q+1})\\
  &=
\sum_{k<l}
(-1)^{k+l+1} f([X_k,X_l],X_1,\cdots,\widehat{X_k},\cdots,\widehat{X_l},\cdots,X_{q+1}).
\end{aligned}
$$

链复形
$C^\bullet(\mathfrak{g})$
的第 $q$ 阶上同调定义为 Lie 代数 $\mathfrak{g}$ 的第 $q$ 阶上同调

### 15 与 Lie 群的联系

### 16 半单 Lie 代数

### 17 酉法

### 18 Hopf 定理

### 19 不变上链

对 $X\in\mathfrak{g}$ 定义
$\mathcal{L}_X\colon C^q(\mathfrak{g}) \to C^q(\mathfrak{g}),$
$$
(\mathcal{L}_X f)
(X_1,\cdots,X_q)=-\sum_{i=1}^q
f(\cdots,[X,X_i],\cdots).
$$

> 原文定义的 $d_X$ 相当于这里的 $-\mathcal{L}_X$. 我将符号改过来的原因, 一是为了模拟 Lie 导数, 二是使得 $X\mapsto \mathcal{L}_X$ 成为 Lie 代数表示. 

若 $\mathcal{L}_X f=0$, 则称 $f$ 为不变上链.
与 12 节相同的计算可以证明每个不变上链都是上圈,
即 $\delta f = 0$.

> 这里的不变上链对应 Lie 群上的双不变微分形式.

可以证明如下的性质:

- $\mathcal{L}_X (f_1\wedge f_2) = (\mathcal{L}_X f_1) \wedge f_2 + f_1\wedge (\mathcal{L}_X f_2)$;
- $[\mathcal{L}_X,\mathcal{L}_Y] = \mathcal{L}_{[X,Y]}$; (原文中这个性质写作 $d_yd_x-d_xd_y=d_{[x,y]}$, 令人迷惑.)
- $\mathcal{L}_X \delta = \delta \mathcal{L}_X$;
- 若 $f$ 为上圈 (即 $\delta f = 0$), 则 $\mathcal{L}_X f$ 为上边缘. (事实上 $\mathcal{L}_X f = \delta i_X f$.)

### 20 Lie 代数表示的双线性型

设 $\rho\colon\mathfrak{g}\to \mathfrak{gl}(V)$ 是 Lie 代数表示.
定义 $\mathfrak{g}$ 上的双线性型
$$
B(x,y) = \operatorname{tr} (\rho(x)\rho(y)).
$$

> 这与今天所谓 Killing 形式有关.

容易验证
$$
B([x,z],y)=B(x,[z,y]).
$$

若 $\mathfrak{g}$ 半单,
且 $\rho$ 为忠实表示,
则双线性型 $B$ 非奇异.



### 21 Lie 代数的 2 阶与 3 阶上同调

### 22 相对上同调

## 第四章 关联于 Lie 代数表示的上同调

### 23 定义

设 $\rho\colon \mathfrak g\to \mathfrak{gl}(V)$ 是 (有限维) Lie 代数表示.
定义
$$
C^\bullet (\mathfrak{g}, V) = \operatorname{Hom}(\wedge^\bullet \mathfrak{g}, V),
$$

前面定义的 $C^\bullet (\mathfrak{g})$ 是 $V$ 取为平凡表示 $K$ 的特例.

$C^\bullet (\mathfrak{g}, V)$ 的上边缘算子
$\delta\colon C^q (\mathfrak{g}, V) \to C^{q+1} (\mathfrak{g},V)$ 定义为
$$
\begin{aligned}
  &\delta f(X_1,\cdots,X_{q+1})\\
  &= \sum_{k=1}^{q+1}
  (-1)^{k+1} \rho(X_i) f(X_1,\cdots,\widehat{X_i},\cdots,X_{q+1})\\
  &+\sum_{k<l}(-1)^{k+l+1} f([X_k,X_l],X_1,\cdots,\widehat{X_k},\cdots,\widehat{X_l},\cdots,X_{q+1}).
\end{aligned}
$$

对 $X\in \mathfrak{g}$, 定义
$\mathcal{L}_X\colon C^q(\mathfrak{g}, V) \to C^q(\mathfrak{g}, V)$,
$$
\begin{aligned}
  &(\mathcal{L}_X f)(X_1,\cdots,X_q)\\&:=
\rho(X)f(X_1,\cdots,X_q)-\sum_{i=1}^q
f(\cdots,[X,X_i],\cdots).
\end{aligned}
$$

> 与前文类似, 这是在模拟 Lie 导数.

定义
$i_X\colon C^{q+1}(\mathfrak{g}, V) \to C^q(\mathfrak{g}, V)$,
$$
(i_X f)(X_1,\cdots,X_q):=
f(X,X_1,\cdots,X_q).
$$

> 这是在模拟内导数 (inner derivative).

由定义直接可得以下结论:

- $[i_X,\mathcal{L}_Y] =   i_X\mathcal{L}_Y - \mathcal{L}_Yi_X = i_{[X,Y]}$;
- $\mathcal{L}_X = i_X \delta + \delta i_X$.
- $[\mathcal{L}_X,\mathcal{L}_Y]=\mathcal{L}_{[X,Y]}$.

第二个结论现在称为 Cartan's magic formula.

注意一个特例,
即 $q=0$ 时
$\mathcal{L}_X f = \rho(X) f$,
此时有
$[\mathcal{L}_X,\mathcal{L}_Y] f= [\rho(X),\rho(Y)]f = \rho([X,Y]) f=\mathcal{L}_{[X,Y]} f$.

### 24 半单代数的情形

**定理 24.1**

若 $\mathfrak{g}$ 为半单 Lie 代数,
$\rho\colon \mathfrak{g} \to \mathfrak{gl}(V)$
为非平凡不可约表示,
则对任意 $q\geq 0$,
$H^q(\mathfrak{g},V)=0$.

### 25

**定理 25.1**

Lie 代数 $\mathfrak{g}$ 半单当且仅当对 $\mathfrak{g}$ 的任意表示 $V$,
都有 $H^1(\mathfrak{g},V) = 0$.

**证明**

(没看懂)

> 在此我推荐苏竞存先生的《流形的拓扑学》, 这本书语言平实, 而包含的思想十分深邃. 我最近在学 Atiyah-Singer 指标定理的前置知识, 包括示性类, 在这本书中得到了很大的启发.

# 第二部分 同调代数

本部分用同调代数的语言解释 Chevalley-Eilenberg 上同调.

参考书:

- 同调代数
  - P. J. Hilton, U. Stammbach, _A Course in Homological Algebra_
  - Weibel, _An Introduction to Homological Algebra_
  - Freyd, _Abelian Categories: An Introduction to the Theory of Functors_
- Lie 群与 Lie 代数
  - A. Kirillov, _Introduction to Lie Groups and Lie Algebras_
  - A. W. Knapp, _Lie Groups, Lie Algebras, and Cohomology_

历史上, Lie 代数上同调的引入有两个动机. 一方面是 Lie 代数扩张 (为了研究 Lie 代数的结构, 我们需要了解半直积), 另一方面是 de Rham 上同调 (也就是 Chevalley-Eilenberg 的原文).

## Lie 代数的基础知识

### 泛包络代数

设有结合代数 $A$ 与 Lie 代数同态 $\mathfrak{g} \to \operatorname{Lie}(A)$,
则称 $A$ 为 $\mathfrak{g}$ 的一个**包络代数**(enveloping algebra),
其中 $\operatorname{Lie}(A)$ 是以 $A$ 为基础向量空间, $[x,y]=xy-yx$ 为 Lie 括号构成的 Lie 代数.

$\mathfrak{g}$ 的**泛包络代数** (universal enveloping algebra) $U\mathfrak{g}$ 是满足泛性质的包络代数, 即是其包络代数范畴中的始对象.

泛包络代数的具体构造来自张量代数 $T\mathfrak{g}$,
定义
$$
U \mathfrak{g} = T\mathfrak{g}\big/ \big(x\otimes y - y\otimes x - [x,y]\big)
$$
为张量代数商去一个适当的理想所得的代数, 这个理想是由 "应当等于 $0$" 的那些元素生成的.

泛包络代数的泛性质也可翻译为 $U$ 是函子 $\operatorname{Lie}$ 的左伴随.

### 左 g-模

$\mathfrak{g}$ 的 Lie 代数表示,
又称左 $\mathfrak{g}$-模,
定义为 Lie 代数同态
$\mathfrak{g} \to L(\operatorname{End}_K(A))$.
上式右边的 Lie 代数有时记作 $\mathfrak{gl}(A)$.

由泛包络代数的性质,
上述 Lie 代数同态对应代数同态
$U \mathfrak{g} \to \operatorname{End}_K(A)$,
故 $A$ 也可视为左 $U \mathfrak{g}$-模.

事实上, 左 $\mathfrak{g}$-模的范畴同构于左 $U\mathfrak{g}$-模的范畴.
我们称自由 $U\mathfrak{g}$-模为自由 $\mathfrak{g}$-模.   

Lie 代数的一个重要表示是自身的伴随表示,
即 $\operatorname{ad}\colon \mathfrak{g}\to L(\operatorname{End}_K \mathfrak{g})$,
$$
\operatorname{ad}(x)\colon y\mapsto [x,y].
$$
使 $\operatorname{ad}$ 成为 Lie 代数表示的正是 Jacobi 恒等式.

**定理 (Birkhoff-Witt)**

设 $e_i$ 为 $\mathfrak{g}$ 的 $K$-基.
对序列 $I=(i_1\leq \cdots \leq i_k)$ (包括空序列) 定义
$e_I = e_{i_1}\cdots e_{i_k}$,
则所有的 $e_I$
构成
$U \mathfrak{g}$
的
$K$-基.

**推论**

对 $\mathfrak{g}$ 的任意子 Lie 代数 $\mathfrak{h}$,
$U \mathfrak{g}$ 都是自由 $\mathfrak{h}$-模.

### Casimir 元素

**命题**

设 $\mathfrak{g}$ 为半单 Lie 代数, $V$ 为非平凡不可约 $\mathfrak{g}$-模.
那么存在 $c\in Z(U\mathfrak{g})$
使得 $c$ 在 $V$ 上的作用为一非零常数,
且 $c$ 在平凡表示上的作用为 $0$.


## 同调代数的基础知识

设 $R$ 为环, 或为某个域上的代数 ($R$ 的乘法**不一定**交换),
我们只考虑左 $R$-模范畴 $R\mathsf{Mod}$.

### 消解

左 $R$-模 $P$ 称为**投射模**是指函子 $\operatorname{Hom}(P,-)$ 正合. 一般这个函子只是左正合, 故投射是指这个函子右正合.

很明显自由 $R$-模是投射的.
(似乎我们只会用到自由模.)

左 $R$-模 $A$ 的**投射消解**是一个由投射模组成的链复形
$$
\cdots\to P_2\to P_1\to P_0 \to 0\to 0 \to\cdots,
$$
其仅在 $0$ 处有一个同调 $A$.
换言之, 存在上述链复形到
$\cdots\to 0 \to 0 \to A \to 0 \to 0 \to\cdots$
的拟同构.

### Ext 函子

Ext 是 "Hom的导出函子",
这里只介绍其一种定义.
设 $R$ 为环,
$A,B$ 为左 $R$-模,
取 $A$ 的投射消解
$$
\cdots\to P_1\to P_0\to 0,
$$
以反变函子 $\operatorname{Hom}_R(-,B)$ 作用, 得到
$$
0\to \operatorname{Hom}_R(P_0,B)\to \operatorname{Hom}_R(P_1,B)\to \cdots.
$$
$\operatorname{Ext}_R^i (A,B)$ 等于上述复形第 $i$ 个位置的上同调.

Ext 函子得名于模的扩张. 具体而言有如下结论.

**命题**

对 $R$-模 $A,B$,
$\operatorname{Ext}_R^1(A,B)$
的元素一一对应于扩张
$$
0\to A \to C\to B\to 0
$$
的同构类.



## 上同调的同调代数定义

设 $\mathfrak{g}$ 是域 $K$ 上的 Lie 代数. 对 $\mathfrak{g}$-模 $A$ 定义上同调
$$
H^n(\mathfrak{g},V) = \operatorname{Ext}_\mathfrak{g}^n (K,V),
$$
其中 $K$ 是平凡 $\mathfrak{g}$-模.

## 域 $K$ 的 Koszul 消解

Chevalley-Eilenberg 复形本质上来自域 $K$ 作为平凡 $\mathfrak{g}$-模的一个自由消解(free resolution),
称为 Koszul 消解.

令 $C_n=U\mathfrak{g}\otimes_K \wedge^n \mathfrak{g}$,
$d_n\colon C_n\to C_{n-1}$ 定义为
$$
\begin{aligned}
  &d_n(x_1\wedge\cdots\wedge x_n)=\sum_{i=1}^n(-1)^{i+1}
x_i\cdot (x_1\wedge\cdots\wedge\widehat{x_i}\wedge\cdots\wedge x_n)\\
&+\sum_{i<j}(-1)^{i+j}[x_i,x_j]\wedge x_1\wedge\cdots\wedge\widehat{x_i}\wedge\widehat{x_j}\wedge\cdots\wedge x_n.
\end{aligned}
$$

$\mathfrak{g}$-模 $V$
对应的 Cartan-Eilenberg 上同调来自复形
$\operatorname{Hom}_{\mathfrak{g}}(C_\bullet, V)$,
而 $C_\bullet$ 是 $K$ 的消解, 故上述复形的上同调按定义为
$\operatorname{Ext}^\bullet_{\mathfrak{g}}(K,V)$.

## 半单 Lie 代数的表示完全可约

**结论**
对任意 $\mathfrak{g}$-模 $V$,
$H^1(\mathfrak{g},V) = 0$.

**证明**

回忆对于紧 Lie 群的 Lie 代数,
Chevalley-Eilenberg 已经证明了这个结论.
下面是一个纯代数的证明.

设
$$
0\to V_1\to V \to V_2\to 0
$$
为 $\mathfrak{g}$-模的短正合列,
则有链复形的短正合列
$$
0\to \operatorname{Hom}(C_\bullet,V_1)\to \operatorname{Hom}(C_\bullet,V) \to \operatorname{Hom}(C_\bullet,V_2)\to 0.
$$
取上同调的长正合列得到
$$
\cdots \to H^1(\mathfrak{g},V_1)\to H^1(\mathfrak{g},V) \to H^1(\mathfrak{g},V_2) \to \cdots.
$$
这说明若结论对 $V_1,V_2$ 都成立,
则结论对 $V$ 也成立.
于是只需证明 $V$ 为不可约表示的情形.

而由定义
$H^1(\mathfrak{g},V) = \operatorname{Ext}^1(K,V)$,
故只需证明任何扩张
$$
0\to V\to W \to K\to 0
$$
都分裂.

正如 Chevalley-Eilenberg 文中所提示,
我们需要分两种情况.

若 $V$ 为平凡表示, 即 $V=K$,
则 $W$ 是一个二维表示,
而 $\mathfrak{g}$ 的表示矩阵是严格上三角阵
(即只有右上角非零), 从而是幂零的.
因为 $[\mathfrak{g},\mathfrak{g}]=\mathfrak{g}$,
所以 $W$ 为平凡表示.

若 $V$ 为非平凡表示,
回忆存在 $c\in Z(U\mathfrak{g})$
在 $V$ 上的作用为非零常数 $\lambda$;
则 $c$ 在 $W$ 上的表示矩阵为上三角阵,
其特征值为 $0$ (重数 $1$),
$\lambda$ (重数 $\operatorname{dim}\mathfrak{V}$).
因而 $W$ 可分解为 $V\oplus W^0$,
其中 $W^0$ 为 $c$ 对应 $0$ 的特征子空间.
又因为 $c$ 与 $\mathfrak{g}$ 的作用交换,
知 $W^0$ 为子表示,
这说明扩张 $0\to V\to W\to K \to 0$ 分裂.
$\square$



对 $\mathfrak{g}$-模 $V_1,V_2$,
我们证明任意短正合列
$$
0\to V_1 \to W \to V_2 \to 0
$$
分裂.
这等价于存在截面 $f\colon V_2\to W$.

以 $\operatorname{Hom}_{K}(V_2,-) = V_2^*\otimes -$ 作用得到
$$
0\to\text{Hom}_{K}(V_2,V_1)\to\text{Hom}_{K}(V_2,W)\to\text{Hom}_{K}(V_2,V_2),
$$
也即
$$
0\to V_2^*\otimes V_1\to V_2^*\otimes W \to V_2^*\otimes V_2 \to 0.
$$

再以 $\operatorname{Hom}_{\mathfrak{g}}(K,-)$ 作用,
得到左正合列
$$
0\to\text{Hom}_{\mathfrak{g}}(V_2,V_1)\to\text{Hom}_{\mathfrak{g}}(V_2,W)\to\text{Hom}_{\mathfrak{g}}(V_2,V_2),
$$
也即
$$
0\to \operatorname{Hom}_{\mathfrak{g}}(K,V_2^*\otimes V_1)
\to \operatorname{Hom}_{\mathfrak{g}}(K,V_2^*\otimes W)
\to \operatorname{Hom}_{\mathfrak{g}}(K,V_2^*\otimes V_2) \to 0.
$$
结论等价于这个序列右正合,
而我们已经证明对任意 $\mathfrak{g}$-模 $V$,
$$
\operatorname{Ext}_{\mathfrak{g}}^1 (K,V)=0.
$$
因此结论成立.