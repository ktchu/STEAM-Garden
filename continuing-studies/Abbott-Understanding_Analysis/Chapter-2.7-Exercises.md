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

__Solution__. Without loss of generality, assume $n > m$. Observe that

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

__Solution__. Consider the intervals $I_n = [s_{2n}, s_{2n-1}]$. Observe that

* $s_{2n+2} \ge s_{2n}$ because $s_{2n+2} = s_{2n} + a_{2n+1} - a_{2n+2}$ and
  $a_{2n+2} \le a_{2n+2};$

* $s_{2n+1} \le s_{2n-1}$ because $s_{2n+1} = s_{2n-1} - a_{2n} + a_{2n+1}$ and
  $a_{2n+1} \le a_{2n},$

which implies that $I_1 \supseteq I_2 \supseteq I_3 \supseteq \cdots$. By the Nested
Interval Property, $\bigcap_{n=1}^\infty I_n$ is nonempty.

Let $\epsilon > 0$ and $s \in \bigcap_{n=1}^\infty I_n$. Observing that
$(s_{2n} - s_{2n-1}) = (a_{2n}) \rightarrow 0$ as $n \rightarrow \infty$ (since
$(a_n) \rightarrow 0$), there exists $M \in \N$ such that $m \ge M$ implies that
$|s_{2m} - s_{2m-1}| < \epsilon$. $n \ge 2M$ implies the following.

* When $n$ is even, $n = 2m \ge 2M$, which implies that $m \ge M.$ Since $s \in I_m$,
  $|s - s_n| = |s - s_{2m}| \le |s_{2m-1} - s_{2m}| < \epsilon$.

* if $n$ is odd, $n = 2m - 1 \ge 2M$, which implies that $m \ge M + 1/2 \ge M.$ Since
  $s \in I_m$, $|s - s_n| = |s - s_{2m-1}| \le |s_{2m-1} - s_{2m}| < \epsilon$.

Therefore, $(s_n)$ converges.

#### 2.7.1.c.

__Problem__. Consider the subsequences $(s_{2n})$ and $(s_{2n+1})$, and show how the
Monotone Convergence Theorem leads to a third proof for the Alternating Series Test.

__Solution__. Using induction, we can prove that $s_n$ is bounded above by $a_1$. Clearly,
$s_1 = a_1 \le a_1$ and $s_2 = a_1 - a_2 \le a_1$. Now, suppose that
$s_{2n-1}, s_{2n} \le a_1$. Then

* $s_{2n+1}
  = s_{2n-1} - a_{2n} + a_{2n+1}
  = s_{2n-1} - (a_{2n} - a_{2n+1})
  \le s_{2n-1}
  \le a_1,
  $
  where the second to last inequality follows because $a_{2n} \ge a_{2n+1}$ and

* $s_{2n+2} = s_{2n+1} - a_{2n+2} \le s_{2n+1} \le a_1$.

Thus, $s_n \le a_1$ for all $n \in N$. Using similar logic, we can prove that $s_n$ is
bounded below by $(a_1 - a_2)$. Combining these results, we can conclude that $(s_n)$ is
bounded.

Now, let $\epsilon > 0$. Observe that the odd partial sums $s_{2n-1}$ form a bounded,
monotonically decreasing sequence, so the sequence $(s_{2n-1})$ converges. Let
$s = \lim s_{2n-1}$ as $n \rightarrow \infty$. Then there exists $N_1 \in \N$ such that
$n \ge N_1$ implies that $|s_{2n - 1} - s| < \epsilon / 2$. Since
$(a_n) \rightarrow 0$, there exists $N_2 \in \N$ such that $|a_n| < \epsilon / 2$ if
$n \ge N_2$. Let $N = 2 \max(N_1, N_2)$ and $n \ge N$.

* If $n$ is odd, then $n = 2m - 1 \ge N \ge 2 N_1$, which implies that
  $m \ge N_1 + 1/2 > N_1$. Thus, $|s_n - s| = |s_{2m-1} - s| < \epsilon / 2 < \epsilon.$

