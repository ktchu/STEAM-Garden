Linear Algebra Done Right (S. Axler): Exercises 1.C
===================================================

-------------------------------------------------------------------------------
### 1.

For each of the following subsets of $\mathbb{F}^3$, determine whether it is a
subspace of $\mathbb{F}^3$.

#### 1.a.

__Problem__. $\{ (x_1, x_2, x_3) \in \mathbb{F}^3 : x_1 + 2 x_2 + 3 x_3 = 0 \}$

__Solution__. Yes.

* $0 + 2(0) + 3(0) = 0$, so $0$ is in the set.

* Let $x$ and $y$ be in the set. $x + y$ satisfies

  \[
    (x_1 + y_1) + 2 (x_2 + y_2) + 3 (x_3 + y_3)
    = (x_1 + 2 x_2 + 3 x_3) + (y_1 + 2 y_2 + 3 y_3)
    = 0 + 0 = 0,
  \]

  so the set is closed under addition.

* Let $x$ be in the set and $\lambda \in \mathbb{F}$. $\lambda x$ satisfies

  \[
    \lambda x_1 + 2 (\lambda x_2) + 3 (\lambda x_3)
    = \lambda (x_1 + 2 x_2 + 3 x_3) = \lambda 0 = 0,
  \]

  so the set is closed under scalar multiplication.

#### 1.b.

__Problem__. $\{ (x_1, x_2, x_3) \in \mathbb{F}^3 : x_1 + 2 x_2 + 3 x_3 = 4 \}$

__Solution__. No.

* $0 + 2(0) + 3(0) = 0 \ne 4$, so $0$ is not in the set.

* Let $x$ and $y$ be in the set. $x + y$ satisfies

  \[
    (x_1 + y_1) + 2 (x_2 + y_2) + 3 (x_3 + y_3)
    = (x_1 + 2 x_2 + 3 x_3) + (y_1 + 2 y_2 + 3 y_3)
    = 4 + 4 = 8 \ne 4
  \]

  so the set is not closed under addition.

* Let $x$ be in the set and $\lambda \in \mathbb{F}$. $\lambda x$ satisfies

  \[
    \lambda x_1 + 2 (\lambda x_2) + 3 (\lambda x_3)
    = \lambda (x_1 + 2 x_2 + 3 x_3) = 4 \lambda,
  \]

  which does not equal 4 except for $\lambda = 1$, so the set is not closed
  under scalar multiplication.

#### 1.c.

__Problem__. $\{ (x_1, x_2, x_3) \in \mathbb{F}^3 : x_1 x_2 x_3 = 0 \}$

__Solution__. No. The set does not satisfy closure under addition.
Let $x = (1, 1, 0)$ and $y = (0, 0, 1)$, then $x$ and $y$ are in the set.
However, $x + y = (1, 1, 1)$ does not satisfy the condition that the product
of the components is zero.

#### 1.d.

__Problem__. $\{(x_1, x_2, x_3) \in \mathbb{F}^3 : x_1 = 5 x_3 \}$

__Solution__. Yes.

* $0 = 5(0)$, so $0$ is in the set.

* Let $x$ and $y$ be in the set. $x + y$ satisfies

  \[
    x_1 + y_1 = 5 x_3 + 5 y_3 = 5 (x_3 + y_3),
  \]

  so the set is closed under addition.

* Let $x$ be in the set and $\lambda \in \mathbb{F}$. $\lambda x$ satisfies

  \[
    \lambda x_1 = \lambda (5 x_3) = 5 (\lambda x_3),
  \]

  so the set is closed under scalar multiplication.

-------------------------------------------------------------------------------
### 2.

__Problem__. Verify all of the assertions in Example 1.35.

__Solution__. TODO

-------------------------------------------------------------------------------
### 3.

__Problem__. Show that the set of differentiable real-valued functions $f$ on
the interval $(-4, 4)$ such that $f'(-1) = 3f(2)$ is a subspace of
$\mathbb{R}^{(-4, 4)}$.

__Solution__. It is straightforward to verify that the conditions for a
subspace are satisfied.

* The zero function $f(x) = 0$ on $(-4, 4)$ satisfies the $f'(-1) = 3 f(2)$.

* Let $f$ and $g$ be in the set, then

  \[
    (f + g)'(-1) = f'(-1) + g'(-1) = 3f(2) + 3g(2) = (3f + 3g)(2) = 3(f+g)(2),
  \]

  so additive closure is satisfied.

* Let $f$ in the set and $\lambda \in \mathbb{R}$, then

  \[
    (\lambda f)'(-1) = \lambda f'(-1) = \lambda(3f(2)) = 3(\lambda f(2))
  \]

  so the set is closed under scalar multiplication.

-------------------------------------------------------------------------------
### 4.

__Problem__. Suppose that $b \in \mathbb{R}$. Show that the set of continuous
real-valued functions $f$ on the interval $[0, 1]$ such that $\int_0^1 f = b$
is a subspace of $\mathbb{F}^{[0,1]}$ if and only if $b = 0$.

__Solution__. TODO

-------------------------------------------------------------------------------
### 5.

