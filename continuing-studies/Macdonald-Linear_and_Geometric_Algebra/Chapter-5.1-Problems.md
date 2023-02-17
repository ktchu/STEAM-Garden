Linear and Geometric Algebra (A. Macdonald): Chapter 5.1 Problems
=================================================================
--------------------------------------------------------------------------------------------
### 5.1.1.

__Problem__. Show that oriented area addition is well defined, i.e., if
$a \mathbf{w}$ ($a \ne 0$) is used instead of $\mathbf{w}$ to form
$\mathbf{B}_1 + \mathbf{B}_2$ in Figure 5.4, then the sum is the same.

__Solution__. Since any vector in the intersection of the planes
$\mathbf{B}_1$ and $\mathbf{B}_2$ must be a nonzero scalar multiple of
$\mathbf{w}$, we show that the construction for $\mathbf{B}_1 + \mathbf{B}_2$
in Figure 5.4 yields the same result for $a \mathbf{w}$ ($a \ne 0$). Without
loss of generality, we can assume that that $\mathbf{B}_1$ can be represented
as $\mathbf{B}_1 = \mathbf{w} \wedge \mathbf{u}$. Therefore, reshaping
$\mathbf{B}_1$ into a rectangle using $a \mathbf{w}$ as one of the sides, we
find that the other side must be equal to $(1/a) \mathbf{u}$ so that the outer
product of the sides does not change. Similarly, for $\mathbf{B}_2$, the other
side is equal to $(1/a) \mathbf{v}$.

Using the construction from Figure 5.4, we obtain the rectangle that is
represented by

$$
a \mathbf{w} \wedge
  \left(\frac{1}{a} \mathbf{u} + \frac{1}{a} \mathbf{v} \right)
= a \mathbf{w} \wedge \frac{1}{a} (\mathbf{u} + \mathbf{v})
= \mathbf{w} \wedge (\mathbf{u} + \mathbf{v}) = \mathbf{B}_1 + \mathbf{B}_2,
$$

where the last equality follows from the definition of
$\mathbf{B}_1 + \mathbf{B}_2$ in the construction shown in Figure 5.4.

--------------------------------------------------------------------------------------------
### 5.1.2.

#### 5.1.2.a.

__Problem__. Find the area of the parallelogram with vertices at (0,0),
(2,1), (1,3), and (3,4).

__Solution__. Let $\mathbf{u} = 2 \mathbf{e}_1 + \mathbf{e}_2$ and
$\mathbf{v} = \mathbf{e}_1 + 3 \mathbf{e}_2$. Then, the parallelogram
can be represented by the oriented area

$$
\mathbf{u} \wedge \mathbf{v}
= (2 \mathbf{e}_1 + \mathbf{e}_2) \wedge (\mathbf{e}_1 + 3 \mathbf{e}_2)
= 5 \mathbf{e}_1 \wedge \mathbf{e}_2.
$$

The area of the parellelogram is equal to 5 because
$|5 \mathbf{e}_1 \wedge \mathbf{e}_2| = 5 |\mathbf{e}_1 \wedge \mathbf{e}_2|$
and $|\mathbf{e}_1 \wedge \mathbf{e}_2| = 1$.

#### 5.1.2.b.

__Problem__. Find the area of the triangle with vertices at (0,0),
(2,1), and (1,3).

__Solution__. The triangle with vertices at (0,0), (2,1), and (1,3) is half
the parallelogram from part (a), so the area is equal to half the area
of $5 \mathbf{e}_1 \wedge \mathbf{e}_2$. Therefore, the area of the triangle
is equal to 5/2.

--------------------------------------------------------------------------------------------
### 5.1.3.

__Problem__. Find the area of the parallelogram with vertices at (1,1), (3,2),
(2,4), and (4,5).

__Solution__. The parallelogram with vertices at (1,1), (3,2), (2,4), and
(4,5) is the same as the parallelogram from Problem 5.1.2.a shifted by
$\mathbf{e}_1 + \mathbf{e}_2$, so the parallelogram is represented by the same
oriented area and the area of the parallelogram is 5.

--------------------------------------------------------------------------------------------
### 5.1.4.

See Theorem 5.2.

#### 5.1.4.a.

__Problem__. Prove the companion to O3:

