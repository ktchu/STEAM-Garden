Probability: Appendices
=======================

*Author(s)*: Kevin Chu `<kevin@velexi.com>`

__Last Updated__: 2022-07-24

--------------------------------------------------------------------------------------------

Table of Contents
-----------------

A. [Useful Mathematical Definitions and Results][#A]

B. [Useful Mathematical Identities and Inequalities][#B]

C. [Useful Mathematical Functions][#C]

--------------------------------------------------------------------------------------------

## 0. Notation

* $\newcommand{\R}{\mathbb{R}}$
  The set of real numbers: $\R$

* $\newcommand{\Pr}[1]{{\mathbb{P}\left[{#1}\right]}}$
  Probability of event $E$: $\Pr{E}$

* $\newcommand{\1}[1]{{\mathbf{1}_{\left\{{#1}\right\}}}}$
  Indicator for event $E$: $\1{E}$

* $\newcommand{\p}[1]{{p\left({#1}\right)}}$
  Probability density (or mass) function for a random variable $X$: $\p{x}$

* $\newcommand{\E}[1]{{\mathbb{E}\left[{#1}\right]}}$
  Expected value of $X$: $\E{X}$

* $\newcommand{\Var}[1]{{\operatorname{Var}}{\left(#1\right)}}$
  Variance of $X$: $\Var{X}$

* $\newcommand{\sd}[1]{\sigma{\left(#1\right)}}$
  Standard deviation of $X$: $\sd{X}$

* $\newcommand{\Cov}[1]{{\operatorname{Cov}}{\left(#1\right)}}$
  Covariance of $X$: $\Cov{X}$

--------------------------------------------------------------------------------------------

## Appendix A. Basic Results From Set Theory

* __De Morgan's Laws__. Let $A_1, \ldots, A_n$ be arbitrary sets.

  $$
  \left( \cup_{i=1}^n A_i \right)^c = \cap_{i=1}^n A_i^c \\
  \left( \cap_{i=1}^n A_i \right)^c = \cup_{i=1}^n A_i^c
  $$

* __Inclusion-Exclusion Principle__. Let $A_1, \ldots, A_n$ be arbitrary sets.

  $$
  \left| \bigcup_{i=1}^n A_i \right|
  = \sum_{\emptyset \ne J \subseteq \{1, \ldots, n\}}
    (-1)^{|J|+1} \left| \bigcap_{j \in J} A_j \right|
  $$

  _Important Special Case_. When the size of intersection of the sets in the
  inclusion-exclusion formula only depends on the number sets in the intersection and not
  the specific sets that appear, the inclusion-exclusion formula simplifies to

  $$
  \left| \bigcup_{i=1}^n A_i \right|
  = \sum_{k=1}^n (-1)^{k-1} {n \choose k} \alpha_k
  $$

  where $\alpha_k = \left| \bigcap_{j \in J} A_j \right|$ for all $J$ with $|J| = k$.

--------------------------------------------------------------------------------------------

## Appendix B. Useful Mathematical Identities and Inequalities

* __Minkowski's Inequality__. For $p \ge 1$,

  $$
  \E{|X + Y|^p})^{1/p}
  \le \left( \E{|X|^p} \right)^{1/p} + \left( \E{|Y|^p} \right)^{1/p}.
  $$

* __Cauchy-Schwarz Inequality__

  $$
  \E{XY} \le \left( \E{|X|^2} \right)^{1/2} \left( \E{|Y|^2} \right)^{1/2}.
  $$

* __Holder's Inequality__: If $p, q > 1$ are _conjugate exponents_ (i.e.,
  $1/p + 1/q = 1$), then

  $$
  \E{XY} \le \left( \E{|X|^p} \right)^{1/p} \left( \E{|Y|^q} \right)^{1/q}.
  $$

  _Note_: the Cauchy-Schwarz Inequality is a special case of Holder's Inequality.

--------------------------------------------------------------------------------------------

## Appendix C. Useful Mathematical Functions

* __Gamma Function__. The gamma function is defined as

  \[
    \Gamma(\alpha) = \int_0^\infty e^{-y} y^{\alpha - 1} dy
  \]

  * An important property of the gamma function is

    \[
      \Gamma(\alpha) = (\alpha - 1) \Gamma(\alpha - 1),
    \]

    which is straightforward to derive using integration by parts.

  * $\Gamma(n) = (n-1)!$ when $n$ is an integer.

--------------------------------------------------------------------------------------------

[----------------------------------- INTERNAL LINKS -----------------------------------]: #

[#A]: #appendix-a-basic-results-from-set-theory

[#B]: #appendix-b-useful-mathematical-identities-and-inequalities

[#C]: #appendix-c-useful-mathematical-functions

[----------------------------------- EXTERNAL LINKS -----------------------------------]: #
