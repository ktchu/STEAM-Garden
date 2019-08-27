Linear and Geometric Algebra (A. Macdonald): Chapter 4 Exercises
=================================================================

-------------------------------------------------------------------------------

### 4.1.

__Problem__. (Norm) Show that the norm $|\mathbf{v}|$ of an oriented length
can be expressed in terms of the inner product:
$|\mathbf{v}|^2 = \mathbf{v} \cdot \mathbf{v}$.

__Solution__. By definition, $\mathbf{u} \cdot \mathbf{v} =
|\mathbf{u}| |\mathbf{v}| \cos \theta$, where $\theta$ is the angle between the oriented lengths.
Therefore, $\mathbf{v} \cdot \mathbf{v} = |\mathbf{v}|^2$ because $\theta = 0$
in this case and $\cos \theta = 1$.

### 4.2.

__Problem__. Suppose that $\mathbf{u} \cdot \mathbf{v} = 4$. What is
$2 \mathbf{u} \cdot 6 \mathbf{v}$? Explain.

__Solution__. Let $\theta$ be the angle between $\mathbf{u}$ and $\mathbf{v}$.
Then $\theta$ is also the angle between $2 \mathbf{u}$ and $6 \mathbf{v}$ so
that
\[
2 \mathbf{u} \cdot 6 \mathbf{v}
= |2 \mathbf{u}| |6 \mathbf{v}| \cos \theta
= (2 |\mathbf{u}|) (6 |\mathbf{v}|) \cos \theta \\
= 12 |\mathbf{u}| |\mathbf{v}| \cos \theta
= 12 ( \mathbf{u} \cdot \mathbf{v} )
= 12 (4) = 48
\]

### 4.3.

__Problem__. Compute
\[
2 \mathbf{e}_1 \cdot (2 \mathbf{e}_1 + 2 \sqrt{3} \mathbf{e}_2)
\]
from Definition 4.1. Here $\mathbf{e}_1$ and $\mathbf{e}_2$ are perpendicular
vectors of length one.

__Solution__. Using only the geometric definition of inner product (based on
lengths and angles),
\[
2 \mathbf{e}_1 \cdot (2 \mathbf{e}_1 + 2 \sqrt{3} \mathbf{e}_2)
=
|2 \mathbf{e}_1| |2 \mathbf{e}_1 + 2 \sqrt{3} \mathbf{e}_2| \cos \theta,
\]
where $\theta$ is the angle between the vectors $2 \mathbf{e}_1$ and
$2 \mathbf{e}_1 + 2 \sqrt{3} \mathbf{e}_2$. Since $\mathbf{e}_1$ and
$\mathbf{e}_2$ are perpendicular,
\[
|2 \mathbf{e}_1| = 2 \\
|2 \mathbf{e}_1 + 2 \sqrt{3} \mathbf{e}_2| = 4.
\]
Observing that $2 \mathbf{e}_1 + 2 \sqrt{3} \mathbf{e}_2$ and $2 \mathbf{e}_1$
are the hypotenuse and one leg of a 30-60-90 right triangle (with $\theta$ as
the angle between them), we see that $\cos \theta = 1/2$. Therefore,
\[
2 \mathbf{e}_1 \cdot (2 \mathbf{e}_1 + 2 \sqrt{3} \mathbf{e}_2)
= (2) (4) (1/2) = 4.
\]

### 4.4.

__Problem__. Show that if $|\mathbf{u}| = |\mathbf{v}|$, then
$\mathbf{u} + \mathbf{v}$ and $\mathbf{u} - \mathbf{v}$ are orthogonal. Draw
a diagram for this.

__Solution__. Applying the properties of dot product,
\[
(\mathbf{u} + \mathbf{v}) \cdot (\mathbf{u} - \mathbf{v})
=   \mathbf{u} \cdot \mathbf{u} - \mathbf{u} \cdot \mathbf{v}
  + \mathbf{v} \cdot \mathbf{u} - \mathbf{v} \cdot \mathbf{v} \\
=   |\mathbf{u}|^2 - \mathbf{u} \cdot \mathbf{v}
  + \mathbf{v} \cdot \mathbf{u} - |\mathbf{v}|^2 \\
=   |\mathbf{u}|^2 - |\mathbf{v}|^2,
\]
where the last equality follows because the inner product is symmetric.
If $|\mathbf{u}| = |\mathbf{v}|$, then the inner product of
$\mathbf{u} + \mathbf{v}$ and $\mathbf{u} - \mathbf{v}$ is zero which shows
that they are orthogonal.

Geometrically, $\mathbf{u} + \mathbf{v}$ and $\mathbf{u} - \mathbf{v}$ are
the two diagonals of a rhombus. Since rhombuses are kites, their diagonals
intersect at right angles.

### 4.5.

__Problem__. Let
\[
\mathbf{u} = u_1 \mathbf{e}_1 + u_2 \mathbf{e}_2 + u_3 \mathbf{e}_3.
\]
Show that $|\mathbf{u}|^2 = u_1^2 + u_2^2 + u_3^2$.

__Solution__.
\[
|\mathbf{u}|^2
=       (u_1 \mathbf{e}_1 + u_2 \mathbf{e}_2 + u_3 \mathbf{e}_3)
  \cdot (u_1 \mathbf{e}_1 + u_2 \mathbf{e}_2 + u_3 \mathbf{e}_3) \\
=   u_1^2 \mathbf{e}_1 \cdot \mathbf{e}_1
  + u_1 u_2 \mathbf{e}_1 \cdot \mathbf{e}_2
  + u_1 u_3 \mathbf{e}_1 \cdot \mathbf{e}_3 \\
  + u_2 u_1 \mathbf{e}_2 \cdot \mathbf{e}_1
  + u_2^2 \mathbf{e}_2 \cdot \mathbf{e}_2
  + u_3 u_2 \mathbf{e}_3 \cdot \mathbf{e}_2 \\
  + u_3 u_1 \mathbf{e}_3 \cdot \mathbf{e}_1
  + u_3 u_2 \mathbf{e}_3 \cdot \mathbf{e}_2
  + u_3^2 \mathbf{e}_3 \cdot \mathbf{e}_3 \\
= u_1^2 + u_2^2 + u_3^2,
\]
where the last equality follows because $\mathbf{e}_1$, $\mathbf{e}_2$, and
$\mathbf{e}_3$ are an orthonormal set.

### 4.6.

__Problem__. TODO

__Solution__. TODO

-------------------------------------------------------------------------------
