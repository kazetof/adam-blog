---
layout: post
mathjax: true
title: 距離空間の完備化
date: 2018-09-10 00:55:20 +0300
description: None (optional)
img: post-5.jpg # Add image post (optional)
tags: [Blog, Math, 解析, 関数解析, 集合と位相]
author: kazetof # Add name author (optional)
comments: true
---

# 距離空間の完備化

**定義1 完備**

距離空間$(X, d)$上の任意のコーシー列が$(X, d)$内で収束するとき$X$は完備$(complete)$であると呼ぶ．

**定義2 完備化**

完備でない距離空間$(X, d)$に，任意のコーシー列$(x_{n})_{n \in \mathbb{N}}$の収束する点を全て付け加えて完備な距離空間を構成することを完備化と呼ぶ．
また，これによって構成された完備距離空間$(X^{\*}, d^{\*})$を，$(X, d)$の完備化と呼ぶ．

**命題1**

距離空間$(X, d)$の完備化$(X^{\*}, d^{\*})$で，ある$f: X \to X^{\*}$が存在し，以下の条件を満たす．

1. $f$は[等長写像](../isometrymap/)．
2. $f$の像$f(X)$は$X^{\*}$で稠密．

*証明*

まず$(X, d)$から$(X^{\*}, d^{\*})$を構成する．$X$に対して，$X$上の任意のコーシー列の収束する点を付け加えたいので，$X$上のすべてのコーシー列の集合$C$を考える．$C$には，異なるコーシー列であるが収束する点が同じものが存在しうる．こういったものを同一視したいため，$C$を以下の同値関係によって割る．

$(x_{n}), (y_{n}) \in C$に対して，関係$(\simeq)$を，

\begin{equation}
(x_{n}) \simeq (y_{n}) \iff \lim_{n \to \infty} d(x_{n}, y_{n}) = 0,
\end{equation}
と定義する．

この右辺は極限によって定義されており，収束する場合と発散する場合がある．発散する場合も考慮するにはこの定義では不足であり別途定義する必要があるが，この数列は常に収束することを示す．距離関数の値域は$\mathbb{R}$であるため，$(d(x_{n}, y_{n}))$がコーシー列であることを示せば良い．三角不等式より，

$$
d(x_{m}, y_{m}) - d(x_{n}, y_{n}) \leq d(x_{m}, x_{n}) + d(x_{n}, y_{m}) - (d(x_{n}, y_{m}) - d(y_{m}, y_{n})) = d(x_{m}, x_{n}) + d(y_{m}, y_{n})．
$$

そこで，仮定より$(x_{n}), (y_{n})$はコーシー列であるため，$\forall \epsilon/2 > 0 [ \exists N_{x} \in \mathbb{N} (m,n > N_{x} \Rightarrow d(x_{m}, x_{n}) < \epsilon/2) \wedge \exists N_{y} \in \mathbb{N} (m,n > N_{y} \Rightarrow d(y_{m}, y_{n}) < \epsilon/2)]$となるため，$N = \max(N_{x}, X_{y})$と置くと，$m,n > N$について$d(x_{m}, y_{m}) - d(x_{n}, y_{n}) < \epsilon$が成り立つ．これは$(d(x_{n}, y_{n}))$が$\mathbb{R}$上でコーシー列であることを意味する．

次に上で定義した関係$(\simeq)$が同値関係となっていることを確認する．

$\forall x \in X (d(x, x) = 0)$より，$\forall (x_{n}) \in C(\lim_{n \to \infty} d(x_{n}, x_{n})=0)$なので反射律を満たす．

距離関数$d$の対称性より，$\lim_{n \to \infty} d(x_{n}, y_{n}) \Rightarrow \lim_{n \to \infty} d(y_{n}, x_{n})$なので対称律を満たす．

任意の$x_{n}, y_{n}, z_{n} \in X$について，三角不等式より，$d(x_{n}, z_{n}) \leq d(x_{n}, y_{n}) + d(y_{n}, z_{n})$が成り立つ．
$(x_{n}), (y_{n}), (z_{n}) \in C$について，$\lim_{n \to \infty} d(x_{n}, z_{n}) \leq \lim_{n \to \infty} d(x_{n}, y_{n}) + \lim_{n \to \infty} d(y_{n}, z_{n})$となる．ここで，$(x_{n}) \simeq (y_{n}) \wedge (y_{n}) \simeq (z_{n})$が成り立つならば，この関係の定義より不等式の右辺は$0$となるため，$(x_{n}) \simeq (z_{n})$である．従って推移律を満たす．

以上より関係$(\simeq)$は，$C$上の同値関係である．

