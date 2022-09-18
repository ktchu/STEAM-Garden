---
tags: geometric-algebra, geometry
---

--------------------------------------------------------------------------------------------

2022-09-03: Bounds on Blades Formed From Nearly Orthogonal Vectors
------------------------------------------------------------------

_Author(s)_: Kevin Chu `<kevin@velexi.com>`

_Last Updated_: 2022-09-17

--------------------------------------------------------------------------------------------
### Summary

In this note, we derive bounds on the norm of blades formed from sets of nearly orthogonal
of vectors.

TODO

--------------------------------------------------------------------------------------------
### Notation

* $\newcommand{\R}{\mathbb{R}}$
  $\newcommand{\e}{\mathbf{e}}$
  The standard basis for $\R^n$: $\{ \e_1, \ldots, \e_n \}$

* $\newcommand{\sgn}[1]{\operatorname{sgn}\left({#1}\right)}$
  Sign of $x$: $\sgn{x}$

* __Blades__

  * $\newcommand{\B}[1]{\mathbf{#1}}$
    A blade: $\B{B}$ (uppercase, boldface)

  * $\newcommand{\norm}[2][2]{\left\Vert{#2}\right\Vert_{#1}}$
    The 2-norm of blade $\B{B}$: $\norm{\B{B}}$

  * $\newcommand{\dual}[1]{{#1}^\perp}$
    The orthogonal complement (i.e., dual) of blade $\B{B}$: $\dual{\B{B}}$

  * $\newcommand{\proj}[2]{P_{#1}\left({#2}\right)}$
    The orthogonal projection of blade $\B{A}$ onto the subspace represented by $\B{B}$:
    $\proj{\B{B}}{\B{A}}$

* __Vectors__

  * A vector: $\B{v}$ (lowercase, boldface)

  * The $i$-th component of vector $\B{v}$ with respect to the standard basis:
    $v_i$ (lowercase, lightface)

  * For indexed vector $\B{v}_i$, the $j$-th component of $\B{v}_i$: $v_{ij}$

* $\newcommand{\rej}[2]{\perp_{#1}\left({#2}\right)}$
  The rejection of vector $\B{v}$ from the subspace represented by $\B{B}$:
  $\rej{\B{B}}{\B{v}}$

* __Canonical Basis Blades__. Let $S$ be a subset of $\{1, \ldots, n\}$.

  * $\newcommand{\card}[1]{\left|{#1}\right|}$
    The cardinality of $S$: $\card{S}$

  * $\newcommand{\E}{\B{E}}$
    The blade formed by the standard basis vectors $\e_i$ with indices in $S$:
    $\E_S = \bigwedge_{k \in S} \e_k$

  * The projection of blade $\B{B}$ onto $\E_S$: $\proj{S}{\B{B}}$

  * The 2-norm of projection of blade $\B{B}$ onto $\E_S$:
    $\norm[S]{\B{B}} = \norm{\proj{S}{\B{B}}}$

--------------------------------------------------------------------------------------------
### Definitions

* __$\epsilon$-Similar Vector Sets__. For $\epsilon > 0$, two sets of vectors
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
### Assumptions

Throughout these notes, we assume the following:

* $\{\B{v}_1, \ldots, \B{v}_n\}$ is $\epsilon$-similar to the standard basis for $\R^n$
  under the identity permutation on the indices,

* $\phi_i$ is the angle formed between $\B{v}_i$ and $\e_i$,

* $S$ is a subset of $\{1, \ldots n\}$, and

* all angles between vectors and blades are taken to lie in the interval $[0, \pi/2]$.

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
### Propositions

#### Lemma 1. Bounds on Angles $\B{v}_i$, $\proj{S}{\B{v}_i}$, and $\e_i$

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

__Corollary__. If $i \in S$, then

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

#### Lemma 2. $\frac{\abs{v_{ij}}}{\norm[S]{\B{v}_i}} \le \epsilon$

If $i, j \in S$ and $i \ne j$,

$$
\frac{\abs{v_{ij}}}{\norm[S]{\B{v}_i}} \le \epsilon.
$$

_Proof_. Since $i, j \in S$, we can expand $\norm[S]{\B{v}_i}^2$ as

$$
\norm[S]{\B{v}_i}^2
= v_{ii}^2 + v_{ij}^2 + \sum_{k \in S, k \ne i,j} v_{ik}^2.
$$

Solving this equation for $v_{ij}^2$ yields

$$
\begin{align}
v_{ij}^2
&= \norm[S]{\B{v}_i}^2 - v_{ii}^2 - \sum_{k \in S, k \ne i,j} v_{ik}^2 \\
&\le \norm[S]{\B{v}_i}^2 - v_{ii}^2 \\
&= \norm[S]{\B{v}_i}^2 \left( 1 - \frac{v_{ii}^2}{\norm[S]{\B{v}_i}^2} \right) \\
&\le \epsilon^2 \norm[S]{\B{v}_i}^2.
\end{align}
$$

Rearranging and taking square roots yields the desired result.

__Corollary__. If $i \ne j$, then

$$
\frac{\abs{v_{ij}}}{\norm{\B{v}_i}} \le \epsilon.
$$

_Proof_. Taking $S = \{1, \ldots, n\}$ yields the desired result. Alternatively, the
result follows because $\norm[S]{\B{v}_i} \le \norm{\B{v}_i}$ implies that
$\frac{\abs{v_{ij}}}{\norm{\B{v}_i}} \le \frac{\abs{v_{ij}}}{\norm[S]{\B{v}_i}}$.

#### Lemma 3. $\abs{\frac{v_{ij}}{v_{ii}}} \le \epsilon (1 + \epsilon^2)$

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

__Remark__. TODO

* geometric interpetation as tangent of angle when $\B{v}_i$ is projected onto any
  two-dimensional subspace formed from two standard basis vectors when one of them is
  $\e_i$.

#### Proposition 4. $\norm[S]{\B{V}} \ge (1 - s \epsilon) \prod_{i \in S} \norm[S]{\B{v}_i}$

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

__Corollary__. If $\B{V} = \bigwedge_{i \in S} \B{v}_i$, then

$$
\norm{\B{V}} \ge (1 - s \epsilon) \prod_{i \in S} \norm[S]{\B{v}_i}.
$$

_Proof_. The result follows because $\norm{\B{V}} \ge \norm[S]{\B{V}}$.

#### Proposition 5. $\frac{\norm[S]{\B{V}}}{\norm{\B{V}}} \ge (1 - s \epsilon) \left( 1 - \epsilon^2 \right)^{s/2}$

Let $\B{V} = \bigwedge_{i \in S} \B{v}_i$. If $s \epsilon \le 1$, then

$$
\frac{\norm[S]{\B{V}}}{\norm{\B{V}}} \ge (1 - s \epsilon) \left( 1 - \epsilon^2 \right)^{s/2}.
$$

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

where we have used the corollary to Lemma 1 for the last inequality.

__Corollary__. If $\theta$ is the angle between $\B{V}$ and the subspace $\E_S$, then
$\cos \theta \ge (1 - s \epsilon) \left( 1 - \epsilon^2 \right)^{s/2}$. A simpler but
looser bound on $\cos \theta$ is $\cos \theta \ge (1 - s \epsilon)^2$.

_Proof_. The result follows from the definition of $\cos \theta$:

$$
\cos \theta
= \frac{\norm{\proj{S}{\B{V}}}}{\norm{\B{V}}}
= \frac{\norm[S]{\B{V}}}{\norm{\B{V}}}.
$$

The looser bound follows from the observations that

* $\sqrt{1 - \epsilon^2} \ge 1 - \epsilon$

  and

* $(1 - \epsilon)^2 \ge 1 - s \epsilon$,

which toegher imply that

$$
\left( 1 - \epsilon^2 \right)^{s/2}
\le \left( 1 - \epsilon \right)^s
\le 1 - s \epsilon.
$$



#### Proposition 6. $\norm{\rej{\B{V}}{\B{v}_i}} \ge \abs{v_{ii}} \left( 1  - \frac{\sin \theta}{\cos \phi_i} \right)$

Let $\B{V} = \bigwedge_{k \in S} \B{v}_k$. If $i \notin S$, then

$$
\norm{\rej{\B{V}}{\B{v}_i}}
\ge \abs{v_{ii}} \left( 1  - \frac{\sin \theta}{\cos \phi_i} \right)
$$

where $\theta$ is the angle between $\B{V}$ and $\E_S$.

_Proof_. Consider decompositions of $\R^n$ into direct sums of orthogonal subspaces:
$\B{V} \oplus \dual{\B{V}}$ and $\E_S \oplus \dual{\E_S}$ [2,3]. Representing $\B{v}_i$
in terms of these direct sums, we have

$$
\B{v}_i = \proj{\B{V}}{\B{v}_i} + \proj{\dual{\B{V}}}{\B{v}_i}
$$

and

$$
\B{v}_i = \proj{\B{\E_S}}{\B{v}_i} + \proj{\dual{\B{\E_S}}}{\B{v}_i}.
$$

Note $i \notin S$ implies that $\proj{\dual{\B{V}}}{\B{v}_i} \ne \B{0}$.

Using the inequality relationships between representations of vectors as orthogonal
projections in different orthogonal subspace pairs of the same dimension [4], we have the
following bound on the magnitudes of the projection of $\B{v}_i$ onto $\dual{\B{\E_S}}$:

$$
\norm{\proj{\dual{\B{\E_S}}}{\B{v}_i}}
\le \sin \theta \norm{\proj{\B{V}}{\B{v}_i}} + \norm{\proj{\dual{\B{V}}}{\B{v}_i}}
$$

where $\theta$ is the angle between $\B{V}$ and $\E_S$.

Rearranging this inequality, identifying $\proj{\dual{\B{V}}}{\B{v}_i}$ with
$\rej{\B{V}}{\B{v}_i}$, and observing that
$\norm{\proj{\B{V}}{\B{v}_i}} \le \norm{\B{v}_i}$ and
$\abs{v_{ii}} \le \norm{\proj{\dual{\B{\E_S}}}{\B{v}_i}}$
yields the lower bound

$$
\begin{align}
\norm{\rej{\B{V}}{\B{v}_i}}
&\ge \abs{v_{ii}} - \sin \theta \norm{\B{v}_i} \\
&= \abs{v_{ii}} \left( 1  - \sin \theta \frac{\norm{\B{v}_i}}{\abs{v_{ii}}} \right) \\
&= \abs{v_{ii}} \left( 1  - \frac{\sin \theta}{\cos \phi_i} \right).
\end{align}
$$

__Corollary__. If $s \epsilon \le 1$, then

$$
\norm{\rej{\B{V}}{\B{v}_i}}
\ge \abs{v_{ii}}
    \left[
      1 - \left(
            \frac{1 - (1 - s \epsilon)^2 \left(1 - \epsilon^2 \right)^s}{1 - \epsilon^2}
          \right)^{1/2}
   \right]
$$

Simpler but looser bounds for $\norm{\rej{\B{V}}{\B{v}_i}}$ are

$$
\begin{align}
\norm{\rej{\B{V}}{\B{v}_i}}
&\ge 1 - \left( 1 + \epsilon^2 \right) \left( 1 - (1 - s \epsilon)^4 \right)^{1/2} \\
&\ge \abs{v_{ii}} \left( 1 - 2 \sqrt{s \epsilon} \left( 1 + \epsilon^2 \right) \right)
\end{align}
$$

_Proof_. If $s \epsilon \le 1$, then corollary of Proposition 5 implies that

$$
\sin^2 \theta
= 1 - \cos^2 \theta
\le 1 - (1 - s \epsilon)^2 \left(1 - \epsilon^2 \right)^s.
$$

Combining this bound with the corollary to Lemma 1 leads to

$$
\frac{\sin^2 \theta}{\cos^2 \phi_i}
\le \frac{1 - (1 - s \epsilon)^2 \left(1 - \epsilon^2 \right)^s}{1 - \epsilon^2}.
$$

Therefore,

$$
\begin{align}
\norm{\rej{\B{V}}{\B{v}_i}}
&\ge \abs{v_{ii}} \left( 1  - \frac{\sin \theta}{\cos \phi_i} \right) \\
&\ge \abs{v_{ii}}
     \left[
       1 - \left(
             \frac{1 - (1 - s \epsilon)^2 \left(1 - \epsilon^2 \right)^s}{1 - \epsilon^2}
           \right)^{1/2}
    \right]
\end{align}
$$

The looser bounds follows because

$$
\begin{align}
1  - \frac{\sin \theta}{\cos \phi_i}
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

where the first inequality follows from the looser bound for $\cos \theta$ in the corollary
to Proposition 5, the second inequality follows because
$\left(1 - \epsilon^2\right)^{-1/2} \le 1 + \epsilon^2$, and the third inequality follows
because $(1 - x)^n > 1 - nx$ for positive $x$ and $n$.

--------------------------------------------------------------------------------------------
### References

1. R.P. Brent, J.H. Osborn, W.D. Smith. "Note on best possible bounds for determinants of
   matrices close to the identity matrix" (2015).

2. S. Axler. "Linear Algebra Done Right" (2015).

3. A. Macdonald. "Linear and Geometric Algebra" (2010).

4. [[2022-09-14-Generalization-of-Orthogonal-Projection-Transformation-Formulas]]

--------------------------------------------------------------------------------------------
