Linear and Geometric Algebra (A. Macdonald): Chapter 4
======================================================

## Exercises: Section 4.4

-------------------------------------------------------------------------------

### 4.24.

__Problem__. Prove the Corollary 4.17: a set of $n$ nonzero orthogonal vectors
in an $n$-dimensional inner product space is a basis.

__Solution__. Let $V$ be the $n$-dimensional inner product space, and let $B$
be a set of $n$ nonzero orthogonal vectors in $V$. By Theorem 4.16, the
elements of $B$ are linearly independent.  Therefore, by (Theorem 2.19),
$B$ is a basis.

### 4.25.

__Problem__. Let $\{ \mathbf{u}_1, \ldots, \mathbf{u}_r \}$ be a basis for a
subspace $\mathbf{U}$. Show that $\mathbf{v}$ is orthogonal to $\mathbf{U}$
if and only if it is orthogonal to every $\mathbf{u}_i$.

__Solution__.

($\Rightarrow$) If $\mathbf{v}$ is orthogonal to $\mathbf{U}$,
then $\mathbf{v}$ is orthogonal to every vector in $\mathbf{U}$. Therefore,
$\mathbf{v}$ is orthogonal to every $\mathbf{u}_i$ because every
$\mathbf{u}_i \in \mathbf{U}$.

($\Leftarrow$) Since the $\mathbf{u}_i$ form a basis for $\mathbf{U}$,
any $\mathbf{w} \in \mathbf{U}$ can be expressed as a linear combination of
the $\mathbf{u}_i$: $\mathbf{w} = \sum_i c_i \mathbf{u}_i$. Taking the inner
product of $\mathbf{w}$ with $\mathbf{v}$, we find that
\[
\mathbf{v} \cdot \mathbf{w} = \sum_i c_i \mathbf{v} \cdot \mathbf{u}_i
= \sum_i 0 = 0.
\]

Therefore, $\mathbf{v}$ is orthogonal to $\mathbf{U}$.

### 4.26.

__Problem__. Show that $\mathbf{b}_3 \perp \mathbf{U}_2$,
$\mathbf{b}_3 \ne \mathbf{0}$, and
$\{ \mathbf{b}_1, \mathbf{b}_2, \mathbf{b}_3 \}$ is an orthogonal basis
for $\mathbf{U}_3 = \text{span}(\mathbf{u}_1, \mathbf{u}_2, \mathbf{u}_3)$.
Draw a figure showing $\mathbf{b}_1$, $\mathbf{b}_2$, $\mathbf{b}_3$, and
$\mathbf{u}_3$

__Solution__.

_Show that $\mathbf{b}_3 \perp \mathbf{U}_2$_. Observe that
$\mathbf{b}_3 \perp \mathbf{b}_1$:
\[
\mathbf{b}_1 \cdot \mathbf{b}_3
= \mathbf{b}_1 \cdot \left(
    \mathbf{u}_3
  - \frac{\mathbf{u}_3 \cdot \mathbf{b}_1}{\mathbf{b}_1 \cdot \mathbf{b}_1}
      \mathbf{b}_1
  - \frac{\mathbf{u}_3 \cdot \mathbf{b}_2}{\mathbf{b}_2 \cdot \mathbf{b}_2}
      \mathbf{b}_2
  \right)
= \mathbf{b}_1 \cdot \mathbf{u}_3
  - \frac{\mathbf{u}_3 \cdot \mathbf{b}_1}{\mathbf{b}_1 \cdot \mathbf{b}_1}
      (\mathbf{b}_1 \cdot \mathbf{b}_1)
  - \frac{\mathbf{u}_3 \cdot \mathbf{b}_2}{\mathbf{b}_2 \cdot \mathbf{b}_2}
      (\mathbf{b}_1 \cdot \mathbf{b}_2) \\
= \mathbf{b}_1 \cdot \mathbf{u}_3 - \mathbf{u}_3 \cdot \mathbf{b}_1 - 0
= 0.
\]

