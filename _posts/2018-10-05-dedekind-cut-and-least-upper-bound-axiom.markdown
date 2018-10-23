---
layout: post
title: デデキントの公理と有界性公理の同値性
date: 2018-10-05 00:40:00 +0900
description: None
img: post-4.jpg # Add image post (optional)
tags: [Blog, Math, 解析]
author: kazetof # Add name author (optional)
comments: true
mathjax: true
---

# デデキントの切断
$\mathbb{R}$を全順序集合である体とする．このとき，$\mathbb{R}$の部分集合の組$\( A, B\)$について以下が成り立つとき，$\( A, B\)$を切断と呼ぶ．

1. $A \neq \emptyset \land B \neq \emptyset$．
2. $A \cap B = \emptyset$．
3. $A \cup B = \mathbb{R}$．
4. $\forall a \in A \forall b \in B (a < b)$．

# デデキントの公理
デデキントの切断に対して，$A$の最大元と$B$の最小元の存在に関して，以下の4ケースが考えられる．

1. $A$の最大元が存在する $\land$ $B$の最小元が存在しない．
2. $A$の最大元が存在しない $\land$ $B$の最小元が存在する．
3. $A$の最大元が存在する $\land$ $B$の最小元が存在する．
4. $A$の最大元が存在しない $\land$ $B$の最小元が存在しない．

このとき，1,2のみに限る．

**備考**

3.は$\mathbb{R}$が全順序集合である体であることから常に成り立たない．この公理は，4があり得ないことを仮定する．

## $\mathbb{R}$の稠密性
$\mathbb{R}$を全順序集合である体とする．このとき，$\mathbb{R}$は稠密である．

**証明**

任意の$a,b \in \mathbb{R}$($a < b$)について，$c=\frac{a+b}{2}$ととる．$\mathbb{R}$が体であることより，$c \in \mathbb{R}$であり，全順序集合であることからこの$c$にも順序関係が定義される．このときの順序は，$a < b \iff a + a < a + b \iff a = \frac{a + a}{2} < \frac{a + b}{2} = c$より$a < c$．同様に，$a < b \iff a + b < b + b \iff c = \frac{a + b}{2} < \frac{b + b}{2} = b$より$c < b$である．したがって任意の$a,b \in \mathbb{R}$($a < b$)について$a < c < b$となる$c$が存在するため，$\mathbb{R}$は稠密である．$\square$

## デデキントの切断 3.
デデキントの切断の

3.$A$の最大元が存在する $\land$ $B$の最小元が存在する．

は，常に成り立たない．

**証明**

3.が成り立つと仮定し，$A$の最大元を$a$，$B$の最小元を$b$とすると，$a=b$はありえない．$a \in A \land a \in B$となり切断の定義2. $A \cap B = \emptyset$．に反するからである．$a \neq b$のとき切断の定義4. より$a < b$である．$\mathbb{R}$の稠密性より$a < c < b$となる$c \in \mathbb{R}$が存在する．この$c$は$a < c$より$c \notin A$であり$c < b$より$c \notin B$である．これは切断の定義3. $A \cup B = \mathbb{R}$．に矛盾する．$\square$

# 有界性公理
$\mathbb{R}$を全順序集合である体とする．$\mathbb{R}$の任意の部分集合$A \subset \mathbb{R} (A \neq \emptyset)$について，$A$が上に有界（下に有界）ならば，上限$s = \sup A \in \mathbb{R}$(下限$s = \inf A$)が存在する．

# デデキントの公理と有界性公理の同値性
ここで，デデキントの公理と有界性公理が同値であることを示す．

## デデキントの公理 $\Rightarrow$ 有界性公理
### 証明の流れ
有界性公理の，上に有界な空でない任意の部分集合$A \subset \mathbb{R}$について，

$$
U = \{ u \in  \mathbb{R} | \forall a \in A ( a \leq u) \},\\
L = U^{C} = \{ l \in \mathbb{R} | \exists a \in A ( a > l) \}.
$$

と定義する．$U$はAの上界であり，$L$はその補集合である．

1. $(L, U)$が切断である．
2. $L$の最大元または$U$の最小元が$s = \sup A$となる．
3. $L$の最大元は存在しない．
4. $U$の最小元が$s = \sup A$となる．

という順に示す．

まず切断であることを確認する．

### 1. $L \neq \emptyset \land U \neq \emptyset$．

