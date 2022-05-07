Linear Algebra Done Right (S. Axler): Exercises 2.C
===================================================

-------------------------------------------------------------------------------
### 1.

__Problem__. Suppose $V$ is finite-dimensional and $U$ is a subspace of $V$
such that $\dim U = \dim V$. Prove that $U = V$.

__Solution__. Clearly, $U \subseteq V$, so it suffices to show that
$V \subseteq U$. Since $U$ is a subspace of $V$, any basis
$v_1, \ldots, v_n$ for $U$ is linearly independent in $V$. Since
$\dim U = \dim V = n$, $v_1, \ldots, v_n$ is actually a basis for $V$, which
implies that $V \subseteq \operatorname{span} (v_1, \ldots, v_n) = U$. Thus,
we can conclude that $U = V$.

-------------------------------------------------------------------------------
### 2.

__Problem__. Show that the subspaces of $\mathbb{R}^2$ are precisely $\{ 0 \}$,
$\mathbb{R}^2$, and all lines in $\mathbb{R}^2$ through the origin.

__Solution__.  Let $V$ be a subspace of $\mathbb{R}^2$. Since $\mathbb{R}^2$
is 2-dimensional, $V$ must have dimension 0, 1, or 2. We consider each case in
turn.

$\dim V = 0$. The basis for $V$ is empty, so the only vector in $V$ is 0. That
is $V = \{ 0 \}$.

$\dim V = 1$. The basis of $V$ contains a single vector $v_1$. Therefore,
$V$ is the set of vectors $a v_1$ where $a \in \mathbb{R}$. In other words,
$V$ is precisely the set points that lie on a line through the origin with
direction defined by $v_1$.

$\dim V = 2$. From Problem 1, $\dim V = \dim \mathbb{R}^2$ implies that
$V = \mathbb{R}^2$.

-------------------------------------------------------------------------------
### 3.

__Problem__. Show that the subspaces of $\mathbb{R}^3$ are precisely $\{ 0 \}$,
$\mathbb{R}^3$, all lines in $\mathbb{R}^3$ through the origin, and
all planes in $\mathbb{R}^3$ through the origin.

__Solution__.  Let $V$ be a subspace of $\mathbb{R}^3$. Since $\mathbb{R}^3$
is 3-dimensional, $V$ must have dimension 0, 1, 2, 3. The proofs for the cases
$\dim V = 0$ and $\dim V = 1$ are identical to the proofs for these cases in
Problem 2. The reasoning for the case $\dim V = 3$ is analogous to the case
$\dim V = 2$ in Problem 2. Thus, we need only supply a proof for the case
$\dim V = 2$.

$\dim V = 2$. The basis of $V$ contains a two linearly independent vectors
$v_1$ and $v_2$. Therefore, $V$ is the set of vectors $a_1 v_1 + a_2 v_2$ where
$a_1, a_2 \in \mathbb{R}$. The linear independence of $v_1$ and $v_2$ implies
that $a_1 v_1 + a_2 v_2$ is not a scalar multiple of $v_1$ or $v_2$ (because
$v_2$ is not a scalar multiple of $v_1$ and vice versa). In other words, $V$ is
a plane. More precisely, $V$ is the plane through the origin containing $v_1$
and $v_2$.

-------------------------------------------------------------------------------
### 4.

#### 4.a.

__Problem__. Let $U = \{ p \in \mathcal{P}_4(\mathbb{F}) | p(6) = 0 \}$.
Find a basis of $U$.

__Solution__. Consider the set of polynomials

\[
  p_1(x) = x - 6 \\
  p_2(x) = x (x - 6) \\
  p_3(x) = x^2 (x - 6) \\
  p_4(x) = x^3 (x - 6).
\]

Observe that $p_1, p_2, p_3, p_4$ are linearly independent because any linear
combination of $p_1, p_2, p_3, p_4$ can rearranged into the form

\[
a_1 p_1(x) + a_2 p_2(x) + a_3 p_3(x) + a_4 p_4(x)
= (x - 6) \left( a_1 + a_2 x + a_3 x^2 + a_4 x^4 \right)
\]

and $1, x, x^2, x^3$ are linearly independent.

