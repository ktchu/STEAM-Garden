Linear and Geometric Algebra (Macdonald): Problems 7.1
======================================================

--------------------------------------------------------------------------------------------
## 0. Notation

* $\newcommand{\R}{\mathbb{R}}$
  The set of real numbers: $\R$

* $\newcommand{\kpart}[2]{\left\langle{#1}\right\rangle_{#2}}$
  $k$-vector part of multivector $M$: $\kpart{M}{k}$

* $\newcommand{\norm}[1]{\left\vert{#1}\right\vert}$
  Norm of multivector $M$: $\norm{M}$

* $\newcommand{\B}[1]{\mathbf{#1}}$
  A blade $A$: $\B{A}$

* $\newcommand{\I}{\B{I}}$
  The pseudoscalar for the geometric algebra: $\I$

* $\newcommand{\proj}[2]{P_{\B{#1}} \left(\B{#2}\right)}$
  The projection of blade $\B{A}$ onto the subspace represented by blade $\B{B}$:
  $\proj{B}{A}$

--------------------------------------------------------------------------------------------
### 7.1.8.

__Problem__. Show that the angle between two subspaces of equal dimension is equal to the
angle between their orthogonal complements. For example, the angle between two planes of
$\R^3$ is equal to the angle between lines orthogonal to the planes. Can you picture this?

__Solution__. Let $\B{A}$ and $\B{B}$ be blades representing subspaces of equal
dimension. Then they have the same grade, so

$$
\B{A} \cdot \B{B} = \kpart{\B{A} \B{B}}{0}.
$$

Observing that

$$
\B{A} \B{B}
= \B{A} \left( \I^{-1} \I \right) \B{B}
= \left( \B{A} \I^{-1} \right) \left( \I \B{B} \right)
= \pm \left( \B{A} \I^{-1} \right) \left( \B{B} \I^{-1} \right)
= \pm \B{A}^* \B{B}^*,
$$

we can conclude that

$$
\B{A} \cdot \B{B}
= \kpart{\B{A} \B{B}}{0}
= \kpart{\B{A}^* \B{B}^*}{0}
= \B{A}^* \cdot \B{B}^*.
$$

Therefore, since the norm of a blade and its orthogonal complement are equal,

$$
\frac{\B{A} \cdot \B{B}}{\norm{\B{A}} \norm{\B{B}}}
= \frac{\B{A}^* \cdot \B{B}^*}{\norm{\B{A}^*} \norm{\B{B}^*}},
$$

which equivalent to the desired result.

--------------------------------------------------------------------------------------------
