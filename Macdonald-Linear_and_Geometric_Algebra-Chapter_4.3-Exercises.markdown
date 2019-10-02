Linear and Geometric Algebra (A. Macdonald): Chapter 4
======================================================

## Exercises: Section 4.3

-------------------------------------------------------------------------------

### 4.11.

__Problem__. Prove the companion to I2:
\[
\mathbf{w} \cdot (\mathbf{u} + \mathbf{v})
= \mathbf{w} \cdot \mathbf{u} + \mathbf{w} \cdot \mathbf{v}.
\]

__Solution__. Note that we only know that $\mathbf{u}$, $\mathbf{v}$, and
$\mathbf{w}$ are vectors in the an inner product space, so we may only use the
axioms I1-I4 to prove the result.
\[
\mathbf{w} \cdot (\mathbf{u} + \mathbf{v})
= (\mathbf{u} + \mathbf{v}) \cdot \mathbf{w}
= \mathbf{u} \cdot \mathbf{w} + \mathbf{v} \cdot \mathbf{w}
= \mathbf{w} \cdot \mathbf{u} + \mathbf{w} \cdot \mathbf{u},
\]
where we have used I2 for the first and last equalities and I3 for the middle
equality.

### 4.12.

__Problem__. The inner product Eq. (4.8) on $\mathbb{R}^n$ is sometimes called
the _standard inner product_ to distinguish it from other useful inner products
on the vector space $\mathbb{R}^n$. For example, for fixed scalars $a_i > 0$,
define
\[
  \mathbf{u} \odot \mathbf{v} = a_1 u_1 v_1 + \cdots + a_n u_n v_n.
\]
The product $\odot$ satisfies I1-I4 and so is an inner product on $\mathbb{R}^n$.
Prove I4: If $\mathbf{v} \ne \mathbf{0}$, then
$\mathbf{v} \cdot \mathbf{v} > 0$.

__Solution__. By the definition of $\odot$,
\[
\mathbf{v} \cdot \mathbf{v}
= \sum_i a_i v_i^2.
\]
Since $a_i > 0$ for all $i$, each term is strictly nonnegative which implies
that the $\mathbf{v} \odot \mathbf{v} \ge 0$ for all $\mathbf{v}$. If
$\mathbf{v} \ne \mathbf{0}$, then at least one component of $v_i$ is strictly
positive, so the sum, and therefore $\mathbf{v} \odot \mathbf{v}$, is also
strictly positive.

### 4.13.

__Problem__.

__Solution__.

-------------------------------------------------------------------------------
