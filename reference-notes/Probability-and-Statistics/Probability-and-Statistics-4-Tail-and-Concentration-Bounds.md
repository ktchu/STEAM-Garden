Probability and Statistics: Tail and Concentration Bounds
=========================================================

*Author(s)*: Kevin Chu `<kevin@velexi.com>`

__Last Updated__: 2022-07-24

--------------------------------------------------------------------------------------------

Table of Contents
-----------------

1. [Basic Tail and Concentration Bounds][#1]

2. [Sub-Gaussian Distributions][#2]

3. [Sub-Exponential Distributions][#3]

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

## 1. Basic Tail and Concentration Bounds

* TODO: Notes
  * Useful for bounding tail probabilities by with expectation values

* __Markov's Inequality__. For nonnegative random variables,

  \[
    P(X \ge a) \le \frac{\mathbb{E} [X]}{a}
  \]

  * Markov's inequality yields a nice bound on the probability that $X$ is
    greater than a multiple its expected value:

    \[
      P(X \ge \alpha E[X]) \le 1 / \alpha.
    \]

* Chebyshev's inequality
  * TODO

* Bounds based on higher-order moments
  * TODO

* Chernoff bound
  * TODO

--------------------------------------------------------------------------------------------

## 2. Sub-Gaussian Distributions

### Key Ideas

* Useful for computing tail and concentration bounds of random variables.

* Many common probability distributions are sub-Gaussian.

### Definition

A random variable $X$ with mean $\mu = E[X]$ is _sub-Gaussian_ if there is a
positive number $\sigma$ such that

\[
E\left[ e^{\lambda (X - \mu)} \right] \le e^{\sigma^2 \lambda^2 / 2}
\text{ for all } \lambda \in \mathbb{R}.
\]

### Equivalent Characterizations

Let $X$ is a zero-mean random variable. Then the following properties are
equivalent.

* The moment-generating function satisfies the following bound:

  \[
    E\left[ e^{\lambda X} \right] \le e^{\lambda^2 \sigma^2 / 2}
    \text{ for all } \lambda \in \mathbb{R},
  \]

  where $\sigma$ is a constant.

* The tail probability of $X$ is bounded by a constant multiple greater
  than 1 of the tail probability for a Gaussian random variable
  $Z \sim \mathcal{N}(0, \tau^2)$:

  \[
    P(|X| \ge t) \le c P(|Z| \ge t)
    \text{ for all } t \ge 0,
  \]

  where $c \ge 1$.

* The even moments of $X$ satisy the following bound:

  \[
    E\left[ X^{2k} \right] \le \frac{(2k)!}{2^k k!} \theta^{2k}
    \text{ for all } k = 1, 2, \ldots
  \]

  where $\theta \ge 0$.

* The expectation value of $\exp \left(\frac{\lambda X^2}{2 \sigma^2}\right)$
  satisfies the following bound:

  \[
    E[ e^{\frac{\lambda X^2}{2 \sigma^2}} ]
    \le \frac{1}{\sqrt{1 - \lambda}}
    \text{ for all } 0 \le \lambda < 1.
  \]

### Properties

* A random variable $X$ is sub-Gaussian if and only if $-X$ is sub-Gaussian.

  _Proof_. If $X$ is sub-Gaussian, then

  \[
    E\left[ e^{\lambda (X - \mu)} \right] \le e^{\sigma^2 \lambda^2 / 2}
    \text{ for all } \lambda \in \mathbb{R},
  \]

  which is equivalent to

  \[
    E\left[ e^{-\lambda (X - \mu)} \right] \le e^{\sigma^2 \lambda^2 / 2}
    \text{ for all } \lambda \in \mathbb{R}.
  \]

  Let $Y = -X$. Then $E[Y] = -\mu$. In terms of $Y$ and $E[Y]$, the above
  inequality becomes

  \[
    E\left[ e^{\lambda (Y - E[Y])} \right] \le e^{\sigma^2 \lambda^2 / 2}
    \text{ for all } \lambda \in \mathbb{R}.
  \]

  Therefore $Y$ is sub-Gaussian. The same reasoning with $X$ replaced by
  $Y = -X$ yields the converse statement.

* If $X_1, \ldots, X_n$ are independent sub-Gaussian random variables with
  parameters $\sigma_1, \ldots, \sigma_n$, then any linear combination
  $Y = \alpha_1 X_1 + \cdots + \alpha_n X_n$ is sub-Gaussian with parameter
  $\sigma = \sqrt{\sum_i \alpha_i^2 \sigma_i^2}$.

  _Proof_. Let $\mu_i = E[X_i]$ so that $E[Y] = \sum_i \alpha_i \mu_i$. The
  following chain of equalities and inequalities yields the desired result:

  \[
    E\left[ e^{\lambda (Y - E[Y])} \right]
    = E\left[ e^{\lambda \left( \sum_i \alpha_i (X_i - \mu_i) \right)} \right]
    = \prod_i E\left[ e^{\lambda \alpha_i (X_i - \mu_i)} \right]
    = \prod_i E\left[ e^{\lambda \alpha_i (X_i - \mu_i)} \right] \\
    \le \prod_i e^{\sigma_i^2 (\lambda \alpha_i)^2 / 2}
    = \prod_i e^{\alpha_i^2 \sigma_i^2 \lambda^2 / 2}
    = e^{\left( \sum_i \alpha_i^2 \sigma_i^2 \right) \lambda^2 / 2}.
  \]

### Tail and Concentration Bounds

* If $X$ is a sub-Gaussian random variable with mean $\mu$, then

  * $P(X - \mu \ge t) \le e^{-\frac{t^2}{2 \sigma^2}}$

  * $P(X - \mu \le -t) \le e^{-\frac{t^2}{2 \sigma^2}}$

  * $P(|X - \mu| \ge t) \le 2 e^{-\frac{t^2}{2 \sigma^2}}$

  _Proof_.

  \[
  P(X - \mu \ge t)
  = P\left( e^{\lambda (X - \mu)} \ge e^{\lambda t} \right)
  \le \frac{ E\left[ e^{\lambda(X - \mu)} \right] }{ e^{\lambda t} }
  \le e^{\sigma^2 \lambda^2 / 2 - \lambda t}
  \]

  where the first inequality follows by applying Markov's inequality to the
  random variable $e^{\lambda (X - \mu)}$ and the second inequality follows
  because $X$ is sub-Gaussian. Minimizing $\lambda$ yields the Chernoff
  bound

  \[
  P(X - \mu \ge t) \le e^{-\frac{t^2}{2 \sigma^2}}.
  \]

  Because $-X$ is also sub-Gaussian, we can apply the same reasoning to $-X$
  to obtain

  \[
  P(X - \mu \le -t) = P(-X + \mu \ge t) \le e^{-\frac{t^2}{2 \sigma^2}}.
  \]

  Finally, combining these two tail bounds yields the concentration bound

  \[
  P(|X - \mu| \ge t)
  = P(X - \mu \ge t) + P(X - \mu \le -t)
  \le 2 e^{-\frac{t^2}{2 \sigma^2}}.
  \]

### Examples

* Gaussian random variables
  * TODO

* Rademacher variables
  * TODO

* Bounded random variables
  * TODO

--------------------------------------------------------------------------------------------

## 3. Sub-Exponential Distributions

### Key Ideas

* Useful for computing tail and concentration bounds of random variables.

* Many random variables that are not sub-Gaussian are sub-exponential.

### Definition

A random variable $X$ with mean $\mu = E[X]$ is _sub-exponential_ if there
are non-negative parameters $(\nu, b)$ such that

\[
E\left[ e^{\lambda (X - \mu)} \right] \le e^{\nu^2 \lambda^2 / 2}
\text{ for all } |\lambda| < \frac{1}{b}.
\]

### Equivalent Characterizations

Let $X$ is a zero-mean random variable. Then the following properties are
equivalent.

* The moment-generating function satisfies the following bound:

  \[
    E\left[ e^{\lambda X} \right] \le e^{\lambda^2 \nu^2 / 2}
    \text{ for all } |\lambda| < 1 / b
  \]

  where $\nu$ and $b$ are constants.

* $E[e^{\lambda X}]$ is finite for all $|\lambda| \le c$ for some constant
  $c > 0$.

* The tail probability of $X$ is bounded by an exponentially decaying function:

  \[
    P(|X| \ge t) \le c_1 e^{-c_2 t}
    \text{ for all } t \ge 0,
  \]

  where $c_1, c_2 \ge 0$.

* The moments of $X$ satisfy the property:

  \[
    \sup_{k \ge 2} \left( \frac{E[ X^k]}{k!} \right)^{1/k} < \infty.
  \]

### Properties
* A random variable $X$ is sub-exponential if and only if $-X$ is
  sub-exponential.

  _Proof_. If $X$ is sub-exponential, then

  \[
    E\left[ e^{\lambda (X - \mu)} \right] \le e^{\nu^2 \lambda^2 / 2}
    \text{ for all } |\lambda| < \frac{1}{b},
  \]

  which is equivalent to

  \[
    E\left[ e^{-\lambda (X - \mu)} \right] \le e^{\nu^2 \lambda^2 / 2}
    \text{ for all } |\lambda| < \frac{1}{b}.
  \]

  Let $Y = -X$. Then $E[Y] = -\mu$. In terms of $Y$ and $E[Y]$, the above
  inequality becomes

  \[
    E\left[ e^{\lambda (Y - E[Y])} \right] \le e^{\nu^2 \lambda^2 / 2}
    \text{ for all } |\lambda| < \frac{1}{b}.
  \]

  Therefore $Y$ is sub-exponential. The same reasoning with $X$ replaced by
  $Y = -X$ yields the converse statement.

* If $X_1, \ldots, X_n$ are independent sub-exponential random variables with
  parameters $(\nu_1, b_1), \ldots, (\nu_n, b_n)$, then any linear combination
  $Y = \alpha_1 X_1 + \cdots + \alpha_n X_n$ is sub-exponential with parameters
  $\left( \sqrt{\sum_i \alpha_i^2 \nu_i^2}, \max_i |\alpha_i| b_i \right)$.

  _Proof_. Let $\mu_i = E[X_i]$ so that $E[Y] = \sum_i \alpha_i \mu_i$. The
  following chain of equalities and inequalities yields the desired result:

  \[
    E\left[ e^{\lambda (Y - E[Y])} \right]
    = E\left[ e^{\lambda \left( \sum_i \alpha_i (X_i - \mu_i) \right)} \right]
    = \prod_i E\left[ e^{\lambda \alpha_i (X_i - \mu_i)} \right]
    = \prod_i E\left[ e^{\lambda \alpha_i (X_i - \mu_i)} \right] \\
    \le \prod_i e^{\nu_i^2 (\lambda \alpha_i)^2 / 2}
    = \prod_i e^{\alpha_i^2 \nu_i^2 \lambda^2 / 2}
    = e^{\left( \sum_i \alpha_i^2 \nu_i^2 \right) \lambda^2 / 2},
  \]

  where the inequality holds only if $|\lambda \alpha_i| < 1 / b_i$ for all
  $i$. Choosing $|\lambda| < \frac{1}{\max_i |\alpha_i| b_i}$ satisfies this
  requirement. Therefore, $Y$ is sub-exponential with parameters
  $\left( \sqrt{\sum_i \alpha_i^2 \nu_i^2}, \max_i |\alpha_i| b_i \right )$.

### Tail and Concentration Bounds

* TODO

### Examples

* Gaussian random variables
  * TODO

* Chi-squared random variables
  * TODO

* Bounded random variables
  * TODO

--------------------------------------------------------------------------------------------

## 4. References

1. R. Vershynin. "High-Dimensional Probability". (2018)

2. M.J. Wainwright. "High-Dimensional Statistics: A Non-Asymptotic Viewpoint". (2019)

--------------------------------------------------------------------------------------------

[----------------------------------- INTERNAL LINKS -----------------------------------]: #

[#1]: #1-basic-tail-and-concentration-bounds

[#2]: #2-sub-gaussian-distributions

[#3]: #3-sub-exponential-distributions

[#4]: #4-references

[----------------------------------- EXTERNAL LINKS -----------------------------------]: #

[wikipedia-characteristic-function]: https://en.wikipedia.org/wiki/Characteristic_function_(probability_theory)

[wikipedia-moment-generating-function]: https://en.wikipedia.org/wiki/Moment-generating_function