$$
a(\mathbf{u} \wedge \mathbf{v}) = \mathbf{u} \wedge (a \mathbf{v}).
$$

__Solution__.

_Geometric Proof_. We modify Figure 5.6 so that the scaled parallelogram is
represented by a parallelgram with $\mathbf{u}$ unchanged and $\mathbf{v}$ is
extended to $a \mathbf{v}$. The area of the resulting scaled parallel can be
represented by $\mathbf{u} \wedge (a \mathbf{v})$.

_Algebraic Proof_. We first observe that $a (\mathbf{u} \wedge \mathbf{v})$ is
in the same plane as $\mathbf{u} \wedge (a \mathbf{v})$ because the first
vectors are parallel and the second vectors are parallel. Second, both sides
of the equation have the same orientation for the following reasons.

* If $a > 0$, then the orientation of neither side of the equation changes
  relative to the orientation of $\mathbf{u} \wedge \mathbf{v}$.

* If $a < 0$, then the orientation of the left-hand side of the equation is
  opposite the orientation of $\mathbf{u} \wedge \mathbf{v}$. The orientation
  of $a \mathbf{v}$ is opposite the orientation of $\mathbf{v}$, so
  $\mathbf{u} \wedge (a \mathbf{v})$ is also opposite the orientation of
  $\mathbf{u} \wedge \mathbf{v}$.

Finally, the norm of both sides of the equation are equal because

$$
|a (\mathbf{u} \wedge \mathbf{v})|
= |a| |\mathbf{u}| |\mathbf{v}| \sin \theta
= |\mathbf{u}| |(a \mathbf{v})| \sin \theta
= |\mathbf{u} \wedge (a \mathbf{v})|,
$$

where $\theta$ is the angle between $\mathbf{u}$ and $\mathbf{v}$ (measured
from $\mathbf{u}$ to $\mathbf{v}$).

Combined, these results that the two sides of the equation are equal.

#### 5.1.4.b.

__Problem__. Prove the companion to O4:

$$
  \mathbf{w} \wedge (\mathbf{u} + \mathbf{v})
= \mathbf{w} \wedge \mathbf{u} + \mathbf{w} \wedge \mathbf{v}.
$$

__Solution__. Using O2 and O4,

$$
\mathbf{w} \wedge (\mathbf{u} + \mathbf{v})
= -(\mathbf{u} + \mathbf{v}) \wedge \mathbf{w}
= (-\mathbf{u} - \mathbf{v}) \wedge \mathbf{w}
= -\mathbf{u} \wedge \mathbf{w} - \mathbf{v} \wedge \mathbf{w}
= \mathbf{w} \wedge \mathbf{u} + \mathbf{w} \wedge \mathbf{v}
$$

--------------------------------------------------------------------------------------------
### 5.1.5.

Let $\mathbf{a}$ and $\mathbf{b} \ne \mathbf{0}$ be given vectors.

#### 5.1.5.a.

__Problem__. Show that

$$
(\mathbf{x} - \mathbf{a}) \wedge \mathbf{b} = \mathbf{0}
$$

is a vector equation of the line $\mathscr{l}$ through $\mathbf{a}$ and
parallel to $\mathbf{b}$.

__Solution__. Observe that $\mathbf{u} \wedge \mathbf{b} = 0$ if and only if
the sine of the angle between $\mathbf{u}$ and $\mathbf{b}$ is 0. Therefore,
the angle between $\mathbf{u}$ and $\mathbf{b}$ is 0 or $\pi$, so $\mathbf{u}$
and $\mathbf{b}$ are parallel. Applying this observation to the equation

$$
(\mathbf{x} - \mathbf{a}) \wedge \mathbf{b} = \mathbf{0},
$$

we can conclude that the set of points $\mathscr{l}$ satisfying this equation
consists of those points where $(\mathbf{x} - \mathbf{a})$ is parallel
to $\mathbf{b}$ -- that is, $\mathscr{l}$ is the set of points that can be reached
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

$$
\mathbf{x} \wedge \mathbf{b} = \mathbf{a} \wedge \mathbf{b},
$$

which implies that the two parallelograms are equal oriented areas. In
particular, their areas are equal.

--------------------------------------------------------------------------------------------
