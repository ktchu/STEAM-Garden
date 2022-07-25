Probability and Statistics: Common Distributions
================================================

*Author(s)*: Kevin Chu `<kevin@velexi.com>`

__Last Updated__: 2022-07-24

--------------------------------------------------------------------------------------------

Table of Contents
-----------------

1. [Binomial and Related Distributions][#1]

   1.1. [Bernoulli Distribution][#1.1]

   1.2. [Binomial Distribution][#1.2]

   1.3. [Geometric Distribution][#1.3]

2. [Poisson Distribution][#2]

3. [Gaussian and Related Distributions][#3]

   3.1 [Gaussian Distribution][#3.1]

   3.2 [Chi-Squared Distribution][#3.2]

4. [Exponential Distribution][#4]

5. [Gamma Distribution][#5]

6. [Additional Distributions][#6]

7. [References][#7]

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

## 1. Binomial and Related Distributions

### 1.1. Bernoulli Distribution

TODO

### 1.2. Binomial Distribution

TODO

### 1.3. Geometric Distribution

TODO

--------------------------------------------------------------------------------------------

## 2. Poisson Distribution

### Key Ideas

* Basic model for "event counting".

### Parameters

* $\lambda > 0$: average number of events

### Probability Distribution

\[
  P(x = k) = \frac{\lambda^k}{k!} e^{-\lambda}
\]

### Moment-Generating Function

\[
  M(t) = e^{\lambda(e^t - 1)}
\]

### Properties

* __Expected Value__: $\lambda$

* __Variance__: $\lambda$

* __Sum of Poisson Random Variables__. If $S$ is the sum of $N$ iid
  Poisson distributed random variables with parameter $\lambda$, then $S$ is
  a Poisson random variable with parameter $\lambda N$.

  * _Proof_

    \[
      M_S(t) = \prod_{k = 1}^N M_X(a_k t)
      = \prod_{k = 1}^N e^{\lambda(e^t - 1)}
      = e^{\lambda N (e^t - 1)}
    \]

--------------------------------------------------------------------------------------------

## 3. Gaussian and Related Distributions

### 3.1. Gaussian Distribution

#### Key Ideas

* The most commonly occurring probability distribution.

#### Parameters

* $\mu$: average

* $\sigma > 0$: standard deviation

#### Probability Distribution

\[
  P(x) = \frac{1}{\sqrt{2 \pi \sigma^2}} e^{-(x - \mu)^2 / 2 \sigma^2}
\]

#### Moment-Generating Function

\[
  M(t) = e^{\mu t + \sigma^2 t^2 / 2}
\]

#### Properties

* __Expected Value__: $\mu$

* __Variance__: $\sigma^2$

* __Sum of Gaussian Random Variables__. If $S = \sum_k a_k X_k$ is a
  linear combination of $N$ iid Gaussian distributed random variables $X_k$
  with parameters $\mu_k$ and $\sigma_k$, then $S$ is a Gaussian random
  variable with parameters $\mu = \sum_{k = 1}^N a_k \mu_k$ and
  $\sigma^2 = \sum_{k = 1}^N a_k^2 \sigma_k^2$.

  * _Proof_

    \[
      M_S(t) = \prod_{k = 1}^N M_X(a_k t)
      = \prod_{k = 1}^N
        \exp \left( a_k \mu_k t + a_k^2 \sigma_k^2 t^2 / 2 \right) \\
      = \exp\left(
          \left( \sum_{k = 1}^N a_k \mu_k \right) t +
          \left( \sum_{k = 1}^N k a_k^2 \sigma_k^2 \right) t^2 / 2
        \right)
    \]

### 3.2. Chi-Squared Distribution

TODO

--------------------------------------------------------------------------------------------

## 4. Exponential Distribution

### Key Ideas

* Basic model for "waiting time".

### Parameters

* $\lambda > 0$: event arrival rate

### Probability Distribution

\[
  P(x) = \left\{
      \begin{array}{ll}
        \lambda e^{-\lambda x} & x \ge 0 \\
        0                      & x < 0
      \end{array}
    \right.
\]

### Moment-Generating Function

\[
  M(t) = \frac{\lambda}{\lambda - t}
\]

### Properties

* __Expected Value__: $1 / \lambda$

* __Variance__: $1 / \lambda^2$

* __Memoryless__. $P(X > s+t | X > t) = P(X > s)$ for all $s, t \ge 0$.

  * In words, the probability that the waiting time is greater than $s + t$
    given the knowledge that the waiting time is greater than $t$ is equal
    the probability that the waiting time is greater than the additional
    time $s$.

  * Exponentially distributed random variables are the _only_ random variable
    that is memoryless.

* __Sum of Exponential Random Variables__. If $S$ is the sum of $N$ iid
  exponentially distributed random variables with parameter $\lambda$, then
  $S$ is a random variable that has a gamma distribution with parameters
  $(N, \lambda)$.

  * _Proof_

    \[
      M_S(t) = \prod_{k = 1}^N M_X(t)
      = \prod_{k = 1}^N \frac{\lambda}{\lambda - t}
      = \left( \frac{\lambda}{\lambda - t} \right)^N
    \]

* __Relationship to Poisson Processes__

  * TODO

--------------------------------------------------------------------------------------------

## 5. Gamma Distribution

### Key Ideas

* Basic model for sum of waiting times.

### Parameters

* $\alpha > 0$: number of events

  * _Note_: $\alpha$ does not need to be an integer

* $\lambda > 0$: event arrival rate

### Probability Distribution

\[
  P(x) = \left\{
      \begin{array}{ll}
        \frac{\lambda e^{-\lambda x} (\lambda x)^{\alpha - 1}}
             {\Gamma(\alpha)}                                   & x \ge 0 \\
        0                                                       & x < 0
      \end{array}
    \right.
\]

### Moment-Generating Function

\[
  M(t) = \left( \frac{\lambda}{\lambda - t} \right)^\alpha
\]

### Properties

* __Expected Value__: $\alpha / \lambda$

* __Variance__: $\alpha / \lambda^2$

* __Sum of Exponential Random Variables__. If $S$ is the sum of $N$ iid
  gamma distributed random variables with parameters $(\alpha_k, \lambda)$,
  then $S$ is a random variable that has a gamma distribution with parameters
  $(\sum_{k=1}^N \alpha_k, \lambda)$. Note that the $\lambda$ parameter must
  be the same for all of the random variables in the sum.

  * _Proof_

    \[
      M_S(t) = \prod_{k = 1}^N M_X(t)
      = \prod_{k = 1}^N \left( \frac{\lambda}{\lambda - t} \right)^{\alpha_k}
      = \left( \frac{\lambda}{\lambda - t} \right)^{\sum_{k = 1}^N \alpha_k}
    \]

--------------------------------------------------------------------------------------------

## 6. Additional Distributions

* Hypergeometric distribution

* Logistic distribution

--------------------------------------------------------------------------------------------

## 7. References

1. S.M. Ross. "Introduction to Probability and Statistics for Engineers and
   Scientists" (2004).

2. H.M. Taylor and S. Karlin. "An Introduction to Stochastic Modeling". (1998)

--------------------------------------------------------------------------------------------

[----------------------------------- INTERNAL LINKS -----------------------------------]: #

[#1]: #1-binomial-and-related-distributions
[#1.1]: #11-bernoulli-distribution
[#1.2]: #12-binomial-distribution
[#1.3]: #13-geometric-distribution

[#2]: #2-poisson-distribution

[#3]: #3-gaussian-and-related-distributions
[#3.1]: #31-gaussian-distribution
[#3.2]: #32-chi-squared-distribution

[#4]: #4-exponential-distribution

[#5]: #5-gamma-distribution

[#6]: #6-additional-distributions

[#7]: #7-references

[----------------------------------- EXTERNAL LINKS -----------------------------------]: #
