Linear and Geometric Algebra (A. Macdonald): Chapter 4
======================================================

## Problems 4.3

-------------------------------------------------------------------------------

### 4.3.1.

__Problem__. Prove that a subspace of an inner product space is an inner
product space.

__Solution__. A subspace of an inner product space (1) is a vector space
because it is a subspace of a vector space and (2) inherits the inner product
from the containing inner product space. Therefore, it is an inner product
space.

### 4.3.2.

__Problem__. Define an inner product on $C[a, b]$ analogous to that of
Eq. (4.9): $\mathbf{u} \odot \mathbf{v} = a_1 u_1 v_1 + \cdots + a_n u_n v_n$.

__Solution__. Let $a(x) > 0$ on $[a, b]$, then an inner product analogous to
Eq. (4.9) is
\[
f \cdot g = \int_a^b a(x) f(x) g(x) dx
\]

### 4.3.3.

#### 4.3.3.a.

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

#### 4.3.3.b.

__Problem__. Prove that if
$\mathbf{u} \cdot \mathbf{u}_1 = \mathbf{u} \cdot \mathbf{u}_2$ for every
$\mathbf{u}$, then $\mathbf{u}_1 = \mathbf{u}_2$.

__Solution__.

### 4.3.4.

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

### 4.3.5.

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

### 4.3.6.

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

### 4.3.7.

__Problem__. Show that
$(\mathbf{u} + \mathbf{v}) \cdot (\mathbf{u} - \mathbf{v}) = 0$ if and only if
$|\mathbf{u}| = |\mathbf{v}|$.

__Solution__.
\[
(\mathbf{u} + \mathbf{v}) \cdot (\mathbf{u} - \mathbf{v})
= |\mathbf{u}|^2 - |\mathbf{v}|^2
\]
The desired results follow from this identity.

### 4.3.8.

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

### 4.3.9.

(Norms) Let $\mathbf{v} = (v_1, \ldots, v_n)$ be a vector in $\mathbb{R}^n$.
In this problem, we define two norms on $\mathbb{R}^n$ that cannot be defined
in terms of an inner product on $\mathbb{R}^n$.

### 4.3.9.a.

__Problem__. Define $|\mathbf{v}|_1 = |v_1| + \cdots + |v_n|$. Show that
$|\mathbf{v}|_1$ is a norm.

__Solution__. TODO

### 4.3.9.b.

__Problem__. Define $|\mathbf{v}|_\infty = \max_{1 \le i \le n} |v_i|$. Show
that $|\mathbf{v}|_\infty$ is a norm.

__Solution__. TODO

-------------------------------------------------------------------------------
