Linear Algebra Done Right (S. Axler): Exercises 2.A
===================================================

-------------------------------------------------------------------------------
### 1.

__Problem__. Suppose $v_1$, $v_2$, $v_3$, $v_4$ span $V$. Prove that the list

\[
  v_1 - v_2, v_2 - v_3, v_3 - v_4, v_4
\]

also spans $V$.

__Solution__. First, observe that $v_1$, $v_2$, $v_3$, $v_4$ span $V$ implies
that $\operatorname{span}(v_1, v_2, v_3, v_4) = V$. Since
$v_1 - v_2, v_2 - v_3, v_3 - v_4, v_4$ are all linear combinations of
$v_1, v_2, v_3, v_4$, we can conclude that

\[
\operatorname{span}(v_1 - v_2, v_2 - v_3, v_3 - v_4, v_4) \subseteq
\operatorname{span}(v_1, v_2, v_3, v_4) = V.
\]

Reversing the roles of the two lists of vectors, we can conclude that

\[
V = \operatorname{span}(v_1, v_2, v_3, v_4) \subseteq
\operatorname{span}(v_1 - v_2, v_2 - v_3, v_3 - v_4, v_4).
\]

Combining these two inclusions yields the desired result:

\[
\operatorname{span}(v_1 - v_2, v_2 - v_3, v_3 - v_4, v_4) = V
\]

-------------------------------------------------------------------------------
### 2.

__Problem__. Verify the assertions in Example 2.18.

__Solution__. TODO

-------------------------------------------------------------------------------
### 3.

__Problem__. Find a number $t$ such that

\[
  (3, 1, 4), (2, -3, 5), (5, 9, t)
\]

is not linearly independent in $\mathbb{R}^3$.

__Solution__. For this set of vectors to be linearly dependent, we need
$(5, 9, t)$ to be a linear combination of $(3, 1, 4)$ and $(2, -3, 5)$. That
is,

\[
  (5, 9, t) = a (3, 1, 4) + b (2, -3, 5).
\]

Solving for $a$ and $b$ that satisfy

\[
  3 a + 2 b = 5 \\
    a - 3 b = 9,
\]

we find that $a = 3$ and $b = -2$. Therefore, taking $t = 4 a + 5 b = 2$
yields a linearly dependent set of vectors.

-------------------------------------------------------------------------------
### 4.

__Problem__. Verify the assertion in the second bullet point in Example 2.20.

__Solution__. TODO

-------------------------------------------------------------------------------
### 5.

#### 5.a.

__Problem__. Show that if we think of $\mathbb{C}$ as a vector space over
$\mathbb{R}$, then the list $(1 + i, 1 - i)$ is linearly independent.

__Solution__. Suppose $a (1 + i) + b (1 - i) = 0$. Thinking of the complex
numbers as a two-dimensional vector space over the real numbers, this equation
implies that

\[
  a + b = 0 \\
  a - b = 0.
\]

Solving this system of equation, we find that $a = b = 0$. Therefore, the list
$(1 + i, 1 - i)$ is linearly independent.

#### 5.b.

__Problem__. Show that if we think of $\mathbb{C}$ as a vector space over
$\mathbb{C}$, then the list $(1 + i, 1 - i)$ is linearly dependent.

__Solution__.  In the linear combination $a (1 + i) + b (1 - i)$, both $a$ and
$b$ can be complex numbers. Taking $a = 1 - i$ and $b = -1 - i$ yields
$a (1 + i) + b (1 - i) = 2 - 2 = 0$. Therefore, $1 + i$ and $1 - i$ are
linearly dependent.

-------------------------------------------------------------------------------
### 6.

__Problem__. Suppose $v_1$, $v_2$, $v_3$, $v_4$ is linearly independent in $V$.
Prove that the list

\[
  v_1 - v_2, v_2 - v_3, v_3 - v_4, v_4
\]

is also linearly independent.

__Solution__. Consider a linear combination of $v_1 - v_2$, $v_2 - v_3$,
$v_3 - v_4$, $v_4$ that is equal to 0:

\[
  a (v_1 - v_2) + b (v_2 - v_3) + c(v_3 - v_4) + d v_4 = 0
\]

Rearranging this equation, we find that