* If $n$ is even, then $n = 2m \ge N \ge 2 N_1, 2 N_2$, which implies that $m \ge N_1$ and
  $n \ge 2 N_2 > N_2$. Observe that

  $$
  |s_n - s|
  = |s_{2m} - s|
  = |s_{2m-1} - a_{2m} - s|
  \le |s_{2m-1} - s | + |a_{2m}|
  < \epsilon / 2 + \epsilon / 2
  = \epsilon
  $$

  where the first inequality follows from the triangle inequality and the second
  inequality follows because $m \ge N_1$ implies that $|s_{2m-1} - s| < \epsilon / 2$ and
  $n \ge N_2$ implies that $|a_{2m}| = |a_n| < \epsilon / 2.$

Therefore, $(s_n)$ converges.

--------------------------------------------------------------------------------------------
### 2.7.2.

__Problem__. Decide whether each of the following series converges of diverges:

(a) $\sum_{n=1}^\infty \frac{1}{2^n + n}$

(b) $\sum_{n=1}^\infty \frac{\sin(n)}{n^2}$

(c) $1 - \frac{3}{4} + \frac{4}{6} - \frac{5}{8} + \frac{6}{10} - \frac{7}{12} + \cdots$

(d) $1 + \frac{1}{2} - \frac{1}{3} + \frac{1}{4} + \frac{1}{5} - \frac{1}{6}
     + \frac{1}{7} + \frac{1}{8} - \frac{1}{9} + \cdots$

(e) $1 - \frac{1}{2^2} + \frac{1}{3} - \frac{1}{4^2} + \frac{1}{5} - \frac{1}{6^2}
     + \frac{1}{7} - \frac{1}{8^2} + \cdots$

__Solution__.

(a) Converges.

$$
\sum_{n=1}^\infty \frac{1}{2^n + n}
< \sum_{n=1}^\infty \frac{1}{2^n}.
$$

(b) Converges.

$$
\sum_{n=1}^\infty \left| \frac{\sin(n)}{n^2} \right|
\le \sum_{n=1}^\infty \frac{1}{n^2}
$$

Since the right hand side converges, the original sum converges absolutely.

(c) Diverges.

Observe that

$$
a_n
= (-1)^{n+1} \left( \frac{n+1}{2n} \right)
= \frac{(-1)^{n+1}}{2} + \frac{(-1)^{n+1}}{2n}
$$

Let $s_n$ be the partial sums of $\sum_{n=1}^\infty a_n$. Then the even and odd
subsequences of $(s_n)$ converge to different values, so the series diverges.

* $(s_{2n}) \rightarrow \sum_{n=1}^\infty \frac{(-1)^{n+1}}{2n}$

* $(s_{2n+1}) \rightarrow -\frac{1}{2} + \sum_{n=1}^\infty \frac{(-1)^{n+1}}{2n}$

Note that $\sum_{n=1}^\infty \frac{(-1)^{n+1}}{2n}$ converges by the Alternating Series
Test.

(d) Diverges.

Observing that
$a_{3n-2} + a_{3n-1} + a_{3n}
= \frac{1}{3n-2} + \frac{1}{3n-1} - \frac{1}{3n} > \frac{1}{3n-2} > \frac{1}{3n}$ (where
the first inequality follows because $\frac{1}{3n-1} > \frac{1}{3n}$), the subsequence
$(s_{3n})$ satisfies the inequality

$$
s_{3n} > \sum_{k=1}^{n} \frac{1}{3k} = \frac{H_{3n}}{3}.
$$

Therefore, $(s_n)$ has a divergent subsequence, which implies that it diverges.

(e) Diverges.

Observing that
$a_{2n-1} + a_{2n}
= \frac{1}{2n-1} - \frac{1}{(2n)^2} > \frac{1}{2n-1} > \frac{1}{2n},$ the subsequence
$(s_{2n})$ satisfies the inequality

