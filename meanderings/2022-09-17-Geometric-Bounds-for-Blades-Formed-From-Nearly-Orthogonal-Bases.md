---
tags: geometric-algebra, geometry
---

--------------------------------------------------------------------------------------------

2022-09-17: Geometric Bounds for Blades Formed From Nearly Orthogonal Bases
===========================================================================

_Author(s)_: Kevin Chu `<kevin@velexi.com>`

_Last Updated_: 2022-09-22

--------------------------------------------------------------------------------------------
## Notation

* $\newcommand{\R}{\mathbb{R}}$
  $\newcommand{\e}{\mathbf{e}}$
  The standard basis for $\R^n$: $\{ \e_1, \ldots, \e_n \}$

* $\newcommand{\abs}[1]{\left\vert{#1}\right\vert}$
  The absolute value of $x$: $\abs{x}$

__Blades__

* $\newcommand{\B}[1]{\mathbf{#1}}$
  A blade: $\B{B}$ (uppercase, boldface)

* $\newcommand{\norm}[2][2]{\left\Vert{#2}\right\Vert_{#1}}$
  The 2-norm of blade $\B{B}$: $\norm{\B{B}}$

* $\newcommand{\dual}[1]{{#1}^\perp}$
  The orthogonal complement (i.e., dual) of blade $\B{B}$: $\dual{\B{B}}$

* $\newcommand{\proj}[2]{P_{#1}\left({#2}\right)}$
  The orthogonal projection of blade $\B{A}$ onto the subspace represented by $\B{B}$:
  $\proj{\B{B}}{\B{A}}$

__Vectors__

* A vector: $\B{v}$ (lowercase, boldface)

* The $i$-th component of vector $\B{v}$ with respect to the standard basis:
  $v_i$ (lowercase, lightface)

* For indexed vector $\B{v}_i$, the $j$-th component of $\B{v}_i$: $v_{ij}$

* $\newcommand{\rej}[2]{\perp_{#1}\left({#2}\right)}$
  The rejection of vector $\B{v}$ from the subspace represented by $\B{B}$:
  $\rej{\B{B}}{\B{v}}$

__Canonical Basis Blades__. Let $S$ be a subset of $\{1, \ldots, n\}$.

* $\newcommand{\E}{\B{E}}$
  The blade formed by the standard basis vectors $\e_i$ with indices in $S$:
  $\E_S = \bigwedge_{k \in S} \e_k$

* The projection of blade $\B{B}$ onto $\E_S$: $\proj{S}{\B{B}}$

* The 2-norm of projection of blade $\B{B}$ onto $\E_S$:
  $\norm[S]{\B{B}} = \norm{\proj{S}{\B{B}}}$

--------------------------------------------------------------------------------------------
## Summary

The utility of orthogonal bases for representating and analyzing vectors in inner product
spaces cannot be overstated. Much of the power of orthogonal bases originates from the
special geometric properties of right angles and the simple relationships they imply.

For non-orthogonal bases that are nearly orthogonal, many of the useful geometric qualities
of orthogonal bases are retained in an _approximate_ manner. In this note, we identify
and prove bounds that quantify the deviation of useful geometric quantities for nearly
orthogonal bases.

### Key Results

Let $\{\B{v}_1, \ldots, \B{v}_n\}$ be a nearly orthogonal basis with the angle $\phi_i$
formed between $\B{v}_i$ and $\e_i$ such that $\cos \phi_i \ge \sqrt{1 - \epsilon^2}$ for
all $i$. In addition, let $S$ be a subset of $\{1, \ldots n\}$ and define $\theta_S$ to be
the angle formed between $\B{V}$ and $\E_S$.

__Characterizing "Nearness" to the Standard Basis__

_Angles_

* The angle between $\proj{S}{\B{v}_i}$ and $\e_i$ is no greater than the angle between
  $\B{v}_i$ and $\e_i$.

* The angle between $\proj{S}{\B{v}_i}$ and $\B{v}_i$ is no greater than the angle between
  $\B{v}_i$ and $\e_i$.

_Projections_

* $\frac{\norm{\proj{S}{\B{v}_i}}}{\norm{\B{v}_i}}$ is no less than $\sqrt{1 - \epsilon^2}$.

* The $\B{v}_i$ are close to (scalar multiples of) the standard basis in the following
  sense:

  * $\sqrt{1 - \epsilon^2} \le \frac{\abs{v_{ii}}}{\norm{\B{v}_i}}, \frac{\abs{v_{ii}}}{\norm[S]{\B{v}_i}} \le 1$

  * $\left( \sum_{k \in S, k \ne i} v_{ik}^2 \right)^{1/2} \le \epsilon \norm[S]{\B{v}_i}$

  * $\left( \sum_{k \in S'} v_{ik}^2 \right)^{1/2} \le \epsilon \norm[S]{\B{v}_i}$ when
    $S' \subset S$ such that $i \notin S'$

  * $\left( \sum_{k \in S} v_{ik}^2 \right)^{1/2} \le \epsilon \norm{\B{v}_i}$ when
    $i \notin S$

  * $\frac{\abs{v_{ij}}}{\norm{\B{v}_i}}, \frac{\abs{v_{ij}}}{\norm[S]{\B{v}_i}} \le \epsilon$ when $i \ne j$

  * $\abs{\frac{v_{ij}}{v_{ii}}} \le \epsilon (1 + \epsilon^2)$

__Approximate Orthogonality of $\{ \B{v}_1, \ldots \B{v}_n \}$__

Let $\B{V} = \bigwedge_{i \in S} \B{v}_i$.

* The volume of $\proj{S}{\B{V}}$, the projection of $\B{V}$ onto $\E_S$, is nearly equal
  to the product of the norms of the projections of $\B{v}_i$ onto $E_S$ (for $i \in S$):

  $$
  (1 - s \epsilon) \prod_{i \in S} \norm[S]{\B{v}_i}
  \le \norm[S]{\B{V}}
  \le \prod_{i \in S} \norm[S]{\B{v}_i}.
  $$

* The angle between $\proj{S}{\B{V}}$ and $\E_S$ is nearly 1:

  $$
  (1 - s \epsilon)^2
  \le (1 - s \epsilon) \left( 1 - \epsilon^2 \right)^{s/2}
  \le \cos \theta_S = \frac{\norm[S]{\B{V}}}{\norm{\B{V}}}
  \le 1.
  $$

* When $i \notin S$, the projection of $\B{v}_i$ onto the orthogonal complement of $\B{V}$
  is nearly equal to $\abs{v_{ii}}$:

  $$
  1 - \left(
        \frac{1 - (1 - s \epsilon)^2 \left(1 - \epsilon^2 \right)^s}{1 - \epsilon^2}
      \right)^{1/2}
  \le \frac{\norm{\rej{\B{V}}{\B{v}_i}}}{\abs{v_{ii}}}
  \le \left( 1 + \epsilon^2 \right).
  $$

  Simpler but looser lower bounds are

  $$
  \begin{align}
  \frac{\norm{\rej{\B{V}}{\B{v}_i}}}{\abs{v_{ii}}}
  &\ge 1 - \left( 1 + \epsilon^2 \right) \left( 1 - (1 - s \epsilon)^4 \right)^{1/2} \\
  &\ge 1 - 2 \sqrt{s \epsilon} \left( 1 + \epsilon^2 \right).
  \end{align}
  $$

  Interestingly, _without_ assuming that $\{ \B{v}_1, \ldots, \B{v}_n \}$ is nearly
  orthogonal, $\frac{\norm{\rej{\B{V}}{\B{v}_i}}}{\abs{v_{ii}}}$ can still be bounded in
  terms of the angle $\phi_i$ between $\B{v}_i$ and $\e_i$ and the angle $\theta_S$
  betweeen $\B{V}$ and $\E_S$:

  $$
  \left( 1  - \frac{\sin \theta_S}{\cos \phi_i} \right)
  \le \frac{\norm{\rej{\B{V}}{\B{v}_i}}}{\abs{v_{ii}}}
  \le \frac{1}{\cos \phi_i}.
  $$

--------------------------------------------------------------------------------------------
## Additional Notation

* $\newcommand{\sgn}[1]{\operatorname{sgn}\left({#1}\right)}$
  Sign of $x$: $\sgn{x}$

* $\newcommand{\card}[1]{\left|{#1}\right|}$
  The cardinality of a set $S$: $\card{S}$

--------------------------------------------------------------------------------------------
## Definitions

* __$\epsilon$-Similar Vector Sets__. For $0 < \epsilon < 1$, two sets of vectors
  $\{\B{u}_1, \ldots, \B{u}_m\}$ and $\{\B{v}_1, \ldots, \B{v}_m\}$ are said to be
  _$\epsilon$-similar_ to each other if there is a permutation $\sigma$ of
  $\{1, \ldots, m\}$ so that

  $$
  \abs{ \left( \frac{\B{u}_{\sigma(i)}}{\norm{\B{u}_{\sigma(i)}}} \right) \cdot
        \left( \frac{\B{v}_i}{\norm{\B{v}_i}} \right)
      }
  \ge \sqrt{1 - \epsilon^2}
  $$

  for $1 \le i \le m$. Intuitively, the vectors from the two sets can be paired up so
  that the angles between paired vectors is small.

* __Nearby Orthogonal Vectors__. A set of vectors $\{\B{v}_1, \ldots, \B{v}_m\}$ is said
  to be _nearly orthogonal_ if it is $\epsilon$-similar to a set of orthonormal vectors
  $\{\B{b}_1, \ldots, \B{b}_m\}$.

--------------------------------------------------------------------------------------------
## Assumptions

Throughout these notes, we assume the following.

* $\{\B{v}_1, \ldots, \B{v}_n\}$ is $\epsilon$-similar to the standard basis for $\R^n$
  under the identity permutation on the indices.

* $\phi_i$ is the angle formed between $\B{v}_i$ and $\e_i$.

* $S$ is a subset of $\{1, \ldots n\}$.

* $\theta_S$ is the angle formed between $\B{V}$ and $\E_S$.

* All angles are taken to lie in the interval $[0, \pi/2]$.

It is convenient to express the first and second assumptions in terms of the components
(with respect to the standard basis) of the $\B{v}_i$:

$$
\cos \phi_i = \frac{\abs{v_{ii}}}{\norm{\B{v}_i}} \ge \sqrt{1 - \epsilon^2}
$$

for $1 \le i \le n$.

#### Remark

All results hold for the general case where $\{\B{v}_1, \ldots, \B{v}_n\}$ is
$\epsilon$-similar to an arbitrary orthonormal basis $\{\B{b}_1, \ldots, \B{b}_n\}$ because
we can use the following procedure to transform the general case into a scenario that
satisfies the conditions of the first assumption.

1. Map $\B{v}_i$ to $\B{v}_{\sigma(i)}$ so that after mapping $\B{v}_j$ matches with
   $\B{b}_j$ for all $j$.

2. Apply the orthogonal linear transformation that maps $\B{b}_i$ to $\e_i$ to the
   vector space so that the orthonormal basis is the standard basis for $\R^n$.

--------------------------------------------------------------------------------------------
## Characterizing "Nearness" to the Standard Basis

### Lemma 1. Bounds for $\proj{S}{\B{v}_i}$

If $i \in S$, then

* the angle between $\proj{S}{\B{v}_i}$ and $\e_i$ is no greater than the angle between
  $\B{v}_i$ and $\e_i$;

* the angle between $\proj{S}{\B{v}_i}$ and $\B{v}_i$ is no greater than the angle between
  $\B{v}_i$ and $\e_i$.

_Proof_. For the first bound, $\norm[S]{\B{v}_i} \le \norm{\B{v}_i}$ implies that

$$
\frac{\abs{v_{ii}}}{\norm[S]{\B{v}_i}}
\ge \frac{\abs{v_{ii}}}{\norm{\B{v}_i}}
= \cos \phi_i.
$$

When $i \in S$, the expression on the left-hand side is equal to the cosine of the angle
between $\proj{S}{\B{v}_i}$ and $\e_i$, which yields the desired result.

For the second bound, $\abs{v_{ii}} \le \norm[S]{\B{v}_i}$ when $i \in S$, so

$$
\frac{\norm[S]{\B{v}_i}}{\norm{\B{v}_i}}
\ge \frac{\abs{v_{ii}}}{\norm{\B{v}_i}}
= \cos \phi_i.
$$

Observing that the expression on the left-hand side is equal to the cosine of the angle
between $\proj{S}{\B{v}_i}$ and $\B{v}_i$ yields the desired result.

#### Corollary 1.1. $\sqrt{1 - \epsilon^2} \le \frac{\abs{v_{ii}}}{\norm[S]{\B{v}_i}}, \frac{\norm[S]{\B{v}_i}}{\norm{\B{v}_i}} \le 1$

If $i \in S$, then

$$
\sqrt{1 - \epsilon^2} \le \frac{\abs{v_{ii}}}{\norm[S]{\B{v}_i}} \le 1.
$$

and

$$
\sqrt{1 - \epsilon^2} \le \frac{\norm[S]{\B{v}_i}}{\norm{\B{v}_i}} \le 1
$$

_Proof_. The lower bounds follow from the assumption that
$\cos \phi_i \ge \sqrt{1 - \epsilon^2}$. The upper bounds follow because cosine is never
greater than 1. The upper bounds can also be directly verified from the observations that

* $v_{ii} \le \norm[S]{\B{v}_i}$ when $i \in S$

  and

* $\norm[S]{\B{v}_i} \le \norm{\B{v}_i}$.

### Lemma 2. $\left( \sum_{k \in S, k \ne i} v_{ik}^2 \right)^{1/2} \le \epsilon \norm[S]{\B{v}_i}$

If $i \in S$, then

$$
\left( \sum_{k \in S, k \ne i} v_{ik}^2 \right)^{1/2}
\le \epsilon \norm[S]{\B{v}_i}.
$$

_Proof_. Since $i \in S$, we can expand $\norm[S]{\B{v}_i}^2$ as

$$
\norm[S]{\B{v}_i}^2
= v_{ii}^2 + \sum_{k \in S, k \ne i} v_{ik}^2.
$$

Rearranging this equation and using the Corollary 1.1, we find that

$$
\begin{align}
\sum_{k \in S, k \ne i} v_{ik}^2
&= \norm[S]{\B{v}_i}^2 - v_{ii}^2  \\
&= \norm[S]{\B{v}_i}^2 \left( 1 - \frac{v_{ii}^2}{\norm[S]{\B{v}_i}^2} \right) \\
&\le \epsilon^2 \norm[S]{\B{v}_i}^2,
\end{align}
$$

which is equivalent to the desire result upon taking square roots.

#### Corollary 2.1. $\left( \sum_{k \in S'} v_{ik}^2 \right)^{1/2} \le \epsilon \norm[S]{\B{v}_i}$

If $i \in S$ and $S' \subset S$ such that $i \notin S'$, then

$$
\left( \sum_{k \in S'} v_{ik}^2 \right)^{1/2}
\le \epsilon \norm[S]{\B{v}_i}.
$$

_Proof_. The result follows from Lemma 2 because

$$
\sum_{k \in S'} v_{ik}^2 \le \sum_{k \in S, k \ne i} v_{ik}^2.
$$

#### Corollary 2.2. $\left( \sum_{k \in S} v_{ik}^2 \right)^{1/2} \le \epsilon \norm{\B{v}_i}$

If $i \notin S$, then

$$
\left( \sum_{k \in S} v_{ik}^2 \right)^{1/2}
\le \epsilon \norm{\B{v}_i}.
$$

_Proof_. The result follow from Corollary 2.1 by taking $S' = S$ and
$S = \{ 1, \ldots n \}$.

#### Corollary 2.3. $\frac{\abs{v_{ij}}}{\norm[S]{\B{v}_i}} \le \epsilon$

If $i, j \in S$ and $i \ne j$,

$$
\frac{\abs{v_{ij}}}{\norm[S]{\B{v}_i}} \le \epsilon.
$$

_Proof_. Taking $S' = \{j\}$ in Corollary 2.1 yields the desired result.

#### Corollary 2.4. $\frac{\abs{v_{ij}}}{\norm{\B{v}_i}} \le \epsilon$

If $i \ne j$, then

$$
\frac{\abs{v_{ij}}}{\norm{\B{v}_i}} \le \epsilon.
$$

_Proof_. Taking $S = \{1, \ldots, n\}$ in Corollary 2.3 yields the desired result.
Alternatively, the result follows because $\norm[S]{\B{v}_i} \le \norm{\B{v}_i}$ implies
that $\frac{\abs{v_{ij}}}{\norm{\B{v}_i}} \le \frac{\abs{v_{ij}}}{\norm[S]{\B{v}_i}}$.

### Lemma 3. $\abs{\frac{v_{ij}}{v_{ii}}} \le \epsilon (1 + \epsilon^2)$

If $i \ne j$ and $\epsilon$ is sufficiently small ($\lesssim 0.78$), then

$$
\abs{\frac{v_{ij}}{v_{ii}}} \le \epsilon (1 + \epsilon^2).
$$

_Proof_.

$$
\abs{\frac{v_{ij}}{v_{ii}}}
= \Biggl( \frac{\abs{v_{ij}}}{\norm{\B{v}_i}} \Biggr)
  \Biggl( \frac{\norm{\B{v}_i}}{\abs{v_{ii}}} \Biggr)
\le \frac{\epsilon}{\sqrt{1 - \epsilon^2}}
\le \epsilon (1 + \epsilon^2),
$$

where the last inequality follows because it is equivalent to the inequality

$$
f(x) = (1 - x^2) (1 + x^2)^2 - 1 \ge 0
$$

which can be shown to hold on the interval
$\left[0, \left( \frac{\sqrt{5} - 1}{2} \right)^{1/2} \right]$ through an analysis of
the roots of $f(x)$ and the sign of $f(x)$ between the roots.

__Remark__. The geometric interpretation of this lemma is that there is an upper bound on
the tangent of angle between $\e_i$ and the projection of $\B{v}_i$ onto any two-dimensional
subspace of the form $\e_i \wedge e_j$.

--------------------------------------------------------------------------------------------
## Approximate Orthogonality of $\{ \B{v}_1, \ldots \B{v}_n \}$

### Proposition 4. Projections of $\{ \B{v}_1, \ldots \B{v}_n \}$ are Nearly Orthogonal

Let $i \ne j$. If $i, j \in S$, then

$$
\frac{\abs{\proj{S}{\B{v}_i} \cdot \proj{S}{\B{v}_j}}}{\norm[S]{\B{v}_i} \norm[S]{\B{v}_j}}
\le 3 \epsilon.
$$

_Proof_. Expressing the inner product of $\proj{S}{\B{v}_i}$ and $\proj{S}{\B{v}_j}$ over
components

$$
\proj{S}{\B{v}_i} \cdot \proj{S}{\B{v}_j}
= \sum_{k \in S} v_{ik} v_{jk}.
$$

If $i, j \in S$, then

$$
\begin{align}
\abs{\proj{S}{\B{v}_i} \cdot \proj{S}{\B{v}_j}}
&= \abs{ v_{ii} v_{ji} + v_{ij} v_{jj} + \sum_{k \in S, k \ne i, j} v_{ik} v_{jk} } \\
&\le \abs{v_{ii}} \abs{v_{ji}} + \abs{v_{ij}} \abs{v_{jj}}
     + \abs{ \sum_{k \in S, k \ne i, j} v_{ik} v_{jk} } \\
&\le \abs{v_{ii}} \abs{v_{ji}} + \abs{v_{ij}} \abs{v_{jj}}
     + \left( \sum_{k \in S, k \ne i, j} v_{ik}^2 \right)^{1/2}
       \left( \sum_{k \in S, k \ne i, j} v_{jk}^2 \right)^{1/2} \\
&\le 2 \epsilon \norm[S]{\B{v}_i} \norm[S]{\B{v}_j}
     + \epsilon^2 \norm[S]{\B{v}_i} \norm[S]{\B{v}_j} \\
&\le 3 \epsilon \norm[S]{\B{v}_i} \norm[S]{\B{v}_j}
\end{align}
$$

where the second inequality follows from the triangle inequality, the third inequality
follows from the Cauchy-Schwarz inequality, the fourth inequality follows from the
assumption that the $\B{v}_i$ are $\epsilon$-similar to the standard basis and
Corollary 2.1, and the last inequality follows because $\epsilon^2 < \epsilon$ when
$\epsilon < 1$. Rearranging the last inequality yields the desired result.

#### Corollary 4.1. $\frac{\abs{\B{v}_i \cdot \B{v}_j}}{\norm{\B{v}_i} \norm{\B{v}_j}} \le 3 \epsilon$

If $i \ne j$, then

$$
\frac{\abs{\B{v}_i \cdot \B{v}_j}}{\norm{\B{v}_i} \norm{\B{v}_j}} \le 3 \epsilon.
$$

_Proof_. The result follows by taking $S = \{1, \ldots n\}$.

__Remark__. The geometric interpretations of Proposition 4 and Corollary 4.1 are that

* any two vectors $\B{v}_i$ and $\B{v}_j$ are nearly orthogonal (Corollary 4.1) and

* the projections of $\B{v}_i$ and $\B{v}_j$ onto subspaces $E_S$ containing $e_i$ and
  $e_j$ continue to remain nearly orthogonal (Proposition 4).

### Proposition 5. $\norm[S]{\B{V}} \ge (1 - s \epsilon) \prod_{i \in S} \norm[S]{\B{v}_i}$

Let $\B{V} = \bigwedge_{i \in S} \B{v}_i$. If $s \epsilon \le 1$
then

$$
\norm[S]{\B{V}} \ge (1 - s \epsilon) \prod_{i \in S} \norm[S]{\B{v}_i}
$$

_Proof_. Let $\hat{\B{v}}_i$ be the subvector of $\B{v}_i$ consisting of the components
whose indices are in $S$. We can express $\norm[S]{\B{V}}$ as the absolute value of the
determinant of a matrix with columns $\hat{\B{v}}_i$:

$$
\norm[S]{\B{V}}
= \biggl| \det
    \left[ \begin{array}{c|c|c}
      \hat{\B{v}}_1 & \cdots & \hat{\B{v}}_s
    \end{array} \right]
  \biggr|.
$$

Factoring out $\sgn{v_{ii}} \norm[S]{\B{v}_i}$ from each column,

$$
\norm[S]{\B{V}}
= \left( \prod_{i \in S} \norm[S]{\B{v}_i} \right)
  \Biggl|
    \det \left[ \begin{array}{c|c|c}
      \frac{\sgn{v_{11}} v_1}{\norm[S]{\B{v}_1}}
      & \cdots
      & \frac{\sgn{v_{ss}} v_s}{\norm[S]{\B{v}_s}}
    \end{array} \right]
  \Biggr|.
$$

In this form, the matrix is close to the identity because
$\frac{\abs{v_{ii}}}{\norm[S]{\B{v}_i}} \ge \sqrt{1 - \epsilon^2} \ge 1 - \epsilon$ and
$\frac{\abs{v_{ij}}}{\norm[S]{\B{v}_i}} \le \epsilon$. Therefore, $s \epsilon \le 1$
implies that the determinant in the expression for $\norm[S]{\B{V}}$ is bounded below by
$(1 - s \epsilon)$ [1], which yields the desired result.

#### Corollary 5.1. $\norm{\B{V}} \ge (1 - s \epsilon) \prod_{i \in S} \norm[S]{\B{v}_i}$

If $\B{V} = \bigwedge_{i \in S} \B{v}_i$, then

$$
\norm{\B{V}} \ge (1 - s \epsilon) \prod_{i \in S} \norm[S]{\B{v}_i}.
$$

_Proof_. The result follows because $\norm{\B{V}} \ge \norm[S]{\B{V}}$.

### Proposition 6. $\cos \theta_S = \frac{\norm[S]{\B{V}}}{\norm{\B{V}}} \ge (1 - s \epsilon) \left( 1 - \epsilon^2 \right)^{s/2} \ge (1 - s \epsilon)^2$

Let $\B{V} = \bigwedge_{i \in S} \B{v}_i$. If $s \epsilon \le 1$, then

$$
\frac{\norm[S]{\B{V}}}{\norm{\B{V}}} \ge (1 - s \epsilon) \left( 1 - \epsilon^2 \right)^{s/2}.
$$

A simpler but looser bound is $\frac{\norm[S]{\B{V}}}{\norm{\B{V}}} \ge (1 - s \epsilon)^2$.

_Proof_. Combining the lower bound on $\norm[S]{\B{V}}$ with Hadamard's inequality

$$
\norm{\B{V}} \le \prod_{i \in S} \norm{\B{v}_i},
$$

we find that

$$
\frac{\norm[S]{\B{V}}}{\norm{\B{V}}}
\ge \frac{(1 - s \epsilon) \prod_{i \in S} \norm[S]{\B{v}_i}}
         {\prod_{i \in S} \norm{\B{v}_i}}
= (1 - s \epsilon) \prod_{i \in S} \frac{\norm[S]{\B{v}_i}}{\norm{\B{v}_i}}
\ge (1 - s \epsilon) \left( 1 - \epsilon^2 \right)^{s/2}
$$

The looser bound follows from the observations that

* $\sqrt{1 - \epsilon^2} \ge 1 - \epsilon$

  and

* $(1 - \epsilon)^s \ge 1 - s \epsilon$,

which together imply that

$$
\left( 1 - \epsilon^2 \right)^{s/2}
\le \left( 1 - \epsilon \right)^s
\le 1 - s \epsilon.
$$

where we have used the Corollary 1.1 for the last inequality.

__Remark__. The geometric interpretation of Proposition 6 is that any blade formed as the
outer product of the $\B{v}_i$ almost lies completely within $\E_S$ (where $S$ is the set
of the indices of the vectors included into the outer product). As a consequence, blades of
the form $\B{V} = \bigwedge_{i \in S} \B{v}_i$ are almost equal to their projections onto
$\E_S$.

#### Corollary 6.1. $\cos \theta_S \ge (1 - s \epsilon) \left( 1 - \epsilon^2 \right)^{s/2} \ge (1 - s \epsilon)^2$

If $\theta_S$ is the angle between $\B{V}$ and the subspace $\E_S$, then
$\cos \theta_S \ge (1 - s \epsilon) \left( 1 - \epsilon^2 \right)^{s/2}$. A simpler but
looser bound is $\cos \theta_S \ge (1 - s \epsilon)^2$.

_Proof_. The result follows from the definition of $\cos \theta_S$:

$$
\cos \theta_S
= \frac{\norm{\proj{S}{\B{V}}}}{\norm{\B{V}}}
= \frac{\norm[S]{\B{V}}}{\norm{\B{V}}}.
$$

### Proposition 7. $\left( 1  - \frac{\sin \theta_S}{\cos \phi_i} \right) \le \frac{\norm{\rej{\B{V}}{\B{v}_i}}}{\abs{v_{ii}}} \le \frac{1}{\cos \phi_i}$ when $i \notin S$

Let $\B{V} = \bigwedge_{k \in S} \B{v}_k$. If $i \notin S$, then

$$
\left( 1  - \frac{\sin \theta_S}{\cos \phi_i} \right)
\le \frac{\norm{\rej{\B{V}}{\B{v}_i}}}{\abs{v_{ii}}}
\le \frac{1}{\cos \phi_i}.
$$

where $\theta_S$ is the angle between $\B{V}$ and $\E_S$.

_Proof_. The upper bound follows from the observation that
$\norm{\rej{\B{V}}{\B{v}_i}} \le \norm{\B{v}_i}$ and the definition of $\phi_i$:

$$
\frac{\norm{\rej{\B{V}}{\B{v}_i}}}{\abs{v_{ii}}}
\le \frac{\norm{\B{v}_i}}{\abs{v_{ii}}}
= \frac{1}{\cos \phi_i}.
$$

For the lower bound, consider decompositions of $\R^n$ into direct sums of orthogonal
subspaces: $\B{V} \oplus \dual{\B{V}}$ and $\E_S \oplus \dual{\E_S}$ [2,3]. Representing
$\B{v}_i$ in terms of these direct sums, we have

$$
\B{v}_i = \proj{\B{V}}{\B{v}_i} + \proj{\dual{\B{V}}}{\B{v}_i}
$$

and

$$
\B{v}_i = \proj{\B{\E_S}}{\B{v}_i} + \proj{\dual{\B{\E_S}}}{\B{v}_i}.
$$

Note $i \notin S$ implies that $\proj{\dual{\B{V}}}{\B{v}_i} \ne \B{0}$.

Using the inequality relationships between representations of vectors as orthogonal
projections in different orthogonal subspace pairs of the same dimension [4], we obtain
the following bound on the magnitudes of the projection of $\B{v}_i$ onto $\dual{\B{\E_S}}$:

$$
\norm{\proj{\dual{\B{\E_S}}}{\B{v}_i}}
\le \sin \theta_S \norm{\proj{\B{V}}{\B{v}_i}} + \norm{\proj{\dual{\B{V}}}{\B{v}_i}}
$$

where $\theta_S$ is the angle between $\B{V}$ and $\E_S$.

Rearranging this inequality, identifying $\proj{\dual{\B{V}}}{\B{v}_i}$ with
$\rej{\B{V}}{\B{v}_i}$, and observing that
$\norm{\proj{\B{V}}{\B{v}_i}} \le \norm{\B{v}_i}$ and
$\abs{v_{ii}} \le \norm{\proj{\dual{\B{\E_S}}}{\B{v}_i}}$
yields the lower bound

$$
\begin{align}
\norm{\rej{\B{V}}{\B{v}_i}}
&\ge \abs{v_{ii}} - \sin \theta_S \norm{\B{v}_i} \\
&= \abs{v_{ii}} \left( 1  - \sin \theta_S \frac{\norm{\B{v}_i}}{\abs{v_{ii}}} \right) \\
&= \abs{v_{ii}} \left( 1  - \frac{\sin \theta_S}{\cos \phi_i} \right),
\end{align}
$$

which is equivalent to the desired result.

__Remark__.

The geometric interpretation of Proposition 7 is that the magnitude of the orthogonal
projection of $\B{v}_i$ onto the blade formed by any $\B{V}$ not containing $\B{v}_i$ is
constrained by how close (1) $\B{v}_i$ is to $\e_i$ and (2) $\B{V}$ is to $\E_S$. When
$\phi_i$ and $\theta_S$ are both small, the magnitude of the projection of $\B{v}_i$ onto
$\B{V}$ is close to $\abs{v_{ii}}$ (the magnitude of the projection of $\B{v}_i$ onto
$\e_i$).

#### Corollary 7.1. Bounds on $\frac{\norm{\rej{\B{V}}{\B{v}_i}}}{\abs{v_{ii}}}$ for Nearly Orthogonal Vectors

If $s \epsilon \le 1$, then

$$
1 - \left(
      \frac{1 - (1 - s \epsilon)^2 \left(1 - \epsilon^2 \right)^s}{1 - \epsilon^2}
    \right)^{1/2}
\le \frac{\norm{\rej{\B{V}}{\B{v}_i}}}{\abs{v_{ii}}}
\le \left( 1 + \epsilon^2 \right).
$$

Simpler but looser lower bounds for $\frac{\norm{\rej{\B{V}}{\B{v}_i}}}{\abs{v_{ii}}}$ are

$$
\begin{align}
\frac{\norm{\rej{\B{V}}{\B{v}_i}}}{\abs{v_{ii}}}
&\ge 1 - \left( 1 + \epsilon^2 \right) \left( 1 - (1 - s \epsilon)^4 \right)^{1/2} \\
&\ge 1 - 2 \sqrt{s \epsilon} \left( 1 + \epsilon^2 \right)
\end{align}
$$

_Proof_. The upper bound follows because the assumption that the $\B{v}_i$ are
$\epsilon$-similar to the standard basis implies that

$$
\frac{1}{\cos \phi_i}
\le \frac{1}{\sqrt{1 - \epsilon^2}}
\le 1 + \epsilon^2.
$$

For the lower bound, then Corollary 6.1 implies that

$$
\sin^2 \theta_S
= 1 - \cos^2 \theta_S
\le 1 - (1 - s \epsilon)^2 \left(1 - \epsilon^2 \right)^s.
$$

when $s \epsilon \le 1$.

Combining this bound with the Corollary 1.1 leads to

$$
\frac{\sin^2 \theta_S}{\cos^2 \phi_i}
\le \frac{1 - (1 - s \epsilon)^2 \left(1 - \epsilon^2 \right)^s}{1 - \epsilon^2}.
$$

Therefore, we have the lower bound

$$
\begin{align}
\frac{\norm{\rej{\B{V}}{\B{v}_i}}}{\abs{v_{ii}}}
&\ge 1  - \frac{\sin \theta_S}{\cos \phi_i} \\
&\ge 1 - \left(
           \frac{1 - (1 - s \epsilon)^2 \left(1 - \epsilon^2 \right)^s}{1 - \epsilon^2}
         \right)^{1/2}
\end{align}
$$

The looser lower bounds follows because

$$
\begin{align}
1  - \frac{\sin \theta_S}{\cos \phi_i}
&\ge 1 - \left(
          \frac{1 - (1 - s \epsilon)^4}{1 - \epsilon^2}
        \right)^{1/2} \\
&\ge 1 - \left( 1 + \epsilon^2 \right)
         \left( 1 - (1 - s \epsilon)^4 \right)^{1/2} \\
&\ge 1 - \left( 1 + \epsilon^2 \right)
         \left( 1 - (1 - 4 s \epsilon) \right)^{1/2} \\
&= 1 - 2 \sqrt{s \epsilon} \left( 1 + \epsilon^2 \right)
\end{align}
$$

where the first inequality follows from the looser lower bound for $\cos \theta_S$ in
Corollary 6.1, the second inequality follows because
$\left(1 - \epsilon^2\right)^{-1/2} \le 1 + \epsilon^2$, and the third inequality follows
because $(1 - x)^n > 1 - nx$ for positive $x$ and $n$.

--------------------------------------------------------------------------------------------
## References

1. R.P. Brent, J.H. Osborn, W.D. Smith. "Note on best possible bounds for determinants of
   matrices close to the identity matrix" (2015).

2. S. Axler. "Linear Algebra Done Right" (2015).

3. A. Macdonald. "Linear and Geometric Algebra" (2010).

4. [[2022-09-14-Generalization-of-Orthogonal-Projection-Transformation-Formulas]]

--------------------------------------------------------------------------------------------
