---
layout: post
title: 上に有界な単調増加数列 
date: 2018-11-11 09:30:00 +0900
description: None
img: post-1.jpg # Add image post (optional)
tags: [Blog, Math, 解析]
author: kazetof # Add name author (optional)
comments: true
mathjax: true
---

## 定理
$\mathbb{R}$上の，上に有界な単調増加数列$\\{ a_{n} \\}$は収束する．

## 証明
${ a_{n} }$が上に有界な単調増加数列であるとき，それを集合とみなした$A = \\{ a_{n} | n \in \mathbb{N} \\}$は，上に有界な$\mathbb{R}$の部分集合である．そのため，[有界性公理](../dedekind-cut-and-least-upper-bound-axiom/)より上限$s = \sup(A)$が存在する． \\
$\epsilon > 0$を任意にとると，$s$が上限であることより，$s-\epsilon$は$A$の上界ではない． $s-\epsilon$が$A$の上界ではないとき，$s-\epsilon < a_{n_{0}} \leq s$ となるような$a_{n_{0}} \in A$が存在する． \\
このとき，${ a_{n} }$が単調増加数列であることを用いると，任意の$n_{0} \leq n$となる$n$について，

$$s-\epsilon < a_{n_{0}} \leq a_{n}$$

が成り立つ．また，$s$は上限であり任意の$a_{n} \in A$について$a_{n} \leq s$を満たすため，

$$s-\epsilon < a_{n_{0}} \leq a_{n} \leq s$$

が成り立つ．$\epsilon > 0$より右辺に$\epsilon$を足すと等号ではなくなり，

$$s-\epsilon < a_{n}< s + \epsilon \iff  | a_{n} - s| < \epsilon$$

となる．

$\epsilon > 0$について$a_{n_{0}} \in A$が存在するとき，$\\{ a_{n} \\}$は$\mathbb{N} \to A$の全射とみなせるため，$a_{n_{0}}$に対応する$n_{0} \in \mathbb{N}$は存在する．\\
最終的に，任意の$\epsilon > 0$について$n_{0} \in \mathbb{N}$が存在し，$n_{0} \leq n \Rightarrow  | a_{n} - s| < \epsilon$を満たす．これは，${ a_{n} }$が$s$に収束することを意味する．$\square$



