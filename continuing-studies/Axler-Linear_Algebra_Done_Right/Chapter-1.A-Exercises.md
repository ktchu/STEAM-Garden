Linear Algebra Done Right (S. Axler): Exercises 1.A
===================================================

-------------------------------------------------------------------------------
### 1.

__Problem__. Suppose $a$ and $b$ are real numbers, not both 0. Find real
numbers $c$ and $d$ such that

$$
1 / (a + bi) = c + di
$$

__Solution__. Note that $(a + bi) (a - bi) = a^2 + b+2$. Dividing through by
$(a + bi) (a^2 + b^2)$ yields

$$
\frac{1}{a + bi}
= \frac{a - bi}{a^2 + b^2}
= \frac{a}{a^2 + b^2} - \frac{b}{a^2 + b^2}.
$$

Therefore,

$$
c = \frac{a}{a^2 + b^2} \\
d = \frac{-b}{a^2 + b^2}
$$

-------------------------------------------------------------------------------
### 2.

__Problem__. Show that

$$
\frac{-1 + \sqrt{3} i}{2}
$$

is a cube root of 1.

__Solution__.

$$
\begin{align}
\left( \frac{-1 + \sqrt{3} i}{2} \right)^3
&= \left( \frac{-1 + \sqrt{3} i}{2} \right)^2
   \left( \frac{-1 + \sqrt{3} i}{2} \right) \\
&= \left( \frac{-2 - 2\sqrt{3} i}{4} \right)
   \left( \frac{-1 + \sqrt{3} i}{2} \right) \\
&= \left( \frac{-1 - \sqrt{3} i}{2} \right)
   \left( \frac{-1 + \sqrt{3} i}{2} \right) \\
&= \frac{1 + 3}{4} = 1
\end{align}
$$

-------------------------------------------------------------------------------
### 3.

__Problem__. Find two distinct square roots of $i$.

__Solution__. Suppose $(a + bi)^2 = i$. Then

$$
a^2 - b^2 + 2 a b i = i.
$$

Therefore, $a^2 = b^2$ and $ab = 1/2$. The first relation implies that
$|a| = |b|$ so that combined with the second relation, we see that
$|a| = |b| = 1 / \sqrt{2}$. The second relation also implies that $a$ and $b$
have the same sign. Putting all of these results together, the two square
roots of $i$ are $\frac{1 + i}{\sqrt{2}}$ and $\frac{-1 - i}{\sqrt{2}}$.

-------------------------------------------------------------------------------
### 4.

__Problem__. Show that $\alpha + \beta = \beta + \alpha$ for all
$\alpha, \beta \in \mathbb{C}$.

__Solution__. Let $\alpha = a_r + a_i i$ and $\beta = b_r + b_i i$. Then the
following sequence of equalities proves the result:

$$
\alpha + \beta
= (a_r + a_i i) + (b_r + b_i i) \\
= (a_r + b_r) + (a_i + b_i) i \\
= (b_r + a_r) + (b_i + a_i) i \\
= (b_r + b_i i) + (a_r + a_i i)
= \beta + \alpha
$$

In the above sequence of equalities, the definition of addition of complex
numbers justifies the second and fourth equalities and the commutativity of
addition justifies the third equality.

-------------------------------------------------------------------------------
### 5.

__Problem__. Show that

$$
(\alpha + \beta) + \lambda = \alpha + (\beta + \lambda)
$$

for all $\alpha, \beta, \lambda \in \mathbb{C}$.

__Solution__. The proof is analogous to the proof for Problem #4.

-------------------------------------------------------------------------------
### 6.

__Problem__. Show that

$$
(\alpha \beta) \lambda = \alpha (\beta \lambda)
$$

for all $\alpha, \beta, \lambda \in \mathbb{C}$.

__Solution__. The proof is analogous to the proof for Problem #4.

-------------------------------------------------------------------------------
### 7.

__Problem__. Show that for every $\alpha \in \mathbb{C}$, there exists a
unique $\beta \in \mathbb{C}$ such that $\alpha + \beta = 0$.

__Solution__. Suppose that $\beta_1$ and $\beta_2$ are inverses of $\alpha$.
Since $\beta_1$ is an inverse of $\alpha$,

$$
0 = \alpha + \beta_1
$$

Adding $\beta_2$ to both sides, we find that

$$
\beta_2 = (\alpha + \beta_1) + \beta_2 = (\alpha + \beta_2) + \beta_1
= \beta_1
$$

where the last equality follows because $\beta_2$ is an inverse of $\alpha$.
Therefore, $\beta_1 = \beta_2$, so $\alpha$ has a unique inverse.

-------------------------------------------------------------------------------
### 8.

__Problem__. Show that for every $\alpha \in \mathbb{C}$ with $\alpha \ne 0$,
there exists a unique $\beta \in \mathbb{C}$ such that $\alpha \beta = 1$.

__Solution__. The proof is analogous to the proof for Problem #7.

-------------------------------------------------------------------------------
### 9.

__Problem__. Show that

$$
\lambda (\alpha + \beta) = \lambda \alpha + \lambda \beta
$$

for all $\lambda, \alpha, \beta \in \mathbb{C}$.

