Linear Algebra Done Right (S. Axler): Exercises 1.B
===================================================

-------------------------------------------------------------------------------
### 1.

__Problem__. Prove that $-(-v) = v$ for every $v \in V$.

__Solution__. For every $v \in V$, $-v = (-1)v$. Therefore,

$$
-(-v) = (-1)(-v) = (-1)(-1)v = 1v = v.
$$

-------------------------------------------------------------------------------
### 2.

__Problem__. Suppose $a \in \mathbb{F}$, $v \in V$, and $av = 0$. Prove that
$a = 0$ or $v = 0$.

__Solution__. Clearly, $a = 0$ is one possibility of $av = 0$ because $0v = 0$.
If $a \ne 0$, then $a$ has a multiplicative inverse $a^{-1}$. Therefore

$$
v = 1v = (a^{-1} a) v = a^{-1} (av) = a^{-1} 0 = 0
$$

-------------------------------------------------------------------------------
### 3.

__Problem__. Suppose $v, w \in V$. Explain why there exists a unique $x \in V$
such that $v + 3x = w$.

__Solution__. Intuitively, there is a unique $x \in V$ satisfying $v + 3x = w$
because additive inverses are and multiplicative inverses of nonzero scalars
are unique, which implies that adding the additive inverse of $v$ followed by
multiplication by $1/3$ yields a unique value $x$ that satisfies the original
equation.

More formally, suppose that $x_1$ and $x_2$ both satisfy the equation
$v + 3x = w$. Then

$$
\begin{align}
v + 3 x_1 &= v + 3 x_2 \\
\Rightarrow 3 x_1 &= v + 3 x_1 - v1 = v + 3 x_2 - v = 3 x_2 \\
\Rightarrow x_1 &= (1/3) (3 x_1) = (1/3) (3 x_2) = x_2.
\end{align}
$$

-------------------------------------------------------------------------------
### 4.

__Problem__. The empty set is not a vector space. The empty set fails to
satisfy only one of the requirements listed in 1.19. Which one?

__Solution__. Any vector space much contain an additive identity $0$. Since
the empty set contains no elements, it lacks an additive identity. Therefore,
it is not a vector space.

-------------------------------------------------------------------------------
### 5.

__Problem__. Show that in the definition of a vector space (1.19), the additive
inverse condition can be replaced with the condition that $0v = 0$ for all
$v \in V$.

Here the $0$ on the left side is the number $0$, and the $0$ on the right side
is the additive identity of $V$. (The phrase "a condition can be replaced" in
a definition means that the collection of objects satisfying the definition is
unchanged if the original condition is replaced with the new definition.)

__Solution__. To show that we can replace the additive inverse condition with
the condition $0v = 0$ forall $v \in V$, we show that they are equivalent.

If we assume the additive inverse condition, then for every $0v \in V$ has
and inverse $w \in V$. Therefore,

$$
0v = 0v + 0 = 0v + (0v + w) = (0 + 0) v + w = 0v + w = 0
$$

If we assume that $0v = 0$, then every $v \in V$ has an inverse equal to
$(-1)v$ because

$$
v + (-1)v = 1v + (-1)v = (1 - 1)v = 0v = 0.
$$

-------------------------------------------------------------------------------
### 6.

__Problem__. Let $\infty$ and $-\infty$ denote two distinct objects, neither
of which is in $\mathbb{R}$. Define an addition and scalar multiplication on
$\mathbb{R} \cup \{\infty\} \cup \{-\infty\}$ as you could guess from the
notation. Specifically, the sum and product of two real numbers is as usual,
and for $t \in \mathbb{R}$ define

$$
TODO
$$

Is $\mathbb{R} \cup \{\infty\} \cup \{-\infty\}$ a vector space over
$\mathbb{R}$? Explain.

__Solution__. TODO

-------------------------------------------------------------------------------