$$
s_{2n} > \sum_{k=1}^{n} \frac{1}{2k} = \frac{H_{n}}{2}.
$$

Therefore, $(s_n)$ has a divergent subsequence, which implies that it diverges.

--------------------------------------------------------------------------------------------
### 2.7.3.

#### 2.7.3.a.

__Problem__. Provide the details for the proof of the Comparison Test (Theorem 2.7.4) using
the Cauchy Criterion for Series.

_Theorem 2.7.4_. Assume $(a_k)$ and $(b_k)$ are sequences satisyfing $0 \le a_k \le b_k$
for all $k \in \N$.

(i) If $\sum_{k=1}^\infty b_k$ converges, then $\sum_{k=1}^\infty a_k$ converges.

(ii) If $\sum_{k=1}^\infty a_k$ diverges, then $\sum_{k=1}^\infty b_k$ diverges.

__Solution__. Let $s_n = \sum_{k=1}^n a_k$ and $t_n = \sum_{k=1}^n b_k$. If
$\sum_{k=1}^\infty b_k$ converges, then by the Cauchy Criterion for Series, there exists
$N \in \N$ such that $n > m \ge N$ implies that $|t_n - t_m| < \epsilon.$ Therefore,

$$
|s_n - s_m|
= \sum_{k=m+1}^n a_k
\le \sum_{k=m+1}^n b_k
= |t_n - t_m|
< \epsilon,
$$

which implies that $\sum_{k=1}^\infty a_k$ converges.

If $\sum_{k=1}^\infty a_k$ diverges, then $(s_n)$ is not a Cauchy sequence. Thus, for all
$N \in \N$, there exists $n > m \ge N$ such that $|s_n - s_m| > \epsilon.$ Therefore,

$$
|t_n - t_m|
= \sum_{k=m+1}^n b_k
\ge \sum_{k=m+1}^n a_k
= |t_n - t_m|
> \epsilon,
$$

which implies that $\sum_{k=1}^\infty b_k$ diverges.

#### 2.7.3.b.

__Problem__. Give another proof of the Comparison Test, this time using the Monotone
Convergence Theorem.

__Solution__. First, observe that both $(s_n)$ and $(t_n)$ are monotone increasing
sequences. If $\sum_{k=1}^\infty b_k$ converges, then $(t_n)$ is bounded. Let $M > 0$
such that $|t_n| \le M$ for all $n > 1.$  Then $(s_n)$ is bounded because
$|s_n| \le |t_n| \le M$. Therefore, $(s_n)$ converges by the Monotone Convergence Theorem.

If $\sum_{k=1}^\infty a_k$ diverges, then $(s_n)$ is unbounded (because it is monotone).
Thus, for all $M > 0$, there exists $n \in \N$ such that $|s_n| > M$. Then $(t_n)$ is
also unbounded because $|t_n| \ge |s_n| > M$. Therefore, $(t_n)$ diverges because it is
unbounded.

--------------------------------------------------------------------------------------------
### 2.7.4.

Give an example of each or explain why the request is impossible referencing the proper
theorems(s).

#### 2.7.4.a.

__Problem__. Two series $\sum x_n$ and $\sum y_n$ that both diverge but where
$\sum x_n y_n$ converges.

__Solution__. Let $x_n = y_n = 1/n$. Then $\sum x_n = \sum y_n$ diverges because it is the
harmonic series. However, $\sum x_n y_n = \sum 1/n^2$ converges because it is the sum of
powers of $1/n$ with a power greater than 1.

#### 2.7.4.b.

__Problem__. A convergent series $\sum x_n$ and a bounded sequence $(y_n)$ such that
$\sum x_n y_n$ diverges.

__Solution__. Let $x_n = (-1)^n/n$ and $y_n = (-1)^n$. Then $\sum x_n$ converges by the
Alternating Series Test. However, $\sum x_n y_n = \sum 1/n$ diverges because it is the
harmonic series.

#### 2.7.4.c.

