Randomized Algorithms Notes
===========================

*Author(s)*: Kevin Chu `<kevin@velexi.com>`

__Last Updated__: 2022-05-25

--------------------------------------------------------------------------------------------

References
----------
* R. Motwani and P. Raghavan. "Randomized Algorithms". (1995)

--------------------------------------------------------------------------------------------

## 1. Overview

### 1.1. Key Ideas

* Two main advantages of randomized algorithms: (1) performance and (2) simplicity.

* When analyzing randomized algorithms, we typically focus on the impact of random choices
  _made by the algorithm_ on the behavior of the algorithm.

  * In contrast, _probabilistic analysis of algorithms_ assumes a distribution on the
    inputs and analyzes the impact of randomness in the input on the behavior of the
    (possibly deterministic) algorithm.

* Two types of randomized algorithms

  * __Las Vegas__: guaranteed correct solution with randomness in the resource usage

  * __Monte Carlo__: fixed resource usage with a probability of error in the solution

* Two main types of bounds

  * bounds on expectation values

  * bounds on probability of specific events (e.g., successful computation of solution)

### 1.2. Additional Consideration

* Randomness is a resource with cost

  * generation of random bits

  * computational overhead of sampling from a particular distribution

### TODO: Organize

#### Basic Tools and Techniques

* If an algorithm has probability $p$ of success, use repeated execution of the algorithm
  to increase the probability of success.

  * If the algorithm is repeated $N = K/p$ times, the probability of failure is bounded
    above by $e^{-K}$:

    \[ 
    P(\textrm{failure})
    = (1 - p)^N
    \le \left( e^{-p} \right)^N
    = \left( e^{-p} \right)^{K/p}
    = e^{-K}.
    \] 

    The probability of success is bounded below by $1 - e^{-K}$.

  * The expected number of repetitions required to achieve success is proportional to $1/p$.

* Union bound

* Decomposition of intesection of events as a product of conditional probabilities.

* Linearity of expectation

  * For counting, use an appropriately chosen indicator function

* Minimax Principle
  * general technique for proving lower bounds on running times of randomized algorithms

--------------------------------------------------------------------------------------------

## Appendix A. Useful Probabilty Results

* Linearity of Expectation
  * Important observation: holds regardless of dependencies between random variables

* Union Bound

--------------------------------------------------------------------------------------------