$A$は有界であるため，ある$b \in \mathbb{R}$が存在し，$\forall a \in A (a \leq b)$となる．このとき，$b \in U$であるため$U \neq \emptyset$である．また，$A \neq \emptyset$の仮定より，ある$a \in A$がとれる．$a-1 \in \mathbb{R}$を考えると，$a-1 < a \in A$であり，これは$a-1 \in L$を意味する．従って$L \neq \emptyset$となる．

### 2. $L \cap U = \emptyset$．
$L$は$U$の補集合として定義しているため，$L \cap U = \emptyset$である．実際に，$L \cap U \neq \emptyset$とすると，$c \in L \cap U$がとれて，$c \in U$より$\forall a \in A (a \leq c)$である．一方で，$c \in L$より$\exists a \in A (a > c)$となり任意の$a$について$a \leq c$に矛盾する．従って$L \cap U = \emptyset$が示された．

### 3. $L \cup U = \mathbb{R}$．
$L=U^{C}$であったため，$U^{C} \cup U = \mathbb{R}$を示す．まず，$U, U^{C} \in \mathbb{R}$より$U \cup U^{C} \subset \mathbb{R}$が成り立つ．一方で，任意に$a \in \mathbb{R}$をとると，$a \in U$または$a \notin U$のいずれかが成り立つ．従って任意の$a \in \mathbb{R}$について，$$a \in \mathbb{R} \Rightarrow a \in \{ a | a \in U \lor a \notin U \} = \{ a | a \in U \} \cup \{ a | a \notin U \} = U \cup U^{C}$$より，$\mathbb{R} \subset U^{C} \cup U$．以上より$U^{C} \cup U = \mathbb{R}$が示された．

### 4. $\forall a \in L \forall b \in U (a < b)$．
任意に$a \in L$をとると，$a < c$となる$c \in A$が存在する．また，$U$の定義より任意の$c^{\prime} \in A$に対して，任意の$b \in U$は$c^{\prime} \leq b$が成り立つ．任意の$c^{\prime}$について成り立つため，$c$についても成り立ち，$a < c \leq b$となる．以上より，$\forall a \in L \forall b \in U (a < b)$が示された．

1.2.3.4より，$(L, U)$は切断である．デデキントの公理より，$L$の最大元または$U$の最小元が存在する．

### $L$の最大元は存在しない
$L$の最大元が存在すると仮定し，それを$s$とおく．このとき$s \in L$より$s < a \in A$となる$a$が存在する．$\mathbb{R}$の稠密性より，$s < b < a$となる$b \in \mathbb{R}$が存在し，$s$が$L$の最大元であることから，$b \in U$が成り立つ．しかし，$b < a$が任意の$a \in A$について$a \leq u$が成り立つという$U$の定義に反する．従って$L$の最大元は存在しない．

### $U$の最小元は$A$の上限
$L$の最小元が存在しないため，デデキントの公理より$U$の最小元が存在する．$U$は$A$の上界の集合として定義されていたため，その最小元は$A$の上限である．従って$A$の上限が存在する．$\square$

## 有界性公理 $\Rightarrow$ デデキントの公理 

まず，任意の切断$(L, U)$の$L$は上に有界である．もしも$L$が上に有界でないとすると，任意の$a \in \mathbb{R}$について$a < l$となる$l \in L$が存在し，$U = \emptyset$となるが，これは切断の定義2.に反する．

この$L$に対して有界性公理より上限が存在する．$s = \sup L$とおくと，$s \in L$と$s \in U$の場合が考えられる．$s \in L$であるとき，$s$は$L$の最大元であり，$s \in U$であるとき，$s$は$U$の最小元であることを示す．

$s \in L$のとき，$s$は$L$の上界の要素であることから，$\forall l \in L(l \leq s)$が成り立ち，仮定より$s \in L$であるため，$s$は$L$の最大元である．

$s \in U$のとき，$\forall u \in U(s \leq u)$を示せば良い．任意の$\epsilon > 0$について，$s - \epsilon$は$s$が$L$の上限であることから，$L$に属する．つまり，$\forall x \in \mathbb{R}(x < s \Rightarrow x \in L)$が成り立ち，対偶をとると$\forall x \in \mathbb{R}(x \in U \Rightarrow x \geq s)$となる．従って$s$は$U$の最小元である．$\square$

# 参考文献
- 杉浦光夫「解析入門Ⅰ」
