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

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 2.3.

__Problem__. A population having $N$ distinct elements is samples with replacement. Because
of repetitions, a random sample of size $r$ may contain fewer than $r$ distinct elements.
Let $S_r$ be the sample size necessary to get $r$ distinct elements. Show that

$$
\E{S_r} = N \left( \frac{1}{N} + \frac{1}{N-1} + \cdots + \frac{1}{N - r + 1} \right).
$$

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 2.4.

A fair coin is tossed until the first time that the same side appears twice in succession.
Let $N$ be the number of tosses required.

#### 2.4.a.

__Problem__. Determine the probability mass function for $N$.

__Solution__. TODO

#### 2.4.b.

__Problem__. Let $A$ be the event that $N$ is even and $B$ be the event that $N \le 6$.
Evaluate $\Pr{A}$, $\Pr{B}$, and $\Pr{AB}$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 2.5.

Two players, $A$ and $B$, take turns on a gambling machine until one of them scores a
success, the first to do so being the winner. Their probabilities for success on a single
play are $p$ for $A$ and $q$ for $B$, and successive plays are independent.

#### 2.5.a.

__Problem__. Determine the probability that $A$ wins the contest given that $A$ plays first.

__Solution__. TODO

#### 2.5.b.

__Problem__. Determine the mean number of plays required, given that $A$ wins.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 2.6.

__Problem__. A pair of dice is tossed. If the two outcomes are equal, the dice are tossed
again, and the process repeated. If the dice are unequal, their sum is recorded. Determine
the probability mass function for the sum.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 2.7.

__Problem__. Let $U$ and $W$ be jointly distributed random variables. Show that $U$ and $W$
are independent if

$$
\Pr{U > u \textrm{ and } W > w} = \Pr{U > u} \Pr{W > w}
$$

for all $u, w$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 2.8.

__Problem__. Suppose $X$ is a random variable with finite mean $\mu$ and variance
$\sigma^2$, and $Y = a + bX$ for certain constantys $a, b \ne 0$. Determine the mean and
variance for $Y$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 2.9.

__Problem__. Determine the mean and variance for the probability mass function

$$
p(k) = \frac{2 (n-k)}{n (n-1)}
$$

for $k = 1, 2, \ldots, n$.

__Solution__. TODO

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

__Solution__. TODO

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
