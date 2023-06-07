Introduction to Crystallography (D. Sands): Chapter 1 Exercises
===============================================================

--------------------------------------------------------------------------------------------
### Notation


* $\newcommand{\R}[0]{\mathbb{R}}$
  The set of real numbers: $\R$

* $\newcommand{\vec}[1]{\mathbf{#1}}$
  A vector: $\vec{v}$

* $\newcommand{\e}{\vec{e}}$
  The $i$-th standard basis vector: $\e_i$

* $\newcommand{\a}{\vec{a}}$ $\newcommand{\b}{\vec{b}}$ $\newcommand{\c}{\vec{c}}$
  The basis vectors for the lattice defined by a unit cell: $\a, \b, \c$

--------------------------------------------------------------------------------------------
### 1.

__Problem__. TODO

__Solution__. TODO

--------------------------------------------------------------------------------------------
## Additional Exercises

--------------------------------------------------------------------------------------------
### A.1-3.1.

__Problem__. Show that the lattice angles $\alpha$, $\beta$, and $\gamma$ can always be
chosen so that $0 < \alpha, \beta, \gamma \le \pi/2$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### A.1-5.1.

__Problem__. Let $\a, \b, \c$ be basis vectors for the lattice defined by a unit cell.
Express the unit cell basis vectors in terms of the standard basis $\e_1, \e_2, \e_3$ for
$\R^3$ and the lattice constants $a$, $b$, $c$, $\alpha$, $\beta$, and $\gamma$.

__Solution__. We choose the unit cell basis vectors for computational convenience.

* Letting $\a$ be parallel to $\e_1$ (with the same orientation) implies that $\a = a \e_1$.

* Letting $\b$ lie in the plane defined by $\e_1, \e_2$ (so that the orientation of
  $(\a, \b)$ and $(\e_1, \e_2)$ are the same) yields

  $$
  \b = (b \cos\gamma) \e_1 + (b \sin\gamma) \e_2
  $$

To express $\c$ in terms of the standard basis, we use constraints imposed by the length
of $\c$ and the definitions $\alpha$ and $\beta$ to solve for $x$, $y$, and $z$ in the
following expression:

$$
\c = x \e_1 + y \e_2 + z \e_3.
$$

* $\a \cdot \c = ac \cos\beta$ implies that $x = c \cos\beta$.

* $\b \cdot \c = bc \cos\alpha$ implies that

  $$
  bc \cos\alpha = xb \cos\gamma + by \sin\gamma.
  $$

  Solving for $y$, we find that

  $$
  y = \frac{c}{\sin\gamma} ( \cos\alpha - \cos\beta \cos\gamma ).
  $$

* $\Vert \c \Vert_2^2 = c^2$ implies that

  $$
  c^2
  = c^2 \cos^2 \beta
    + \frac{c^2}{\sin^2 \gamma} ( \cos\alpha - \cos\beta \cos\gamma )^2
    + z^2.
  $$

  Rearranging, we find that

  $$
  \begin{align}
  z^2
  &=  c^2
      \left[
        1 - \cos^2 \beta
        - \frac{1}{\sin^2 \gamma}
          \left(
            \cos^2 \alpha - 2 \cos\alpha \cos\beta \cos\gamma + \cos^2 \beta \cos^2 \gamma
          \right)
      \right] \\
  &=  \frac{c^2}{\sin^2 \gamma}
      \left[
        \sin^2 \gamma - \cos^2 \beta \sin^2 \gamma
        - \cos^2 \alpha + 2 \cos\alpha \cos\beta \cos\gamma - \cos^2 \beta \cos^2 \gamma
      \right] \\
  &=  \frac{c^2}{\sin^2 \gamma}
      \left[
        1 - \cos^2 \alpha - \cos^2 \beta - \cos^2 \gamma
        + 2 \cos\alpha \cos\beta \cos\gamma
      \right].
  \end{align}
  $$

Summarizing these results, we have

$$
\begin{align}
\a &= a \e_1 \\
\b &= (b \cos\gamma) \e_1 + (b \sin\gamma) \e_2 \\
\c &= (c \cos\gamma) \e_1
    + \left( \frac{c}{\sin\gamma} (\cos\alpha - \cos\beta \cos\gamma) \right) \e_2
    + \left[\frac{c}{\sin\gamma}
      (
        1 - \cos^2 \alpha - \cos^2 \beta - \cos^2 \gamma + 2 \cos\alpha \cos\beta \cos\gamma
      )^{1/2}
      \right] \e_3.
\end{align}
$$

--------------------------------------------------------------------------------------------
### A.1-5.2.

__Problem__. Derive the folllowing formula for the volume of a general unit cell defined by
the lattice constants $a$, $b$, $c$, $\alpha$, $\beta$, and $\gamma$.

$$
V = abc
    \left(
      1 - \cos^2 \alpha - \cos^2 \beta - \cos^2 \gamma
      + 2 \cos\alpha \cos\beta \cos\gamma
    \right)^{1/2}
$$

__Solution__. Let $\a, \b, \c$ be basis vectors that define the unit cell.

_Geometric Algebra Derivation_. The volume of the parallelipiped defined by $\a, \b, \c$
is equal to $V = \vert \a \wedge \b \wedge \c \vert$. Using the expressions for the
unit cell basis vectors from Problem A.1-5.2 and observing that only one term in the outer
product survives, we find that

$$
\begin{align}
V
&=  \left\vert
      a \left( b \sin\gamma \right)
      \left[\frac{c}{\sin\gamma}
        \left(
          1 - \cos^2 \alpha - \cos^2 \beta - \cos^2 \gamma
          + 2 \cos\alpha \cos\beta \cos\gamma
        \right)^{1/2}
      \right]
      (\e_1 \wedge \e_2 \wedge \e_3)
    \right\vert \\
&=  abc
    \left(
      1 - \cos^2 \alpha - \cos^2 \beta - \cos^2 \gamma
      + 2 \cos\alpha \cos\beta \cos\gamma
    \right)^{1/2}.
\end{align}
$$

_Linear Algebra Derivation_. The volume of the parallelipiped defined by $\a, \b, \c$
is equal to the triple scalar product of $\a, \b, \c$:
$V = \vert \a \cdot (\b \times \c) \vert$. When $\a, \b, \c$ are represented in an
orthonormal basis, the triple scalar product may be expressed as a determinant

$$
\a \cdot (\b \times \c)
= \det\left(
    \begin{array}{c}
      \a \\\hline
      \b \\\hline
      \c \\
    \end{array}
  \right),
$$

where each basis vector is a row in the matrix. Using the expressions for the unit cell
basis vectors from Problem A.1-5.2, we find that the volume is equal to the absolute value
of the determinant of a lower triangular matrix:

$$
\begin{align}
V
&=  \left\vert
      \begin{array}{ccc}
      a & 0 & 0 \\
      b \cos\gamma & b \sin\gamma & 0 \\
      c \cos\beta & \frac{c}{\sin\gamma}(\cos\alpha - \cos\beta \cos\gamma)
      & \left[\frac{c}{\sin\gamma}
          \left(
            1 - \cos^2 \alpha - \cos^2 \beta - \cos^2 \gamma
            + 2 \cos\alpha \cos\beta \cos\gamma
          \right)^{1/2}
        \right]
      \end{array}
    \right\vert \\
&=  abc
    \left(
      1 - \cos^2 \alpha - \cos^2 \beta - \cos^2 \gamma
      + 2 \cos\alpha \cos\beta \cos\gamma
    \right)^{1/2},
\end{align}
$$

where the last line follows from fact that the determinant of a triangular matrix is the
product of the diagonal elements.

--------------------------------------------------------------------------------------------
### A.1-5.3.

__Problem__. Derive the formula for the distance between two points $p_1 = (x_1, y_1, z_1)$
and $p_2 = (x_2, y_2, z_2)$.

$$
l = \left[
  \begin{array}{l}
    (x_1 - x_2)^2 a^2 + (y_1 - y_2)^2 b^2 + (z_1 - z_2)^2 c^2 \\
    +\ 2 (x_1 - x_2) (y_1 - y_2) ab \cos\gamma
    + 2 (y_1 - y_2) (z_1 - z_2) bc \cos\alpha
    + 2 (z_1 - z_2) (x_1 - x_2) ca \cos\beta
  \end{array}
\right]^{1/2}
$$

__Solution__. Using the expressions for the unit cell basis vectors from Problem A.1-5.2,
the difference between the points $p_1$ and $p_2$ in terms of the standard basis is:

$$
\begin{align}
p_1 - p_2
&=  [
      (x_1 - x_2) a
      + (y_1 - y_2) b \cos\gamma
      + (z_1 - z_2) c \cos\gamma
    ] \ \e1 \\
&+  [
      (y_1 - y_2) b \sin\gamma
      + (z_1 - z_2) \frac{c}{\sin\gamma} (\cos\alpha - \cos\beta \cos\gamma)
    ] \ \e2 \\
&+  \frac{(z_1 - z_2) c}{\sin\gamma}
    (
      1 - \cos^2 \alpha - \cos^2 \beta - \cos^2 \gamma + 2 \cos\alpha \cos\beta \cos\gamma
    )^{1/2}
    \ \e3
\end{align}
$$

Using the Pythagorean theorem, we can compute the square of the distance between $p_1$ and
$p_2$:

$$
\begin{align}
l^2
&=  \left[\begin{array}{l}
      (x_1 - x_2)^2 a^2
      + (y_1 - y_2)^2 b^2 \cos^2 \gamma
      + (z_1 - z_2)^2 c^2 \cos^2 \beta \\
      +\ 2 (x_1 - x_2) (y_1 - y_2) ab \cos\gamma
      + 2 (y_1 - y_2) (z_1 - z_2) bc \cos\beta \cos\gamma
      + 2 (z_1 - z_2) (x_1 - x_2) ca \cos\beta
    \end{array}\right] \\
&+  \left[\begin{array}{l}
      (y_1 - y_2)^2 b^2 \sin^2 \gamma
      + \frac{(z_1 - z_2)^2 c^2}{\sin^2 \gamma}
        (\cos^2 \alpha + \cos^2 \beta \cos^2 \gamma - 2 \cos\alpha \cos\beta \cos\gamma) \\
      +\ 2 (y_1 - y_2) (z_1 - z_2) bc (\cos\alpha - \cos\beta \cos\gamma)
    \end{array}\right] \\
&+  \left[
      \frac{(z_1 - z_2)^2 c^2}{\sin^2 \gamma}
      (1 - \cos^2 \alpha - \cos^2 \beta - \cos^2 \gamma + 2 \cos\alpha \cos\beta \cos\gamma)
    \right].
\end{align}
$$

After some algebraic manipulation and use of trignometric identities, the terms involving
$b^2$ and $c^2$ simplify to $(y_1 - y_2)^2 b^2$ and $(z_1 - z_2)^2 c^2$, respectively, and
the terms involving $bc \cos\beta \cos\gamma$ cancel out yielding the desired result:

$$
\begin{align}
l^2
&=  (x_1 - x_2)^2 a^2
    + (y_1 - y_2)^2 b^2
    + (z_1 - z_2)^2 c^2 \\
&+  2 (x_1 - x_2) (y_1 - y_2) ab \cos\gamma
    + 2 (y_1 - y_2) (z_1 - z_2) bc \cos\alpha
    + 2 (z_1 - z_2) (x_1 - x_2) ca \cos\beta.
\end{align}
$$

--------------------------------------------------------------------------------------------