__Problem__. Two sequences $(x_n)$ and $(y_n)$ where $\sum x_n$ and $\sum (x_n + y_n)$
both converge by $\sum y_n$ diverges.

__Solution__. This request is impossible to satisfy because the Algebraic Limit Theorem
implies that if $\sum x_n$ and $\sum (x_n + y_n)$ both converge, then
$\sum ((x_n + y_n) - x_n) = \sum y_n$ converges.

#### 2.7.4.d.

__Problem__. A sequence $(x_n)$ satsifying $0 \le x_n \le 1/n$ where $\sum (-1)^n x_n$
diverges

__Solution__. Let

$$
x_n = \left\{\begin{array}{cl}
  \frac{1}{2n} & \textrm{$n$ even} \\
             0 & \textrm{$n$ odd} \\
\end{array}\right.
$$

Then $0 \le x_n \le 1/n$ and $\sum{n=1}^\infty (-1)^n x_n = \sum_{k=1}^\infty 1/2k$, which
diverges because it is a multiple of the harmonic series.

--------------------------------------------------------------------------------------------
### 2.7.5.

__Problem__. Now that we have proved the basic facts about geometric series, supply a proof
for Corollary 2.4.7.

_Corollary 2.4.7_. The series $\sum_{n=1}^\infty 1 / n^p$ converges if and only if $p > 1.$

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 2.7.6.

__Problem__. Let's say that a series _subverges_ if the sequence of partial sums contains
a subsequence that converges. Consider this (invented) definition for a moment, and then
decide which of the following statements are valid propositions about subvergent series:

(a) If $(a_n)$ is bounded, then $\sum a_n$ subverges.

(b) All convergent series are subvergent.

(c) If $\sum |a_n|$ subverges, then $\sum a_n$ subverges as well.

(d) If $\sum a_n$ subverges, then $(a_n)$ has a convergent subsequence.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 2.7.7.

### 2.7.7.a.

__Problem__. Show that if $a_n > 0$ and $\lim (n a_n) = l$ with $l \ne 0,$ then the series
$\sum a_n$ diverges.

__Solution__. Since $a_n > 0$, $\lim(n a_n) = l > 0$, there exists $N \in \N$ such that
$|n a_n - l| < l / 2$ whenever $n \ge N$. Thus, we can conclude that $a_n > l / 2n > 0$ for
$n \ge N$. Observe that

$$
\begin{align}
s_n
&= \sum_{k=1}^n a_k \\
&= \sum_{k=1}^{N-1} a_k + \sum_{k=N}^n a_k \\
&> \sum_{k=1}^{N-1} a_k + \sum_{k=N}^n \frac{l}{2k} \\
&= \sum_{k=1}^{N-1} a_k - \sum_{k=1}^{N-1} \frac{l}{2k}
 + \sum_{k=1}^{N-1} \frac{l}{2k} + \sum_{k=N}^n \frac{l}{2k} \\
&= \sum_{k=1}^{N-1} a_k - \sum_{k=1}^{N-1} \frac{l}{2k}
 + \sum_{k=1}^n \frac{l}{2k} \\
&= M + \frac{l}{2} H_n
\end{align}
$$

where $M$ is a constant equal to $\sum_{k=1}^{N-1} a_k - \sum_{k=1}^{N-1} \frac{l}{2k}$.
Therefore, $\sum a_n$ diverges because $H_n$ diverges.

### 2.7.7.b.

__Problem__. Assume $a_n > 0$ and $\lim (n^2 a_n)$ exists. Show that $\sum a_n$ converges.

__Solution__. Since $a_n > 0$, $\lim(n^2 a_n) = l > 0$, there exists $N \in \N$ such that
$|n^2 a_n - l| < l / 2$ whenever $n \ge N$. Thus, we can conclude that $a_n < 3l / 2n^2 > 0$
for $n \ge N$. Observe that

$$
\begin{align}
s_n
&= \sum_{k=1}^n a_k \\
&= \sum_{k=1}^{N-1} a_k + \sum_{k=N}^n a_k \\
&< \sum_{k=1}^{N-1} a_k + \sum_{k=N}^n \frac{3l}{2k^2} \\
&= \sum_{k=1}^{N-1} a_k - \sum_{k=1}^{N-1} \frac{l}{2k^2}
 + \sum_{k=1}^{N-1} \frac{3l}{2k^2} + \sum_{k=N}^n \frac{3l}{2k^2} \\
&= \sum_{k=1}^{N-1} a_k - \sum_{k=1}^{N-1} \frac{3l}{2k^2}
 + \sum_{k=1}^n \frac{3l}{2k^2} \\
&= M + \frac{3l}{2} \sum_{k=1}^n \frac{1}{k^2}
\end{align}
$$

where $M$ is a constant equal to $\sum_{k=1}^{N-1} a_k - \sum_{k=1}^{N-1} \frac{3l}{2k^2}$.
Therefore, $\sum a_n$ converges because $\sum 1/n^2$ converges.

--------------------------------------------------------------------------------------------
### 2.7.8.

__Problem__. Consider each of the following propositions. Provide short proofs for those
that are true and counterexamples for any that are not.

(a) If $\sum a_n$ converges absolutely, then $\sum a_n^2$ also converges absolutely.

(b) If $\sum a_n$ converges and $(b_n)$ converges, then $\sum a_n b_n$ converges.

(c) If $\sum a_n$ converge conditionally, then $\sum n^2 a_n$ diverges.

__Solution__.

(a) Let $\epsilon > 0$. Since $\sum a_n$ converges absolutely, the Cauchy Criterion for
Series implies that there exists $N \in \N$ such that $n > m \ge N$ implies that
$\sum_{k=m+1}^n |a_k| < \sqrt{\epsilon}.$ Observing that

$$
\sum_{k=m+1}^n |a_k|^2
\le \left( \sum_{k=m+1}^n |a_k| \right)^2
< \epsilon,
$$

we can conclude that $\sum |a_n|^2$ converges because it satisfies the Cauchy Criterion for
Series (with the same choice of $N$).

(b) This proposition is false. As a counterexample, consider
$a_n = b_n = (-1)^n / \sqrt{n}$. Then $\sum a_n$ converges by the Alternative Series Test
and $b_n$ converges to 0. However, $\sum a_n b_n = \sum 1 / n$ is the harmonic series,
which diverges.

(c) Suppose $\sum n^2 a_n$ converges. Then $(n^2 a_n) \rightarrow 0,$ which implies that
there exists $N \in \N$ such that $|n^2 a_n| < 1$ for all $n \ge N$. Thus, for $n \ge N$,
$|a_n| < 1 / n^2$. Since $\sum 1 / n^2$ converges absolutely, $\sum a_n$ must also
converge absolutely, a contradiction with the assumption that $\sum a_n$ converges
conditionally. Therefore, $\sum n^2 a_n$ must diverge if $\sum a_n$ converges
conditionally.

--------------------------------------------------------------------------------------------
### 2.7.9. Ratio Test

Given a series $\sum_{n=1}^\infty a_n$ with $a_n \ne 0$, the Ratio Test states that if
$(a_n)$ satisfies

$$
\lim \left| \frac{a_{n+1}}{a_n} \right| = r < 1,
$$

then the series converges absolutely.

#### 2.7.9.a.

__Problem__. Let $r'$ satisfy $r < r' < 1$. Explain why there exists an $N$ such that
$n \ge N$ implies $|a_{n+1}| \le |a_n| r'.$

__Solution__. TODO

#### 2.7.9.b.

__Problem__. Why does $|a_N| \sum (r')^n$ converge?

__Solution__. TODO

#### 2.7.9.c.

__Problem__. Now, show that $\sum |a_n|$ converges, and conclude that $\sum a_n$ converges.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 2.7.10. Infinite Products

Review Exercise 2.4.10 about infinite products and then answer the following questions.

#### 2.7.10.a.

__Problem__. Does

$$
\frac{2}{1} \cdot \frac{3}{2} \cdot \frac{5}{4} \cdot \frac{9}{8} \cdot \frac{17}{16} \cdots
$$

converge?

__Solution__. TODO

#### 2.7.10.b.

__Problem__. The infinite product

$$
\frac{1}{2} \cdot \frac{3}{4} \cdot \frac{5}{6} \cdot \frac{7}{8} \cdot \frac{9}{10} \cdots
$$

certainly converges. (Why?) Does it converge to zero?

__Solution__. TODO

#### 2.7.10.c.

__Problem__. In 1655, John Wallis famously derived the formula

$$
\left( \frac{2 \cdot 2}{1 \cdot 3} \right)
\left( \frac{4 \cdot 4}{3 \cdot 5} \right)
\left( \frac{6 \cdot 6}{5 \cdot 7} \right)
\left( \frac{8 \cdot 8}{7 \cdot 9} \right)
\cdots
= \frac{\pi}{2}.
$$

Show that the left side of this identity at least converges to something. (A complete proof
of this result is taken up in Section 8.3.)

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 2.7.11.

__Problem__. Find examples of two series $\sum a_n$ and $\sum b_n$ both of which diverge
but for which $\sum \min(a_n, b_n)$ converges. To make it more challenging, produce examples
where $(a_n)$ and $(b_n)$ are strictly positive and decreasing.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 2.7.12. Summation-by-parts

__Problem__. Let $(x_n)$ and $(y_n)$ be sequences, let $s_n = x_1 + x_2 + \cdots + x_n$ and
set $s_0 = 0.$ Use the observation that $x_j = s_j - s_{j-1}$ to verify the formula

$$
\sum_{j=m}^n x_j y_j
=  s_n y_{n+1} - s_{m-1} y_m + \sum_{j=m}^n s_j (y_j - y_{j+1}).

$$

__Solution__. Observe that $s_n y_{n+1} - s_{m-1} y_m$ is equal to the telescoping sum

$$
\sum_{j=m}^n (s_j y_{j+1} - s_{j-1} y_j).
$$

Adding and subtracting $s_j y_j$ to the summand, this sum becomes

$$
\begin{align}
\sum_{j=m}^n (s_j y_{j+1} - s_{j-1} y_j)
&= \sum_{j=m}^n (s_j y_{j+1} - s_j y_j) + (s_j y_j - s_{j-1} y_j) \\
&= \sum_{j=m}^n (s_j y_{j+1} - s_j y_j) + \sum_{j=m}^n (s_j y_j - s_{j-1} y_j) \\
&= \sum_{j=m}^n s_j (y_{j+1} - y_j) + \sum_{j=m}^n (s_j - s_{j-1}) y_j \\
&= \sum_{j=m}^n s_j (y_{j+1} - y_j) + \sum_{j=m}^n x_j y_j.
\end{align}
$$

Therefore,

$$
s_n y_{n+1} - s_{m-1} y_m
= \sum_{j=m}^n s_j (y_{j+1} - y_j) + \sum_{j=m}^n x_j y_j,
$$

which, when rearranged, yields the desired result.

--------------------------------------------------------------------------------------------
### 2.7.13. Abel's Test

Abel's Test for convergence states that if the series $\sum_{k=1}^\infty x_k$ converges,
and if $(y_n)$ is a sequences satisfying

$$
y_1 \ge y_2 \ge y_3 \ge \cdots \ge 0,
$$

then the series $\sum_{k=1}^\infty x_k y_k$ converges.

#### 2.7.13.a.

__Problem__. Use Exercise 2.7.12 to show that

$$
\sum_{k=1}^n x_k y_k = s_n y_{n+1} + \sum_{k=1}^n s_k (y_k - y_{k+1}),
$$

where $s_n = x_1 + x_2 + \cdots + x_n.$

__Solution__. Taking $m = 1$ in the summation-by-parts formula yields

$$
\begin{align}
\sum_{k=1}^n x_k y_k
&= s_n y_{n+1} - s_0 y_1 + \sum_{k=1}^n s_k (y_k - y_{k+1}) \\
&= s_n y_{n+1} + \sum_{k=1}^n s_k (y_k - y_{k+1}) \\
\end{align}
$$

where the second equality follows because $s_0 = 0$.

#### 2.7.13.b.

__Problem__. Use the Comparison Test to argue that $\sum_{k=1}^\infty s_k (y_k - y_{k+1})$
converges absolutely, and show how this leads directly to a proof of Abel's Test

__Solution__. First, observe that $s_k$ must be bounded because $\sum_{k=1}^\infty x_k$
converges. Let $|s_k| \le M$. Then

$$
|s_k (y_k - y_{k+1})| \le M |y_k - y_{k+1}| = M (y_k - y_{k+1})
$$

where the last equality follows because $y_k \ge y_{k+1} \ge 0$. Next, observe that
$(y_i)$ converges because it is monotone and bounded (by $0$ and $y_1$). Let $y$ be the
limit of $(y_i)$. The partial sums of $(y_j - y_{j+1})$ are telescoping sums:

$$
\sum_{j=1}^k (y_j - y_{j+1}) = y_1 - y_{k+1},
$$

so the series $\sum_{k=1}^\infty M (y_k - y_{k+1})$ converges (because the partial sums are
monotone increasing and bounded by above by $y_1$). Therefore, the Comparison Test implies
that the series $\sum_{k=1}^\infty |s_k (y_k - y_{k+1})|$ converges. In other words,
$\sum_{k=1}^\infty s_k (y_k - y_{k+1})$ converges absolutely.

Combining this conclusion with the convergence of $(s_n)$ and $(y_n)$ yields the desired
result because each of the terms in the expression for the partial sum
$\sum_{k=1}^n x_k y_k$ converge:

$$
\begin{align}
\sum_{k=1}^\infty x_k y_k
&= \lim_{n \rightarrow \infty} \sum_{k=1}^n x_k y_k \\
&= \lim_{n \rightarrow \infty}
  \left[ s_n y_{n+1} + \sum_{k=1}^n s_k (y_k - y_{k+1}) \right] \\
&= \lim_{n \rightarrow \infty} s_n y_{n+1}
  + \lim_{n \rightarrow \infty} \sum_{k=1}^n s_k (y_k - y_{k+1}) \\
&= \left[ \lim_{n \rightarrow \infty} s_n \right]
   \left[ \lim_{n \rightarrow \infty} y_{n+1} \right]
  + \lim_{n \rightarrow \infty} \sum_{k=1}^n s_k (y_k - y_{k+1}), \\
&= \left[ \lim_{n \rightarrow \infty} s_n \right]
   \left[ \lim_{n \rightarrow \infty} y_n \right]
  + \lim_{n \rightarrow \infty} \sum_{k=1}^n s_k (y_k - y_{k+1}), \\
\end{align}
$$

where all of the limits on the last expression on the right-hand side exist.

--------------------------------------------------------------------------------------------
### 2.7.14. Dirichlet's Test

Dirichlet's Test for convergence states that if the partial sums of $\sum_{k=1}^\infty x_k$
are bounded (but not necessarily convergent), and if $(y_k)$ is a sequence satisfying
$y_1 \ge y_2 \ge y_3 \ge \cdots \ge 0$ with $\lim y_k = 0$, then the series
$\sum_{k=1}^\infty x_k y_k$ converges.

#### 2.7.14.a.

__Problem__. Point how the hypothesis of Dirichlet's Test differs from that of Abel's Test
in Exercise 2.7.13, but show that essentially the same strategy can be used to provide a
proof.

__Solution__. TODO

#### 2.7.14.b.

__Problem__. Show how the Alternating Series Test (Theorem 2.7.7) can be derived as a
special case of Dirichlet's Test.

__Solution__. TODO

--------------------------------------------------------------------------------------------