where the second to last equality follows from orthogonality of
$\mathbf{b}_1$ and $\mathbf{b}_2$. An analogous derivation shows that
$\mathbf{b}_3 \perp \mathbf{b}_2$. Since
$\mathbf{U}_2 = \text{span} (\mathbf{u}_1, \mathbf{u}_2)
              = \text{span} (\mathbf{b}_1, \mathbf{b}_2)$, it follows that
$\mathbf{b}_3 \perp \mathbf{U}_2$.


_Show that $\mathbf{b}_3 \ne \mathbf{0}$_.
Since $\mathbf{u}_1$, $\mathbf{u}_2$, $\mathbf{u}_3$ are linearly independent
and $\text{span} (\mathbf{u}_1, \mathbf{u}_2)
 = \text{span} (\mathbf{b}_1, \mathbf{b}_2)$, $\mathbf{u}_3$ cannot be equal
to a linear combination of $\mathbf{b}_1$ and $\mathbf{b}_2$. Therefore,
$\mathbf{b}_3$ is not zero.

_Show $\{ \mathbf{b}_1, \mathbf{b}_2, \mathbf{b}_3 \}$ is an orthogonal basis
for $\mathbf{U}_3 = \text{span}(\mathbf{u}_1, \mathbf{u}_2, \mathbf{u}_3)$_.
The definition of $\mathbf{b}_3$ shows that
$\mathbf{b}_3 \in \text{span} (\mathbf{b}_1, \mathbf{b}_2, \mathbf{u}_3)$ and
$\mathbf{u}_3 \in \text{span} (\mathbf{b}_1, \mathbf{b}_2, \mathbf{b}_3)$,so
$\text{span} (\mathbf{b}_1, \mathbf{b}_2, \mathbf{u}_3) =
 \text{span} (\mathbf{b}_1, \mathbf{b}_2, \mathbf{b}_3)$.
Since
$\text{span} (\mathbf{b}_1, \mathbf{b}_2) =
 \text{span} (\mathbf{u}_1, \mathbf{u}_2)$,
$\text{span} (\mathbf{b}_1, \mathbf{b}_2, \mathbf{b}_3) =
 \text{span} (\mathbf{u}_1, \mathbf{u}_2, \mathbf{u}_3) = \mathbf{U}_3$.
Finally, since $\{ \mathbf{b}_1, \mathbf{b}_2, \mathbf{b}_3 \}$ are nonzero
orthogonal vectors, they are linearly independent and form an orthogonal
basis for $\mathbf{U}_3$.

### 4.27.

__Problem__. Write the expression for $\mathbf{b}_4$.

__Solution__.
\[
\mathbf{b}_4 =
    \mathbf{u}_4
  - \frac{\mathbf{u}_4 \cdot \mathbf{b}_1}{\mathbf{b}_1 \cdot \mathbf{b}_1}
      \mathbf{b}_1
  - \frac{\mathbf{u}_4 \cdot \mathbf{b}_2}{\mathbf{b}_2 \cdot \mathbf{b}_2}
      \mathbf{b}_2
  - \frac{\mathbf{u}_4 \cdot \mathbf{b}_3}{\mathbf{b}_3 \cdot \mathbf{b}_3}
      \mathbf{b}_3
\]

### 4.28.

__Problem__. Perform a Gram-Schmidt orthogonalization on the linearly
independent vectors $\mathbf{u}_1 = (2,2,2)$, $\mathbf{u}_2 = (0,2,2)$,
and $\mathbf{u}_3 = (0,0,2)$.

__Solution__.
\[
\mathbf{b}_1 = \mathbf{u}_1 = (2,2,2)
\]

\[
\mathbf{b}_2
=   \mathbf{u}_2
  - \frac{\mathbf{u}_2 \cdot \mathbf{b}_1}{\mathbf{b}_1 \cdot \mathbf{b}_1}
    \mathbf{b}_1
= (0,2,2) - \frac{(0,2,2) \cdot (2,2,2)}{12} (2,2,2)
= (0,2,2) - \frac{8}{12} (2,2,2) \\
= (0,2,2) - (4/3,4/3,4/3) = (-4/3,2/3,2/3)
\]