To show that $p_1, p_2, p_3, p_4$ span $U$, consider $p \in U$. $p(6) = 0$
implies that $p$ can be expressed as the product of $(x - 6)$ and a polynomial
of degree at most 3:

\[
  p(x) = (x - 6) (a_1 + a_2 x + a_3 x^2 + a_4 x^3)
       = a_1 p_1(x) + a_2 p_2(x) + a_3 p_3(x) + a_4 p_4(x).
\]

In other words, $p \in \operatorname{span}(p_1, p_2, p_3, p_4)$ and
$p_1, p_2, p_3, p_4$ span $U$.

Because $p_1, p_2, p_3, p_4$ are linearly independent and span $U$, they
form a basis for $U$.

#### 4.b.

__Problem__. Extend the basis in part (a) to a basis of
$\mathcal{P}_4(\mathbb{F})$.

__Solution__. Add $p_0 = 1$ to the basis in part (a). Suppose there exists a
linear combination of $p_0, \ldots, p_4$ that is equal to 0:

\[
  0 = a_0 p_0(x) + a_1 p_1(x) + a_2 p_2(x) + a_3 p_3(x) + a_4 p_4(x).
\]

Choosing $x = 6$, we see that $a_0 = 0$, which implies that

\[
  0 = a_1 p_1(x) + a_2 p_2(x) + a_3 p_3(x) + a_4 p_4(x).
\]

Therefore, $a_1 = a_2 = a_3 = a_4 = 0$ because $p_1, p_2, p_3, p_4$ are
linearly independent. Thus, we can conclude that $p_0, \ldots, p_4$ are
linearly independent, which implies that $p_0, \ldots, p_4$ is a basis for
$\mathcal{P}_4(\mathbb{F})$ because the number of basis polynomials is equal
to the dimension of $\mathcal{P}_4(\mathbb{F})$.

#### 4.c.

__Problem__. Find a subspace $W$ of $\mathcal{P}_4(\mathbb{F})$ such that
$\mathcal{P}_4(\mathbb{F}) = U \oplus W$.

__Solution__. If $W$ is constructed as the span of any basis of vectors that
extends a basis for $U$ to a basis for $\mathcal{P}_4(\mathbb{F})$, then
$\mathcal{P}_4(\mathbb{F}) = U \oplus W$. Therefore,
$W = \operatorname{span}(p_0)$, the subspace of constant polynomials, is a
subspace having the desired property.

-------------------------------------------------------------------------------
### 5.

#### 5.a.

__Problem__. Let $U = \{ p \in \mathcal{P}_4(\mathbb{F}) | p''(6) = 0 \}$.
Find a basis of $U$.

__Solution__. Consider the set of polynomials

\[
  p_0(x) = 1 \\
  p_1(x) = (x - 6) \\
  p_3(x) = (x - 6)^3 \\
  p_4(x) = (x - 6)^4.
\]

Observe that $p_0, p_1, p_3, p_4$ are linearly independent because monomials
form a basis over polynomials and $p_0, p_1, p_3, p_4$ are a subset of the
monomials.

To show that $p_0, p_1, p_3, p_4$ span $U$, consider $p \in U$. $p''(6) = 0$
implies that $p''(x) $ can be expressed as the product of $(x - 6)$ and a
polynomial of degree at most 1 (so that integrating twice yields a polynomial
of at most 4):

\[
  p''(x) = (x - 6) \left( a_3 + a_4 (x - 6) \right)
         = a_3 (x - 6) + a_4 (x - 6)^2,
\]

where we have expressed the second factor in terms of the basis $1, (x-6)$.

Integrating $p''$ yields

\[
  p'(x) = a_1 + \frac{a_3}{2} (x - 6)^2 + \frac{a_4}{3} (x - 6)^3,
\]

where $a_1$ is the integration constant.

Integrating a second time, we obtain

\[
  p(x) = a_0 + a_1 (x - 6) + \frac{a_3}{6} (x - 6)^3
       + \frac{a_4}{12} (x - 6)^4,
\]

where $a_0 - 6 a_1$ is the integration constant. In other words, $p$ is a
linear combination of $p_0, p_1, p_3, p_4$ and $p_0, p_1, p_3, p_4$ span $U$.

