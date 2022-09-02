Mathematics (2020)
==================

*Author(s)*: Kevin Chu `<kevin@velexi.com>`

-------------------------------------------------------------------------------

2020-12-06: Notes on Gaussian Random Processes
----------------------------------------------

* Gaussian random processes are generalization of multivariate Gaussian random
  variables.

* Gaussian random processes are defined by two functions:

  * mean function $\mu(x)$

  * covariance function $K(x, x')$

* A linear transformations on a Gaussian random processes is defined by a set
  of linear functionals of functions on the domain of the Gaussian random
  processes:

  $$
    \int f_i(x) g(x) dx,
  $$

  where $g(x)$ is a sample drawn from the Gaussian random process and $f_i(x)$
  is an element of the dual of the vector space of the integrable functions on
  $x$.

* Let $\mathbf{f(g)}$ be the vector with components equal to
  $\int f_i(x) g(x) dx$. Then

  $$
    E[\mathbf{f}_i] = \int f_i(x) \mu(x) dx \\
    Cov[\mathbf{f}_i, \mathbf{f}_j] = \int f_i(x) K(x, x') f_j(x') dx dx'
  $$

* The "standard" basis for the space of functions of $x$ is

  $$
    f_{x'}(x) = \delta_{x, x'} =
      \left\{
        \begin{array}{cc}
          1 & x = x' \\
          0 & x \ne x'
        \end{array}
      \right.
  $$

-------------------------------------------------------------------------------

2020-11-20: Rank of Matrix With Elements of the Form $\alpha^T \beta$
---------------------------------------------------------------------

### Result

If $X$ is an $M \times N$ matrix with elements that are inner products of
vectors in $\mathbb{R}^r$, then the rank of $X$ is less than or equal to $r$.

### Proof

Let $X_{mn} = \alpha_m^T \beta_n$. Then $X$ can be expressed in terms of the
standard bases for $\mathbb{R}^M$ and $\mathbb{R}^N$:

$$
  X = \sum_{m = 1}^M \sum_{n = 1}^N \left( \alpha_m^T \beta_n \right) e_m e^T_n
$$

Expressing the inner product as a sum,

$$
  X
  = \sum_{m = 1}^M \sum_{n = 1}^N
    \sum_{i = 1}^r \alpha_{mi} \beta_{ni} e_m e^T_n.
$$

Reordering the sums and factoring the product yields

$$
  X
  = \sum_{i = 1}^r
    \sum_{m = 1}^M \sum_{n = 1}^N \alpha_{mi} \beta_{ni} e_m e^T_n \\
  = \sum_{i = 1}^r
    \left( \sum_{m = 1}^M \alpha_{mi} e_m \right)
    \left( \sum_{n = 1}^N \beta_{ni} e_n^T \right)
  = \sum_{i = 1}^r
    \left( \sum_{m = 1}^M \alpha_{mi} e_m \right)
    \left( \sum_{n = 1}^N \beta_{ni} e_n \right)^T,
$$

which is the sum of $r$ outer products of vectors in $\mathbb{R}^M$ and
$\mathbb{R}^N$. Therefore, $X$ is at most rank $r$.

-------------------------------------------------------------------------------

2020-11-20: Bound on Tail Sum $\sum_{k = M}^\infty \frac{1}{k!}$
----------------------------------------------------------------

### Result

$$
  \sum_{k = M}^\infty \frac{1}{k!} \le \frac{2}{M!}
$$

### Proof

$$
\sum_{k = M}^\infty \frac{1}{k!}
= \frac{1}{M!} \sum_{k = M}^\infty \frac{M!}{k!}
= \frac{1}{M!} \sum_{k = M}^\infty \frac{1}{(M + 1) (M + 2) \cdots (k - 1) k}
$$

All of the factors in the denominator of each term are greater than $M$ and the
number of factors is equal to $k - M$, so

$$
\sum_{k = M}^\infty \frac{1}{(M + 1) (M + 2) \cdots (k - 1) k}
\le \sum_{k = M}^\infty \frac{1}{M^{(k - M)}}
= \sum_{i = 0}^\infty \frac{1}{M^i}
= \frac{M}{M-1}
\le 2
$$

for $M \ge 2$. The result follows.

-------------------------------------------------------------------------------

2020-06-25: Maximum-Term Method for Computing Infinite Series
-------------------------------------------------------------

### Summary

* The _maximum-term method_ is used to compute (or bound) the value of
  infinite series when the terms in the series are (1) positive and
  (2) the maximum value of first $n$ terms is asymptotically superpolynomial
  function of $n$ (e.g., exponential).

* __Application to statistical thermodynamics__. This method is useful for
  computing the value of macroscopic variables in the thermodynamic limit.

### Discussion

Let $X = (x_1, x_2, x_3, \ldots)$ be a sequence of positive elements where
$\max_{i \le n} x_i$ is asymptotically a superpolynomial function of $n$.
Consider the partial sums of $X$:

$$
  S_n = \sum_{i=1}^n x_i.
$$

Letting $f(n) = \max_{i \le n} x_i$,

$$
  f(n) \le S_n \le n f(n)
$$

so that

$$
  \ln f(n) \le \ln S_n \le \ln f(n) + \ln n.
$$

Since $f(n)$ is asymptotically superpolynomial, then $\ln n = o(\ln f(n))$, so

$$
  \ln f(n) + \ln n = \ln f(n) \left( 1 + \frac{\ln n}{\ln f(n)} \right)
  \rightarrow \ln f(n)
$$

as $n \rightarrow \infty$. Therefore,

$$
  \lim_{n \rightarrow \infty} \ln S_n = \ln f(n) = \ln \max_{i \le n} x_i
$$

by the squeeze theorem.

__Corollary__. Since the exponential function is continuous everywhere on the
real line,

$$
  \lim_{n \rightarrow \infty} S_n = f(n) = \max_{i \le n} x_i.
$$


### References

* D. A. McQuarrie. "Statistical Thermodynamics" (1973).

-------------------------------------------------------------------------------

2020-06-22: Common Useful Inequalities
--------------------------------------

_Last Updated_: 2020-06-23

### Bernoulli's Inequality

Let $x > -1$.

* If $r > 1$ or $r < 0$, then

  $$
    (1 + x)^r \ge 1 + rx.
  $$

* If $0 \le r \le 1$, then

  $$
    (1 + x)^r \le 1 + rx.
  $$

* If $r = 0$ or $r = 1$, then

  $$
    (1 + x)^r = 1 + rx.
  $$

__Proof__

Consider the function $f(x) = (1 + x)^r - (1 + rx)$. Its first and second
derivatives of are $f'(x) = r ((1 + x)^{r - 1} - 1)$ and
$f''(x) = r (r - 1) (1 + x)^{r - 2}$, respectively. Observe that $f(0) = 0$
and $f'(0) = 0$.

When $r > 1$ or $r < 0$, $f''(x) \ge 0$ for $x > -1$, so $f(x)$ achieves a
minimum value of 0 (at $x = 0$) in the region $x > -1$. Therefore,
$(1 + x)^r \ge 1 + rx$.

When $0 < r < 1$, $f''(x) > 0$ for $x > -1$, so $f(x)$ achieves a maximum value
of 0 (at $x = 0$) in the region $x > -1$. Therefore, $(1 + x)^r \le 1 + rx$.

For $r = 0$ and $r = 1$, $f(x)$ is identically 0, so the inequality is an
equality: $(1 + x)^r = 1 + rx$.

### Geometric Series Bound

$$
  (1 - r)^{-1} \le 1 + 2r
$$

__Proof__

When $r \le 1/2$, then $r/(1 - r) \le 1$. Therefore

$$
  (1 - r)^{-1} = 1 + r + \sum_{i = 2}^\infty r^i
= 1 + r + \frac{r^2}{1 - r} \le 1 + 2r
$$

-------------------------------------------------------------------------------
