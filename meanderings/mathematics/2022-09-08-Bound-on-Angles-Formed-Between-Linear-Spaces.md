---
tags: geometric-algebra, linear-algebra
---

--------------------------------------------------------------------------------------------

2022-09-08: Bound on Angles Formed Between Linear Spaces
--------------------------------------------------------

_Author(s)_: Kevin Chu `<kevin@velexi.com>`

_Last Updated_: 2022-09-09

--------------------------------------------------------------------------------------------
### Summary

If $B$ and $C$ are linear spaces and $A$ is subspace of $B$, then the angle formed between
$A$ and $C$ is no greater than the angle formed between $B$ and $C$.

* In terms of cosines of the angles, $\cos \theta_{AC} \ge \cos \theta_{BC}$, where
  $\theta_{AC}$ and $\theta_{BC}$ are the angles between $A$ and $C$ and between $B$ and
  $C$, respectively.

* In terms of blade projections,

  $$
  \frac{\norm{\proj{C}{A}}}{\norm{A}} \ge \frac{\norm{\proj{C}{B}}}{\norm{B}}.
  $$

--------------------------------------------------------------------------------------------
### Notation

Let $B$ and $C$ be blades.

* Define $\norm{B}$ to be the norm of $B$.
  $\newcommand{\norm}[1]{\left\Vert #1\right\Vert}$

* Define $\proj{C}{B}$ to be the projection of blade $B$ onto the subspace represented
  by $C$.
  $\newcommand{\proj}[2]{P_{#1}\left(#2\right)}$

* Define $\grade{B}$ to be the grade of $B$.
  $\newcommand{\grade}[1]{\operatorname{grade}\left(#1\right)}$

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
A = a_1 \cdots a_j = a_1 \wedge \cdots a_j,
$$

$$
B = a_1 \cdots a_j b_{j+1} \cdots b_k
= a_1 \wedge \cdots a_j \wedge b_{j+1} \wedge \cdots \wedge b_k,
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

--------------------------------------------------------------------------------------------