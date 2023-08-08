Stochastic Processes: Markov Chains
===================================

_Author(s)_: Kevin Chu `<kevin@velexi.com>`

_Last Updated_: 2023-08-07

--------------------------------------------------------------------------------------------

Table of Contents
-----------------

1. [Definitions][#1]

2. [Analysis of Markov Chains][#2]

3. [Long Run Behavior][#3]

4. [Classification of States][#4]

5. [Illustrative Examples of Markov Chains][#5]

6. [Additional Notes][#6]

--------------------------------------------------------------------------------------------

References
----------

* H.M. Taylor and S. Karlin. "An Introduction to Stochastic Modeling" (1998).

* S.M. Ross. "Stochastic Processes" (1996).

--------------------------------------------------------------------------------------------

## 0. Notation

* $\newcommand{\Pr}[1]{{\mathbb{P}\left[{#1}\right]}}$
  Probability of event $E$: $\Pr{E}$

* $\newcommand{\1}[1]{{\mathbf{1}_{\left\{{#1}\right\}}}}$
  Indicator for event $E$: $\1{E}$

--------------------------------------------------------------------------------------------

## 1. Definitions

* A _Markov chain_ $X_i$ a sequence of random variables with the property that the
  distribution $X_{n+1}$ depends only on the value of $X_n$ and is independent of all
  earlier values of $X_j$ (and all later values of $X_j$):

  $$
  \Pr{X_{n+1} = j | X_0 = i_0, X_1 = i_1, \ldots, X_n = i}
  = \Pr{X_{n+1} = j | X_n = i}
  $$

* The _transition probabilities_ $P^{n,n+1}_{ij} = \Pr{X_{n+1} = j | X_n = i}$ define the
  conditional probability that the Markov chain transitions to the state $X_{n+1} = j$
  given that it is in the state $X_n = i$.

* The transition probabilities $P^{n,n+1}_{ij}$ can be organized into a
 _transition probability matrix_ (or Markov matrix):

  $$
  \newcommand{\P}{\mathbf{P}}
  $$

  $$
  \P^{n,n+1} = \left[\begin{array}{cccc}
  P^{n,n+1}_{00} & P^{n,n+1}_{01} & \cdots & P^{n,n+1}_{0m} \\
  P^{n,n+1}_{10} & P^{n,n+1}_{11} & \cdots & P^{n,n+1}_{1m} \\
  \vdots
  P^{n,n+1}_{m0} & P^{n,n+1}_{m1} & \cdots & P^{n,n+1}_{mm} \\
  \end{array}\right]
  $$

  When the transition probability matrix does not depened on the (time) index, we can drop
  the superscript:

  $$
  \P^{n,n+1} = \P.
  $$


* The transition probability matrix from the initial state to (time) index $n$ is denoted
  by $\P^{(n)}$.

--------------------------------------------------------------------------------------------

## 2. Analysis of Markov Chains

### 2.1. Multi-step Transition Probabilities

The transition probability matrix from time $0$ to time $n$ can be expressed as a
product of transition probability matrices at times $0$ to $n$:

$$
\P^{(n)} = \prod_{k=0}^n \P^{k,k+1}
$$

When the transition probability matrix does not depened on the time, we can drop the
superscript:

$$
\P^{(n)} = \P^n.
$$

### 2.2. First Step Analysis

First step analysis is a useful technique for analyzing many functionals on Markov
chains. The basic procedure is as follows.

* Calculate the value of the functional for each possible transition.

* Use the law of total probability to express the functional before transition in terms
  of the transition probabilities and the values of the functional after transition.

* Invoke the Markov property to express the values of functional after transition in
  terms of the functional before transition.

* Derive the system of equations for the values of the functional.

_Example_

TODO

--------------------------------------------------------------------------------------------

## 3. Long Run Behavior

### 3.1. Definitions

* A Markov chain (or its transition probability matrix) is _regular_ if all of the elements
  of $\P^k$ are strictly positive for some power $k$.

### 3.2. Key Results

* (Lemma) If $P^k$ has no zero elements, then $P^l$ has no zero elements for all $l \ge k$.

* (Lemma) A transition probability matrix $\P$ on $N$ states is regular if and only if
  $\P^{N^2}$ has no zero elements.

* (Theorem) If a Markov chain is regular, it has a _limiting probability distribution_ that
  is independent of the iniital state $X_0$:

  $$
  \lim_{n \rightarrow \infty} \Pr{X_n = j | X_0 = i} = \pi_j > 0
  $$

  for $j = 0, 1, \ldots, N$. In terms of the transition probability matrix,

  $$
  \lim_{n \rightarrow \infty} P^{(n)}_{ij} = \pi_j > 0
  $$

  for $j = 0, 1, \ldots, N$. The limiting distribution

  $$
  \pi = [\pi_0, \pi_1, \ldots, \pi_N]
  $$

  satisfies the constraint $\sum_j \pi_j = 1$.

* (Theorem) Let $\P$ be a regular transition probability matrix on the states
  $0, 1, \ldots, N$. Then the limiting distribution $\pi = [\pi_0, \pi_1, \ldots, \pi_N]$
  is the unique nonnegative solution of the equations

  $$
  \begin{align}
  \pi \P &= \pi \\
  \pi [1, 1, \ldots, 1]^T &= 1 \\
  \end{align}
  $$

  _Proof_. Since $\P$ is regular, $\lim_{n \rightarrow \infty} P^{(n)}_{ij} = \pi_j$ for
  $j = 0, 1, \ldots, N$ with $\sum_j \pi_j = 1$. Expressing $\P^{(n)}$ as a product of
  $\P$ and $\P^{(n-1)}$ and taking the limit as $n \rightarrow \infty$ yields

  $$
  \left[\begin{array}{c}
    \pi \\
    \pi \\
    \vdots \\
    \pi \\
  \end{array}\right]
  = \left[\begin{array}{c}
      \pi \\
      \pi \\
      \vdots \\
      \pi \\
    \end{array}\right]
    \P.
  $$

  All of the rows of this equation are identical: $\pi = \pi \P$. The row equations
  combined with the normalization condition for probability distributions show that the
  limiting distribution satisifes the specified equations.

  To show that this solution is unique, suppose that $\mathbf{x} = [x_0, x_1, \ldots, x_N]$
  is a solution to the equations. Then

  $$
  \begin{align}
  \mathbf{x} \P &= \mathbf{x} \\
  \mathbf{x} [1, 1, \ldots, 1]^T &= 1 \\
  \end{align}
  $$

  Repeatedly multiplying the first equation on the right by $\P$, using the fact that
  $\mathbf{x} \P = \mathbf{x}$, and taking the limit as $n \rightarrow \infty$ (which is
  permitted because $\P^{(n)}$ converges) shows that $\mathbf{x}$ satisfies

  $$
  \mathbf{x} \left[\begin{array}{c}
    \pi \\
    \pi \\
    \vdots \\
    \pi \\
  \end{array}\right]
  = \mathbf{x}.
  $$

  Observe that

  $$
  \mathbf{x} \left[\begin{array}{c}
    \pi \\
    \pi \\
    \vdots \\
    \pi \\
  \end{array}\right]
  = \mathbf{x} \left(\left[\begin{array}{c}
    1 \\
    1 \\
    \vdots \\
    1 \\
  \end{array}\right] \pi \right)
  = \left( \mathbf{x} \left[\begin{array}{c}
    1 \\
    1 \\
    \vdots \\
    1 \\
  \end{array}\right]\right) \pi
  = \pi
  $$

  where the last equality follows because $\mathbf{x} [1, 1, \ldots, 1]^T = 1$. Therefore,
  $\mathbf{x} = \pi$, which implies that the limiting distribution $\pi$ is the unique
  solution to the specified equations.

* __Intepretations of the Limiting Distribution__

  * After the process has been running for a long time, $\pi_j$ is the probability of
    finding the process in state $j$ regardless of process's initial state.

  * After the process has been running for a long time, $\pi_j$ is the average time that
    the process spends in state $j$ regardless of process's initial state.

    _Proof_. TODO. Relies on the fact that for sequences $(a_k)$ that converge

    $$
    \lim_{m \rightarrow \infty} \frac{1}{m} \sum_{k=1}^m a_k = a.
    $$

### 3.3. Additional Notes

* To determine if a Markov chain is regular, it suffices to check whether successive
  squares of $\P$ have zero elements: $\P^2, \P^4, \P^8, \ldots$. Moreever, since the
  elements of $\P$ are strictly nonnegative, it suffices to track whether elements are
  zero or nonzero -- it is unncessary to determine the numerical values of the matrix
  elements.

--------------------------------------------------------------------------------------------

## 4. Classification of States

* TODO

--------------------------------------------------------------------------------------------

## 5. Illustrative Examples of Markov Chains

### 5.1. Applications of Markov Chain Models

* __Two-State Markov Chain__

  * TODO

* __General Absorbing Chain__

  * TODO

* __Markov Chains Defined By Independent Random Variables__

  * TODO

* __One-Dimensional Random Walks__

  * TODO

* __Success Runs__

  * TODO

* __Branching Processes__

  * TODO

### 5.2. Applications of Long Run Behavior

* __Including History in the State Description__

  * TODO

* __Reliability and Redundancy__

  * TODO

* __Continuous Sampling Plan__

  * TODO

* __Age Replacement Policies__

  * TODO

* __Optimal Replacement Rules__

  * TODO

--------------------------------------------------------------------------------------------

## 6. Additional Notes

* __Doubly Stochastic Matrices__. A transition probability matrix is _doubly stochastic_
  if all of its columns sum to 1.

  * (Lemma) If a transition probability matrix $\P$ on $N$ states is doubly stochastic,
    then its limiting distribution is $\pi = [1/N, 1/N, \ldots, 1/N]$.

    _Proof_. It is straightforward to verify that $\pi = [1/N, 1/N, \ldots, 1/N]$ satisfies
    the equations for the limiting distribution:

    $$
    \begin{align}
    [1/N, 1/N, \ldots, 1/N] \P
    &= \frac{1}{N} [1, 1, \ldots 1] P \\
    &= \frac{1}{N} \left[ \sum_i P_{i1}, \sum_i P_{i2}, \ldots \sum_i P_{iN}, \right] \\
    &= \frac{1}{N} [1, 1, \ldots 1] \\
    &= [1/N, 1/N, \ldots, 1/N].
    \end{align}
    $$

    and $\sum_{j=1}^N 1/N = 1$. Since the limiting distribution is unique,
    $\pi = [1/N, 1/N, \ldots, 1/N]$ is the limiting distribution of $\P$.

--------------------------------------------------------------------------------------------

[----------------------------------- INTERNAL LINKS -----------------------------------]: #

[#0]: #references
[#1]: #1-definitions
[#2]: #2-analysis-of-markov-chains
[#3]: #3-long-run-behavior
[#4]: #4-classification-of-states
[#5]: #5-illustrative-examples-of-markov-chains
[#6]: #6-additional-notes

[----------------------------------- EXTERNAL LINKS -----------------------------------]: #