\[
  a v_1 + (b - a) v_2 + (c - b) v_3 + (d - c) v_4 = 0.
\]

Since $v_1$, $v_2$, $v_3$, $v_4$ are linearly independent, $a = 0$,
$(b - a) = 0$, $(c - b) = 0$, and $(d - c) = 0$. Solving this system of
equations, we find that $a = b = c = d = 0$. Therefore, the list of vectors
$v_1 - v_2$, $v_2 - v_3$, $v_3 - v_4$, and $v_4$ is linearly independent.

-------------------------------------------------------------------------------
### 7.

__Problem__. Prove or give a counterexample: If $v_1, v_2, v_3, \ldots, v_m$
is a linearly independent list of vectors in $V$, then

\[
  5 v_1 - 4 v_2, v_2, v_3, \ldots, v_m
\]

is linearly independent.

__Solution__. The list of vectors

\[
  5 v_1 - 4 v_2, v_2, v_3, \ldots, v_m
\]

is linearly independent. Let a linear combination of this list of vectors be
equal to 0:

\[
  0
  = c_1 (5 v_1 - 4 v_2) + c_2 v_2 + c_3 v_3 + \cdots + c_m v_m \\
  = 5 c_1 v_1 + (c_2 - 4 c_1) v_2 + c_3 v_3 + \cdots + c_m v_m
\]

Since $v_1, v_2, \ldots, v_m$ are linearly independent,

\[
  5 c_1 = 0 \\
  c_2 - 4 c_1 = 0 \\
  c_3 = c_4 = \cdots = c_m = 0.
\]

The solution to the first two equations is $c_1 = 0 = c_2$, which yields the
desired conclusion.

-------------------------------------------------------------------------------
### 8.

__Problem__. Prove or give a counterexample: If $v_1, v_2, v_3, \ldots, v_m$
is a linearly independent list of vectors in $V$ and $\lambda \in \mathbb{F}$
with $\lambda \ne 0$, then $\lambda v_1, \lambda v_2, \ldots, \lambda v_m$
is linearly independent.

__Solution__. The list of vectors

\[
  \lambda v_1, \lambda v_2, \ldots, \lambda v_m
\]

is linearly independent. Let a linear combination of this list of vectors be
equal to 0:

\[
  0
  = c_1 (\lambda v_1) + c_2 (\lambda v_2) + \cdots + c_m (\lambda v_m) \\
  = \lambda (c_1 v_1 + c_2 v_2 + \cdots + c_m v_m),
\]

which implies that $c_1 v_1 + c_2 v_2 + \cdots + c_m v_m = 0$. Since
$v_1, v_2, \ldots, v_m$ are linearly independent, $c_1 = \cdots = c_m = 0$,
which yields the desired conclusion.

-------------------------------------------------------------------------------
### 9.

__Problem__. Prove or give a counterexample: If $v_1, v_2, v_3, \ldots, v_m$
and $w_1, w_2, w_3, \ldots, w_m$ are linearly independent lists of vectors in
$V$, then $v_1 + w_1, v_2 + w_2, \ldots, v_m + w_m$ is linearly independent.

__Solution__. The list of vectors

\[
  v_1 + w_1, v_2 + w_2, \ldots, v_m + w_m
\]

is not necessarily linearly independent. As a counterexample, let
$v_1, v_2, v_3, \ldots, v_m$ be linearly independent and $w_i = -v_i$
for all $i$. Then $w_1, w_2, w_3, \ldots, w_m$ are linearly independent.
However, $v_i + w_i = 0$ for all $i$, so the set of $v_i + w_i$ are not
linearly independent.

-------------------------------------------------------------------------------
### 10.

__Problem__. Suppose that $v_1, v_2, v_3, \ldots, v_m$ is linearly independent
in $V$ and $w \in V$. Prove that if $v_1 + w, v_2 + w, \ldots, v_m + w$ is
linearly dependent, then $w \in \operatorname{span}(v_1, \ldots, v_m)$.

__Solution__. Since $v_1 + w, v_2 + w, \ldots, v_m + w$ is linearly dependent,
there exist $c_1, c_2, \ldots, c_m$ not all zero such that

