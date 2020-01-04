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

___I1___. We wish to show that

\[
(a \mathbf{u}) \cdot \mathbf{w} = a ( \mathbf{u} \cdot \mathbf{w} )
\]

Note that all of the vectors in the above relation lie in a plane. Consider
the triangles formed with $\mathbf{u}$ and $a \mathbf{u}$ as bases. Dropping
an altitude from the top vertex of the triangle, we obtain three right
triangles with the same altitude. Letting $h$ be the length of the altitude
and $\Delta$ be the distance between the point where $\mathbf{u}$ and
$\mathbf{w}$ meet, we find that (after applying the Pythagorean theorem
three times):
\[
|a \mathbf{u} + \mathbf{w}|^2 = h^2
                            + \left( a |\mathbf{u}| \pm \Delta \right)^2 \\
|\mathbf{u} + \mathbf{w}|^2 = h^2
                            + \left( |\mathbf{u}| \pm \Delta \right)^2 \\
|\mathbf{w}|^2 = h^2 + \Delta^2
\]

where the sign on $\Delta$ depends on whether the angle betweeen $\mathbf{u}$
and $\mathbf{w}$ is acute or obtuse. After some algebra, we obtain

\[
|a \mathbf{u} + \mathbf{w}|^2 - |a \mathbf{u}|^2 - |\mathbf{w}|^2 =
  \pm 2 a |\mathbf{u}| \Delta.
|\mathbf{u} + \mathbf{w}|^2 - |\mathbf{u}|^2 - |\mathbf{w}|^2 =
  \pm 2|\mathbf{u}| \Delta \\
\]

Using the polarization identity to express the left-hand side of these
equations, we obtain the desired result:
\[
(a \mathbf{u}) \cdot \mathbf{w} = a ( \mathbf{u} \cdot \mathbf{w} ).
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

### 4.16.

__Problem__. Prove that
\[
|\mathbf{u} + \mathbf{v}|^2 + |\mathbf{u} - \mathbf{v}|^2
= 2 |\mathbf{u}|^2 + 2 |\mathbf{v}|^2.
\]
This is called the _parallelogram identity_. Illustrate with a sketch for
oriented lengths.

__Solution__.
\[
|\mathbf{u} + \mathbf{v}|^2 + |\mathbf{u} - \mathbf{v}|^2
= (\mathbf{u} + \mathbf{v}) \cdot (\mathbf{u} + \mathbf{v})
+ (\mathbf{u} - \mathbf{v}) \cdot (\mathbf{u} - \mathbf{v}) \\
= |\mathbf{u}|^2 + |\mathbf{v}|^2 + 2 \mathbf{u} \cdot \mathbf{v}
+ |\mathbf{u}|^2 + |\mathbf{v}|^2 - 2 \mathbf{u} \cdot \mathbf{v}
= 2 |\mathbf{u}|^2 + 2 |\mathbf{v}|^2
\]

### 4.17.

__Problem__. Let $\mathbf{u} = (u_1, \ldots, u_n)$ and
$\mathbf{v} = (v_1, \ldots, v_n)$ be vectors in $\mathbb{R}^n$. Express
the Cauchy-Schwarz inequality in terms of the $u$'s and $v$'s.

__Solution__. Expressing the terms in the Cauchy-Schwarz inequality in terms
of components,
\[
|\mathbf{u} \cdot \mathbf{v}| \le |\mathbf{u}| |\mathbf{v}|
\]
becomes
\[
\left| \sum_i u_i v_i \right| \le
\sqrt{
  \left( \sum_i u_i^2 \right) \left( \sum_i v_i^2 \right)
}
\]

### 4.18.

__Problem__. Repeat Exercise 4.17 for the inner product of Exercise 4.12.

__Solution__. Expressing the terms in the Cauchy-Schwarz inequality in terms
of components,
\[
|\mathbf{u} \odot \mathbf{v}| \le |\mathbf{u}| |\mathbf{v}|
\]
becomes
\[
\left| \sum_i a_i u_i v_i \right| \le
\sqrt{
  \left( \sum_i a_i u_i^2 \right) \left( \sum_i a_i v_i^2 \right)
}
\]

### 4.19.

__Problem__. Prove N1 of Theorem 4.14: if $\mathbf{v} \ne \mathbf{0}$, then
$|\mathbf{v}| > 0$.

__Solution__. $|\mathbf{v}|$ is equal to the positive square root of
$\mathbf{v} \cdot \mathbf{v}$, which is postiive when
$\mathbf{v} \ne \mathbf{0}$.

### 4.20.

__Problem__. Show that $|\mathbf{0}| = 0$ using only Theorem 4.14.

__Solution__.
\[
|\mathbf{0}| = |0 \mathbf{0}| = |0| |\mathbf{0}| = 0 |\mathbf{0}| = 0,
\]
where the second equality follows from N2 of Theorem 4.14 by letting
$a = 0$ and $\mathbf{v} = \mathbf{0}$.

### 4.21.

__Problem__. Show that if $|\mathbf{v}| \ne \mathbf{0}$, then
$\frac{1}{|\mathbf{v}|} \mathbf{v}$ is _normalized_, i.e., has norm 1.

__Solution__.
\[
\left| \frac{1}{|\mathbf{v}|} \mathbf{v} \right|^2
= \left( \frac{1}{|\mathbf{v}|} \mathbf{v} \right) \cdot
  \left( \frac{1}{|\mathbf{v}|} \mathbf{v} \right)
= \frac{1}{|\mathbf{v}|^2} ( \mathbf{v} \cdot \mathbf{v} )
= \frac{1}{|\mathbf{v}|^2} |\mathbf{v}|^2 = 1
\]

### 4.22.

__Problem__. Prove Axiom I2 for the inner product space $C[a,b]$.

__Solution__.
\[
(f + g) \cdot h
= \int_a^b \left( f(x) + g(x) \right) h(x) dx
= \int_a^b \left( f(x) h(x) + g(x) h(x) \right) dx \\
= \int_a^b f(x) h(x) dx + \int_a^b g(x) h(x) dx
= f \cdot h + g \cdot h
\]

### 4.23.

__Problem__. What is the norm of the function $f(x) = x$ in $C[0,1]$ with
the inner product $f \cdot g = \int_a^b f(x) g(x) dx$?

__Solution__.
\[
|f|^2 = \int_0^1 f(x)^2 dx = \int_0^1 x^2 dx = 1/3,
\]

so $|f| = 1 / \sqrt{3}$.

-------------------------------------------------------------------------------