__Problem__. Is $\mathbb{R}^2$ a subspace of the complex vector space
$\mathbb{C}^2$?

__Solution__. Yes. First, $\mathbb{R}^2 \subset \mathbb{C}^2$ because
$\mathbb{R} \subset \mathbb{C}$. Second, the conditions for a subspace are
automatically satisfied for $\mathbb{R}^2$ because $\mathbb{R}^2$ satisifes
all of the conditions for a vector space, which are a superset of the
conditions for a subspace.

-------------------------------------------------------------------------------
### 6.

#### 6.a.

__Problem__. Is $\{ (a, b, c) \in \mathbb{R}^3 : a^3 = b^3 \}$ a subspace of
$\mathbb{R}^3$?

__Solution__. Yes. Verification of the conditions for a subspace relies on the
fact that the function $f: \mathbb{R} \rightarrow \mathbb{R}$ defined by
$f(x) = x^3$ is 1-1.

* 0 is in the set because $a = 0 = b$ satisfies $a^3 = 0 = b^3$.

* If $x = (x_1, x_2, x_3)$ and $y = (y_1, y_2, y_3)$ are in the set then
  $x_1^3 = x_2^3$ and $y_1^3 = y_2^3$, which implies that $x_1 = x_2$ and
  $y_1 = y_2$. Therefore, $(x_1 + y_1)^3 = (x_2 + y_2)^3$, so the set is
  closed under addition.

* Let $x = (x_1, x_2, x_3)$ and $\lambda \in \mathbb{R}$. $x_1^3 = x_2^3$
  implies that $x_1 = x_2$. Therefore, $(\lambda x_1)^3 = (\lambda x_2)^3$,
  so the set is closed under scalar multiplication.

#### 6.b.

__Problem__. Is $\{ (a, b, c) \in \mathbb{C}^3 : a^3 = b^3 \}$ a subspace of
$\mathbb{C}^3$?

__Solution__. No. Additive closure is not satisified for this set. Consider
$x = (x_1, x_2, x_3) = (1, e^{2 \pi i / 3}, 0)$ and
$y = (y_1, y_2, y_3) = (1, 1, 0)$. Then
$x_1 = 1^3 = 1 = e^{2 \pi} = (e^{2 \pi i / 3})^3 = x_2^3$ and
$y_1 = 1^3 = y_2^3$. However, $(x_1 + y_1)^3 = 2^3 = 8$ while

\[
  (x_2 + y_2)^3
  = (1 + e^{2 \pi i / 3})^3
  = 1 + 3 e^{2 \pi i / 3} + 3 e^{4 \pi i / 3}) + e^{2 \pi} \\
  = 2 + 3 (\cos(2 \pi / 3) + i \sin(2 \pi / 3))
      + 3 (\cos(4 \pi / 3) + i \sin(4 \pi / 3)) \\
  = 2 + 6 (\cos(2 \pi / 3)
  = 2 + 6 (-1/2) = 2 - 3 = -1.
\]

-------------------------------------------------------------------------------
### 7.

__Problem__. Give an example of a nonempty subset $U$ of $\mathbb{R}^2$ such
that $U$ is closed under addition and under taking additive inverses
(meaning $-u \in U$ whenever $u \in U$), but $U$ is not a subspace of
$\mathbb{R}^2$.

__Solution__. TODO

-------------------------------------------------------------------------------
### 8.

__Problem__. Give an example of a nonempty subset $U$ of $\mathbb{R}^2$ such
that $U$ is closed under scalar multiplication, but $U$ is not a subspace of
$\mathbb{R}^2$.

__Solution__. TODO

-------------------------------------------------------------------------------
### 9.

__Problem__. A function $f : \mathbb{R} \rightarrow \mathbb{R}$ is called
___periodic___ if there exists a positive number $p$ such that
$f(x) = f(x + p)$ for all $x \in \mathbb{R}$. Is the set of periodict functions
from $\mathbb{R}$ to $\mathbb{R}$ a subspace of $\mathbb{R}^\mathbb{R}$?
Explain.

__Solution__. TODO

-------------------------------------------------------------------------------
### 10.

__Problem__. Suppose $U_1$ and $U_2$ are subspaces of $V$. Prove that the
intersection $U_1 \cap U_2$ is a subspace of $V$.

__Solution__. Verify the conditions for a subspace.

* $U_1$ and $U_2$ are subspaces of $V$, so $0 \in U_1$ and $0 \in U_2$.
  Therefore, $0 \in U_1 \cap U_2$.

* Let $x, y \in U_1 \cap U_2$. Since $U_1$ and $U_2$ are subspaces,
  $x + y \in U_1$ and $x + y \in U_2$. Therefore, $x + y \in U_1 \cap U_2$,
  so $U_1 \cap U_2$ is closed under addition.

* Let $x \in U_1 \cap U_2$ and $\lambda \in \mathbb{F}$. Since $U_1$ and $U_2$
  are subspaces, $\lambda x \in U_1$ and $\lambda x \in U_2$. Therefore,
  $\lambda x \in U_1 \cap U_2$, so $U_1 \cap U_2$ is closed under scalar
  multiplication.