Because $p_0, p_1, p_3, p_4$ are linearly independent and span $U$, they
form a basis for $U$.

#### 5.b.

__Problem__. Extend the basis in part (a) to a basis of
$\mathcal{P}_4(\mathbb{F})$.

__Solution__. Add $p_2(x) = (x - 6)^2$ to the basis in part (a). Suppose there
exists a linear combination of $p_0, \ldots, p_4$ that is equal to 0:

\[
  0 = a_0 p_0(x) + a_1 p_1(x) + a_2 p_2(x) + a_3 p_3(x) + a_4 p_4(x).
\]

Differentiating twice and choosing $x = 6$, we see that $a_2 = 0$, which
implies that

\[
  0 = a_0 p_0(x) + a_1 p_1(x) + a_3 p_3(x) + a_4 p_4(x).
\]

Therefore, $a_0 = a_1 = a_3 = a_4 = 0$ because $p_0, p_1, p_3, p_4$ are
linearly independent. Thus, we can conclude that $p_0, \ldots, p_4$ are
linearly independent, which implies that $p_0, \ldots, p_4$ is a basis for
$\mathcal{P}_4(\mathbb{F})$ because the number of basis polynomials is equal
to the dimension of $\mathcal{P}_4(\mathbb{F})$.

#### 5.c.

__Problem__. Find a subspace $W$ of $\mathcal{P}_4(\mathbb{F})$ such that
$\mathcal{P}_4(\mathbb{F}) = U \oplus W$.

__Solution__. If $W$ is constructed as the span of any basis of vectors that
extends a basis for $U$ to a basis for $\mathcal{P}_4(\mathbb{F})$, then
$\mathcal{P}_4(\mathbb{F}) = U \oplus W$. Therefore,
$W = \operatorname{span}(p_2)$, the subspace of multiples of $(x - 6)^2$, is a
subspace having the desired property.

-------------------------------------------------------------------------------
### 6.

#### 6.a.

__Problem__. Let $U = \{ p \in \mathcal{P}_4(\mathbb{F}) | p(2) = p(5) \}$.
Find a basis of $U$.

__Solution__. Consider the set of polynomials

\[
  p_0(x) = 1 \\
  p_2(x) = (x - 3.5)^2 \\
  p_4(x) = (x - 3.5)^4 \\
  p_{1,3}(x) = (x - 3.5) - \frac{4}{9} (x - 3.5)^3.
\]

First, we show that $p_0, p_2, p_4, p_1,3$ are linearly independent. Suppose
that

\[
  0 = a_0 p_0(x) + a_2 p_2(x) + a_4 p_4(x) + a_{1,3} p_{1,3}(x),
\]

which can be rearranged to

\[
  a_0 p_0(x) + a_2 p_2(x) + a_4 p_4(x) = -a_{1,3} p_{1,3}(x).
\]

Observing that the left-hand side of the equation is even and the right-hand
side of the equation is odd, we can conclude that both sides of the equation
must equal zero because the only function that is both even and odd is the
zero function. Clearly, the right-hand side of the equation being equal to
zero implies that $a_{1,3} = 0$. The left-hand side of the equation being equal
to zero implies that $a_0 = a_2 = a_4 = 0$ from the linear independence of
$p_0, p_2, p_4$ (which follows because $p_0, p_2, p_4$ is a subset of the
monomials). Therefore, $p_0, p_2, p_4, p_{1,3}$ are linearly independent.

To show that $p_0, p_2, p_4, p_{1,3}$ span $U$, consider $p \in U$. Since
$p \in \mathcal{P}_4$, we can express $p$ as a linear combination of the basis
$1, (x - 3.5), (x - 3.5)^2, (x - 3.5)^3, (x - 3.5)^4$:

\[
  p(x) = a_0 + a_1 (x - 3.5) + a_2 (x - 3.5)^2
       + a_3 (x - 3.5)^3 + a_4 (x - 3.5)^4.
\]

Applying the constraint $p(2) = p(5)$

\[
a_0 + a_1 (-1.5) + a_2 (-1.5)^2 + a_3 (-1.5)^3 + a_4 (-1.5)^4
= a_0 + a_1 (1.5) + a_2 (1.5)^2 + a_3 (1.5)^3 + a_4 (1.5)^4,
\]

