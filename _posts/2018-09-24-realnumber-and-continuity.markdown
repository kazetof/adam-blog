---
layout: post
title: 実数の連続性
date: 2018-09-19 00:40:00 +0900
description: None
img: post-3.jpg # Add image post (optional)
tags: [Blog, Math, 解析]
author: kazetof # Add name author (optional)
comments: true
mathjax: true
---

## 連続の公理

### 公理1 (連続の公理)
実数体$\mathbb{R}$の，上に有界な部分集合$A \in \mathbb{R} (A \neq \emptyset)$について，$A$の上限$s \in \mathbb{R}$が存在する．

### 命題
実数体$\mathbb{R}$の，下に有界な部分集合$B \in \mathbb{R} (B \neq \emptyset)$について，$B$の下限$t \in \mathbb{R}$が存在する．

**証明**

$$B^{-} = \{ -b | b \in B\}$$
とする．仮定より$$B$$は下に有界であるため，下界から一つ$l$をとると，$$l \leq b ( \forall b \in B)$$が成り立ち，従って任意の$-b$について$$-l \geq -b$$も成り立つ．これは$-l$が$B^{-}$の上界となっていることを意味し，$B^{-}$は有界となる．公理1より，$B^{-}$には上限が存在し，それを$s \in \mathbb{R}$とする．


### 命題
$A, B$が$\mathbb{R}$の空でない部分集合とし，$A \subset B$が成り立つとする．このとき，$B$が上に有界ならば$A$も上に有界である．

### 命題
$A, B$が$\mathbb{R}$の空でない上に有界な部分集合とし，$A \subset B$が成り立つとする．このとき，

$$
\sup{A} \leq \sup{B}
$$

が成り立つ．

### 命題
$A, B$が$\mathbb{R}$の空でない下にに有界な部分集合とし，$A \subset B$が成り立つとする．このとき，

$$
\inf{A} \geq \inf{B}
$$

が成り立つ．