-------------------------------------------------------------------------------
### 11.

__Problem__. Prove that the intersection of every collection of subspaces of
$V$ is a subpsace of $V$.

__Solution__. TODO

-------------------------------------------------------------------------------
### 12.

__Problem__. Prove that the union of two subspaces of $V$ is a subspace of $V$
if and only if one of the subspaces is contained in the other.

__Solution__. TODO

-------------------------------------------------------------------------------
### 13.

__Problem__. Prove that the union of three subspaces of $V$ is a subspace of
$V$ if and only if one of the subpsaces contains the other two. [_This exercise
is surprisingly harder than the previous exercises, possibly because this
exercise is not true if we replace $\mathbb{F}$ with a field containing only
two elements_].

__Solution__. TODO

-------------------------------------------------------------------------------
### 14.

__Problem__. Verify the assertion in Example 1.38.

__Solution__. TODO

-------------------------------------------------------------------------------
### 15.

__Problem__. Suppose $U$ is a subspace of $V$. What is $U + U$?

__Solution__. $U + U = U$.

_Proof_. $U \subseteq U + U$ because $x \in U$ and $0 \in U$ implies that
$x = x + 0 \in U + U$. If $z \in U + U$, $z = x + y$ where $x, y \in U$.
Therefore, $z \in U$ because $U$ is a subspace of $V$.

-------------------------------------------------------------------------------
### 16.

__Problem__. Is the operation of addition on the subspaces of $V$ commutative?
In other words, if $U$ and $W$ are subspaces of $V$, is $U + W = W + U$?

__Solution__. Yes. Addition of subspaces is commutative because addition of
vectors is commutative.

-------------------------------------------------------------------------------
### 17.

__Problem__. Is the operation of addition on the subspaces of $V$ associative?
In other words, if $U_1$, $U_2$, and $U_3$ are subspaces of $V$, is
$(U_1 + U_2) + U_3 = U_1 + (U_2 + U_3)$?

__Solution__. Yes. Addition of subspaces is associative because addition of
vectors is associative.

-------------------------------------------------------------------------------
### 18.

__Problem__. Does the operation of addition on the subspaces of $V$ have an
additive identity? Which subspaces have additive inverses?

__Solution__. The subspace $\{0\}$ is the identity of the subspace addition
operation. The only subspace with an inverse under subspace addition is
$\{0\}$ because subspace addition always yields a vector space that is at
least as large as the larger subspace. Therefore, the sum of any subspace
larger than $\{0\}$ with any other subspace will always be larger than $\{0\}$.

-------------------------------------------------------------------------------
### 19.

__Problem__. Prove or give a counterexample: if $U_1$, $U_2$, $W$ are subspaces
of $V$ such that

\[
  U_1 + W = U_2 + W,
\]

then $U_1 = U_2$.

__Solution__. TODO

-------------------------------------------------------------------------------
### 20.

__Problem__. Suppose

\[
  U = \{ (x, x, y, y) \in \mathbb{F}^4 : x, y \in \mathbb{F} \}.
\]

Find a subspace $W$ of $\mathbb{F}^4$ such that $\mathbb{F}^4 = U \oplus W$.

__Solution__. TODO

-------------------------------------------------------------------------------
### 21.

__Problem__. Suppose

\[
  U = \{ (x, y, x + y, x - y, 2x) \in \mathbb{F}^5 : x, y \in \mathbb{F} \}.
\]

Find a subspace $W$ of $\mathbb{F}^5$ such that $\mathbb{F}^5 = U \oplus W$.

__Solution__. TODO

-------------------------------------------------------------------------------
### 22.

__Problem__. Suppose

\[
  U = \{ (x, y, x + y, x - y, 2x) \in \mathbb{F}^5 : x, y \in \mathbb{F} \}.
\]

Find three subspaces $W_1$, $W_2$, $W_3$ of $\mathbb{F}^5$, none of which
equals $\{ 0 \}$, such that $\mathbb{F}^5 = U \oplus W_1 \oplus W_2 \oplus W_3$.

__Solution__. TODO

-------------------------------------------------------------------------------
### 23.

__Problem__. Prove or give a counterexample: if $U_1$, $U_2$, $W$ are subspaces
of $V$ such that

\[
  V = U_1 \oplus W \textrm{ and } V = U_2 \oplus W,
\]

then $U_1 = U_2$.

__Solution__. TODO

-------------------------------------------------------------------------------
### 24.

__Problem__. A function $f : \mathbb{R} \rightarrow \mathbb{R}$ is called
_even_ if

\[
  f(-x) = f(x)
\]

for all $x \in \mathbb{R}$. A function $f : \mathbb{R} \rightarrow \mathbb{R}$
is called _odd_ if

\[
  f(-x) = -f(x)
\]

for all $x \in \mathbb{R}$. Let $U_e$ denote the set of real-valued even
functions on $\mathbb{R}$ and let $U_o$ denote thes et of real-valued odd
functions on $\mathbb{R}$. Show that $\mathbb{R}^\mathbb{R} = U_e \oplus U_o$.

__Solution__. TODO

-------------------------------------------------------------------------------
