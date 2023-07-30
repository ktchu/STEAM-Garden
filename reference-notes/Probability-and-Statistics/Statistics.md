tatistics
==========

*Author(s)*: Kevin Chu `<kevin@velexi.com>`

__Last Updated__: 2023-07-27

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

* $\newcommand{\Cov}[1]{{\operatorname{Cov}}{\left(#1\right)}}$
  Covariance of $X$: $\Cov{X}$

--------------------------------------------------------------------------------------------

## 1. Parameter Estimation

#### 1.1. Bernoulli Parameter Estimation

Suppose that $x_1, x_2, \ldots, x_n \in \{0, 1\} $ is a random, independent samples drawn
from a Bernoulli distribution with parameter $p$ such that $m$ of the $x_i$ is equal to 1.
Two estimates $p$ include: the _Maximum Likelihood Estimate_ and the _Bayes Estimator_.

__Maximum Likelihood Estimate (MLE)__

The MLE for $p$ is the value of $p$ that maximizes the probability of observing
$x_1, x_2, \ldots, x_n$:

$$
\Pr{X_1 = x_1, X_2 = x_2, \ldots, X_n = x_n; p} = \prod_{i=1}^n p^{x_i} (1-p)^{1-x_i}.
$$

___Important Note___. The above expression is a function of $p$ and each of the $x_i$ is
known. In particular, the function is _not_ a probability or probability density in $p$. To
emphasize this interpretation, we introduce the _likelihood function_

$$
L(p; x_1, x_2, \ldots, x_n) = \Pr{X_1 = x_1, X_2 = x_2, \ldots, X_n = x_n; p},
$$

which is parameterized by the values of the observed samples $x_1, x_2, \ldots, x_n$.

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

___Advantages___

* TODO

___Disadvantages___

* TODO

__Bayes Estimation__

Bayes Estimation is based on two ideas: (1) that we can model the parameter $p$ as a random
variable $P$ and (2) that observations provide information (via Bayes rule) about the
distribution of $P$.

Using Bayes rule,

$$
\begin{align}
\Pr{P = p | X_1 = x_1, X_2 = x_2, \ldots, X_n = x_n}
&= \frac{
    \Pr{X_1 = x_1, X_2 = x_2, \ldots, X_n = x_n | P = p}
    \Pr{P = p}
  }{
    \Pr{X_1 = x_1, X_2 = x_2, \ldots, X_n = x_n}
  } \\
&= \frac{
    \left( \prod_{i=1}^n p^{x_i} (1-p)^{1-x_i} \right)
    \Pr{P = p}
  }{
    \int_0^1 \prod_{i=1}^n p^{x_i} (1-p)^{1-x_i} dp
  } \\
\end{align}
$$

When there is no prior information about $P$, $\Pr{P = p}$ is a uniform distribution on
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
definition of the $\beta$-function $B(m, n) = \int_0^1 x^{m-1} (1-x)^{n-1} dx$.

* __Point Estimate__

  To calculate a point estimate for $p$, we select a figure of merit (FoM) for each choice
  of $p$ and find the value of $p$ that optmizes the FoM.

  A common choice for the FoM is the mean square error (MSE): $\E{(P - p)^2}$. Expanding
  the expectation, taking the derivative of the MSE with respect to $p$, and setting the
  derivative equal to zero, we obtain

  $$
  \begin{align}
  0
  &= \frac{d \E{(P-p)^2}}{dp} \\
  &= \frac{d}{dp} \left( \E{P^2} - 2 \E{Pp} + \E{p^2} \right) \\
  &= \frac{d}{dp} \left( \E{P^2} - 2 \E{Pp} + \E{p^2} \right) \\
  &= \frac{d}{dp} \left( \E{P^2} - 2p \E{P} + p^2 \right) \\
  &= 0 - 2 \E{P} + 2p, \\
  \end{align}.
  $$

  which yields $p = \E{P}$ as the Bayes estimator (when the MSE is used as the FoM).

  * TODO: computation of $\E{P}$

* __Confidence Interval Estimate__

  * TODO

___Advantages___

* TODO
* Allows us to incorporate previous beliefs about $p$.
* Allows choice of error measure.

___Disadvantages___

* TODO


--------------------------------------------------------------------------------------------

## 5. References

1. TODO

--------------------------------------------------------------------------------------------

[----------------------------------- INTERNAL LINKS -----------------------------------]: #

[#5]: #5-references

[----------------------------------- EXTERNAL LINKS -----------------------------------]: #
