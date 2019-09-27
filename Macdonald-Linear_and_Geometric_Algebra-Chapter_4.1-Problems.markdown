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

### 4.1.3

#### 4.1.3.a

__Problem__. Find the equation, in the form $ax + by+cz = 0$, of the plane
through the origin and orthogonal to the vector
$\mathbf{n} = \mathbf{e_1} + 2 \mathbf{e_2} + 3 \mathbf{e_3}$.

__Solution__. Let
$\mathbf{v} = x \mathbf{e_1} + y \mathbf{e_2} + z \mathbf{e_3}$ be an arbitrary
vector that lies in desired plane. Expanding the orthogonality equation
$\mathbf{v} \cdot \mathbf{n} = 0$ in terms of components, we find the equation
of the plane is given by
\[
 0 = \mathbf{v} \cdot \mathbf{n} = x + 2 y + 3 z.
\]

#### 4.1.3.b

__Problem__. Find the equation, in the form $ax + by+cz = d$, of the plane
through the point $\mathbf{v}_0 \mathbf{e_1} - \mathbf{e_2} + \mathbf{e_3}$ and
orthogonal to the vector
$\mathbf{n} = \mathbf{e_1} + 2 \mathbf{e_2} + 3 \mathbf{e_3}$.

__Solution__. Let
$\mathbf{v} = x \mathbf{e_1} + y \mathbf{e_2} + z \mathbf{e_3}$ be an arbitrary
vector that lies in the desired plane. Expanding the orthogonality equation
$(\mathbf{v} - \mathbf{v}_0) \cdot \mathbf{n} = 0$ in terms of
components, we find that
\[
 0 = (\mathbf{v} - \mathbf{v}_0) \cdot \mathbf{n} =
 (x - 1) + 2 (y + 1) + 3 (z - 1),
\]
which can be rearranged to obtain the equation of the plane:
\[
 x + 2 y + 3 z = 1 - 2 + 3 = 2.
\]

-------------------------------------------------------------------------------
