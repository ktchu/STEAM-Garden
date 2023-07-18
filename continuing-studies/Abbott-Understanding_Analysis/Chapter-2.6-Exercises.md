Understanding Analysis (S. Abbott): Section 2.6 Exercises
=========================================================

--------------------------------------------------------------------------------------------
### Notation

* $\newcommand{\N}{\mathbb{N}}$
  The set of natural numbers: $\N$

* $\newcommand{\Z}{\mathbb{Z}}$
  The set of integers: $\Z$

* $\newcommand{\R}{\mathbb{R}}$
  The set of real numbers: $\R$

--------------------------------------------------------------------------------------------
### 2.6.1.

__Problem__. Supply a proof for Theorem 2.6.2.

_Theorem 2.6.2_. Every convergent sequence is a Cauchy sequence.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 2.6.2.

Give an example of each of the following, or argue that such a request is impossible.

#### 2.6.2.a.

__Problem__. A Cauchy sequence that is not monotone.

__Solution__. TODO

#### 2.6.2.b.

__Problem__. A Cauchy sequence with an unbounded subsequence.

__Solution__. TODO

#### 2.6.2.c.

__Problem__. A divergent monotone sequence with a Cauchy subsequence.

__Solution__. TODO

#### 2.6.2.d.

__Problem__. An unbounded sequence containing a subsequence that is Cauchy.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 2.6.3.

If $(x_n)$ and $(y_n)$ are Cauchy sequences, then one easy way to prove that $(x_n + y_n)$
is Cauchy is to use the Cauchy Criterion. By Theorem 2.6.4, $(x_n)$ and $(y_n)$ must be
convergent, and the Algebraic Limit Theorem then implies that $(x_n + y_n)$ is convergent
and hence Cauchy.

#### 2.6.3.a.

__Problem__. Give a direct argument that $(x_n + y_n)$ is a Cauchy sequence that does not
use the Cauchy Criterion or the Algebraic Limit Theorem.

__Solution__. TODO

#### 2.6.3.b.

__Problem__. Do the same for the product $(x_n y_n)$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 2.6.4.

Let $(a_n)$ and $(b_n)$ be Cauchy sequences. Decide whether each of the following sequences
is a Cauchy sequence, justifying each conclusion.

#### 2.6.4.a.

__Problem__. $c_n = |a_n - b_n|$

__Solution__. Since $(a_n)$ and $(b_n)$ are Cauchy, they are both convergent with limits
$a$ and $b$, respectively. Let $\epsilon > 0$. Then there exists $N_1, N_2 \in \N$ such that
$|a_n - a| < \epsilon/2$ for $n \ge N_1$ and $|b_n - b| < \epsilon/2$ for $n \ge N_2$.
Thus, for $n \ge N = \max(N_1, N_2)$, we have

$$
|a_n - b_n|
= |a_n - a + a - b + b - b_n|
\le |a_n - a| + |a - b| + |b - b_n|
< \epsilon/2 + |a - b| + \epsilon/2
= |a - b| + \epsilon.
$$

Rearranging, we obtain

$$
|a_n - b_n| - |a - b| < \epsilon.
$$

Similarly,

$$
|a - b| < |a_n - b_n| + \epsilon,
$$

which implies that

$$
|a - b| - |a_n - b_n| < \epsilon.
$$

Combining these inequalities yields

$$
\left| |a_n - b_n| - |a - b| \right| < \epsilon.
$$

In other words, $c_n = |a_n - b_n|$ converges to $|a - b|$ and hence is Cauchy.

#### 2.6.4.b.

__Problem__. $c_n = (-1)^n a_n$

__Solution__. Consider the even and odd subsequences

$$
\begin{align}
c_{2n} &= a_{2n} \\
c_{2n+1} &= -a_{2n+1} \\
\end{align}
$$

Since $c_{2n} \rightarrow a$ and $c_{2n+1} \rightarrow -a$, $c_n$ is a divergent sequence.
Therefore, the Cauchy Criterion implies that $c_n$ is not Cauchy.

#### 2.6.4.c.

__Problem__. $c_n = \lfloor a_n \rfloor$ where $\lfloor x \rfloor$ refers to the greatest
integer less than or equal to $x.$

__Solution__. Since $(a_n)$ is Cauchy, it converges. Let $\lim a_n = a$.

_Case 1_: $a \in \Z$. In this case, $c_n$ is not guaranteed to converge, so $c_n$ is not
Cauchy. As a counterexample, consider the Cauchy sequence $a_n = 1 + (-1)^n / n$ which
converges to $1$. Observe that $a_n$ alternates between being greater than and less than
$1$, so $c_{2n} = 1$ and $c_{2n+1} = 0$ for all $n \in \N$. Therefore, the subsequence of
even and odd terms in $(c_n)$ converge to different limits, which implies that $(c_n)$ does
not converge and hence cannot be Cauchy.

_Case 2_: $a \notin \Z$. In this case, $c_n$ converges and is Cauchy. Let
$\epsilon = \min(a - \lfloor a \rfloor, \lfloor a \rfloor + 1 - a)$. Since
$a \ne \lfloor a \rfloor$, $\epsilon > 0$.
Then there exists $N \in \N$ such that $n \ge N$ implies that $|a_n - a| < \epsilon$, which
implies that, for sufficiently large $n$, $\lfloor a \rfloor < a_n < \lfloor a \rfloor + 1$.
Therefore, $c_n = \lfloor a_n \rfloor = \lfloor a \rfloor$ for $n \ge N$, so we can
conclude that $(c_n)$ converges to $\lfloor a \rfloor$ and hence is Cauchy.

--------------------------------------------------------------------------------------------