__Solution__. Let $\alpha = a_r + a_i i$, $\beta = b_r + b_i i$, and
$\lambda = c_r + c_i i$. Then the following sequence of equalities proves the
result:

$$
\begin{align}
\lambda (\alpha + \beta)
&= (c_r + c_i i) [(a_r + a_i i) + (b_r + b_i i)] \\
&= (c_r + c_i i) [(a_r + b_r) + (a_i + b_i) i] \\
&= [c_r (a_r + b_r) - c_i (a_i + b_i)] +
   [c_r (a_i + b_i) + c_i (a_r + b_r)] i \\
&= [(c_r a_r - c_i a_i) + (c_r a_i + c_i a_r) i] +
   [(c_r b_r - c_i b_i) + (c_r b_i + c_i b_r) i] \\
&= (c_r + c_i i) (a_r + a_i i) + (c_r + c_i i) (b_r + b_i i) \\
&= \lambda \alpha + \lambda \beta
\end{align}
$$

In the above sequence of equalities, the definition of addition of complex
numbers justifies the second and fourth equalities and the definition of
multiplication justifies the third and fifth equalities.

-------------------------------------------------------------------------------
### 10.

__Problem__. Find $x \in \mathbb{R}^4$ such that

$$
(4, -3, 1, 7) + 2 x = (5, 9, -6, 8).
$$

__Solution__. Using the definition of addition for vectors, the above equation
can be expressed as

$$
(4 + 2 x_1, -3 + 2 x_2, 1 + 2 x_3, 7 + 2 x_4) = (5, 9, -6, 8).
$$

Solving for $x_1$, $x_2$, $x_3$, and $x_4$, we find that
$x = (1/2, 6, -7/2, 1/2)$.

-------------------------------------------------------------------------------
### 11.

__Problem__. Explain why there does not exist $\lambda \in \mathbb{C}$ such
that

$$
\lambda (2 - 3i, 5 + 4i, -6 + 7i) = (12 - 5i, 7 + 22i, -32 - 9i).
$$

__Solution__. Using the definition of scalar multiplication, the above equation
can be expressed as

$$
(\lambda (2 - 3i), \lambda (5 + 4i), \lambda (-6 + 7i)
= (12 - 5i, 7 + 22i, -32 - 9i).
$$

Using the first list item to solve for $\lambda$ yields
$\lambda = (12 - 5i) / (2 - 3i)$. We need to check that this value of
$\lambda$ satisfies the equations for the second and third list items.
The equation for the second list item is satisfied:

$$
\lambda (5 + 4i) = (12 - 5i) (5 + 4i) / (2 - 3i) = 7 + 22 i
$$

Unfortunately, the equation for the third list item is _not_ satisfied

$$
\lambda (-6 + 7i) = (12 - 5i) (-6 + 7i) / (2 - 3i) = -32 + 9 i
\ne -32 - 9 i
$$

-------------------------------------------------------------------------------
### 12.

__Problem__. Show that $(x + y) + z = x + (y + z)$ for all
$x, y, z \in \mathbb{F}^n$.

__Solution__. Let $x = (x_1, x_2, \ldots, x_n)$, $y = (y_1, y_2, \ldots, y_n)$,
and $z = (z_1, z_2, \ldots, z_n)$. Then the following sequence of equalities
proves the result:

$$
\begin{align}
(x + y) + z
&= ((x_1 + y_1) + z_1, (x_2 + y_2) + z_2, \ldots, (x_n + y_n) + z_n) \\
&= (x_1 + (y_1 + z_1), x_2 + (y_2 + z_2), \ldots, x_n + (y_n + z_n)) \\
&= x + (y + z).
\end{align}
$$

In the above sequence of equalities, the definition of vector addition numbers
justifies the first and last equalities, and the associative law for addition
of scalars justifies the second equality.

-------------------------------------------------------------------------------
### 13.

__Problem__. Show that $(ab) x = a (bx)$ for all $x \in \mathbb{F}^n$ and
$a, b \in \mathbb{F}$.

__Solution__. The proof is analogous to the proof for Problem #12.

-------------------------------------------------------------------------------
### 14.

__Problem__. Show that $1x = x$ for all $x \in \mathbb{F}^n$.

__Solution__. Let $x = (x_1, x_2, \ldots, x_n)$. Then the following sequence
of equalities proves the result:

$$
1x = (1(x_1), 1(x_2), \ldots, 1(x_n))
= (x_1, x_2, \ldots, x_n)
x.
$$

In the above sequence of equalities, the definition of scalar multiplication
in $\mathbb{F}^n$ justifies the first and last equalities, and the definition
of the identity in $\mathbb{F}$ justifies the second equality.

-------------------------------------------------------------------------------
### 15.

__Problem__. Show that $\lambda (x + y) = \lambda x + \lambda y$ for all
$\lambda \in \mathbb{F}$ and $x, y \in \mathbb{F}^n$.

__Solution__. The proof is analogous to the proof for Problem #12.

-------------------------------------------------------------------------------
### 16.

__Problem__. Show that $(a + b) x = a x + b x$ for all $a, b \in \mathbb{F}$
and $x \in \mathbb{F}^n$.

__Solution__. The proof is analogous to the proof for Problem #12.

-------------------------------------------------------------------------------
