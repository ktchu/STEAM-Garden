---
tags: geometric-algebra, linear-algebra
---

--------------------------------------------------------------------------------------------

2022-09-08: Bounds on Angles and Projections Between Linear Spaces
------------------------------------------------------------------

_Author(s)_: Kevin Chu `<kevin@velexi.com>`

_Last Updated_: 2022-09-13

--------------------------------------------------------------------------------------------
### Summary

Let $\B{B}$ and $\B{C}$ be blades representing linear spaces and $\theta_{BC}$ be the angle
between them. Then (1) the angle between linear spaces and (2) the projection between
blades related to $\B{B}$ and $\B{C}$ satsify inequality bounds related to $\theta_{BC}$.
These bounds generalize the equality relationships satisified when $\B{B}$ is a vector
(i.e., a 1-blade).

#### Angle Bounds

* The angle $\theta_{BC^*}$ between $\mathbf{B}$ and $\mathbf{C}^*$ (the orthogonal
  complement of $\mathbf{C}$) is bounded from below:

  $$
  \theta_{BC^*} \ge \frac{\pi}{2} - \theta_{BC}.
  $$

* Let $\mathbf{A}$ be subspace of $\mathbf{B}$.

  * The angle $\theta_{AC}$ between $\mathbf{A}$ and $\mathbf{C}$ is bounded from above:

    $$
    \theta_{AC} \le \theta_{BC}.
    $$

  * The angle $\theta_{AC^*}$ between $\mathbf{A}$ and $\mathbf{C}^*$ is bounded from below:

    $$
    \theta_{AC^*} \ge \frac{\pi}{2} - \theta_{BC}.
    $$

#### Projection Bounds

* The norm of the projection of $\mathbf{B}$ onto $\mathbf{C}^*$ is no more than
  $\vert \mathbf{B} \vert \sin \theta_{BC}$.

* Let $\mathbf{A}$ be a subspace of $\mathbf{B}$. Then

  * the norm of the projection of $\mathbf{A}$ onto $\mathbf{C}$ is no less than
    $\vert \mathbf{A} \vert \cos \theta_{BC}$

    and

  * the norm of the projection of $\mathbf{A}$ onto $\mathbf{C}^*$ is no more than
    $\vert \mathbf{A} \vert \sin \theta_{BC}$.

#### Equality Relationships When $\mathbf{B}$ is a Vector

Let $\mathbf{B}$ be a vector (i.e., a 1-blade), then

* the angle $\theta_{BC^*}$ beteween $\mathbf{B}$ onto $\mathbf{C}^*$ is equal to
  $\frac{\pi}{2} - \theta_{BC}$

  and

* the norm of the projection of $\mathbf{B}$ onto $\mathbf{C}^*$ is equal to
  $\vert \mathbf{B} \vert \sin \theta_{BC}$.

--------------------------------------------------------------------------------------------
### Notation

* $\newcommand{\B}[1]{\mathbf{#1}}$
  A blade: $\B{B}$ (uppercase, boldface)

* $\newcommand{\norm}[1]{\left\vert #1\right\vert}$
  The norm of multivector $M$: $\norm{M}$

* $\newcommand{\proj}[2]{P_{\B{#1}}\left(#2\right)}$
  The projection of blade $\B{A}$ onto the subspace represented by $\B{B}$:
  $\proj{B}{\B{A}}$

* $\newcommand{\grade}[1]{\operatorname{grade}\left(#1\right)}$
  The grade of blade $\B{B}$: $\grade{\B{B}}$

--------------------------------------------------------------------------------------------

### Proposition

Let $B$ and $C$ be blades with $\grade{B} \le \grade{C}$ and let $\theta_{BC}$ be the angle
between them. If $A \subseteq B$ and $\theta_{AC}$ is the defined as the angle between $A$
and $C$, then $\cos \theta_{AC} \ge \cos \theta_{BC}$. In other words,
$\theta_{AC} \le \theta_{BC}$.

_Proof_. Without loss of generality, assume that $\norm{C} = 1$. Let $k = \grade{B}$.
Choose $\{a_1, \ldots, a_j\}$ to be an orthonormal basis for $A$. Extend this orthonormal
basis to an orthonormal basis for $B$: $\{a_1, \ldots, a_j, b_{j+1}, \ldots, b_k\}$. Then
$\norm{A} = 1$, $\norm{B} = 1$,

$$
A = a_1 \cdots a_j = a_1 \wedge \cdots \wedge a_j,
$$

$$
B = a_1 \cdots a_j b_{j+1} \cdots b_k
= a_1 \wedge \cdots \wedge a_j \wedge b_{j+1} \wedge \cdots \wedge b_k,
$$

and

$$
\cos \theta_{BC}
= \frac{\norm{\proj{C}{B}}}{\norm{B} \norm{C}}
= \norm{\proj{C}{B}}
$$

Since projection preserves outer products,

$$
\proj{C}{B}
= \proj{C}{a_1 \cdots a_j} \wedge \proj{C}{b_{j+1} \cdots b_k}.
= \proj{C}{A} \wedge \proj{C}{b_{j+1} \cdots b_k}.
$$

Taking norms and using Hadamard's inequality for outer products, we find that

$$
\norm{\proj{C}{B}}
\le \norm{\proj{C}{A}} \norm{\proj{C}{b_{j+1} \cdots b_k}}
\le \norm{\proj{C}{A}}
$$

where the last inequality follows because $b_{j+1} \cdots b_k$ is a unit blade by
construction and projection can only decrease the norm of a blade.

Expressing norms of projections in terms of cosines of angles yields the desired result:

$$
\cos \theta_{BC}
= \frac{\norm{\proj{C}{B}}}{\norm{B} \norm{C}}
= \norm{\proj{C}{B}}
\le \norm{\proj{C}{A}}
= \frac{\norm{\proj{C}{A}}}{\norm{A} \norm{C}}
= \cos \theta_{AC}.
$$

__Corollary__

* In terms of cosines of the angles, $\cos \theta_{AC} \ge \cos \theta_{BC}$, where
  $\theta_{AC}$ and $\theta_{BC}$ are the angles between $A$ and $C$ and between $B$ and
  $C$, respectively.

* In terms of blade projections,

  $$
  \frac{\norm{\proj{C}{A}}}{\norm{A}} \ge \frac{\norm{\proj{C}{B}}}{\norm{B}}.
  $$

--------------------------------------------------------------------------------------------

### Proposition

Let $B$ and $C$ be subspaces with the same dimension. If $x$ is a vector, then the
projection of $x$ onto $B$ can be expressed in terms of the projections of $x$ onto $C$
and its orthogonal complement $C^*$:

$$
\proj{B}{x} = \proj{B}{\proj{C}{x}} + \proj{B}{\proj{C^*}{x}}.
$$

Bounds on $\norm{\proj{B}{x}}$: TODO


_Proof_. TODO

--------------------------------------------------------------------------------------------
