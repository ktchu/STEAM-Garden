Mathematics (2022)
==================

*Author(s)*: Kevin Chu `<kevin@velexi.com>`

--------------------------------------------------------------------------------------------

## Notation

* $\newcommand{\R}[0]{\mathbb{R}}$
  The set of real numbers: $\R$

* $\newcommand{\Z}[0]{\mathbb{Z}}$
  The set of integers: $\Z$

--------------------------------------------------------------------------------------------

## 2022-08-30: Inequalities - $(1+x)(1-y) \ge 1$

* Let $0 \le x, y \le 1$. Then $(1 + x) (1 - y) \ge 1$ if and only if $x \ge y / (1 - y)$.

  _Proof_.

  $$
  (1 + x) (1 - y) \ge 1
  \Leftrightarrow x (1 - y) \ge y
  \Leftrightarrow x \ge \frac{y}{1 - y}
  $$

  __Corollary__.  $(1 + x) (1 - y) \ge 1$ if and only if $y \le x / (1 + x)$.

--------------------------------------------------------------------------------------------

## 2022-07-23: Miscellaneous Identities and Bounds

* $a^{b \ln c} = c^{b \ln a}$

  _Proof_. Note that $x = e^{\ln x}$ for all $x > 0$. Therefore,

  $$
  a^{b \ln c}
  = \left( e^{\ln a} \right)^{b \ln c}
  = e^{\ln a (b \ln c)}
  = e^{\ln c (b \ln a)}
  = \left( e^{\ln c} \right)^{b \ln a}
  = c^{b \ln a}
  $$

* $x \ln x - x \ge -1$ for $x > 0$

  _Proof_. Let $f(x) = x \ln x - x$. Then $f'(x) = \ln x$ and $f''(x) = 1/x$. For $x > 0$,
  $f''(x) > 0$, so $f$ is convex. $f'(x) = 0$ at $x = 1$, so the minimum of $f$ is $-1$.

* For all positive integers $n$, $x \ge (\ln x)^n$ for sufficienty large $x$.

  _Proof_. Consider the ratio $\frac{(\ln x)^n}{x}$. By L'Hopital's,

  $$
  \lim_{x \rightarrow \infty} \frac{(\ln x)^n}{x}
  = \lim_{x \rightarrow \infty} \frac{n (\ln x)^{n-1}}{x}
  = \cdots
  = \lim_{x \rightarrow \infty} \frac{n (n-1) \cdots (2) (\ln x)}{x}
  = \lim_{x \rightarrow \infty} \frac{n!}{x}
  = 0.
  $$

  Therefore, by the definition of the limit, there exists $x_0$ such that

  $$
  \frac{(\ln x)^n}{x} \le 1
  $$

  for $x \ge x_0$. Rearranging this bound yields the desired inequality.

  __Remarks__

  * The value of $x_0$ required for the inequality to hold grows large very quickly as a
    function of $n$.

  * For $n = 2$, the inequality holds for $x_0 = 1$.

    _Proof_. Consider the function $f(x) = x - (\ln x)^2$. The derivatives of $f$ are

    $$
    \begin{align}
    f'(x) &= 1 - \frac{2 \ln x}{x} \\
    f''(x) &= \frac{2 (\ln x - 1)}{x^2} \\
    f^{(3)}(x) &= \frac{6 - 4 \ln x}{x^3}.
    \end{align}
    $$

    Observe that $f'(e)$ is a global minimum for $f'$ because $f''(x)$ has a single zero at
    $x = e$ and $f^{(3)}(e) > 0$. Therefore, $f'(x) > 0$ for all $x$ (because
    $f'(e) = 1 - 2/e > 0$), so we can conclude that $f(x) > 0$ for $x > 1$ because
    $f(1) = 1$ and $f(x) = f(1) + \int_1^x f'(x) dx$.

--------------------------------------------------------------------------------------------

## 2022-07-10: References for Laplace's Method and Watson's Lemma

### References

