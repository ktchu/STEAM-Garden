---
tags: geometric-algebra, linear-algebra
---

--------------------------------------------------------------------------------------------

2022-09-08: Bounds on Angles and Projections Between Blades
-----------------------------------------------------------

_Author(s)_: Kevin Chu `<kevin@velexi.com>`

_Last Updated_: 2022-09-13

--------------------------------------------------------------------------------------------
### Notation

* $\newcommand{\B}[1]{\mathbf{#1}}$
  A blade: $\B{B}$ (uppercase, boldface)

* $\newcommand{\norm}[1]{\left\vert #1\right\vert}$
  The norm of multivector $M$: $\norm{M}$

* $\newcommand{\dual}[1]{#1^\perp}$
  The orthogonal complement (i.e., dual) of blade $\B{B}$: $\dual{\B{B}}$

* $\newcommand{\proj}[2]{P_{#1}\left(#2\right)}$
  The orthogonal projection of blade $\B{A}$ onto the subspace represented by $\B{B}$:
  $\proj{\B{B}}{\B{A}}$

--------------------------------------------------------------------------------------------
### Summary

When $\B{v}$ is a vector and $U$ is a subspace of a vector space $V$, the angle
$\theta$ between $\B{v}$ and $U$ completely determines (1) the angle between $\B{v}$ and
$\dual{U}$ and (2) the projection of $\B{v}$ onto $\dual{U}$:

* the angle between $\B{v}$ and $\dual{U}$ is equal to $\frac{\pi}{2} - \theta$;

* the norm of the projection of $\B{v}$ onto $\dual{U}$ is equal to
  $\norm{\B{v}} \sin \theta$.

For blades with grade greater than 1, geometry is more complicated. In particular, we no
longer have simple equality relationships between the angle a blade $\B{B}$ makes with a
subspace $U$ and other geometric quantities – instead , we have simple _inequality_
relationships. In this note, we several bounds that are useful when examining the geometry
of blade (and subspace) constructions.

#### Key Results

Let $\B{B}$ and $\B{C}$ be blades and $\theta_{BC}$ be the angle between them. Then the
angles between and projections of blades related to $\B{B}$ and $\B{C}$ satisfy the
following inequalities involving $\theta_{BC}$ (where all angles are taken to lie within
the interval $[0, \pi/2]$).

__Relationships Between Subspaces of $\B{B}$ and $\B{C}$__

* If $\B{A}$ is a subspace of $\B{B}$, then the angle $\theta_{AC}$ between $\B{A}$ and
  $\B{C}$ is bounded from above:

  $$
  \theta_{AC} \le \theta_{BC}.
  $$

* If $\B{A}$ is a blade that represents a subspace of $\B{B}$, then the norm of the
  projection of $\B{A}$ onto $\B{C}$ is bounded from below:

  $$
  \norm{\proj{\B{C}}{\B{A}}}
  \ge \norm{\B{A}} \cos \theta_{BC}.
  $$

__Relationships Between $\B{B}$ and $\dual{\B{C}}$__

* If $\B{B}$ is a $k$-blade, then the angle $\theta_{B\dual{C}}$ between $\B{B}$ and
  $\dual{\B{C}}$ is bounded from below:

  $$
  \theta_{B\dual{C}}
  \ge \cos^{-1} \left( (\sin \theta_{BC})^k \right)
  \ge \frac{\pi}{2} - \theta_{BC}.
  $$

* If $\B{B}$ is a $k$-blade, then the norm of the projection of $\B{B}$ onto $\dual{\B{C}}$
  is bounded from above:

  $$
  \norm{\proj{\dual{\B{C}}}{\B{B}}}
  \le \norm{\B{B}} (\sin \theta_{BC})^k
  \le \norm{\B{B}} \sin \theta_{BC}
  $$

__Relationships Between Subspaces of $\B{B}$ and $\dual{\B{C}}$__

* If $\B{A}$ is a subspace of $\B{B}$, then the angle $\theta_{A\dual{C}}$ between $\B{A}$
  and $\dual{\B{C}}$ is bounded from above and below by expressions involving
  $\theta_{BC}$ and $\theta_{B\dual{C}}$:

  $$
  \left( \frac{\pi}{2} - \theta_{BC} \right)
  \le \theta_{A\dual{C}}
  \le \theta_{B\dual{C}}.
  $$

* If $\B{A}$ is a blade that represents a subspace of $\B{B}$, then the norm of the
  projection of $\B{A}$ onto $\dual{\B{C}}$ is bounded from above and below by expressions
  involving $\theta_{BC}$ and $\theta_{B\dual{C}}$:

  $$
  \norm{\B{A}} \cos \theta_{B\dual{C}}
  \le \norm{\proj{\dual{\B{C}}}{\B{A}}}
  \le \norm{\B{A}} \sin \theta_{BC}.
  $$

### Remark

* The bounds gives a sense how different life is in high-dimension vector spaces. If we are
  not careful, our intution from planar geometry might lead us astray.

  For example, the angle between $\B{B}$ and the orthogonal complement of $\B{C}$ must be
  closer to $\pi/2$ than any subspace of $\B{B}$ is to $\B{C}$. In other words, if any
  subspace of $\B{B}$ is close to lying in $\B{C}$, $\B{B}$ must make a large angle with
  and have a very small projection onto $\dual{\B{C}}$.

* An interesting consequence of the lower bound on $\theta_{B\dual{C}}$ is that it is easy
  for blades with high grades to simultaneously form large angles with both a subspace and
  its orthogonal complement.

--------------------------------------------------------------------------------------------
### Additional Notation

* $\newcommand{\grade}[1]{\operatorname{grade}\left(#1\right)}$
  The grade of blade $\B{B}$: $\grade{\B{B}}$

* $\B{A}$ is a subspace of $\B{B}$: $\B{A} \subseteq \B{B}$

--------------------------------------------------------------------------------------------

### Propositions

For all of the propositions, assume the following.

* Let $\B{B}$ and $\B{C}$ be blades with $\grade{\B{B}} \le \grade{\B{C}}$ and
  $\theta_{BC}$ be the angle between them. We neglect the case
  $\grade{\B{B}} \ge \grade{\B{C}}$ because it implies $\theta_{BC} = \pi/2$, which leads
  to trivial bounds.

* All angles are taken to lie within the interval $[0, \pi/2]$.

#### Proposition 1: $\norm{\proj{\B{C}}{\B{A}}} \ge \norm{\B{A}} \cos \theta_{BC}$

If $\B{A} \subseteq \B{B}$, then

$$
\norm{\proj{\B{C}}{\B{A}}} \ge \norm{\B{A}} \cos \theta_{BC}.
$$

_Proof_. Let $j = \grade{\B{A}}$ and $k = \grade{\B{B}}$. Choose $\{a_1, \ldots, a_j\}$ to
be an orthogonal basis for $\B{A}$ such that

$$
\B{A} = a_1 \cdots a_j = a_1 \wedge \cdots \wedge a_j.
$$

Extend this basis to an orthogonal basis for $\B{B}$:
$\{a_1, \ldots, a_j, b_{j+1}, \ldots, b_k\}$ choosing $\norm{b_i} = 1$ for all
$j+1 \le i \le k$. Then

$$
\B{B} = a_1 \cdots a_j b_{j+1} \cdots b_k
= a_1 \wedge \cdots \wedge a_j \wedge b_{j+1} \wedge \cdots \wedge b_k,
$$

$$
\norm{\B{B}} = \norm{\B{A}},
$$

and

$$
\cos \theta_{BC}
= \frac{\norm{\proj{\B{C}}{\B{B}}}}{\norm{\B{B}}}
= \frac{\norm{\proj{\B{C}}{\B{B}}}}{\norm{\B{A}}}
$$

Since projection preserves outer products,

$$
\proj{\B{C}}{\B{B}}
= \proj{\B{C}}{a_1 \cdots a_j} \wedge \proj{C}{b_{j+1} \cdots b_k}
= \proj{\B{C}}{\B{A}} \wedge \proj{C}{b_{j+1} \cdots b_k}.
$$

Taking norms and using Hadamard's inequality for outer products, we find that

$$
\norm{\proj{\B{C}}{\B{B}}}
\le \norm{\proj{\B{C}}{\B{A}}} \norm{\proj{\B{C}}{b_{j+1} \cdots b_k}}
\le \norm{\proj{\B{C}}{\B{A}}}
$$

where the last inequality follows because $b_{j+1} \cdots b_k$ is a unit blade by
construction and projection can only decrease the norm of a blade.

Therefore,

$$
\cos \theta_{BC}
\le \frac{\norm{\proj{\B{C}}{\B{A}}}}{\norm{\B{A}}},
$$

which is equivalent to the desired result.

__Corollary__. If $\B{A} \subseteq \B{B}$, then the angle $\theta_{AC}$ between $\B{A}$ and
$\B{C}$ satisfies the inequality:

$$
\theta_{AC} \le \theta_{BC}.
$$

_Proof_. Recalling that

$$
\cos \theta_{AC} = \frac{\norm{\proj{\B{C}}{\B{A}}}}{\norm{\B{A}}},
$$

we can express the inequality in the previous proposition as

$$
\cos \theta_{BC} \le \cos \theta_{AC},
$$

which is equivalent to the desired result because cosine is a decreasing function on
$[0, \pi/2]$.

__Corollary__. If $\B{A} \subseteq \B{B}$, then

$$
\frac{\norm{\proj{\B{C}}{\B{A}}}}{\norm{\B{A}}}
\ge \frac{\norm{\proj{\B{C}}{\B{B}}}}{\norm{\B{B}}}.
$$

_Proof_. The result follows from the definition of the cosine of the angle between two
blades.

#### Proposition 2: $\norm{\proj{\dual{\B{C}}}{\B{B}}} \le \norm{\B{B}} (\sin \theta_{BC})^k$

The norm of the projection of $\B{B}$ onto $\dual{\B{C}}$ satisfies the inequality:

$$
\norm{\proj{\dual{\B{C}}}{\B{B}}}
\le \norm{\B{B}} (\sin \theta_{BC})^k.
$$

_Proof_. We start by expressing the projection of $\B{B}$ onto $\dual{\B{C}}$ in terms
of dot products (left contractions) and the norms of $\B{B}$ and $\B{C}$:

$$
\frac{\norm{\proj{\dual{\B{C}}}{\B{B}}}}{\norm{\B{B}}}
= \cos \theta_{B\dual{C}}
= \frac{\norm{\B{B} \cdot \dual{\B{C}}}}{\norm{\B{B}} \norm{\B{C}}}.
$$

By (1) duality of the inner and outer products and (2) equality of the norms of dual blades,

$$
\norm{\B{B} \cdot \dual{\B{C}}}
= \norm{ \dual{\left( \B{B} \wedge \B{C} \right)} }
= \norm{\B{B} \wedge \B{C}},
$$

so

$$
\frac{\norm{\proj{\dual{\B{C}}}{\B{B}}}}{\norm{\B{B}}}
= \frac{\norm{\B{B} \wedge \B{C}}}{\norm{\B{B}} \norm{\B{C}}}.
$$

To bound $\norm{\B{B} \wedge \B{C}}$, choose an orthogonal basis
$\{\B{b}_1, \ldots, \B{b}_k\}$ for $\B{B}$, where $k$ is the grade of $\B{B}$.
Then

$$
\B{B}
= \B{b}_1 \cdots \B{b}_k
= \B{b}_1 \wedge \cdots \wedge \B{b}_k
$$

and

$$
\norm{\B{B}} = \prod_{i=1}^k \norm{\B{b}_i}.
$$

Decomposing each $\B{b}_i$ as a sum of its projection onto and rejection from $\B{C}$,
$\B{b}_i = \B{b}_i^\parallel + \B{b}_i^\perp$, we can express $\B{B} \wedge \B{C}$ as

$$
\B{B} \wedge \B{C}
= \left( \B{b}_1 \wedge \cdots \wedge \B{b}_k \right) \wedge \B{C}
= \left( \B{b}_1^\perp \wedge \cdots \wedge \B{b}_k^\perp \right) \wedge \B{C}
$$

where the second equality follows from linearity of the outer product and the observation
that $\B{b}_i^\parallel \wedge \B{C} = 0$ because $\B{b}_i^\parallel$ lies in $\B{C}$.

Using Hadamard's inequality for outer products leads to the upper bound

$$
\norm{\B{B} \wedge \B{C}}
\le \left( \prod_{i=1}^k \norm{\B{b}_i^\perp} \right) \norm{\B{C}}
$$

Since each $\B{b}_i$ is a 1-blade contained in $\B{B}$, Proposition 1 implies that

$$
\norm{\B{b}_i^\parallel}
= \norm{\proj{\B{C}}{\B{b}_i}}
\ge \norm{\B{b}_i} \cos \theta_{BC},
$$

which implies that

$$
\norm{\B{b}_i^\perp}
\le \norm{\B{b}_i} \sin \theta_{BC}
$$

because $\norm{\B{b}_i}^2 = \norm{\B{b}_i^\parallel}^2 + \norm{\B{b}_i^\perp}^2$.

Therefore,

$$
\norm{\B{B} \wedge \B{C}}
\le \left( \prod_{i=1}^k \norm{\B{b}_i} \sin \theta_{BC} \right) \norm{\B{C}}
= (\sin \theta_{BC})^k \norm{\B{B}} \norm{\B{C}}
$$

Using this bound into the expression for the projection of $\B{B}$ onto $\dual{\B{C}}$
yields the bound

$$
\frac{\norm{\proj{\dual{\B{C}}}{\B{B}}}}{\norm{\B{B}}}
= \frac{\norm{\B{B} \wedge \B{C}}}{\norm{\B{B}} \norm{\B{C}}}
\le (\sin \theta_{BC})^k,
$$

which is equivalent to the desired result.

__Corollary__

The norm of the projection of $\B{B}$ onto $\dual{\B{C}}$ satisfies the inequality:

$$
\norm{\proj{\dual{\B{C}}}{\B{B}}} \le \norm{\B{B}} \sin \theta_{BC}.
$$

_Proof_. The result follows because $(\sin \theta)^k \le \sin \theta$.

__Corollary__

The angle $\theta_{B\dual{C}}$ between $\B{B}$ and $\dual{\B{C}}$ satisfies the
inequalities:

$$
\theta_{B\dual{C}}
\ge \cos^{-1} \left( (\sin \theta_{BC})^k \right)
\ge \frac{\pi}{2} - \theta_{BC}.
$$

_Proof_. Dividing the inequality in Proposition 2 and the previous corollary by
$\norm{\B{B}}$ and recalling the definition of the cosine of the angle between blades
yields

$$
\cos \theta_{B\dual{C}}
\le (\sin \theta_{BC})^k
\le \sin \theta_{BC} = \cos \left( \frac{\pi}{2} - \theta_{BC} \right),
$$

which is equivalent to the desired result.

#### Proposition 3: $\norm{\B{A}} \cos \theta_{B\dual{C}} \le \norm{\proj{\dual{\B{C}}}{\B{A}}} \le \norm{\B{A}} \sin \theta_{BC}$

If $\B{A} \subseteq \B{B}$, then

$$
\norm{\B{A}} \cos \theta_{B\dual{C}}
\le \norm{\proj{\dual{\B{C}}}{\B{A}}}
\le \norm{\B{A}} \sin \theta_{BC}.
$$

_Proof_. The lower bound follows from Proposition 1 with $\dual{\B{C}}$ in the place of
$\B{C}$.

To prove the upper bound, observe that Proposition 1 with $\B{A}$ in the place of $\B{B}$
implies that $\norm{\proj{\dual{\B{C}}}{\B{A}}} \le \norm{\B{A}} \sin \theta_{AC}$. Since
$\theta_{AC} \le \theta_{BC}$ by corollary of Proposition 1,
$\sin \theta_{AC} \le \sin \theta_{BC}$, which yields the desired upper bound.

__Corollary__. If $\B{A} \subseteq \B{B}$, then the angle $\theta_{A\dual{C}}$ between
$\B{A}$ and $\dual{\B{C}}$ satisfies the inequalities:

$$
\left( \frac{\pi}{2} - \theta_{BC} \right)
\le \theta_{A\dual{C}}
\le \theta_{B\dual{C}}.
$$

_Proof_. Dividing the inequalities in the previous proposition by $\norm{\B{A}}$ and
recalling the definition of the cosine between blades leads to

$$
\cos \theta_{B\dual{C}}
\le \cos \theta_{A\dual{C}}
\le \sin \theta_{BC},
$$

which is equivalent to the desired result.

--------------------------------------------------------------------------------------------