\[
\mathbf{b}_3
=   \mathbf{u}_3
  - \frac{\mathbf{u}_3 \cdot \mathbf{b}_1}{\mathbf{b}_1 \cdot \mathbf{b}_1}
    \mathbf{b}_1
  - \frac{\mathbf{u}_3 \cdot \mathbf{b}_2}{\mathbf{b}_2 \cdot \mathbf{b}_2}
    \mathbf{b}_2 \\
=   (0,0,2)
  - \frac{(0,0,2) \cdot (2,2,2)}{12} (2,2,2)
  - \frac{(0,0,2) \cdot (-4/3,2/3,2/3)}{24/9} (-4/3,2/3,2/3) \\
=   (0,0,2) - \frac{4}{12} (2,2,2) - \frac{4/3}{24/9} (-4/3,2/3,2/3) \\
=   (0,0,2) - (2/3,2/3,2/3) - (-2/3,1/3,1/3) \\
= (0,-1,1)
\]

### 4.29.

__Problem__. Let $\mathbf{A} = \text{span}(\mathbf{a}_1, \ldots \mathbf{a}_m)$
and $\mathbf{B} = \text{span}(\mathbf{b}_1, \ldots \mathbf{b}_n)$. Show that
$\text{span} (\mathbf{A}, \mathbf{B})
 = \text{span} (\mathbf{a}_1, \ldots \mathbf{a}_m,
                \mathbf{b}_1, \ldots \mathbf{b}_n)$.

__Solution__.

Suppose that $\mathbf{u} \in \text{span}(\mathbf{A}, \mathbf{B})$. Then
$\mathbf{u} = \mathbf{a} + \mathbf{b}$ for $\mathbf{a} \in \mathbf{A}$ and
$\mathbf{b} \in \mathbf{B}$.  Since $\mathbf{a} \in \mathbf{A}$ and
$\mathbf{b} \in \mathbf{B}$, $\mathbf{a}$ is a linear combination of
$\{ \mathbf{a}_1, \ldots, \mathbf{a}_m \}$ and $\mathbf{b}$ is a linear
combination of $\{ \mathbf{b}_1, \ldots, \mathbf{b}_n \}$. Therefore,
$\mathbf{u}$ is a linear combination of
$\{ \mathbf{a}_1, \ldots, \mathbf{a}_m, \mathbf{b}_1, \ldots, \mathbf{b}_n \}$,
so $\mathbf{u} \in \text{span} (\mathbf{a}_1, \ldots \mathbf{a}_m,
                                \mathbf{b}_1, \ldots \mathbf{b}_n)$
and $\text{span}(\mathbf{A}, \mathbf{B}) \subseteq
     \text{span} (\mathbf{a}_1, \ldots \mathbf{a}_m,
                  \mathbf{b}_1, \ldots \mathbf{b}_n)$.

Next, suppose that $\mathbf{u} \in
                    \text{span} (\mathbf{a}_1, \ldots \mathbf{a}_m,
                                 \mathbf{b}_1, \ldots \mathbf{b}_n)$.
Then, $\mathbf{u}$ is a linear combination of
$\{ \mathbf{a}_1, \ldots, \mathbf{a}_m, \mathbf{b}_1, \ldots, \mathbf{b}_n \}$:
\[
  \mathbf{u} = \sum_{i=1}^m \alpha_i \mathbf{a}_i
             + \sum_{i=1}^n \beta_i \mathbf{b}_i.
\]
Since $\sum_{i=1}^m \alpha_i \mathbf{a}_i \in \mathbf{A}$ and
$\sum_{i=1}^n \beta_i \mathbf{b}_i \in \mathbf{B}$, we see that $\mathbf{u}$
is the sum of a vector in $\mathbf{A}$ and a vector in $\mathbf{B}$. Therefore,
$\mathbf{u} \in \text{span}(\mathbf{A}, \mathbf{B})$ and
$\text{span} (\mathbf{a}_1, \ldots \mathbf{a}_m,
              \mathbf{b}_1, \ldots \mathbf{b}_n) \subseteq
 \text{span}(\mathbf{A}, \mathbf{B})$.

Combining the two inclusion results, we obtain the desired result:
$\text{span} (\mathbf{a}_1, \ldots \mathbf{a}_m,
              \mathbf{b}_1, \ldots \mathbf{b}_n)
 = \text{span}(\mathbf{A}, \mathbf{B})$.