さて，この同値関係$(\simeq)$の商集合を$X^{\*}=C / \simeq$として，$X^{\*}$上の距離関数
$(d^{\*} : X^{\*} \times X^{\*} \to \mathbb{R})$を定義する．$X^{\*}$を$X$上のコーシー列の収束先の集合としたいので，$X^{\*}$上の距離を$X$の距離の極限で定義する．つまり，$x^{\*}, y^{\*} \in X^{\*}$について，

\begin{equation}
d^{\*}(x^{\*}, y^{\*}) = \lim_{n \to \infty} d(x_{n}, y_{n})，
\end{equation}

と定義する．

この定義が同値類の代表元の取り方に依存しないことを示す．$(x_{n}), (x_{n}^{\prime}), (y_{n}), (y_{n}^{\prime}) \in C$で，$(x_{n}) \simeq (x_{n}^{\prime}) \wedge (y_{n}) \simeq (y_{n}^{\prime})$とする．

$$
d(x_{n}, y_{n}) \leq d(x_{n}, x_{n}^{\prime}) + d(x_{n}^{\prime}, y_{n}^{\prime}) + d(y_{n}^{\prime}, y_{n}) \\
d(x_{n}, y_{n}) - d(x_{n}^{\prime}, y_{n}^{\prime}) \leq d(x_{n}, x_{n}^{\prime}) + d(y_{n}, y_{n}^{\prime}),
$$

$$
d(x_{n}^{\prime}, y_{n}^{\prime}) \leq d(x_{n}^{\prime}, x_{n}) + d(x_{n}, y_{n}) + d(y_{n}, y_{n}^{\prime}) \\
d(x_{n}, y_{n}) - d(x_{n}^{\prime}, y_{n}^{\prime}) \geq - \bigl( d(x_{n}, x_{n}^{\prime}) + d(y_{n}, y_{n}^{\prime}) \bigr)
$$

であるため，

$$
| d(x_{n}, y_{n}) - d(x_{n}^{\prime}, y_{n}^{\prime}) | \leq d(x_{n}, x_{n}^{\prime}) + d(y_{n}, y_{n}^{\prime})
$$

が成り立つ．この不等式の右辺は同値関係$(\simeq)$の定義より$n \to \infty$で$0$となるため，

$$
\lim_{n \to \infty} d(x_{n}, y_{n}) = \lim_{n \to \infty} d(x_{n}^{\prime}, y_{n}^{\prime}) 
$$
が成り立つ．

この距離関数$(d^{\*})$が距離関数の定義を満たすことを確認する．

(2)の右辺の点列を考える．二つのコーシー列が与えられるごとに，(2)の右辺が収束することは既にみた．$\mathbb{R}$上で収束するならば有界であり上限を$M$ととると，$X$上の距離関数$d$の定義より$\geq 0$なので$[0,M]$上の点列である．閉区間上の点列であるため，極限はこの区間内に収まる．したがって$\forall x^{\*}, y^{\*} \in X^{\*} ( d^{\*}(x^{\*}, y^{\*}) \geq 0)$が成り立つ．

$x^{\*}, y^{\*} \in X^{\*}$について$x^{\*} = y^{\*}$ならば$d^{\*}(x^{\*}, y^{\*}) = \lim_{n \to \infty} d(x_{n}, x_{n}) = 0$である．また，$d^{\*}(x^{\*}, y^{\*}) = 0$ならば$\lim_{n \to \infty} d(x_{n}, x_{n}) = 0$より$(x_{n}) \simeq (y_{n})$でありこれは$(x_{n})$と$(y_{n})$が同じ同値類に属することを意味する．つまり$x^{\*} = y^{\*}$である．

$d^{\*}(x^{\*}, y^{\*}) = \lim_{n \to \infty} d(x_{n}, y_{n}) = \lim_{n \to \infty} d(y_{n}, x_{n}) = d^{\*}(y^{\*}, x^{\*})$より対称性が成り立つ．


任意に$(x_{n}), (y_{n}), (z_{n}) \in C$をとり，それぞれ対応する同値類を$x^{\*}, y^{\*}, z^{\*} \in X^{\*}$とすると，$d^{\*}(x^{\*}, z^{\*}) = \lim_{n \to \infty} d(x_{n}, z_{n}) \leq \lim_{n \to \infty}(d(x_{n}, y_{n}) + d(y_{n}, z_{n})) = d^{\*}(x^{\*}, y^{\*}) + d^{\*}(y^{\*}, z^{\*})$より$d^{\*}$で三角不等式が成り立つ．

以上より$d^{\*}$は距離関数の定義を満たす．

これまでに$(X, d)$から，まだ完備であることは確認していないものの，$(X^{\*}, d^{\*})$を構成した．次に命題の条件を満たすように$f: X \to X^{\*}$を構成する．
任意の$x \in X$にしてその恒等列$(x_{n})$は，どのような$m,n \in \mathbb{N}$をとっても$d(x_{m}, x_{n})=0$なのでコーシー列である．$x$をこのコーシー列の属する同値類と対応させる写像を$f$とする．

