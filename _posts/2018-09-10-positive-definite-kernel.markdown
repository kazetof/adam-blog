---
layout: post
title: 正定値カーネル
date: 2018-09-10 22:05:20 +0900
description: None
img: post-3.jpg # Add image post (optional)
tags: [Blog, Math, カーネル法]
author: kazetof # Add name author (optional)
---

## 正定値カーネル
ここでは正定値カーネルの値域として$\mathbb{R}$を考える．

### 定義1 正定値カーネル
$X$を集合として，次の条件を満たす写像$$k: X \times X \to \mathbb{R}$$を$$X$$上の正定値カーネルという．

1. (対称性) 任意の$$x, y \in X$$について，$$k(x, y) = k(y, x)$$.
2. (正値性) 任意の$$n \in \mathbb{N}$$について，任意の$$x_{1}, \cdots, x_{n} \in X$$と任意の$$c_{1}, \cdots, c_{n} \in \mathbb{R}$$をとると，

\begin{equation}
\sum_{i,j=1}^{n} c_{i}c_{j} k(x_{i}, x_{j}) \geq 0.
\end{equation}

対称性が成り立っているとき，正値性の条件は二次形式に直すと$$\forall \textbf{x} \in X^{n} \forall \textbf{c} \in \mathbb{R}^{n} (\textbf{c}^{T} K \textbf{c} \geq 0)$$が成り立つことであり，$$K$$が半正定値行列であることを意味する．ここで，$$K = (k(\textbf{x}_{i}, \textbf{x}_{j}))_{i,j}^{n}$$であり．この$$K$$をグラム行列という．
## 正定値カーネルの性質
### 命題1
$$\forall x \in X (k(x, x) \geq 0)$$が成り立つ．

*証明*

$n=1$のとき，正値性より$$\forall x \in X \forall c \in \mathbb{R}(c^{2}k(x,x) \geq 0)$$が成り立っている．$$c=0$$のとき$$0 \geq 0$$であり，$$c\neq0$$のとき$$k(x, x) \geq 0$$である．従って題意は成り立つ．$$\square$$

### 命題2

$$\forall x, y \in X (k(x,y)^{2} \leq k(x, x)k(y, y))$$が成り立つ．

*証明*

正値性は任意の$$n \in \mathbb{N}$$について成り立つため，$$n=2$$でも成り立つ．このとき，$$K = \left(
    \begin{array}{cc}
      k(x,x) & k(x,y) \\
      k(y,x) & k(y,y) \\
    \end{array}
\right)$$は半正定値行列である．半正定値行列あるならば，その固有値は非負である．また，行列式は固有値の積に等しいため，$$det(K) \geq 0$$が成り立つ．つまり

$$
k(x,x)k(y,y) - k(x,y)k(y,x) \geq 0 \\
k(x,x)k(y,y) \geq k(x,y)^{2}，
$$

となる．$$\square$$

### 命題3

$$X$$の任意の部分集合$$y$$について，$$k$$の$$Y \times Y$$への制限は，$$Y$$上の正定値カーネルである．

*証明*

対称性と正値性は共に任意の$$x \in X$$について成り立つ命題であり，従って任意の部分集合について成り立つ．$$\square$$

## 参考文献
福水健次，カーネル法入門