\[
  c_1 (v_1 + w) + c_2 (v_2 + w) + \cdots c_m (v_m + w) = 0.
\]

Rearranging this equations, we can express $w$ in terms of $v_1, \ldots, v_m$:

\[
  w
  = -\frac{c_1 v_1 + \cdots + c_m v_m}{c_1 + \cdots + c_m} \\
  = -\sum \left(\frac{c_i}{c_1 + \cdots + c_m}\right) v_i,
\]

where we are guaranteed that the denominator is nonzero because at least one
of the $c_i$ is nonzero. Therefore, $w$ is equal to linear combination of the
$v_i$, which implies that $w \in \operatorname{span}(v_1, \ldots, v_m)$.

-------------------------------------------------------------------------------
### 11.

__Problem__. Suppose that $v_1, v_2, v_3, \ldots, v_m$ is linearly independent
in $V$ and $w \in V$. Show that $v_1, v_2, \ldots, v_m, w$ is linearly
independent if and only if $w \notin \operatorname{span}(v_1, \ldots, v_m)$.

__Solution__.

$(\Rightarrow)$ We prove the contrapositive. Suppose that
$w \in \operatorname{span}(v_1, \ldots, v_m)$. Then $w$ is a linear
combination of the $v_i$:

\[
  w = c_1 v_1 + \cdots c_m v_m,
\]

where at least one $c_i$ is nonzero. Rearranging this equation, we find a
nontrivial linear combination of the $v_1, \ldots, v_m, w$ that sum to zero,
which implies tht $v_1, v_2, \ldots, v_m, w$ is not linearly independent.

$(\Leftarrow)$ We prove the contrapositive. If $w = 0$, then clearly,
$w \in \operatorname{span}(v_1, \ldots, v_m)$. If $w \ne 0$ and
$v_1, v_2, \ldots, v_m, w$ is linearly dependent, then there exist
$c_1, \ldots, c_m, c_w$ not all zero such that

\[
  0 = c_1 v_1 + \ldots + c_m v_m + c_w w
\]

Note that the linear independence of $v_1, \ldots, v_m$ implies that $c_w$
cannot be zero - otherwise all of the $c_i$ would be forced to be zero.
Since $c_w \ne 0$, we can solve for $w$ as

\[
  w =
  -\frac{1}{c_w} (c_1 v_1 + \ldots + c_m v_m) \\
  =   \left(\frac{-c_1}{c_w}\right) v_1 + \ldots
    + \left(\frac{-c_m}{c_w}\right) v_m
\]

where at least one of $c_i \ne 0$ because $w \ne 0$. Therefore, $w$ is a
linear combination of $v_1, \ldots, v_m$, so we can conclude that
$w \in \operatorname{span}(v_1, \ldots, v_m)$.



-------------------------------------------------------------------------------
### 12.

__Problem__. Explain why there does not exist a list of six polynomials that is
linearly independent in $\mathcal{P}_4 (\mathbb{F})$.

__Solution__. The list of polynomials $1, x, x^2, x^3, x^4$ spans the vector
space $\mathcal{P}_4 (\mathbb{F})$. Therefore, any list of linearly independent
polynomials in $\mathcal{P}_4 (\mathbb{F})$ must at most 5 elements because
the length of any list of linearly independent vectors in a vector space is
bounded above by the length of any list of spanning vectors for the vector
space.

-------------------------------------------------------------------------------
### 13.

__Problem__. Explain why no list of four polynomials spans
$\mathcal{P}_4 (\mathbb{F})$.

__Solution__. The list of polynomials $1, x, x^2, x^3, x^4$ is linearly
independent in $\mathcal{P}_4 (\mathbb{F})$. Therefore, any list of polynomials
that spans $\mathcal{P}_4 (\mathbb{F})$ must contain at least 5 elements
because the length of any list of spanning vectors in a vector space is bounded
below by the length of any list of linearly independent vectors for the vector
space.

-------------------------------------------------------------------------------
### 14.

__Problem__. Prove that $V$ is infinite-dimensional if and only if there is a
sequence $v_1, v_2, \ldots$ of vectors in $V$ such that $v_1, v_2, \ldots, v_m$
is linearly independent for every positive integer $m$.

__Solution__.

