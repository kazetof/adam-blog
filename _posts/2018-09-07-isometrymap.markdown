---
layout: post
title: 等長写像の性質
date: 2018-09-10 00:55:20 +0900
description: None
img: post-6.jpg # Add image post (optional)
tags: [Blog, Math]
author: kazetof # Add name author (optional)
---

## 等長写像

**定義1 等長写像**

2つの距離空間 $(X, d_{X})$ , $(Y, d_{Y})$について，写像$f: X \to Y$が
\begin{equation}
\forall x_{1}, x_{2} \in X  \bigl( d_{X}(x_{1}, x_{2}) = d_{Y}(f(x_{1}), f(x_{2})) \bigr)
\end{equation}
を満たすとき，$f$を等長写像と呼ぶ．


**命題1**

等長写像ならば単射である．

*証明*

$f$が単射でないと仮定する．$x_{1}, x_{2} \in X$で$x_{1} \neq x_{2} \wedge f(x_{1}) = f(x_{2})$となるものが存在する．

この$x_{1}, x_{2}$について，$f$は等長写像なので，
$$
d_{X}(x_{1}, x_{2}) = d_{Y}(f(x_{1}), f(x_{2})) = d_{Y}(f(x_{1}), f(x_{1})) = 0．
$$

$d_{X}(x_{1}, x_{2})=0$より$x_{1}=x_{2}$となるため矛盾．従って$f$は単射である．$\square$

**命題2**

等長写像ならば一様連続である．

*証明*

任意の$\epsilon>0$について，$\delta$を$0 < \delta < \epsilon$ととると，任意の$x_{1}, x_{2} \in X$について
$$
d_{X}(x_{1}, x_{2}) < \delta \Rightarrow d_{Y}(f(x_{1}), f(x_{2})) < \delta < \epsilon
$$
が成り立つ．従って$f$は一様連続である．$\square$

**命題3**

等長写像ならば連続である．

*証明*

命題2より$f$は一様連続．一様連続$\Rightarrow$連続が成り立つ．$\square$

**命題4**

等長写像$f$により，$X$は$f$の像$f(X) \subset Y$と同相である．

*証明*

$f: X \to f(X)$は命題1より単射，値域は像なので全射である．また，命題3より連続である．
$f$の逆写像$f^{-1}$を考える．任意の$y_{1}, y_{2} \in f(X)$について$x_{1}, x_{2} \in X$が存在し，$y_{1} = f(x_{1}), y_{2} = f(x_{2})$と書け，$x_{1} = f^{-1}(y_{1}), x_{2} = f^{-1}(y_{2})$である．これより，
$$
d_{Y}(y_{1}, y_{2}) = d_{Y}(f(x_{1}), f(x_{2})) = d_{X}(x_{1}, x_{2}) = d_{X}(f^{-1}(y_{1}), f^{-1}(y_{2}))．
$$
これは，$f^{-1}$が$f(X)$から$X$への等長写像であることを意味する．従って命題3より$f^{-1}$は連続である．
$f$は$X$から$f(X)$への連続な全単射で，その逆写像も連続であるため，同相写像である．従って$X$は$f(X)$と同相である．$\square$

**命題5**

$(x_{n})$が$X$上のコーシー列であるとき，$(f(x_{n}))$は$Y$上のコーシー列である．

*証明*

$(x_{n})$が$X$上のコーシー列なので，任意の$\epsilon > 0$についてある$N \in \mathbb{N}$が存在し，任意の$m,n \in \mathbb{N}$について$m,n > N \Rightarrow d_{X}(x_{m}, x_{n}) < \epsilon$が成り立つ．
$d_{X}(x_{m}, x_{n}) = d_{Y}(f(x_{m}), f(x_{n}))$なので，このとき，同じ$\epsilon, N$に対して，
任意の$m,n \in \mathbb{N}$について$m,n > N \Rightarrow d_{Y}(f(x_{m}), f(x_{n})) < \epsilon$が成り立っている．従って$(f(x_{n}))$もコーシー列である．$\square$

## 後で読みたい資料
これの等長変換のところ

[http://www.math.nagoya-u.ac.jp/~kanai/2001kisoIV/ch3.pdf](http://www.math.nagoya-u.ac.jp/~kanai/2001kisoIV/ch3.pdf)

