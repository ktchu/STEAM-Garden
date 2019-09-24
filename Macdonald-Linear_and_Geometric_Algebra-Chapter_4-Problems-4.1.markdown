Linear and Geometric Algebra (A. Macdonald): Chapter 4
======================================================

## Problems 4.1
-------------------------------------------------------------------------------

### 4.1.1

__Problem__. Modify Eq. (4.3) to provide
$(a \mathbf{u}) \cdot \mathbf{v} = a (\mathbf{u} \cdot \mathbf{v})$ when
$a < 0$.

__Solution__. Recall Eq. (4.3). For $a \ge 0$,
\[
(a \mathbf{u}) \cdot \mathbf{v}
= |a \mathbf{u}| |\mathbf{v}| \cos \theta
= a |\mathbf{u}| |\mathbf{v}| \cos \theta
= a (\mathbf{u} \cdot \mathbf{v})
\]

When $a < 0$, note that the angle between $a \mathbf{u}$ and $\mathbf{v}$
is $\pi - \theta$. Therefore,
\[
(a \mathbf{u}) \cdot \mathbf{v}
= |a \mathbf{u}| |\mathbf{v}| \cos \left( \pi - \theta \right)
= -a |\mathbf{u}| |\mathbf{v}| \cos \left( \pi - \theta \right)
= a |\mathbf{u}| |\mathbf{v}| \cos \theta
= a (\mathbf{u} \cdot \mathbf{v}).
\]

### 4.1.2

__Problem__. Find a vector in the $\mathbf{e_1}$-$\mathbf{e_2}$ plane
orthogonal to $a_1 \mathbf{e_1} + a_2 \mathbf{e_2}$ and of equal norm.

__Solution__. Let $\mathbf{u} = a_1 \mathbf{e_1} + a_2 \mathbf{e_2}$. Then
the vector $\mathbf{v} = a_2 \mathbf{e_1} - a_1 \mathbf{e_2}$ has the desired
properties.
\[
\mathbf{u} \cdot \mathbf{v}
= (a_1 \mathbf{e_1} + a_2 \mathbf{e_2}) \cdot
  (a_2 \mathbf{e_1} - a_1 \mathbf{e_2})
=   a_1 a_2 (\mathbf{e_1} \cdot \mathbf{e_1})
  - a_1 a_1 (\mathbf{e_1} \cdot \mathbf{e_2})
  + a_2 a_2 (\mathbf{e_2} \cdot \mathbf{e_1})
  - a_2 a_1 (\mathbf{e_2} \cdot \mathbf{e_2})
= 0.
\]
and
\[
|\mathbf{v}|^2 = a_2^1 + a_1^2 = a_1^2 + a_2^2 = |\mathbf{u}|^2.
\]

-------------------------------------------------------------------------------