$(\Rightarrow)$ Let $V$ be infinite-dimensional. We construct an infinite
sequence satisfying the desired properties by induction. Let $v_1 \in V$.
Clearly, $v_1$ is linearly independent. Now, suppose that $v_1, \ldots, v_k$
are $k$ linearly independent vectors in $V$. Since $V$ is infinite-dimensional,
$v_1, \ldots, v_k$ does not span $V$, so we can choose
$v_{k+1} \in V - \operatorname{span}(v_1, \ldots, v_k)$. Observe that
$v_1, \ldots, v_k, v_{k+1}$ must be linearly independent. Otherwise,
the linear independence of $v_1, \ldots, v_k$ implies that $v_{k+1}$ can be
expressed as a nontrivial linear combination of $v_1, \ldots, v_k$,
contradicting the fact that $v_{k+1}$ is not in the span of $v_1, \ldots, v_k$.
Continuing in this manner yields a sequence of vectors $v_1, v_2, \ldots$
satisfying the desired property that $v_1, \ldots, v_m$ is linearly independent
for every positive integer $m$.

$(\Leftarrow)$ We prove the contrapositive. If $V$ is finite-dimensional, then
there exists a finite list of vectors $w_1, w_2, \ldots, w_n$ that spans $V$.
Since the length of any list of linearly independent vectors in $V$ is bounded
above by $n$, any sequence of vectors $v_1, v_2, \ldots, v_m$ with $m > n$
must be linearly dependent. Therefore, there cannot exist a sequence
$v_1, v_2, \ldots$ in $V$ such that $v_1, \ldots, v_m$ in $V$ is linearly
independent for every positive integer $m$.

-------------------------------------------------------------------------------
### 15.

__Problem__. Prove that $\mathbb{F}^\infty$ is infinite-dimensional.

__Solution__. Let $v_i \in \mathbb{F}^\infty$ be the infinite sequence
consisting of 0s except for a single 1 at the $i$-th position. The infinite
sequence of vectors $v_1, v_2, \ldots$ satisfies the property that
$v_1, \ldots, v_m$ is linearly independent for every positive $m$. Therefore,
by Problem #14, $\mathbb{F}^\infty$ is infinite-dimensional.

-------------------------------------------------------------------------------
### 16.

__Problem__. Prove that the real vector space of all continuous real-valued
functions on the interval $[0, 1]$ is infinite-dimensional.

__Solution__. Let $f_n(x)$ be equal to 0 for when $x \ne 1/n$ and equal to 1
when $x = 1/n$. Then $f_1, f_2, \ldots$ is an infinite sequence of functions
with the property that $f_1, \ldots, f_m$ is linearly independent for every
positive $m$. Therefore, by Problem #14, $\mathbb{F}^\infty$ is
infinite-dimensional.

-------------------------------------------------------------------------------
### 17.

__Problem__. Suppose $p_0, p_1, \ldots, p_m$ are polynomials in
$\mathcal{P}_m (\mathbb{F})$ such that $p_j(2) = 0$ for each $j$. Prove that
$p_0, p_1, \ldots, p_m$ is not linearly independent in
$\mathcal{P}_m (\mathbb{F})$.


__Solution__. $p_j(2) = 0$ for each $j$ implies that each $p_j(x)$ can be
expressed as a product $(x-2) q_j(x)$ where $q_j$ is a polynomial in
$\mathcal{P}_{m-1} (\mathbb{F})$. Since the dimension of
$\mathcal{P}_{m-1} (\mathbb{F})$ is $m$, the $m+1$ polynomials $q_j$ must be
linearly dependent. Therefore, there exist $a_0, a_1, \ldots, a_m$ not all
to zero such that

\[
  a_0 q_0(x) + a_1 q_1(x) + \cdots + a_m q_m(x) = 0.
\]

Multiplying this equation by $(x-2)$, we obtain a nontrivial linear combination
of the $p_0, p_1, \ldots, p_m$ that equals zero:

\[
  (x-2) \left( a_0 q_0(x) + a_1 q_1(x) + \cdots + a_m q_m(x) \right)
  = a_0 p_0(x) + a_1 p_1(x) + \cdots + a_m p_m(x) = 0,
\]

which yields the desired result.

-------------------------------------------------------------------------------
