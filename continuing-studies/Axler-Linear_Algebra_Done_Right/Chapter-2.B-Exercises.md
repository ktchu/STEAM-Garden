Linear Algebra Done Right (S. Axler): Exercises 2.B
===================================================

-------------------------------------------------------------------------------
### 1.

__Problem__. Find all vector spaces that have exactly one basis.

__Solution__. The vector space consisting of only the zero vector is the only
basis that has exactly one basis. The basis for this vector space is the empty
set.

-------------------------------------------------------------------------------
### 2.

__Problem__. Verify the assertions in Example 2.28.

__Solution__. TODO

-------------------------------------------------------------------------------
### 3.

#### 3.a.

__Problem__. Let $U$ be the subspace of $\mathbb{R}^5$ defined by

\[
  U = \{ (x_1, x_2, x_3, x_4, x_5) \in \mathbb{R}^5 |
         x_1 = 3 x_2, x_3 = 7 x_4 \}
\]

Find a basis of $U$.

__Solution__. There are two constraint equations, so the dimension of $U$ is
$5 - 2 = 3$. Treating $x_2$, $x_4$ and $x_5$ as free variables, we can
construct a basis for $U$ by taking $(1, 0, 0)$, $(0, 1, 0)$ and $(0, 0, 1)$
as a basis for $(x_2, x_4, x_5)$. Using this basis for the space
$\{ (x_2, x_4, x_5) \in \mathbb{R}^3 \}$ and the constraint equations for $U$,
we find the following basis for $U$:
$\{ (3, 1, 0, 0, 0), (0, 0, 7, 1, 0), (0, 0, 0, 0, 1) \}$.

#### 3.b.

__Problem__. Extend the basis in part (a) to a basis of $\mathbb{R}^5$.

__Solution__. Observe that adding vectors to the complete bases for the two
subspaces $\{ (x_1, x_2) \in \mathbb{R}^2 \}$ and
$\{ (x_3, x_4) \in \mathbb{R}^2 \}$ will extend the basis from part (a) to a
basis for $\mathbb{R}^5$. One choice is to add the vectors $(1, 0, 0, 0, 0)$
and $(0, 0, 1, 0, 0)$.

#### 3.c.

__Problem__. Find a subspace $W$ of $\mathbb{R}^5$ such that
$\mathbb{R}^5 = U \oplus W$.

__Solution__. Take $W = \{ (1, 0, 0, 0, 0), (0, 0, 1, 0, 0) \}$. Clearly,
any $v \in \mathbb{R}^5$ can be written as a sum of a vector in $U$ and a
vector in $W$, so $\mathbb{R}^5 = U + W$. This sum is a direct sum because
$U \cap W = \{ 0 \}$.

-------------------------------------------------------------------------------
### 4.

#### 4.a.

__Problem__. Let $U$ be the subspace of $\mathbb{C}^5$ defined by

\[
  U = \{ (z_1, z_2, z_3, z_4, z_5) \in \mathbb{C}^5 |
         6 z_1 = z_2, z_3 + 2 z_4 + 3 z_5 = 0 \}
\]

Find a basis of $U$.

__Solution__. There are two constraint equations, so the dimension of $U$ is
$5 - 2 = 3$. Treating $z_1$, $z_4$ and $z_5$ as free variables, we can
construct a basis for $U$ by taking $(1, 0, 0)$, $(0, 1, 0)$ and $(0, 0, 1)$
as a basis for $(z_1, z_4, z_5)$. Using this basis for the space
$\{ (z_1, z_4, z_5) \in \mathbb{C}^3 \}$ and the constraint equations for $U$,
we find the following basis for $U$:
$\{ (1, 6, 0, 0, 0), (0, 0, 2, 1, 0), (0, 0, 3, 0, 1) \}$.


#### 4.b.

__Problem__. Extend the basis in part (a) to a basis of $\mathbb{C}^5$.

__Solution__. Observe that adding vectors to the complete bases for the two
subspaces $\{ (z_1, z_2) \in \mathbb{C}^2 \}$ and
$\{ (z_3, z_4, z_5) \in \mathbb{C}^2 \}$ will extend the basis from part (a)
to a basis for $\mathbb{C}^5$. One choice is to add the vectors
$(1, 0, 0, 0, 0)$ and $(0, 0, 1, 0, 0)$.

#### 4.c.

__Problem__. Find a subspace $W$ of $\mathbb{C}^5$ such that
$\mathbb{C}^5 = U \oplus W$.

__Solution__. Take $W = \{ (1, 0, 0, 0, 0), (0, 0, 1, 0, 0) \}$. Clearly,
any $v \in \mathbb{C}^5$ can be written as a sum of a vector in $U$ and a
vector in $W$, so $\mathbb{C}^5 = U + W$. This sum is a direct sum because
$U \cap W = \{ 0 \}$.

-------------------------------------------------------------------------------
### 5.

__Problem__. Prove or disprove: there exists a basis $p_0, p_1, p_2, p_3$ of
$\mathcal{P}_3(F)$ such that none of the polynomials $p_0, p_1, p_2, p_3$ has
degree 2.

__Solution__. The statement is false. Let $Q$ be the subspace of polynomials
in $\mathcal{P}_3(F)$ that do not have degree 2. $Q$ is spanned by the
polynomials $1, x, x^3$. Therefore, any linearly independent set of polynomials
in $Q$ can have at most length 3. A basis consisting of 4 polynomials
violates this condition.

