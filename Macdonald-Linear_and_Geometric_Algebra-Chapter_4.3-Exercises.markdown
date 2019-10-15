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

__Problem__. Two vectors can be orthogonal with respect to one inner product
on a vector space and not orthogonal with respect to another. Find an example
in $\mathbb{R}^2$ using the standard inner product and an inner product from
Exercise 4.12: $\mathbf{u} \odot \mathbf{v} = u_1 v_1 + 2 u_2 v_2$.

__Solution__. Let $\mathbf{u} = [1, 1]$ and $\mathbf{v} = [1, -1]$. Then
$\mathbf{u} \cdot \mathbf{v} = 1 - 1 = 0$, so the two vectors are orthogonal
with respect to the standard inner product. However,
$\mathbf{u} \odot \mathbf{v} = 1 - 2 = -1$, so the two vectors are not
orthogonal with respect to the $\odot$ inner product.

### 4.14.

__Problem__. (Polarization identity). The norm is defined in terms of the inner
product: $|\mathbf{v}|^2 = \mathbf{v} \cdot \mathbf{v}$. Show that the inner
product can be expressed in terms of the norm by the _polarization identity_:
\[
\mathbf{u} \cdot \mathbf{v}
= \frac{1}{2} \left(  |\mathbf{u} + \mathbf{v}|^2
                    - |\mathbf{u}|^2 - |\mathbf{v}|^2
              \right)
\]

__Solution__.
We need to show that the polarization identity satisfies the properties of an
inner product.

___I1___. TODO
\[
(a \mathbf{u}) \cdot \mathbf{w}
= \frac{1}{2}
  \left( |(a \mathbf{u}) + \mathbf{w}|^2 - |a \mathbf{u}|^2 - |\mathbf{w}|^2
  \right)
\]

___I2___. TODO
\[
(\mathbf{u} + \mathbf{v}) \cdot \mathbf{w}
= \frac{1}{2}
  \left( |(\mathbf{u} + \mathbf{v}) + \mathbf{w}|^2
       - |\mathbf{u} + \mathbf{v}|^2 - |\mathbf{w}|^2
  \right) \\
= \frac{1}{2}
  \left( |(\mathbf{u} + \mathbf{v}) + \mathbf{w}|^2
       - |\mathbf{u} + \mathbf{v}|^2
       + |\mathbf{v} + \mathbf{w}|^2 - |\mathbf{v} + \mathbf{w}|^2
       + |\mathbf{v}|^2 - |\mathbf{v}|^2
       - |\mathbf{w}|^2
  \right)
\]


___I3___. The definition of the inner product provided by the polarization identity
is symmetric in $\mathbf{u}$ and $\mathbf{v}$, so it trivially satisfies
$\mathbf{u} \cdot \mathbf{v} = \mathbf{v} \cdot \mathbf{u}$

___I4___. If $\mathbf{v} \ne \mathbf{0}$, then $|\mathbf{v}|^2 > 0$.
Therefore,
\[
\mathbf{v} \cdot \mathbf{v}
= \frac{1}{2} \left(  |\mathbf{v} + \mathbf{v}|^2
                    - |\mathbf{v}|^2 - |\mathbf{v}|^2
              \right)
= \frac{1}{2} \left(|2 \mathbf{v}|^2 - 2 |\mathbf{v}|^2 \right)
= \frac{1}{2} \left(4 |\mathbf{v}|^2 - 2 |\mathbf{v}|^2 \right)
= |\mathbf{v}|^2 > 0.
\]

### 4.15.

__Problem__. Prove the Pythagorean theorem: if $\mathbf{u}$ and $\mathbf{v}$
are orthogonal vectors, then
$|\mathbf{u} + \mathbf{v}|^2 = |\mathbf{u}|^2 + |\mathbf{v}|^2$.

__Solution__. If $\mathbf{u}$ and $\mathbf{v}$, then
$\mathbf{u} \cdot \mathbf{v} = 0$. Therefore,
\[
|\mathbf{u} + \mathbf{v}|^2
= (\mathbf{u} + \mathbf{v}) \cdot (\mathbf{u} + \mathbf{v})
= \mathbf{u} \cdot \mathbf{u} + \mathbf{v} \cdot \mathbf{v}
  + 2 \mathbf{u} \cdot \mathbf{v}
= |\mathbf{u}|^2 + |\mathbf{v}|^2
\]

-------------------------------------------------------------------------------
