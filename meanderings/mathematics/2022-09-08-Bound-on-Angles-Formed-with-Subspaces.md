---
tags: geometric-algebra
---

--------------------------------------------------------------------------------------------

2022-09-08: Bound on Angles Formed with Subspaces
-------------------------------------------------

_Author(s)_: Kevin Chu `<kevin@velexi.com>`

_Last Updated_: 2022-09-08

--------------------------------------------------------------------------------------------
### Summary

If $B$ and $C$ are linear spaces and $A$ is subspace of $B$, then the angle formed between
$A$ and $C$ is no greater than the angle formed between $B$ and $C$.

--------------------------------------------------------------------------------------------
### Notation

* Let $B$ and $C$ be blades.

  * Define $\norm{B}$ to be the norm of $B$.
    $\newcommand{\norm}[1]{\left\Vert #1\right\Vert}$

  * Define $\proj{C}{B}$ to be the projection of blade $B$ onto the subspace represented
    by $C$.
    $\newcommand{\proj}[2]{P_{#1}\left(#2\right)}$

  * Define $\grade{B}$ to be the grade of $B$.
    $\newcommand{\grade}[1]{\operatorname{grade}\left(#1\right)}$

--------------------------------------------------------------------------------------------

### Proposition

Let $B$ and $C$ be blades with $\grade{B} \le \grade{C}$ and let $\theta$ be the angle
  between them.

If $A \subseteq B$ and $\theta_A$ is the defined as the angle between $A$ and $C$, then

$$
\cos \theta_A \ge \cos \theta.
$$

_Proof_. Without loss of generality, assume that $\norm{C} = 1$. Let $k = \grade{B}$.
Choose $\{a_1, \ldots, a_j\}$ to be an orthonormal basis for $A$. Extend this orthonormal
basis to an orthonormal basis for $B$: $\{a_1, \ldots, a_j, b_{j+1}, \ldots, b_k\}$. Then
$B = a_1 \cdots a_j b_{j+1} \cdots b_k$ $\norm{B} = 1$, and

$$
\cos \theta
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
construction and the projection of a unit blade has norm at most one.

Therefore,

$$
\cos \theta
\le \norm{\proj{C}{A}}
= \frac{\norm{\proj{C}{A}}}{\norm{A} \norm{C}}
= \cos \theta_A
$$

where the second equality follows because $a_1 \cdots a_j$ is a unit blade by construction.

--------------------------------------------------------------------------------------------