which implies that

\[
a_3 = -\frac{4}{9} a_1.
\]

Therefore, $p$ is a polynomial of the form

\[
  p(x) = a_0 + a_2 (x - 3.5)^2 + a_4 (x - 3.5)^4
       + a_1 \left( (x - 3.5) - \frac{4}{9} (x - 3.5) \right)^3,
\]

which is a linear combination of $p_0, p_2, p_4, p_{1,3}$.

#### 6.b.

__Problem__. Extend the basis in part (a) to a basis of
$\mathcal{P}_4(\mathbb{F})$.

__Solution__. Add $p_1(x) = (x - 3.5)$ to the basis in part (a). Suppose there
exists a linear combination of $p_0, p_1, p_2, p_4, p_{1,3}$ that is equal to 0:

\[
  0 = a_0 p_0(x) + a_1 p_1(x) + a_2 p_2(x) + a_4 p_4(x) + a_{1,3} p_{1,3}(x).
\]

Differentiating this equation and choosing $x = 3.5$, we find that $a_1 = 0$,
which implies that

\[
  0 = a_0 p_0(x) + a_2 p_2(x) + a_4 p_4(x) + a_{1,3} p_{1,3}(x)
\]

Therefore, $a_0 = a_2 = a_4 = a_{1,3} = 0$ because $p_0, p_2, p_4, p_{1,3}$ are
linearly independent. Thus, we can conclude that $p_0, p_1, p_2, p_4, p_{1,3}$
are linearly independent, which implies that $p_0, p_1, p_2, p_4, p_{1,3}$ is
a basis for $\mathcal{P}_4(\mathbb{F})$ because the number of basis polynomials
is equal to the dimension of $\mathcal{P}_4(\mathbb{F})$.

#### 6.c.

__Problem__. Find a subspace $W$ of $\mathcal{P}_4(\mathbb{F})$ such that
$\mathcal{P}_4(\mathbb{F}) = U \oplus W$.

__Solution__. If $W$ is constructed as the span of any basis of vectors that
extends a basis for $U$ to a basis for $\mathcal{P}_4(\mathbb{F})$, then
$\mathcal{P}_4(\mathbb{F}) = U \oplus W$. Therefore,
$W = \operatorname{span}(p_1)$, the subspace of multiples of $(x - 3.5)$, is a
subspace having the desired property.

-------------------------------------------------------------------------------
### 7.

#### 7.a.

__Problem__. Let
$U = \{ p \in \mathcal{P}_4(\mathbb{F}) | p(2) = p(5) = p(6) \}$. Find a basis
of $U$.

__Solution__. TODO

#### 7.b.

__Problem__. Extend the basis in part (a) to a basis of
$\mathcal{P}_4(\mathbb{F})$.

__Solution__. TODO

#### 7.c.

__Problem__. Find a subspace $W$ of $\mathcal{P}_4(\mathbb{F})$ such that
$\mathcal{P}_4(\mathbb{F}) = U \oplus W$.

__Solution__. TODO

-------------------------------------------------------------------------------
### 8.

#### 8.a.

__Problem__. Let
$U = \{ p \in \mathcal{P}_4(\mathbb{F}) | \int_{-1}^1 p = 0 \}$. Find a basis
of $U$.

__Solution__. TODO

#### 8.b.

__Problem__. Extend the basis in part (a) to a basis of
$\mathcal{P}_4(\mathbb{F})$.

__Solution__. TODO

#### 8.c.

__Problem__. Find a subspace $W$ of $\mathcal{P}_4(\mathbb{F})$ such that
$\mathcal{P}_4(\mathbb{F}) = U \oplus W$.

__Solution__. TODO

-------------------------------------------------------------------------------
### 9.

__Problem__. Suppose $v_1, \ldots, v_m$ is linearly independent in $V$ and
$w \in V$. Prove that

\[
  \dim \operatorname{span} (v_1 + w, \ldots, v_m + w) \ge m - 1.
\]

__Solution__. TODO

-------------------------------------------------------------------------------
### 10.

__Problem__. Suppose $p_0, p_1, \ldots, p_m \in \mathcal{P}(\mathbb{F})$ are
such that each $p_j$ has degree $j$. Prove that $p_0, p_1, \ldots, p_m$ is a
basis of $\mathcal{P}_m(\mathbb{F})$.

