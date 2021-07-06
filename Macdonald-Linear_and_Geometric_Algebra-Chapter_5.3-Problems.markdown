Linear and Geometric Algebra (A. Macdonald): Chapter 5
======================================================

## Problems 5.3

-------------------------------------------------------------------------------

### 5.3.1.

__Problem__. The geometric product distributes over vector addition:

$$
(\mathbf{u} + \mathbf{v}) \mathbf{w} =
\mathbf{u} \mathbf{w} + \mathbf{v} \mathbf{w}
$$

and

$$
\mathbf{w} (\mathbf{u} + \mathbf{v}) =
\mathbf{w} \mathbf{u} + \mathbf{w} \mathbf{v}
$$

Prove the first of these.

__Solution__.

$$
  (\mathbf{u} + \mathbf{v}) \mathbf{w}
=   (\mathbf{u} + \mathbf{v}) \cdot \mathbf{w}
  + (\mathbf{u} + \mathbf{v}) \wedge \mathbf{w} \\
=   (\mathbf{u} \cdot \mathbf{w} + \mathbf{v} \cdot \mathbf{w})
  + (\mathbf{u} \wedge \mathbf{w} + \mathbf{v} \wedge \mathbf{w}) \\
=   (\mathbf{u} \cdot \mathbf{w} + \mathbf{u} \wedge \mathbf{w})
  + (\mathbf{v} \cdot \mathbf{w} + \mathbf{v} \wedge \mathbf{w}) \\
=   \mathbf{u} \mathbf{w} + \mathbf{v} \mathbf{w}
$$

### 5.3.2.

#### 5.3.2.a.

__Problem__. Let $A$ be a multivector which is not a scalar. Show that if
$A^2 = a A$, $a$ a scalar, then $A$ has no inverse.

__Solution__. Rearranging $A^2 = a A$ and factoring, we find that
$A (A - a) = 0$. Suppose that $A$ has an inverse. Multiplying by $A^{-1}$
would yield $A - a = A^{-1} 0 = 0$. In other words, $A = a$, which contradicts
the assumption that $A$ is not a scalar. Therefore, $A$ cannot have an inverse.

#### 5.3.2.b.

__Problem__. Show that if $\mathbf{e}$ is a unit vector then $1 + \mathbf{e}$
has no inverse.

__Solution__. $(1 + \mathbf{e})^2 = 1 + 2 \mathbf{e} + 1 = 2 (1 + \mathbf{e})$.
Therefore, by part (a), $1 + \mathbf{e}$ has no inverse.

### 5.3.3.

__Problem__. Solve the system of equations $\mathbf{a} \cdot \mathbf{v} = s$,
$\mathbf{a} \wedge \mathbf{v} = \mathbf{B}$ for the unknown vector
$\mathbf{v}$. Here $\mathbf{a} \ne \mathbf{0}$ is a vector, $s$ is a scalar,
and $\mathbf{B}$ is a bivector.

__Solution__. Use the geometric product to combine these two equations into a
single equation:

$$
\mathbf{a} \mathbf{v} = s + \mathbf{B}.
$$

Right multiplying this equation by
$\mathbf{a}^{-1} = \mathbf{a} / |\mathbf{a}|^2$ yields the solution

$$
\mathbf{v}
= \frac{\mathbf{a} (s + \mathbf{B})}{|\mathbf{a}|^2}
= \frac{s \mathbf{a} + \mathbf{a} \mathbf{B}}{|\mathbf{a}|^2}.
$$


### 5.3.4.

__Problem__. Suppose that $\mathbf{a} \perp \mathbf{b}$. Show that

$$
\mathbf{a} \cdot (\mathbf{a} \wedge \mathbf{b}) = |\mathbf{a}|^2 \mathbf{b}.
$$

_Hint_: In Chapter 6 we will learn that vector $\cdot$ bivector is the vector
part of (vector)(bivector).

__Solution__. First, we extend the definition of geometric product to the
product of a vector times a bivector:

$$
\mathbf{u} \mathbf{B}
= \mathbf{u} \cdot \mathbf{B} + \mathbf{u} \wedge \mathbf{B}.
$$

Using this definition,

$$
\mathbf{a} (\mathbf{a} \wedge \mathbf{b})
=   \mathbf{a} \cdot (\mathbf{a} \wedge \mathbf{b}) +
  + \mathbf{a} \wedge (\mathbf{a} \wedge \mathbf{b})
= \mathbf{a} \cdot (\mathbf{a} \wedge \mathbf{b})
$$

because the outer product is commutative and $\mathbf{a} \wedge \mathbf{a} = 0$.

Since $\mathbf{a} \perp \mathbf{b}$, $\mathbf{a} \wedge \mathbf{b}$ is equal
to the geometric product of $\mathbf{a}$ and $\mathbf{b}$, so

$$
\mathbf{a} (\mathbf{a} \wedge \mathbf{b})
= \mathbf{a} (\mathbf{a} \mathbf{b})
= |\mathbf{a}|^2 \mathbf{b}
$$

where we have used the associative property of the geometric product.
Combining these results yields the desired result.

### 5.3.5.

__Problem__. Show that

$$
\mathbf{e}_1 \cdot (\mathbf{e}_2 \wedge \mathbf{e}_3) = 0
$$

__Solution__. TODO

-------------------------------------------------------------------------------