-------------------------------------------------------------------------------
### 6.

__Problem__. Suppose $v_1, v_2, v_3, v_4$ is a basis of $V$. Prove that

\[
  w_1 = v_1 + v_2, w_2 = v_2 + v_3, w_3 = v_3 + v_4, w_4 = v_4
\]

is also a basis of $V$.

__Solution__.  The $w_i$ are a basis if they (1) spans $V$ and
(2) are linearly independent. To see that the $w_i$ span $V$, let $v \in V$.
Since the $v_i$ are a basis, $v$ is a linear combination of the $v_i$:

\[
  v = a_1 v_1 + a_2 v_2 + a_3 v_3 + a_4 v_4.
\]

Reorganizing the sum, we can express $v$ as a linear combination of the $w_i$:

\[
  v
  = a_1 (v_1 + v_2) + (a_2 - a_1) (v_2 + v_3)
    + (a_3 + a_1 - a_2) (v_3 + v_4)
    + (a_4 - a_1 + a_2 - a_3) v_4 \\
  = a_1 w_1 + (a_2 - a_1) w_2 + (a_3 + a_1 - a_2) w_3
    + (a_4 - a_1 + a_2 - a_3) w_4.
\]

To see that the $w_i$ are linearly independent, suppose

\[
  0 = a_1 w_1 + a_2 w_2 + a_3 w_3 + a_4 w_4.
\]

Expressing the sum in terms of the $v_i$,

\[
0 = a_1 (v_1 + v_2) + a_2 (v_2 + v_3) + a_3 (v_3 + v_4) + a_4 v_4
  = a_1 v_1 + (a_1 + a_2) v_2 + (a_2 + a_3) v_3 + (a_3 + a_4) v_4.
\]

Since the $v_i$ are linearly independent, the coefficients on the $v_i$ must
all be zero, which implies that all of the $a_i$ are zero.

-------------------------------------------------------------------------------
### 7.

__Problem__. Prove or give a counterexample: If $v_1, v_2, v_3, v_4$ is a basis
of $V$ and $U$ is a subspace of $V$ such that $v_1, v_2 \in U$ and
$v_3 \notin U$ and $v_4 \notin U$, then $v_1, v_2$ is a basis of $U$.

__Solution__. The statement is false.

_Counterexample_. Let $v_1, v_2, v_3, v_4$ be the standard basis for
$\mathbb{R}^4$:

\[
  v_1 = (1, 0, 0, 0) \\
  v_2 = (0, 1, 0, 0) \\
  v_3 = (0, 0, 1, 0) \\
  v_4 = (0, 0, 0, 1).
\]

Consider the subspace $U$ defined by the span of $v_1$, $v_2$,
and $w = (0, 0, 1, 1)$. Clearly, $v_1, v_2 \in U$. Consider the equation

\[
  (0, 0, 1, 0)
  = a_1 v_1 + a_2 v_2 + a_3 (0, 0, 1, 1)
  = (a_1, a_2, a_3, a_3).
\]

Because there is no solution for $a_1, a_2, a_3$ that satisfies this equation,
$v_3$ is not a linear combination of $v_1, v_2, w$. Therefore, $v_3 \notin U$.
Similarly, $v_4 \notin U$.

-------------------------------------------------------------------------------
### 8.

__Problem__. Suppose $U$ and $W$ are subspaces of $V$ such that
$V = U \oplus W$. Suppose also that $u_1, \ldots, u_m$ is a basis of $U$ and
$w_1, \ldots, w_n$ is a basis of $W$. Prove that

\[
  u_1, \ldots, u_m, w_1, \ldots, w_n
\]

is a basis of $V$.

__Solution__. To show that $u_1, \ldots, u_m, w_1, \ldots, w_n$ is a basis for
$V$, we need to show that the vectors (1) span $V$ and (2) are linearly
independent.

Let $v \in V$. Then $v = u + w$ where $u \in U$ and $w \in W$.
Expressing $u$ in terms of the basis for $U$ and $w$ in terms of the basis for
$W$, respectively, we find that

\[
  v = a_1 u_1 + \cdots + a_m u_m + b_1 w_1 + \cdots + b_m w_n.
\]

Therefore, $\{ u_1, \ldots, u_m, w_1, \ldots, w_n \}$ spans $V$.

Observe that since $V$ is a direct sum of $U$ and $W$, every vector in $V$ is
a unique sum of $u \in U$ and $w \in W$. Therefore, if
$v = a_1 u_1 + \cdots + a_m u_m + b_1 w_1 + \cdots + b_m w_n$, we must have
$u = a_1 u_1 + \cdots + a_m u_m$ and $w = b_1 w_1 + \cdots + b_m w_n$.

Now suppose that

\[
  0 = a_1 u_1 + \cdots + a_m u_m + b_1 w_1 + \cdots + b_m w_n
    = u + w,
\]

where $u = a_1 u_1 + \cdots + a_m u_m$ and $w = b_1 w_1 + \cdots + b_m w_n$.
Both $u$ and $w$ must equal zero (because $V$ is a direct sum of $U$ and $W$),
so can conclude that all of the $a_i$ and $b_i$ must equal zero (because the
$u_i$ are a basis for $U$ and the $w_i$ are a basis for $W$). Therefore,
$\{ u_1, \ldots, u_m, w_1, \ldots, w_n \}$ are linearly independent.

-------------------------------------------------------------------------------