* "The method of Laplace and Watson's lemma", _J. Concrete and Applicable Math_. 10 (2012).
  [(PDF)](https://www.researchgate.net/publication/267127890_The_method_of_Laplace_and_Watson%27s_lemma)

* [Approximating integrals with Laplace's method](https://francisbach.com/laplace-method/)

--------------------------------------------------------------------------------------------

## 2022-07-05: Bounds for $e^x$

### Linear Function Bounds for $e^x$

* For $0 \le x \le 1$, $e^x \le 1 + 2 x$.

  _Proof_. Let $f(x) = e^x - (1 + 2x)$. Observe that $f(0) = 0$, $f'(0) = -1 < 0$, and
  $f(x) \rightarrow \infty$ as $x \rightarrow \infty$, which implies that $f(x) \le 0$ for
  $0 \le x \le x^*$, where $x^*$ fixed value of $x$. Since $f'(x) = e^x - 2$ and
  $f''(x) = e^x$, the slope of $f$ strictly increases as $x$ increases. Therefore,
  $f'(x) = 0$ at only a single value of $x = \ln 2 > 0$, which implies that $f(x) = 0$ for
  only one positive value of $x$ (otherwise, the mean-value theorem would imply that there
  are multiple values of $x > 0$ with $f'(x) = 0$). Noting that $f(1) < 0$ (because
  $e < 3 = 1 + 2 \cdot 1$), we can conclude that $f(x) \le 0$ for $0 \le x \le 1$, which is
  equivalent to the desired result.

  __Corollary__. For $-1 \le x \le 0$, $e^{-x} \le 1 - 2 x$.

  * _Proof_. Let $y = -x$ so that $0 \le y \le 1$. The result follows from the inequality
    $e^{-x} = e^y \le 1 + 2 y = 1 - 2 x$.

* Let $0 \le \delta \le 1$. Then

  $$
  e^x \le 1 + (1 + \delta) x
  $$

  for $0 \le x \le \delta/2$.

  _Proof_. Define $f(x) = 1 + (1 + \delta) x - e^x$. Then $f'(x) = (1 + \delta) - e^x$ and
  $f''(x) = -e^x$. Since $f(0) = 0$ and $f'(0) = 1 + \delta > 0$, there exists
  $\varepsilon > 0$ such that $f(x) > 0$ for $x \in (0, \varepsilon)$. Observing that
  $f''(x)$ is strictly negative, we can conclude that $f'(x) = 0$ at only a single value
  of $x > 0$, which implies that $f(x) = 0$ for only one positive value of $x$ (otherwise,
  the mean-value theorem would imply that there are multiple values of $x > 0$ with
  $f'(x) = 0$).

  Consider $x = \delta/2$.

  $$
  f(\delta/2)
  = 1 + \frac{(1 + \delta) \delta}{2} - e^{\delta/2}
  = \frac{3}{2} \left( \frac{\delta}{2} \right)^2
    + \left( 1 + \frac{\delta}{2} + \frac{1}{2} \left( \frac{\delta}{2} \right)^2
    - e^{\delta/2} \right).
  $$

  Since $\delta / 2 \ge 0$, we can use the bound $e^x - (1 + x + x^2/2) \le x^3 / (1 - x)$,
  which yields

  $$
  f(\delta/2)
  \ge \frac{3}{2} \left( \frac{\delta}{2} \right)^2
  - \frac{\left( \delta/2 \right)^3}{1 - \delta/2}
  = \left( \frac{\delta}{2} \right)^2
    \left( \frac{3}{2} - \frac{\delta/2}{1 - \delta/2} \right).
  $$

  Note that $\delta \le 1$ implies that

  $$
  \frac{\delta/2}{1 - \delta/2} \le 1
  $$

  so that

  $$
  f(\delta/2) \ge \frac{1}{2} \left( \frac{\delta}{2} \right)^2 > 0.
  $$

  Therefore, we can conclude that that $f(x) > 0$ for $0 \le x \le \delta/2$, which
  is equivalent to the desired bound.

  __Remark__. The previous proposition is a corollary of this proposition with $\delta = 1$.

### Geometric Series Bounds for $e^x$

* For $x < 1$, $e^x \le \frac{1}{1 - x}$.

  _Proof_. Let $f(x) = 1 - (1-x) e^x$. The desired inequality is equivalent to $f(x) \ge 0$.
  Differentiating $f(x)$, we find that $f'(x) = x e^x$.

  For $0 < x < 1$, $f'(x)$ is nonnegative, so $f(x) \ge 0$ because $f(0) = 0$ and

  $$
  f(x) - f(0) = \int_0^x f'(s) ds \ge \int_0^x 0 ds = 0.
  $$

  For $x < 0$, $f'(x)$ is nonpositive, so $f(x) \ge 0$ because $f(0) = 0$ and

  $$
  f(0) - f(x) = \int_x^0 f'(s) ds \le \int_x^0 0 ds = 0.
  $$

  Finally, note that for $x = 0$, we have $f(0) = 0 \ge 0$. Therefore, $f(x) \ge 0$ for
  $x < 1$, as desired.

* __Bounds for Tail Series $\sum_{k=n}^\infty \frac{x^k}{k!}$__. Let $n$ be a positive
  integer. For $x < 1$,

  $$
  \sum_{k=n}^\infty \frac{x^k}{k!} \le \frac{|x|^n}{1 - x}.
  $$

  _Proof_. Let

  $$
  f(x)
  = x^n - (1 - x) \sum_{k=n}^\infty \frac{x^k}{k!}
  = x^n - (1-x) \left( e^x - \sum_{k=0}^{n-1} \frac{x^k}{k!} \right)
  = x^n - (1-x) e^x + (1-x) \sum_{k=0}^{n-1} \frac{x^k}{k!}.
  $$

  The desired inequality is equivalent to

  * $f(x) \ge 0$ when $x \ge 0$,

  * $f(x) \ge 0$ when $x \le 0$ and $n$ is even, and

  * $f(x) \le 0$ when $x \le 0$ and $n$ is odd.

  Differentiating $f(x)$, we find that

  $$
  \begin{align}
  f'(x)
  &= n x^{n-1} + x e^x
    - \sum_{k=0}^{n-1} \frac{x^k}{k!} + (1-x) \sum_{k=0}^{n-2} \frac{x^k}{k!} \\
  &= n x^{n-1} + x e^x - \frac{x^{n-1}}{(n-1)!} - x \sum_{k=0}^{n-2} \frac{x^k}{k!} \\
  &= \left( n - \frac{1}{(n-1)!} \right) x^{n-1}
     + x e^x - x \sum_{k=0}^{n-2} \frac{x^k}{k!}.
  \end{align}
  $$

  For $0 < x < 1$, the bound $e^x \ge \sum_{k=0}^{n} \frac{x^k}{k!}$ (which is satisfied
  for all $x \ge 0$) implies that

  $$
  f'(x) \ge \left( n - \frac{1}{(n-1)!} \right) x^{n-1}.
  $$

  Therefore, $f'(x)$ is nonnegative, so $f(x) \ge 0$ because $f(0) = 0$ and

  $$
  f(x) - f(0) = \int_0^x f'(s) ds \ge \int_0^x 0 ds = 0.
  $$

  For $x < 0$, we need to consider two cases separately: $n$ even and $n$ odd.

  When $n$ is even, $e^x \le \sum_{k=0}^{n-2} \frac{x^k}{k!}$ (because $n-2$ is even), so

  $$
  f'(x) \le \left( n - \frac{1}{(n-1)!} \right) x^{n-1}.
  $$

  Therefore, $f'(x)$ is nonpositive, so $f(x) \ge 0$ because $f(0) = 0$ and

  $$
  f(0) - f(x) = \int_x^0 f'(s) ds \le \int_x^0 0 ds = 0.
  $$

  When $n$ is odd, $e^x \ge \sum_{k=0}^{n-2} \frac{x^k}{k!}$ (because $n-2$ is odd), so

  $$
  f'(x) \ge \left( n - \frac{1}{(n-1)!} \right) x^{n-1}.
  $$

  Therefore, $f'(x)$ is nonnegative, so $f(x) \le 0$ because $f(0) = 0$ and

  $$
  f(0) - f(x) = \int_x^0 f'(s) ds \ge \int_x^0 0 ds = 0.
  $$

  Finally, note that for $x = 0$, we have $f(0) = 0 \ge 0$. Combining the results for all
  of these cases, we obtain the desired bound.

--------------------------------------------------------------------------------------------

## 2022-07-05: Bounds for $\ln(1+x)$

* For $0 \le x \le 1$,

  $$
  x - \frac{x^2}{2} \le \ln(1+x) \le x
  $$

  _Proof_. For $t \ge 0$, $1 + t \ge 1$, which implies that $1 \ge 1 / (1 + t)$.
  Integration yields the upper bound on $\ln(1+x)$:

  $$
  x = \int_0^x 1 dt \ge \int_0^x \left( \frac{dt}{1+t} \right) dt = \ln(1+x).
  $$

  To prove the lower bound, observe that $0 \le t \le 1$ implies that $1 - t^2 \le 1$,
  which can be rearranged to $1 - t \le 1 / (1 + t)$. Integration yields the lower bound:

  $$
  x - \frac{x^2}{2} = \int_0^x (1 - t) dt
  \le \int_0^x \left( \frac{1}{1+t} \right) dt = \ln(1+x).
  $$

  __Corollary__. For $0 \le x \le 1$, $x/2 \le \ln(1+x)$.

  _Proof_. The desired bound follows from the observation that
  $x - x^2/2 \ge x - x / 2 = x/2$ for $0 \le x \le 1$.

--------------------------------------------------------------------------------------------

## 2022-06-16: Permutations with Fixed Points

### Counting Derangments

#### Definitions

* __Derangement__. A _derangement_ is a permutation that has no fixed points.

* __Subfactorial__. The _subfactorial_ of $n$, commonly denoted $!n$, is the number of
  derangements for a set with cardinality $n$.

  * The subfactorial of $n$ is also called the $n$-th _derangement number_ or the $n$-th
    _de Montmort number_.

#### Formulas

* __Recursion Relations__.

  * _Two-Term Recurrence_. For $n \ge 2$,

    $$
    !n = (n-1) ( !(n-1) + !(n-2) ),
    $$

    with $!0 = 1$ and $!1 = 0$.

    _Proof_. Counting derangements for a set of cardinality $n$ is equivalent to the
    "hat-check problem" which consider the number of ways that $n$ hats can be returned to
    $n$ people so that no hat is returned to its owner.

    Let $P_1, \ldots, P_n$ and $h_1, \ldots, h_n$ represent people and hats respectively.
    Suppose that $P_1$ receives $h_i$. Consider $h_i$'s owner, $P_i$. There are two
    possibilities for the hat that $P_i$ receives.

    * $P_i$ receives a hat other than $h_1$. This case is equivalent to the hat-check
      problem with $(n-1)$ people and $(n-1)$ hats (where $h_1$ takes the place of $h_i$).

    * $P_i$ receives $h_1$. In this case, the problem is reduced to the hat-check problem
      for $(n-2)$ people and $(n-2)$ hats.

    Since there are $(n-1)$ hats that $P_1$ could have received and the number of
    derangements for $P_2, \ldots, P_n$ for each possible hat returned to $P_1$ is the sum
    of the number of derangements for the reduced problems:

    $$
    !n = (n-1) ( !(n-1) + !(n-2) ).
    $$

    The base case $!1 = 0$ is readily verified; the base case $!0 = 1$ is equivalent to the
    case $!2 = 1$, which is readily verified.

  * _One-Term Recurrence_. For $n \ge 1$,

    $$
    !n = n(!(n-1)) + (-1)^n
    $$

    with $!0 = 1$.

* __Explicit Formulas__

  * _Sum Formula_

    $$
    !n = n! \sum_{i=0}^n \frac{(-1)^i}{i!} \textrm{ for $n \ge 0$}
    $$

    _Proof_. Let $S_k$ be the set of permutations of $n$ objects that fixes the $k$-th
    object. If $T$ is the intersection of a collection of $i$ of these, it contains
    permutations that fix a particular set of $i$ objects, which implies that
    $|T| = (n-i)!$ permutations. Therefore, by the inclusion-exclusion principle:

    $$
    \begin{align}
    |S_1 \cup \cdots \cup S_n|
    &= \sum_{i} |S_i|
    - \sum_{i < j} |S_i \cap S_j|
    + \sum_{i < j < k} |S_i \cap S_j \cap S_k|
    + \cdots
    + (-1)^{n+1} |S_1 \cap \cdots \cap S_n| \\
    &= {n \choose 1} (n-1)!
    - {n \choose 2} (n-2)!
    + {n \choose 3} (n-3)!
    + \cdots
    + (-1)^{n+1} {n \choose n} 0! \\
    &= \sum_{i=1}^n (-1)^{i+1} {n \choose i} (n-i)! \\
    &= n! \sum_{i=1}^n \frac{(-1)^{i+1}}{i!}
    \end{align}
    $$

    where the factors of $n \choose i$ in the second equality counts the number of ways to
    select $i$ objects to fix.

    Observing that the complement of $S_1 \cup \cdots \cup S_n$ is the set of permutations
    with no fixed points, the number of derangements of $n$ objects is equal to

    $$
    !n
    = n! - |S_1 \cup \cdots \cup S_n|
    = n! \sum_{i=1}^n \frac{(-1)^i}{i!}
    $$

  * _Rounding Formulas_

    $$
    !n = \left[ \frac{n!}{e} \right] \textrm{ for $n \ge 1$}
    $$

    where $[x]$ is nearest integer to $x$.

    $$
    !n = \left\lfloor \frac{n!}{e} + \frac{1}{2} \right\rfloor \textrm{ for $n \ge 1$}
    $$

    where $\lfloor x \rfloor$ is the greatest integer less than or equal to $x$ (i.e.,
    the floor function).

### Sums Involving Permutations with Fixed Points

Let $p_n(k)$ be the number of permutations of $\{1, \ldots, n\}$ with exactly $k$ fixed
points.

* $\sum_{k=0}^n p_n(k) = n!$

  _Proof_. Let $X_k$ be the set of permutations of $\{1, \ldots, n\}$ that have exactly
  $k$ fixed points. Since $\bigcup_{0 \le k \le n} X_k$ is the set of all permutations of
  $\{1, \ldots, n\}$ and $X_j \bigcap X_k = \emptyset$ for all $j \ne k$, $X_k$ is a
  partition of $S_n$ (the set of permutations of $n$ objects). Therefore,
  $\sum_{k=0}^n p_n(k) = n!$.

* $\sum_{k=0}^n k p_n(k) = n!$

  _Proof_. For each permutation $\pi \in S_n$, define the vector $(e_1, \ldots, e_n)$ so
  that $e_i = 1$ if $i$ is a fixed point of $\pi$ and $e_i = 0$ if $i$ is not a fixed point
  of $\pi$. Counting the number of ones contained in all of the vectors by summing over
  permutations yields $\sum_{k=0}^n k p_n(k)$.

  We can also count the number of ones in all of the vectors by summing over the elements
  of $\{1, \ldots, n\}$. For each $i$, the number of vectors where $e_i = 1$ is equal to
  the number of permutations that fix $i$. This is equal to $(n-1)!$, the number of
  permutations the remaining $(n-1)$ elements. Therefore, the total number of ones in
  all of the vectors is equal to $n \times (n-1)! = n!$, which yields the desired result.

* $\sum_{k=0}^n k^2 p_n(k) = 2 n!$

  _Proof_. For each permutation $\pi \in S_n$, define the vector
  $(d_1, \ldots, d_n) = k (e_1, \ldots, e_n)$ where $k$ is the number of fixed points in
  $\pi$ and $e_i$ is defined as above (i.e., $e_i = 1$ if $\pi(i) = i$; $e_i = 0$ if
  $\pi(i) \ne i$). Computing the sum of all of the components of the vectors
  $(d_1, \ldots, d_n)$ by summing over the permutations yields
  $\sum_{k=0}^n k^2 p_n(k) = 2 n!$.

  We can also compute the sum all of the components of the vectors $(d_1, \ldots, d_n)$ by
  summing over the elements of $\{1, \ldots, n\}$. For each $i$, the number of vectors
  where $d_i = k$ is equal to the number of permutations of the remaining $(n-1)$ elements
  with exactly $(k-1)$ fixed points: $p_{n-1}(k-1)$. Therefore, the sum of the $d_i$
  components over all permutations is

  $$
  \sum_{k=1}^n k p_{n-1}(k-1)
  = \sum_{k=0}^{n-1} (k+1) p_{n-1}(k)
  = \sum_{k=0}^{n-1} k p_{n-1}(k) + \sum_{k=0}^{n-1} p_{n-1}(k)
  = 2(n-1)!
  $$

  where the last equality follows by using the previous two results. Summing over $i$
  yields the desired result: $n \times 2(n-1)! = 2n!$.

### References

1. [Wikipedia: Derangement](https://en.wikipedia.org/wiki/Derangement)

2. [Counting Permuations with Fixed Points](https://www.cut-the-knot.org/arithmetic/combinatorics/PermutationsWithFixedPoints.shtml)

--------------------------------------------------------------------------------------------

## 2022-06-09: Determinant Bounds

* __$A$ is near the identity matrix__. [1] provides the following sharp bounds on $\det A$.

  Let $A = I - E$ be an $n \times n$ matrix with

  $$
  \begin{align}
  |E_{ii}| \le \delta & \\
  |E_{ij}| \le \varepsilon &\textrm{ for $i \ne j$}
  \end{align}
  $$

  Then

  $$
  (1 - \delta - (n-1) \varepsilon) (1 - \delta + \varepsilon)^{n-1}
  \le \det A
  \le ( (1 + \delta)^2 + (n-1) \varepsilon^2 )^{n/2},
  $$

  where the lower bound holds under the condition $\delta + (n-1) \varepsilon \le 1$ and
  the upper bound holds for any $\delta$ and $\varepsilon$.

  __Corollary__. When $\delta = \varepsilon$,

  $$
  1 - n \varepsilon
  \le \det A
  \le ( 1 + 2 \varepsilon + n \varepsilon^2 )^{n/2},
  $$

  where the lower bound holds under the condition $n \varepsilon \le 1$ and the upper bound
  holds for any $\delta$ and $\varepsilon$.

  __Corollary__. When $\delta = 0$,

  $$
  (1 - (n-1) \varepsilon) (1 + \varepsilon)^{n-1}
  \le \det A
  \le ( 1 + (n-1) \varepsilon^2 )^{n/2},
  $$

  where the lower bound holds under the condition $(n-1) \varepsilon \le 1$ and the upper
  bound holds for any $\delta$ and $\varepsilon$.

* __$A$ is diagonally dominant__. [2] provides the following bounds on $\det A$.

  * Let $A$ be an $n \times n$ strictly diagonally dominant complex matrix. That is,

    $$
    |a_{ii}| > \sum_{i \ne j} |a_{ij}|.
    $$

    Define

    $$
    u_i = \sum_{j=i+1}^n |a_{ij}|.
    $$

    Then

    $$
    0
    < \prod_{i=1}^n \left( |a_{ii}| - u_i \right)
    \le |\det A|
    \le \prod_{i=1}^n \left( |a_{ii}| + u_i \right).
    $$

    __Remarks__.

    * When $A$ is diagonally dominant but not strictly (i.e.,
      $|a_{ii}| > \sum_{i \ne j} |a_{ij}|$), then the lower bound on $\det A$ is not
      strictly positive:

      $$
      0 \le \prod_{i=1}^n \left( |a_{ii}| - u_i \right).
      $$

    * When $A$ real with positive diagonal elements, then the bounds hold without the
      absolute value on $\det A$:

      $$
      0
      < \prod_{i=1}^n \left( |a_{ii}| - u_i \right)
      \le \det A
      \le \prod_{i=1}^n \left( |a_{ii}| + u_i \right).
      $$

### References

1. R.P. Brent, J.H. Osborn, W.D. Smith. "Note on best possible bounds for determinants of
   matrices close to the identity matrix" (2015).

2. G.B. Price. "Bounds for Determinants with Dominant Principal Diagonal" (1951).

--------------------------------------------------------------------------------------------

## 2022-06-07: Hadamard's Inequality

### Notation

* $\newcommand{\tr}[0]{\operatorname{tr}}$
  Trace of a matrix $A$: $\tr A$.

### Theorem

Let $M$ be an $n \times n$ matrix having columns $v_i$. Then

$$
| \det M | \leq \prod_{i=1}^{n} \|v_i\|.
$$

If the $n$ vectors are non-zero, equality is achieved if and only if the vectors are
orthogonal.

_Proof_

* __Lemma__. If $A$ is an $n \times n$ matrix where each column has length 1, then
  $\det A \le 1$.

  _Proof_. Consider $P = A'A$' and let the eigenvalues of $P$ be
  $\lambda_1, \ldots, \lambda_n$. Since the length of each vector $v_i$ is 1, the diagonal
  elements of $P$ are all equal to 1. Recall that

  $$
  \begin{align}
  \det P &= \prod_{i=1}^n \lambda_i \\
  \tr P &= \sum_{i=1}^n P_{ii} = \sum_{i=1}^n \lambda_i,
  \end{align}
  $$

  where the last equality follows because the trace is invariant under similarity
  transformations.

  By the AM-GM inequality,

  $$
  \left( \prod_{i=1}^n \lambda_i \right)^{1/n}
  \le \frac{1}{n} \sum_{i=1}^n \lambda_i
  = \frac{1}{n} \sum_{i=1}^n P_{ii}
  = \frac{\tr P}{n} = 1.
  $$

  Therefore,

  $$
  \det A = \sqrt{\det P} \le (\tr P)^{n/2} = 1^{n/2} = 1.
  $$

To complete the proof of Hadamard's inequality, observe that

$$
|\det M|
= \left( \prod_{i=1}^{n} \|v_i\| \right) |\det A|,
$$

where the $i$-th column of $A$ is equal to $v_i / \|v_i\|$. Since the columns of $A$ all
have unit length, the lemma implies that $|\det A| \le 1$. Hadamard's inequality follows.

### Remarks

* __Geometric Intepretation__. The volume of the parallelipiped formed by the vectors $v_i$
  is bounded above by the product of the lengths of the vectors.

### References

* [Wikipedia: Hadamard's Inequality](https://en.wikipedia.org/wiki/Hadamard's_inequality)

--------------------------------------------------------------------------------------------

## 2022-06-07: Useful Inequalities

* Let $m < n$. Then

  $$
  \frac{m-k}{n-k} \le \frac{m}{n}
  $$

  for $0 \le k \le m$.

* If $0 \le \varepsilon \le 1$,

  $$
  1 - \frac{\varepsilon^2}{2}
  \ge \sqrt{1 - \varepsilon^2}
  \ge 1 - \varepsilon^2
  \ge 1 - \varepsilon.
  $$

  The first inequality is Bernoulli's inequality for exponents between 0 and 1.

* For all $z \ge 0$, $|z-1| \ge \delta$ implies $|z^2-1| \ge \max(\delta, \delta^2)$.

  _Proof_.  $|z-1| \ge \delta$ implies that $z - 1 \ge \delta$ or $1 - z \ge \delta$.

  For the case $z - 1 \ge \delta$, observe that $z +1 \ge \delta + 2$, which implies that

  $$
  |z^2 - 1| = (z - 1) (z + 1)
  \ge \delta (\delta + 2)
  \ge \delta^2 + 2 \delta.
  $$

  When $\delta \le 1$, $\max(\delta, \delta^2) = \delta \le \delta^2 + 2 \delta$. When
  $\delta > 1$, $\max(\delta, \delta^2) = \delta^2 \le \delta^2 + 2 \delta$. In both cases,
  $|z^2 - 1| \ge \max(\delta, \delta^2)$.

  For the case $1 - z \ge \delta$, we need only consider the case $\delta \le 1$ (because
  $\delta > 1$ would imply that $z < 0$).  If $1 - z \ge \delta$, then $z \le 1 - \delta$
  so that

  $$
  |z^2 - 1| = 1 - z^2
  \ge 1 - (1 - \delta)^2
  = 1 - (1 - 2 \delta + \delta^2)
  = \delta + (\delta - \delta^2)
  \ge \delta
  = \max(\delta, \delta^2).
  $$

  _References_

  * R. Vershynin. "High-Dimensional Probability" (2018).

--------------------------------------------------------------------------------------------

## 2022-06-06: Blades - Norm Bounds

_Last Updated_: 2022-06-08

### Notation

* $\newcommand{\R}[0]{\mathbb{R}}$
  The set of real numbers: $\R$

* $\newcommand{\P}[2]{\mathbf{P}_{#1}\left({#2}\right)}$
  The projection of blade $A$ onto blade $B$: $\P{B}{A}$

### Lemmas

* Let $B_1, \ldots, B_m$ be blades with unit norm. If
  $| B_1 \wedge \cdots \wedge B_m | > 1 - \varepsilon$, then
  $| B_{i_1} \wedge \cdots \wedge B_{i_k} | > 1 - \varepsilon$ for any
  $\{i_1, \ldots, i_k\} \subseteq \{1, \ldots, m\}$.

  _Proof_. We prove the contrapositive. Suppose there exists a set
  $\Omega = \{i_1, \ldots, i_k\} \subseteq \{1, \ldots, m\}$ such that
  $| B_{i_1} \wedge \cdots \wedge B_{i_k} | \le 1 - \varepsilon$. Then

  $$
  | B_1 \wedge \cdots \wedge B_m |
  \le | B_{i_1} \wedge \cdots \wedge B_{i_k} | | B_{j_1} \wedge \cdots \wedge B_{j_{m-k}} |
  \le 1 - \varepsilon
  $$

  where $j_1, \ldots, j_{m-k} \notin \Omega$. The second inequality follows the assumption
  $| B_{i_1} \wedge \cdots \wedge B_{i_k} | \le 1 - \varepsilon$ and the observation that
  $| B_{j_1} \wedge \cdots \wedge B_{j_l} | \le |B_{j_1}| \cdots |B_{j_l}| = 1$ when the
  $B_i$ all have unit norm.

  __Corollary__. If $B_1, \ldots, B_m$ are blades with unit norm such that
  $| B_1 \wedge \cdots \wedge B_m | > 1 - \varepsilon$, then $|B_i| > 1 - \varepsilon$ for
  all $1 \le i \le m$.

  __Remarks__. The inequality

  $$
  | B_1 \wedge \cdots \wedge B_k | \le |B_1| \cdots |B_k|
  $$

  is a generalization of Hadamard's inequality to blades of arbitrary grade in terms of
  their outer product decompositions into blades of arbitrary grade.

* Let $u = (u_1, \ldots, u_n)$ be a unit vector in $\R^n$ having the property that the
  projection of $u$ onto any blade formed as the outer product of $s < \frac{n}{2}$
  standard basis vectors that include $e_i$ is greater than $\sqrt{1 - \varepsilon^2}$.

  Then the magnitude of the projection of $u$ onto $e_i$ is bounded from below:

  $$
  |u_i|^2
  \ge 1 - \left( 1 + \frac{s-1}{n-s} \right) \varepsilon^2
  \ge 1 - \left( 1 + \frac{2s}{n} \right) \varepsilon^2.
  $$

  _Proof_. The lower bound on the projection of $u$ onto the outer project of $s$ standard
  basis vectors that include $e_i$ implies that

  $$
  u_i^2 + \sum_{j \in \Omega, j \ne i} u_j^2 \ge 1 - \varepsilon^2,
  $$

  where $\Omega \subset \{1, \ldots, n\}$ such that $i \in \Omega$ and $|\Omega| = s$.
  Since $u$ has unit norm,

  $$
  u_i^2 + \sum_{j \in \Omega, j \ne i} u_j^2 = 1 - \sum_{j \notin \Omega} u_j^2,
  $$

  which implies that

  $$
  \sum_{j \notin \Omega} u_j^2 \le \varepsilon^2
  $$

  Summing over the ${ n-1 \choose s-1 }$ choices for sets $\Omega$ containing $i$, we
  obtain

  $$
  { n-2 \choose s-1 } \sum_{j \ne i} u_j^2 \le { n-1 \choose s-1 } \varepsilon^2
  $$

  because for each $j \ne i$, $u_j$ appears in the sums for the ${ n-2 \choose s-1 }$ sets
  $\Omega$ that do not contain $j$. Rearranging and simplifying,

  $$
  \sum_{j \ne i} u_j^2
  \le \left( \frac{n-1}{n-s} \right) \varepsilon^2
  = \left( 1 + \frac{s-1}{n-s} \right) \varepsilon^2,
  $$

  which implies that

  $$
  |u_i|^2
  \ge 1 - \left( 1 + \frac{s-1}{n-s} \right) \varepsilon^2
  \ge 1 - \left( 1 + \frac{s}{n-s} \right) \varepsilon^2
  \ge 1 - \left( 1 + \frac{2s}{n} \right) \varepsilon^2.
  $$

  The last inequality follows because

  $$
  \frac{m-k}{n-k} \le \frac{m}{n}
  $$

  when $m < n$ and $0 \le k \le m$.

* Let $u_1, \ldots, u_n \in \R^n$ be unit vectors such that
  $u_i \cdot e_i \ge \sqrt{1 - \varepsilon^2}$ for $1 \le i \le n$ and $s$ be a positive
  integer such that $s \varepsilon \le 1$. Then for any
  $\Omega = \{i_1, \ldots, i_k\} \subseteq \{1, \ldots, n\}$ with $k \le s$,

  $$
  | \P{B}{u_{i_1}} \wedge \cdots \wedge \P{B}{u_{i_k}} | \ge 1 - k \varepsilon
  $$

  where $\P{B}{u}$ is the projection of $u$ onto the space represented by the blade
  $B = e_{i_1} \wedge \cdots \wedge e_{i_k}$.

  _Proof_. Construct the $k \times k$ square matrix $M$ with $i$-th column equal to the
  $k$-component vector formed by restricting $u_i$ to the indices in $\Omega$. The
  bounds on $u_i \cdot e_i$ impliy the following bounds on the elements of $M$:

  $$
  M_{jj} = u_{i_j} \cdot e_{i_j} \ge 1 - \varepsilon \textrm{ for all $j$}
  $$

  and
  $$

  M_{jl} \le \varepsilon \textrm{ for all $j \ne l$},
  $$

  where the first inequality follows because $\sqrt{1 - \varepsilon^2} \ge 1 - \varepsilon$
  and the second inequality follows because the $j$-th component of $u_i$ is bounded above by
  $\sqrt{1 - (u_i \cdot e_i)^2} \le \varepsilon$.

  Observe that

  $$
  | \P{B}{u_{i_1}} \wedge \cdots \wedge \P{B}{u_{i_k}} | = \det M.
  $$

  Therefore,

  $$
  | \P{B}{u_{i_1}} \wedge \cdots \wedge \P{B}{u_{i_k}} | \ge 1 - k \varepsilon
  $$

  where the inequality follows from the lower bound on the determinant of matrices near
  the identity matrix [1].

  __Corollary__. If $u_1, \ldots, u_n \in \R^n$ are unit vectors such that
  $u_i \cdot e_i \ge \sqrt{1 - \varepsilon^2}$ for $1 \le i \le n$ and
  $s \varepsilon \le 1$, then
  $| u_{i_1} \wedge \cdots \wedge u_{i_s} | \ge 1 - s \varepsilon$ for any
  $\{i_1, \ldots, i_s\} \subseteq \{1, \ldots, n\}$.

* Let $u_1, \ldots, u_n \in \R^n$ be unit vectors such that

  $$
  \begin{align}
  u_i \cdot e_i \ge 1 - \delta \\
  u_i \cdot e_j \le \varepsilon &\textrm{ for $i \ne j$}.
  \end{align}
  $$

  If $s$ be a positive integer such that $\delta + (s-1) \varepsilon \le 1$, then for any
  $\Omega = \{i_1, \ldots, i_k\} \subseteq \{1, \ldots, n\}$ with $k \le s$,

  $$
  | \P{B}{u_{i_1}} \wedge \cdots \wedge \P{B}{u_{i_k}} |
  \ge (1 - \delta - (k-1) \varepsilon)(1 - \delta + \varepsilon)^{k-1}.
  $$

  where $\P{B}{u}$ is the projection of $u$ onto the space represented by the blade
  $B = e_{i_1} \wedge \cdots \wedge e_{i_k}$.

  _Proof_. The proof is analogous to the above Lemma except that $\delta \ne \varepsilon$ so
  that the lower bound on the determinant is modified [1].

### References

1. R.P. Brent, J.H. Osborn, W.D. Smith. "Note on best possible bounds for determinants of
   matrices close to the identity matrix" (2015).

--------------------------------------------------------------------------------------------

## 2022-05-30: Field Extensions and Tensor Product of Vector Spaces

### References

* H. Yuki. "Math Girls$^5$: Galois Theory" (2012).

### Observation

* If feels like there is a connection between

  * constructing a field extension of a base field $\mathbb{F}$ by sequentially adjoining
    elements $x_1, \ldots, x_n$ when $x_{k} \notin \mathbb{F}(x_1) \cdots (x_{k-1})$ and

  * constructing a tensor product of vector spaces $U_1, \ldots, U_n$ with
    $\dim U_k = [\mathbb{F}(x_k) : \mathbb{F}]$ (where $[K : L]$ is the degree of the field
    extension $K/L$).

--------------------------------------------------------------------------------------------

## 2022-05-28: Galois Theory

_Last Updated_: 2022-05-28

### References

* H. Yuki. "Math Girls$^5$: Galois Theory" (2012).

### Definitions

* _Symmetric Polynomial_. A polynomial in $x_1, \ldots, x_n$ is symmetric if it is
  invariant under any permutation of the variables.

* _Elementary Symmetric Polynomial_. A symmetric polynomial formed as a sum of products
  of terms that all have the same degree

  * Examples: $x_1 + x_2 + x_3$, $x_1 x_2 + x_2 x_3 + x_3 x_1$, $x_1 x_2 x_3$

* _Lagrange Resolvent_. For an $n$-th degree polynomial $P$ with roots $\alpha_j$, the
  the $k$-th Lagrange resolvent is equal to

  $$
  L_n(k) = \sum_{j=1}^n \zeta_n^{kj} \alpha_j,
  $$

  where $\zeta_n$ is a primitive $n$th root of unity.

### Key Ideas

* _Fundamental Theorem of Symmetric Polynomials_. Any symmetric polynomial can be
  expressed as a linear combination of elementary symmetric polynomials.

* Elementary symmetric polynomials, and therefore _any_ symmetric polynomial, of the roots
  of a polynomial $P$ can be expressed in terms of the coefficients of $P$.

* The Lagrange resolvents … TODO

--------------------------------------------------------------------------------------------

## 2022-05-30: Exercise - Linearity of Expectation

### Expected Number of Attempts Before Success

__Problem__. Suppose we have a biased coin that lands heads up with probability $p$. If
we repeatedly toss the coin until it lands with heads up, find the expected number times
we toss the coin.

__Solution 1__. Using linearity of expectation.

Let $X_k$ be an indicator variable that equals 1 if the coin has not yet landed with heads
up after $k$ tosses (i.e., tosses $1, \ldots, k$ are all tails) and equal to 0 if the coin
has landed with heads up on or before the $k$-th toss. For any realized sequence of tosses,

$$
1 + \sum_{k=1}^\infty X_k
$$

is equal to the number of tosses needed before the coin lands heads up. By linearity of
expectation, the expected number of tosses before the coin lands heads up is equal to

$$
E\left[1 + \sum_{k=1}^\infty X_k \right]
= 1 + \sum_{k=1}^\infty E[X_k]
= 1 + \sum_{k=1}^\infty P(\textrm{first $k$ tosses are all tails}),
$$

where the last equality follows because $X_k$ is an indicator function. Since the
probability that the first $k$ tosses are all tails is equal to $(1-p)^k$, this sum is
equal to

$$
1 + \sum_{k=1}^\infty (1 - p)^{k}
= 1 + \frac{1 - p}{1 - (1-p)}
= 1 + \frac{1 - p}{p}
= \frac{1}{p}.
$$

__Solution 2__. Direct calculation from the probability distribution.

Let $X$ be the number of tosses until the coin lands heads up for the first time. The
distribution for $X$ is (one form of) the geometric distribution:

$$
P(\textrm{$k$-th toss is first heads}) = p (1 - p)^{k-1}.
$$

Using this probability distribution,

$$
\begin{align}
E[X]
&= \sum_{k = 1}^\infty k p (1 - p)^{k-1} \\
&= p \left. \frac{d}{dx} \sum_{k = 0}^\infty x^k \right|_{x = (1-p)} \\
&= p \left. \frac{d}{dx} \left( \frac{1}{1-x} \right) \right|_{x = (1-p)} \\
&= \left. \frac{p}{(1-x)^2} \right|_{x = (1-p)} \\
&= \left. \frac{p}{(1-x)^2} \right|_{x = (1-p)} \\
&= \frac{1}{p}.
\end{align}
$$

### Upper Bound on Expected Number of Attempts Before Success

__Problem__. For a biased coin that lands heads up with probability no less than $p$, show
that the expected number times we need toss the coin until it lands with heads up is less
than $1/p$.

__Solution__.

Letting $X_k$ be the same indicator variable used above, the expected number of tosses
before the coin lands heads up is equal to

$$
E\left[1 + \sum_{k=1}^\infty X_k \right]
= 1 + \sum_{k=1}^\infty E[X_k]
= 1 + \sum_{k=1}^\infty P(\textrm{first $k$ tosses are all tails}).
$$

Since the probability that the coin lands heads up is no less than $p$, the probability
that the coin lands tails up is less than $(1-p)$. Therefore, the desired expected value
is bounded above by

$$
1 + \sum_{k=1}^\infty (1-p)^k
= 1 + \frac{1-p}{p}
= \frac{1}{p}.
$$

--------------------------------------------------------------------------------------------

## 2022-05-24: Exercise - Using Calculus to Derive Inequality

__Problem__. Show that

$$
  \frac{e^{-\lambda}}{\sqrt{1 - 2 \lambda}} \le e^{2 \lambda^2}.
$$

for $|\lambda| \le 1/4$.

(From Example 2.8 in "High-Dimensional Statistics" by M. Wainwright).

__Solution__. Consider the function

$$
  f(\lambda) = 1 - 2 \lambda - e^{-2 \lambda - 4 \lambda^2}
$$

The desired inequality is equivalent $f(\lambda) \ge 0$. Differentiating, we find that
the first and second derivatives of $f$ are

$$
\begin{align}
f'(\lambda) &= - 2  + (2 + 8 \lambda) e^{-2 \lambda - 4 \lambda^2} \\

f''(\lambda)
&= \left( 8 - (2 + 8 \lambda)^2 \right) e^{-2 \lambda - 4 \lambda^2}
= 4 \left( 1 - 8 \lambda - 16 \lambda^2 \right) e^{-2 \lambda - 4 \lambda^2}.
\end{align}
$$

Observe that $f'(0) = 0$, and $f''(0) = 4$, so $f(0) = 0$ is a local minimum.

For $-1 \le \lambda \le 0$, recall that

$$
e^{-2 \lambda - 4 \lambda^2}
\le e^{-2 \lambda}
\le 1 - 4 \lambda,
$$

which implies that

$$
f'(\lambda)
\le -2 + 2 (1 + 4 \lambda) ( 1 - 4 \lambda)
= -2 + 2 (1 - 16 \lambda^2)
= -16 \lambda^2
\le 0.
$$

Therefore, $f(\lambda) \ge f(0) = 0$ for $-1 \le \lambda \le 0$ because

$$
f(0) - f(\lambda)
= \int_{-\lambda}^0 f'(s) ds
\le \int_{-\lambda}^0 0 ds
= 0.
$$

For $\lambda \ge 0$, note that $f''(\lambda)$ has one positive, non-repeated root at
$\lambda_0 = (-1 + \sqrt{2}) / 4$. At $\lambda = \lambda_0$, $f''(\lambda)$ transitions
from positive to negative, which implies that $f'(\lambda)$ increases for
$0 \le \lambda \le \lambda_0$ and then decreases for $\lambda > \lambda_0$. These
observations, combined with $f'(0) = 0$, imply that $f'(\lambda) = 0$ at a single value of
$x > 0$. Therefore, $f(\lambda) = 0$ for only one positive value of $\lambda$ (otherwise,
the mean-value theorem would imply that there are multiple values of $\lambda > 0$ with
$f'(\lambda) = 0$). Noting that $f(1/4) > 0$, which follows from

$$
f(1/4)
= 1 - \frac{1}{2} - e^{-3/4}
= \frac{1}{2} - e^{-3/4}
\ge \frac{1}{2} - \sum_{k=0}^4 \frac{(-1)^k}{k!}\left(\frac{3}{4}\right)^k
= \frac{1}{2} - \frac{971}{2048}
= \frac{53}{2048} > 0,
$$

we can conclude that $f(\lambda) \ge 0$ for $0 \le \lambda \le 1/4$.

Combining our results for positive and negative $\lambda$, we find that $f(\lambda) \ge 0$
for $|\lambda| \le 1/4$, which is equivalent to the desired inequality

$$
  \frac{e^{-\lambda}}{\sqrt{1 - 2 \lambda}} \le e^{2 \lambda^2}.
$$

--------------------------------------------------------------------------------------------

## 2022-05-24: Polynomial Bounds for $e^x$

* For all $x \in \R$, $e^x \ge 1 + x$.

* For $x \ge 0$, $e^x \ge \sum_{k = 0}^n \frac{x^k}{k!}$ for $n \in \Z$.

* For $x < 0$, $e^x \le \sum_{k = 0}^n \frac{x^k}{k!}$ when $n$ is even.

* For $x < 0$, $e^x \ge \sum_{k = 0}^n \frac{x^k}{k!}$ when $n$ is odd.

### References

* https://www.bowaggoner.com/blog/2017/10-06-useful-bounds-taylors/

* https://math.stackexchange.com/questions/210591/upper-bound-of-exponential-function

--------------------------------------------------------------------------------------------
