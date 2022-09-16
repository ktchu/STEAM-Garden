---
tags: geometric-algebra, linear-algebra
---

--------------------------------------------------------------------------------------------

2022-09-14: Generalizations of Orthogonal Projection Transformation Formulas
----------------------------------------------------------------------------

_Author(s)_: Kevin Chu `<kevin@velexi.com>`

_Last Updated_: 2022-09-15

--------------------------------------------------------------------------------------------
### Notation

* $\newcommand{\B}[1]{\mathbf{#1}}$
  A blade: $\B{B}$ (uppercase, boldface)

* $\newcommand{\dual}[1]{#1^\perp}$
  The orthogonal complement (i.e., dual) of blade $\B{B}$: $\dual{\B{B}}$

* $\newcommand{\norm}[1]{\left\vert #1\right\vert}$
  The norm of multivector $M$: $\norm{M}$

* $\newcommand{\proj}[2]{P_{#1}\left(#2\right)}$
  The orthogonal projection of blade $\B{A}$ onto the subspace represented by $\B{B}$:
  $\proj{\B{B}}{\B{A}}$

--------------------------------------------------------------------------------------------
### Summary

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
orthogonal complements. The simple transformation in two dimensions generalizes to:

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

--------------------------------------------------------------------------------------------
### Propositions

#### Lemma 1: Linear Transformation Formula

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

which can be expressed as a block matrix equation:

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
= \proj{\B{V}}{\proj{\B{U}}{x}} + \proj{\B{V}}{\proj{\dual{\B{U}}}{x}}.
$$

Similiarly, projecting $\B{x}$ onto $\dual{\B{V}}$ yields the second equation:

$$
\proj{\dual{\B{V}}}{\B{x}}
= \proj{\dual{\B{V}}}{\proj{\B{U}}{x}} + \proj{\dual{\B{V}}}{\proj{\dual{\B{U}}}{x}}.
$$

#### Proposition 2: Upper Bounds on Orthogonal Projections

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

#### Proposition 3: Lower Bounds on Orthogonal Projections

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
### References

1. [[2022-09-08-Bounds-on-Angles-and-Projections-Between-Blades]]

--------------------------------------------------------------------------------------------
