---
tags: geometric-algebra
---

--------------------------------------------------------------------------------------------

2022-09-27: Useful Blade Identities
===================================

_Author(s)_: Kevin Chu `<kevin@velexi.com>`

_Last Updated_: 2022-09-27

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

### Proposition 1. $\dual{(\B{A} \B{B})} = \B{A} \dual{\B{B}}$ when $\B{A} \cap \B{B} = 0$

If $\B{A}$ and $\B{B}$ are blades such that the $\B{A} \cap \B{B} = 0$, then

$$
\dual{(\B{A} \B{B})} = \B{A} \dual{\B{B}}.
$$

_Proof_. Choose orthogonal bases for both $\B{A}$ and $\B{B}$. $\B{A} \cap \B{B} = 0$
implies that $\B{a}_i$ and $\B{b}_j$ are orthogonal when $\B{a}_i$ and $\B{b}_j$ are basis
vectors for $\B{A}$ and $\B{B}$, respectively. Thus, $\B{A} \B{B} = \B{A} \wedge \B{B}$ [1],
which implies that [1]

$$
\dual{(\B{A} \B{B})}
= \dual{(\B{A} \wedge \B{B})}
= \B{A} \cdot \dual{\B{B}}
= \B{A} \dual{\B{B}}
$$

where second equality follows from the duality relations between inner and outer products
[1] and the third inequality because $\B{A} \cap \B{B} = 0$ implies that
$\B{A} \subset \dual{\B{B}}$ so that $\B{A} \cdot \dual{\B{B}} = \B{A} \dual{\B{B}}$ [1].

--------------------------------------------------------------------------------------------
## References

1. A. Macdonald. "Linear and Geometric Algebra" (2010).

--------------------------------------------------------------------------------------------
