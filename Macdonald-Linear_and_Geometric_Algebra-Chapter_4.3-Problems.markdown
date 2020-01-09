Linear and Geometric Algebra (A. Macdonald): Chapter 4
======================================================

## Problems 4.3

-------------------------------------------------------------------------------

### 4.3.1

__Problem__. Prove that a subspace of an inner product space is an inner
product space.

__Solution__. A subspace of an inner product space (1) is a vector space
because it is a subspace of a vector space and (2) inherits the inner product
from the containing inner product space. Therefore, it is an inner product
space.

### 4.3.2

__Problem__. Define an inner product on $C[a, b]$ analogous to that of
Eq. (4.9): $\mathbf{u} \odot \mathbf{v} = a_1 u_1 v_1 + \cdots + a_n u_n v_n$.

__Solution__. Let $a(x) > 0$ on $[a, b]$, then an inner product analogous to
Eq. (4.9) is
\[
f \cdot g = \int_a^b a(x) f(x) g(x) dx
\]

### 4.3.3

#### 4.3.3.a

__Problem__. Prove that $\mathbf{u} \cdot \mathbf{0} = 0$.

__Solution__. Recall that $\mathbf{0} = \mathbf{0} + \mathbf{0}$. Therefore,
\[
\mathbf{u} \cdot \mathbf{0}
= \mathbf{u} \cdot \left( \mathbf{0} + \mathbf{0} \right)
= \mathbf{u} \cdot \mathbf{0} + \mathbf{u} \cdot \mathbf{0}
\]
Subtracting $\mathbf{u} \cdot \mathbf{0}$ from both sides,
\[
\mathbf{u} \cdot \mathbf{0} = 0
\]

#### 4.3.3.b

__Problem__. Prove that if
$\mathbf{u} \cdot \mathbf{u}_1 = \mathbf{u} \cdot \mathbf{u}_2$ for every
$\mathbf{u}$, then $\mathbf{u}_1 = \mathbf{u}_2$.

__Solution__.

### 4.3.4

__Problem__. (Parallelogram identity). Show that
\[
|\mathbf{u} + \mathbf{v}|^2 + |\mathbf{u} - \mathbf{v}|^2 =
2 \left( |\mathbf{u}|^2 + |\mathbf{v}|^2 \right)
\]

__Solution__.
\[
|\mathbf{u} + \mathbf{v}|^2
= (\mathbf{u} + \mathbf{v}) \cdot (\mathbf{u} + \mathbf{v})
= |\mathbf{u}|^2 + |\mathbf{v}|^2 + 2 (\mathbf{u} \cdot \mathbf{v})
\]

\[
|\mathbf{u} - \mathbf{v}|^2
= (\mathbf{u} - \mathbf{v}) \cdot (\mathbf{u} - \mathbf{v})
= |\mathbf{u}|^2 + |\mathbf{v}|^2 - 2 (\mathbf{u} \cdot \mathbf{v})
\]

Therefore,
\[
|\mathbf{u} + \mathbf{v}|^2 + |\mathbf{u} - \mathbf{v}|^2
= 2 \left( |\mathbf{u}|^2 + |\mathbf{v}|^2 \right)
\]

### 4.3.5

__Problem__. Show that $\mathbf{u} \cdot \mathbf{v} = 0$ if and only if
$|\mathbf{u} + \mathbf{v}| = |\mathbf{u} - \mathbf{v}|$.

__Solution__.
\[
|\mathbf{u} + \mathbf{v}|^2
= (\mathbf{u} + \mathbf{v}) \cdot (\mathbf{u} + \mathbf{v})
= |\mathbf{u}|^2 + |\mathbf{v}|^2 + 2 (\mathbf{u} \cdot \mathbf{v})
\]

\[
|\mathbf{u} - \mathbf{v}|^2
= (\mathbf{u} - \mathbf{v}) \cdot (\mathbf{u} - \mathbf{v})
= |\mathbf{u}|^2 + |\mathbf{v}|^2 - 2 (\mathbf{u} \cdot \mathbf{v})
\]

Therefore, $\mathbf{u} \cdot \mathbf{v} = 0$ implies that
$|\mathbf{u} + \mathbf{v}|^2 = |\mathbf{u} - \mathbf{v}|^2$ so that
$|\mathbf{u} + \mathbf{v}| = |\mathbf{u} - \mathbf{v}|$. Conversely,
$|\mathbf{u} + \mathbf{v}| = |\mathbf{u} - \mathbf{v}|$ implies that
$2 (\mathbf{u} \cdot \mathbf{v}) = -2 (\mathbf{u} \cdot \mathbf{v})$
so that $\mathbf{u} \cdot \mathbf{v} = 0$.

### 4.3.6

