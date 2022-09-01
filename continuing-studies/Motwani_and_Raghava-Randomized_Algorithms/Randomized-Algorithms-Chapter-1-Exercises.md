Randomized Algorithms (R. Motwani & P. Raghavan): Chapter 1 Exercises
=====================================================================

--------------------------------------------------------------------------------------------
### Exercise 1.1.

__Problem__. Consider the (random) permutation $\pi$ of $S$ induced by the level-order
traversal of the tree $T$ corresponding to an execution of __RandQS__. Is $\pi$
_uniformly_ distributed over the space of all permutations of the elements
$S_{(1)}, \ldots, S_{(n)}$?

__Solution__. Yes. TODO

--------------------------------------------------------------------------------------------
### Exercise 1.2.

__Problem__. Suppose that at each step of our min-cut algorithm, instead of choosing a
random edge for contraction we choose two vertices at random and coalesce them into a
single vertex. Show that there are inputs on which the probability that this modified
algorithm finds a min-cut is exponentially small.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### Exercise 1.3.

__Problem__. Consider a Monte Carlo algorithm $A$ for a problem $\Pi$ whose expected
running time is at most $T(n)$ on an any instance of size $n$ and that produces a correct
solution with probability $\gamma(n)$. Suppose further that given a solution to $\Pi$, we
can verify its correctness in time $t(n)$. Show how to obtain a Las Vegas algorithm that
always gives a correct answer to $\Pi$ and runs in expected time at most
$(T(n) + t(n)) / \gamma(n)$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### Exercise 1.4.

__Problem__. Let $0 < \epsilon_2 < \epsilon_1 < 1$. Consider a Monte Carlo algorithm that
gives the correct solution to a problem with probability at least $1 - \epsilon_1$
regardless of the input. How many independent executions of this algorithm suffice to raise
the probability of obtaining a correct solution to at least $1 - \epsilon_2$, regardless
of the input?

__Solution__. TODO

--------------------------------------------------------------------------------------------
### Exercise 1.5.

__Problem__. Show that there exists a set of line segments for which no binary planar
partition can avoid breaking up some of the segments into pieces, if each segment is to lie
in a different region of the partition.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### Exercise 1.6.

__Problem__. If $X$ were to range over all integers having value at most $m-1$ (possibly
including negative integrers), how would the statement and proof of the Theorem 1.3 change?

__Solution__. TODO

--------------------------------------------------------------------------------------------
### Exercise 1.7.

__Problem__. What prevents us from using Theorem 1.3 to bound the expected number of levels
of recursion in the __RandQS__ algorithm?

__Solution__. TODO

--------------------------------------------------------------------------------------------
