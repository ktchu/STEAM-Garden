Probability: Fundamentals
=========================

*Author(s)*: Kevin Chu `<kevin@velexi.com>`

__Last Updated__: 2023-09-20

--------------------------------------------------------------------------------------------

Table of Contents
-----------------

1. [Basic Probability][#1]

   * 1.1. [Fundamental Concepts][#1.1]

   * 1.2. [Basic Results][#1.2]

   * 1.3. [Infinite Collections of Events][#1.3]

2. [Random Variables][#2]

   * 2.1. [Fundamental Concepts][#2.1]

   * 2.2. [Expected Value][#2.2]

   * 2.3. [Random Sums and Products][#2.3]

   * 2.4. [Other Useful Results][#2.4]

3. [Moment-Generating and Characteristic Functions][#3]

   * 3.1. [Fundamental Concepts][#3.1]

   * 3.2. [Basic Results][#3.2]

   * 3.3. [Applications][#3.3]

4. [Basic Probability Bounds][#4]

5. [References][#5]

--------------------------------------------------------------------------------------------

## 0. Notation

* $\newcommand{\R}{\mathbb{R}}$
  The set of real numbers: $\R$

* Complement of an event $A$: $A^c$

* $\newcommand{\Pr}[1]{\mathbb{P}\left[{#1}\right]}$
  Probability of event $A$: $\Pr{A}$

* $\newcommand{\1}[1]{\mathbf{1}_{\left\{{#1}\right\}}}$
  Indicator for event $A$: $\1{A}$

* Cumulative distribution function (CDF) for a random variable $X$: $F(x)$ or $F_X(x)$

  * $\newcommand{\Fbar}{\overline{F}}$
    "Complement" of the CDF for a random variable $X$: $\Fbar(x)$ or $\Fbar_X(x)$

* Probability density (or mass) function for a random variable $X$: $p(x)$ or $p_X(x)$

* $\newcommand{\E}[1]{\mathbb{E}\left[{#1}\right]}$
  Expected value of $X$: $\E{X}$

* $\newcommand{\var}[1]{\operatorname{var}\left(#1\right)}$
  Variance of $X$: $\var{X}$

* $\newcommand{\stddev}[1]{\sigma{\left(#1\right)}}$
  Standard deviation of $X$: $\stddev{X}$

* $\newcommand{\cov}[2]{\operatorname{cov}\left(#1, #2\right)}$
  Covariance of $X$ and $Y$: $\cov{X}{Y}$

--------------------------------------------------------------------------------------------

## 1. Basic Probability

### 1.1. Fundamental Concepts

* __Basic Axioms of Probability__

  * Let $S$ be a sample space of all possible outcomes of a random experiment.
  * An _event_ is a subset of $S$.
  * For each event $A$, the _probability of $A$_ $\Pr{A}$ is a number satisfying the
    following axioms:

    * $0 \le \Pr{A} \le 1$
    * $P(S) = 1$.
    * For any countable collection of events $A_1, A_2, A_3, \ldots$ that are mutually
      exclusive (e.g., $A_i \cap A_j = \emptyset$ if $i \ne j$),

      $$
      \Pr{\bigcap_{i=1}^\infty A_i} = \sum_{i=1}^\infty \Pr{A_i}.
      $$

* __Independence__. Events $A_1, A_2, \ldots$ are _independent_ if and only if
  $\Pr{A_{i_1} \cap \cdots \cap A_{i_n}} = \Pr{A_{i_1}} \cdots \Pr{A_{i_n}}$ for any finite
  subset of the events $A_i$.

* __Conditional Probability__. Let $A$ and $B$ be two events. When $\Pr{B} > 0$, the
  _conditional probability_ of $A$ given $B$, denoted by $\Pr{A|B}$ is equal to

  $$
  \Pr{A|B} = \frac{\Pr{A}}{\Pr{A \cap B}}.
  $$

  When $\Pr{B} = 0$, the conditional probability of $A$ given $B$ is undefined.

### 1.2. Basic Results

* __Monotonicity of Probability__. If $A \subseteq B,$ then $\Pr{A} \le \Pr{B}.$

* __Complementary Events__. $\Pr{A^c} = 1 - \Pr{A}.$
  * __Complements Independent Events__. If $A_1, A_2, \ldots$ are independent events, then
    their complements $A_1^c, A_2^c, \ldots$ are independent events.

* __Union of Disjoint Events__. Let $A_1, A_2, \ldots, A_n$ be disjoint events. Then
  $\Pr{\bigcup_{i=1}^n A_i} = \sum_{i=1}^n \Pr{A_i}.$

* __Union Bound (Boole's Inequality)__

  * _Finite Case_. Let $A_1, A_2, \ldots, A_n$ be a collection of arbitrary events. Then
    $\Pr{\bigcup_{i=1}^n A_i} \le \sum_{i=1}^n \Pr{A_i}.$

  * _Infinite Case_. Let $A_1, A_2, \ldots$ be a countable collection of events. Then
    $\Pr{\bigcup_{i=1}^\infty A_i} \le \sum_{i=1}^\infty \Pr{A_i}.$

* __Law of Total Probability__. Let $A_1, A_2, \ldots$ be disjoint events. Then, for any
  event $B$, $\Pr{B} = \sum_{i=1}^\infty \Pr{B \cap A_i}$.

* __Inclusion-Exclusion Principle__. Let $A_1, \ldots, A_n$ be arbitrary events. Then

  $$
  \Pr{\bigcup_{i=1}^n A_i}
  = \sum_{k=1}^n
    (-1)^{k-1} \sum_{J \subseteq \{1, \ldots, n\}, |J|=k} \Pr{\bigcap_{j \in J} A_j}
  $$

  * __Bonferroni inequalities__. Let $A_1, \ldots, A_n$ be arbitrary events and define

    $$
    \begin{align}
    S_1 &= \sum_{i=1}^n \Pr{A_i} \\
    S_2 &= \sum_{1 \le i < j \le n} \Pr{A_i \cap A_j} \\
    &\vdots \\
    S_k &= \sum_{1 \le i_1 < \cdots < i_k \le n} \Pr{A_{i_1} \cap \cdots \cap A_{i_k}}. \\
    \end{align}
    $$

    When $n$ is odd, then

    $$
    \Pr{\bigcup_{i=1}^n A_i}
    = \sum_{j=1}^n (-1)^{j-1} S_j
    \le \sum_{j=1}^{n-2} (-1)^{j-1} S_j
    \le \sum_{j=1}^{n-4} (-1)^{j-1} S_j
    \le \cdots
    \le \sum_{j=1}^1 (-1)^{j-1} S_j
    $$

    and

    $$
    \sum_{j=1}^2 (-1)^{j-1} S_j
    \le \cdots
    \le \sum_{j=1}^{n-3} (-1)^{j-1} S_j
    \le \sum_{j=1}^{n-1} (-1)^{j-1} S_j
    \le \sum_{j=1}^n (-1)^{j-1} S_j
    = \Pr{\bigcup_{i=1}^n A_i}
    $$

    When $n$ is even, then

    $$
    \Pr{\bigcup_{i=1}^n A_i}
    = \sum_{j=1}^n (-1)^{j-1} S_j
    \le \sum_{j=1}^{n-1} (-1)^{j-1} S_j
    \le \sum_{j=1}^{n-3} (-1)^{j-1} S_j
    \le \cdots
    \le \sum_{j=1}^1 (-1)^{j-1} S_j
    $$

    and

    $$
    \sum_{j=1}^2 (-1)^{j-1} S_j
    \le \cdots
    \le \sum_{j=1}^{n-4} (-1)^{j-1} S_j
    \le \sum_{j=1}^{n-2} (-1)^{j-1} S_j
    \le \sum_{j=1}^n (-1)^{j-1} S_j
    = \Pr{\bigcup_{i=1}^n A_i}
    $$

### 1.3. Infinite Collections of Events

#### 1.3.1. Definitions

* __Monotone Sequences of Events__. Let $A_1, A_2, \ldots$ be a sequence of events.

  * _Increasing Sequences_. A sequence of event is _increasing_ if $A_n \subset A_{n+1}$
    for all $n \ge 1.$ If the containment chain is not strict (i.e., $A_n \subseteq A_{n+1}$
    for all $n \ge 1$), then the sequence of events is called _nondecreasing_.

  * _Decreasing Sequences_. A sequence of event is _decreasing_ if $A_n \supset A_{n+1}$
    for all $n \ge 1.$ If the containment chain is not strict (i.e., $A_n \subseteq A_{n+1}$
    for all $n \ge 1$), then the sequence of events is called _nonincreasing_.

* __Limits of Monotone Sequences of Events__. Let $A_1, A_2, \ldots$ be a monotone sequence
  of events.

  * _Nondecreasing Sequences_. For an nondecreasing sequence of events, the limit of the
    sequence $\lim_{n \rightarrow \infty} A_n$ is defined by
    $\lim_{n \rightarrow \infty} A_n = \bigcup_{i=1}^\infty A_i.$

  * _Nonincreasing Sequences_. For a nonincreasing sequence of events, the limit of the
    sequence $\lim_{n \rightarrow \infty} A_n$ is defined by
    $\lim_{n \rightarrow \infty} A_n = \bigcap_{i=1}^\infty A_i.$

* __Limit Superior and Limit Inferior__

  * $\lim \sup A_n$ is defined by

    $$
    \lim \sup A_n
    = \bigcap_{n=1}^\infty \bigcup_{i=n}^\infty A_i
    = \lim_{n \rightarrow \infty} \bigcup_{i=n}^\infty A_i,
    $$

    where the last equality follows because $\bigcup_{i=n}^\infty A_i$ is nonincreasing. It
    represents the event that an infinite number of the events $A_i$ occur.

  * $\lim \inf A_n$ is defined by

    $$
    \lim \inf A_n
    = \bigcup_{n=1}^\infty \bigcap_{i=n}^\infty A_i
    = \lim_{n \rightarrow \infty} \bigcap_{i=n}^\infty A_i
    $$

    where the last equality follows because $\bigcap_{i=n}^\infty A_i$ is nondecreasing. It
    represents the event that all but a finite number of events $A_i$ occur.

#### 1.3.2. Useful Results

* __Continuity of Probability__. If $A_1, A_2, \ldots$ is either an increasing or
  decreasing sequences of events, then

  $$
  \lim_{n \rightarrow \infty} \Pr{A_n} = \Pr{ \lim_{n \rightarrow \infty} A_n }.
  $$

  _Proof_. TODO

* __Borel-Cantelli Lemma__. Let $A_1, A_2, \ldots$ be a sequence of events. If

  $$
  \sum_{i=1}^\infty \Pr{A_i} < \infty,
  $$

  then the probability that an infinite number of the $A_i$ occurs is equal to $0$:

  $$
  \Pr{\textrm{an infinite number of the $A_i$ occur}} = 0.
  $$

  _Proof_. The event that an infinite number of the $A_i$ occurs is $\lim \sup A_n$:

  $$
  \lim \sup A_n
  = \bigcap_{n=1}^\infty \bigcup_{i=n}^\infty A_i
  = \lim_{n \rightarrow \infty} \bigcup_{i=n}^\infty A_i.
  $$

  Since $B_n = \bigcup_{i=n}^\infty A_i$ is a nonincreasing sequence of events,

  $$
  \begin{align}
  \Pr{\lim_{n \rightarrow \infty} B_n}
  &= \lim_{n \rightarrow \infty} \Pr{B_n} \\
  &= \lim_{n \rightarrow \infty} \Pr{\bigcup_{i=n}^\infty A_i} \\
  &\le \lim_{n \rightarrow \infty} \sum_{i=n}^\infty \Pr{A_i} \\
  &= 0
  \end{align}
  $$

  where the inequality follows from the union bound and the limit equal zero because
  $\sum_{i=1}^\infty \Pr{A_i}$ finite implies that the limit of the tail sums as $n$
  approaches infinity must be $0.$

* __Converse of Borel-Cantelli Lemma__. Let $A_1, A_2, \ldots$ be a sequence of independent
  events. If

  $$
  \sum_{i=1}^\infty \Pr{A_i} = \infty,
  $$

  then the probability that an infinite number of the $A_i$ occurs is equal to 1:

  $$
  \Pr{\textrm{an infinite number of the $A_i$ occur}} = 1.
  $$

  _Proof_. The event that an infinite number of the $A_i$ occurs is $\lim \sup A_n$:

  $$
  \lim \sup A_n
  = \bigcap_{n=1}^\infty \bigcup_{i=n}^\infty A_i
  = \lim_{n \rightarrow \infty} \bigcup_{i=n}^\infty A_i.
  $$

  Recognizing that $B_n = \bigcup_{i=n}^\infty A_i$ is a nonincreasing sequence of events,

  $$
  \begin{align}
  \Pr{\lim_{n \rightarrow \infty} B_n}
  &= \lim_{n \rightarrow \infty} \Pr{B_n} \\
  &= \lim_{n \rightarrow \infty} \Pr{\bigcup_{i=n}^\infty A_i} \\
  &= \lim_{n \rightarrow \infty}
       \left( 1 - \Pr{\left( \bigcup_{i=n}^\infty A_i \right)^c} \right)\\
  &= 1 - \lim_{n \rightarrow \infty} \Pr{\bigcap_{i=n}^\infty A_i^c}.
  \end{align}
  $$

  Since the $A_i$ are independent,

  $$
  \begin{align}
  \Pr{\bigcap_{i=n}^\infty A_i^c}
  &= \prod_{i=n}^\infty \Pr{A_i^c} \\
  &= \prod_{i=n}^\infty (1 - \Pr{A_i}) \\
  &\le \prod_{i=n}^\infty e^{-\Pr{A_i}} \\
  &= \exp\left(-\sum_{i=n}^\infty \Pr{A_i}\right) \\
  &= 0
  \end{align}
  $$

  where the inequality follows because $(1 + x) \le e^{x}$ for all $x$ and the last
  equality follows from the assumption that $\sum_{i=1}^\infty \Pr{A_i} = 0.$

  Therefore, $\Pr{\lim_{n \rightarrow \infty} B_n} = 1$ (because
  $1 - \lim_{n \rightarrow \infty} \Pr{\bigcap_{i=n}^\infty A_i^c} \ge (1 - 0)$
  and probabilities can be no greater than 1).

--------------------------------------------------------------------------------------------

## 2. Random Variables

### 2.1. Fundamental Concepts

* __Random Variable__. A _random variable_ is a variable $X$ whose value is randomly
  selected from a probability distribution defined by one of the following functions.

  * __Cumulative Distribution Function (CDF)__. The _cumulative distribution function_,
    typically denoted by $F_X(x)$ or $F(x)$ (when the random variable is clear from
    context), is the probability that a random variable $X$ is no more than $x$:

    $$
    F_X(x) = \Pr{X \le x}
    $$

  * __Upper Tail Probability__: $\Fbar_X(x) = \Pr{X > x} = 1 - F_X(x)$

  * __Probability Density Function__. When $X$ is a _continous random variable_, the
    probability distribution may be specified by a _probability density function_, denoted
    by $p(x)$:

    $$
    p(x) = \frac{d F_X}{dx}.
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
    $p(x)$:

    $$
    p(x) = \Pr{X = x}.
    $$

* __Random Vector__. A _random vector_ is a vector $(X_1, \ldots, X_n)$ which has
  components that are random variables. The probability distribution of a random vector is
  defined by one of the following functions.

  * __Joint Distribution Function__. The _joint distribution function_ for a random vector
    $(X_1, \ldots, X_n)$ is defined as

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

  The marginal distribution function of any subvector of $(X_1, \ldots, X_n)$ is defined
  analogously.

* __Independence__. Random variables $X_1, \ldots, X_n$ are _independent_ if their joint
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

* __Median__. The _median_ of a random variable $X$ is any value $\nu$ satisfying the
  property that

  $$
  \Pr{X \ge \nu} \ge \frac{1}{2}
  $$

  and

  $$
  \Pr{X \le \nu} \ge \frac{1}{2}.
  $$

### 2.2. Expected Value

#### 2.2.1. Definitions

* __Expected Value__. The _expected value_ of a random variable $X$, denoted by $\E{X}$, is
  one way to estimate the "typical value" realized by $X$. When $X$ is a continuous random
  variable, $\E{X}$ is defined as

  $$
  \E{X} = \int_{-\infty}^\infty x p(x) dx.
  $$

  When $X$ is a discrete random variable, $\E{X}$ is defined as

  $$
  \E{X} = \sum_{i} x_i \Pr{X = x_i} = \sum_{i} x_i p(x_i).
  $$

  * __Expected Value of a Function of Random Variable__. Let $h(X)$ be a function of a
    continuous random variable $X$. Then $h(X)$ is a random variable and the expected value
    of $h(X)$ may be expressed as

    $$
    \begin{align}
    \E{h(X)}
    &= \int_{-\infty}^\infty h(x) dF(x) \\
    &= \int_{-\infty}^\infty h(x) p(x) dx
    \end{align}
    $$

* __Moments__. The $m$-th moment of $X$ is defined as $\E{X^m}$.

  * __Central Moment__. The $m$-th central moment of $X$ is defined as
    $\E{\left( X - \E{X} \right)^m}$.

  * __Absolute Moment__. The $m$-th absolute moment of $X$ is defined as $\E{|X|^m}$.

  * __Expected Value, Mean, Average__: the first moment of $X$, $\E{X}$

  * __Variance__: the second central moment of $X$

    $$
    \var{X} = \E{\left( X - \E{X} \right)^2} = \E{X^2} - (\E{X})^2
    $$

* __Standard Deviation__. The _standard deviation_ of $X$, denoted $\stddev{X}$, is
  defined
  as

  $$
  \stddev{X} = \sqrt{\var{X}}.
  $$

* __Covariance__: the _covariance_ of two random variables $X$ and $Y$ is defined as

  $$
  \begin{align}
  \cov{X}{Y}
  &= \E{ \left(\left( X - \E{X} \right) \left( Y - \E{Y} \right)\right) } \\
  &= \E{XY} - \E{X}\E{Y} \\
  \end{align}
  $$

* __Uncorrelated__. Random variables $X$ and $Y$ are _uncorrelated_ if their covariance
  is 0:

  $$
  \E{(X - \mu_X)(Y - \mu_Y)} = \E{XY} - \mu_X \mu_Y = 0.
  $$

#### 2.2.2. Basic Results

* __Linearity of Expected Value__. Let $X_1, \ldots, X_n$ be arbitrary random variables.
  Then

  $$
  \E{X_1 + \cdots + X_n} = \E{X_1} + \cdots + \E{X_n}
  $$

  _regardless_ of whether the $X_i$ are independent or have dependencies between them.

* __Expected Value in Terms of Tail Probabilities__. The expected value of a random
  variable can be expressed as an integral or sum over tail probabilities. This identity
  can be useful for bounding expected values by tail probabilities.

  * __Discrete Random Variables__ (Taylor and Karlin, Section I.5.1). Let $X$ be a
    non-negative discrete random variable. Then

    $$
    \E{X} = \sum_{k=0}^\infty \Pr{X > k} = \sum_{k=1}^\infty \Pr{X \ge k}
    $$

    _Proof_. Observe that any non-negative integer $n$ can be expressed as the sum

    $$
    n = \sum_{k=0}^\infty \1{k < n}.
    $$

    Substituting this expression for the random variable $X$, taking expected values, and
    using linearity of expected values yields

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
  \E{ |X|^\alpha } = \int_0^\infty |x|^\alpha p(x) dx.
  $$

  Expressing $|x|^\alpha$ as the integral

  $$
  \alpha \int_0^{|x|} t^{\alpha - 1} dt,
  $$

  we obtain

  $$
  \E{ |X|^\alpha }
  = \int_0^\infty \left(\alpha \int_0^{|x|} t^{\alpha - 1} dt \right) p(x) dx
  = \alpha \int_0^\infty \int_0^{|x|} t^{\alpha - 1} p(x) dt dx.
  $$

  Interchanging the order of integration yields the desired result

  $$
  \E{ |X|^\alpha }
  = \alpha \int_0^\infty \left( \int_t^\infty p(x) dx \right) t^{\alpha - 1} dt
  = \alpha \int_0^\infty t^{\alpha - 1} \Pr{|X| > t} dt
  $$

### 2.3. Random Sums and Products

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
  $Z = \sum_{i=1}^n a_i X_i$ are

  $$
  \E{Z} = \sum_{i=1}^n a_i \E{X_i}
  $$

  and

  $$
  \begin{align}
  \var{Z}
  &= \sum_{i=1}^n a_i^2 \var{X_i} + \sum_{i,j=1, i \ne j}^n a_i a_j \cov{X_i}{X_j} \\
  &= \sum_{i=1}^n a_i^2 \var{X_i} + 2 \sum_{i,j=1, i < j}^n a_i a_j \cov{X_i}{X_j} \\
  \end{align}
  $$

  Both of these results following directly from the linearity of expected values.

* __Random Products__. Let $X_1, \ldots, X_n$ be independent random variables. Then

  $$
  \E{X_1 \cdots X_n} = \E{X_1} \cdots \E{X_n}.
  $$

### 2.4. Other Useful Results

* __Relationship between Independent and Uncorrelated__

  * Random variables that independent are uncorrelated (assuming that all relevant expected
    values are finite).

  * Random variables that are uncorrelated need not be independent.

* __Existence of the Values of a Random Variable__. If the expected value of a random
  variable exists (i.e., is finite), then we are guaranteed the existence of

  * at least one instance of the random variable no greater than expected value and

  * at least one instance of the random variable no less than expected value.

--------------------------------------------------------------------------------------------

## 3. Moment-Generating and Characteristic Functions

### 3.1. Fundamental Concepts

* __Moment-Generating Function (MGF)__. For $t \in \R$, the _moment-generating function_ is
  the expected value of $e^{tX}$ of a random variable $X$:

  $$
  M(t) = \E{e^{tX}} = \int_{-\infty}^\infty e^{tx} p(x) dx
  $$

  _Note_: the moment-generating function only exists for probability density functions
  where the integral converges.

* __Characteristic Function__. For $t \in \R$, the _characteristic function_ is the
  expected value of $e^{itX}$ of a random variable $X$ (essentially the Fourier transform
  of the probability density function):

  $$
  \phi(t) = \E{e^{itX}} = \int_{-\infty}^\infty e^{itx} p(x) dx
  $$

  _Note_: the characteristic function exists for all probability density functions.

* __Random Vectors__. For $t_1, t_2, \ldots, t_n \in \R$,
  the moment-generating function of a random vector $(X_1, X_2, \ldots, X_n)$ is defined by

  $$
  M(t_1, t_2, \ldots, t_n) = \E{e^{\sum_{i=1}^n t_i X_i}}
  = \int_{-\infty}^\infty \exp\left( \sum_{i=1}^n t_i x_i \right) p(x_1, x_2, \ldots, x_n)
                          dx_1 dx_2 \cdots dx_n.
  $$

  The characteristic function for random vectors is defined analogously.

### 3.2. Basic Results

* __Unique Characterization of Probability Distributions__. Both the moment-generating and
  characteristic functions _completely define_ the probability distribution of a random
  variable.

  * If two probability distributions have the same moment-generating or characteristic
    function, then they are identical (except possibly on a set of measure zero).

* __Computing Moments__. The moments of a random variable $X$ can be computed
  from the derivatives of the moment-generating or characteristic function:

  $$
  \E{X^n} = \left. \frac{d^n}{dt^n} M(t) \right|_{t=0}
  $$

  $$
  \E{X^n} = i^{-n} \left[ \frac{d^n}{dt^n} \phi(t) \right]_{t = 0}
  $$

  _Proof_. The result follows from the following observations:

  $$
  \frac{d^n}{dt^n} M(t)
  = \frac{d^n}{dt^n} \E{e^{tX}}
  = \E{X^n e^{tX}}.
  $$

  $$
  \frac{d^n}{dt^n} \phi(t)
  = \frac{d^n}{dt^n} \E{e^{itX}}
  = i^n \E{X^n e^{itX}}.
  $$

* __Probability Distributions of Sums of Independent Random Variables__

  * Moment-generating and characteristic functions are useful for calculating the
    probability distributions of linear combinations of independent random variables.

  * Let $S = \sum a_k X_k$ where $X_k$ are independent random variables and the $a_k$ are
    constants. Then the moment-generating function for $S$ is given by

    $$
      M_S(t) = \E{e^{tS}}
      = \E{\exp\left( \sum_{k = 1}^N t a_k x_k \right)}
      = \E{\prod_{k = 1}^N e^{t a_k x_k}}
      = \prod_{k = 1}^N \E{e^{(a_k t) x_k}}
      = \prod_{k = 1}^N M_{X_k}(at).
    $$

    where the second to last equality follows from the independence of the $X_k$ and
    $M_{X_K}(t)$ is the moment-generating function for $X_k$.

  * Similarly, the characteristic function for $S$ is given by

    $$
      \phi_S(t) = \E{e^{itS}}
      = \E{\exp\left( \sum_{k = 1}^N i t a_k x_k \right)}
      = \E{\prod_{k = 1}^N e^{i t a_k x_k}}
      = \prod_{k = 1}^N \E{e^{i (a_k t) x_k}}
      = \prod_{k = 1}^N \phi_{X_k}(at)
    $$

  * In some situations, it is possible to invert $\phi_S(t)$ or $M_S(t)$ to obtain the
    probability density function for the sum $S$.

    * For some common distributions, it is possible to recognize that the
      moment-generating/characteristic function for a sum is equal to the
      moment-generating/characteristic function for a known distribution.

    * Laplace transform tables are useful for inverting $M_S(t)$.

    * Fourier transform tables are useful for inverting $\phi_S(t)$.

    * When inversion tables are insufficient, contour integration techniques (including
      approximation methods) can be useful to analyze the properties of the probability
      density function.

* __Linear Transformations of Random Variables__. If $S = aX + b$, then the
  moment-generating and characteristic functions for $S$ are

  $$
  \begin{align}
  M_S(t) &= \E{e^{t (aX + b)}} = e^{tb} \E{e^{(at)X}} = e^{tb} M_X(at) \\
  \phi_S(t) &= \E{e^{it (aX + b)}} = e^{itb} \E{e^{i(at)X}} = e^{itb} \phi_X(at) \\
  \end{align}
  $$

* __Other Results__
  * For random variables that are nonnegative, it can be more convenient to work with the
    Laplace transform of the random variable instead of the moment-generating or
    characteristic function.

  * When a random variable has a moment-generating function $M(t)$, then the characteristic
    function $\phi(t)$ can be extended to the complex plane and $M(t) = \phi(-it)$.

--------------------------------------------------------------------------------------------

## 4. Basic Probability Bounds

* __Jensen's Inequality__. If $f$ is a convex function, then

  $$
  f(\E{X}) \le \E{f(X)}.
  $$

  _Proof_. Let $\mu = \E{X}$. Under the assumption that $f$ is twice-differentiable at
  $\mu$ and $f'$ is continuous on an interval containing $\mu$, $f(x)$ can be represented
  by the first-order Taylor polynomial at $\mu$:

  $$
  f(x) = f(\mu) + f'(\mu) (x - \mu) + \frac{f''(\xi)}{2} (x - \mu)^2
  $$

  where $\xi$ lies between $\mu$ and $x$. Since $f$ is convex, $f''(\xi) \ge 0$, which
  implies that

  $$
  f(x) \ge f(\mu) + f'(\mu) (x - \mu).
  $$

  Taking expectations, we find that

  $$
  \begin{align}
  \E{f(X)}
  &\ge \E{f(\mu) + f'(\mu) (x - \mu)} \\
  &= f(\mu) + f'(\mu) \E{x - \mu} \\
  &= f(\mu) + f'(\mu) \left( \E{x} - \mu \right) \\
  &= f(\mu)
  \end{align}
  $$

  where the last equality follows because $\E{x} = \mu$.

* __Union Bound__. Let $A_1, \ldots$ be a collection of events. Then the probability
  that probability any of the events occurs (i.e., the union of the events) is bounded by
  sum of the probabilities of the individual events:

  $$
  \Pr{\textrm{any of the $A_i$ occurs}}
  = \Pr{\bigcup_{i=1}^\infty A_i}
  \le \sum_{i=1}^\infty \Pr{A_i}.
  $$

  _Remark_. The expression on the right-hand side of the inequality is the first term of
  the inclusion-exclusion principle.

* __Basic Tail Bounds__

  * __Markov's Inequality__. Let $X$ be a non-negative random variable with a finite mean.
    Then the tail probability for $X$ satisfies the bound

    $$
    \Pr{X \ge t} \le \frac{\E{X}}{t}.
    $$

    _Proof 1_. If $X$ possesses a probability density function $p(x)$, then

    $$
    \E{X}
    = \int_0^\infty x p(x) dx
    \ge \int_t^\infty x p(x) dx
    \ge \int_t^\infty t p(x) dx
    = t \Pr{X \ge t}.
    $$

    Rearranging this inequality yields the desired result.

    _Proof 2_. Expressing the expected value in terms of tail probabilities,

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
    \Pr{|X - \mu| \ge t} \le \frac{\var{X}}{t^2}.
    $$

    _Proof_. Observe that

    $$
    \Pr{|X - \mu| \ge t} = \Pr{(X - \mu)^2 \ge t^2}.
    $$

    Since $(X - \mu)^2$ is non-negative random variable, Markov's inequality implies that

    $$
    \Pr{(X - \mu)^2 \ge t^2}
    \le \frac{\E{(X - \mu)^2}}{t^2}
    \le \frac{\var{X}}{t^2}.
    $$

  * __Generic Chernoff Bounds__. The moment-generating function can be used to compute
    bounds on the probability contained in the upper tail of a probability distribution.

    When $t > 0$,

    $$
    \Pr{X \ge a} = \Pr{e^{tX} \ge e^{ta}} \le e^{-at} \E{e^{tX}} = e^{-at} M(t)
    $$

    where the first equality follows because $e^{tx}$ is a monotonically increasing
    function of $x$ when $t > 0$ and the inequality follows from Markov's inequality.

    When $t < 0$,

    $$
    \Pr{X \le a} = \Pr{e^{tX} \ge e^{ta}} \le e^{-at} \E{e^{tX}} = e^{-at} M(t)
    $$

    where the first equality follows because $e^{tx}$ is a monotonically decreasing
    function of $x$ when $t < 0$ and the inequality follows from Markov's inequality.

    _Remark_. These bounds for the tail probabilities forms the foundation of "optimal"
    Chernoff bounds.

* __Bounds on Moments__

  * __Upper Bound on $e^{\mu t}$__. Let $\mu = \E{X}$. Then

    $$
    e^{\mu t} \le M(t).
    $$

    _Proof_. The bound follows directly from Jensen's inequality because $e^{tx}$ is a
    convex function of $x$.

  * __Upper Bounds on the Moments__. The $m$-th moment of $X$ is bounded from above:

    $$
    E[X^m] \le \left( \frac{m}{te} \right)^m M(t).
    $$

    _Proof_. Letting $z = Xt/m - 1$ in the inequality $1 + z \le e^z$ and rearranging, we
    obtain the inequality

    $$
    X^m \le \left( \frac{m}{te} \right)^m e^{tX}.
    $$

    Taking the expected value of both sides yields the desired result.

--------------------------------------------------------------------------------------------

## 5. References

1. S.M. Ross. "Introduction to Probability and Statistics for Engineers and Scientists"
   (2004).

2. S.M. Ross. "Stochastic Processes" (1996).

3. R. Vershynin. "High-Dimensional Probability". (2018)

4. H.M. Taylor and S. Karlin. "An Introduction to Stochastic Modeling". (1998)

5. [Wikipedia: Characteristic function][wikipedia-characteristic-function]

6. [Wikipedia: Moment-generating function][wikipedia-moment-generating-function]

7. [Wikipedia: Boole's Inequality][wikipedia-booles-inequality]

--------------------------------------------------------------------------------------------

[----------------------------------- INTERNAL LINKS -----------------------------------]: #

[#1]: #1-basic-probability
[#1.1]: #11-fundamental-concepts
[#1.2]: #12-basic-results
[#1.3]: #13-infinite-collections-of-events

[#2]: #2-random-variables
[#2.1]: #21-fundamental-concepts
[#2.2]: #22-expected-value
[#2.3]: #23-random-sums-and-products
[#2.4]: #24-other-useful-results

[#3]: #3-moment-generating-and-characteristic-functions
[#3.1]: #31-fundamental-concepts
[#3.2]: #32-basic-results
[#3.3]: #33-applications

[#4]: #4-basic-probability-bounds

[#5]: #5-references

[----------------------------------- EXTERNAL LINKS -----------------------------------]: #

[wikipedia-characteristic-function]: https://en.wikipedia.org/wiki/Characteristic_function_(probability_theory)

[wikipedia-moment-generating-function]: https://en.wikipedia.org/wiki/Moment-generating_function

[wikipedia-booles-inequality]: https://en.wikipedia.org/wiki/Boole%27s_inequality
