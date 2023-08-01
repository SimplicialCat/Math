#! https://zhuanlan.zhihu.com/p/645887550
# 综合微分几何 (5) 微分形式, 流与 Stokes 定理

上文: [综合微分几何 (4) 切向量场](https://zhuanlan.zhihu.com/p/638825155)

传统微分几何中, $n$-形式 $\omega$ 是 $\wedge^n T^*M$ 的截面, 吃 $n$ 个切向量 (或 $\wedge^n TM$ 的元素) 吐一个数, 且满足反对称性.

我们思考综合微分几何中的 $n$-形式如何定义. 注意到 $n$ 个切向量等同于 $D(n)$ 到 $M$ 的一个映射 (微线性条件), 一个合理的定义是函数 $M^{D(n)} \to R$. 但是有时考虑无穷小平行体 (infinitesimal parallelepipedum) $D^n \to M$, 也即定义微分形式为映射 $M^{D^n}\to R$ 同样合理; 后面将看到,  这样可以更方便地定义外微分 (这涉及到无穷小平行体的 "边界"), 以及 $n$-形式在 $n$ 维 "子流形" 上的积分. 我们下面将采取后一种定义. 在 Kock 2009 年的书 _Synthetic Geometry of Manifolds_ 中, 两种微分形式分别称为 "胡须状" $n$-形式 (whisker $n$-form) 和 "方形" $n$-形式 (cubical $n$-form).

以下的 $M$ 都是指任意的微线性对象.

---

我们在此处引入一个证明线性映射的工具, 因为它对下面的构造十分有用.

**引理** (齐次性引理). 设 $V$ 是 $R$-模, $f\colon V \to R$ 是任意函数. 若 $f$ 是齐 $1$ 次函数, 即 $f(ax)=af(x)\,\forall a\in R\forall x\in V$, 则 $f$ 是线性函数.

**证明**. 对 $x\in V$, 记 $v_x$ 为向量场 $(y,d)\mapsto y+d\cdot x$.

对任意 $d\in D$,
$$
\begin{aligned}
	d\cdot f(x+y)&=
	f(d\cdot (x+y))\\
	&=f(d\cdot x) + d\cdot v_y (f)(d\cdot x)\\
	&=f(d\cdot x) + d\cdot \big(v_y(f)(0) + d\cdot v_xv_y(f)(0)\big)\\
	&=f(d\cdot x) + d\cdot v_y(f)(0)\\
	&=f(d\cdot x)+ f(d\cdot y)\\
	&=d(f(x)+f(y)).
\end{aligned}
$$
这说明 $f(x+y) = f(x) + f(y)$, 即线性条件等价于齐次性条件.

---

## 微分形式

对于 $x=(x_1,\cdots,x_n) \in R^n$ 与 $a\in R$, 记 $a\cdot_k x = (x_1,\cdots,x_{k-1},ax_k,x_{k+1},\cdots,x_n)$.

对于 $n$ 维无穷小平行体 $\gamma\in M^{D^n}$, 记 $a\cdot_k\gamma$ 为其第 $k$ 方向伸缩 $a$ 倍所得的无穷小平行体, 也即
$$
(a\cdot_k\gamma)(d) = \gamma(a\cdot_k d).
$$

**定义** (方形微分形式). $M$ 上的 (方形) $n$-形式 (cubical $n$-form) 是满足如下条件的映射 $\omega \colon M^{D^n} \to R$:

- 多重线性, 即对任意 $1\leq k\leq n$, $a\in R$, $\gamma\in M^{D^n}$, 有 $\omega(a \cdot_k \gamma) = a\omega(\gamma)$ (线性条件等价于齐次性条件);
- 反对称, 即对任意排列 $\sigma\in S_n$, 有 $\omega(\sigma(\gamma))=\operatorname{sign}(\sigma)\omega(\gamma)$, 其中 $\sigma(\gamma)$ 表示排列作用于 $\gamma \colon D^n\to M$ 的参数.

记 $M$ 上 $n$-形式的空间为 $\Omega^n(M)$. $n$-形式乘以一个函数仍是 $n$-形式, 即 $\Omega^n(M)$ 是 $R^M$-模.

任意映射 $f \colon M \to N$ 可将 $N$ 上的微分形式拉回到 $M$ 上: 只需简单地作复合 $D^n \to M \to N$. 这就是说 $\Omega^n$ 是个反变函子. 记 $M$ 上的微分形式 $\omega$ 沿着 $f$ 的拉回为 $f^*\omega$.

## 外微分

我们的思路是这样的: 先定义无穷小平行体的边界, 定义微分形式与无穷小平行体的配对, 也即微分形式在无穷小平行体上积分, 然后用边界关于此配对的对偶定义微分形式的外微分.

第一个问题是无穷小平行体 $\gamma \colon D^n \to M$ 的边界是什么. 我们很快发现, 甚至不能定义无穷小线段 $D \to M$ 的边界.

无穷小线段的边界应当是两个点. 可以令其中一个点是 $0\in D$ 的像, 但我们无法指出另一个点是什么, 因为我们甚至不能指出 $D$ 的一个非零元. 因此, 如下的定义是一个合理的做法.

**定义**. 设 $\gamma \colon D^n \to M$ 是无穷小平行体, $e=(e_1,\cdots,e_n)\in D^n$, 那么二元对 $(\gamma,e)$ 称作带标记的 (marked) 无穷小平行体. 这就是说, 定义 $M$ 上的 $n$ 维带标记无穷小平行体的空间为 $M^{D^n}\times D^n$.

为了方便我们定义与微分形式相对偶的流 (current) 的概念. (注意这个概念与通常的流的定义稍有不同.)

**定义** (流). $M$ 上的 $n$-流是 $\Omega^n(M)$ 上的线性函数.

由定义, 带标记的无穷小平行体是一个流. 流的空间是一个 $R$-模.

相对于微分形式可以拉回, 我们知道流可以推出: 对任意映射 $f\colon M\to N$ 与 $M$ 上的流 $\tau$, 定义 $N$ 上的流 $f_*\tau$ 如下.
$$
\int_{f_*\tau}\omega = \int_{\tau}f^*\omega.
$$

---

设 $(\gamma,e)$ 为 $(n+1)$ 维带标记无穷小平行体. 一个平行体每个方向有两个面, 我们定义 $(\gamma,e)$ 的第 $i$ 方向的两个面为
$$
F_0^i (\gamma,e)=(\gamma_0^i,(e_1,\cdots,\widehat {e_i},\cdots,e_{n+1})),
$$
$$
F_1^i (\gamma,e)=(\gamma_1^i,(e_1,\cdots,\widehat {e_i},\cdots,e_{n+1})),
$$
其中 $\gamma_j^i\colon (d_1,\cdots,d_n) \mapsto (d_1,\cdots,d_{i-1},j e_i,d_i,\cdots,d_n)\,(j=0,1)$

$\gamma_0^i\colon (d_1,\cdots,d_n) \mapsto (d_1,\cdots,d_{i-1},0,d_i,\cdots,d_n)$

$\gamma_0^i\colon (d_1,\cdots,d_n) \mapsto (d_1,\cdots,d_{i-1},0,d_i,\cdots,d_n)$, $\gamma_1^i\colon (d_1,\cdots,d_n) \mapsto (d_1,\cdots,d_{i-1},e_i,d_i,\cdots,d_n)$

**定义** (带标记无穷小平行体的边界). 一个带标记无穷小平行体的边界是每个面 (取合适定向) 的和, 作为一个流:
$$
\partial (\gamma,e) := \sum_{i=1}^{n+1}\sum_{j=0}^1 (-1)^{i+j} F_j^i (\gamma,e),
$$
也即
$$
\partial (\gamma,e) := \sum_{i=1}^{n+1}\sum_{j=0}^1 (-1)^{i+j} F_j^i (\gamma,e),
$$
也即
$$
\partial (\gamma,e) := \sum_{i=1}^{n+1} \big( (-1)^i F_0^i (\gamma,e) + (-1)^{i+1}F_1^{i}(\gamma,e)\big),
$$
就像单纯形的边界一样.

**定义** (微分形式在带标记无穷小平行体上的积分). 设 $\omega \colon M^{D^n} \to R$ 是 $n$-形式, $(\gamma,e)$ 是带标记的无穷小平行体, 定义 $\omega$ 在 $(\gamma,e)$ 上的积分
$$
\int_{(\gamma,e)}\omega = e_1\cdots e_n \cdot \omega(\gamma).
$$
当然, 我们可将上式延拓到有限的线性组合.

微分形式的重要性质是, 一个微分形式由它在所有带标记无穷小平行体上的积分完全确定; 换言之, 微分形式可视为满足适当条件的映射 $\phi\colon M^{D^n}\times D^n \to R$:

- $\phi(a\cdot_k \gamma, e) = a \phi(\gamma,e)$;
- $\phi(\gamma,a\cdot_k e) = a\phi(\gamma,e)$;
- $\phi(\sigma(\gamma),e) = \operatorname{sign}(\sigma)\phi(\gamma,e)\,(\sigma\in S_n)$.

**命题** (微分形式由它在所有带标记无穷小平行体上的积分完全确定). 给定满足上述条件的映射 $\phi\colon M^{D^n}\times D^n \to R$, 存在唯一的微分形式 $\omega \colon  M^{D^n} \to R$ 使得
$$
\phi(\gamma,e)=\int_{(\gamma,e)}\omega.
$$
**证明**. 由条件, 只要 $d$ 的任一分量为零, 就有 $\phi(\gamma,d)=0$. 因此由 $D^n$ 的 K--L 公理, 存在唯一的函数 $\omega(\gamma)$ 满足
$$
\phi(\gamma,d)=d_1\cdots d_n \cdot \omega(\gamma).
$$
由条件, $\omega(\gamma)$ 是多重线性且反对称的. 这说明它是一个微分形式. $\square$

由上述性质, 我们便可以由带标记无穷小平行体上的积分来定义一个微分形式的外微分.

**定义** (外微分). 一个 $n$-形式 $\omega$ 的外微分 $d\omega$ 是由下式定义的 $(n+1)$-形式: 对任意带标记无穷小平行体 $(\gamma,e)$,
$$
\int_{(\gamma,e)}d\omega = \int_{\partial (\gamma,e)}\omega.
$$
这就是 Stokes 公式 (的一个无穷小版本).

**例** (函数的微分). 函数即 $0$-形式的外微分就是普通的微分. 设 $f\in M \to R$ 为函数. 按上述的定义, $df\colon M^D\to R$ 是由下式定义的 $1$-形式: 对任意带标记的无穷小线段 $(\gamma,e)\in M^D \times D$,
$$
\int_{(\gamma,e)} df = \int_{\partial (\gamma,e)}f,
$$
而由定义, $\partial (\gamma,e) = (\gamma(e),()) - (\gamma(0),())$,
$$
\int_{(\gamma,e)} df = f(\gamma(e))-f(\gamma(0))=e\cdot (f\circ \gamma)'(0),
$$
因此有
$$
df(\gamma)= (f\circ\gamma)'(0).
$$
这与传统微分几何的结论 (甚至记号) 完全一致.

**命题**. 外微分与拉回交换.

(?)

## 积分

考虑 $R^n$ 的方形区域 $P = [a_1,b_1]\times\cdots\times[a_n,b_n]$. 容易看出, $P$ 上的 $n$-形式可唯一地写成
$$
f\,dx_1\cdots dx_n,
$$
其中 $f$ 是 $P$ 上的函数. 具体地, 对任意 $x=(x_1,\cdots,x_n)\in P$ 令 $\gamma\colon D^n \to P$ 为无穷小平行体
$$
(d_1,\cdots,d_n) \mapsto (x_1+d_1,\cdots,x_n+d_n),
$$
那么 $f(x)$ 即是 $n$-形式在 $\gamma$ 上的取值.

**定义**. 区域 $P$ 的边界 $\partial P$ 是 $2n$ 个面 (取合适的定向) 的和, 与带标记无穷小平行体的边界完全类似. 具体地,
$$
\partial P:= \sum_{i=1}^n\sum_{j=0}^1 (-1)^{i+j} F_j^i P,
$$
$$
F_j^i P := [a_1,b_1]\times\cdots\times \{t_j^i\}\times\cdots\times [a_n,b_n],
$$
$$
t_j^i=\begin{cases}
a_i & j=0,\\
b_i & j=1.
\end{cases}
$$
**引理** (边界的可加性). 若两个方形区域 $P_1,P_2$ 沿某个面拼起来等于方形区域 $Q$, 那么 $\partial Q$ 等于 $\partial P_1 + \partial P_2$.

**定理** ($R^n$ 的方形区域上的 Stokes 定理). 对 $P$ 上的任意 $(n-1)$-形式 $\omega$,
$$
\int_{\partial P}\omega = \int_P d\omega.
$$
**证明**. 为了记号的简便, 我们只对 $n=2$ 证明这个结论. 思路很简单: 先考虑一个宽度无穷小的长条形.

考虑 $b_2=a_2+d_2\,(d_2\in D)$ 的情形. 定义函数 $g,h \colon [a_1,b_1]\to R$,
$$
g(x)=\int_{\partial([a_1,x]\times [a_2,b_2])}\omega,
$$
$$
h(x)=\int_{[a_1,x]\times [a_2,b_2]}d\omega.
$$
首先, $g(a_1)=h(a_1)=0$. 然后计算 $g,h$ 的导数: 由边界的可加性以及外微分 $d$ 的定义,
$$
\begin{aligned}
	g(x+d_1)-g(x)&=\int_{\partial([x,x+d_1]\times [a_2,b_2])}\omega\\
	&=\int_{[x,x+d_1]\times [a_2,b_2]}d\omega\\
	&= h(x+d_1)-h(x),
\end{aligned}
$$
这说明 $g'=h'$, 从而 $g=h$.

现在我们对宽度无穷小的长方形证明了 Stokes 定理; 然后再对另一个方向做同样的事情, 就证明了一般长方形的 Stokes 定理. $\square$

设 $M$ 为微线性对象. 称映射
$$
\tau \colon P \to M
$$
为 $M$ 中的 $n$ 维曲面. 定义 $\tau$ 的边界 $\partial \tau = \tau_*\partial P$.

**定义** (微分形式在曲面上积分). 设 $\omega$ 是 $M$ 上的 $n$-形式, 那么 $\tau^*\omega$ 是 $P$ 上的 $n$-形式. 将 $\tau^*\omega$ 唯一地表示为 $f\,dx_1\cdots dx_n$, 定义
$$
\int_\tau\omega :=\int_{P}\tau^*\omega.
$$

**推论**. 对 $M$ 上的 $(n-1)$-形式 $\omega$ 与 $n$ 维曲面 $\tau \colon P \to M$,
$$
\int_\tau d\omega = \int_{\partial \tau}\omega.
$$
**证明**.
$$
\begin{aligned}
	\int_{\tau}d\omega&=\int_P \tau^*d\omega\\
	&=\int_P d(\tau^*\omega)\\
	&=\int_{\partial P}\tau^*\omega\\
	&=\int_{\partial \tau}\omega.
\end{aligned}
$$