---
tags: algorithms, stochastic-models
---

--------------------------------------------------------------------------------------------

2022-08-31: Random Walk Models for Iterative Probabilistic Algorithms
---------------------------------------------------------------------

_Author(s)_: Kevin Chu `<kevin@velexi.com>`

_Last Updated_: 2022-09-07

--------------------------------------------------------------------------------------------
### Summary

For a two-state random walk model, the time that the spent in each state is proportional to
the probability of transitioning into that state from the other state. In the context of
iterative probabilistic algorithms, this observation implies that an algorithm that has a
high probabilty of remaining in one state once it arrives in that state will spend most of
its time in that state as long as the probability of transitioning into that state isn't
too low.

--------------------------------------------------------------------------------------------
### Observations

* For iterative algorithms where the behavior at each iteration is non-deterministic, a
  random walk perspective may be useful for analyzing the behavior of the algorithm.

  * Note that this approach is useful for both analysis of randomized algorithms and
    probabilistic analysis of deterministic algorithms where the origin of the randomness
    is external to the algorithm.

* Markov chain models are useful for modeling the random walk on states.

--------------------------------------------------------------------------------------------
### Notation

* $P_{i,j} = \Pr{\textrm{next state is } j | \textrm{current state is } i}$

  * _Note_. Following the convention used for Markov chain models, we represent probability
    distributions as row vectors, this choice of notation implies that the probability
    distribution at the next time step is computed by multiplying the current probability
    distribution (row vector) by the transition matrix _on the right_.

--------------------------------------------------------------------------------------------
### Two-State Model

* __Model__. There are two states $A$ and $B$ with transition matrix is given by

  $$
  P = \left[ \begin{array}{cc}
        1 - P_{A,B} & P_{A,B} \\
        \varepsilon & 1 - \varepsilon
      \end{array} \right]
  $$

  where the state $B$ transitions to itself with high probability (and, therefore, to
  state $A$ with low probability). Mathematically, $0 < \varepsilon \ll 1$.

* __Assumptions__

  * There is a nonzero probability of transitioning from $A$ to $B$: $P_{A,B} > 0$.

* __Analysis__. In the long-time limit, the relative time spent in each state tends towards
  the stationary distribution for the Markov chain model with transition matrix $P$. For
  two-state models with transition matrix

  $$
  \left[ \begin{array}{cc}
    1 - a & a \\
    b     & 1 - b
  \end{array} \right],
  $$

  it is well-known that the stationary distribution is given by [1]:

  $$
  \left(
  \frac{b}{a+b}, \frac{a}{a+b}
  \right).
  $$

  Applying this result to the two-state model for a sequence of non-deterministic
  iterations of an algorithm, the relative time spent in states $A$ and $B$ are

  $$
  \begin{align}
    \textrm{fraction of time spent in state $A$} &=
      \frac{\varepsilon}{P_{A,B} + \varepsilon} \\
    \textrm{fraction of time spent in state $B$} &= \frac{P_{A,B}}{P_{A,B} + \varepsilon}
  \end{align},
  $$

  which tend towards $1$ and $0$ as $\varepsilon \rightarrow 0$. More precisely,

  $$
  \begin{align}
    \textrm{fraction of time spent in state $A$} &\approx
      \frac{\varepsilon}{P_{A,B}} \left( 1 - \frac{\varepsilon}{P_{A,B}} \right) \\
    \textrm{fraction of time spent in state $B$} &\approx 1 - \frac{\varepsilon}{P_{A,B}}
  \end{align}
  $$

  assuming that there is a non-neglible probability of transitioning from $A$ to $B$
  (or more precisely, $\varepsilon \ll P_{A,B}$).

--------------------------------------------------------------------------------------------
### Random Walk Model

* __Model__. There is a starting state $0$ and a chain of states $1, \ldots, n$. The
  only allowed transitions are between neighboring states, which implies that the
  transition matrix is tridiaonal:

  $$
  P = \left[ \begin{array}{cccccc}
        r_0    & p_0    & 0      & 0       & \cdots  & 0 \\
        q_1    & r_1    & p_1    & 0       & \cdots  & 0 \\
        \vdots & \ddots & \ddots & \ddots  & \vdots  & \vdots \\
        0      & 0      & 0      & q_{n-1} & r_{n-1} & p_{n-1} \\
        0      & 0      & 0      & 0       & q_n     & r_n
      \end{array} \right]
  $$

  where

  $$
  \begin{align}
  q_i &= P_{i,i-1} \\
  r_i &= P_{i,i} \\
  p_i &= P_{i,i+1}
  \end{align}
  $$

* __Assumptions__

  * For $1 \le i \le n-1$, $q_i \ll r_i + p_i$.

  * $q_n \ll r_n$

* __Questions__

  * If the algorithm starts in the state 1. What is the probability that the algorithm
    reaches state $n$ before reaching state 0?

  * If the algorithm starts in state $n$, what is the expected time that it takes for the
    algorithm to reach state 0?

--------------------------------------------------------------------------------------------
### References

1. Taylor H.M. and Karlin S. "An Introduction to Stochastic Modeling" (1998).

--------------------------------------------------------------------------------------------
