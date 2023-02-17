Linear and Geometric Algebra (A. Macdonald): Chapter 5.3 Exercises
==================================================================
--------------------------------------------------------------------------------------------
### 5.9.

#### 5.9.a.

__Problem__. Verify vector space axiom V1 for $\mathbb{G}^3$.

$$
  M + N = N + M
$$

__Solution__. Axiom V1 for $\mathbb{G}^3$ follows because the commutative
property holds for scalar addition, vector addition, bivector addition, and
trivector addition.

#### 5.9.b.

__Problem__. Verify vector space axiom V4 for $\mathbb{G}^3$.

$$
  0 M = 0
$$

__Solution__. Axiom V4 for $\mathbb{G}^3$ follows because scalar multiplication
of scalars, vectors, bivectors, and trivectors by 0 yields 0. Therefore, scalar
multiplication of $M = s + \mathbf{v} + \mathbf{B} + \mathbf{T}$ by 0 yields
0.

--------------------------------------------------------------------------------------------
### 5.10.

Prove the consequences of the definition of the geometric product:

$$
\mathbf{u} \mathbf{v}
= \mathbf{u} \cdot \mathbf{v} + \mathbf{u} \wedge \mathbf{v}
$$

#### 5.10.a.

__Problem__.

$$
\mathbf{u} \parallel \mathbf{v} \Leftrightarrow
\mathbf{u} \mathbf{v} = \mathbf{u} \cdot \mathbf{v}
= \pm|\mathbf{u}| |\mathbf{v}| \textrm{, a scalar}
$$

__Solution__. If $\mathbf{u} \parallel \mathbf{v}$, then
$\mathbf{u} \cdot \mathbf{v} = \pm |\mathbf{u}| |\mathbf{v}|$ and
$\mathbf{u} \wedge \mathbf{v} = 0$. Therefore,

$$
  \mathbf{u} \mathbf{v}
  = \mathbf{u} \cdot \mathbf{v}
  = \pm |\mathbf{u}| |\mathbf{v}|.
$$

#### 5.10.b.

__Problem__.

$$
\mathbf{u} \perp \mathbf{v} \Leftrightarrow
\mathbf{u} \mathbf{v} = \mathbf{u} \wedge \mathbf{v}
\textrm{, a bivector}
$$

__Solution__. If $\mathbf{u} \perp \mathbf{v}$, then
$\mathbf{u} \cdot \mathbf{v} = 0$. Therefore,

$$
  \mathbf{u} \mathbf{v} = \mathbf{u} \wedge \mathbf{v}.
$$

#### 5.10.c.

__Problem__.

$$
\mathbf{u} \perp \mathbf{v} \Leftrightarrow
\mathbf{u} \mathbf{v} = -\mathbf{v} \mathbf{u}
\textrm{, a bivector}
$$

__Solution__. If $\mathbf{u} \perp \mathbf{v}$, then
$\mathbf{u} \mathbf{v} = \mathbf{u} \wedge \mathbf{v}$ and
$\mathbf{v} \mathbf{u} = \mathbf{v} \wedge \mathbf{u}$. Therefore

$$
  \mathbf{u} \mathbf{v} = - \mathbf{v} \mathbf{u}.
$$

--------------------------------------------------------------------------------------------
### 5.11.

__Problem__. Prove: If $a$ is a scalar and $\mathbf{u}$ and $\mathbf{v}$ are
vectors, then $a(\mathbf{u} \mathbf{v}) = (a\mathbf{u}) \mathbf{v}$. It is also
$a(\mathbf{u} \mathbf{v}) = \mathbf{u} (a\mathbf{v})$.

__Solution__.

$$
  a(\mathbf{u} \mathbf{v})
  = a(\mathbf{u} \cdot \mathbf{v} + \mathbf{u} \wedge \mathbf{v})
  = a (\mathbf{u} \cdot \mathbf{v}) + a (\mathbf{u} \wedge \mathbf{v})
  = (a \mathbf{u}) \cdot \mathbf{v} + (a \mathbf{u}) \wedge \mathbf{v}
  = (a \mathbf{u}) \mathbf{v}.
$$

--------------------------------------------------------------------------------------------
### 5.12.

__Problem__. Solve the equation

$$
(3 \mathbf{e}_1 + 4 \mathbf{e}_2) M + (3 \mathbf{e}_1 + 4 \mathbf{e}_2) =
5 \mathbf{e}_1 + 7 \mathbf{e}_2
$$

for the multivector $M$. _Hint_: You know how to solve the scalar equation
$10 x + 2 = 4$.

__Solution__. Subtracting $3 \mathbf{e}_1 + 4 \mathbf{e}_2$ from both sides
of the equation, we obtain

$$
(3 \mathbf{e}_1 + 4 \mathbf{e}_2) M = 2 \mathbf{e}_1 + 3 \mathbf{e}_2
$$

Multiplying both sides of this equation by

$$
  (3 \mathbf{e}_1 + 4 \mathbf{e}_2)^{-1} =
  \frac{1}{25} (3 \mathbf{e}_1 + 4 \mathbf{e}_2)
$$

yields

$$
\begin{align}
M
&= \frac{1}{25} (3 \mathbf{e}_1 + 4 \mathbf{e}_2)
                (2 \mathbf{e}_1 + 3 \mathbf{e}_2) \\
&= \frac{1}{25} (  6 \mathbf{e}_1 \mathbf{e}_1
                +  9 \mathbf{e}_1 \mathbf{e}_2
                +  8 \mathbf{e}_2 \mathbf{e}_1
                + 12 \mathbf{e}_2 \mathbf{e}_2) \\
&= \frac{1}{25} (  18
                +  9 \mathbf{e}_1 \mathbf{e}_2
                -  8 \mathbf{e}_1 \mathbf{e}_2) \\
&= \frac{1}{25} (  18 + \mathbf{e}_1 \wedge \mathbf{e}_2 ) \\
&= \frac{18}{25} + \frac{1}{25} (\mathbf{e}_1 \wedge \mathbf{e}_2)
\end{align}
$$

--------------------------------------------------------------------------------------------
