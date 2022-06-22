Probability and Statistics
==========================

*Author(s)*: Kevin Chu `<kevin@velexi.com>`

__Last Updated__: 2022-06-03

--------------------------------------------------------------------------------------------

Table of Contents
-----------------

1. [Fundamental Concepts][#1]

    1.1. [Characteristic and Moment-Generating Functions][#1.1]

    1.2. [Useful Mathematical Relations][#1.2]

    3.1. [Geometric][#3.1]

2. [Important Probability Distributions][#2]

3. [Limit Theorems][#3]

4. [Tail and Concentration Bounds][#4]

    4.1. [Basic Tail and Concentration Bounds][#4.1]

    4.2. [Sub-Gaussian Random Variables][#4.2]

    4.3. [Sub-Exponential Random Variables][#4.3]

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

## 1. Fundamental Concepts

### 1.1. Basic Concepts of Probability Theory

* ___Union of Disjoint Events___. If $A_1, A_2, \ldots$ are disjoint events, then
  $\Pr{A_1 \cup A_2 \cup \cdots} = \sum_{i=1}^\infty \Pr{A_i}$.

* ___Law of Total Probability___. Let $A_1, A_2, \ldots$ be disjoint events. For any event
  $B$, $\Pr{B} = \sum_{i=1}^\infty \Pr{B \cap A_i}$.

* ___Independence___. Events $A_1, A_2, \ldots$ are _independent_ if and only if
  $\Pr{A_{i_1} \cap \cdots \cap A_{i_n}} = \Pr{A_{i_1}} \cdots \Pr{A_{i_n}}$ for any finite
  subset of the events $A_i$.

* ___Conditional Probability___. Let $A$ and $B$ be two events. When $\Pr{B} > 0$, the
  _conditional probability_ of $A$ given $B$, denoted by $\Pr{A|B}$ is equal to

  $$
  \Pr{A|B} = \frac{\Pr{A}}{\Pr{A \cap B}}.
  $$

  When $\Pr{B} = 0$, the conditional probability of $A$ given $B$ is undefined.

* ___Inclusion-Exclusion Principle___. Let $A_1, \ldots, A_n$ be arbitrary events.

  $$
  \Pr{\bigcup_{i=1}^n A_i}
  = \sum_{k=1}^n
    (-1)^{k-1} \sum_{J \subseteq \{1, \ldots, n\}, |J|=k} \Pr{\bigcap_{j \in J} A_j}
  $$

  * In the context of set theory, the inclusion-exclusion principle is expressed as

    $$
    \left| \bigcup_{i=1}^n A_i \right|
    = \sum_{\emptyset \ne J \subseteq \{1, \ldots, n\}}
      (-1)^{|J|+1} \left| \bigcap_{j \in J} A_j \right|
    $$


* ___De Morgan's Laws___. Let $A_1, \ldots, A_n$ be arbitrary events.

  $$
  \left( \cup_{i=1}^n A_i \right)^c = \cap_{i=1}^n A_i^c \\
  \left( \cap_{i=1}^n A_i \right)^c = \cup_{i=1}^n A_i^c
  $$

### 1.2. Random Variables

#### Definitions

* ___Random Variable___. A variable $X$ whose value is randomly selected from a probability
  distribution defined by one of the following functions.

  * _Cumulative Distribution Function (CDF)_. The _cumulative distribution function_,
    denoted by $F_X(x)$, is the probability that a random variable $X$ is no more than $x$:

    $$
    F_X(x) = \Pr{X \le x}
    $$

  * _Probability Density Function_. When $X$ is a _continous random variable_, the
    probability distribution may be specified by a _probability density function_, denoted
    by $\p{x}$:

    $$
    \p{x} = \frac{d F_X}{dx}.
    $$

    Informally, we can express the probability that $X$ lies in an infintesimally small
    interval around $x$ by

    $$
    \Pr{x < X \le x + dx} = p(x) dx.
    $$

  * _Probability Mass Function_.  When $X$ is a _discrete random variable_, the probability
    distribution may be specified by a _probability mass function_, denoted by $\p{x}$:

    $$
    \p{x} = \Pr{X = x}.
    $$

* ___Expected Value___. The _expected value_ of a random variable $X$, denoted $\E{X}$,
  is equal to

  $$
  \E{X} = \sum_{i} x_i \Pr{X = x_i} = \sum_{i} x_i \p{x_i}
  $$

  when $X$ is a discrete random variable and

  $$
  \E{X} = \int_{-\infty}^\infty x \p{x} dx
  $$

  when $X$ is a continuous random variable.

* ___Moments___. The $m$-th moment of $X$ is defined as $\E{X^m}$.

  * _Central Moments_. The $m$-th central moment of $X$ is defined as
    $\E{\left( X - \E{X} \right)^m}$.

  * _Absolute Moments_. The $m$-th absolute moment of $X$ is defined as $\E{|X|^m}$.

  * __Important Moments__

    * _Expected Value, Mean, Average_: the first moment of $X$, $\E{X}$

    * _Variance_: the second central moment of $X$

      $$
      \Var{X} = \E{\left( X - \E{X} \right)^2}
      $$

  * __Related Quantities__

    * _Standard Deviation_. The _standard deviation_ of $X$, denoted $\sd{X}$, is defined
      as

      $$
      \sd{X} = \sqrt{\Var{X}}
      $$

    * _Covariance_: the _covariance_ of two random variables $X$ and $Y$ is defined as

      $$
      \cov{X} = \E{ \left(\left( X - \E{X} \right) \left( Y - \E{Y} \right)\right) }
      $$

* ___Moment Generating Function___: $\E{e^{tX}}$, where $t \in \R$

* ___Tail Probability___: $\Pr{X > x} = 1 - F_X(x)$

* ___Uncorrelated___. TODO

  * Independent implies uncorrelated.

  * Uncorrelated does not imply independent.

### 1.2. Important Identities and Inequalities

* ___Jensen's Inequality___. If $f$ is a convex function, then

  $$
  f(\E{X}) \le \E{f(X)}.
  $$

* ___Minkowski's Inequality___. For $p \ge 1$,

  $$
  \E{|X + Y|^p})^{1/p}
  \le \left( \E{|X|^p} \right)^{1/p} + \left( \E{|Y|^p} \right)^{1/p}.
  $$

* ___Cauchy-Schwarz Inequality___

  $$
  \E{XY} \le \left( \E{|X|^2} \right)^{1/2} \left( \E{|Y|^2} \right)^{1/2}.
  $$

* ___Holder's Inequality___: If $p, q > 1$ are _conjugate exponents_ (i.e.,
  $1/p + 1/q = 1$), then

  $$
  \E{XY} \le \left( \E{|X|^p} \right)^{1/p} \left( \E{|Y|^q} \right)^{1/q}.
  $$

* ___Expected Value in Terms of Tail Probabilities___. The expected value of a random
  variable can be expressed as an integral or sum over tail probabilities. These identities
  can be useful for bounding expectation values by tail probabilities.

  * __Discrete Random Variables__ (Taylor and Karlin, Section I.5.1). Let $X$ be a
    non-negative discrete random variable. Then

    $$
    \E{X} = \sum_{k=0}^\infty \Pr{X > k} = \sum_{k=1}^\infty \Pr{X \ge k}
    $$

    _Proof_. Observe that any non-negative integer $n$ can be expressed as the sum

    $$
    n = \sum_{k=0}^\infty \1{k < n}.
    $$

    Substituting the random variable $X$ and taking expectation yields

    $$
    \E{X}
    = \E{ \sum_{k=0}^\infty \1{k < X} }
    = \sum_{k=0}^\infty \E{ \1{k < X} }
    = \sum_{k=0}^\infty \Pr{X > k}
    $$

    The alternate sum over tail probabilities follows by shifting the summation index by
    1 or using the identity

    $$
    n = \sum_{k=1}^\infty \1{k \le n}.
    $$

  * __Continuous Random Variables__ (Vershynin, Lemma 1.2.1). Let $X$ be a non-negative
    continuous random variable. Then

    $$
    \E{X} = \int_0^\infty \Pr{X > t} dt.
    $$

    * _Corollary: Moments in Terms of Tail Probabilities_

      $$
      \E{ |X|^\alpha } = \alpha \int_0^\infty t^{\alpha - 1} \Pr{|X| > t} dt
      $$

      _Proof 1_. From the integral identity, we have

      $$
      \E{ |X|^\alpha } = \int_0^\infty \Pr{|X|^\alpha > s} ds.
      $$

      Using the change of variables $s = t^\alpha$ yields the desired result:

      $$
      \mathbb{E} |X|^\alpha
      = \alpha \int_0^\infty t^{\alpha-1} \Pr{ |X|^\alpha > t^\alpha } dt
      = \alpha \int_0^\infty t^{\alpha-1} \Pr{ |X| > t } dt.
      $$

      _Proof 2_. Direct computation of the expected value.

      $$
      \E{ |X|^\alpha } = \int_0^\infty |x|^\alpha \p{x} dx.
      $$

      Expressing $|x|^\alpha$ as the integral

      $$
      \alpha \int_0^{|x|} t^{\alpha - 1} dt,
      $$

      we obtain

      $$
      \E{ |X|^\alpha }
      = \int_0^\infty \left(\alpha \int_0^{|x|} t^{\alpha - 1} dt \right) \p{x} dx
      = \alpha \int_0^\infty \int_0^{|x|} t^{\alpha - 1} \p{x} dt dx.
      $$

      Finally, interchanging the order of integration yields the desired result

      $$
      \E{ |X|^\alpha }
      = \alpha \int_0^\infty \int_t^\infty \p{x} dx t^{\alpha - 1} dt
      = \alpha \int_0^\infty t^{\alpha - 1} \Pr{|X| > t} dt
      $$

    * __Generalization: Arbitrary Random Variable $X$__

      $$
      \E{X} = \int_0^\infty \Pr{X > t} dt - \int_{-\infty}^0 \Pr{X < t} dt
      $$

#### Important Properties/Results

* Expectation

  * Linearity of Expectation

    * Important observation: holds regardless of dependencies between random variables
      in sum.

  * Existence of expectation value implies existence of

    * at least one instance of the random variable no greater than expectation value

    * at least one instance of the random variable no less than expectation value

* Union Bound

### 1.1. Characteristic and Moment-Generating Functions

#### Definitions

* __Characteristic Function__: expectation value of $e^{itX}$ of a random
  variable $X$ (essentially the Fourier transform of the probability density
  function).

  \[
    \phi(t) = \E{e^{itX}} = \int_{-\infty}^\infty e^{-itx} P(x) dx
  \]

  ___Note___: the characteristic function exists for all probability density
  functions.

* __Moment-Generating Function__: expectation value of $e^{tX}$ of a random
  variable $X$.

  \[
    M(t) = \int_{-\infty}^\infty e^{tx} P(x) dx
  \]

  ___Note___: the moment-generating function may not exist for all probability
  density functions.

#### Properties

* Both the characteristic function and the moment-generating function
  _completely define_ the probability distribution of a random variable.

  * If two probability distributions have the same characteristic function,
    then they are identical (except possibly on a set of measure zero).

  * If two probability distributions have the same moment-generating function,
    then they are identical (except possibly on a set of measure zero).

* When a random variable has a moment-generating function $M(t)$, then the
  characteristic function $\phi(t)$ can be extended to the complex plane and
  $M(t) = \phi(-it)$.

* The moment-generating function is bounded below by $e^{\mu t}$ where
  $\mu$ is the mean of $X$: $M(t) \ge e^{\mu t}$.

  * This bound follows directly from Jensen's inequality because $e^{tx}$
    is a convex function of $x$.

#### Uses

* __Probability Distributions of Sums of Independent Random Variables__

  * Characteristic and moment-generating functions are useful for calculating
    the probability distributions of linear combinations of independent
    random variables.

  * Let $S = \sum a_k X_k$ where $X_k$ are independent random variables and
    $a_k$ are constants. Then, the characteristic function for $S$ is given by

    \[
      \phi(t) = E[e^{itS}]
      = E[e^{\sum_{k = 1}^N it a_k x_k}]
      = E\left[ \prod_{k = 1}^N e^{it a_k x_k} \right]
      = \prod_{k = 1}^N E[e^{it a_k x_k}]
      = \prod_{k = 1}^N \phi_k(at)
    \]

    where the second to last equality follows from the independence of the
    $X_k$.

  * Similarly, the moment-generating function for $S$ is given by

    \[
      M(t) = E[e^{tS}]
      = E[e^{\sum_{k = 1}^N t a_k x_k}]
      = E\left[ \prod_{k = 1}^N e^{t a_k x_k} \right]
      = \prod_{k = 1}^N E[e^{t a_k x_k}]
      = \prod_{k = 1}^N M_k(at)
    \]

  * In some situations, it is possible to invert $\phi(t)$ or $M(t)$ to obtain
    the probability density function for the sum $S$.

* __Linear Transformations of Random Variables__

  If $S = aX + b$, then the characteristic and moment-generating functions for
  $S$ are

  \[
    \phi(t) = E[e^{it (aX + b)}] = e^{itb} E[e^{itaX}] = e^{itb} \phi(at) \\
    M(t) = E[e^{t (aX + b)}] = e^{tb} E[e^{taX}] = e^{tb} M(at)
  \]

* __Moments__. The characteristic and moment-generating functions can be used
  to compute the moments of a random variable $X$.

  \[
    E[X^n] = i^{-n} \left[ \frac{d^n}{dt^n} \phi(t) \right]_{t = 0} \\
    E[X^n] = \left. \frac{d^n M(t)}{dt^n} \right|_{t = 0}
  \]

* __Bounding Upper Tail Probabilities__. The moment-generating function can be
  used to compute bounds on the probability contained in the upper tail of a
  probability distribution:

  \[
    P(X \ge a) = P(e^{tX} \ge e^{ta}) \le e^{-at} E[e^{tX}] = e^{-at} M(t)
  \]

  where the first equality follows because $e^{tx}$ is a monotonically
  increasing function of $x$ when $t > 0$ and the inequality follows from
  Markov's inequality.

### 1.x Geometric Perspective for Random Variables

* Random variable is a vector space

* Norm: $\Vert X \Vert_{L^p} = \left( E\left[ |X|^p \right] \right)^{1/p}$
  where $p \in [1, \infty]$.

  * Triangle inequality property follows from Minkowski's inequality.

  * $\Vert X \Vert_{L^p}$ is an increasing function of $p$:

    $$
    \Vert X \Vert_{L^p} \le \Vert X \Vert_{L^q}
    $$

    _Proof_. Using Jensen's inequality,

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

## 3. Important Probability Distributions

### 3.1. Poisson Distribution

#### Key Ideas

* Basic model for "event counting".

#### Parameters

* $\lambda > 0$: average number of events

#### Probability Distribution

\[
  P(x = k) = \frac{\lambda^k}{k!} e^{-\lambda}
\]

#### Moment-Generating Function

\[
  M(t) = e^{\lambda(e^t - 1)}
\]

#### Properties

* ___Expected Value___: $\lambda$

* ___Variance___: $\lambda$

* ___Sum of Poisson Random Variables___. If $S$ is the sum of $N$ iid
  Poisson distributed random variables with parameter $\lambda$, then $S$ is
  a Poisson random variable with parameter $\lambda N$.

  * _Proof_

    \[
      M_S(t) = \prod_{k = 1}^N M_X(a_k t)
      = \prod_{k = 1}^N e^{\lambda(e^t - 1)}
      = e^{\lambda N (e^t - 1)}
    \]

### 2.2. Gaussian Distribution

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

* ___Expected Value___: $\mu$

* ___Variance___: $\sigma^2$

* ___Sum of Gaussian Random Variables___. If $S = \sum_k a_k X_k$ is a
  linear combination of $N$ iid Gaussian distributed random variables $X_k$
  with parameters $\mu_k$ and $\sigma_k$, then $S$ is a Gaussian random
  variable with parameters $\mu = \sum_{k = 1}^N a_k \mu_k$ and
  $\sigma^2 = \sum_{k = 1}^N a_k^2 \sigma_k^2$.

  * _Proof_

    \[
      M_S(t) = \prod_{k = 1}^N M_X(a_k t)
      = \prod_{k = 1}^N
        \exp \left( a_k \mu_k t + a_k^2 \sigma_k^2 t^2 / 2 \right)
      = \exp\left(
          \left( \sum_{k = 1}^N a_k \mu_k \right) t +
          \left( \sum_{k = 1}^N k a_k^2 \sigma_k^2 \right) t^2 / 2
        \right)
    \]

### 2.3. Exponential Distribution

#### Key Ideas

* Basic model for "waiting time".

#### Parameters

* $\lambda > 0$: event arrival rate

#### Probability Distribution

\[
  P(x) = \left\{
      \begin{array}{ll}
        \lambda e^{-\lambda x} & x \ge 0 \\
        0                      & x < 0
      \end{array}
    \right.
\]

#### Moment-Generating Function

\[
  M(t) = \frac{\lambda}{\lambda - t}
\]

#### Properties

* ___Expected Value___: $1 / \lambda$

* ___Variance___: $1 / \lambda^2$

* ___Memoryless___. $P(X > s+t | X > t) = P(X > s)$ for all $s, t \ge 0$.

  * In words, the probability that the waiting time is greater than $s + t$
    given the knowledge that the waiting time is greater than $t$ is equal
    the probability that the waiting time is greater than the additional
    time $s$.

  * Exponentially distributed random variables are the _only_ random variable
    that is memoryless.

* ___Sum of Exponential Random Variables___. If $S$ is the sum of $N$ iid
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

### 2.4. Gamma Distribution

#### Key Ideas

* Basic model for sum of waiting times.

#### Parameters

* $\alpha > 0$: number of events

  * _Note_: $\alpha$ does not need to be an integer

* $\lambda > 0$: event arrival rate

#### Probability Distribution

\[
  P(x) = \left\{
      \begin{array}{ll}
        \frac{\lambda e^{-\lambda x} (\lambda x)^{\alpha - 1}}
             {\Gamma(\alpha)}                                   & x \ge 0 \\
        0                                                       & x < 0
      \end{array}
    \right.
\]

#### Moment-Generating Function

\[
  M(t) = \left( \frac{\lambda}{\lambda - t} \right)^\alpha
\]

#### Properties

* ___Expected Value___: $\alpha / \lambda$

* ___Variance___: $\alpha / \lambda^2$

* ___Sum of Exponential Random Variables___. If $S$ is the sum of $N$ iid
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


### 2.5. Additional Distributions

* __TODO: Add in the future__

  * Bernoulli distribution

  * Hypergeometric distribution

  * $\chi^2$ distribution

  * Logistic distribution

--------------------------------------------------------------------------------------------

## 3. Tail and Concentration Bounds

TODO: ORGANIZE

#### 1.2.x. Basic Tail and Concentration Bounds

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


### 3.2. Sub-Gaussian Random Variables

#### Key Ideas

* Useful for computing tail and concentration bounds of random variables.

* Many common probability distributions are sub-Gaussian.

#### Definition

A random variable $X$ with mean $\mu = E[X]$ is _sub-Gaussian_ if there is a
positive number $\sigma$ such that

\[
E\left[ e^{\lambda (X - \mu)} \right] \le e^{\sigma^2 \lambda^2 / 2}
\text{ for all } \lambda \in \mathbb{R}.
\]

#### Equivalent Characterizations

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

#### Properties

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

#### Tail and Concentration Bounds

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

#### Examples

* Gaussian random variables
  * TODO

* Rademacher variables
  * TODO

* Bounded random variables
  * TODO

### 3.3. Sub-Exponential Random Variables

#### Key Ideas

* Useful for computing tail and concentration bounds of random variables.

* Many random variables that are not sub-Gaussian are sub-exponential.

#### Definition

A random variable $X$ with mean $\mu = E[X]$ is _sub-exponential_ if there
are non-negative parameters $(\nu, b)$ such that

\[
E\left[ e^{\lambda (X - \mu)} \right] \le e^{\nu^2 \lambda^2 / 2}
\text{ for all } |\lambda| < \frac{1}{b}.
\]

#### Equivalent Characterizations

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

#### Properties
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

#### Tail and Concentration Bounds

* TODO

#### Examples

* Gaussian random variables
  * TODO

* Chi-squared random variables
  * TODO

* Bounded random variables
  * TODO

--------------------------------------------------------------------------------------------

## 4. Limit Theorems

TODO: ORGANIZE
### 1.2. Limit Theorems

* __Weak Law of Large Numbers__. TODO

* __Strong Law of Large Numbers__. Let $X_1, X_2, \ldots$ be a sequence of i.i.d. random
  variables with mean $\mu$. Define $S_N = X_1 + \cdots + X_N$. As $N \rightarrow \infty$,
  $\frac{S_N}{N} \rightarrow \mu$ almost surely.

* __Central Limit Theorem__ (Lindeberg-Levy). Let $X_1, X_2, \ldots$ be a sequence of
  i.i.d. random variables with mean $\mu$ and variance $\sigma^2$. Define
  $S_N = X_1 + \cdots + X_N$ and

  $$
  Z_n = \frac{S_N - \E{S_N}}{\sigma_N}
  $$

  where $\sigma_N^2 = \Var{S_N} = N \sigma^2$.

  * TODO: Proof of Central Limit Theorem

* __Borel's Law of Large Numbers__. TODO
  * frequency of event --> probability of event

* TODO Law of large numbers
  * Proofs using both Chebyshev's Inequality and characteristic function

* __Poisson Limit of Bernoulli Random Variables__. For each $n$, let
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

## 5. References

1. S.M. Ross. "Introduction to Probability and Statistics for Engineers and
   Scientists" (2004).

2. R. Vershynin. "High-Dimensional Probability". (2018)

3. M.J. Wainwright. "High-Dimensional Statistics: A Non-Asymptotic Viewpoint". (2019)

4. H.M. Taylor and S. Karlin. "An Introduction to Stochastic Modeling". (1998)

5. [Wikipedia: Characteristic function][wikipedia-characteristic-function]

6. [Wikipedia: Moment-generating function][wikipedia-moment-generating-function]

--------------------------------------------------------------------------------------------

## Appendix A. Useful Mathematical Definitions and Results

* __Convergence in Distribution__. TODO
  * pointwise convergencde of the CDF

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

[#1]: #1-fundamental-concepts
[#1.1]: #11-characteristic-and-moment-generating-functions
[#1.2]: #12-useful-mathematical-relations

[#2]: #2-common-probability-distributions

[#3]: #3-tail-and-concentration-bounds
[#3.1]: #31-basic-tail-and-concentration-bounds
[#3.2]: #32-sub-gaussian-random-variables
[#3.3]: #33-sub-exponential-random-variables

[#4]: #4-limit-theorems

[#5]: #5-references

[----------------------------------- EXTERNAL LINKS -----------------------------------]: #

[chrome-markdown-viewer]: https://chrome.google.com/webstore/detail/markdown-viewer/ckkdlimhmcjmikdlpkmbgfkaikojcbjk

[wikipedia-characteristic-function]: https://en.wikipedia.org/wiki/Characteristic_function_(probability_theory)

[wikipedia-moment-generating-function]: https://en.wikipedia.org/wiki/Moment-generating_function
