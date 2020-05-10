Linear and Geometric Algebra (A. Macdonald): Chapter 5
======================================================

## Problems 5.1

-------------------------------------------------------------------------------

### 5.1.1.

__Problem__. Show that oriented area addition is well defined, i.e., if
$a \mathbf{w}$ ($a \ne 0$) is used instead of $\mathbf{w}$ to form
$\mathbf{B}_1 + \mathbf{B}_2$ in Figure 5.4, then the sum is the same.

__Solution__. TODO

### 5.1.2.

#### 5.1.2.a.

__Problem__. Find the area of the parallelogram with vertices at (0,0),
(2,1), (1,3), and (3,4).

__Solution__. Let $\mathbf{u} = 2 \mathbf{e}_1 + \mathbf{e}_2$ and
$\mathbf{v} = \mathbf{e}_1 + 3 \mathbf{e}_2$. Then, the parallelogram
can be represented by the oriented area

\[
\mathbf{u} \wedge \mathbf{v}
= (2 \mathbf{e}_1 + \mathbf{e}_2) \wedge (\mathbf{e}_1 + 3 \mathbf{e}_2)
= 5 \mathbf{e}_1 \wedge \mathbf{e}_2.
\]

The area of the parellelogram is equal to 5 because
$|5 \mathbf{e}_1 \wedge \mathbf{e}_2| = 5 |\mathbf{e}_1 \wedge \mathbf{e}_2|$
and $|\mathbf{e}_1 \wedge \mathbf{e}_2| = 1$.

#### 5.1.2.b.

__Problem__. Find the area of the triangle with vertices at (0,0),
(2,1), and (1,3).

__Solution__. The triangle with vertices at (0,0), (2,1), and (1,3) is half
the parallelogram from part (a), so the area is equal to half the area
of $5|\mathbf{e}_1 \wedge \mathbf{e}_2$. Therefore, the area of the triangle
is equal to 5/2.

### 5.1.3.

__Problem__. Find the area of the parallelogram with vertices at (1,1), (3,2),
(2,4), and (4,5).

__Solution__. The parallelogram with vertices at (1,1), (3,2), (2,4), and
(4,5) is the same as the parallelogram from Problem 5.1.2.a shifted by
$\mathbf{e}_1 + \mathbf{e}_2$, so the parallelogram is represented by the same
oriented area and the area of the parallelogram is 5.

### 5.1.4.

See Theorem 5.2.

#### 5.1.4.a.

__Problem__. Prove the companion to O3:

\[
a(\mathbf{u} \wedge \mathbf{v}) = \mathbf{u} \wedge (a \mathbf{v}).
\]

__Solution__. TODO

#### 5.1.4.b.

__Problem__. Prove the companion to O4:
\[
  \mathbf{w} \wedge (\mathbf{u} + \mathbf{v})
= \mathbf{w} \wedge \mathbf{u} + \mathbf{w} \wedge \mathbf{v}.
\]

__Solution__. Using O2 and O4,

\[
\mathbf{w} \wedge (\mathbf{u} + \mathbf{v})
= -(\mathbf{u} + \mathbf{v}) \wedge \mathbf{w}
= (-\mathbf{u} - \mathbf{v}) \wedge \mathbf{w}
= -\mathbf{u} \wedge \mathbf{w} - \mathbf{v} \wedge \mathbf{w}
= \mathbf{w} \wedge \mathbf{u} + \mathbf{w} \wedge \mathbf{v}
\]

### 5.1.5.

Let $\mathbf{a}$ and $\mathbf{b} \ne \mathbf{0}$ be given vectors.

#### 5.1.5.a.

__Problem__. Show that

\[
(\mathbf{x} - \mathbf{a}) \wedge \mathbf{b} = \mathbf{0}
\]

is a vector equation of the line $\mathscr{l}$ through $\mathbf{a}$ and
parallel to $\mathbf{b}$.

__Solution__. Observe that $\mathbf{u} \wedge \mathbf{b} = 0$ if and only if
the sine of the angle between $\mathbf{u}$ and $\mathbf{b}$ is 0. Therefore,
the angle between $\mathbf{u}$ and $\mathbf{b}$ is 0 or $\pi$, so $\mathbf{u}$
and $\mathbf{b}$ are parallel because the angle between them must be be an
integer multiple of $\pi$. Applying this observation to the equation

\[
(\mathbf{x} - \mathbf{a}) \wedge \mathbf{b} = \mathbf{0},
\]

we can conclude that the set of points $\mathscr{l}$ satisfying this equation
consists of those points where $(\mathbf{x} - \mathbf{a})$ is parallel
to $\mathbf{b}$ -- that is, $\mathscr{l}$ is set of points that can be reached
by adding an arbitrary vector parallel to $\mathbf{b}$ to the point
$\mathbf{a}$. In other words, $\mathscr{l}$ is precisely the line passing
through $\mathbf{a}$ that is parallel to $\mathbf{b}$.

#### 5.1.5.b.

__Problem__. Show that the parallelogram with sides $\mathbf{x}$ and
$\mathbf{b}$ and the paralleogram with sides $\mathbf{a}$ and $\mathbf{b}$
have the same area.

__Solution__. The parallelogram with sides $\mathbf{x}$ and $\mathbf{b}$
can be expressed as $\mathbf{x} \wedge \mathbf{b}$. Similarly, the
parallelogram with sides $\mathbf{a}$ and $\mathbf{b}$ can be expressed as
$\mathbf{a} \wedge \mathbf{b}$. Rearranging the vector equation for the line,
we see that

\[
\mathbf{x} \wedge \mathbf{b} = \mathbf{a} \wedge \mathbf{b},
\]

which implies that the two parallelograms are equal oriented areas. In
particular, their areas are equal.

-------------------------------------------------------------------------------
