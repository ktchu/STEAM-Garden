Understanding Analysis (S. Abbott): Section 2.7 Exercises
=========================================================

--------------------------------------------------------------------------------------------
### Notation

* $\newcommand{\N}{\mathbb{N}}$
  The set of natural numbers: $\N$

* $\newcommand{\R}{\mathbb{R}}$
  The set of real numbers: $\R$

--------------------------------------------------------------------------------------------
### 2.7.1. Alternating Series Test

Let $(a_n)$ be a sequence satisfying,

(i) $a_1 \ge a_2 \ge a_3 \ge \cdots \ge a_n \ge a_{n+1} \ge \cdots$ and

(ii) $(a_n) \rightarrow 0$.

Then, the alternating series $\sum_{n=1}^\infty (-1)^{n+1} a_n$ converges.

Proving the Alternating Series Test amounts to showing that the sequence of partial sums

$$
s_n = a_1 - a_2 + a_3 - \cdots \pm a_n
$$

converges. (The opening example in Section 2.1 includes a typical illustration of $(s_n)$.)
Different characterizations of completeness lead to different proofs.

#### 2.7.1.a.

__Problem__. Prove the Alternating Series Test by showing that $(s_n)$ is a Cauchy sequence.

__Solution__. Observe that

$$
|s_n - s_m|
= \left\{
\begin{array}{ll}
|a_{m+1} - a_{m+2} + \cdots + a_{n-1} - a_n| & \textrm{when $(n-m)$ is even} \\
|a_{m+1} - a_{m+2} + a_{m+3} \cdots - a_{n-1} + a_n| & \textrm{when $(n-m)$ is odd} \\
\end{array}
\right.
$$

$(a_n)$ is monotone decreasing, so $(a_{k} - a_{k+1}) \ge 0$ for all $k$. When $(n-m)$ is
odd, break the sum $a_{m+1} - a_{m+2} + a_{m+3} \cdots - a_{n-1} + a_n$ into two parts:
$a_{m+1}$ and $(- a_{m+2} + a_{m+3} \cdots - a_{n-1} + a_n)$, where the second part has
an even number of terms. Then

$$
\begin{align}
|a_{m+2} - a_{m+3} + \cdots + a_{n-1} - a_n|
&= |(a_{m+2} - a_{m+3}) + (a_{m+4} - a_{m+5}) + \cdots + (a_{n-1} - a_n)| \\
&= (a_{m+2} - a_{m+3}) + (a_{m+4} - a_{m+5}) + \cdots + (a_{n-1} - a_n) \\
&\le (a_{m+2} - a_{m+3}) + (a_{m+3} - a_{m+4}) + (a_{m+4} - a_{m+5})
     + \cdots + (a_{n-2} - a_{n-1}) + (a_{n-1} - a_n) \\
&= a_{m+2} - a_n = |a_n - a_{m+2}|,
\end{align}
$$

where the second equality follows because each of the terms in parentheses is nonnegative,
the inequality follows because the nonnegative expression in the third line is sum of the
expression in the second line and additional nonnegative terms, and the second to last
equality follows because the expression in the third line is a telescoping sum.

Let $\epsilon > 0$. Since $(a_n)$ converges, it is a Cauchy sequence, which implies that
there exists an $N_1 \in \N$ such that whenever $n, m \ge N_2$ it follows that
$|a_n - a_{m}| < \epsilon / 2$. Since $(a_n)$ converges to $0$, there exists an
$N_2 \in \N$ such that whenever $n \ge N_2$ it follows that
$|a_n - 0| = |a_n| < \epsilon / 2$. Taking $N = \max(N_1, N_2)$, we can conclude that
$n, m \ge N$ implies that

$$
\begin{align}
|s_n - s_m|
&= |a_{m+1} - a_{m+2} + \cdots - a_{n-1} + a_n| \\
&\le |a_{m+1}| + |a_{m+2} - \cdots + a_{n-1} - a_n| \\
&\le |a_{m+1}| + |a_n - a_{m+2}| \\
&< \epsilon/2 + \epsilon/2 = \epsilon.
\end{align}
$$

When $(n-m)$ is even,

$$
\begin{align}
|s_n - s_m|
&= |a_{m+1} - a_{m+2} + \cdots + a_{n-1} - a_n| \\
&\le |a_n - a_{m+1}| \\
&< \epsilon/2 < \epsilon,
\end{align}
$$

where the first inequality follows from the same analysis we used for the $(n-m)$ odd case.

Combining the results for the even and odd cases for $(n-m)$, we conclude that $(s_n)$ is
a Cauchy sequence, which implies that it converges.

#### 2.7.1.b.

__Problem__. Supply another proof of this result using the Nested Interval Property
(Theorem 1.4.1).

__Solution__. TODO

#### 2.7.1.c.

__Problem__. Consider the subsequences $(s_{2n})$ and $(s_{2n+1})$, and show how the
Monotone Convergence Theorem leads to a third proof for the Alternating Series Test.

__Solution__. TODO

--------------------------------------------------------------------------------------------
