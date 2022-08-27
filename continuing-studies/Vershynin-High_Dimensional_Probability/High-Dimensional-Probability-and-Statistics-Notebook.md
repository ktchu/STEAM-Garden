High-Dimensional Probability and Statistics Notes
=================================================

_Author(s)_: Kevin Chu `<kevin@velexi.com>`

_Last Updated_: 2022-06-11

--------------------------------------------------------------------------------------------

References
----------
* Vershynin. "High-Dimensional Probability". (2018)
* Wainwright. "High-Dimensional Statistics". (2019)

--------------------------------------------------------------------------------------------

## 0. Notation

* $\newcommand{\R}{\mathbb{R}}$
  The set of real numbers: $\R$

* $\newcommand{\Pr}[1]{\mathbb{P}\left[{#1}\right]}$
  Probability of event $E$: $\Pr{E}$

* $\newcommand{\1}[1]{\mathbf{1}_{\left\{{#1}\right\}}}$
  Indicator for event $E$: $\1{E}$

* $\newcommand{\p}[1]{p\left({#1}\right)}$
  Probability density (or mass) function for a random variable $X$: $\p{x}$

* $\newcommand{\E}[1]{\mathbb{E}[{#1}]}$
  Expected value of $X$: $\E{X}$

* $\newcommand{\Var}[1]{\operatorname{Var}{\left(#1\right)}}$
  Variance of $X$: $\Var{X}$

* $\newcommand{\sd}[1]{\sigma{\left(#1\right)}}$
  Standard deviation of $X$: $\sd{X}$

* $\newcommand{\cov}[1]{\operatorname{cov}{\left(#1\right)}}$
  Covariance of $X$: $\cov{X}$

--------------------------------------------------------------------------------------------

## 1. TODO

* __Rademacher Variable__ Let $X$ and $X'$ be i.i.d. random variables. The probability
  density function for $Y = X - X'$ is an even function: $\p{Y} = \p{-Y}$.

  _Proof_. TODO

--------------------------------------------------------------------------------------------

## Concentration Bounds

* The central limit theorem is not useful for concentration bounds of sums of i.i.d.
  random variables because the error in the approximation (i.e. the difference between
  the distribution for $S_N$ and a normal distribution) decays too slowly (i.e.,
  $O(1 / \sqrt{N})$) that it overwhelms the exponential decay rate of the Gaussian
  distribution.

  * (Berry-Esseen Central Limit Theorem) Let $X_1, X_2, \ldots$ be i.i.d. random varaibles
    with mean $\mu$ and variance $\sigma^2$. Define 

    $$
    Z_n = \frac{1}{\sigma \sqrt{n}} \sum_{i=1}^n (X_i - \mu)
    $$

    For every positive integer $n$ and $t \in \R$,

    $$
    \left| \Pr{Z_n \ge t} - \Pr{g \ge t} \right| \le \frac{\rho}{\sqrt{n}},
    $$

    where $\rho = \E{\left( |X_1 - \mu|^3 / \sigma^3 \right)}$ and $g \sim N(0, 1)$.

    _Remarks_

    * In general, this weak bound cannot be improved. 

    * This bound implies that we are only able to guarantee that the error between $Z_n$
      and a normally distributed variable is $O(1 / \sqrt{N})$.

--------------------------------------------------------------------------------------------
