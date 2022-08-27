An Introduction to Stochastic Modeling (Taylor and Karlin): Problems 1.2
========================================================================

--------------------------------------------------------------------------------------------
## 0. Notation

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

* $\newcommand{\Cov}[1]{{\operatorname{Cov}}{\left(#1\right)}}$
  Covariance of $X$: $\Cov{X}$

--------------------------------------------------------------------------------------------
### 2.1.

__Problem__. Thirteen cards numbered $1, \ldots, 13$ are shuffled and dealt one at a time.
Say a _match_ occurs on deal $k$ if the $k$th card revealed is card number $k$. Let $N$
be the total number of matches that occur in the thirteen cards. Determine $\E{N}$.

__Hint__ Write $N = \1{A_1} + \cdots + \1{A_{13}}$ where $A_k$ is the event that a match
occurs on deal $k$.

__Solution__. Let $N = \1{A_1} + \cdots + \1{A_{13}}$ where $A_k$ is the event that a
match occur on deal $k$. Then

$$
\E{N}
= \E{\1{A_1}} + \cdots + \E{\1{A_{13}}}
= \Pr{A_1} + \cdots + \Pr{A_{13}}
= \frac{1}{13} + \cdots + \frac{1}{13}
= 1.
$$

--------------------------------------------------------------------------------------------
### 2.2.

__Problem__. Let $N$ cards carry the distinct numbers $x_1, \ldots, x_N$. If two cards
are drawn at random without replacement, show that the correlation coefficient $\rho$
between the numbers appearing on the two cards is $-1/(N-1)$.

__Solution__.  Let $Y$ and $Z$ be random variables for the outcomes first and second
drawn cards, respectively. $\rho = \sigma_{YZ} / \sigma_Y \sigma_Z$. Calculating the
quantities required to compute $\rho$:

* $$
  \mu_Y
  = \E{Y}
  = \sum_{i=1}^N \Pr{Y = x_i} x_i
  = \sum_{i=1}^N \left(\frac{1}{N}\right) x_i
  = \frac{\sum_{i=1}^N x_i}{N}
  $$

* $$
  \mu_Z
  = \E{Z}
  = \sum_{i=1}^N \Pr{Y = x_i} \sum_{j=1}^N \Pr{Z = x_j | Y = x_i} x_j \\
  = \sum_{i=1}^N \left(\frac{1}{N}\right)
    \sum_{j=1, j\ne i}^N \left(\frac{1}{N-1}\right) x_j
  = \frac{1}{N(N-1)} \sum_{i=1}^N \sum_{j=1, j\ne i}^N x_j
  = \frac{\sum_{i=1}^N x_i}{N}
  = \mu_Y
  $$

* $$
  \E{Y^2}
  = \sum_{i=1}^N \Pr{Y = x_i} x_i^2
  = \sum_{i=1}^N \left(\frac{1}{N}\right) x_i^2
  = \frac{\sum_{i=1}^N x_i^2}{N}
  $$

* $$
  \E{Z^2}
  = \sum_{i=1}^N \Pr{Y = x_i} \sum_{j=1}^N \Pr{Z = x_j | Y = x_i} x_j^2 \\
  = \sum_{i=1}^N \left(\frac{1}{N}\right)
    \sum_{j=1, j\ne i}^N \left(\frac{1}{N-1}\right) x_j^2
  = \frac{1}{N(N-1)} \sum_{i=1}^N \sum_{j=1, j\ne i}^N x_j^2
  = \frac{\sum_{i=1}^N x_i^2}{N}
  = \E{Y^2}
  $$

* $$
  \Cov{YZ}
  = \sum_{i=1}^N \sum_{j=1}^N \Pr{Y = x_i, Z = x_j} x_i x_j
  = \sum_{i=1}^N \sum_{j=1, j\ne i}^N \left(\frac{1}{N(N-1)}\right) x_i x_j \\
  = \frac{1}{N(N-1)} \sum_{i=1}^N \sum_{j=1, j\ne i}^N x_i x_j
  $$

* TODO

* $$
  \sigma_{YZ}
  = \Cov{YZ} - \mu_Y \mu_Z
  = \E{XY} - \mu_X \mu_Y
  $$

--------------------------------------------------------------------------------------------
### 2.3.

__Problem__. A population having $N$ distinct elements is sampled with replacement. Because
of repetitions, a random sample of size $r$ may contain fewer than $r$ distinct elements.
Let $S_r$ be the sample size necessary to get $r$ distinct elements. Show that

$$
\E{S_r} = N \left( \frac{1}{N} + \frac{1}{N-1} + \cdots + \frac{1}{N - r + 1} \right).
$$

__Solution__. Since the first sample always yields a 1 distinct element, $S_1 = 1 = N/N$.
For $r \ge 2$, consider a sequence of samples drawn from the population. Let $X_i$ be the
number of samples between the appearance of the $(i-1)$-th and the $i$-th distinct elements
in the sequence (not including either of them). Then $S_r = 1 + \sum_{i=2}^r (1 + X_i)$.

Consider the sequence of samples after the appearance of the $(i-1)$-th distinct element.
Let $A_k$ be the event that all of the elements before or on the $k$-th sample are repeats
of the first $i-1$ distinct elements. Observe that $X_i = \sum_{k=1}^\infty \1{A_k}$, so

$$
\E{X_i}
= \sum_{k=1}^\infty \E{\1{A_k}}
= \sum_{k=1}^\infty \Pr{A_k}
= \sum_{k=1}^\infty \left(\frac{i-1}{N}\right)^k
= \left(\frac{i}{N}\right) \left(\frac{1}{1 - (i-1) / N}\right)
= \frac{i-1}{N-i+1}.
$$

Taking the expectation of $S_r$, we obtain the desired result

$$
\E{S_r}
= 1 + \sum_{i=2}^r (1 + \E{X_i})
= 1 + \sum_{i=2}^r \left( 1 + \frac{i-1}{N-i+1} \right)
= \frac{N}{N} + \sum_{i=2}^r \frac{N}{N-i+1}
= N \sum_{i=1}^r \frac{1}{N-i+1}.
$$

--------------------------------------------------------------------------------------------
### 2.4.

A fair coin is tossed until the first time that the same side appears twice in succession.
Let $N$ be the number of tosses required.

#### 2.4.a.

__Problem__. Determine the probability mass function for $N$.

__Solution__. Let $q_N$ be the probability that the same side does not appear twice in
succession within the first $N$ tosses. Then $q_N$ satisfies the recurrence relation

$$
q_N = q_{N-1} \times \Pr{\textrm{the $N$-th toss is different from the $(N-1)$-st toss}}
$$

for $N > 2$ and initial condition $q_2 = 1/2$. The solution to this recurrence is
$q_N = 2^{-(N-1)}$. Therefore, the probability mass function for $N$ is

$$
p_N
= q_{N-1} \times \Pr{\textrm{the $N$-th toss is the same as the $(N-1)$-st toss}}
= q_{N-1} \times \frac{1}{2}
= 2^{-(N-1)}
$$

for $N \ge 2$ and $p_1 = 0$.


#### 2.4.b.

__Problem__. Let $A$ be the event that $N$ is even and $B$ be the event that $N \le 6$.
Evaluate $\Pr{A}$, $\Pr{B}$, and $\Pr{AB}$.

__Solution__.

$$
\Pr{\textrm{$N$ is even}}
= \sum_{N=2}^\infty 2^{-N+1}
= 2 \sum_{N=2}^\infty 2^{-N}
= 2 \sum_{k=1}^\infty 2^{-2k}
= 2 \sum_{k=1}^\infty 4^{-k}
= 2 \left( \frac{1/4}{1 - 1/4} \right)
= \frac{2}{3}
$$

$$
\Pr{\textrm{$N \le 6$}}
= \sum_{N=2}^6 2^{-N+1}
= 2 \sum_{N=2}^6 2^{-N}
= 2 \left( \frac{1/4 - (1/2)^7}{1 - 1/2} \right)
= 2 ( 2^{-1} - 2^{-6} )
= 1 - 2^{-5}
$$

$$
\Pr{\textrm{$N$ is even and $N \le 6$}}
= \sum_{k=1}^3 2^{-2k+1}
= 2 \sum_{k=1}^3 4^{-k}
= 2 \left( \frac{1/4 - (1/4)^4}{1 - 1/4} \right)
= \frac{2}{3} ( 1 - 4^{-3} )
$$

--------------------------------------------------------------------------------------------
### 2.5.

Two players, $A$ and $B$, take turns on a gambling machine until one of them scores a
success, the first to do so being the winner. Their probabilities for success on a single
play are $p$ for $A$ and $q$ for $B$, and successive plays are independent.

#### 2.5.a.

__Problem__. Determine the probability that $A$ wins the contest given that $A$ plays first.

__Solution__. Let $P_n$ be the probability that player $A$ wins the game after $n$ rounds.
Clearly, $P_1 = p$. For $n \ge 2$, the probability that neither player has won the game
after playing $(n-1)$ rounds is $((1-p) (1-q))^{n-1}$, so $P_n = p ((1-p) (1-q))^{n-1}$.
Note that the expression for $P_n$ when $n \ge 2$ also holds when $n = 1$.

To compute the probability that player $A$ wins the game, we sum $P_n$ over all possible
values of $n$:

$$
\Pr{\textrm{player $A$ wins}}
= \sum_{n=1}^\infty p ((1 - p) (1 - q))^{n-1}
= p \sum_{n=0}^\infty ((1 - p) (1 - q))^n
= \frac{p}{1 - (1 - p) (1 - q)}
$$

#### 2.5.b.

__Problem__. Determine the mean number of plays required, given that $A$ wins.

__Solution__. Let $P_A = p / (1 - (1 - p)(1 - q))$ be the probability that $A$ wins. Then
given that $A$ wins, the game requires $n$ rounds of play with probability

$$
\frac{p ((1-p)(1-q))^{n-1}}{P_A}.
$$

Therefore, the expected number of rounds of play given that $A$ wins is equal to

$$
\sum_{n=1}^\infty n \frac{p ((1 - p) (1 - q))^{n-1}}{P_A}
= \left(\frac{p}{P_A}\right) \sum_{n=1}^\infty n ((1 - p) (1 - q))^{n-1}
= \left(\frac{p}{P_A}\right)
  \sum_{n=1}^\infty \left. \frac{d}{dx} x^n \right|_{x = (1- p)(1-q)} \\
= \left(\frac{p}{P_A}\right) \left.
    \frac{d}{dx} \left( \sum_{n=1}^\infty x^n \right)
  \right|_{x = (1- p)(1-q)}
= \left(\frac{p}{P_A}\right)
  \left. \frac{d}{dx} \left(\frac{x}{1-x}\right) \right|_{x = (1- p)(1-q)} \\
= \left(\frac{p}{P_A}\right)
  \left. \frac{d}{dx} \left(1 - \frac{1}{1-x}\right) \right|_{x = (1- p)(1-q)}
= \left(\frac{p}{P_A}\right) \left. \frac{1}{(1-x)^2} \right|_{x = (1- p)(1-q)} \\
= \left(\frac{p}{P_A}\right) \frac{1}{(1 - (1-p)(1-q))^2}
= \frac{1}{1 - (1-p)(1-q)}.
$$

--------------------------------------------------------------------------------------------
### 2.6.

__Problem__. A pair of dice is tossed. If the two outcomes are equal, the dice are tossed
again, and the process repeated. If the dice are unequal, their sum is recorded. Determine
the probability mass function for the sum.

__Solution__. Since rolls where the two dice are equal are ignored, the total number
of outcomes for the pair of dice is 30 (= 36 - 6) and the possible values for the sum are
3, 4, 5, 6, 7, 8, 9, 10, and 11. Counting the possible ways for each of these value
can occur yields the frequency table for the sum $S$:

$$
\begin{array}{lccccccccc}
\textrm{S}         & 3 & 4 & 5 & 6 & 7 & 8 & 9 & 10 & 11 \\
\textrm{frequency} & 2 & 2 & 4 & 4 & 6 & 4 & 4 &  2 &  2
\end{array}
$$

Therefore, the probability mass function for $S$ is

$$
\begin{array}{lccccccccc}
\textrm{S}    &    3 &    4 &    5 &    6 &   7 &    8 &    9 &   10 &   11 \\
\textrm{P(S)} & 1/15 & 1/15 & 2/15 & 2/15 & 1/5 & 2/15 & 2/15 & 1/15 & 1/15
\end{array}
$$

--------------------------------------------------------------------------------------------
### 2.7.

__Problem__. Let $U$ and $W$ be jointly distributed random variables. Show that $U$ and $W$
are independent if

$$
\Pr{\textrm{$U > u$ and $W > w$}} = \Pr{U > u} \Pr{W > w}
$$

for all $u, w$.

__Solution__. Observe that

$$
\Pr{\textrm{$U \le u$ and $W \le w$}}
= 1 - \Pr{\textrm{$U > u$ or $W > w$}} \\
= 1 - (\Pr{U > u} + \Pr{W > w} - \Pr{\textrm{$U > u$ and $W > w$}}) \\
= 1 - (\Pr{U > u} + \Pr{W > w} - \Pr{U > u} \Pr{W > w}) \\
= (1 - \Pr{U > u})(1 - \Pr{W > w})
= \Pr{U \le u} \Pr{W \le w},
$$

which implies that $U$ and $W$ are independent.

--------------------------------------------------------------------------------------------
### 2.8.

__Problem__. Suppose $X$ is a random variable with finite mean $\mu$ and variance
$\sigma^2$, and $Y = a + bX$ for certain constants $a, b \ne 0$. Determine the mean and
variance for $Y$.

__Solution__. By linearity of expectation,

$$
\E{Y} = a + b \E{X} = a + b \mu
$$

and

$$
\Var{Y} = \Var{a} + b^2 \Var{X} = 0 + b^2 \sigma^2 = b^2 \sigma^2.
$$

--------------------------------------------------------------------------------------------
### 2.9.

__Problem__. Determine the mean and variance for the probability mass function

$$
p(k) = \frac{2 (n-k)}{n (n-1)}
$$

for $k = 1, 2, \ldots, n$.

__Solution__. The mean of $k$ is

$$
\E{k}
= \sum_{k=1}^n \frac{2 k (n-k)}{n (n-1)}
= \frac{2}{n (n-1)} \sum_{k=1}^n k n - k^2 \\
= \frac{2}{n (n-1)} \left( \frac{n^2(n+1)}{2} - \frac{n (n+1) (2n + 1)}{6} \right)
= \frac{n+1}{3}
$$

The second-moment of $k$ is

$$
\E{k^2}
= \sum_{k=1}^n \frac{2 k^2 (n-k)}{n (n-1)}
= \frac{2}{n (n-1)} \sum_{k=1}^n k^2 n - k^3 \\
= \frac{2}{n (n-1)} \left( \frac{n^2 (n+1) (2n + 1)}{6} - \frac{n^2 (n+1)^2}{4}\right) \\
= \frac{n(n+1)}{6}
$$

Therefore, the variance of $k$ is

$$
\Var{k} = \E{k^2} - \E{k}^2
= \frac{n(n+1)}{6} - \frac{(n+1)^2}{9}
= \frac{(n+1)(n-2)}{18}
$$

--------------------------------------------------------------------------------------------
### 2.10.

__Problem__. Random variables $X$ and $Y$ are independent and have the probability mass
functions

$$
p_X(0) = \frac{1}{2}, p_X(3) = \frac{1}{2},
$$

and

$$
p_Y(1) = \frac{1}{6}, p_Y(2) = \frac{1}{3},  p_Y(3) = \frac{1}{2}.
$$

Determine the probability mass function of the sum $Z = X + Y$.

__Solution__. Observe that each possible ordered pair $(X, Y)$ yields a unique value for
$Z$. Therefore, the probability mass function of $Z$ is given by

$$
p_Z(z) = p_X(x) p_Y(y)
$$

because $X$ and $Y$ are independent. Enumerating the ordered pairs $(X, Y)$ and computing
$Z = X + Y$, we find that

$$
\begin{array}{ll}
(0, 1): & p_Z(1) = 1/12 \\
(0, 2): & p_Z(2) = 1/6 \\
(0, 3): & p_Z(3) = 1/4 \\
(3, 1): & p_Z(4) = 1/4 \\
(3, 2): & p_Z(5) = 1/4 \\
(3, 3): & p_Z(6) = 1/4
\end{array}
$$

--------------------------------------------------------------------------------------------
### 2.11.

__Problem__. Random variables $U$ and $V$ are independent and have the probability mass
functions

$$
p_U(0) = \frac{1}{3}, p_U(1) = \frac{1}{3}, p_U(2) = \frac{1}{3}
$$

and

$$
p_V(1) = \frac{1}{2}, p_V(2) = \frac{1}{2}.
$$

Determine the probability mass function of the sum $W = U + V$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 2.12.

__Problem__. Let $U$, $V$, and $W$ be independent random variables with equal variances
$\sigma^2$. Define $X = U + W$ and $Y = V - W$. Find the covariance between $X$ and $Y$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 2.13.

__Problem__. Let $X$ and $Y$ be independent random variables each with the uniform
probability density function

$$
f(x) = \left\{
\begin{array}{ll}
1 & \textrm{for $0 < x < 1$}, \\
0 & \textrm{elsewhere}.
\end{array}
\right.
$$

Find thye joint probability density function of $U$ and $V$, where $U = \max(X, Y)$ and
$V= \min(X, Y)$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 2.x.

__Problem__. TODO

__Solution__. TODO

--------------------------------------------------------------------------------------------