### 4.30.

#### 4.30.a.

__Problem__. Let $\mathbf{U}$ be the $\mathbf{e}_1 \mathbf{e}_2$ plane in
$\mathbb{R}^3$. What is $\mathbf{U}^\perp$?

__Solution__. $\mathbf{U}^\perp$ is the $\mathbf{e}_3$ line.

#### 4.30.b

__Problem__. Let $\mathbf{U}$ be the $\mathbf{e}_1 \mathbf{e}_2$ plane in
$\mathbb{R}^4$. What is $\mathbf{U}^\perp$?

__Solution__. $\mathbf{U}^\perp$ is the line $\mathbf{e}_3 \mathbf{e}_4$ plane.

### 4.31.

__Problem__. Let $\mathbf{U}$ be a subspace of an inner product space
$\mathbf{V}$. Then $\mathbf{U}^\perp$ is a subspace of $\mathbf{V}$.

__Solution__.

We need to show that (1) $\mathbf{0} \in \mathbf{U}^\perp$ and
(2) $\mathbf{U}^\perp$ is closed under scalar multiplication and vector
addition.

(1) $\mathbf{0} \in \mathbf{U}^\perp$ because
$\mathbf{0} \cdot \mathbf{u} = 0$ for every $\mathbf{u} \in \mathbf{U}$.

(2) Let $\mathbf{v}, \mathbf{w} \in \mathbf{U}^\perp$ and let
$\mathbf{u} \in \mathbf{U}$.

$\mathbf{v} \cdot \mathbf{u} = 0$ implies that
$(\alpha \mathbf{v}) \cdot \mathbf{u} = 0$. Since this holds for all
$\mathbf{u} \in \mathbf{U}$, $(\alpha \mathbf{v}) \in \mathbf{U}^\perp$ and
$\mathbf{U}^\perp$ is closed under scalar multiplication.

$\mathbf{v} \cdot \mathbf{u} = 0$ and $\mathbf{w} \cdot \mathbf{u} = 0$
implies that $(\mathbf{v} + \mathbf{w}) \cdot \mathbf{u} = 0$. Since this is holds for any
$\mathbf{u} \in \mathbf{U}$, $\mathbf{v} + \mathbf{w} \in \mathbf{U}^\perp$
and $\mathbf{U}^\perp$ is closed under vector addition.

### 4.32.

#### 4.32.a.

__Problem__. Find $P_{\mathbf{U}} (\mathbf{v})$, where $\mathbf{v} = (1,1,1,1)$
and $\mathbf{U}$ is 2-dimensional, with orthogonal basis
$\mathbf{u}_1 = (3,0,4,0)$ and $\mathbf{u}_2 = (0,3,0,4)$.

__Solution__.

Normalizing $\mathbf{u}_1$ and $\mathbf{u}_2$, we obtain an orthonormal
basis for $\mathbf{U}$:

\[
  \hat{\mathbf{u}}_1 = (3/5, 0, 4/5, 0) \\
  \hat{\mathbf{u}}_2 = (0, 3/5, 0, 4/5)
\]

Projecting $\mathbf{v}$ onto $\hat{\mathbf{u}}_1$ and $\hat{\mathbf{u}}_2$,
we obtain $P_\mathbf{U} (\mathbf{v})$:

\[
  P_\mathbf{U} (\mathbf{v}) = (21/25, 21/25, 28/25, 28/25).
\]

#### 4.32.b

__Problem__. Determine $\mathbf{v} - P_{\mathbf{U}} (\mathbf{v})$.
A check: $|\mathbf{v} - P_{\mathbf{U}} (\mathbf{v})| = 0.28$.

__Solution__.

\[
  \mathbf{v} - P_\mathbf{U} (\mathbf{v})
  = (1, 1, 1, 1) - (21/25, 21/25, 28/25, 28/25) \\
  = (4/25, 4/25, -3/25, -3/25).
\]

Check: $|\mathbf{v} - P_\mathbf{U} (\mathbf{v})| = \sqrt{50} / 25 \approx 0.28$

-------------------------------------------------------------------------------
