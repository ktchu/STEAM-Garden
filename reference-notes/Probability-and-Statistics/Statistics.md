Statistics
==========

*Author(s)*: Kevin Chu `<kevin@velexi.com>`

__Last Updated__: 2023-07-31

--------------------------------------------------------------------------------------------

Table of Contents
-----------------

1. [Parameter Estimation][#1]

2. [References][#2]

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

## 1. Parameter Estimation

### 1.1. Parameter Estimation Methods

The goal of parameter estimation is to estimate the parameters
$\{ \theta_1, \ldots, \theta_k \}$ of a probability distribution from a set of i.i.d.
observations $x_1, x_2, \ldots, x_n \in \{0, 1\}$ drawn from the probability distribution.

#### 1.1.1. Maximum Likelihood Estimate

The _maximum likelihood estimate_ (MLE) selects the set of parameters
$\{ \theta_1, \ldots, \theta_k \}$ that maximize the probability of observing
$x_1, x_2, \ldots, x_n$:

$$
\Pr{X_1 = x_1, X_2 = x_2, \ldots, X_n = x_n; \theta_1, \ldots, \theta_k}.
$$

___Important Note___. The above expression is a function of $(\theta_1, \ldots, \theta_k)$
and each of the $x_i$ is known. In particular, the function is _not_ a probability or
probability density in $(\theta_1, \ldots, \theta_k)$. To emphasize this interpretation,
we introduce the _likelihood function_

$$
L(\theta_1, \ldots, \theta_k; x_1, x_2, \ldots, x_n)
= \Pr{X_1 = x_1, X_2 = x_2, \ldots, X_n = x_n; \theta_1, \ldots, \theta_k},
$$

which is parameterized by the values of the observed samples $x_1, x_2, \ldots, x_n$.

___Advantages___

* No arbitrariness in the point estimate.

___Disadvantages___

* Not readily extended to provide confidence interval estimates.

#### 1.1.2. Bayes Estimator

The _Bayes estimator_ is based on two ideas: (1) that we can model the parameters
$\{ \theta_1, \ldots, \theta_k \}$ as random variables $\{ \Theta_1, \ldots \Theta_k \}$
and (2) that observations provide information (via Bayes rule) about the distribution of
$\{ \Theta_1, \ldots \Theta_k \}$.

Using Bayes rule,

$$
\Pr{\Theta_1 = \theta_1, \ldots, \Theta_k = \theta_k
    | X_1 = x_1, X_2 = x_2, \ldots, X_n = x_n}
= \frac{
    \Pr{X_1 = x_1, X_2 = x_2, \ldots, X_n = x_n
        | \Theta_1 = \theta_1, \ldots, \Theta_k = \theta_k}
    \times \Pr{\Theta_1 = \theta_1, \ldots, \Theta_k = \theta_k}
  }{
    \Pr{X_1 = x_1, X_2 = x_2, \ldots, X_n = x_n}
  }.
$$

The factor $\Pr{\Theta_1 = \theta_1, \ldots, \Theta_k = \theta_k}$ encodes any prior
information or beliefs about $(\Theta_1, \ldots, \Theta_k)$. When there is no prior
information about $(\Theta_1, \ldots \Theta_k)$, it is common to assume that
$\Pr{\Theta_1 = \theta_1, \ldots, \Theta_k = \theta_k}$ is a uniform distribution on the
parameter space for $(\Theta_1, \ldots, \Theta_k)$.

To calculate a point estimate for $p$, we select a figure of merit (FoM) for each choice
of $(\theta_1, \ldots, \theta_k)$ and find the value of $(\theta_1, \ldots, \theta_k)$
that optmizes the FoM. A common choice for the FoM is the mean square error (MSE):
$\E{\sum_{i=1}^k (\Theta_i - \theta_i)^2}$.  Expanding the expectation, taking the
gradient of the MSE with respect to $(\theta_1, \ldots, \theta_k)$, and setting the
gradent equal to zero, we obtain

$$
\begin{align}
0
&= \frac{d \E{(\Theta_i - \theta_i)^2}}{d\theta_i} \\
&= \frac{d}{d\theta_i} \left(
     \E{\Theta_i^2} - 2 \E{\Theta_i \theta_i} + \E{\theta_i^2}
   \right) \\
&= \frac{d}{d\theta_i} \left(
     \E{\Theta_i^2} - 2\theta_i \E{\Theta_i} + \theta_i^2
   \right) \\
&= 0 - 2 \E{\Theta_i} + 2\theta_i, \\
\end{align}.
$$

which yields $\theta_i = \E{\Theta_i}$ as the Bayes estimator (when the MSE is used as the
FoM).

___Advantages___

* Amenable to incorporation of previous beliefs about $(\Theta_1, \ldots, \Theta_k)$.
* Flexible choice of the figure of merit when computing a point estimate for
  $(\theta_1, \ldots, \theta_k)$.
* Readily extended to provide confidence interval estimates.

___Disadvantages___

* The figure of merit used for point estimation is an arbitrary choice.

### 1.2. Bernoulli Parameter Estimation

Suppose that $x_1, x_2, \ldots, x_n \in \{0, 1\}$ is a random, independent samples drawn
from a Bernoulli distribution with parameter $p$ such that $m$ of the $x_i$ are equal to 1.

#### Maximum Likelihood Estimate (MLE)

The MLE for $p$ is the value of $p$ that maximizes the likelihood function for $p$ (i.e.,
the probability of observing $x_1, x_2, \ldots, x_n$):

$$
L(p; x_1, x_2, \ldots, x_n)
= \Pr{X_1 = x_1, X_2 = x_2, \ldots, X_n = x_n; p}
= \prod_{i=1}^n p^{x_i} (1-p)^{1-x_i}.
$$

To find the MLE for $p$, it is convenient to work with $\log L(p)$, which has the same
maximum as $L(p)$:

$$
\log L = \sum_{i=1}^n x_i \log p - (1-x_i) \log (1-p).
$$

Taking the derivative of $\log L$, we obtain

$$
\frac{d \log L}{dp} = \sum_{i=1}^n \frac{x_i}{p} + \frac{1-x_i}{1-p}.
$$

Setting the derivative equal to zero and observing that $\sum_{i=1}^n = m$ yields

$$
0 = \frac{m}{p} + \frac{n-m}{1-p},
$$

which implies that $p = m / n$.

#### Bayes Estimation

Using Bayes rule, the posterior probability distribution for $p$ given the observations
$x_1, \ldots, x_n$ is

$$
\begin{align}
\Pr{P = p | X_1 = x_1, X_2 = x_2, \ldots, X_n = x_n}
&= \frac{
    \Pr{X_1 = x_1, X_2 = x_2, \ldots, X_n = x_n | P = p} \times \Pr{P = p}
  }{
    \Pr{X_1 = x_1, X_2 = x_2, \ldots, X_n = x_n}
  } \\
&= \frac{
    \left( \prod_{i=1}^n p^{x_i} (1-p)^{1-x_i} \right) \times \Pr{P = p}
  }{
    \int_0^1 \prod_{i=1}^n p^{x_i} (1-p)^{1-x_i} dp
  } \\
\end{align}
$$

Assuming no prior information about $P$, $\Pr{P = p}$ is a uniform distribution on
$[0, 1]$, so the posterior probability becomes

$$
\begin{align}
\Pr{P = p | X_1 = x_1, X_2 = x_2, \ldots, X_n = x_n}
&= \frac{
    \prod_{i=1}^n p^{x_i} (1-p)^{1-x_i}
  }{
    \int_0^1 \prod_{i=1}^n p^{x_i} (1-p)^{1-x_i} dp
  } \\
&= \frac{ p^m (1-p)^{n-m} }{ \int_0^1 p^m (1-p)^{n-m} dp } \\
&= \frac{ p^m (1-p)^{n-m} }{ B(m+1, n-m+1) } \\
\end{align}
$$

where the last step follows from the observation that $\sum_{i=1}^n x_i = m$ and the
definition of the beta function $B(m, n) = \int_0^1 x^{m-1} (1-x)^{n-1} dx$.

* __Point Estimate__. Using the MSE as the FoM for $p$, the Bayes estimator for $p$ is
  equal to $\E{P}$:

  $$
  \begin{align}
  \E{P}
  &= \int_0^1 p \left( \frac{ p^m (1-p)^{n-m} }{ B(m+1, n-m+1) } \right) dp \\
  &= \int_0^1 \frac{ p^{m+1} (1-p)^{n-m} }{ B(m+1, n-m+1) } dp \\
  &= \frac{ B(m+2, n-m+1) }{ B(m+1, n-m+1) }.
  \end{align}
  $$

  Expressing the beta function in terms of the gamma function,

  $$
  \begin{align}
  \frac{ B(m+2, n-m+1) }{ B(m+1, n-m+1) }
  &= \frac{ \Gamma(m+2) \Gamma(n-m+1) }{\Gamma(n+3)} \times
     \frac{ \Gamma(n+2) }{ \Gamma(m+1) \Gamma(n-m+1) } \\
  &= \frac{ \Gamma(m+2) \Gamma(n+2) }{ \Gamma(m+1) \Gamma(n+3) } \\
  &= \frac{ m+1 }{ n+2 }.
  \end{align}
  $$

* __Confidence Interval Estimate__. Since the Bernoulli distribution has only one
  parameter, we can use the posterior probability distribution to compute confidence
  intervals for $p$. The confidence interval for $p$ at confidence level $\alpha$ is the
  interval $[r, s]$ where $r$ and $s$ are solutions to the equations:

  $$
  \begin{align}
  \frac{1}{2} \left( 1 -\frac{\alpha}{100} \right)
  &= \int_0^r \frac{ p^m (1-p)^{n-m} }{ B(m+1, n-m+1) } dp \\
  \frac{1}{2} \left( 1 -\frac{\alpha}{100} \right)
  &= \int_s^1 \frac{ p^m (1-p)^{n-m} }{ B(m+1, n-m+1) } dp. \\
  \end{align}
  $$


--------------------------------------------------------------------------------------------

## 2. References

1. TODO

--------------------------------------------------------------------------------------------

[----------------------------------- INTERNAL LINKS -----------------------------------]: #

[#1]: #1-parameter-estimation

[#2]: #2-references

[----------------------------------- EXTERNAL LINKS -----------------------------------]: #
