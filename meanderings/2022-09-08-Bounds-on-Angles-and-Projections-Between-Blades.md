---
tags: geometric-algebra, linear-algebra
---

--------------------------------------------------------------------------------------------

2022-09-08: Bounds on Angles and Projections Between Blades
===========================================================

_Author(s)_: Kevin Chu `<kevin@velexi.com>`

_Last Updated_: 2022-10-12

--------------------------------------------------------------------------------------------
## Notation

* $\newcommand{\B}[1]{\mathbf{#1}}$
  A blade: $\B{B}$ (uppercase, boldface)

* $\newcommand{\norm}[1]{\vert{#1}\vert}$
  The norm of blade $\B{B}$: $\norm{\B{B}}$

* $\newcommand{\grade}[1]{\operatorname{grade}\left({#1}\right)}$
  The grade of blade $\B{B}$: $\grade{\B{B}}$

* $\B{A}$ is a subspace of $\B{B}$: $\B{A} \subseteq \B{B}$

* $\newcommand{\I}{\B{I}}$
  The unit pseudoscalar: $\I$

* $\newcommand{\dual}[1]{{#1}^\perp}$
  The orthogonal complement (i.e., dual) of blade $\B{B}$: $\dual{\B{B}}$

* $\newcommand{\proj}[2]{P_{#1}\left({#2}\right)}$
  The orthogonal projection of blade $\B{A}$ onto the subspace represented by $\B{B}$:
  $\proj{\B{B}}{\B{A}}$

* The angle formed between subspaces $\B{B}$ and $\B{C}$: $\theta_{BC}$

--------------------------------------------------------------------------------------------
## Summary

When $\B{v}$ is a vector and $U$ is a subspace of a vector space $V$, the angle
$\theta$ between $\B{v}$ and $U$ completely determines (1) the angle between $\B{v}$ and
$\dual{U}$ and (2) the projection of $\B{v}$ onto $\dual{U}$:

* the angle between $\B{v}$ and $\dual{U}$ is equal to $\frac{\pi}{2} - \theta$;

* the norm of the projection of $\B{v}$ onto $\dual{U}$ is equal to
  $\norm{\B{v}} \sin \theta$.

For blades with grade greater than 1, the geometry is more complicated. In particular, we
no longer have simple equality relationships between the angle a blade $\B{B}$ makes with
a subspace $U$ and other geometric quantities – instead , we have simple _inequality_
relationships. In this note, we identify and prove several bounds that are useful when
examining the geometry of blade (and subspace) constructions.

### Key Results

Let $\B{B}$ and $\B{C}$ be blades with $\grade{\B{B}} \le \grade{\B{C}}$ and $\theta_{BC}$
be the angle between them. Then the angles between and projections of blades related to
$\B{B}$ and $\B{C}$ satisfy the following inequalities involving $\theta_{BC}$ (where all
angles are taken to lie within the interval $[0, \pi/2]$).

__Relationships Between $\B{C}$ and Subspaces of $\B{B}$__

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

__Relationships Between $\B{B}$ and Subspaces of $\B{C}$__

* If $\B{D}$ is a subspace of $\B{C}$, then the angle $\theta_{BD}$ between $\B{B}$ and
  $\B{D}$ is bounded from below:

  $$
  \theta_{BD} \ge \theta_{BC}.
  $$

* If $\B{D}$ is a blade that represents a subspace of $\B{C}$, then the norm of the
  projection of $\B{B}$ onto $\B{D}$ is bounded from above:

  $$
  \norm{\proj{\B{D}}{\B{B}}}
  \le \norm{\B{B}} \cos \theta_{BC}.
  $$

__Relationships Between $\dual{\B{C}}$ and $\B{B}$__

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

__Relationships Between $\dual{\B{C}}$ and Subspaces of $\B{B}$__

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

### Remarks

Thes bounds gives a sense how different life is in high-dimension vector spaces. If we are
not careful, our intuition from planar geometry might lead us astray. The following are a
few interesting examples.

* The angle between $\B{B}$ and the orthogonal complement of $\B{C}$ must be closer to
  $\pi/2$ than any subspace of $\B{B}$ is to $\B{C}$. In particular, if any subspace of
  $\B{B}$ is close to lying in $\B{C}$, $\B{B}$ must make a large angle with and have a
  very small projection onto $\dual{\B{C}}$.

* A consequence of the lower bound on $\theta_{B\dual{C}}$ is that it is easy
  for blades with high grades to simultaneously form large angles with both a subspace and
  its orthogonal complement. In low-dimensional spaces, blades that are far from a subspace
  (in the sense of forming a large angle with the subspace) cannot be that far from the
  subspace's orthogonal complement.

--------------------------------------------------------------------------------------------
## Propositions

For all of the propositions, assume the following.

* Let $\B{B}$ and $\B{C}$ be blades with $\grade{\B{B}} \le \grade{\B{C}}$ and
  $\theta_{BC}$ be the angle between them. We neglect the case
  $\grade{\B{B}} \ge \grade{\B{C}}$ because it implies $\theta_{BC} = \pi/2$, which leads
  to trivial bounds.

* All angles are taken to lie within the interval $[0, \pi/2]$.

### Proposition 1. $\norm{\proj{\B{C}}{\B{A}}} \ge \norm{\B{A}} \cos \theta_{BC}$ when $\B{A} \subseteq \B{B}$

If $\B{A} \subseteq \B{B}$, then

$$
\norm{\proj{\B{C}}{\B{A}}} \ge \norm{\B{A}} \cos \theta_{BC}.
$$

_Proof_. Let $j = \grade{\B{A}}$ and $k = \grade{\B{B}}$. Choose
$\{\B{a}_1, \ldots, \B{a}_j\}$ to be an orthogonal basis for $\B{A}$ such that

$$
\B{A} = \B{a}_1 \cdots \B{a}_j = \B{a}_1 \wedge \cdots \wedge \B{a}_j.
$$

Extend this basis to an orthogonal basis
$\{\B{a}_1, \ldots, \B{a}_j, \B{b}_{j+1}, \ldots, \B{b}_k\}$ for
$\B{B}$ choosing $\norm{\B{b}_i} = 1$ for $j+1 \le i \le k$. Then

$$
\B{B} = \B{a}_1 \cdots \B{a}_j \B{b}_{j+1} \cdots \B{b}_k
= \B{a}_1 \wedge \cdots \wedge \B{a}_j \wedge \B{b}_{j+1} \wedge \cdots \wedge \B{b}_k,
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

Since projection preserves outer products [1],

$$
\proj{\B{C}}{\B{B}}
= \proj{\B{C}}{\B{a}_1 \cdots \B{a}_j} \wedge \proj{C}{\B{b}_{j+1} \cdots \B{b}_k}
= \proj{\B{C}}{\B{A}} \wedge \proj{C}{\B{b}_{j+1} \cdots \B{b}_k}.
$$

Taking norms and using Hadamard's inequality for outer products, we find that

$$
\norm{\proj{\B{C}}{\B{B}}}
\le \norm{\proj{\B{C}}{\B{A}}} \norm{\proj{\B{C}}{\B{b}_{j+1} \cdots \B{b}_k}}
\le \norm{\proj{\B{C}}{\B{A}}}
$$

where the last inequality follows because $\B{b}_{j+1} \cdots \B{b}_k$ is a unit blade by
construction and projection can only decrease the norm of a blade.

Therefore,

$$
\cos \theta_{BC}
\le \frac{\norm{\proj{\B{C}}{\B{A}}}}{\norm{\B{A}}},
$$

which is equivalent to the desired result.

#### Corollary 1.1. $\theta_{AC} \le \theta_{BC}$ when $\B{A} \subseteq \B{B}$

If $\B{A} \subseteq \B{B}$, then the angle $\theta_{AC}$ between $\B{A}$ and $\B{C}$
satisfies the inequality

$$
\theta_{AC} \le \theta_{BC}.
$$

_Proof_. Since

$$
\cos \theta_{AC} = \frac{\norm{\proj{\B{C}}{\B{A}}}}{\norm{\B{A}}},
$$

we can express the inequality in the previous proposition as

$$
\cos \theta_{BC} \le \cos \theta_{AC},
$$

which is equivalent to the desired result because cosine is a decreasing function on
$[0, \pi/2]$.

#### Corollary 1.2. $\frac{\norm{\proj{\B{C}}{\B{A}}}}{\norm{\B{A}}} \ge \frac{\norm{\proj{\B{C}}{\B{B}}}}{\norm{\B{B}}}$ when $\B{A} \subseteq \B{B}$

If $\B{A} \subseteq \B{B}$, then

$$
\frac{\norm{\proj{\B{C}}{\B{A}}}}{\norm{\B{A}}}
\ge \frac{\norm{\proj{\B{C}}{\B{B}}}}{\norm{\B{B}}}.
$$

_Proof_. The result follows from the definition of the cosine of the angle between two
blades.

### Proposition 2. $\norm{\proj{\B{D}}{\B{B}}} \le \norm{\B{B}} \cos \theta_{BC}$ when $\B{D} \subseteq \B{C}$

If $\B{D} \subseteq \B{C}$, then

$$
\norm{\proj{\B{D}}{\B{B}}} \le \norm{\B{B}} \cos \theta_{BC}.
$$

__Remark__. This proposition is a generalization of the vector property that
$\norm{\proj{\B{D}}{\B{v}}} \le \norm{\proj{\B{C}}{\B{v}}}$ when $\B{D} \subseteq \B{C}.$

_Proof_. Let $j = \grade{\B{D}}$ and $k = \grade{\B{C}}$. Choose
$\{\B{d}_1, \ldots, \B{d}_j\}$ to be an orthonormal basis for $\B{D}$ such that

$$
\B{D} = \B{d}_1 \cdots \B{d}_j = \B{d}_1 \wedge \cdots \wedge \B{d}_j.
$$

Extend this basis to an orthonormal basis
$\{\B{d}_1, \ldots, \B{d}_j, \B{c}_{j+1}, \ldots, \B{c}_k\}$ for
$\B{C}$. Then

$$
\B{C} = \B{d}_1 \cdots \B{d}_j \B{c}_{j+1} \cdots \B{c}_k
= \B{d}_1 \wedge \cdots \wedge \B{d}_j \wedge \B{c}_{j+1} \wedge \cdots \wedge \B{c}_k,
$$

$$
\norm{\B{D}} = \norm{\B{C}} = 1,
$$

and

$$
\begin{align}
\norm{\dual{\B{D}}}
&= \norm{(\B{d}_1 \cdots \B{d}_j) \ \I^{-1}} \\
&= \norm{(\B{d}_1 \cdots \B{d}_j \B{c}_{j+1}^2 \cdots \B{c}_k^2) \ \I^{-1}} \\
&= \norm{(\B{d}_1 \cdots \B{d}_j \B{c}_{j+1} \cdots \B{c}_k)
         (\B{c}_{j+1} \cdots \B{c}_k) \ \I^{-1}} \\
&= \norm{\left( \B{d}_1 \cdots \B{d}_j \B{c}_{j+1} \cdots \B{c}_k \ \I^{-1} \right)
         (\B{c}_{j+1} \cdots \B{c}_k)} \\
&= \norm{\dual{\B{C}} (\B{c}_{j+1} \cdots \B{c}_k)} \\
&= \norm{\dual{\B{C}} \wedge (\B{c}_{j+1} \cdots \B{c}_k)}
\end{align}
$$

where the last equality follows because $\B{c}_i \in \dual{\left(\dual{\B{C}}\right)}$ for
$j+1 \le i \le k$ [2].

Expressing $\norm{\proj{\B{D}}{\B{B}}}$ in terms of inner and geometric products, we have

$$
\begin{align}
\norm{\proj{\B{D}}{\B{B}}}
&= \frac{\norm{\B{B} \cdot \B{D}}}{\norm{\B{D}}} = \norm{\B{B} \cdot \B{D}} \\
&= \norm{\dual{(\B{B} \cdot \B{D})}} \\
&= \norm{\B{B} \wedge \dual{\B{D}}} \\
&= \norm{\B{B} \wedge \left( \dual{\B{C}} \wedge (\B{c}_{j+1} \cdots \B{c}_k) \right) } \\
&= \norm{\left( \B{B} \wedge \dual{\B{C}} \right) \wedge (\B{c}_{j+1} \cdots \B{c}_k) }
\end{align}
$$

where the second equality follows because the norm of a blade and its dual are equal [1]
and the third equality follows from the duality of the inner and outer products [1].

Using Hadamard's inequality for outer products, we find that

$$
\begin{align}
\norm{\proj{\B{D}}{\B{B}}}
&= \norm{\left( \B{B} \wedge \dual{\B{C}} \right) \wedge (\B{c}_{j+1} \cdots \B{c}_k) } \\
&\le \norm{\B{B} \wedge \dual{\B{C}}} \norm{\B{c}_{j+1} \cdots \B{c}_k} \\
&= \norm{\B{B} \wedge \dual{\B{C}}} \\
&= \norm{\dual{ \left( \B{B} \cdot \B{C} \right) }} \\
&= \norm{\B{B} \cdot \B{C}} \\
&= \norm{\proj{\B{C}}{\B{B}}}
\end{align}
$$

Therefore,

$$
\frac{\norm{\proj{\B{D}}{\B{B}}}}{\norm{\B{B}}}
\le \frac{\norm{\proj{\B{C}}{\B{B}}}}{\norm{\B{B}}}
= \cos \theta_{BC}
$$

which is equivalent to the desired result.

#### Corollary 2.1. $\theta_{BD} \ge \theta_{BC}$ when $\B{D} \subseteq \B{C}$

If $\B{D} \subseteq \B{C}$, then the angle $\theta_{BD}$ between $\B{B}$ and $\B{D}$
satisfies the inequality

$$
\theta_{BD} \ge \theta_{BC}.
$$

_Proof_. Since

$$
\cos \theta_{BD} = \frac{\norm{\proj{\B{D}}{\B{B}}}}{\norm{\B{B}}},
$$

we can express the inequality in the previous proposition as

$$
\cos \theta_{BD} \le \cos \theta_{BC},
$$

which is equivalent to the desired result because cosine is a decreasing function on
$[0, \pi/2]$.

#### Corollary 2.2. $\frac{\norm{\proj{\B{D}}{\B{B}}}}{\norm{\B{B}}} \le \frac{\norm{\proj{\B{C}}{\B{B}}}}{\norm{\B{B}}}$ when $\B{D} \subseteq \B{C}$

If $\B{D} \subseteq \B{C}$, then

$$
\frac{\norm{\proj{\B{D}}{\B{B}}}}{\norm{\B{B}}}
\le \frac{\norm{\proj{\B{C}}{\B{B}}}}{\norm{\B{B}}}.
$$

_Proof_. The result follows from the definition of the cosine of the angle between two
blades.

### Proposition 3. $\norm{\proj{\dual{\B{C}}}{\B{B}}} \le \norm{\B{B}} (\sin \theta_{BC})^k$

The norm of the projection of $\B{B}$ onto $\dual{\B{C}}$ satisfies the inequality

$$
\norm{\proj{\dual{\B{C}}}{\B{B}}}
\le \norm{\B{B}} (\sin \theta_{BC})^k.
$$

__Remark__. A geometric interpretation of this proposition is that a high-grade blade
$\B{B}$ is nearly orthogonal to most subspaces because no matter how large of an angle it
makes with an arbitrary subspace $\B{C}$ (i.e., $\sin \theta_{BC}$ close to 1), the power
of $k$ in the bound implies that the projection of $\B{B}$ onto the orthogonal complement
of $\B{C}$ is small.

_Proof_. We start by expressing the projection of $\B{B}$ onto $\dual{\B{C}}$ in terms
of inner products (left contractions) and the norms of $\B{B}$ and $\B{C}$:

$$
\frac{\norm{\proj{\dual{\B{C}}}{\B{B}}}}{\norm{\B{B}}}
= \cos \theta_{B\dual{C}}
= \frac{\norm{\B{B} \cdot \dual{\B{C}}}}{\norm{\B{B}} \norm{\B{C}}}.
$$

By (1) duality of the inner and outer products and (2) equality of the norms of dual blades
[1],

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

#### Corollary 3.1. $\norm{\proj{\dual{\B{C}}}{\B{B}}} \le \norm{\B{B}} \sin \theta_{BC}$

The norm of the projection of $\B{B}$ onto $\dual{\B{C}}$ satisfies the inequality

$$
\norm{\proj{\dual{\B{C}}}{\B{B}}} \le \norm{\B{B}} \sin \theta_{BC}.
$$

_Proof_. The result follows because $(\sin \theta)^k \le \sin \theta$.

#### Corollary 3.2. $\theta_{B\dual{C}} \ge \cos^{-1} \left( (\sin \theta_{BC})^k \right) \ge \frac{\pi}{2} - \theta_{BC}$

The angle $\theta_{B\dual{C}}$ between $\B{B}$ and $\dual{\B{C}}$ satisfies the
inequalities

$$
\theta_{B\dual{C}}
\ge \cos^{-1} \left( (\sin \theta_{BC})^k \right)
\ge \frac{\pi}{2} - \theta_{BC}.
$$

_Proof_. Dividing the inequalities from Proposition 3 by $\norm{\B{B}}$ and using the
definition of the cosine of the angle between blades, we find that

$$
\cos \theta_{B\dual{C}}
\le (\sin \theta_{BC})^k
\le \sin \theta_{BC} = \cos \left( \frac{\pi}{2} - \theta_{BC} \right),
$$

where the second inequality follows because $(\sin \theta)^k \le \sin \theta$. Taking
inverse cosines yields the desired result.

### Proposition 4. $\norm{\B{A}} \cos \theta_{B\dual{C}} \le \norm{\proj{\dual{\B{C}}}{\B{A}}} \le \norm{\B{A}} \sin \theta_{BC}$ when $\B{A} \subseteq \B{B}$

If $\B{A} \subseteq \B{B}$, then

$$
\norm{\B{A}} \cos \theta_{B\dual{C}}
\le \norm{\proj{\dual{\B{C}}}{\B{A}}}
\le \norm{\B{A}} \sin \theta_{BC}.
$$

_Proof_. The lower bound follows from Proposition 1 with $\dual{\B{C}}$ in the place of
$\B{C}$.

To prove the upper bound, observe that Proposition 3 with $\B{A}$ in the place of $\B{B}$
implies that $\norm{\proj{\dual{\B{C}}}{\B{A}}} \le \norm{\B{A}} \sin \theta_{AC}$. Since
$\theta_{AC} \le \theta_{BC}$ by corollary of Proposition 1,
$\sin \theta_{AC} \le \sin \theta_{BC}$, which yields the desired upper bound.

#### Corollary 4.1. $\left( \frac{\pi}{2} - \theta_{BC} \right) \le \theta_{A\dual{C}} \le \theta_{B\dual{C}}$

If $\B{A} \subseteq \B{B}$, then the angle $\theta_{A\dual{C}}$ between $\B{A}$ and
$\dual{\B{C}}$ satisfies the inequalities

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
## References

1. A. Macdonald. "Linear and Geometric Algebra" (2010).

2. [[2022-09-27-Useful-Blade-Identities]]

--------------------------------------------------------------------------------------------