__Problem__. Prove that
\[
\mathbf{u} \cdot \mathbf{v}
\le \frac{1}{2} \left( |\mathbf{u}|^2 + |\mathbf{v}|^2 \right)
\]

__Solution__. Consider
\[
|\mathbf{u} - \mathbf{v}|^2
= (\mathbf{u} - \mathbf{v}) \cdot (\mathbf{u} - \mathbf{v})
= |\mathbf{u}|^2 + |\mathbf{v}|^2 - 2 (\mathbf{u} \cdot \mathbf{v})
\]

Since $|\mathbf{u} - \mathbf{v}|^2 \ge 0$,
\[
|\mathbf{u}|^2 + |\mathbf{v}|^2 - 2 (\mathbf{u} \cdot \mathbf{v}) \ge 0.
\]
Rearranging this inequality, we obtain the desired inequality
\[
\mathbf{u} \cdot \mathbf{v}
\le \frac{1}{2} \left( |\mathbf{u}|^2 + |\mathbf{v}|^2 \right)
\]

### 4.3.7

__Problem__. Show that
$(\mathbf{u} + \mathbf{v}) \cdot (\mathbf{u} - \mathbf{v}) = 0$ if and only if
$|\mathbf{u}| = |\mathbf{v}|$.

__Solution__.
\[
(\mathbf{u} + \mathbf{v}) \cdot (\mathbf{u} - \mathbf{v})
= |\mathbf{u}|^2 - |\mathbf{v}|^2
\]
The desired results follow from this identity.

### 4.3.8

__Problem__. Suppose that $\mathbf{u}$ and $\mathbf{v}$ are orthogonal. Show
that $|\mathbf{u} + t \mathbf{v}| \ge |\mathbf{u}|$ for all scalars $t$.

__Solution__.
\[
|\mathbf{u} + t \mathbf{v}|^2
= (\mathbf{u} + t \mathbf{v}) \cdot (\mathbf{u} + t \mathbf{v})
= |\mathbf{u}|^2 + t^2 |\mathbf{v}|^2 + 2 t (\mathbf{u} \cdot \mathbf{v})
= |\mathbf{u}|^2 + t^2 |\mathbf{v}|^2,
\]
where the last equality follows because $\mathbf{u}$ and $\mathbf{v}$ are
orthogonal. Since $t^2 |\mathbf{v}|^2 \ge 0$ for all $t$ and $\mathbf{v}$,
we can deduce that
\[
|\mathbf{u} + t \mathbf{v}|^2 \ge |\mathbf{u}|^2,
\]
which yields the desired inequality
\[
|\mathbf{u} + t \mathbf{v}| \ge |\mathbf{u}|.
\]

### 4.3.9

(Norms) Let $\mathbf{v} = (v_1, \ldots, v_n)$ be a vector in $\mathbb{R}^n$.
In this problem, we define two norms on $\mathbb{R}^n$ that cannot be defined
in terms of an inner product on $\mathbb{R}^n$.

#### 4.3.9.a

__Problem__. Define $|\mathbf{v}|_1 = |v_1| + \cdots + |v_n|$. Show that
$|\mathbf{v}|_1$ is a norm.

__Solution__. We need to show that $|\mathbf{v}|_1$ satisfies the properties
of a norm.

___N1___. If $\mathbf{v} \ne \mathbf{0}$, then at least one component of
$\mathbf{v}$ is nonzero. Without loss of generality, suppose that
$|v_1| \ne 0$. Then $|\mathbf{v}|_1 \ge |v_1| > 0$ so that
$|\mathbf{v}|_1 > 0$.

___N2___.
\[
  a \mathbf{v} = a (v_1, \ldots, v_n) = (a v_1, \ldots a v_n).
\]

Therefore
\[
|a \mathbf{v}|_1 = |a v_1| + \cdots + |a v_n|
                 = |a| |v_1| + \cdots + |a| |v_n| = |a| |\mathbf{v}|_1.
\]

___N3___.
\[
\mathbf{u} + \mathbf{v} = (u_1, \ldots, u_n) + (v_1, \ldots, v_n)
                        = (u_1 + v_1, \ldots, u_n + v_n)
\]

Therefore
\[
|\mathbf{u} + \mathbf{v}|_1
= |u_1 + v_1| + \cdots + |u_n + v_n|
\le (|u_1| + |v_1|) + \cdots + (|u_n| + |v_n|)
= |\mathbf{u}|_1 + |\mathbf{v}|_1
\]

#### 4.3.9.b

__Problem__. Define $|\mathbf{v}|_\infty = \max_{1 \le i \le n} |v_i|$. Show
that $|\mathbf{v}|_\infty$ is a norm.

__Solution__. We need to show that $|\mathbf{v}|_\infty$ satisfies the
properties of a norm.

