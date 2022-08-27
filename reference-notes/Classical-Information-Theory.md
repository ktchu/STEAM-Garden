Classical Information Theory: Summary of Core Concepts
======================================================

__Last Updated__: 2020-05-05

-------------------------------------------------------------------------------

Preface
-------

* This document is written using GitHub Markdown.  It is best viewed using a
  Markdown viewer that supports GitHub Markdown:

  * [Chrome Markdown Viewer][chrome-markdown-viewer]

    * _Note_: be sure to enable the following extension settings

      * Automatically allow access on the following sites
        * `file:///*`

      * Allow access to file URLS

  * [Atom Editor](https://atom.io/)

-------------------------------------------------------------------------------

Table of Contents
-----------------

1. [Essence of Information Theory][#1]

2. [Information Content][#2]

3. [Information Overlap and Transformations][#3]

4. [Information Content: Continuous Random Variables][#4]

5. [Information Overlap and Transformations: Continuous Random Variables][#5]

6. [Information Communication and Encoding][#6]

7. [References][#7]

-------------------------------------------------------------------------------

## 1. Essence of Information Theory

Information theory provides a framework for understanding and characterizing
one or more data sources by analyzing the properties of the distribution
of symbols produced by the data sources.

### 1.1. Key Features

* The individual symbols produced by the data source have no intrinsic
  mathematical structure.

* All of the structure of the data source is contained in the probability
  distribution of the data source.

### 1.2. Notes

* In this document, all logarithms are base 2.

-------------------------------------------------------------------------------

## 2. Information Content

### 2.1. Definitions

* __Data Source__: a collection of symbols and the probability distribution
  over the symbols

* __bit__: a unit of measure for the number of possible values that a random
  variable can take

### 2.2. Measures of Information

* __Capacity__: number of symbols in a data source

* __Content__: entropy of probability distribution over symbols

  * ___Entropy___. The entropy $H(X)$ of a data source is equal to the
    expected value of $1 / p(x)$ where $x$ is a symbol and $p(x)$ is the
    probability of obtaining $x$ from the data source:
    $H(X) = E[ \log(1/p(X)) ]$.

  * ___Relationship to Uncertainty___. The entropy of a data source can be
    interpreted as the average uncertainty/surprise of a single sample from
    the data source.

  * ___Estimating Entropy___. Entropy estimates based on simple sample-based
    estimates of the probability distribution of symbols _overestimate_ the
    entropy because they assume that samples are independent.

    * ___TODO___. Reconcile these two ideas: (1) MLE estimate of entropy
      computed using sample-based estimates of the probabilities
      _underestimates_ the entropy and (2) estimates of entropy that ignore
      dependence between samples _overestimates_ the entropy.

    * _Intuition_. Assuming that samples are independent is analogous to
      using multiple symbols to represent a single value or splitting a single
      symbol into multiple symbols. Both of these transformations increase the
      apparent entropy of the data source by making it look like there is
      more uncertainty in the outcome than there really is. Mathematically,
      the probability distribution appears to be more spread out than it
      really is because the probability that would originally have been
      concentrated in a single value is distributed across multiple symbols.

    * _Examples_

      * Estimation of the distribution of letters in the alphabet based on
        text samples.

      * Estimation of the distribution of pixel intensities based on simple
        pixel sampling from images.

### 2.3. Key Ideas

* __Relation between number of bits and uncertainty__. Each bit represents a
  multiplicative factor of 2 for the amount of uncertainty (in the sense of
  probability) there is about the value of a random variable. $n$ bits
  represents a multiplicative factor of $2^n$. _Note_: $n$ is permitted to be
  a non-integer value.

  * ___Special Cases___

    * For a uniformly distributed random variable, the number of bits is
      related to the number of values available to the random variable.

  * ___Examples___.

    * If the entropy of a random variable $X$ increases by $n$ bits, then
      uncertainty in $X$ increases by a factor of $2^n$.

    * If we receive $n$ bits about a random variable $X$, then the amount
      of uncertainty in $X$ decreases by a factor of $2^n$.

    * If we receive half a bit of information about a random variable, the
      uncertainty in the random variable is reduced by a factor of
      $2^{0.5} \approx 0.71$.

* __Maximum Entropy Distribution__. For a data source with a capacity of $n$,
  the maximum entropy distribution is a uniform distribution over the $n$
  symbols in the data source. The value of the maximum entropy is $\log n$.

* __Asymptotic Equipartition Property (AEP)__

  * For sequences of independently selected symbols,

    * most events that could _potentially_ occur, do not occur; and

    * the events that do occur, occur with almost the same probability.

  * For a data source with entropy $H$, the number of typical sequences of
    length $n$ is $2^{nH}$.

-------------------------------------------------------------------------------

## 3. Information Overlap and Transformations

### 3.1. Definitions

* __Information Transformation__: "mapping" between two collections of
  symbols

  * An information transformation is _not_ necessarily a mathematical function
    between input symbols and output symbols because each input symbol can be
    associated with multiple outputs.

  * An information transformation _is_ a function between the input symbols
    and the power set of the output symbols (i.e., the set of subsets of
    the collection of output symbols).

### 3.2. Key Ideas

* __Relative Entropy__: measure of the difference between two probability
  distributions

  \[
    D(p||q) = E \left[ \log \frac{ p(X) }{ q(X) } \right]
  \]

  where the expectation is taken over the probability distribution $p$.

  * ___Key Results___

    * Relative entropy is ___not___ a true distance/metric function.
      * $D(p||q)$ is not symmetric in the probability distributions
      * $D(p||q)$ does not satisfy the triangle inequality

    * The relatively entropy is always non-negative $D(p||q) >0$ and is
      zero iff $p = q$.

    * The relative entropy also goes by the name _Kullback-Leibler divergence_.

* __Joint Entropy__: entropy of joint probability distribution of two data
  sources (e.g., inputs and outputs of a transformation)

  * The joint entropy $H(X,Y)$ of two data sources is equal to the expected
    value of $1 / p(x, y)$ where $p(x, y)$ is the probability of obtaining
    $x$ and $y$ from data sources $X$ and $Y$:

    \[
      H(X,Y) = E[ \log(1/p(X,Y) ].
    \]

  * ___Statistically Independent Data Sources___. For
    _statistically independent_ data sources, the joint entropy is equal to
    the sum of the entropies of the individual data sources:

    \[
      H(X,Y) = H(X) + H(Y).
    \]

* __Conditional Entropy__: entropy of conditional probability distribution
  of data source given the value of a symbol drawn from a second data source
  averaged over all possible symbols of the second data source:

  \[
    H(X|Y) = H(X,Y) - H(Y).
  \]

  * ___Derivation___

    \[
      H(X|Y) = E_Y[ E_{X|Y} [ \log(1/p(X|Y)) ] ] \\
             = E_Y[ E_{X|Y} [ \log(p(Y) / p(X,Y)) ] ] \\
             = E_Y[ E_{X|Y} [ \log(1 / p(X,Y)) - \log(1 / p(Y)) ] ] \\
             = E_Y[ E_{X|Y} [ \log(1 / p(X,Y)) ]
                  - E_{X|Y}[ \log(1 / p(Y)) ] ] \\
             = E_Y[ E_{X|Y}[ \log(1 / p(X,Y)) ] - \log(1 / p(Y)) ] \\
             = E_Y[ E_{X|Y}[ \log(1 / p(X,Y)) ] ] - E_Y[ \log(1 / p(Y)) ] \\
             = H(X,Y) - H(Y)
    \]

  * ___Interpretation___. For information transformations from $X$ to $Y$,

    * the typical number of outputs that each input is associated with is
      $2^{H(Y|X)}$;

    * the typical number of inputs that is associated with each output is
      $2^{H(X|Y)}$.

  * ___Key Results___

    * The conditional entropy is always less than the unconditional entropy:
      $H(X|Y) \le H(X)$.

  * ___Applications___

    * _Noisy Communication Channels_. A noisy communication channel adds
      noise to messages sent on the channel.

        * The conditional entropy $H(Y|X)$ is a measure of the entropy of the
          channel noise.

        * Note that, for any practical communication channel, the uncertainty
          in the input given the output must be bounded above by the channel
          noise: $H(X|Y) \le H(Y|X)$. Otherwise, $H(Y) \le H(X)$, which
          implies that the output has a smaller information content than the
          input. In other words, the space of outputs is not large enough for
          the inputs to be uniquely mapped to outputs (even in the absence of
          channel noise).

* __Mutual Information__. Relative entropy between the joint probability
  distribution of two data sources $X$ and $Y$ and the product distribution
  $p(x) p(y)$:

  \[
    I(X;Y) = E\left[ \log \frac{ p(X,Y) }{ p(X) p(Y) } \right].
  \]

  * ___Interpretations___. Note that the first three representations of mutual
    information are consistent because $H(X|Y) = H(Y) - H(X,Y)$.

    * $I(X;Y)$ is a measure of the statistical dependence between two data
      sources and is equal to the difference between the joint entropy
      assuming that the data sources are independent and the actual joint
      entropy. _Note_: mutual information is blind to the nature of the
      relationship between $X$ and $Y$.

      \[
        I(X;Y) = H(X) + H(Y) - H(X,Y)
      \]

    * $I(X;Y)$ represents the decrease in uncertainty of one data source
      resulting from information gained from a second data source:

      \[
        I(X;Y) = H(X) - H(X|Y).
      \]

    * $I(X;Y)$ represents the amount of entropy in $Y$ that is exclusively
      related to the entropy in $X$ (and vice versa) -- that is, it is the
      amount of entropy that it _not related to noise_:

      \[
        I(X;Y) = H(X,Y) - [ H(X|Y) + H(Y|X) ],
      \]

      where $H(X|Y)$ is the entropy of $X$ due to noise and $H(Y|X)$ is the
      entropy of $Y$ due to noise.

    * $I(X;Y)$ represents the average (over $Y$) of relative entropy (KL
      divergence) between the posterior distribution of $X$ (given information
      about $Y$) and the prior distribution of $X$:

      \[
        I(X;Y) = E_Y [ D(p(X|Y)||p(X)) ]
               = E_Y \left[ E_{X|Y} \left[
                   \log \frac{ p(X|Y) }{ p(X) }
                 \right] \right]
               = E_Y \left[ E_{X|Y} \left[
                   \log \frac{ p(X,Y) }{ p(X) p(Y) }
                 \right] \right] \\
               = E \left[ \log \frac{ p(X,Y) }{ p(X) p(Y) } \right]
      \]

      By symmetry, $I(X;Y)$ also represents the average (over $X$) of the
      relative entropy of the posterior distribution of $Y$ (given information
      about $X$) and the prior distribution of $Y$.

  * ___Key Results___

    * Mutual information cannot be negative: $I(X;Y) \ge 0$.

    * For _statistically independent_ collections of symbols, the mutual
      information is 0.

    * _Redundant Information_. Mutual information is a measure of the amount
      of information shared between two data sources.

  * ___Applications___

    * _Channel Capacity_. The capacity of a channel (noisy or noiseless) is
      defined as the maximum achievable mutual information between inputs and
      outputs, where the maximum is taken over all possible probability
      distributions of the input.

      \[
        C = \max_{p(X)} I(X;Y).
      \]

      * _Note_: in the context of communication channels, mutual information
        is a related to the number of input values that can be reliably
        determined from knowledge of the output values. More precisely,
        mutual information is equal to the logarithm of the number of input
        values that can be discriminated.

### 3.3. Auxiliary Concepts

* __Schematic Representations__. Schematic representations are useful for
  visualizing the relationships between joint entropy, conditional entropy,
  marginal entropies, and mutual information.

  * _Venn Diagram_. The most commonly used schematic diagram. Under certain
    conditions, some areas in the Venn diagram can become negative.

  * _Joint Entropy Container_

    ```
    |-------------------------------- H(X,Y) --------------------------------|

    |--------------------- H(Y) ----------------------|------- H(X|Y) -------|

    |------------ H(X|Y) ------------|---------------- H(X) -----------------|

                                     |---- I(X;Y) ----|
    ```

    * $H(X, Y)$ acts as the "entropy container" and is composed of the
      following three components:

      * $H(X|Y)$: the entropy due to noise in $X$;

      * $H(Y|X)$: the entropy due to noise in $Y$;

      * $I(X;Y)$: the mutual information -- the entropy shared by $X$ and $Y$
        resulting from co-dependence of $X$ and $Y$.

* __Transmission Efficiency__. When applied to communication channels, the
  ratio of the mutual information to the output entropy is a measure of how
  efficiently information is transmitted from the input to the output:

  \[
    \frac{ I(X;Y) }{ H(Y) }
  \]

* __Chain Rule for Entropies__. The mathematical relationship between entropy
  of a single data source, joint entropy of two data sources, and conditional
  entropy can be arranged as the following chain rules:

  \[
    H(X, Y) = H(X) + H(Y|X) \\
    H(X, Y) = H(Y) + H(X|Y)
  \]

* __Error Correcting Codes__. TODO

* __Proof of Bounds via Averages__.  If the average over a set of values is
  $\epsilon$, then at least one of the values in the set must be less than or
  equal to $\epsilon$.

  * This idea is part of Shannon's original proof of the noisy channel coding
    theorem.

-------------------------------------------------------------------------------

## 4. Information Content: Continuous Random Variables

### 4.1. Critical Observations

* ___Entropy is not well-defined for continouous variables___.

  * __Entropy depends on bin width__. Estimates of the entropy based on
    discretization of the probability density function result in an entropy
    that diverges to infinity as the bin width decreases.

    * If a continuous probability density $p(x)$ is approximated as a discrete
      probability distribution using bins of width $\Delta x$, then discrete
      approximation to the entropy is given by:

      \[
        H( X^\Delta ) =
          \log \frac{1}{\Delta x} +
          \sum_i \left( p(x_i) \log \frac{1}{p(x_i)} \right) \Delta x
      \]

      As $\Delta x \rightarrow 0$, the $\log \frac{1}{\Delta x}$ term
      diverges to $\infty$, and the sum approaches the integral

      \[
        \int \left( p(x) \log \frac{1}{p(x)} \right) dx
      \]

  * __Intuition__. Using a greater precision to perform measurements (which
    corresponds to using a smaller bin width increases the amount of
    information provided by the measurement).

* ___Quantities that involve differences between entropies are well-defined___.

  * The divergent term in discrete approximations of the entropy cancel out
    for differences between entropies.

### 4.2. Definitions

* __Capacity__: TODO

* __Differential Entropy__: the part of the discrete approximation to the
  entropy that remains finite as the bin width decreases to 0:

  \[
    H_{dif}(X) = E[ \log(1 / p(X)) ]
            = \int \left( p(x) \log \frac{1}{p(x)} \right) dx
  \]

  * ___Estimating Differential Entropy___

    * _Discrete Approximation_. Discretize the continuous probability
      distribution and compute

      \[
        H_{dif}(X) \approx
        - \log \frac{1}{\Delta x} + \sum_i P_i \log \frac{1}{P_i}
      \]

      where $P_i = p(x_i) \Delta x$ is the probability of a sample occurring
      in the $i$-th bin.

    * _Kernel Estimation_. Fit a parametric function to the data and use
      analytic expressions to compute the differential entropy using the
      integral formulation.

### 4.3. Key Ideas

* __Meaning of Differential Entropy__

  * ___No direct relationship to information___. Unlike entropy for discrete
    random variables, differential entropy does not have a precise
    interpretation in terms of the amount of information each sample of the
    variable conveys. In principle, each value of a continuous variable
    conveys an infinite amount of information.

  * ___Noise limits the "information capacity" of continuous variables___.
    Intuitively, noise transforms a continuous random variable into a discrete
    random variable (by dividing the range of of the continuous variable into
    discrete intervals). The entropy of the discrete random variable has a
    finite entropy that is directly related to the average amount of
    information conveyed by each measurement.

* __Differential entropy changes under variable transformation__. Unlike
  discrete probability distributions (where the entropy does not depend on the
  value of the symbol), the value of $H_{dif}$ changes when the random
  variable is transformed. If $y = f(x)$, then the $H_{dif}(Y)$ is related to
  $H_{dif}(Y)$ via:

  \[
    H_{dif}(Y)
    = \int \left( p_Y(y) \log \frac{1}{p_Y(y)} \right) dy
    = \int \left( p_X(x) \log \frac{|df/dx|}{p_X(x)} \right) dx
    = H_{dif}(X) + E[|df/dx|]
  \]

  * ___Intuition___. Continuous random variables implicitly encode information
    about the (local) scale used to measure the random variable. A
    transformation of the random variable implicitly changes the (local) scale
    used to measure the random variable. Viewing the differential entropy as
    the limit of the entropy of discrete approximations of the continuous
    probability density (with a bin width adjustment), it makes sense that
    a transformation of the random variable changes the value of the
    differential entropy because for any particular choice of bin width, the
    approximate discrete probability distribution changes when the random
    variable is transformed.

  * ___Mathematical Origins___

    * $H_{dif}$ is an integral quantity

    * Continuous probability densities scale under a change of variables.

* __Interpretation of bits for continuous variables___. As for discrete random
  variables, each bit represents a multiplicative factor of 2 for the amount
  of uncertainty (in the sense of probability) there is about the value of a
  random variable. $n$ bits represents a multiplicative factor of $2^n$.
  _Note_: $n$ is permitted to be a non-integer value.

  * ___Special Cases___

    * For a uniformly distributed random variable, the number of bits is
      related to the "size" of the space of values available to the random
      variable.

* __Maximum Entropy Distributions__. Unlike discrete probability distributions,
  the maximum entropy distribution for a continuous random variable depends
  on the constraints that define the random variable. These can be derived
  using the calculus of variations.

  * ___Finite Range___. For a random variable with a finite range, the
    maximum (differential) entropy distribution is a uniform distribution over
    the possible values for the random variable. The value of the maximum
    entropy is $\sum_i \log l_i$, where $l_i$ is the length/area/volume of one
    of the regions whose union is the set of possible values for the random
    variable. For instance, if $a < x < b$ is the set of possible values for
    the random variable $X$, then the maximum entropy distribution is
    $p(x) = 1 / (b - a)$ and the value of the maximum differential entropy is
    $H_{dif} (X) = \log (b - a)$ bits.

  * ___Fixed Mean___. For a random variable that is positive and has a
    mean value $\mu$, the maximum (differential) entropy distribution is
    an exponential distribution: $p(x) = \frac{1}{\mu} e^{-x / \mu}$ and the
    value of the maximum differential entropy is $H_{dif} (X) = \log e \mu$
    bits.

  * ___Fixed Variance___. For a random variable with a specified variance
    $\sigma^2$, the maximum (differential) entropy distribution is Gaussian
    distribution:

    \[
      p(x) = \frac{1}{\sigma \sqrt{2 \pi}} e^{-(x-\mu)^2 / 2 \sigma^2}
    \]

    and the value of maximum differential entropy is

    \[
      H_{dif} (X) = \frac{1}{2} \log (2 \pi e) + \log \sigma
                  \approx 2.05 + \log \sigma.
    \]

      * _Application_. Many physical systems generate power-limited signals,
        which implies a signal with a limited variance. To transfer
        information with the greatest efficiency, the signal should be encoded
        so that the distribution of values is a Gaussian distribution. Since
        noise is typically Gaussian, the noisy signal is a combination of
        Gaussian random variables, so it too has a Gaussian distribution.
        Therefore, recordings of a signal that look like pure Gaussian noise
        may be an indication that the system is designed to communicate
        information optimally.

-------------------------------------------------------------------------------

## 5. Information Overlap and Transformations: Continuous Random Variables

### 5.1. Definitions

* __Joint Differential Entropy__: differential entropy of the joint probability
  density of two data sources:

  \[
    H_{dif} (X, Y) = E \left[ \log \frac{1}{p(X, Y)} \right]
                   = \iint p(x, y) \log \frac{1}{p(x, y)} dx dy.
  \]

  * ___Notes___

    * For continuous random variables, the infinity problems associated with
      joint entropy are still present. The infinities are handled in an
      analogous manner as for the single variable case (i.e., by only keeping
      the finite part).

    * The entropy of a discrete approximation to the probability density
      includes two divergent terms: $\log (1 / \Delta x)$ and
      $\log (1 / \Delta y)$.

* __Conditional Differential Entropy__: differential entropy of conditional
  probability density of a data source given the value measured for a second
  data source averaged over all possible values of the second data source:

  \[
    H_{dif} (X|Y) = E \left[ \log \frac{1}{p(X|Y)} \right]
                  = \iint p(x, y) \log \frac{1}{p(x|y)} dx dy \\
                  = \iint p(x, y) \log \frac{1}{p(x,y) / p(y)} dx dy
                  =   \iint p(x, y) \log \frac{1}{p(x,y)} dx dy
                    - \iint p(x, y) \log \frac{1}{p(y)} dx dy \\
                  =   E \left[ \log \frac{1}{p(X, Y)} \right]
                    - E \left[ \log \frac{1}{p(Y)} \right]
                  = H_{dif} (X, Y) - H_{dif} (Y).
  \]

  * ___Note___. The entropy (not differential) of a discrete approximation to
    the probability density only includes a $\log (1 / \Delta x)$ divergence
    -- the $\log (1 / \Delta y)$ divergence cancels out.

    \[
      H(X^\Delta, Y^\Delta) - H(Y^\Delta)
      =   \left(
            H_{dif}(X, Y) + \log \frac{1}{\Delta x} + \log \frac{1}{\Delta y}
          \right)
        - \left( H_{dif}(Y) + \log \frac{1}{\Delta y} \right) \\
      = H_{dif}(X, Y) - H_{dif}(Y) + \log \frac{1}{\Delta x}
    \]

  * ___Key Results___

    * The conditional differential entropy is always less than the
      unconditional entropy: $H(X|Y) \le H(X)$.

* __Relative Entropy__: measure of the difference between two probability
  distributions.

  \[
    D(p||q) = E \left[ \log \frac{ p(X) }{ q(X) } \right]
  \]

  where the expectation is taken over the probability distribution $p$.

  * ___Note___. Because the formula for relative entropy involves only the
    ratio of probability densities, relative entropies for discrete
    approximations to the probability density converge directly to the
    relative entropy for the continuous random variable. There are no
    divergent that need to be ignored.

  * ___Key Results___. All of the previous results about relative entropy for
    discrete random variables hold for continuous random variables.

    * Relative entropy is ___not___ a true distance/metric function.
      * $D(p||q)$ is not symmetric in the probability distributions
      * $D(p||q)$ does not satisfy the triangle inequality

    * The relatively entropy is always non-negative $D(p||q) >0$ and is
      zero iff $p = q$.

    * The relative entropy is also know as the _Kullback-Leibler divergence_.

* __Mutual Information__. As for discrete random variables, the mutual
  information of continuous random variables $I(X;Y)$ is a measure of the
  statistical dependence between the random variables $X$ and $Y$ and is
  blind to the precise nature of the relationship between the random variables.

  * ___Formulas___. The formulas for the mutual information of continuous
    random variables are the same as for discrete random variables with
    entropy replaced by differential entropy.

    * _Relative entropy between joint probability and product probability_

      \[
        I(X;Y) = E \left[ \log \frac{p(X,Y)}{p(X)p(Y)} \right]
               = H_{dif}(X) + H_{dif}(Y) - H_{dif}(X,Y).
      \]

    * _Conditional entropy formulation_

      \[
        I(X;Y) = H_{dif}(X) - H_{dif}(X|Y) = H_{dif}(Y) - H_{dif}(Y|X).
      \]

    * _Noise removal formulation_

      \[
        I(X;Y) = H_{dif}(X,Y) - [ H_{dif}(X|Y) + H_{dif}(Y|X) ].
      \]

    * _Expected relative entropy of posterior and prior distributions_

      \[
        I(X;Y) = E_Y [ D(p(X|Y)||p(X)) ] = E_X [ D(p(Y|X)||p(Y)) ]
      \]

  * ___Note___. The mutual information for discrete approximations to the
    probability density _does not_ contain any divergent terms -- all
    divergences cancel out.

  * ___Key Results___. All of the previous results about mutual information
    for discrete random variables hold for continuous random variables.

    * The mutual information represents the decrease in the uncertainty of
      one random variables resulting from knowledge gained from a second
      random variable.

    * The mutual information for continuous random variables is nonnegative:
      $I(X;Y) \ge 0$.

### 5.2. Key Ideas

* __Statistically Independent Data Sources__

  * ___Joint Differential Entropy___. The joint differential entropy for
    _statistically independent_ data sources is equal to the the sum of the
    differential entropies of the individual data sources:

    \[
      H_{dif}(X,Y) = H_{dif}(X) + H_{dif}(Y).
    \]

  * ___Mutual Information___.  For _statistically independent_ data sources,
    the mutual information is equal to 0:

    \[
        H_{dif}(X,Y) = H_{dif}(X) + H_{dif}(Y)
        \Rightarrow I(X;Y) = H_{dif}(X) + H_{dif}(Y) - H_{dif}(X,Y) = 0.
    \]

* __Mutual Information is Invariant to Variable Transformations__. The mutual
  information is invariant to invertible transformations of the random
  variables.

  * ___Significance___. Mutual information can be used to quantify the
    co-dependence between two variables independent of the method used to take
    measurements of the individual variables.

  * ___Proof___. Let $X' = f(X)$ and $Y' = g(Y)$ where $f$ and $g$ are
    invertible functions. Then

    \[
      H_{dif}(X', Y') =   H_{dif}(X, Y)
                        + E[ \log |f'(X)| ] + E[ \log |g'(Y)| ] \\
      H_{dif}(X') =   H_{dif}(X) + E[ \log |f'(X)| ] \\
      H_{dif}(Y') =   H_{dif}(Y) + E[ \log |g'(Y)| ].
    \]

    Therefore,

    \[
      I(X'; Y') = H_{dif}(X') + H_{dif}(Y') - H_{dif}(X', Y') \\
                =   H_{dif}(X) + E[ \log |f'(X)| ]
                  + H_{dif}(Y) + E[ \log |g'(Y)| ]
                  - \left(
                      H_{dif}(X, Y)
                    + E[ \log |f'(X)| ] + E[ \log |g'(Y)| ]
                    \right) \\
                = H_{dif}(X) + H_{dif}(Y) - H_{dif}(X, Y)
                = I(X; Y).
    \]

-------------------------------------------------------------------------------

## 6. Information Communication and Encoding

### 6.1. Definitions

* __Encoding__

  * ___Discrete Data Sources___: mapping from symbols (or blocks of symbols)
    to code words (often binary numbers)

  * ___Continuous Data Sources___: mapping from raw data source values to
    encoded values

* __Channel Capacity__: maximum amount of information that can be transferred
  over a communication channel. Mathematically, channel capacity $C$ is
  defined as

  \[
    C = \max_{p(X)} I(X;Y).
  \]

### 6.2. Key Ideas

* __Maximum Entropy Distributions__. Maximum entropy distributions are
  important because each individual value obtained from such distributions
  conveys the greatest amount of information.

* __The choice of encoding scheme affects information communication rates__.
  To maximize the amount of information that can be transferred over a
  communication channel, it is important to use an encoding scheme that
  transforms the distribution of a data source in a manner that maximizes
  the mutual information between the channel input and output.

  * ___For simple channel noise, maximize input (differential) entropy___.
    For simple models of the channel noise, maximizing the mutual information
    is equivalent to maximizing the (differential) entropy of the channel
    input.

    * _Discrete Channel_. Maximizing information transfer over discrete
      channels often relies on block-encoding. As the block length increases,
      two things happen:

      * the symbols in the block become less correlated (i.e., more
        independent) and

      * the probability distribution of typical sequences of symbols becomes
        more uniform (as a consequence of AEP).

      The result is that the block-encoding of the original symbols tends
      towards the maximum entropy distribution for discrete data sources.

    * _Gaussian Channel_. For a continuous channel where

      * the output is the sum of the input and noise: $Y = X + \eta$,

      * the output has a fixed variance (e.g. ,power-limited), and

      * the noise is independent of the input and has a Gaussian distribution,

      the mutual information between the input and output is equal to the
      difference between the differential entropies of the output and the
      noise

      \[
        I(X;Y) = H_{dif}(Y) - H_{dif}(Y|X) = H_{dif}(Y) - H_{dif}(\eta).
      \]

      Maximizing mutual information is equivalent to maximizing the
      differential entropy of the output, which implies $Y$ should have a
      Gaussian distribution. Since the sum of Gaussian distributions has a
      Gaussian distribution, the input $X$ should also have a Gaussian
      distribution.

    * _Fixed Range Channel_. For a continuous channel where

      * the output is the sum of the input and noise: $Y = X + \eta$,

      * the output has a fixed range,

      * the noise is independent of the input and is small relative to the
        input (i.e., $|\eta| \ll |X|$),

      the mutual information between the input and output is approximately
      equal to both the differential entropy of the output and the
      differential entropy of the input:

      \[
        I(X;Y) = H_{dif}(Y) - H_{dif}(Y|X)
               \approx H_{dif}(Y)
               \approx H_{dif}(X).
      \]

      To maximize $I(X;Y)$, $Y$ should have a uniform distribution over the
      fixed range. Therefore, $X$ should also have a uniform distribution.
      Encoding an arbitrary random variable $S$ to a uniform distribution is
      easily achieved by defining $X$ to be the cumulative distribution
      function for $S$:

      \[
        X(s) = \int_{-\infty}^s p_S(t) dt.
      \]

  * ___Approaches for Arbitrary Channels___. For arbitrary channels where
    there is

    * a defined relationship between the input and output and

    * a specified noise model,

    it should be possible to use the _calculus of variations_ to derive
    appropriate constraints and attributes for the input distribution.

### 6.3. Discrete Channels

#### 6.3.1. Common Encoding Schemes for Discrete Data Sources

* __Symbol Encoding__ (Huffman). The symbols of a data source with entropy
  $H$ can be encoded using binary numbers as code words so that the average
  code word length is between $H$ and $H + 1$.

* __Block Encoding__. A data source with entropy $H$ can be block-encoded
  using $H + \epsilon$ bits per symbol, where $\epsilon > 0$ is arbitrarily
  small, by using a sufficiently large block size.

  * By the Asymptotic Equipartition Property (AEP) of sequences, the number
    of _typical_ sequences of $n$ symbols is approximately $2^{nH}$.

  * We can encode the typical sequences using approximately $nH$ bits.

  * Therefore, the block-encoding uses approximately $H$ bits per communicated
    symbol.

#### 6.3.2. Discrete Channel Coding Theorems

* __Shannon's Noiseless Channel Coding Theorem__. A data source with
  entropy $H$ can be encoded so that it can be transmitted at an average
  rate of $C/H - \epsilon$ symbols per second over a channel with capacity
  $C$ of bits per second, where $\epsilon > 0$ is arbitrarily small.

* __Shannon's Noisy Channel Coding Theorem__. Let a discrete channel have
  a capacity $C$ and a discrete source with entropy per second $H$. If
  $H \le C$ there exists a coding system such that the output of the source
  can be transmitted over the channel with an arbitrarily small frequency
  of errors (or an arbitrarily small equivocation). If $H \ge C$ it is
  possible to encode the source so that the equivocation is less than
  $H - C + \epsilon$ where $\epsilon$ is arbitrarily small. There is no
  method of encoding which gives an equivocation less than $H - C$.

  * __Terminology__

    * _equivocation_: the uncertainty of the input given the output
      $H(X|Y)$

  * __Intuition__ (Cover & Thomas, 1991).

    * For large block lengths, all channels look like a noisy typewriter
      that randomly shifts the input.

      * Let $X^n$ and $Y^n$ denote length $n$ sequences of the input $X$ and
        output $Y$. Then, the approximate number of typical sequences $X^n$
        and $Y^n$ are $2^{n H(X)}$ and $2^{n H(Y)}$, respectively. The number
        of jointly typical sequences of length $n$ of pairs $(X, Y)$ is
        approximately $2^{n H(X,Y)}$. As a result, the probability of a pair
        of typical sequences $(X^n, Y^n)$ being a jointly typical sequence is
        approximately $2^{-n I(X;Y)}$. For each $Y^n$, the number of
        associated jointly typical sequences is approximately
        $2^{n H(X) - n I(X;Y)}$. To be able to uniquely associate an input
        sequence $X^n$ with an output sequence $Y^n$, we can only use one
        out of every $2^{n H(X) - n I(X;Y)}$ typical input sequence. Therefore,
        the number of distinguishable sequences $X^n$ is approximately
        $2^{n H(X)} / 2^{n H(X) - n I(X;Y)} = 2^{n I(X;Y)}$.

    * The total number of typical output sequences of length $n$ is
      approximately $2^{n H(Y)}$.

    * The typical number of output sequences associated with each input
      is approximately $2^{n H(Y|X)}$.

    * To be able to uniquely identify an input given the output value,
      the typical subsets of $Y$ associated with input values should be
      disjoint. This provides an upper bound on the number of inputs
      that can be transmitted error-free:

      \[
        \frac{ 2^{n H(Y)} }{ 2^{n H(Y|X)} } = 2^{n (H(Y) - H(Y|X))}
        = 2^{n I(X;Y)}.
      \]

    * If $H(X) \le C = \max I(X;Y)$, then there are enough pre-image inputs
      that map to the disjoint subsets of $Y$ that can be used to encode
      the elements of $X$ for error-free transmission.

    * If $H(X) \ge C$, then there are not enough pre-image inputs to use
      encode the elements of $X$. The greatest uncertainty in the input
      given an output occurs when we distribute the elements of $X$
      uniformly amongst the pre-images. In this situation, each pre-image
      encodes $2^{ n H } / 2^{n C} = 2^{n (H-C)}$ inputs. Therefore, the
      typical number of inputs associated with each output is
      approximately $2^{n (H-C)}$. In other words, the equivocation is
      approximately $H - C$.

### 6.4. Auxiliary Concepts

* __Encodings vs Communication Channels__. Both encodings and communication
  channels transform data sources, so the constructs and concepts of
  information theory can be applied to analyze both stages of a communication
  system. The main differences between encodings and communication channels
  are (1) their purpose and (2) their information theoretic characterization.

  * ___Encodings___

    * _Purpose_: preparation for communication, compression, etc.

    * _Constraints_

      * Mathematical transformation can be _designed_.

    * _Desired Properties_

      * Very high mutual information between input and output.

      * Lossless when possible. Ideally, noise/lossiness should be
        controllable.

  * ___Communication Channels___.

    * _Purpose_: high-fidelity transmission of information

    * _Constraints_

      * Mathematical structure of transformation induced by communication
        channel constrained by physics, biology, etc.

      * Noise is likely to be uncontrollable.

    * _Desired Properties_:

      * High mutual information between input and output.

-------------------------------------------------------------------------------

## 7. References

1. J.V. Stone. "Information Theory" (2015).

2. T.M. Cover an J.A. Thomas. "Elements of Information Theory" (1991).

-------------------------------------------------------------------------------

[-----------------------------INTERNAL LINKS-----------------------------]: #

[#1]: #1-essence-of-information-theory

[#2]: #2-information-content

[#3]: #3-information-overlap-and-transformations

[#4]: #4-information-content-continuous-random-variables

[#5]: #5-information-overlap-and-transformations-continuous-random-variables

[#6]: #6-information-communication-and-encoding

[#7]: #7-references

[-----------------------------EXTERNAL LINKS-----------------------------]: #

[chrome-markdown-viewer]: https://chrome.google.com/webstore/detail/markdown-viewer/ckkdlimhmcjmikdlpkmbgfkaikojcbjk
