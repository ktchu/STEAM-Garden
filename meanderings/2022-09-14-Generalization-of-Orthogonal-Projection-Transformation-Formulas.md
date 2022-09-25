---
tags: geometric-algebra, linear-algebra
---

--------------------------------------------------------------------------------------------

2022-09-14: Generalizations of Orthogonal Projection Transformation Formulas
============================================================================

_Author(s)_: Kevin Chu `<kevin@velexi.com>`

_Last Updated_: 2022-09-25

--------------------------------------------------------------------------------------------
## Notation

__Linear and Geometry Algebra__

* $\newcommand{\R}{\mathbb{R}}$
  $\newcommand{\e}{\mathbf{e}}$
  The standard basis for $\R^n$: $\{ \e_1, \ldots, \e_n \}$

* $\newcommand{\B}[1]{\mathbf{#1}}$
  A blade: $\B{B}$ (uppercase, boldface)

* $\newcommand{\dual}[1]{{#1}^\perp}$
  The orthogonal complement (i.e., dual) of blade $\B{B}$: $\dual{\B{B}}$

* $\newcommand{\norm}[1]{\vert{#1}\vert}$
  The norm of multivector $M$: $\norm{M}$

* $\newcommand{\proj}[2]{P_{#1}\left({#2}\right)}$
  The orthogonal projection of blade $\B{A}$ onto the subspace represented by $\B{B}$:
  $\proj{\B{B}}{\B{A}}$

* $\newcommand{\rej}[2]{R_{#1}\left({#2}\right)}$
  The orthogonal rejection of vector $\B{v}$ from the subspace represented by $\B{B}$:
  $\rej{\B{B}}{\B{v}} = \B{v} - \proj{\B{B}}{\B{v}}$

  ___Note___: this definition _only holds for vectors_. It does not apply to higher-grade
  blades.

* The $i$-th component of vector $\B{v}$ with respect to the standard basis:
  $v_i$ (lowercase, lightface)

* $\newcommand{\E}{\B{E}}$
  The blade formed by the standard basis vectors $\e_i$ with indices in $S$:
  $\E_S = \bigwedge_{k \in S} \e_k$

__Miscellaneous__

* $\newcommand{\abs}[1]{\vert{#1}\vert}$
  The absolute value of $x$: $\abs{x}$

* $\newcommand{\card}[1]{\vert{#1}\vert}$
  The cardinality of set $S$: $\card{S}$

--------------------------------------------------------------------------------------------
## Summary

In two dimensions, the coordinates of a vector represented in two different orthonormal
bases are related by the simple transformation formula

$$
\left[\begin{array}{c}
v_1 \\
v_2 \\
\end{array}\right]
=
\left[\begin{array}{cc}
\cos \theta  & \sin \theta \\
-\sin \theta & \cos \theta \\
\end{array}\right]
\left[\begin{array}{c}
u_1 \\
u_2 \\
\end{array}\right]
$$

where $\theta$ is the angle between the orthonormal bases.

In higher dimensions, we have a similar linear transformation between the decomposition of
a vector over $(U, U^\perp)$ and its decomposition over $(V, V^\perp)$, where $U$ and $V$
are subspaces having the same dimension and $U^\perp$ and $V\perp$ are their respective
orthogonal complements. The simple transformation in two dimensions generalizes to

$$
\begin{align}
\proj{\B{V}}{\B{x}}
&= \proj{\B{V}}{\proj{\B{U}}{\B{x}}}
 + \proj{\B{V}}{\proj{\dual{\B{U}}}{\B{x}}} \\

\proj{\dual{\B{V}}}{\B{x}}
&= \proj{\dual{\B{V}}}{\proj{\B{U}}{\B{x}}}
 + \proj{\dual{\B{V}}}{\proj{\dual{\B{U}}}{\B{x}}}
\end{align}
$$

where $\B{U}$ and $\B{V}$ are blades representing the subspaces $U$ and $V$, respectively,
and $\B{x}$ is an arbitrary vector. While the transformation retains its simple linear form,
the simple equations relating the magnitudes of the projections onto $U$ and $V$ to the
angle $\theta$ between $U$ and $V$ is lost.

When $U$ and $V$ have the same dimension, we do, however, still have
_simple inequality relationships_ between the magnitudes of the projections and
$\theta$:

$$
\left[\begin{array}{cc}
    \cos \theta & -1          \\
    -1          & \cos \theta \\
\end{array}\right]
\left[\begin{array}{c}
  \norm{\proj{\B{U}}{\B{x}}} \\
  \norm{\proj{\dual{\B{U}}}{\B{x}}}
\end{array}\right]

\le \left[\begin{array}{c}
      \norm{\proj{\B{V}}{\B{x}}} \\
      \norm{\proj{\dual{\B{V}}}{\B{x}}}
    \end{array}\right]

\le \left[\begin{array}{cc}
      1           & \sin \theta \\
      \sin \theta & 1           \\
    \end{array}\right]
    \left[\begin{array}{c}
      \norm{\proj{\B{U}}{\B{x}}} \\
      \norm{\proj{\dual{\B{U}}}{\B{x}}}
    \end{array}\right]
$$

where the matrix inequalities are element-wise.

### Application

Given

* $\e_i$ with $1 \le i \le n$,

* $\E_S$ with $S$ a subset of $\{ 1, \ldots, n \}$ not containing $i$, and

* a blade $\B{V}$ representing a subspace of dimension $\card{S}$,

the magnitude of the rejection of a vector $\B{u}$ from $\B{V}$ is bounded in terms of

* $\abs{u_i}$ (the magnitude of the projection of $\B{u}$ onto $\e_i$),

* the angle $\phi$ between $\B{u}$ and $\e_i$, and

* the angle $\theta_S$ betweeen $\B{V}$ and $\E_S$:

$$
\left( 1  - \frac{\sin \theta_S}{\cos \phi} \right)
\le \frac{\norm{\rej{\B{V}}{\B{u}}}}{\abs{u_i}}
\le \frac{1}{\cos \phi}.
$$

Note that this result holds for arbitrary orthonormal bases by defining $u_i$ with respect
to the relevant orthonormal basis instead of the standard basis.

--------------------------------------------------------------------------------------------
## Propositions

### Lemma 1. Linear Transformation Formula

Let $\B{U}$ and $\B{V}$ be blades that represent subspaces with the same dimension. If
$\B{x}$ is a vector, then the projections of $\B{x}$ onto $\B{V}$ and $\dual{\B{V}}$ can
be expressed as a linear transformation the projections of $\B{x}$ onto $\B{U}$ and
$\dual{\B{U}}$:

$$
\proj{\B{V}}{\B{x}}
= \proj{\B{V}}{\proj{\B{U}}{\B{x}}} + \proj{\B{V}}{\proj{\dual{\B{U}}}{\B{x}}}
$$

$$
\proj{\dual{\B{V}}}{\B{x}}
= \proj{\dual{\B{V}}}{\proj{\B{U}}{\B{x}}} + \proj{\dual{\B{V}}}{\proj{\dual{\B{U}}}{\B{x}}}
$$

which can be expressed as the block matrix equation:

$$
\left[\begin{array}{c}
  \proj{\B{V}}{\B{x}} \\
  \proj{\dual{\B{V}}}{\B{x}}
\end{array}\right]
= \left[\begin{array}{cc}
    P_{\B{V}}        & P_{\B{V}} \\
    P_{\dual{\B{V}}} & P_{\dual{\B{V}}} \\
\end{array}\right]
\left[\begin{array}{c}
  \proj{\B{U}}{\B{x}} \\
  \proj{\dual{\B{U}}}{\B{x}}
\end{array}\right].
$$

_Proof_. Since $\B{x}$ is a vector, it can be decomposed as a sum of its projection and
rejection from any subspace. In particular, it can be expressed as

$$
\B{x} = \proj{\B{U}}{\B{x}} + \proj{\dual{\B{U}}}{\B{x}}.
$$

Projecting both sides of this equation onto $\B{V}$ leads to the equation for
$\proj{\B{V}}{\B{x}}$

$$
\proj{\B{V}}{\B{x}}
= \proj{\B{V}}{\proj{\B{U}}{\B{x}}}
  + \proj{\B{V}}{\proj{\dual{\B{U}}}{\B{x}}}.
$$

Similiarly, projecting $\B{x}$ onto $\dual{\B{V}}$ yields the second equation:

$$
\proj{\dual{\B{V}}}{\B{x}}
= \proj{\dual{\B{V}}}{\proj{\B{U}}{\B{x}}}
  + \proj{\dual{\B{V}}}{\proj{\dual{\B{U}}}{\B{x}}}.
$$

### Proposition 2. Upper Bounds on Orthogonal Projections

Let $\B{U}$ and $\B{V}$ be blades that represent subspaces of the same dimension and
let $\theta$ be the angle between $\B{U}$ and $\B{V}$. Then

$$
\norm{\proj{\B{V}}{\B{x}}}
\le \norm{\proj{\B{U}}{\B{x}}} + \sin \theta \norm{\proj{\dual{\B{U}}}{\B{x}}}
$$

$$
\norm{\proj{\dual{\B{V}}}{\B{x}}}
\le \sin \theta \norm{\proj{\B{U}}{\B{x}}} + \norm{\proj{\dual{\B{U}}}{\B{x}}}
$$

which can be expressed in matrix form as

$$
\left[\begin{array}{c}
  \norm{\proj{\B{V}}{\B{x}}} \\
  \norm{\proj{\dual{\B{V}}}{\B{x}}}
\end{array}\right]
\le \left[\begin{array}{cc}
    1           & \sin \theta \\
    \sin \theta & 1           \\
\end{array}\right]
\left[\begin{array}{c}
  \norm{\proj{\B{U}}{\B{x}}} \\
  \norm{\proj{\dual{\B{U}}}{\B{x}}}
\end{array}\right].
$$

_Proof_. Using triangle's inequality, the transformation equations from Lemma 1 imply that

$$
\norm{\proj{\B{V}}{\B{x}}}
\le \norm{\proj{\B{V}}{\proj{\B{U}}{\B{x}}}}
    + \norm{\proj{\B{V}}{\proj{\dual{\B{U}}}{\B{x}}}}
$$

$$
\norm{\proj{\dual{\B{V}}}{\B{x}}}
\le \norm{\proj{\dual{\B{V}}}{\proj{\B{U}}{\B{x}}}}
    + \norm{\proj{\dual{\B{V}}}{\proj{\dual{\B{U}}}{\B{x}}}}.
$$

Since projection can only decrease the length of a vector,
$\norm{\proj{\B{V}}{\proj{\B{U}}{\B{x}}}} \le \norm{\proj{\B{U}}{\B{x}}}$ and
$\norm{\proj{\dual{\B{V}}}{\proj{\dual{\B{U}}}{\B{x}}}}
\le \norm{\proj{\dual{\B{U}}}{\B{x}}}$, so

$$
\norm{\proj{\B{V}}{\B{x}}}
\le \norm{\proj{\B{U}}{\B{x}}} + \norm{\proj{\B{V}}{\proj{\dual{\B{U}}}{\B{x}}}}
$$

$$
\norm{\proj{\dual{\B{V}}}{\B{x}}}
\le \norm{\proj{\dual{\B{V}}}{\proj{\B{U}}{\B{x}}}} + \norm{\proj{\dual{\B{U}}}{\B{x}}}.
$$

Next, observe that

$$
\norm{\proj{\B{V}}{\proj{\dual{\B{U}}}{\B{x}}}}
\le \norm{\proj{\dual{\B{U}}}{\B{x}}} \sin \theta_{\dual{U}\dual{V}}
$$

$$
\norm{\proj{\dual{\B{V}}}{\proj{\B{U}}{\B{x}}}}
\le \norm{\proj{\B{U}}{\B{x}}} \sin \theta.
$$

from the bounds on the projections between blades [1]. Finally, incorporating these bounds
and recalling that $\theta = \theta_{\dual{U}\dual{V}}$ when the dimension of the
subspaces represented by $\B{U}$ and $\B{V}$ are equal, we arrive at the desired results:

$$
\norm{\proj{\B{V}}{\B{x}}}
\le \norm{\proj{\B{U}}{\B{x}}} + \sin \theta \norm{\proj{\dual{\B{U}}}{\B{x}}}
$$

$$
\norm{\proj{\dual{\B{V}}}{\B{x}}}
\le \sin \theta \norm{\proj{\B{U}}{\B{x}}} + \norm{\proj{\dual{\B{U}}}{\B{x}}}.
$$

### Proposition 3. Lower Bounds on Orthogonal Projections

Let $\B{U}$ and $\B{V}$ be blades that represent subspaces of the same dimension and
let $\theta$ be the angle between $\B{U}$ and $\B{V}$. Then

$$
\norm{\proj{\B{V}}{\B{x}}}
\ge \cos \theta \norm{\proj{\B{U}}{\B{x}}} - \norm{\proj{\dual{\B{U}}}{\B{x}}}
$$

$$
\norm{\proj{\dual{\B{V}}}{\B{x}}}
\ge -\norm{\proj{\B{U}}{\B{x}}} + \cos \theta \norm{\proj{\dual{\B{U}}}{\B{x}}}
$$

which can be expressed in matrix form as

$$
\left[\begin{array}{c}
  \norm{\proj{\B{V}}{\B{x}}} \\
  \norm{\proj{\dual{\B{V}}}{\B{x}}}
\end{array}\right]
\ge \left[\begin{array}{cc}
    \cos \theta & -1          \\
    -1          & \cos \theta \\
\end{array}\right]
\left[\begin{array}{c}
  \norm{\proj{\B{U}}{\B{x}}} \\
  \norm{\proj{\dual{\B{U}}}{\B{x}}}
\end{array}\right].
$$

_Proof_. Using the reverse triangle's inequality, the transformation equations from
Lemma 1 imply that

$$
\norm{\proj{\B{V}}{\B{x}}}
\ge \Bigl|
      \norm{\proj{\B{V}}{\proj{\B{U}}{\B{x}}}}
      - \norm{\proj{\B{V}}{\proj{\dual{\B{U}}}{\B{x}}}}
    \Bigr|
\ge \norm{\proj{\B{V}}{\proj{\B{U}}{\B{x}}}}
    - \norm{\proj{\B{V}}{\proj{\dual{\B{U}}}{\B{x}}}}
$$

$$
\norm{\proj{\dual{\B{V}}}{\B{x}}}
\ge \Bigl|
      \norm{\proj{\dual{\B{V}}}{\proj{\B{U}}{\B{x}}}}
      - \norm{\proj{\dual{\B{V}}}{\proj{\dual{\B{U}}}{\B{x}}}}
    \Bigr|
\ge \norm{\proj{\dual{\B{V}}}{\proj{\dual{\B{U}}}{\B{x}}}}
    - \norm{\proj{\dual{\B{V}}}{\proj{\B{U}}{\B{x}}}}.
$$

We continue by following a similar approach to the proof of Proposition 2.

* Projection can only decrease the length of a vector, so

  $$
  \norm{\proj{\B{V}}{\proj{\dual{\B{U}}}{\B{x}}}} \le \norm{\proj{\dual{\B{U}}}{\B{x}}}
  $$

  $$
  \norm{\proj{\dual{\B{V}}}{\proj{\B{U}}{\B{x}}}} \le \norm{\proj{\B{U}}{\B{x}}}.
  $$

* Lower bounds on projections between blades [1] imply

  $$
  \norm{\proj{\B{V}}{\proj{\B{U}}{\B{x}}}}
  \ge \norm{\proj{\B{U}}{\B{x}}} \cos \theta
  $$

  $$
  \norm{\proj{\dual{\B{V}}}{\proj{\dual{\B{U}}}{\B{x}}}}
  \ge \norm{\proj{\dual{\B{U}}}{\B{x}}} \cos \theta_{\dual{U}\dual{V}}.
  $$

Finally, combining these inequalities and recalling that
$\theta = \theta_{\dual{U}\dual{V}}$ (because the dimension of the subspaces
represented by $\B{U}$ and $\B{V}$ are equal), we arrive at the desired results:

$$
\norm{\proj{\B{V}}{\B{x}}}
\ge \cos \theta \norm{\proj{\B{U}}{\B{x}}} - \norm{\proj{\dual{\B{U}}}{\B{x}}}
$$

$$
\norm{\proj{\dual{\B{V}}}{\B{x}}}
\ge -\norm{\proj{\B{U}}{\B{x}}} + \cos \theta \norm{\proj{\dual{\B{U}}}{\B{x}}}.
$$

--------------------------------------------------------------------------------------------
## Application

### Proposition 4. $\left( 1  - \frac{\sin \theta_S}{\cos \phi} \right) \le \frac{\norm{\rej{\B{V}}{\B{u}}}}{\abs{u_i}} \le \frac{1}{\cos \phi}$ when $\B{u} \wedge \B{V} \ne 0$ and $\e_i \wedge \E_S \ne 0$

Let $S$ be a subset of $\{ 1, \ldots n \}$ not containing $i$, $\B{V}$ be a blade, and
$\B{u}$ be a vector. If $\B{u} \wedge \B{V} \ne 0$ (i.e., $\B{u}$ does not lie in the
subspace represented by $\B{V}$), then

$$
\left( 1  - \frac{\sin \theta_S}{\cos \phi} \right)
\le \frac{\norm{\rej{\B{V}}{\B{u}}}}{\abs{u_i}}
\le \frac{1}{\cos \phi}.
$$

where $\theta_S$ is the angle between $\B{V}$ and $\E_S$ and $\phi$ is the angle between
$\B{u}$ and $\e_i$.

_Proof_. The upper bound follows from the observation that
$\norm{\rej{\B{V}}{\B{u}}} \le \norm{\B{u}}$ and the definition of $\phi$:

$$
\frac{\norm{\rej{\B{V}}{\B{u}}}}{\abs{u_i}}
\le \frac{\norm{\B{u}}}{\abs{u_i}}
= \frac{1}{\cos \phi}.
$$

For the lower bound, consider decompositions of $\R^n$ into direct sums of orthogonal
subspaces: $\B{V} \oplus \dual{\B{V}}$ and $\E_S \oplus \dual{\E_S}$ [2,3]. Representing
$\B{u}$ in terms of these direct sums, we have

$$
\B{u} = \proj{\B{V}}{\B{v}} + \proj{\dual{\B{V}}}{\B{u}}
$$

and

$$
\B{u} = \proj{\B{\E_S}}{\B{u}} + \proj{\dual{\B{\E_S}}}{\B{u}}.
$$

Note that $\proj{\dual{\B{V}}}{\B{u}} \ne \B{0}$ because $\B{u} \wedge \B{V} \ne 0$ [3].

Using Proposition 2, we obtain the following upper bound on the magnitudes of the
projection of $\B{u}$ onto $\dual{\B{\E_S}}$:

$$
\norm{\proj{\dual{\B{\E_S}}}{\B{u}}}
\le \sin \theta_S \norm{\proj{\B{V}}{\B{u}}} + \norm{\proj{\dual{\B{V}}}{\B{u}}}.
$$

Rearranging this inequality, identifying $\proj{\dual{\B{V}}}{\B{u}}$ with
$\rej{\B{V}}{\B{u}}$, and observing that
$\norm{\proj{\B{V}}{\B{u}}} \le \norm{\B{u}}$ and
$\abs{u_i} \le \norm{\proj{\dual{\B{\E_S}}}{\B{u}}}$
yields the lower bound

$$
\begin{align}
\norm{\rej{\B{V}}{\B{u}}}
&\ge \abs{u_i} - \sin \theta_S \norm{\B{u}} \\
&= \abs{u_i} \left( 1  - \sin \theta_S \frac{\norm{\B{u}}}{\abs{u_i}} \right) \\
&= \abs{u_i} \left( 1  - \frac{\sin \theta_S}{\cos \phi} \right),
\end{align}
$$

which is equivalent to the desired result.

__Remark__. The geometric interpretation of Proposition 4 is that the magnitude of the
orthogonal projection of a vector $\B{u}$ onto any blade $\B{V}$ not containing $\B{u}$ is
constrained by how close (1) $\B{u}$ is to $\e_i$ and (2) $\B{V}$ is to $\E_S$. When $\phi$
and $\theta_S$ are both small, the magnitude of the rejection of $\B{u}$ from $\B{V}$ is
close to $\abs{u_i}$ (the magnitude of the projection of $\B{u}$ onto $\e_i$).

__Remark__. Proposition 4 holds for arbitrary orthonormal bases. For an arbitrary
orthonormal basis $\{\B{b}_1, \ldots, \B{b}_n\},$

* we transform the vector space using the orthogonal linear transformation that maps
  $\B{b}_i$ to $\e_i$ so that the orthonormal basis becomes the standard basis for $\R^n$

  and

* define vector components by $u_i = \B{u} \cdot \B{b}_i$ (instead of
  $u_i = \B{u} \cdot \e_i$).

--------------------------------------------------------------------------------------------
## References

1. [[2022-09-08-Bounds-on-Angles-and-Projections-Between-Blades]]

2. S. Axler. "Linear Algebra Done Right" (2015).

3. A. Macdonald. "Linear and Geometric Algebra" (2010).

--------------------------------------------------------------------------------------------
