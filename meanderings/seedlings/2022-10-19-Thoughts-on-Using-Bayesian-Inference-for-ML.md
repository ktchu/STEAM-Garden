---
tags: probability, bayesian-inference
---

--------------------------------------------------------------------------------------------

2022-10-19: Bayesian Inference in the Absence of a Complete Likelihood Model
============================================================================

_Author(s)_: Kevin Chu `<kevin@velexi.com>`

_Last Updated_: 2022-10-20

--------------------------------------------------------------------------------------------
## Summary

__BROKEN__. The lower bound is too weak. Even if $L \approx 1$, the updated lower bound
can't increase. We need to include at least two likelihood functions that are
"well-separated" when viewed probability densities/distributions for the observations
given the outcomes.

__IDEAS__.

* Kalman filter for probability estimates.

* Kalman filter to control outcomes.

This note describes a way that Bayesian inference can be used to bound the _a posteriori_
probabilities for a set of mutually exclusive events $\{ E_1, \ldots, E_n \}$ given a
sequence of observations of $\{ D_1, \ldots, D_k \}$ when the likelihood of events given
observations is only _partially known_ (i.e., specified for a subset of the events).

TODO: add more. add application to decision making.

### Key Results

TODO

--------------------------------------------------------------------------------------------
## Notation

