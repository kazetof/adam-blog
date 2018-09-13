---
layout: post
title: 再生核ヒルベルト空間
date: 2018-09-13 20:45:20 +0900
description: None
img: post-1.jpg # Add image post (optional)
tags: [Blog, Math, カーネル法]
author: kazetof # Add name author (optional)
---

## 再生核ヒルベルト空間

### 定義1 再生核ヒルベルト空間
集合$X$上の関数からなるヒルベルト空間$(\mathcal{H}, \langle \cdot, \cdot \rangle_{\mathcal{H}})$で，任意の$x \in X$に対して，$k_{x} \in \mathcal{H}$が存在して，任意の$f \in \mathcal{H}$について，

(再生性) $\langle f, k_{x}\rangle_{\mathcal{H}} = f(x)$

が成り立つとき，$\mathcal{H}$を再生核ヒルベルト空間と呼ぶ．
ここで，$X$上の2変数関数$k$で，$\forall y \in X \bigl( k(y, x) = k_{x}(y) \bigl)$が成り立つような$k$を再生核と呼ぶ．

*備考*

再生核を用いて，$k_{x} = k(\cdot, x)$と表記する．すると，再生性と再生核の定義より$\langle k_{y}, k_{x} \rangle_{\mathcal{H}} = k_{y}(x) = k(x, y)$なので，$\langle k(\cdot, y), k(\cdot, x) \rangle_{\mathcal{H}} = k(x, y)$と表せる．度々証明に用いるため明記しておく．


### 命題1
定義1の$k_{x} \in \mathcal{H}$の存在は一意的である．

*証明*

定義1の$k_{x}$と同じ$x$について，$k_{x}^{\prime} \in \mathcal{H}$が存在して，$\forall f \in \mathcal{H} \bigl( \langle f, k_{x}^{\prime} \rangle_{\mathcal{H}} = f(x) \bigr)$が成り立っていたとすると，

$$
\langle f, k_{x}\rangle_{\mathcal{H}} = \langle f, k_{x}^{\prime} \rangle_{\mathcal{H}}\\
\langle f, k_{x} - k_{x}^{\prime} \rangle_{\mathcal{H}} = 0,
$$

となり，これは任意の$f \in \mathcal{H}$について$k_{x} - k_{x}^{\prime} \in \mathcal{H}$が直交することを意味する．一般的に内積空間で，ある元が任意の元に対して直交するとき，定義よりその元自身とも直交するため，正定値性よりその元は零元となる．従って$\mathcal{H}$の零元を$0_{\mathcal{H}}$とすると，

$$
k_{x} - k_{x}^{\prime} = 0_{\mathcal{H}} \\
k_{x} = k_{x}^{\prime}
$$

が成り立つ．$\square$

### 命題2
$X$上の再生核ヒルベルト空間の再生核$k$は，$X$上の[正定値カーネル](https://kazetof.github.io/blog/positive-definite-kernel/)である．

*証明*

$\forall x, y \in X \bigl( k(x, y) = \langle k(\cdot, y), k(\cdot, x) \rangle_{\mathcal{H}} = \langle k(\cdot, x), k(\cdot, y) \rangle_{\mathcal{H}}\bigr) = k(y, x)$より対称性が成り立つ．

$\forall n \in \mathbb{R} \forall x_{1}, \cdots, x_{n} \in X \forall c_{1}, \cdots, c_{n} \in \mathbb{R}$，

\begin{equation}
\sum_{i,j=1}^{n} c_{i} c_{j} k(x_{i}, x_{j}) = \sum_{i,j=1}^{n} c_{i}c_{j} \langle k(\cdot, x_{j}), k(\cdot, x_{i}) \rangle_{\mathcal{H}} = \langle \sum_{j=1}^{n} c_{j} k(\cdot, x_{j}), \sum_{i=1}^{n} c_{i} k(\cdot, x_{i}) \rangle_{\mathcal{H}}.
\end{equation}

これは$\sum_{j=1}^{n} c_{j} k(\cdot, x_{j}) = \sum_{i=1}^{n} c_{i} k(\cdot, x_{i})$なので常に$0$以上である．従って正値性が成り立つ．$\square$

### 命題3
再生核ヒルベルト空間$\mathcal{H}$の再生核は一意的である．

*証明*

$X$上の再生核ヒルベルト空間$\mathcal{H}$の再生核$k$は$X$上の2変数関数，つまり，値域を$V$とするとき，$k: X \times X \to V$となる写像であった．この$k$とは異なる$k^{\prime}$が存在し，再生核の定義を満たす，つまり$\forall y \in X \bigl( k^{\prime}(y, x) = k_{x}^{\prime}(y) \bigl)$が成り立つとする．

このとき，任意に$x \in X$が与えられたとき，命題1より$k_{x} = k_{x}^{\prime}$が成り立つため，$\forall y \in X (k(y, x) = k^{\prime}(y, x))$が成り立ち，これは$k$と$k^{\prime}$が$x$が与えられた元で1変数関数としては等しい，つまり$k(\cdot, x) = k^{\prime}(\cdot, x)$を意味する．

これを用いると，
$$
\forall x,y \in X, k^{\prime}(x, y) = \langle k^{\prime}(\cdot, y), k^{\prime}(\cdot, x) \rangle_{\mathcal{H}} = \langle k(\cdot, y), k(\cdot, x) \rangle_{\mathcal{H}} = k(x, y)．
$$
である．$\square$

*備考*

福水本によるとこの一意性は対称性を用いると示せると触れられているが，なくてもいけた...かな？詳しい人に教えを請いたい．

## 参考文献

福水健次, カーネル法入門
