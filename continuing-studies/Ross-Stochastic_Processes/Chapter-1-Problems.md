Stochastic Processes (Ross): Problems
=====================================

--------------------------------------------------------------------------------------------
## 0. Notation

* $\newcommand{\Pr}[1]{{\mathbb{P}\left[{#1}\right]}}$
  Probability of event $E$: $\Pr{E}$

* $\newcommand{\1}[1]{{\mathbf{1}_{\left\{{#1}\right\}}}}$
  Indicator for event $E$: $\1{E}$

* $\newcommand{\p}[1]{{p\left({#1}\right)}}$
  Probability density (or mass) function for a random variable $X$: $\p{x}$

* $\newcommand{\tail}[1]{\overline{#1}}$
  Probability that random variable $X$ is greater than $x$: $\tail{F}(x) = \Pr{X \ge x}$

* $\newcommand{\E}[1]{{\mathbb{E}\left[{#1}\right]}}$
  Expected value of $X$: $\E{X}$

* $\newcommand{\Esub}[2]{\mathbb{E}_{#1}\left[{#2}\right]}$
  Expected value of $X$ with respect to random variable $Y$: $\Esub{Y}{X}$

* $\newcommand{\var}[1]{{\operatorname{Var}}{\left(#1\right)}}$
  Variance of $X$: $\var{X}$

* $\newcommand{\cov}[2]{{\operatorname{Cov}}{\left[#1, #2\right]}}$
  Covariance of $X$ and $Y$: $\cov{X}{Y}$

--------------------------------------------------------------------------------------------
### 1.1.

__Problem__. Let $N$ denote a nonnegative integer-valued random variable. Show that

$$
\E{N} = \sum_{k=1}^\infty \Pr{N \ge k} = \sum_{k=0}^\infty \Pr{N > k}.
$$

In general show that if $X$ is nonnegative with distribution $F$, then

$$
\E{X} = \int_0^\infty \overline{F}(x) dx
$$

and

$$
\E{X^n} = \int_0^\infty n x^{n-1} \bar{F}(x) dx
$$

__Solution__. For the random variable $N$, we have

$$
\begin{align}
\E{N}
&= \sum_{j=0}^\infty j \Pr{N = j} = \sum_{j=1}^\infty j \Pr{N = j} \\
&= \sum_{j=1}^\infty \left( \sum_{k=1}^j 1 \right) \Pr{N = j}
 = \sum_{j=1}^\infty \sum_{k=1}^j \Pr{N = j} \\
&= \sum_{k=1}^\infty \sum_{j=k}^\infty \Pr{N = j} \\
&= \sum_{k=1}^\infty \Pr{N \ge k} \\
&= \sum_{k=0}^\infty \Pr{N \ge k + 1} \\
&= \sum_{k=0}^\infty \Pr{N > k}. \\
\end{align}
$$

For the random variable $X$, we have

$$
\begin{align}
\E{X}
&= \int_0^\infty dy \ y \ p(y) \\
&= \int_0^\infty dy \left( \int_0^y dx \right) \ p(y)
 = \int_0^\infty dy \int_0^y dx \ p(y) \\
&= \int_0^\infty dx \int_x^\infty dy \ p(y) \\
&= \int_0^\infty dx \ \tail{F}(x)
\end{align}
$$

To compute $\E{X^n}$, let $Z = X^n$. Then

$$
\begin{align}
\E{Z}
&= \int_0^\infty \tail{F_Z}(z) \ dz \\
&= \int_0^\infty \Pr{Z \ge z} \ dz \\
&= \int_0^\infty \Pr{X \ge z^{1/n}} \ dz \\
&= \int_0^\infty \Pr{X \ge x} \ n x^{n-1} \ dx \\
&= \int_0^\infty n x^{n-1} \ \tail{F}(x) \ dx
\end{align}
$$

--------------------------------------------------------------------------------------------
### 1.2.

__Problem__. If $X$ is a continuous random variable having distribution $F$, show that

(a) $F(X)$ is uniformly distributed over $(0, 1)$;

(b) if $U$ is a uniform $(0, 1)$ random variable, then $F^{-1}(U)$ has distribution $F$,
    where $F^{-1}$(x) is that value of $y$ such that $F(y) = x$.

__Solution__.

(a) Let $Y = F(X)$. Then

$$
\begin{align}
\Pr{Y \le y}
&= \Pr{F(X) \le y} \\
&= \Pr{X \le F^{-1}(y)} \\
&= F(F^{-1}(y)) \\\
&= y
\end{align}
$$

when $0 \le y \le 1$, Clearly, $\Pr{Y \le y} = 0$ for $y < 0$, and $\Pr{Y \le y} = 1$ for
$y > 1$. Therefore, $Y$ is uniformly distribution over $(0, 1).$

(b) Let $Z = F^{-1}(U)$. Then

$$
\begin{align}
\Pr{Z \le z}
&= \Pr{F^{-1}(U) \le z} \\
&= \Pr{U \le F(z)} \\
&= F(z)
\end{align}
$$

where the last equality follows because $U$ is a uniform $(0, 1)$ random variable.
Therefore, $Z \sim F(z)$.

--------------------------------------------------------------------------------------------
### 1.3.

__Problem__. Let $X_n$ denote a binomial random variable with parameters $(n, p_n)$,
$n \ge 1$. If $n p_n \rightarrow \lambda$ as $n \rightarrow \infty$, show that

$$
\Pr{X_n = i} \rightarrow \frac{e^{-\lambda} \lambda^i}{i!}
$$

as $n \rightarrow \infty$.

__Solution__. Since $X_n \sim B(n, p)$,

$$
\Pr{X_n = i} = {n \choose i} p^i (1-p)^{n-i}.
$$

Recall that Stirling's approximation provides bounds the factorial function:

$$
\sqrt{2 \pi n} \left( \frac{n}{e} \right)^n e^{1 / (12n+1)}
\le n!
\le \sqrt{2 \pi n} \left( \frac{n}{e} \right)^n e^{1 / 12n}.
$$

Thus,

$$
\frac{e^{-i}}{i!}
  \sqrt{\frac{n}{n-i}}
  \left( \frac{n}{n-i} \right)^{n-i}
  e^{(1/(n+1) - 1/(n-i) / 12}
  n^i p^i (1-p)^{n-i}
\le \Pr{X_n = i}
\le \frac{e^{-i}}{i!}
  \sqrt{\frac{n}{n-i}}
  \left( \frac{n}{n-i} \right)^{n-i}
  e^{(1/n - 1/(n-i+1) / 12}
  n^i p^i (1-p)^{n-i}.
$$

Observe that as $n \rightarrow \infty$,

$$
\begin{align}
\sqrt{\frac{n}{n-i}}
&\rightarrow 1
\\
\left( \frac{n}{n-i} \right)^{n-i}
= \left(1 + \frac{i}{n-i} \right)^{n-i}
&\rightarrow e^i
\\
\exp\left( \frac{1}{12} \left( \frac{1}{n+1} - \frac{1}{n-i} \right) \right)
= \exp\left( -\frac{i+1}{12 (n+1) (n-i)} \right)
&\rightarrow 1
\\
\exp\left( \frac{1}{12} \left( \frac{1}{n} - \frac{1}{n-i+1} \right) \right)
= \exp\left( -\frac{i-1}{12 n (n-i+1)} \right)
&\rightarrow 1
\\
(1 - p)^{n-i}
= \left( 1 - \frac{\lambda}{n} \right)^{n-i}
= \left( 1 - \frac{\lambda}{n} \right)^n \left( 1 - \frac{\lambda}{n} \right)^{-i}
&\rightarrow e^{-\lambda}.
\end{align}
$$

Combining these results, substituting $\lambda = np$, and simplifying, we find that the
upper and lower bounds on $\Pr{X_n = i}$ both converge to $e^{-\lambda} \lambda^i / i!.$
Therefore, the Squeeze Theorem for sequences implies the desired result.

--------------------------------------------------------------------------------------------
### 1.4.

__Problem__. Compute the mean and variance of a binomial random variable with parameters
$n$ and $p$.

__Solution__. Let $X \sim B(n, p).$ Then

$$
\begin{align}
\E{X}
&= \sum_{k=0}^n k {n \choose k} p^k (1-p)^{n-k} \\
&= \sum_{k=1}^n k {n \choose k} p^k (1-p)^{n-k} \\
&= \sum_{k=1}^n n {n-1 \choose k-1} p^k (1-p)^{n-k} \\
&= np \sum_{k=1}^n {n-1 \choose k-1} p^{k-1} (1-p)^{n-k} \\
&= np \sum_{k=0}^{n-1} {n-1 \choose k} p^k (1-p)^{(n-1)-k} \\
&= np
\end{align}
$$

where the last equality follows because the sum reduces to $(p + (1-p))^{n-1} = 1$ by the
binomial theorem.

To compute the variance of $X$, it is convenient to express $\var{X}$ in the following
manner:

$$
\var{X}
= \E{X^2} - \E{X}^2
= \E{X(X-1)} + \E{X} - \E{X}^2.
$$

Reasoning as we did when computing $\E{X}$,

$$
\begin{align}
\E{X(X-1)}
&= \sum_{k=0}^n k (k-1) {n \choose k} p^k (1-p)^{n-k} \\
&= \sum_{k=2}^n k (k-1) {n \choose k} p^k (1-p)^{n-k} \\
&= \sum_{k=2}^n n (n-1) {n-2 \choose k-2} p^k (1-p)^{n-k} \\
&= n(n-1) p^2 \sum_{k=2}^n {n-2 \choose k-2} p^{k-2} (1-p)^{n-k} \\
&= n(n-1) p^2 \sum_{k=0}^{n-2} {n-2 \choose k} p^k (1-p)^{(n-2)-k} \\
&= n(n-1) p^2.
\end{align}
$$

Thus,

$$
\var{X}
= n(n-1)p^2 + np - (np)^2
= -np^2 + np
= np(1-p).
$$

--------------------------------------------------------------------------------------------
### 1.5.

Suppose that $n$ independent trials -- each of which results in either outcome
$1, 2, \ldots, r$ with respective probabilities $p_1, p_2, \ldots, p,$ -- are performed,
$\sum_1^r p_i = 1.$ Let $N_i$ denote the number of trials resulting in outcome $i$.

#### 1.5..

__Problem__. Compute the joint distribution of $N_1, \ldots, N_r.$ This is called the
_multinomial_ distribution.

__Solution__. TODO

#### 1.5.b.

__Problem__. Compute $\cov{N_i}{N_j}$.

__Solution__. TODO

#### 1.5.c.

__Problem__. Compute the mean and variance of the number of outcomes that do not occur.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 1.6.

Let $X_1, X_2, \ldots$ be independent identically distributed continuous random variables.
We say that a record occurs at time $n,$ $n > 0$ and has value $X_n$ if
$X_n > \max(X_1, \ldots, X_{n-1})$, where $X_0 = \infty.$

#### 1.6.a.

__Problem__. Let $N_n$ denote the total number of records that have occurred up to (and
including) time $n.$ Compute $\E{N_n}$ and $\var{N_N}.$

__Solution__. TODO

#### 1.6.b.

__Problem__. Let $T = \min\{ n: n < 1 \textrm{ and a record occurs at } n \}.$ Compute
$\Pr{T > n}$ and show that $\Pr{T < \infty} = 1$ and $\E{T} = \infty$.

__Solution__. TODO

#### 1.6.c.

__Problem__. Let $T_y$ denote the time of the first record value greater than $y.$ That is,

$$
T_y = \min\{ n : X_n > y \}.
$$

Show that $T_y$ is independent of $X_{T_y}.$ That is, the time of the first value greater
than $y$ is independent of that value. (It may seem more intuitive if you turn this last
statment around.)

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 1.7.

__Problem__. Let $X$ denote the number of white balls selected when $k$ balls are chosen at
random from an urn containing $n$ white and $m$ black balls. Compute $\E{X}$ and $\var{X}$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 1.8.

__Problem__. Let $X_1$ and $X_2$ be independent Poisson random variables with means
$\lambda_1$ and $\lambda_2.$

#### 1.8.a.

__Problem__. Find the distribution of $X_1 + X_2.$

__Solution__. TODO

#### 1.8.b.

__Problem__. Compute the conditional distribution of $X_1$ given that $X_1 + X_2 = n.$

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 1.9.

__Problem__. A round-robin tournament of $n$ contestants is one in which each of the
$n \choose 2$ pairs of contestants play each other exactly once, with the outcome of any
play being that one of the contestants wins and the other loses. Suppose the players are
initially numberd $1, 2, \ldots, n.$ The permutation $i_1, \ldots, i_n$ is called a
Hamiltonian permutation if $i_1$ beats $i_2$, $i_2$ beats $i_3$, $\ldots,$ and $i_{n-1}$
beats $i_n.$ Show that there is an outcome of the round-robin for which the number of
Hamiltonians is at least $n! / 2^{n-1}$.

(_Hint_: Use the probabilistic method.)

__Solution__. TODO

* Represent round-robin tournament as a fully-connected graph. Number of edges
  = ${n \choose 2}.$ Assign each node a label $1, 2, \ldots, n.$

* Enumerate the permutations of $1, 2, \ldots, n$.

* With probability 1/2 each represents a win for the player with the lower label.

* Define $X_k$ to be a random variable
equal to $1$ if the $k$-th permutation is Hamiltonian and $0$ otherwise. Then
$X = \sum_{k=1}^{n!} X_k$ is a random variable equal to the number of Hamiltonian
permutations.

* Probability that the path from $i_1, i_2, \ldots, i_n$ consists of all wins for the
  lower label = $1/2^{n-1}$.

* Expectation value of $X$

  $$
  \E{X}
  = \sum_k \E{X_k}
  = \sum_k \frac{1}{2^{n-1}}
  = \frac{n!}{2^{n-1}}
  $$

* Therefore, there exists at least one tournament where the number of Hamiltonians is
  at least $\frac{n!}{2^{n-1}}.$

--------------------------------------------------------------------------------------------
### 1.10.

__Problem__. Consider a round-robin tournament having $n$ contestants, and let $k,$
$k < n,$ be a positive integer such that ${n \choose k} [1 - 1/2^k]^{n-k} < 1.$ Show that
it is possible for the tournament outcome to be such that for ever set of $k$ contestants
there is a contestant who beat every member of this set.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 1.11.

If $X$ is a nonnegative integer-valued random variable then the function $P(z),$ defined
for $|z| \le 1$ by

$$
P(z) = \E{z^x} = \sum_{j=0}^\infty z^j \Pr{X = j},
$$

is called the probability generating function of $X.$

#### 1.11.a.

__Problem__. Show that

$$
\left. \frac{d^k}{dz^k} P(z) \right|_{|z=0} = k! \Pr{X = k}.
$$

__Solution__.

Observe that

$$
\frac{d^k}{dz^k} z^n
= \left\{\begin{array}{ll}
    \frac{n!}{(n-k)!} z^{n-k} & \textrm{for $n \ge k$} \\
                            0 & \textrm{for $n < k$} \\
 \end{array}\right.,
$$

which implies that

$$
\left. \frac{d^k}{dz^k} z^n \right|_{z=0}
= \left\{\begin{array}{ll}
     0 & \textrm{for $n > k$} \\
    k! & \textrm{for $n = k$} \\
     0 & \textrm{for $n < k$} \\
 \end{array}\right.
$$

Thus,

$$
\left. \frac{d^k}{dz^k} P(z) \right|_{|z=0}
= \left. \sum_{j=k}^\infty \frac{j!}{(j-k)!} z^{j-k} \Pr{X = j} \right|_{|z=0}
= k! \Pr{X = k}.
$$

#### 1.11.b.

__Problem__. With $0$ being considered even, show that

$$
\Pr{X \textrm{ is even}} = \frac{P(-1) + P(1)}{2}.
$$

__Solution__.

Observe that

$$
\Pr{X \textrm{ is even}} = \sum_{j=0}^\infty \Pr{X = 2j},
$$

which implies that

$$
\begin{align}
\Pr{X \textrm{ is even}}
&= \left. \sum_{j=0}^\infty z^{2j} \Pr{X = 2j} \right|_{z=1} \\
&= \frac{1}{2} \left(
       \left. \sum_{j=0}^\infty z^{j} \Pr{X = j} \right|_{z=-1}
     + \left. \sum_{j=0}^\infty z^{j} \Pr{X = j} \right|_{z=1}
   \right) \\
&= \frac{P(-1) + P(1)}{2},
\end{align}
$$

where the second equality follows because $1^j = (-1)^j$ for $j$ even and $1^j = -(-1)^j$
for $j$ odd.

#### 1.11.c.

__Problem__. If $X$ is binomial with parameters $n$ and $p,$ show that

$$
\Pr{X \textrm{ is even}} = \frac{1 + (1 - 2p)^n}{2}
$$

__Solution__.

If $X$ is binomial with parameters $n$ and $p,$

$$
\begin{align}
P(z)
&= \sum_{j=0}^n z^j {n \choose j} p^j (1-p)^{n-j} \\
&= \sum_{j=0}^n {n \choose j} (zp)^j (1-p)^{n-j} \\
&= (1 + (z-1)p)^n
\end{align}
$$

Thus,

$$
\Pr{X \textrm{ is even}}
= \frac{P(1) + P(-1)}{2}
= \frac{1 + (1 - 2p)^n}{2}.
$$

#### 1.11.d.

__Problem__. If $X$ is Poisson with mean $\lambda,$ show that

$$
\Pr{X \textrm{ is even}} = \frac{1 + e^{-2\lambda}}{2}
$$

__Solution__.

If $X$ is Poisson with mean $\lambda,$

$$
\begin{align}
P(z)
&= \sum_{j=0}^\infty z^j \frac{\lambda^j e^{-\lambda}}{j!} \\
&= e^{-\lambda} \sum_{j=0}^\infty \frac{(z\lambda)^j}{j!} \\
&= e^{(z-1) \lambda}
\end{align}
$$

Thus,

$$
\Pr{X \textrm{ is even}}
= \frac{P(1) + P(-1)}{2}
= \frac{1 + e^{-2 \lambda}}{2}.
$$

#### 1.11.e.

__Problem__. If $X$ is geometric with parameter $p,$ show that

$$
\Pr{X \textrm{ is even}} = \frac{1 -p}{2-p}
$$

__Solution__.

If $X$ is geometric with parameter $p,$

$$
\begin{align}
P(z)
&= \sum_{j=1}^\infty z^j p (1-p)^{j-1} \\
&= z p \sum_{j=0}^\infty (z(1-p))^j \\
&= \frac{z p}{1 - z(1-p)}
\end{align}
$$

Thus,

$$
\begin{align}
\Pr{X \textrm{ is even}}
&= \frac{P(1) + P(-1)}{2} \\
&= \frac{1}{2} \left( \frac{p}{1 - (1 - p)} + \frac{-p}{1 + (1 - p)} \right) \\
&= \frac{1}{2} \left( 1 - \frac{p}{2 - p} \right) \\
&= \frac{1 - p}{2 - p}.
\end{align}
$$

#### 1.11.f.

__Problem__. If $X$ is a negative binomial random variable with parameters $r$ and p,$
show that

$$
\Pr{X \textrm{ is even}}
= \frac{1}{2}
  \left[
    1 + (-1)^r \left( \frac{p}{2-p} \right)^r
  \right]
$$

__Solution__.

If $X$ is a negative binomial random variable with paramters $r$ and $p,$

$$
\begin{align}
P(z)
&= \sum_{j=r}^\infty z^j {n-1 \choose j-1} p^j (1 - p)^{n-j} \\
&= \sum_{j=r}^\infty {n-1 \choose j-1} (zp)^j (1 - p)^{n-j} \\
&= \left( \frac{zp}{1 - (1-p)z} \right)^r
\end{align}
$$

Thus,

$$
\begin{align}
\Pr{X \textrm{ is even}}
&= \frac{P(1) + P(-1)}{2} \\
&= \frac{1}{2} \left[
     \left( \frac{p}{1 - (1 - p)} \right)^r
   + \left( \frac{-p}{1 + (1 - p)} \right)^r
   \right] \\
&= \frac{1}{2} \left[
     1
   + (-1)^r \left( \frac{p}{2 - p} \right)^r
   \right]. \\
\end{align}
$$

--------------------------------------------------------------------------------------------
### 1.12.

__Problem__. If $\Pr{0 \le X \le 1} = 1,$, show that

$$
\var{X} \le a^2 / 4.
$$

__Solution__. Let $g(t) = \E{(X - t)^2}.$ Since
$g'(t) = - 2 \E{X} + 2\E{t} = -2 \E{X} + 2 t$ and $g''(t) = 2 > 0,$ we see that $g$ is
minimized when $t = \E{X}$ and has a minimum value equal to $\var{X}.$

Next, consider $g(a/2).$ Observe that

$$
\left| X - \frac{a}{2} \right|
= \left| \frac{X}{2} + \frac{X-a}{2} \right|
\le \left| \frac{X}{2} \right| + \left| \frac{X-a}{2} \right|
= \frac{X}{2} + \frac{a-X}{2}
= \frac{a}{2}
$$

where the inequality follows from the triangle inequality and the second to last equality
follows because $X \le a$. Thus, $g(a/2)$ is bounded above:

$$
g(a/2)
= \E{\left( X - \frac{a}{2} \right)^2}
= \E{\left| X - \frac{a}{2} \right|^2}
\le \E{\left( \frac{a}{2} \right)^2}
= \frac{a^2}{4}.
$$

Combining these two results yields the desired bound: $\var{X} \le g(a/2) \le a^2/4.$

--------------------------------------------------------------------------------------------
### 1.13.

Consider the following method of shuffling a deck of $n$ playing cards, numbers $1$ through
$n.$ Take the top card from the deck and then replace it so that it is equally likely to be
put under exactly $k$ cards, for $k = 0, 1, \ldots, n-1.$ Continue doing this operation
until the card that was initially on the bottom of the deck is now on top. Then do it one
more time and stop.

#### 1.13.a.

__Problem__. Suppose that at some point there are $k$ cards beneath the one that was
originally on the bottom of the deck. Given this set of $k$ cards, explain why each of the
possible $k!$ orderings is equally likely to be the ordering of the last $k$ cards.

__Solution__. TODO

#### 1.13.b.

__Problem__. Conclude that the final ordering of the deck is equally likely to be any of
the $n!$ possible orderings.

__Solution__. TODO

#### 1.13.c.

__Problem__. Find the expected number of times the shuffling operation is performed.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 1.14.

__Problem__. A fair die is continually rolled until an even number has appeared on $10$
distinct rolls. Let $X_i$ denote the number of rolls that land on side $i$. Determine:

(a) $\E{X_1}.$

(b) $\E{X_2}.$

(c) the probability mass function of $X_1.$

(d) the probability mass function of $X_2.$

__Solution__. Let the randon variable $N$ be the number of rolls that have occurred when
the $10$-th even number appears. We can compute the desired quantities by conditioning on
$N$. First, observe that for $n \ge 10$

$$
\Pr{N = n}
= \frac{1}{2} {n-1 \choose 9} \left( \frac{1}{2} \right)^9 \left( \frac{1}{2} \right)^{n-10}
= {n-1 \choose 9} \left( \frac{1}{2} \right)^n
$$

because there is a $1/2$ probability that the last roll is even, $n-1 \choose 9$ ways to
choose the times of the other even rolls, a $1/2$ probability that an even roll occurred
at those times, and a $1/2$ probability that an odd roll occurred at all other times.
Conditioned on the event $N = n$, the the random variable $X_i = k$ has a binomial
distribution with parameters $n$ and $p$ dependent on the whether $i$ is even or odd:

$$
\Pr{X_i = k | N = n}
= \left\{\begin{array}{cl}
    {n-10 \choose k} \left( \frac{1}{3} \right)^k \left( \frac{2}{3} \right)^{n-10-k}
    & \textrm{for $i$ odd} \\
    {10 \choose k} \left( \frac{1}{3} \right)^k \left( \frac{2}{3} \right)^{10-k}
    & \textrm{for $i$ even} \\
  \end{array}\right.
$$

The following identities are useful for the following calculations:

$$
\begin{align}
\frac{d^k}{dx^k} \left( \frac{1}{1 - x} \right)
&= \sum_{n=0}^\infty n (n-1) \cdots (n-k+1) x^{n-k} \\
&= \sum_{n=k}^\infty n (n-1) \cdots (n-k+1) x^{n-k} \\
&= \sum_{n=0}^\infty (n+k) (n+k-1) \cdots (n+1) x^n \\
\end{align}
$$

and

$$
\frac{d^k}{dx^k} \left( \frac{1}{1 - x} \right)
= \frac{k!}{(1-x)^{k+1}}.
$$

(a)

$$
\begin{align}
\E{X_1}
&= \sum_{n=10}^\infty \E{X_1 | N = n} \Pr{N = n} \\
&= \sum_{n=10}^\infty \left( \frac{n-10}{3} \right) \Pr{N = n} \\
&= \sum_{n=11}^\infty \left( \frac{n-10}{3} \right) \Pr{N = n} \\
&= \sum_{n=0}^\infty \left( \frac{n+1}{3} \right) \Pr{N = n+11} \\
&= \sum_{n=0}^\infty
     {n+10 \choose 9} \left( \frac{n+1}{3} \right) \left( \frac{1}{2} \right)^{n+11} \\
&= \frac{1}{3 \cdot 2^{11} \cdot 9!} \sum_{n=0}^\infty
     (n+10) (n+9) \cdots (n+1) \left( \frac{1}{2} \right)^n \\
&= \frac{1}{3 \cdot 2^{11} \cdot 9!} \left( \frac{10!}{(1 - (1/2))^{11}} \right) \\
&= \frac{10}{3}
\end{align}
$$

(b)

$$
\begin{align}
\E{X_2}
&= \sum_{n=10}^\infty \E{X_2 | N = n} \Pr{N = n} \\
&= \sum_{n=10}^\infty \left( \frac{10}{3} \right) \Pr{N = n} \\
&= \frac{10}{3} \sum_{n=10}^\infty \Pr{N = n} \\
&= \frac{10}{3}
\end{align}
$$

where the last line follows because $\Pr{N = n}$ is a probability mass function. We can
verify that the sum over $\Pr{N = n}$ equals 1:

$$
\begin{align}
\sum_{n=10}^\infty \Pr{N = n}
&= \sum_{n=10}^\infty {n-1 \choose 9} \left( \frac{1}{2} \right)^n \\
&= \sum_{n=0}^\infty {n+9 \choose 9} \left( \frac{1}{2} \right)^{n+10} \\
&= \frac{1}{9! \cdot 2^{10}} \sum_{n=0}^\infty (n+9) (n+8) \cdots (n+1) \left( \frac{1}{2} \right)^n \\
&= \frac{1}{9! \cdot 2^{10}} \left( \frac{9!}{(1 - (1/2))^{10}} \right) \\
&= 1.
\end{align}
$$

(c) For $k \ge 0$,

$$
\begin{align}
\Pr{X_1 = k}
&= \sum_{n=10}^\infty \Pr{X_1 = k | N = n} \Pr{N = n} \\
&= \sum_{n=10}^\infty
     {n-10 \choose k} \left( \frac{1}{3} \right)^k \left( \frac{2}{3} \right)^{n-10-k}
     {n-1 \choose 9} \left( \frac{1}{2} \right)^n \\
&= \frac{1}{9! k!} \left( \frac{1}{2} \right)^{k+10}
   \sum_{n=10}^\infty \frac{(n-1)!}{(n-k-10)!} \left( \frac{1}{3} \right)^{n-10} \\
&= \frac{1}{9! k!} \left( \frac{1}{2} \right)^{k+10}
   \sum_{n=0}^\infty \frac{(n+9)!}{(n-k)!} \left( \frac{1}{3} \right)^n \\
&= \frac{1}{9! k!} \left( \frac{1}{2} \right)^{k+10}
   \sum_{n=0}^\infty (n+9) (n+8) \cdots (n-k+1) \left( \frac{1}{3} \right)^n  \\
&= \frac{1}{9! k!} \left( \frac{1}{2} \right)^{k+10}
   \sum_{n=k}^\infty (n+9) (n+8) \cdots (n-k+1) \left( \frac{1}{3} \right)^n  \\
&= \frac{1}{9! k!} \left( \frac{1}{2} \right)^{k+10}
   \sum_{n=0}^\infty (n+k+9) (n+k+8) \cdots (n+1) \left( \frac{1}{3} \right)^{n+k}  \\
&= \frac{1}{9! k!} \left( \frac{1}{2} \right)^{10} \left( \frac{1}{6} \right)^k \
   \sum_{n=0}^\infty (n+k+9) (n+k+8) \cdots (n+1) \left( \frac{1}{3} \right)^n  \\
&= \frac{1}{9! k!} \left( \frac{1}{2} \right)^{10} \left( \frac{1}{6} \right)^k \
   \left. \frac{d^{k+9}}{dx^{k+9}} \left( \frac{1}{1-x} \right) \right|_{x=1/3} \\
&= \frac{1}{9! k!} \left( \frac{1}{2} \right)^{10} \left( \frac{1}{6} \right)^k \
   \left( \frac{(k+9)!}{(1 - (1/3))^{k+10}} \right) \\
&= {k+9 \choose 9} \left( \frac{3}{4} \right)^{10} \left( \frac{1}{4} \right)^k
\end{align}
$$

(d) For $0 \le k \le 10$,

$$
\begin{align}
\Pr{X_2 = k}
&= \sum_{n=10}^\infty \Pr{X_2 = k | N = n} \Pr{N = n} \\
&= \sum_{n=10}^\infty
     {10 \choose k} \left( \frac{1}{3} \right)^k \left( \frac{2}{3} \right)^{10-k}
     {n-1 \choose 9} \left( \frac{1}{2} \right)^n \\
&= {10 \choose k} \left( \frac{1}{3} \right)^k \left( \frac{2}{3} \right)^{10-k}
   \sum_{n=10}^\infty {n-1 \choose 9} \left( \frac{1}{2} \right)^n \\
&= {10 \choose k} \left( \frac{1}{3} \right)^k \left( \frac{2}{3} \right)^{10-k}
   \sum_{n=0}^\infty {n+9 \choose 9} \left( \frac{1}{2} \right)^{n+10} \\
&= \frac{1}{9!} \left( \frac{1}{2} \right)^{10}
   {10 \choose k} \left( \frac{1}{3} \right)^k \left( \frac{2}{3} \right)^{10-k}
   \sum_{n=0}^\infty (n+9) (n+8) \cdots (n+1) \left( \frac{1}{2} \right)^n \\
&= \frac{1}{9!} \left( \frac{1}{2} \right)^{10}
   {10 \choose k} \left( \frac{1}{3} \right)^k \left( \frac{2}{3} \right)^{10-k}
   \left. \frac{d^9}{dx^9} \left( \frac{1}{1-x} \right) \right|_{x=1/2} \\
&= \frac{1}{9!} \left( \frac{1}{2} \right)^{10}
   {10 \choose k} \left( \frac{1}{3} \right)^k \left( \frac{2}{3} \right)^{10-k}
   \left( \frac{9!}{(1 - (1/2))^{10}} \right) \\
&= {10 \choose k} \left( \frac{1}{3} \right)^k \left( \frac{2}{3} \right)^{10-k}.
\end{align}
$$

In other words, $X_2$ has a binomial distribution with parameters $n=10$ and $p=1/3$.
The same analysis shows that $X_4$ and $X_6$ also have the same distribution.

The intuition behind this result is that there are exactly $10$ even rolls, so the
probability that $k$ of them are equal to $2$ is precisely the binomial distribution for
$10$ rolls with a probability of $1/3$ that $2$ is the outcome of each individual roll.

--------------------------------------------------------------------------------------------
### 1.15.

Let $F$ be a continuous distribution function and let $U$ be a uniform $(0, 1)$ random
variable.

#### 1.15.a.

__Problem__. If $X = F^{-1}(U),$ show that $X$ has distribution function $F.$

__Solution__. TODO

#### 1.15.b.

__Problem__. Show that $-\log(U)$ is an exponential random variable with mean $1.$

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 1.16.

__Problem__. Let $f(x)$ and $g(x)$ be probability density functions, and suppose that for
some constant $c,$ $f(x) \le c g(x)$ for all $x.$. Suppose we can generate random variables
having density function $g,$ and consider the following algorithm.

__Step 1:__ Generate $Y,$ a random variable having density $g.$

__Step 2:__ Generate $U,$ a uniform $(0, 1)$ random variable.

__Step 3:__ If $U \le \frac{f(Y)}{c g(Y)}$ set $X = Y.$ Otherwise, go back to Step 1.

Assuming that successively generated random variables are independent, show that:

(a) $X$ has density function $f.$.

(b) the number of iterations of the algorithm needed to generate $X$ is a geometric random
    variable with mean $c.$

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 1.17.

__Problem__. Let $X_1, \ldots, X_n$ be independent and identically distributed continuous
random variables having distribution $F.$ Let $X_{i,n}$ denote the $i$th smallest of
$X_1, \ldots, X_n$ and let $F_{i,n}$ be its distribution function. Show that:

(a) $F_{i,n}(x) = F(x) F_{i-1,n-1}(x) + \tail{F}(x) F_{i,n-1}(x)$

(b) $F_{i,n-1}(x) = \frac{i}{n} F_{i+1,n}(x) + \frac{n-i}{n} F_{i,n}(x).$

(_Hints_: For part (a) condition on whether $X_n \le x,$ and for part (b) start by
conditioning on whether $X_n$ is among the $i$ smallest of $X_1, \ldots, X_n.$)

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 1.18.

__Problem__. A coin, which lands on heads with probability $p,$ is continually flipped.
Compute the expected number of flips that are made until a string of $r$ heads in a row
is obtained.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 1.19.

An urn contains $a$ white and $b$ black balls. After a ball is drawn, it is returned to the
urn if it is white; but if it is black, it is replacecd by a white ball from another urn.
Let $M_n$ denote the expected number of white balls in the urn after the foregoing operation
has been repeated $n$ times.

#### 1.19.a.

__Problem__. Derive the recursive equation

$$
M_{n+1} = \left( 1 - \frac{1}{a+b} \right) M_n + 1.
$$

__Solution__. TODO

#### 1.19.b.

__Problem__. Use part (a) to prove that

$$
M_n = a + b - b \left( 1 - \frac{1}{a + b} \right)^n.
$$

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 1.22.

__Problem__. The conditional variance of $X,$ given $Y,$ is defined by

$$
\var{X|Y} = \E{ (X - \E{X|Y})^2 | Y }.
$$

Prove the conditional variance formula; namely,

$$
\var{X} = \E{ \var{X|Y} } + \var{ \E{X|Y} }.
$$

Use this to obtain $\var{X}$ in Example 1.5(B) and check your result by differentiating the
generating function.

__Solution__. Note: throughout this solution, we use the notation $\Esub{Y}{Z}$ and
$\Esub{X|Y}{Z|Y} = \E{Z|Y}$ when it is helpful to clarify the random variable or
conditional random variable that an expectation is taken over.

First, express $(X - \E{X})^2$ as

$$
\begin{align}
(X - \E{X})^2
&= ( (X - \E{X|Y}) + (\E{X|Y} - \E{X}) )^2 \\
&= (X - \E{X|Y})^2 + (\E{X|Y} - \E{X})^2 + 2 (X - \E{X|Y}) (\E{X|Y} - \E{X}).
\end{align}
$$

Next, observe that

$$
\var{X}
= \Esub{X}{ (X - \E{X})^2 }
= \Esub{Y}{ \Esub{X|Y}{ (X - \E{X})^2 | Y } }.
$$

Using linearity of expectation, $\var{X}$ is the sum of the following three parts:

$$
\Esub{Y}{ \Esub{X|Y} { (X - \E{X|Y})^2 | Y } }
= \E{ \var{X | Y} }
$$

$$
\begin{align}
\Esub{Y}{ \Esub{X|Y}{ (\E{X|Y} - \E{X})^2 | Y } }
&= \Esub{Y}{ (\Esub{X|Y}{X|Y} - \E{X})^2 } \\
&= \Esub{Y}{ (\Esub{X|Y}{X|Y} - \Esub{Y}{\Esub{X|Y}{X|Y}})^2 } \\
&= \var{ \Esub{X|Y}{X|Y} } \\
&= \var{ \E{X|Y} } \\
\end{align}
$$

$$
\begin{align}
2 \Esub{Y}{ \Esub{X|Y}{ (X - \E{X|Y}) (\E{X|Y} - \E{X}) | Y } }
&= 2 \Esub{Y}{ (\E{X|Y} - \E{X}) \Esub{X|Y}{ (X - \E{X|Y}) | Y } } \\
&= 2 \Esub{Y}{ (\E{X|Y} - \E{X}) (\E{X|Y} - \E{X|Y}) } \\
&= 0,
\end{align}
$$

where the first equality follows because $(\E{X|Y} - \E{X})$ is independent of $X$
(conditioned on $Y$).

Combining these terms yields the desired result:

$$
\var{X} = \E{\var{X|Y}} + \var{\E{X|Y}}.
$$

Note that throughout the proof, we have used the observation that the taking repeated
conditional expectations with respect to the same random variable is an idempotent
operation. That is,

$$
\Esub{X|Y}{ \Esub{X|Y}{Z|Y} | Y } = \Esub{X|Y}{Z|Y}.
$$

--------------------------------------------------------------------------------------------
### 1.40.

__Problem__. Suppose that $r = 3$ in Example 1.9(C) and find the probability that the leaf
on the ray of size $n_1$ is the last leaf to be visited.

__Solution__. TODO


--------------------------------------------------------------------------------------------
### 1.41.

Consider a star graph consisting of a central vertex and $r$ rays, with one ray consisting
of $m$ vertices and the other $r-1$ all consisting of $n$ vertices. Let $P_r$ denote the
probability that the leaf on the ray of $m$ vertices is the last leaf visited by a particle
that starts at $0$ and at each step is equally likely to move to any of its neighbors.

#### 1.41.a.

__Problem__. Find $P_2.$

__Solution__. TODO

#### 1.41.b.

__Problem__. Express $P_r$ in terms of $P_{r-1}.$

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 1.42.

__Problem__. Let $Y_z, Y_2, \ldots$ be independent and identically distributed with

$$
\begin{align}
\Pr{Y_n = 0} &= \alpha \\
\Pr{Y_n > y} &= (1 - \alpha) e^{-y} \textrm{ for $y > 0$.}\\
\end{align}
$$

Define the random variables $X_n,$ $n \ge 0$ by

$$
\begin{align}
X_0 &= 0 \\
X_{n+1} &= \alpha X_n + Y_{n+1}. \\
\end{align}
$$

Prove that

$$
\begin{align}
\Pr{X_n = 0} &= \alpha^n \\
\Pr{X_n > x} &= (1 - \alpha^n) e^{-x} \textrm{ for $x > 0.$} \\
\end{align}
$$

__Solution__. Consider the moment generating function for $Y_n$:

$$
\begin{align}
\psi_{Y}(t)
&= \E{e^{tY}} \\
&= \alpha e^{0t} + \int_0^\infty (1-\alpha) e^{-y} e^{ty} dy \\
&= \alpha + \frac{1-\alpha}{1 - t} \\
&= \frac{1-\alpha t}{1 - t},
\end{align}
$$

where $t < 1$ (so that the integral in the second line converges).

Observe that

$$
X_n = \sum_{k=1}^n \alpha^{n-k} Y_k,
$$

so the moment generating function for $X_n$ is equal to

$$
\begin{align}
\psi_{X_n}(t)
&= \prod_{k=1}^n \psi_{Y}(\alpha^{n-k} t) \\
&= \prod_{k=1}^n \frac{1 - \alpha^{n-k+1} t}{1 - \alpha^{n-k}t} \\
&= \frac{1 - \alpha^n t}{1 - t}
\end{align}
$$

because (1) the moment generating function of a sum of independent random variables is
equal to the product of the moment generating function of the individual random variables
and (2) the moment generating function of a random variable $aX$ evaluated at $t$ is equal
to the moment generating function for $X$ evaluated at $at.$

Computing the moment generating function the random variable $Z$ with distribution

$$
\begin{align}
\Pr{Z = 0} &= \alpha^n \\
\Pr{Z > z} &= (1 - \alpha^n) e^{-z} \textrm{ for $z > 0$,} \\
\end{align}
$$

we find that

$$
\begin{align}
\psi_{Z}(t)
&= \E{e^{tZ}} \\
&= \alpha^n e^{0t} + \int_0^\infty (1-\alpha^n) e^{-z} e^{tz} dz \\
&= \alpha^n + \frac{1-\alpha^n}{1 - t} \\
&= \frac{1-\alpha^n t}{1 - t},
\end{align}
$$

where $t < 1$. Therefore, by uniqueness of moment generating functions, we can conclude
that $X_n$ and $Z$ have the same distribution, which yields the desired result.

--------------------------------------------------------------------------------------------
### 1.43.

__Problem__. For a nonnegative random variable $X$, show that for $a > 0,$

$$
\Pr{X \ge a} \le \E{X^t} / a^t.
$$

Then use this result to show that $n! \ge (n/e)^n.$

__Solution__. Since $X$ is nonnegative, $\Pr{X \ge a} = \Pr{X^t \ge a^t}$. Markov's
inequality for the random variable $X^t$ implies that $\Pr{X^t \ge a^t} \le \E{X^t} / a^t,$
which yields the desired result.

To show that $n! \ge (n/e)^n$, let $X$ be an exponential random variable with parameter
$\lambda = 1$. Then

$$
\Pr{X \ge n}
= \int_n^\infty e^{-x} dx
= e^{-n}.
$$

Since $X$ is nonnegative, setting $t = n$ in the upper bound on $\Pr{X \ge n}$ yields

$$
\Pr{X \ge n} \le \E{X^n} / {n^n}.
$$

Using the moment generating function to compute $\E{X^n}$:

$$
\begin{align}
\E{X^n}
&= \left. \frac{d^n \psi}{dt^n} \right|_{t=0} \\
&= \left. \frac{d^n}{dt^n} \left( \frac{1}{1 - t} \right) \right|_{t=0} \\
&= \left. \frac{n!}{(1 - t)^{n+1}} \right|_{t=0} \\
&= n!
\end{align}
$$

where we have used the fact the moment generating function for exponential random variables
is $\psi(t) = \lambda / (\lambda - t).$ Putting these pieces together yields the desired
bound on $n!$:

$$
e^{-n}
= \Pr{X \ge n}
\le \frac{\E{X^n}}{n^n}
\le \frac{n!}{n^n}.
$$

--------------------------------------------------------------------------------------------