* $\newcommand{\Pr}[1]{{\mathbb{P}\left[{#1}\right]}}$
  Probability of event $E$: $\Pr{E}$

* Conditional probability of event $A$ given $B$: $\Pr{A | B}$

* The complement of an event $E$: $E^c$

* $\newcommand{\P}[1]{{P\left({#1}\right)}}$
  For a random variable $X$ with values $\{ x_1, \ldots, x_n \}$, the probability that
  $X = x_i$: $\P{x_i}$

* For a random variables $X$ and $Y$, the probability that $X = x$ given $Y = y$:
  $\P{x | y}$

* $\newcommand{\L}[2]{{L\left({#1}|{#2}\right)}}$
  The likelihood of event $A$ given observation $B$: $\L{A}{B}$

--------------------------------------------------------------------------------------------
## Theoretical Foundations

### Lemma 1. $\Pr{A | B}$ is Bounded from Below by a Function of $\Pr{A}$ and $\Pr{B | A}$

Let $A$ and $B$ be events. Then

$$
\Pr{A | B} \ge \frac{\Pr{B | A} \Pr{A}}{1 - \Pr{A} (1 - \Pr{B | A})}
$$

_Proof_. From Bayes' Theorem, we know that

$$
\Pr{A | B} = \frac{\Pr{B | A} \Pr{A}}{\Pr{B}}
$$

Using the law of total probability, we can express the denominator as

$$
\Pr{B}
= \Pr{B \cap A} + \Pr{B \cap A^c}
= \Pr{B | A} \Pr{A} + \Pr{B | A^c} \Pr{A^c}.
$$

Observing that $\Pr{A^c} = 1 - \Pr{A}$ and $\Pr{B | A} \le 1$ yields the desired result:

$$
\begin{align}
\Pr{A | B}
&= \frac{\Pr{B | A} \Pr{A}}{\Pr{B | A} \Pr{A} + \Pr{B | A^c} \Pr{A^c}} \\
&\ge \frac{\Pr{B | A} \Pr{A}}{\Pr{B | A} \Pr{A} + \Pr{A^c}} \\
&= \frac{\Pr{B | A} \Pr{A}}{\Pr{B | A} \Pr{A} + 1 - \Pr{A}} \\
&= \frac{\Pr{B | A} \Pr{A}}{1 - \Pr{A} (1 - \Pr{B | A})}.
\end{align}
$$

#### Corollary 1.1. Lower Bound on _A Posteriori_ Probabilities Given an Observation

Let $\{ x_1, \ldots, x_n \}$ be the possible outcomes for a random variable $X$ and $d$ be
the value of an observation. If the likelihood function $\L{x}{d}$ is known at $x = x_i$,
then

$$
\P{x_i | d}
\ge \frac{\L{x_i}{d} \P{x_i}}{1 - \P{x_i} (1 - \L{x_i}{d})}
$$

_Proof_. The bound follows by taking $A$ and $B$ in the Lemma to be the events $X = x_i$
and $O = d$, respectively, and recalling the relationship between the probabilities and
likelihoods: $\Pr{O = d | X = x_i} = \P{d | x_i} = \L{x_i}{d}.$

### Proposition 2. Lower Bound on _A Posteriori_ Probabilities Given A Set of Observations

Let $\{ x_1, \ldots, x_n \}$ be the possible outcomes for a random variable $X$ and $S$
be a set of observations that is conditionally independent given $x_i$ for some $i$.
Suppose that $T = \{d_1, \ldots, d_k \} \subset S$. If $d^\star$ is an observation not in
$T$ and the likelihood function $\L{x}{d}$ is known at $x = x_i$ for all $d \in S$, then

$$
\P{x_i | d_1, \ldots, d_k, d^\star}
\ge \frac{\L{x_i}{d^\star} \P{x_i | d_1, \ldots, d_k}}
         {1 - \P{x_i | d_1, \ldots, d_k} (1 - \L{x_i}{d^\star})}.
$$

_Proof_. By the definition of conditional probability

$$
\P{x_i | d_1, \ldots, d_k, d^\star}
= \frac{\P{x_i, d_1, \ldots, d_k, d^\star}}{\P{d_1, \ldots, d_k, d^\star}}.
$$

We can express the numerator in terms of conditional probabilities:

$$
\begin{align}
\P{x_i, d_1, \ldots, d_k, d^\star}
&= \P{d^\star | x_i, d_1, \ldots, d_k} \P{x_i, d_1, \ldots, d_k} \\
&= \P{d^\star | x_i, d_1, \ldots, d_k} \P{x_i | d_1, \ldots, d_k}
   \P{d_1, \ldots, d_k} \\
&= \P{d^\star | x_i} \P{x_i | d_1, \ldots, d_k} \P{d_1, \ldots, d_k} \\
&= \L{x_i}{d_k} \P{x_i | d_1, \ldots, d_k} \P{d_1, \ldots, d_k},
\end{align}
$$

where the second to last equality follows from the conditional independence of the
observations given $x_i$ and the last equality follows from the definition of the
likelihood function. We can express the denominator as a sum:

$$
\begin{align}
\P{d_1, \ldots, d_k, d^\star}
&= \sum_{j=1}^n \P{d_1, \ldots, d_k, d^\star | x_j} \P{x_j} \\
&= \sum_{j=1}^n \P{d^\star | x_j} \P{ d_1, \ldots, d_k | x_j} \P{x_j} \\
&= \sum_{j=1}^n \P{d^\star | x_j} \P{ x_j | d_1, \ldots, d_k} \P{d_1, \ldots, d_k} \\
&= \P{d_1, \ldots, d_k} \sum_{i=1}^n \P{d^\star | x_j} \P{ x_j | d_1, \ldots, d_k}.
\end{align}
$$

where the first equality follows from the law of total probability, the second equality
follows from conditional independence of the observations, and the third equality follows
from Bayes' theorem. The sum in last expression is bounded from above:

$$
\begin{align}
\sum_{j=1}^n \P{d^\star | x_j} \P{ x_j | d_1, \ldots, d_k}
&= \P{d^\star | x_i} \P{ x_j | d_1, \ldots, d_k}
   + \sum_{j=1, j \ne i}^n \P{d^\star | x_j} \P{ x_j | d_1, \ldots, d_k} \\
&\le \P{d^\star | x_i} \P{ x_j | d_1, \ldots, d_k}
    + \sum_{j=1, j \ne i}^n \P{ x_j | d_1, \ldots, d_k} \\
&= \P{d^\star | x_i} \P{ x_j | d_1, \ldots, d_k}
    + \left( 1 - \P{ x_i | d_1, \ldots, d_k} \right) \\
&= 1 - \P{ x_i | d_1, \ldots, d_k} ( 1 - \P{d^\star | x_i} ) \\
&= 1 - \P{ x_i | d_1, \ldots, d_k} ( 1 - \L{x_i}{d^\star} ),
\end{align}
$$

where the inequality follows because (conditional) probabilities are bounded by 1 and the
second equality follows because the conditional probabilities over mutually exclusive
events sum to 1.

Substituting these results into the expression for $\P{x_i | d_1, \ldots, d_k, d^\star}$
we obtain (after cancelling common factors)

$$
\begin{align}
\P{x_i | d_1, \ldots, d_k, d^\star}
&\ge \frac{\L{x_i}{d^\star} \P{x_i | d_1, \ldots, d_k}}
          {1 - \P{ x_i | d_1, \ldots, d_k} ( 1 - \L{x_i}{d^\star} )}.
\end{align}
$$

_Alternate Proof_. Consider the restricted the probability space constructed as the space
of random variables satisfying $O_i = d_i$ for $1 \le i \le k$. Let $P_R(x)$ and $L_R(x|d)$
denote the probability of $x$ and the likelihood of $x$ given $d$ in the restricted
probability space. Then $P_R(x_i) = \P{x_i | d_1, \ldots, d_k}$ and

$$
L_R(x_i | d^\star)
= P_R(d^\star | x_i)
= \P{d^\star | x_i, d_1, \ldots, d_k}
= \P{d^\star | x_i}
= \L{x_i}{d^\star}.
$$

Taking $d = d^\star$, Corollary 1.1 implies that

$$
\begin{align}
P_R(x_i | d^\star)
&\ge \frac{ L_R(x_i | d^\star) P_R(x_i) }
         { 1 - P_R(x_i) (1 - L_R(x_i | d^\star)) } \\
&= \frac{ \L{x_i}{d^\star} \P{x_i | d_1, \ldots, d_k} }
        { 1 - \P{x_i | d_1, \ldots, d_k} (1 - \L{x_i}{d^\star}) }.
\end{align}
$$

#### Corollary 2.1. Lower Bound on _A Posteriori_ Probabilities Given A Sequence of Observations

Let $\{ x_1, \ldots, x_n \}$ be the possible outcomes for a random variable $X$ and 
$\{d_1, d_2, d_3, \ldots \}$ be a sequence of observations that are conditionally
independent given $x_i$ for some $i$. Then

$$
\P{x_i | d_1, \ldots, d_k}
\ge \frac{\L{x_i}{d_k} \P{x_i | d_1, \ldots, d_{k-1}}}
         {1 - \P{x_i | d_1, \ldots, d_{k-1}} (1 - \L{x_i}{d_k})}.
$$

_Proof_. The result follows by taking $S = \{ d_1, \ldots, d_{k-1} \}$ and $d^\star = d_k$
in the Proposition 2.

__Remarks__

* In the Bayesian interpretation, Corollary 2.1 provides a theoretical framework
for sequentially updating the degree of belief that a random variable $X$ will have an
outcome $x_i$.

* Defining $X$ to be an indicator function allows Corollary 2.1 to serve as a framework for
  multi-time point decision-making processes.

--------------------------------------------------------------------------------------------
## Application to Multi-Time Point Decision Making with Incomplete Predictive Model Coverage

For complex systems, it may not be possible to develop a complete set of predictive models
with _full coverage_ of all of the control and observable variables in a system. The
theoretical framework presented in the previous section provides a method for updating the
beliefs about the state of a system given predictive models that only partially cover the
variables that describe the system. Note that the framework is intended to augment (not
replace) previously developed models. In fact, the framework cannot function in the
_total absence_ of predictive models. Examples of predictive models that could be used
within the Bayesian inference framework include:

* physics-based simulations (that incorporate quantification of uncertainty in the input
  parameters) and

* machine learning models (where the output can be interpreted as "belief" strengths).

### Example

Suppose we collect data from system at multiple time points and have a predictive model
that uses the data to predict the outcome of the experiment. Given an outcome $x_i$ of
interest, assume the following:

* we have a lower bound on the probability of $x_i$ (given all previous data) at the
  beginning of each time point, 

* we can relate $x_i$ to the control parameters of the predictve model,

* the predictive model provides an estimate of the probability of observing particular
  data values from the experiment.

With these components, we can estimate a new lower bound on the probability of $x_i$ using
the following procedure:

* Compute the probability of the newly collected data assuming the outcome $x_i$. This
  quantity is the likelihood of $x_i$ given the data: $\P{d | x_i} = \L{x_i}{d}$.

* Update the lower bound on the probability of $x_i$ using the formula from Corollary 2.1.

#### Comments

* We only need _bounds_ on the probabilities of _only_ the outcomes that we are interested.
  We do not need the entire probability distribution over outcomes; nor do we need
  precise probability values.

* Any model that provides an estimate of the probability of the observations given the
  outcome $x_i$ can be used to update the bound on the probability of the outcome.

* The update formula in Corollary 2.1 provides updates that match our intuition.

  If we have a strong belief in the outcome $x_i$ (i.e.
  $\P{x_i | d_1, \ldots, d_k} \approx 1$ or $\P{x_i | d_1, \ldots, d_k} \ll 1$), then new
  data does not significantly affect our belief:

  * $\P{x_i | d_1, \ldots, d_k} \approx 1$
  
    $$
    \frac{\L{x_i}{d_k} \P{x_i | d_1, \ldots, d_{k-1}}}
         {1 - \P{x_i | d_1, \ldots, d_{k-1}} (1 - \L{x_i}{d_k})}
    \approx \frac{\L{x_i}{d_k}}{1 - (1 - \L{x_i}{d_k})}
    \approx 1
    $$

  * $\P{x_i | d_1, \ldots, d_k} \ll 1$
    
    $$
    \frac{\L{x_i}{d_k} \P{x_i | d_1, \ldots, d_{k-1}}}
         {1 - \P{x_i | d_1, \ldots, d_{k-1}} (1 - \L{x_i}{d_k})}
    \approx \L{x_i}{d_k} \P{x_i | d_1, \ldots, d_{k-1}}
    \ll 1
    $$

  * If we have a weak belief in the outcome $x_i$ (e.g.,
    $\P{x_i | d_1, \ldots, d_k} \approx 1/n$), then new data strongly affects our belief:

    TODO

--------------------------------------------------------------------------------------------
## Connections to Control Theory

--------------------------------------------------------------------------------------------
## References

1. [Wikipedia: Bayes' Theorem](https://en.wikipedia.org/wiki/Bayes%27_theorem)

2. [Wikipedia: Conditional independence](https://en.wikipedia.org/wiki/Conditional_independence)

3. [Wikipedia: Likelihood function](https://en.wikipedia.org/wiki/Likelihood_function)

4. R.F. Stengel. "Optimal Control And Estimation" (1994).

--------------------------------------------------------------------------------------------
