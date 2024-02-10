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

__Solution__. Suppose $(x_n)$ be a convergent sequence with limit $x$. Let $\epsilon > 0$.
Then there exists $N \in \N$ such that $n \ge N$ implies that $|x_n - x| < \epsilon / 2$.
If $m, n \ge N$, then

$$
|x_m - x_n| \le |x_m - x| + |x - x_n| < \frac{\epsilon}{2} + \frac{\epsilon}{2} = \epsilon,
$$

which proves that $(x_n)$ is a Cauchy sequence.

--------------------------------------------------------------------------------------------
### 2.6.2.

Give an example of each of the following, or argue that such a request is impossible.

#### 2.6.2.a.

__Problem__. A Cauchy sequence that is not monotone.

__Solution__. Consider the sequence $x_n = (-1)^n / n$. $(x_n)$ converges to $0$, which
implies that it is a Cauchy sequence, but it is not monotone.

#### 2.6.2.b.

__Problem__. A Cauchy sequence with an unbounded subsequence.

__Solution__. This request is impossible to satisfy because Cauchy sequences must be
bounded, which ipmlpies that any subsequence is also bounded.

#### 2.6.2.c.

__Problem__. A divergent monotone sequence with a Cauchy subsequence.

__Solution__. This request is impossible to satisfy because any divergence monotone
sequence must be unbounded. Since any subsequence of a divergent monotone sequence is also
divergent and monotone, all subsequences of a divergent monotone sequence must be unbounded,
and therefore cannot be Cauchy (because Cauchy sequences must be bounded).

#### 2.6.2.d.

__Problem__. An unbounded sequence containing a subsequence that is Cauchy.

__Solution__. Consider the sequence

$$
2, \frac{1}{2}, 3, \frac{1}{3}, \ldots
$$

This sequence is unbounded. The subsequence of even terms $1/2, 1/3, 1/4, \ldots$ converges to $0$, which implies that is Cauchy.

--------------------------------------------------------------------------------------------
### 2.6.3.

If $(x_n)$ and $(y_n)$ are Cauchy sequences, then one easy way to prove that $(x_n + y_n)$
is Cauchy is to use the Cauchy Criterion. By Theorem 2.6.4, $(x_n)$ and $(y_n)$ must be
convergent, and the Algebraic Limit Theorem then implies that $(x_n + y_n)$ is convergent
and hence Cauchy.

#### 2.6.3.a.

__Problem__. Give a direct argument that $(x_n + y_n)$ is a Cauchy sequence that does not
use the Cauchy Criterion or the Algebraic Limit Theorem.

__Solution__. Let $\epsilon > 0$. Since $(x_n)$ and $(y_n)$ are Cauchy, there exists
$N_x, N_y \in \N$ such that $n_x, m_x \ge N$ and $n_y, m_y \ge M$ imply that
$|x_{n_x} - x_{m_x}| < \epsilon / 2$ and $|y_{n_y} - y_{m_y}| < \epsilon / 2$. Let
$N = \max(N_x, N_y)$. Then $n, m > N$ implies that

$$
|(x_n + y_n) - (x_m + y_m)|
= |(x_n - x_m) + (y_n - y_m)|
\le |x_n - x_m| + |y_n - y_m|
< \frac{\epsilon}{2} + \frac{\epsilon}{2}
= \epsilon.
$$

Therefore, $(x_n + y_n)$ is a Cauchy sequence.

#### 2.6.3.b.

__Problem__. Do the same for the product $(x_n y_n)$.

__Solution__. Observe that

$$
|x_n y_n - x_m y_m|
= |(x_n y_n - x_m y_n) + (x_m y_n - x_m y_m)|
\le |x_n y_n - x_m y_n| + |x_m y_n - x_m y_m|
= |y_n| |x_n - x_m| + |x_m| |y_n - y_m|
$$

Let $\epsilon > 0$. Since $(x_n)$ and $(y_n)$ are Cauchy, both sequences are bounded by
some $M > 0$. Using setup analogous to the one in part (a), we can choose $N \in \N$ such
that $n, m > N$ implies that $|x_n - x_m| < \epsilon / 2M$ and
$|y_n - y_m| < \epsilon / 2M$. Then

$$
|x_n y_n - x_m y_m|
\le |y_n| |x_n - x_m| + |x_m| |y_n - y_m|
\le M |x_n - x_m| + M |y_n - y_m|
< M \left( \frac{\epsilon}{2M} \right) + M \left( \frac{\epsilon}{2M} \right)
= \epsilon,
$$

which proves that $(x_n y_n)$ is Cauchy.

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
$a_n \rightarrow a \rfloor$, there exists $N \in \N$ such that $n \ge N$ implies that
$|a_n - a| < \epsilon$, which implies that for sufficiently large $n$,
$\lfloor a \rfloor < a_n < \lfloor a \rfloor + 1$. Therefore,
$c_n = \lfloor a_n \rfloor = \lfloor a \rfloor$ for $n \ge N$, so we can conclude that
$(c_n)$ converges to $\lfloor a \rfloor$ and hence is Cauchy.

--------------------------------------------------------------------------------------------
### 2.6.5.

__Problem__. Consider the following (invented) definition: A sequence $(s_n)$ is
_pseudo-Cauchy_ if, for all $\epsilon > 0,$ there exists and $N$ such that if $n \ge N,$
then $|s_{n+1} - s_n| <  \epsilon.$

Decide which one of the following two propositions is actually true. Supply a proof for the
valid statement and a counterexample for the other.

(i) Pseudo-Cauchy sequences are bounded.

(ii) If $(x_n)$ and $(y_n)$ are pseudo-Cauchy, then $(x_n + y+n)$ is pseudo-Cauchy as well.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 2.6.6.

Let's call a sequence $(a_n)$ _quasi-increasing_ if for all $\epsilon > 0$ there exists an
$N$ such that whenever $n > m \ge N$ it follows that $a_n > a_m - \epsilon.$

#### 2.6.6.a.

__Problem__. Give an example of a sequence that is quasi-increasing but not monotone or
eventually monotone.

__Solution__. TODO

#### 2.6.6.b.

__Problem__. Give an example of a quasi-increasing sequence that is divergent and not
monotone.

__Solution__. TODO

#### 2.6.6.c.

__Problem__. Is there an analogue of the Monotone Convergence Theorem for quasi-increasing
sequences? Given an example of a bounded, quasi-incrasing sequence that doesn't converge,
or prove that no such sequence exists.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 2.6.7.

Exercises 2.4.4 and 2.5.4 establish the equivalence of the Axiom of Completeness and the
Monotone Convergence Theorem. They also show the Nested Interval Property is equivalent to
these other two in the presence of the Archimedean Property.

#### 2.6.7.a.

__Problem__. Assume the Bolzano-Weierstrass Theorem is true and use it to construct a proof
of the Monotone Convergence Theorem without making any appeal to the Archimedean Property.
This shows that BW, AoC, and MCT are all equivalent.

__Solution__. TODO

#### 2.6.7.b.

__Problem__. Use the Cauchy Criterion to prove the Bolzano-Weierstrass Theorem, and find
the point in the argument where the Archimedean Property is implicitly required. This
establishes the final link in the equivalence of the five characterizations of completeness
discussed at the end Section 2.6.

__Solution__. TODO

#### 2.6.7.c.

__Problem__. How do we know it is impossible to prove the Axiom of Completeness starting
from the Archimedean Property?

__Solution__. TODO

--------------------------------------------------------------------------------------------
