Probability and Statistics: Special Topics
==========================================

*Author(s)*: Kevin Chu `<kevin@velexi.com>`

__Last Updated__: 2022-07-24

--------------------------------------------------------------------------------------------

Table of Contents
-----------------

1. [TODO][#1]

5. [References][#5]

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

* $\newcommand{\cov}[1]{{\operatorname{cov}}{\left(#1\right)}}$
  Covariance of $X$: $\cov{X}$

--------------------------------------------------------------------------------------------

## 1. Geometric Perspective for Random Variables

* Random variable is a vector space

* Norm: $\Vert X \Vert_{L^p} = \left( E\left[ |X|^p \right] \right)^{1/p}$
  where $p \in [1, \infty]$.

  * Triangle inequality property follows from Minkowski's inequality.

  * $\Vert X \Vert_{L^p}$ is an increasing function of $p$. If $q > p$,

    $$
    \Vert X \Vert_{L^p} \le \Vert X \Vert_{L^q}.
    $$

    _Proof_. If $q \ge p$, Jensen's inequality implies that

    $$
    \left( \E{X^p}\right)^{q/p} \le \E{X^q},
    $$

    which is equivalent to the desired inequality.

* Geometric Representation of Probability Concepts

  * $\Var{X} = \Vert X \Vert_{L^2}^2$

  * $\cov{X} = \langle X - \E{X}, Y - \E{Y} \rangle_{L^2}$

  * Minkowski's inequality

  * Cauchy-Schwarz inequality

  * Holder's inequality

--------------------------------------------------------------------------------------------

## 5. References

1. R. Vershynin. "High-Dimensional Probability". (2018)

2. M.J. Wainwright. "High-Dimensional Statistics: A Non-Asymptotic Viewpoint". (2019)

--------------------------------------------------------------------------------------------

[----------------------------------- INTERNAL LINKS -----------------------------------]: #

[#5]: #5-references

[----------------------------------- EXTERNAL LINKS -----------------------------------]: #
