Probability and Statistics: Limit Theorems
==========================================

*Author(s)*: Kevin Chu `<kevin@velexi.com>`

__Last Updated__: 2022-07-24

--------------------------------------------------------------------------------------------

Table of Contents
-----------------

1. [Law of Large Numbers][#1]

2. [Central Limit Theorem][#2]

3. [Poisson Limit][#3]

4. [References][#4]

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

### 1. Law of Large Numbers

* __Weak Law of Large Numbers__. TODO

* __Strong Law of Large Numbers__. Let $X_1, X_2, \ldots$ be a sequence of i.i.d. random
  variables with mean $\mu$. Define $S_N = X_1 + \cdots + X_N$. As $N \rightarrow \infty$,
  $\frac{S_N}{N} \rightarrow \mu$ almost surely.

* __Borel's Law of Large Numbers__. TODO
  * frequency of event --> probability of event

* TODO Law of large numbers
  * Proofs using both Chebyshev's Inequality and characteristic function

--------------------------------------------------------------------------------------------

### 2. Central Limit Theorem

* __Central Limit Theorem__ (Lindeberg-Levy). Let $X_1, X_2, \ldots$ be a sequence of
  i.i.d. random variables with mean $\mu$ and variance $\sigma^2$. Define
  $S_N = X_1 + \cdots + X_N$ and

  $$
  Z_n = \frac{S_N - \E{S_N}}{\sigma_N}
  $$

  where $\sigma_N^2 = \Var{S_N} = N \sigma^2$.

  * TODO: Proof of Central Limit Theorem

--------------------------------------------------------------------------------------------

### 3. Poisson Limit

* __Poisson Limit of Sums of Bernoulli Random Variables__. For each $n$, let
  $X_{n,1}, X_{n,2}, \ldots, X_{n,n}$ be a sequence of Bernoulli random variables such
  that

  $$
  \Pr{X_{n, i} = 1} = p_{n, i}.
  $$

  Define

  $$
  S_n = \sum_{i=1}^n X_{n, i}.
  $$

  Suppose that

  $$
  \max_{i \le n} p_{n, i} \rightarrow 0
  $$

  and

  $$
  \E{S_n} = \sum_{i=1}^n p_{n, i} \rightarrow \lambda < \infty
  $$

  as $n \rightarrow \infty$.

  Then $S_n \rightarrow \operatorname{Pois}(\lambda)$ as $n \rightarrow \infty$.

--------------------------------------------------------------------------------------------

## 4. References

1. S.M. Ross. "Introduction to Probability and Statistics for Engineers and
   Scientists" (2004).

2. R. Vershynin. "High-Dimensional Probability". (2018)

--------------------------------------------------------------------------------------------

[----------------------------------- INTERNAL LINKS -----------------------------------]: #

[#1]: #1-law-of-large-numbers

[#2]: #2-central-limit-theorem

[#3]: #3-poisson-limit

[#4]: #4-references

[----------------------------------- EXTERNAL LINKS -----------------------------------]: #