この$f$が等長写像であることを確認する．
$d^{\*}(x^{\*}, y^{\*}) = \lim_{n \to \infty}d(x_{n}, y_{n}) = \lim_{n \to \infty}d(x, y) = d(x, y)$となるため等長写像である．

次に$f$の像$f(X)$が$X^{\*}$で稠密であることを確認する．任意の$(x_{n}) \in C$の対応する$x^{\*}$に対して，

\begin{equation}
\lim_{n \to \infty} f(x_{n}) = x^{\*}
\end{equation}

となれば$f(X)$は$X^{\*}$で稠密である．これは$\forall \epsilon > 0 \exists N \in \mathbb{N}( n \geq N \Rightarrow d^{\*}(x^{\*}, f(x_{n})) < \epsilon)$が成り立つことである．一方で，$\lim_{n \to \infty} d^{\*}(x^{\*}, f(x_{n})) = 0$は，$\forall \epsilon > 0 \exists N \in \mathbb{N} (n \geq N \Rightarrow \|d^{\*}(x^{\*}, f(x_{n}) - 0\| < \epsilon)$であり，必要条件は$d^{\*}(x^{\*}, f(x_{n})) < \epsilon$となるで同値になる．つまり，$\lim_{n \to \infty} d^{\*}(x^{\*}, f(x_{n})) = 0$を示せば良い．

ここで$f(x_{n})$が$x_{n}$の恒等列であったことに注意して，$d^{\*}(x^{\*}, f(x_{n}) = \lim_{m \to \infty} d(x_{m}, x_{n})$となる．従って，$\lim_{n \to \infty} \lim_{m \to \infty} d(x_{m}, x_{n}) = 0$となれば良い．これは収束する点列の極限からなる数列の極限である．仮定より$x_{m}, x_{n}$はコーシー列の要素であるため，$\forall \epsilon > 0 \exists N \in \mathbb{N} (m,n \geq N \Rightarrow d(x_{m}, x_{n})$が成り立っているため，同じ$N$について$\lim_{n \to \infty} \lim_{m \to \infty} d(x_{m}, x_{n}) = 0$が成り立っている．つまり$\lim_{n \to \infty} f(x_{n}) = x^{\*}$が成り立っている．

最後に$(X^{\*}, d^{\*})$が完備であることを確認する．そのためには，$X^{\*}$上の任意のコーシー列$(x_{n}^{\*})$が収束することを示せばよい．$f(X)$は$X^{\*}$内で稠密であるため，任意の$n \in \mathbb{N}$に対してある$x_{n} \in X$が存在して，

\begin{equation}
d^{\*} (x_{n}^{\*}, f(x_{n})) < \frac{1}{n},
\end{equation}

となる．このときこの$x_{n}$を並べた点列$(x_{n})$はコーシー列となる．これは，$f$が等長写像であることにより，

\begin{equation}
d(x_{m}, x_{n}) = d^{\*} (f(x_{m}), f(x_{n})) \leq d^{\*} (f(x_{m}), x_{m}^{\*}) + d^{\*} (x_{m}^{\*}, x_{n}^{\*}) + d^{\*} (x_{n}^{\*}, f(x_{n})).
\end{equation}

この右辺の2項目は$(x_{n}^{\*})$が$X^{\*}$上のコーシー列という仮定より適切な$m,n$をとって$\epsilon / 3$以下にすることができる．1,3項目も(3)で示したように$\epsilon / 3$以下にすることができる．任意の$\epsilon$に対して，これらの3項が全て$\epsilon / 3$が成り立つような$N$を取ることにより，$d(x_{m}, x_{n}) < \epsilon$が成り立つ．従ってこの$(x_{n})$はコーシー列である．

このコーシー列の定める$X^{\*}$の点を$x^{\*}$とすると，

\begin{equation}
d^{\*} (x^{\*}, x_{n}^{\*}) \leq d^{\*} (x^{\*}, f(x_{n})) + d^{\*} (f(x_{n}), x_{n}^{\*}),
\end{equation}

となる．
右辺の第1項目は(7)より$n \to \infty$で$0$になり，第2項目は(8)より$n \to \infty$で$0$．従って$X^{\*}$上のコーシー列$(x_{n}^{\*})$は$x^{\*} \in X^{\*}$に収束する．

以上で命題は構成的に証明された．$\square$

# 備考
一意性については別途証明の必要あり．

# 参考文献
- 森田茂之, 集合と位相空間
- 新井敏康, 集合・論理と位相
- 吉田善章, 新版 応用のための関数解析