__Solution__. TODO

-------------------------------------------------------------------------------
### 11.

__Problem__. Suppose that $U$ and $W$ are subspaces of $\mathbb{R}^8$ such that
$\dim U = 3$, $\dim W = 5$, and $U + W = \mathbb{R}^8$. Prove that
$\mathbb{R}^8 = U \oplus W$.

__Solution__. Since $U + W = \mathbb{R}^8$,

\[
8 = \dim \mathbb{R}^8
= \dim (U + W) = \dim U + \dim W - \dim (U \cap W)
= 3 + 5 - \dim (U \cap W) = 8 - \dim (U \cap W).
\]

which simplifes to $\dim (U \cap W) = 0$. Therefore, $U \cap W = \{ 0 \}$, 
which implies that $U + W$ is a direct sum and yields the desired result.

-------------------------------------------------------------------------------
### 12.

__Problem__. Suppose that $U$ and $W$ are both five-dimensional subspaces of
$\mathbb{R}^9$. Prove that $U \cap W \ne \{ 0 \}$.

__Solution__. Consider $U + W$. Observe that

\[
9 = \dim \mathbb{R}^9
\ge \dim (U + W) = \dim U + \dim W - \dim (U \cap W)
= 5 + 5 - \dim (U \cap W) = 10 - \dim (U \cap W),
\]

which implies that $\dim (U \cap W) \ge 1$. Therefore, $U \cap W$ must contain
at least one nonzero vector, which yields the desired result.

-------------------------------------------------------------------------------
### 13.

__Problem__. Suppose that $U$ and $W$ are both 4-dimensional subspaces of
$\mathbb{C}^6$. Prove that there exist two vectors in $U \cap W$ such that
neither of these vectors is a scalar multiple of the other.

__Solution__. Consider $U + W$. Observe that

\[
6 = \dim \mathbb{R}^6
\ge \dim (U + W) = \dim U + \dim W - \dim (U \cap W)
= 4 + 4 - \dim (U \cap W) = 8 - \dim (U \cap W),
\]

which implies that $\dim (U \cap W) \ge 2$. Therefore, $U \cap W$ must contain
at least two nonzero vectors that are not scalar multiples of each other.

-------------------------------------------------------------------------------
### 14.

__Problem__. Suppose that $U_1, \ldots, U_m$ are finite-dimensional subspaces
of $V$. Prove that $U_1 + \cdots + U_m$ is finite dimensional and

\[
  \dim (U_1 + \cdots + U_m) \le \dim U_1 + \cdots + \dim U_m.
\]

__Solution__. TODO

-------------------------------------------------------------------------------
### 15.

__Problem__. Suppose that $V$ is finite-dimensional, with $\dim V = n \ge 1$.
Prove that there exist 1-dimensional subspaces $U_1, \ldots, U_n$ of $V$ such
that

\[
  V = U_1 \oplus \cdots \oplus U_n.
\]

__Solution__. TODO

-------------------------------------------------------------------------------
### 16.

__Problem__. Suppose that $U_1, \ldots, U_m$ are finite-dimensional subspaces
of $V$ such that $U_1 + \cdots + U_m$ is a direct sum. Prove that
$U_1 \oplus \cdots \oplus U_m$ is finite-dimensional and

\[
  \dim (U_1 \oplus \cdots \oplus U_m) = \dim U_1 + \cdots + \dim U_m.
\]

__Solution__. TODO

-------------------------------------------------------------------------------
### 17.

__Problem__. You might guess, by analogy with the formula for the number of
elements in the union of three subsets of a finite set, that if $U_1, U_2, U_3$
are subspaces of a finite-dimensional vector space, then

\[
  \dim (U_1 + U_2 + U_3)
  = \dim U_1 + \dim U_2 + \dim U_3 \\
    - \dim (U_1 \cap U_2) - \dim (U_1 \cap U_3) - \dim (U_2 \cap U_3) \\
    + \dim (U_1 \cap U_2 \cap U_3).
\]

Prove this or give a counterexample.

__Solution__. TODO

-------------------------------------------------------------------------------