___N1___. If $\mathbf{v} \ne \mathbf{0}$, then at least one component of
$\mathbf{v}$ is nonzero. Therefore, $\max_{1 \le i \le n} |v_i| > 0$ so that
$|\mathbf{v}|_\infty > 0$

___N2___.
\[
  a \mathbf{v} = a (v_1, \ldots, v_n) = (a v_1, \ldots a v_n).
\]

Therefore
\[
|a \mathbf{v}|_\infty = \max_{1 \le i \le n} |a v_i|
                 = |a| \max_{1 \le i \le n} |v_i| = |a| |\mathbf{v}|_\infty.
\]

___N3___.
\[
\mathbf{u} + \mathbf{v} = (u_1, \ldots, u_n) + (v_1, \ldots, v_n)
                        = (u_1 + v_1, \ldots, u_n + v_n)
\]

Therefore
\[
|\mathbf{u} + \mathbf{v}|_\infty
= \max_{1 \le i \le n} |u_i + v_i|
\le \max_{1 \le i \le n} (|u_i| + |v_i|)
= \max_{1 \le i \le n} |u_i| + \max_{1 \le i \le n} |v_i|
= |\mathbf{u}|_\infty + |\mathbf{v}|_\infty
\]

### 4.3.10

__Problem__. Let $|\mathbf{v}|$ be a norm on a vector space. Prove that
$|\mathbf{v} - \mathbf{u}| \ge ||\mathbf{v}| - |\mathbf{u}||$.

__Solution__. Applying the triangle inequality to

\[
\mathbf{v} = \mathbf{u} + (\mathbf{v} - \mathbf{u}) \\
\mathbf{u} = \mathbf{v} + (\mathbf{u} - \mathbf{v}),
\]

we find that
\[
|\mathbf{v}| \le |\mathbf{u}| + |\mathbf{v} - \mathbf{u}| \\
|\mathbf{u}| \le |\mathbf{v}| + |\mathbf{u} - \mathbf{v}|.
\]

Rearranging the inequalities,
\[
|\mathbf{v}| - |\mathbf{u}| \le |\mathbf{v} - \mathbf{u}| \\
|\mathbf{u}| - |\mathbf{v}| \le |\mathbf{u} - \mathbf{v}|.
\]

Combining these inequalities, we obtain
\[
-|\mathbf{u} - \mathbf{v}| = -|\mathbf{v} - \mathbf{u}|
\le |\mathbf{u}| - |\mathbf{v}|
\le |\mathbf{u} - \mathbf{v}|,
\]

which is equivalent to the desired result

\[
||\mathbf{u}| - |\mathbf{v}|| \le |\mathbf{u} - \mathbf{v}|.
\]

### 4.3.11

Consider the vectors $\mathbf{u} = (1,2,3,4)$ and
$\mathbf{v} = (4,3,2,1)$ in $\mathbb{R}^4$.

#### 4.3.11.a

__Problem__. Is the angle between the vectors acute ($< 90^\circ$),
right ($= 90^\circ$), or obtuse ($> 90^\circ$)?

__Solution__. The dot product of $\mathbf{u}$ and $\mathbf{v}$ is positive:

\[
\mathbf{u} \cdot \mathbf{v} = 4 + 6 + 6 + 4 = 20 > 0.
\]

Therefore, the angle between the vectors is acute.

#### 4.3.11.b

__Problem__. Now determine the angle between the vectors.

__Solution__. The cosine of the angle between $\mathbf{u}$ and $\mathbf{v}$
is given by

\[
\frac{\mathbf{u} \cdot \mathbf{v}}{|\mathbf{u}| |\mathbf{v}|}
= \frac{4 + 6 + 6 + 4}{1 + 4 + 9 + 16}
= 20 / 30 = 2/3.
\]

Therefore, the angle between $\mathbf{u}$ and $\mathbf{v}$ is $\arccos(2/3)$.

### 4.3.12

__Problem__. (Spacetime). Einstein's special relativity theory unites space
and time into _spacetime_. Spacetime is represented by a 4-dimentional vector
space with coordinates $(ct, x, y, z)$, where $c$ is the speed of light, $t$
is time, and $(x, y, z)$ are the spatial coordinates. The theory uses an
"inner product" on this space defined by

\[
(ct_1, x_1, y_1, z_1) \cdot (ct_2, x_2, y_2, z_2) =
c^2 t_1 t_2 - x_1 x_2 - y_1 y_2 - z_1 z_2.
\]

Which property of an inner product from Definition 4.9 are, and are not
satisfied by this "inner product"?

__Solution__.

By inspection, _I1_, _I2_, and _I3_ are satisfied. _I4_ is not satisified
because the inner product of a spacetime vector with itself can be zero or
negative. Examples of both of these situations are provided by the vectors
$(1, c, 0, 0)$ and $(1, c, c, 0)$, respectively.


-------------------------------------------------------------------------------
