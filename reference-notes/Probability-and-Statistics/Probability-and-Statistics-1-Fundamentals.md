Probability and Statistics: Fundamentals
========================================

*Author(s)*: Kevin Chu `<kevin@velexi.com>`

__Last Updated__: 2022-07-24

--------------------------------------------------------------------------------------------

Table of Contents
-----------------

1. [Fundamental Concepts][#1]

    1.1. [Basics of Probability Theory][#1.1]

    1.2. [Random Variables][#1.2]

2. [Basic Results][#2]

    2.1. [Expectations][#2.1]

    2.2. [Random Sums][#2.2]

    2.3. [Probability Bounds][#2.3]

    2.4. [Miscellaneous Results][#2.4]

3. [Characteristic and Moment Generating Functions][#3]

    3.1. [Definitions][#3.1]

    3.2. [Properties][#3.2]

    3.3. [Applications][#3.3]

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

## 1. Fundamental Concepts

### 1.1. Basics of Probability Theory

* __Union of Disjoint Events__. Let $A_1, A_2, \ldots$ be disjoint events. Then
  $\Pr{A_1 \cup A_2 \cup \cdots} = \sum_{i=1}^\infty \Pr{A_i}$.

* __Law of Total Probability__. Let $A_1, A_2, \ldots$ be disjoint events. Then, for any
  event $B$, $\Pr{B} = \sum_{i=1}^\infty \Pr{B \cap A_i}$.

* __Independence__. Events $A_1, A_2, \ldots$ are _independent_ if and only if
  $\Pr{A_{i_1} \cap \cdots \cap A_{i_n}} = \Pr{A_{i_1}} \cdots \Pr{A_{i_n}}$ for any finite
  subset of the events $A_i$.

* __Conditional Probability__. Let $A$ and $B$ be two events. When $\Pr{B} > 0$, the
  _conditional probability_ of $A$ given $B$, denoted by $\Pr{A|B}$ is equal to

  $$
  \Pr{A|B} = \frac{\Pr{A}}{\Pr{A \cap B}}.
  $$

  When $\Pr{B} = 0$, the conditional probability of $A$ given $B$ is undefined.

* __Inclusion-Exclusion Principle__. Let $A_1, \ldots, A_n$ be arbitrary events.

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

    _Important Special Case_. When the size of intersection of the sets in the
    inclusion-exclusion formula only depends on the number sets in the intersection and not
    the specific sets that appear, the inclusion-exclusion formula simplifies to

    $$
    \left| \bigcup_{i=1}^n A_i \right|
    = \sum_{k=1}^n (-1)^{k-1} {n \choose k} \alpha_k
    $$

    where $\alpha_k = \left| \bigcap_{j \in J} A_j \right|$ for all $J$ with $|J| = k$.

* __De Morgan's Laws__. Let $A_1, \ldots, A_n$ be arbitrary events.

  $$
  \left( \cup_{i=1}^n A_i \right)^c = \cap_{i=1}^n A_i^c \\
  \left( \cap_{i=1}^n A_i \right)^c = \cup_{i=1}^n A_i^c
  $$

### 1.2. Random Variables

* __Random Variable__. A variable $X$ whose value is randomly selected from a probability
  distribution defined by one of the following functions.

  * __Cumulative Distribution Function (CDF)__. The _cumulative distribution function_,
    denoted by $F_X(x)$, is the probability that a random variable $X$ is no more than $x$:

    $$
    F_X(x) = \Pr{X \le x}
    $$

  * __Probability Density Function__. When $X$ is a _continous random variable_, the
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

    _Remark_. Some continuous random variables do not possess a probability density
    function (i.e., those where $F_X(x)$ is not differentiable), but they do not commonly
    arise in applications.

  * __Probability Mass Function__.  When $X$ is a _discrete random variable_, the
    probability distribution may be specified by a _probability mass function_, denoted by
    $\p{x}$:

    $$
    \p{x} = \Pr{X = x}.
    $$

* __Expected Value__. The _expected value_ of a random variable $X$, denoted by $\E{X}$, is
  one way to estimate the "typical value" realized by $X$. When $X$ is a continuous random
  variable, $\E{X}$ is defined as

  $$
  \E{X} = \int_{-\infty}^\infty x \p{x} dx.
  $$

  When $X$ is a discrete random variable, $\E{X}$ is defined as

  $$
  \E{X} = \sum_{i} x_i \Pr{X = x_i} = \sum_{i} x_i \p{x_i}.
  $$

* __Moments__. The $m$-th moment of $X$ is defined as $\E{X^m}$.

  * __Central Moment__. The $m$-th central moment of $X$ is defined as
    $\E{\left( X - \E{X} \right)^m}$.

  * __Absolute Moment__. The $m$-th absolute moment of $X$ is defined as $\E{|X|^m}$.

  * __Expected Value, Mean, Average__: the first moment of $X$, $\E{X}$

  * __Variance__: the second central moment of $X$

    $$
    \Var{X} = \E{\left( X - \E{X} \right)^2} = \E{X^2} - (\E{X})^2
    $$

  * __Related Quantities__

    * __Standard Deviation__. The _standard deviation_ of $X$, denoted $\sd{X}$, is defined
      as

      $$
      \sd{X} = \sqrt{\Var{X}}.
      $$

    * __Covariance__: the _covariance_ of two random variables $X$ and $Y$ is defined as

      $$
      \cov{X} = \E{ \left(\left( X - \E{X} \right) \left( Y - \E{Y} \right)\right) }
      $$

    * __Median__. The _median_ of a random variable $X$ is any value $\nu$ satisfying the
      property that

      $$
      \Pr{X \ge \nu} \ge \frac{1}{2}
      $$

      and

      $$
      \Pr{X \le \nu} \ge \frac{1}{2}.
      $$

* __Moment Generating Function__: $\E{e^{tX}}$, where $t \in \R$

* __Tail Probability__: $\Pr{X > x} = 1 - F_X(x)$

* __Joint Distribution Functions__. Let $(X_1, \ldots, X_n)$ be a vector of random
  variables. Then the _joint distribution function_ for $(X_1, \ldots, X_n)$ is given by

  $$
  F(x_1, \ldots, x_n) = \Pr{X_1 \le x_1, \ldots, X_n \le x_n}.
  $$

  * __Joint Probability Density__. The random vector $(X_1, \ldots, X_n)$ possesses a
    _joint probability density_ if a function $f(x_1, \ldots, x_n)$ exists such
    that

    $$
    F(x_1, \ldots, x_n)
    = \int_{-\infty}^{x_1} \cdots \int_{-\infty}^{x_n}
      f(x_1, \ldots, x_n) dx_1 \cdots dx_n
    $$

    for all $(x_1, \ldots, x_n)$.

  * __Marginal Distribution Functions__. The _marginal distribution function_ of
    $(X_1, \ldots, X_{n-1})$ is given by

    $$
    F_{X_1,\ldots,X_{n-1}}(x_1, \ldots, x_{n-1})
    = \lim_{x_n \rightarrow \infty} F(x_1, \ldots, x_n)
    $$

    If $(X_1, \ldots, X_{n-1})$ possesses a joint probability density, the marginal
    distribution of $(X_1, \ldots, X_{n-1})$ may also be expressed as

    $$
    F_{X_1,\ldots,X_{n-1}}(x_1, \ldots, x_{n-1})
    = \int_{-\infty}^\infty f(x_1, \ldots, x_n) dx_n
    $$

    The marginal distribution functions of any subvector of $(X_1, \ldots, X_{n-1})$ are
    defined similarly.

  * __Independence and Correlation__

    * __Independent__. Random variables $X_1, \ldots, X_n$ are _independent_ if their joint
      distribution function is a product of the marginal distribution functions for
      $X_1, \ldots, X_n$:

      $$
      F_{X_1, \ldots, X_n}(x_1, \ldots, x_n) = F_{X_1}(x_1) \cdots F_{X_n}(x_n)
      $$

      for all $x_1, \ldots, x_n$. If $X_1, \ldots, X_n$ possess a joint density function,
      then

      $$
      f_{X_1, \ldots, X_n}(x_1, \ldots, x_n) = f_{X_1}(x_1) \cdots f_{X_n}(x_n)
      $$

      for all $x_1, \ldots, x_n$.

    * __Uncorrelated__. Random variables $X$ and $Y$ are _uncorrelated_ if their covariance
      is 0:

      $$
      \E{(X - \mu_X)(Y - \mu_Y)} = \E{XY} - \mu_X \mu_Y = 0.
      $$

--------------------------------------------------------------------------------------------

## 2. Basic Results

### 2.1. Expectations

* __Linearity of Expectation__. Let $X_1, \ldots, X_n$ be arbitrary random variables. Then

  $$
  \E{X_1 + \cdots + X_n} = \E{X_1} + \cdots + \E{X_n}
  $$

  _regardless_ of whether the $X_i$ are independent or have dependencies between them.

* __Expected Value in Terms of Tail Probabilities__. The expected value of a random
  variable can be expressed as an integral or sum over tail probabilities. This identity
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

    Substituting this expression for the random variable $X$, taking expectations, and
    using linearity of expectations yields

    $$
    \E{X}
    = \E{ \sum_{k=0}^\infty \1{k < X} }
    = \sum_{k=0}^\infty \E{ \1{k < X} }
    = \sum_{k=0}^\infty \Pr{X > k}.
    $$

    The alternate sum over tail probabilities (with terms that are not strict inequalities)
    follows by shifting the summation index by 1 or using the identity

    $$
    n = \sum_{k=1}^\infty \1{k \le n}.
    $$

  * __Continuous Random Variables__ (Vershynin, Lemma 1.2.1). Let $X$ be a non-negative
    continuous random variable. Then

    $$
    \E{X} = \int_0^\infty \Pr{X > t} dt.
    $$

    _Proof_. The proof is analogous to the discrete case with sums replaced by integrals
    and the sum identity for $n$ replaced by the integral identity

    $$
    x = \int_0^\infty \1{t < x} dt.
    $$

  * __Generalization to Random Variables with Negative Values__

    $$
    \E{X} = \int_0^\infty \Pr{X > t} dt - \int_{-\infty}^0 \Pr{X < t} dt
    $$

### 2.2. Random Sums

* __Distribution of Random Sums__. Let $X$ and $Y$ be independent random variables. Then
  the distribution of their sum $Z = X + Y$ is given by the convolution of their cumulative
  distribution functions:

  $$
  F_Z(z)
  = \int_{-\infty}^\infty F_X(z - s) dF_Y(s)
  = \int_{-\infty}^\infty F_Y(z - s) dF_X(s).
  $$

  When $X$ and $Y$ have probability density functions, then the probability density of $Z$
  is given by

  $$
  f_Z(z)
  = \int_{-\infty}^\infty f_X(z - s) f_Y(s) ds
  = \int_{-\infty}^\infty f_Y(z - s) df_X(s) ds.
  $$

* __Mean and Variance of Random Sums__. Let $X_1, \ldots, X_n$ be independent random
  variables. Then the mean and variance of the linear combination
  $Z = a_1 X_1 + \cdots + a_n X_n$ are

  $$
  \E{Z} = a_1 \E{X_1} + \cdots + a_n \E{X_n} \\
  \Var{Z} = a_1^2 \Var{X_1} + \cdots + a_n^2 \Var{X_n}.
  $$

  Both of these results following directly from the linearity of expectation.

### 2.3. Probability Bounds

* __Basic Tail Bounds__

  * __Markov's Inequality__. Let $X$ be a non-negative random variable with a finite mean.
    Then the tail probability for $X$ satisfies the bound

    $$
    \Pr{X \ge t} \le \frac{\E{X}}{t}.
    $$

    _Proof 1_. If $X$ possesses a probability density function $\p{x}$, then

    $$
    \E{X}
    = \int_0^\infty x \p{x} dx
    \ge \int_t^\infty x \p{x} dx
    \ge \int_t^\infty t \p{x} dx
    = t \Pr{X \ge t}.
    $$

    Rearranging this inequality yields the desired result.

    _Proof 2_. Expressing the expectation value in terms of tail probabilities,

    $$
    \E{X}
    = \int_0^\infty \Pr{X \ge s} ds
    \ge \int_0^t \Pr{X \ge s} ds
    \ge \int_0^t \Pr{X \ge t} ds
    = t \Pr{X \ge t},
    $$

    where the right-most inequality follows because $\Pr{X \ge s} \ge \Pr{X \ge t}$
    whenever $t \ge s$.

    Rearranging this inequality yields the desired result.

  * __Chebyshev's Inequality__. Let $X$ be a random variable with a finite mean $\mu$ and
    variance $\sigma^2$. Then the tail probability for $X$ satisfies the bound

    $$
    \Pr{|X - \mu| \ge t} \le \frac{\Var{X}}{t^2}.
    $$

    _Proof_. Observe that

    $$
    \Pr{|X - \mu| \ge t} = \Pr{(X - \mu)^2 \ge t^2}.
    $$

    Since $(X - \mu)^2$ is non-negative random variable, Markov's inequality implies that

    $$
    \Pr{(X - \mu)^2 \ge t^2}
    \le \frac{\E{(X - \mu)^2}}{t^2}
    \le \frac{\Var{X}}{t^2}.
    $$

* __Union Bound__. Let $A_1, \ldots, A_n$ be a collection of events. Then the probability
  that probability any of the events occurs (i.e., the union of the events) is bounded by
  sum of the probabilities of the individual events:

  $$
  \Pr{\textrm{any of the $A_i$ occurs}}
  = \Pr{A_1 \cup \cdots \cup A_n}
  \le \Pr{A_1} + \cdots + \Pr{A_n}.
  $$

  _Remark_. The expression on the right-hand side of the inequality is the first term of
  the inclusion-exclusion principle.

### 2.4. Miscellaneous Results

* __Random Products__. Let $X_1, \ldots, X_n$ be independent random variables. Then

  $$
  \E{X_1 \cdots X_n} = \E{X_1} \cdots \E{X_n}.
  $$

* __Bounds on the Values of a Random Variable__. If the expectation value of a random
  variable exists (i.e., is finite), then we are guaranteed the existence of

  * at least one instance of the random variable no greater than expectation value and

  * at least one instance of the random variable no less than expectation value.

* __Moments in Terms of Tail Probabilities__. The moments of a random variable can be
  expressed as an integral or sum over tail probabilities.

  $$
  \E{ |X|^\alpha } = \alpha \int_0^\infty t^{\alpha - 1} \Pr{|X| > t} dt
  $$

  _Proof 1_. From the integral identity, we have

  $$
  \E{ |X|^\alpha } = \int_0^\infty \Pr{|X|^\alpha > s} ds.
  $$

  Using the change of variables $s = t^\alpha$ yields the desired result:

  $$
  \E{|X|^\alpha}
  = \alpha \int_0^\infty t^{\alpha-1} \Pr{ |X|^\alpha > t^\alpha } dt
  = \alpha \int_0^\infty t^{\alpha-1} \Pr{ |X| > t } dt.
  $$

  _Proof 2_. Direct computation of the expected value. Assuming that $X$ possesses a
  probability density function,

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

  Interchanging the order of integration yields the desired result

  $$
  \E{ |X|^\alpha }
  = \alpha \int_0^\infty \left( \int_t^\infty \p{x} dx \right) t^{\alpha - 1} dt
  = \alpha \int_0^\infty t^{\alpha - 1} \Pr{|X| > t} dt
  $$

* __Relationship between Independent and Uncorrelated__

  * Random variables that independent are uncorrelated (assuming that all relevant
    expectation values are finite).

  * Random variables that are uncorrelated need not be independent.

--------------------------------------------------------------------------------------------

## 3. Characteristic and Moment-Generating Functions

### 3.1. Definitions

* __Characteristic Function__: expectation value of $e^{itX}$ of a random variable $X$
  (essentially the Fourier transform of the probability density function).

  \[
    \phi(t) = \E{e^{itX}} = \int_{-\infty}^\infty e^{itx} \p{x} dx
  \]

  _Note_: the characteristic function exists for all probability density functions.

* __Moment-Generating Function__: expectation value of $e^{tX}$ of a random variable $X$.

  \[
    M(t) = \int_{-\infty}^\infty e^{tx} \p{x} dx
  \]

  _Note_: the moment-generating function only exists for probability density functions
  where the integral converges.

### 3.2. Properties

* Both the characteristic function and the moment-generating function _completely define_
  the probability distribution of a random variable.

  * If two probability distributions have the same characteristic function or
    moment-generating function, then they are identical (except possibly on a set of
    measure zero).

* When a random variable has a moment-generating function $M(t)$, then the characteristic
  function $\phi(t)$ can be extended to the complex plane and $M(t) = \phi(-it)$.

* The moment-generating function is bounded below by $e^{\mu t}$ where
  $\mu$ is the mean of $X$: $M(t) \ge e^{\mu t}$.

  _Proof_. The bound follows directly from Jensen's inequality because $e^{tx}$ is a convex
  function of $x$.

### 3.3. Applications

* __Moments__. The characteristic and moment-generating functions can be used to compute
  the moments of a random variable $X$.

  \[
    \E{X^n} = i^{-n} \left[ \frac{d^n}{dt^n} \phi(t) \right]_{t = 0} \\
    \E{X^n} = \left. \frac{d^n M(t)}{dt^n} \right|_{t = 0}
  \]

* __Probability Distributions of Sums of Independent Random Variables__

  * Characteristic and moment-generating functions are useful for calculating the
    probability distributions of linear combinations of independent random variables.

  * Let $S = \sum a_k X_k$ where $X_k$ are independent random variables and the $a_k$ are
    constants. Then the characteristic function for $S$ is given by

    \[
      \phi(t) = \E{e^{itS}}
      = \E{e^{\sum_{k = 1}^N it a_k x_k}}
      = \E{\prod_{k = 1}^N e^{it a_k x_k}}
      = \prod_{k = 1}^N \E{e^{it a_k x_k}}
      = \prod_{k = 1}^N \phi_k(at)
    \]

    where the second to last equality follows from the independence of the
    $X_k$ and $\phi_k(t)$ is the characteristic function for $X_k$.

  * Similarly, the moment-generating function for $S$ is given by

    \[
      M(t) = \E{e^{tS}}
      = \E{e^{\sum_{k = 1}^N t a_k x_k}}
      = \E{\prod_{k = 1}^N e^{t a_k x_k}}
      = \prod_{k = 1}^N \E{e^{t a_k x_k}}
      = \prod_{k = 1}^N M_k(at).
    \]

  * In some situations, it is possible to invert $\phi(t)$ or $M(t)$ to obtain the
    probability density function for the sum $S$.

    * For some common distributions, it is possible to recognize that the
      characteristic/moment-generating function for a sum is equal to the
      characteristic/moment-generating function for a known distribution.

    * Laplace transform tables are useful for inverting $M(t)$.

    * Fourier transform tables are useful for inverting $\phi(t)$.

    * When inversion tables are insufficient, contour integration techniques (including
      approximation methods) can be useful to analyze the properties of the probability
      density function.

* __Bounding Upper Tail Probabilities__. The moment-generating function can be used to
  compute bounds on the probability contained in the upper tail of a probability
  distribution:

  \[
    \Pr{X \ge a} = \Pr{e^{tX} \ge e^{ta}} \le e^{-at} \E{e^{tX}} = e^{-at} M(t)
  \]

  where the first equality follows because $e^{tx}$ is a monotonically increasing function
  of $x$ when $t > 0$ and the inequality follows from Markov's inequality.

  _Remark_. This bound for the tail probability forms the foundation of Chernoff bounds.

* __Linear Transformations of Random Variables__

  If $S = aX + b$, then the characteristic and moment-generating functions for
  $S$ are

  \[
    \phi(t) = \E{e^{it (aX + b)}} = e^{itb} \E{e^{itaX}} = e^{itb} \phi(at) \\
    M(t) = \E{e^{t (aX + b)}} = e^{tb} \E{e^{taX}} = e^{tb} M(at)
  \]

--------------------------------------------------------------------------------------------

## 4. References

1. S.M. Ross. "Introduction to Probability and Statistics for Engineers and Scientists"
   (2004).

2. R. Vershynin. "High-Dimensional Probability". (2018)

3. H.M. Taylor and S. Karlin. "An Introduction to Stochastic Modeling". (1998)

4. [Wikipedia: Characteristic function][wikipedia-characteristic-function]

5. [Wikipedia: Moment-generating function][wikipedia-moment-generating-function]

--------------------------------------------------------------------------------------------

[----------------------------------- INTERNAL LINKS -----------------------------------]: #

[#1]: #1-fundamental-concepts
[#1.1]: #11-basics-of-probability-theory
[#1.2]: #12-random-variables

[#2]: #2-basic-results
[#2.1]: #21-expectations
[#2.2]: #22-random-sums
[#2.3]: #23-probability-bounds
[#2.4]: #24-miscellaneous-results

[#3]: #3-characteristic-and-moment-generating-functions
[#3.1]: #31-definitions
[#3.2]: #32-properties
[#3.3]: #33-applications

[#4]: #4-references

[----------------------------------- EXTERNAL LINKS -----------------------------------]: #

[wikipedia-characteristic-function]: https://en.wikipedia.org/wiki/Characteristic_function_(probability_theory)

[wikipedia-moment-generating-function]: https://en.wikipedia.org/wiki/Moment-generating_function
