---
tags: geometric-algebra
---

--------------------------------------------------------------------------------------------

2022-09-27: Useful Blade Identities
===================================

_Author(s)_: Kevin Chu `<kevin@velexi.com>`

_Last Updated_: 2022-09-28

--------------------------------------------------------------------------------------------
## Summary

This note collects useful blade identities.

--------------------------------------------------------------------------------------------
## Notation

* $\newcommand{\B}[1]{\mathbf{#1}}$
  A blade: $\B{B}$ (uppercase, boldface)

* A vector $\B{v}$ (lowercase, boldface)

* $\newcommand{\norm}[1]{\vert{#1}\vert}$
  The norm of blade $\B{B}$: $\norm{\B{B}}$

* $\newcommand{\dual}[1]{{#1}^*}$
  The dual (i.e., orthogonal complement) of blade $\B{B}$: $\dual{\B{B}}$

* $\newcommand{\grade}[1]{\operatorname{grade}\left({#1}\right)}$
  The grade of blade $\B{B}$: $\grade{\B{B}}$

* $\B{A}$ is a subspace of $\B{B}$: $\B{A} \subseteq \B{B}$

--------------------------------------------------------------------------------------------
## Propositions

### Proposition 1. $\B{A} \B{B} = \B{A} \wedge \B{B}$ when $\B{A} \subseteq \dual{\B{B}}$

If $\B{A}$ and $\B{B}$ are blades such that the $\B{A} \subseteq \dual{\B{B}}$, then

$$
\B{A} \B{B} = \B{A} \wedge \B{B}.
$$

_Proof_. Let $m = \grade{\B{A}}$ and $n = \grade{\B{B}}$ and choose orthogonal bases
$\{ \B{a}_1, \ldots, \B{a}_m \}$ and $\{ \B{b}_1, \ldots, \B{b}_n \}$ for $\B{A}$ and
$\B{B}$, respectively. Since $\B{A} \subseteq \dual{\B{B}}$, $\B{a}_i$ and $\B{b}_j$ are
orthogonal for all $i$ and $j$. Therefore,

$$
\begin{align}
\B{A} \B{B}
&= (a_1 \cdots a_m) (b_1 \cdots b_n) \\
&= (a_1 \cdots a_j b_1 \cdots b_n) \\
&= \B{A} \wedge \B{B}
\end{align}
$$

where the last equality follows because the product of orthogonal vectors is equal to the
outer product of the vectors [1].

### Proposition 2. $\dual{(\B{A} \B{B})} = \B{A} \dual{\B{B}}$ when $\B{A} \subseteq \dual{\B{B}}$

If $\B{A}$ and $\B{B}$ are blades such that the $\B{A} \subseteq \dual{\B{B}}$, then

$$
\dual{(\B{A} \B{B})} = \B{A} \dual{\B{B}}.
$$

_Proof_. Since $\B{A} \subseteq \dual{\B{B}}$, Proposition 1 implies that
$\B{A} \B{B} = \B{A} \wedge \B{B}$. Therefore,

$$
\dual{(\B{A} \B{B})}
= \dual{(\B{A} \wedge \B{B})}
= \B{A} \cdot \dual{\B{B}}
= \B{A} \dual{\B{B}}
$$

where second equality follows from the duality relations between inner and outer products
[1] and the third inequality follows because $\B{A} \subseteq \dual{\B{B}}$ implies that
$\B{A} \cdot \dual{\B{B}} = \B{A} \dual{\B{B}}$ [1].

--------------------------------------------------------------------------------------------
## References

1. A. Macdonald. "Linear and Geometric Algebra" (2010).

--------------------------------------------------------------------------------------------
