Linear Algebra Done Right (S. Axler): Exercises 3.B
===================================================

--------------------------------------------------------------------------------------------
### Notation

* $\newcommand{\R}{\mathbb{R}}$
  The set of real numbers: $\R$

* $\newcommand{\C}{\mathbb{C}}$
  The set of complex numbers: $\C$

* $\newcommand{\F}{\mathbb{F}}$
  An arbitrary scalar field:$\F$

* $\newcommand{\span}[1]{\operatorname{span}\left({#1}\right)}$
  The span of $u, v, w$: $\span{u, v, w}$

* $\newcommand{\null}{\operatorname{null}}$
  The null space of $T$: $\null T$

* $\newcommand{\range}{\operatorname{range}}$
  The range of $T$: $\range T$

* $\newcommand{\maps}[2]{\mathcal{L}\left(#1,#2\right)}$
  The set of linear maps from $V$ to $W$: $\maps{V}{W}$

* $\newcommand{\P}[2][]{\mathcal{P}_{#1}\left(#2\right)}$
  The space of polynomials over of field $\F$: $\P{\F}$

*  The space of polynomials of degree at most $m$ over of field $\F$: $\P[m]{\F}$

--------------------------------------------------------------------------------------------
### 1.

__Problem__. Give an example of a linear map $T$ such that $\dim \null T = 3$ and
$\dim \range T = 2$.

__Solution__. Consider $T: \R^5 \rightarrow \R^5$ by

$
T e_1 = 0 \\
T e_2 = 0 \\
T e_3 = 0 \\
T e_4 = e_4 \\
T e_5 = e_5.
$

If $v \in \null T$, then

$$
0
= T(a_1 e_1 + a_2 e_2 + a_3 e_3 + a_4 e_4 + a_5 e_5)
= a_1 T e_1 + a_2 T e_2 + a_3 T e_3 + a_4 T e_4 + a_5 T e_5
= a_4 e_4 + a_5 e_5,
$$

which implies that $a_4 = 0 = a_5$ because linearly independent. Therefore,
$\null T = \span{e_1, e_2, e_3}$ and $\dim \null T = 3$.

Observe that for any $v = a_1 e_1 + a_2 e_2 + a_3 e_3 + a_4 e_4 + a_5 e_5 \in \R^5$,

$$
Tv = T(a_1 e_1 + a_2 e_2 + a_3 e_3 + a_4 e_4 + a_5 e_5)
= a_1 T e_1 + a_2 T e_2 + a_3 T e_3 + a_4 T e_4 + a_5 T e_5
= a_4 e_4 + a_5 e_5,
$$

which implies the following.

* Any $w \in \range T$ can be expressed as a linear combination of $e_4$ and $e_5$, so
  $\range T \subseteq \span{e_4, e_5}$.

* Any $w \in \span{e_4, e_5}$ is the image of the vector $v = w$, so
  $\span{e_4, e_5} \subseteq \range T$.

Therefore, $\range T = \span{e_4, e_5}$, which implies that $\dim \range T = 2$.

--------------------------------------------------------------------------------------------
### 2.

__Problem__. Suppose $V$ is a vector space and $S, T \in \maps{V}{V}$ are such that

$$
\range S \subset \null T.
$$

Prove that $(ST)^2 = 0$.

__Solution__. Let $u \in V$, $v = Tu$, and $w = Sv$. Then

$$
(ST)^2 u = (ST)(ST) u = STS (Tu) = ST (Sv) = S (Tw) = S (0) = 0.
$$

where the second to last equality follows because $w \in \range S$, which implies
$w \in \null T$. Therefore, we can conclude that $(ST)^2 = 0$ because $u$ is an arbitrary
vector in $V$.

--------------------------------------------------------------------------------------------
### 3.

Suppose $v_1, \ldots, v_m$ is a list of vectors in $V$. Define
$T \in \maps{\F^m}{V}$ by

$$
T(z_1, \ldots, z_m) = z_1 v_1 + \cdots + z_m v_m.
$$

#### 3.a.

__Problem__. What property of $T$ corresponds to $v_1, \ldots, v_m$ spanning $V$?

__Solution__. If $\span{v_1, \ldots, v_m} = V$, then $\range T = V$.

#### 3.b.

__Problem__. What property of $T$ corresponds to $v_1, \ldots, v_m$ being linearly
independent?

__Solution__. If $v_1, \ldots, v_m$ are linearly independent, then $\null T = \{0\}$.

--------------------------------------------------------------------------------------------
### 4.

__Problem__. Show that

$$
\{ T \in \maps{\R^5}{\R^4} : \dim \null T > 2 \}
$$

is not a subspace of $\maps{\R^5}{\R^4}$.

__Solution__. Consider the following two linear maps.

$$
T_1 e_1 = 0 \\
T_1 e_2 = 0 \\
T_1 e_3 = 0 \\
T_1 e_4 = e_4 \\
T_1 e_5 = e_5
$$

and

$$
T_2 e_1 = e_1 \\
T_2 e_2 = e_2 \\
T_2 e_3 = 0 \\
T_2 e_4 = 0 \\
T_2 e_5 = 0
$$

Observe that $\dim \null T_1 = 3 = \dim \null T_2$. However,
$\dim \null (T_1 + T_2) = 1 \le 2$ because

$$
(T_1 + T_2) e_1 = e_1 \\
(T_1 + T_2) e_2 = e_2 \\
(T_1 + T_2) e_3 = 0 \\
(T_1 + T_2) e_4 = e_4 \\
(T_1 + T_2) e_5 = e_5.
$$

--------------------------------------------------------------------------------------------
### 5.

__Problem__. Give an example of a linear map $T: \R^4 \rightarrow \R^4$ such that

$$
\range T = \null T.
$$

__Solution__. Consider $T$ defined by the following:

$$
T e_1 = 0 \\
T e_2 = 0 \\
T e_3 = e_1 \\
T e_4 = e_2.
$$

Clearly, $\null T = \span{e_1, e_2}$.

Consider $v = a_1 e_1 + a_2 e_2 + a_3 e_3 + a_4 e_4 \in V$. Then

$$
Tv = T(a_1 e_1 + a_2 e_2 + a_3 e_3 + a_4 e_4)
= a_1 T e_1 + a_2 T e_2 + a_3 T e_3 + a_4 T e_4
= a_3 e_1 + a_4 e_2,
$$

which implies that $\range T = \span{e_1, e_2}$.

Therefore, $\range T = \null T$, as desired.

--------------------------------------------------------------------------------------------
### 6.

__Problem__. Prove that there does not exist a linear map $T: \R^5 \rightarrow \R^5$ such
that

$$
\range T = \null T.
$$

__Solution__. Suppose there exists a linear map satisfying the conditions. If
$\range T = \null T$, then $\dim \range T = \dim \null T$, which implies that
$\dim \null T + \dim \range T$ is even. However, the Fundamental Theorem of Linear Maps
implies that $\dim \null T + \dim \range T = 5$, which is odd. We have arrived at a
contradiction, so our assumption that a linear map exists with the required conditions
is false.

--------------------------------------------------------------------------------------------
### 7.

__Problem__. Suppose $V$ and $W$ are finite-dimentional with $2 \le \dim V \le \dim W$.
Show that $\{ T \in \maps{V}{W} : T \textrm{ is not injective} \}$ is not a subspace of
$\maps{V}{W}$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 8.

__Problem__. Suppose $V$ and $W$ are finite-dimentional with $\dim V \ge \dim W \ge 2$.
Show that $\{ T \in \maps{V}{W} : T \textrm{ is not surjective} \}$ is not a subspace of
$\maps{V}{W}$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 10.

__Problem__. Suppose $v_1, \ldots, v_n$ spans $V$ and $T \in \maps{V}{W}$. Prove that the
list $T v_1, \ldots, T v_n$ spans $\range T$.

__Solution__. Since $v_1, \ldots, v_n$ spans $V$, it contains a basis for $V$. Without
loss of generality, let $v_1, \ldots, v_m$ with $m \le n$ be a basis $V$. Then $T$ is
uniquely defined by $T v_1, \ldots, T v_m$, which implies that
$\range T = \span{T v_1, \ldots, T v_m}$. Therefore, any superset of
$T v_1, \ldots, T v_m$ spans $\range T$ - in particular, $T v_1, \ldots, T v_n$ spans
$\range T$.

--------------------------------------------------------------------------------------------
### 11.

__Problem__. Suppose $S_1, \ldots, S_n$ are injective linear maps such that
$S_1 S_2 \cdots S_n$ makes sense. Prove that $S_1 S_2 \cdots S_n$ is injective.

__Solution__. Let $u$ and $v$ be vectors such that
$(S_1 S_2 \cdots S_n) u = (S_1 S_2 \cdots S_n) v$. Then
$S_1 (S_2 \cdots S_n u) = S_1 (S_2 \cdots S_n v)$. Since $S_1$ is injective,
$S_2 \cdots S_n u = S_2 \cdots S_n v$. Continuing in this manner, we arrive at the
conclusion $u = v$, which implies that $S_1 S_2 \cdots S_n$ is injective.

--------------------------------------------------------------------------------------------
### 12.

__Problem__. Suppose that $V$ is finite-dimensional and that $T \in \maps{V}{W}$. Prove
that there exists a subspace $U$ of $V$ such that $U \cap \null T = \{0\}$ and
$\range T = \{Tu : u \in U\}$.

__Solution__. Because $\null T$ is a subspace of $V$, there exists a subspace $U$ such
that $V$ is the direct sum of $U$ and $\null T$: $V = U \oplus \null T$. By definition,
$U \cap \null T = \{0\}$.

Consider $\range T$. Clearly, $\range T \supseteq \{Tu : u \in U\}$. Now, suppose that
$w \in \range T$. Then there exists $v \in V$ such that $w = Tv$. Since
$V = U \oplus \null T$, $v$ is equal to a unique sum of $u \in U$ and $u^0 \in \null T$
so that

$$
w = Tv = T(u + u^0) = Tu + T u^0 = Tu + 0 = Tu.
$$

In other words, $w$ is the image of a vector $u \in U$, which implies that
$\range T \subseteq \{Tu : u \in U\}$. Therefore, $\range T = \{Tu : u \in U\}$.

--------------------------------------------------------------------------------------------
### 13.

__Problem__. Suppose $T$ is a linear map from $\F^4$ to $\F^2$ such that

$$
\null T = \{ (x_1, x_2, x_3, x_4) \in \F^4 : x_1 = 5 x_2, x_3 = 7 x_4 \}.
$$

Prove that $T$ is surjective.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 14.

__Problem__. Suppose $U$ is a 3-dimensional subspace of $\R^8$ and that $T$ is a linear map
from $\R^8$ to $\R^5$ such that $\null T = U$. Prove that $T$ is surjective.

__Solution__. By the Fundamental Theorem of Linear Maps,

$$
8 = \dim \R^8
= \dim \null T + \dim \range T
= \dim U + \dim \range T
= 3 + \dim \range T.
$$

Simple algebra yields $\dim \range T = 5$, which implies that $\range T = \R^5$ (because
$\range T \subseteq \R^5$). Therefore, $T$ is surjective.

--------------------------------------------------------------------------------------------
### 15.

__Problem__. Prove that there does not exist a linear map from $\F^5$ to $\F^2$ whose null
space equals

$$
\{ (x_1, x_2, x_3, x_4, x_5) \in \F^5 : x_1 = 3 x_2, x_3 = x_4 = x_5 \}.
$$

__Solution__. Suppose there exists a linear map $T: \F^5 \rightarrow \F^2$ satisfying the
desired conditions. Then

$$
5 = \dim \F^5 = \dim \null T + \dim \range T
\le \dim \null T + \dim \F^2 = \dim \null T + 2.
$$

by the Fundamental Theorem of Linear Maps. Therefore, $\dim \null T \ge 3$. Observing that
$\dim \{ (x_1, x_2, x_3, x_4, x_5) \in \F^5 : x_1 = 3 x_2, x_3 = x_4 = x_5 \} = 2$, we
have a contradiction, so our assumption that a linear map exists with the required
conditions is false.

--------------------------------------------------------------------------------------------
### 16.

__Problem__. Suppose there exists a linear map on $V$ whose null space and range are both
finite-dimensional. Prove that $V$ is finite-dimensional.

__Solution__. Let $T$ be a linear map with finite-dimensional null space and range. By the
Fundamental Theorem of Linear Maps, $\dim V = \dim \null T + \dim \range T < \infty$, which
yields the desired result.

--------------------------------------------------------------------------------------------
### 17.

__Problem__. Suppose $V$ and $W$ are both finite-dimensional. Prove that there exists an
injective linear map from $V$ to $W$ if and only if $\dim V \le \dim W$.

__Solution__

($\Rightarrow$) Let $T$ be an injective linear map from $V$ to $W$. Then $\null T = \{0\}$.
The Fundamental Theorem of Linear Maps implies that

$$
\dim V
= \dim \null T + \dim \range T
= \dim \range T
\le \dim W.
$$

where the inequality follows because $\range T$ is a subspace of $W$.

($\Leftarrow$) Let $v_1, \ldots, v_n$ and $w_1, \ldots, w_m$ be bases for $V$ and $W$,
respectively, where $n = \dim V$ and $m = \dim W$. Since $\dim V \le \dim W$, we can
define a linear map $T: V \rightarrow W$ by $T v_i = w_i$ for all $1 \le i \le n$.
Consider $v = \sum_{i=1}^n a_i v_i \in \null T$. Then

$$
0 = T v
= T \left( \sum_{i=1}^n a_i v_i \right)
= \sum_{i=1}^n a_i T v_i
= \sum_{i=1}^n a_i w_i,
$$

which implies $a_i = 0$ for $1 \le i \le n$ because $w_1, \ldots, w_n$ are linearly
independent. Therefore, $v = 0$, so we can conclude that $\null T = \{0\}$. In other
words, $T$ is injective.

--------------------------------------------------------------------------------------------
### 18.

__Problem__. Suppose $V$ and $W$ are both finite-dimensional. Prove that there exists an
surjective linear map from $V$ to $W$ if and only if $\dim V \ge \dim W$.

__Solution__

($\Rightarrow$) Let $T$ be an surjective linear map from $V$ to $W$. Then $\range T = W$.
The Fundamental Theorem of Linear Maps implies that

$$
\dim V
= \dim \null T + \dim \range T
= \dim \null T + \dim W
\ge \dim W
$$

where the inequality follows because $\dim \null T \ge 0$.

($\Leftarrow$) Let $v_1, \ldots, v_n$ and $w_1, \ldots, w_m$ be bases for $V$ and $W$,
respectively, where $n = \dim V$ and $m = \dim W$. Since $\dim V \ge \dim W$, we can
define a linear map $T: V \rightarrow W$ with

$$
T v_i = w_i \textrm{ for $1 \le i \le m$} \\
T v_i = 0 \textrm{ for $m < i \le n$}.
$$

Consider $w = \sum_{i=1}^m a_i w_i\in W$. Then $T$ maps $v = \sum_{i=1}^m a_i v_i$ to $w$:

$$
T v
= T \left( \sum_{i=1}^m a_i v_i \right)
= \sum_{i=1}^m a_i T v_i
= \sum_{i=1}^m a_i w_i
= w.
$$

Therefore $w \in \range T$, which implies that $T$ is surjective.

--------------------------------------------------------------------------------------------
### 19.

__Problem__. Suppose $V$ and $W$ are both finite-dimensional and that $U$ is a subspace of
$V$. Prove that there exists $T \in \maps{V}{W}$ such that $\null T = U$ if and only if
$\dim U \ge \dim V - \dim W$.

__Solution__

($\Rightarrow$) If $\null T = U$, then

$$
\dim V
= \dim \null T + \dim \range T
= \dim U + \dim \range T
$$

by the Fundamental Theorem of Linear Maps. Rearranging,

$$
\dim U
= \dim V - \dim \range T
\ge \dim V - \dim W
$$

where the inequality follows because $\range T \subseteq W$.

($\Leftarrow$) Because $U$ is a subspace of $V$, there exists a subspace $U^r$ such
that $V$ is the direct sum of $U$ and $U^r$: $V = U \oplus U^r$. Let $u_1, \ldots, u_n$
and $u^r_1, \ldots, u^r_p$ be bases for $U$ and $U^r$, respectively with $n = \dim U$ and
$p = \dim U^r$. Let $w_1, \ldots, w_m$ be a basis for $W$. Observe that $p \le m$ because
$\dim U \ge \dim V - \dim W$. Therefore, we can define a linear map $T: V \rightarrow W$
by

$$
T u_i = 0 \\
T u^r_i = w_i \textrm{ for $1 \le i \le p$}
$$

By definition, $U \subseteq \null T$. Now, suppose that
$v = \sum_{i=1}^n a_i u_i + \sum_{i=1}^p b_i u^r_i \in \null T$. Then

$$
0
= T v
= T \left( \sum_{i=1}^n a_i u_i + \sum_{i=1}^p b_i u^r_i \right)
= \sum_{i=1}^n a_i T u_i + \sum_{i=1}^p b_i T u^r_i
= \sum_{i=1}^p b_i w_i,
$$

which implies that $b_i = 0$ for $1 \le i \le p$ because the $w_i$ are linearly independent.
In other words, $v \in U$, which implies that $\null T \subseteq U$. Combining these
results, we have demonstrated, by construction, the existence of a linear map with
$\null T = U$.

--------------------------------------------------------------------------------------------
### 20.

__Problem__. Suppose $V$ and $W$ are both finite-dimensional and that $T \in \maps{V}{W}$.
Prove that $T$ is injective if and only if there exists $S \in \maps{W}{V}$ such that
$ST$ is the identity map on $V$.

__Solution__.

($\Rightarrow$) Let $U$ be the subspace of $W$ such that $W = U \oplus \range T$. Then each
$w \in W$ can be expressed as a unique sum $w = u + w^r$ where $u \in U$ and
$w^r \in \range T$. Define $S: W \rightarrow V$ by $Sw = v$ where $Tv = w^r$. Note that
$S$ is well-defined because $T$ is injective, which guarantees that for each
$w^r \in \range T$, there exists a unique $v \in V$ such that $Tv = w^r$.

Consider $w_1, w_2 \in W$ and define $v_i$ such that $T v_i = w^r_i$ where
$w_i = u_i + w^r_i$ with $u_i \in U$ and $w^r_i \in \range T$. The following two
observations lead to the conclusion that $S$ is a linear map.

* $T(v_1 + v_2) = T v_1 + T v_2 = w^r_1 + w^r_2$ implies that

  $$
  S(w_1 + w_2)
  = S(u_1 + w^r_1 + u_2 + w^r_2)
  = S(u_1 + u_2 + w^r_1 + w^r_2)
  = v_1 + v_2
  = S w_1 + S w_2.
  $$

* $T(\lambda v_1) = \lambda T v_1 = \lambda w^r_1$, implies that

  $$
  S(\lambda w_1)
  = S(\lambda(u_1 + w^r_1))
  = S(\lambda u_1 + \lambda w^r_1)
  = \lambda v_1
  = \lambda (S w_1).
  $$

Finally, we show that $ST$ is the identity map on $V$. Let $v \in V$ and $w = Tv$, then

$$
ST(v) = S(Tv) = Sw = v
$$

where the last equality follows from the definition of $S$ because $w \in \range T$. Since
$ST(v) = v$ for all $v \in V$, $ST$ is the identity on $V$.

($\Leftarrow$) Let $v_1, v_2 \in V$ such that $T v_1 = T v_2$, then

$$
v_1 = (ST) v_1 = S (T v_1) = S (T v_2) = (ST) v_2 = v_2.
$$

Therefore, $T$ is injective.

--------------------------------------------------------------------------------------------
### 21.

__Problem__. Suppose $V$ and $W$ are both finite-dimensional and that $T \in \maps{V}{W}$.
Prove that $T$ is surjective if and only if there exists $S \in \maps{W}{V}$ such that
$TS$ is the identity map on $W$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 22.

__Problem__. Suppose $U$ and $V$ are finite-dimensional vector spaces and
$S \in \maps{V}{W}$ and $T \in \maps{U}{V}$. Prove that

$$
\dim \null ST \le \dim \null S + \dim \null T.
$$

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 23.

__Problem__. Suppose $U$ and $V$ are finite-dimensional vector spaces and
$S \in \maps{V}{W}$ and $T \in \maps{U}{V}$. Prove that

$$
\dim \range ST \le \min\{ \dim \range S, \dim \range T \}.
$$

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 24.

__Problem__. Suppose $W$ is finite-dimensional and $T_1, T_2 \in \maps{V}{W}$. Prove that
$\null T_1 \subset \null T_2$ if and only if there exists $S \in \maps{W}{W}$ such that
$T_2 = S T_1$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 25.

__Problem__. Suppose $V$ is finite-dimensional and $T_1, T_2 \in \maps{V}{W}$. Prove that
$\range T_1 \subset \range T_2$ if and only if there exists $S \in \maps{V}{V}$ such that
$T_1 = T_2 S$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 26.

__Problem__. Suppose $D \in \maps{\P{\R}}{\P{\R}}$ is such that $\deg Dp = (\deg p) - 1$
for every nonconstant polynomial $p \in \P{\R}$. Prove that $D$ is surjective.

[The notation $D$ is used above to remind you of the differentiation map that sends a
polynomial $p$ to $p'$. Without knowing the formula for the derivative of a polynomial
(except that it reduces the degree by 1), you can use the exercise above to show that for
every polynomial $q \in \P{\R}$, there exists a polynomial $p \in \P{\R}$ such that
$p' = q$.]

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 27.

__Problem__. Suppose $p \in \P{\R}$. Prove that there exists a polynomial $q \in \P{\R}$
such that $5q'' + 3q' = p$.

[This exercise can be done without linear algebra, but it's more fun to do it using linear
algebra.]

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 28.

__Problem__. Suppose $T \in \maps{V}{W}$, and $w_1, \ldots, w_m$ is a basis of $\range T$.
Prove that there exist $\varphi_1, \ldots, \varphi_m \in \maps{V}{\F}$ such that

$$
T v = \varphi_1(v) w_1 + \cdots \varphi_m(v) w_m
$$

for every $v \in V$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 29.

__Problem__. Suppose $\varphi \in \maps{V}{\F}$. Suppose $u \in V$ is not in
$\null \varphi$. Prove that

$$
V = \null \varphi \oplus \{au : a \in \F \}.
$$

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 30.

__Problem__. Suppose $\varphi_1$ and $\varphi_2$ are linear maps from $V$ to $\F$ that have
the same null space. Show that there exists a constant $c \in \F$ such that
$\varphi_1 = c \varphi_2$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 31.

__Problem__. Give an example of two linear maps $T_1$ and $T_2$ from $\R^5$ to $\R^2$ that
have the same null space but are such that $T_1$ is not a scalar multiple of $T_2$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
