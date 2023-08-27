Understanding Analysis (S. Abbott): Section 2.3 Exercises
=========================================================

--------------------------------------------------------------------------------------------
### Notation

* $\newcommand{\N}{\mathbb{N}}$
  The set of natural numbers: $\N$

* $\newcommand{\R}{\mathbb{R}}$
  The set of real numbers: $\R$

--------------------------------------------------------------------------------------------
### 2.3.1.

__Problem__. Let $x_n \ge 0$ for all $n \in \N$.

a. If $(x_n) \rightarrow 0$, show that $(\sqrt{x_n}) \rightarrow 0$.

b. If $(x_n) \rightarrow x$, show that $(\sqrt{x_n}) \rightarrow \sqrt{x}$.


__Solution__.

a. Let $\epsilon > 0$. Since $(x_n) \rightarrow 0$, there exists $N \in \N$ such that
   $|x_n - 0| = |x_n| \le \epsilon^2$ for $n \ge N.$ Therefore, $\sqrt{x_n} \le \epsilon$
   for $n \ge N$, which implies that $(\sqrt{x_n})$ converges to $0$.

b. Let $\epsilon > 0$. Since $(x_n) \rightarrow x,$ there exists $N_1 \in \N$ such that
   $|x_n - x| \le \frac{3}{4} |x|$ for $n \ge N_1,$ which implies that
   $\frac{1}{4}|x| \le |x_n| \le \frac{7}{4} |x|$ for $n \ge N_1.$ Thus,
   $\sqrt{x_n} \ge \frac{1}{2}\sqrt{x}$ for $n \ge N_1.$ Convergence of $(x_n)$ to $x$
   also implies that exists $N_2 \in \N$ such that
   $|x_n - x| \le \frac{3}{2} \epsilon \sqrt{x}.$ Therefore, for $n \ge \max(N_1, N_2)$,

   $$
   |\sqrt{x_n} - \sqrt{x}|
   = \frac{|x_n - x|}{|\sqrt{x_n} + \sqrt{x}|}
   \le \frac{\frac{3}{2} \epsilon \sqrt{x}}{\frac{3}{2} \sqrt{x}}
   = \epsilon,
   $$

  which proves that $(\sqrt{x_n}) \rightarrow \sqrt{x}$.

--------------------------------------------------------------------------------------------
### 2.3.2.

__Problem__. Using only Definition 2.2.3, prove that if $(x_n) \rightarrow 2$, then

a. $\left( \frac{2 x_n - 1}{3} \right) \rightarrow 1$;

b. $( 1 / x_n ) \rightarrow 1/2$.

For this exercise, the Algebraic Limit Theorem is off-limits.

__Solution__.

a. Let $\epsilon > 0$. Since $(x_n) \rightarrow 2,$ there exists $N \in \N$ such that
   $|x_n - 2| \le 3 \epsilon / 2$ for $n \ge N.$ Therefore,

   $$
   \left| \frac{2 x_n - 1}{3} - 1 \right|
   = \left| \frac{2 x_n - 4}{3} \right|
   = \frac{2}{3} |x_n - 2|
   < \frac{2}{3} \cdot \frac{3\epsilon}{2}
   = \epsilon,
   $$

   which proves the desired result.

b. Let $\epsilon > 0$. Since $(x_n) \rightarrow 2$, there exists $N_1 \in \N$ such that
   $|x_n - 2| \le 1$ for $n \ge N_1,$ which implies that $|x_n| > 1.$ The convergence of
   $(x_n)$ to $2$ also implies that there exists $N_2 \in N$ such that
   $|x_n - 2| \le 2 \epsilon$ for $n \ge N_2.$ Therefore, for $n \ge \max(N_1, N_2)$,

   $$
   | 1 / x_n  - 1 / 2|
   = \frac{|2 - x_n|}{2 |x_n|}
   < \frac{2 \epsilon}{2}
   = \epsilon,
   $$

   which proves the desired result.

--------------------------------------------------------------------------------------------
### 2.3.3. Squeeze Theorem

__Problem__. Show that if $x_n \le y_n \le z_n$ for all $n \in \N$, and if
$\lim x_n = \lim z_n = l$, then $\lim y_n = l$ as well.

__Solution__. By the Order Limit Theorem, $l = \lim x_n \le \lim y_n$ and
$\lim y_n \le \lim z_n = l$. Therefore, $\lim y_n = l$.

--------------------------------------------------------------------------------------------
### 2.3.4.

__Problem__. Let $(a_n) \rightarrow 0$, and use the Algebraic Limit Theorem to compute each
of the following limits (assuming the fractions are always defined):

a. $\lim \left( \frac{1 + 2 a_n}{1 + 3 a_n - 4 a_n^2} \right)$

b. $\lim \left( \frac{(a_n+2)^2 - 4}{a_n} \right)$

c. $\lim \left( \frac{\frac{2}{a_n} + 3}{\frac{1}{a_n} + 5} \right)$

__Solution__.

a. Since $\lim 1 + 3 a_n - 4 a_n^2 = 1 + 3 \cdot 0 - 4 \cdot 0^2 = 1 \ne 0$,

   $$
   \lim \left( \frac{1 + 2 a_n}{1 + 3 a_n - 4 a_n^2} \right)
   = \frac{\lim (1 + 2 a_n)}{\lim (1 + 3 a_n - 4 a_n^2)}
   = \frac{1}{1}
   = 1.
   $$

b.
   $$
   \lim \left( \frac{(a_n + 2)^2 -4}{a_n} \right)
   = \lim \left( \frac{a_n^2 + 4 a_n}{a_n} \right)
   = \lim (a_n + 4)
   = 0 + 4
   = 4.
   $$

c.
   $$
   \lim \left( \frac{\frac{2}{a_n} + 3}{\frac{1}{a_n} + 5} \right)
   = \lim \left( \frac{2 + 3 a_n}{1 + 5 a_n} \right)
   = \frac{2 + 3 \cdot 0}{1 + 5 \cdot 0}
   = \frac{2}{1}
   = 2
   $$

--------------------------------------------------------------------------------------------
### 2.3.5.

__Problem__. Let $(x_n)$ and $(y_n)$ be given, and define $(z_n)$ to be the "shuffled"
sequence $(x_1, y_1, x_2, y_2, x_3, y_3, \ldots, x_n, y_n, \ldots)$. Prove that $(z_n)$ is
convergent if and only if $(x_n)$ and $(y_n)$ are both convergent with
$\lim x_n = \lim y_n$.

__Solution__. $(\Rightarrow)$ Let $\epsilon > 0$ and suppose that $(z_n) \rightarrow L$.
Then there exists $N \in \N_z$ such that $n \ge N_z$ implies that $|z_n - L| < \epsilon$.
Observe that $n \ge N$ implies that $2n - 1 \ge 2 N - 1 \ge N$ (since $N \ge 1$). Therefore,

$$
|x_n - L| = |z_{2n-1} - L| < \epsilon
$$

and

$$
|y_n - L| = |z_{2n} - L| < \epsilon,
$$

which shows that $(x_n)$ and $(y_n)$ both converge to the same limit $L$, as desired.

$(\Leftarrow)$ Let $\epsilon > 0$ and suppose that $(x_n)$ and $(y_n)$ both converge to the
same limit $L$. Then there exist $N_x, N_y \in \N$ such that $n \ge N_x$ implies that
$|x_n - L| < \epsilon$ and $n \ge N_y$ implies that $|y_n - L| < \epsilon.$
Let $N = 2 \max(N_x, N_y)$. Observe that

$$
z_n
= \left\{\begin{array}{cl}
    x_{(n+1) / 2} & \textrm{if $n$ odd} \\
          y_{n/2} & \textrm{if $n$ even} \\
  \end{array}\right.
$$

Since $n \ge N$ implies that $(n+1) / 2 > n / 2 \ge N_x$ and $n / 2 \ge N_y$, we obtain

$$
|z_n - L|
= \left\{\begin{array}{cl}
    |x_{(n+1) / 2} - L| < \epsilon & \textrm{if $n$ odd} \\
          |y_{n/2} - L| < \epsilon & \textrm{if $n$ even} \\
  \end{array}\right.
$$

Thus, we can conclude that $(z_n)$ is convergent and its limit is $L$.

--------------------------------------------------------------------------------------------
### 2.3.6.

__Problem__. Consider the sequence given by $b_n = n - \sqrt{n^2 + 2n}.$ Taking
$(1/n) \rightarrow 0$ as given, and using both the Algebraic Limit Theorem and the result
in Exercise 2.3.1, show $\lim b_n$ exists and find the value of the limit.

__Solution__. Observe that

$$
\begin{align}
b_n
&= n - \sqrt{n^2 + 2n} \\
&= \left( n - \sqrt{n^2 + 2n} \right)
   \left( \frac{n + \sqrt{n^2 + 2n}}{n + \sqrt{n^2 + 2n}} \right) \\
&= \frac{
     \left( n - \sqrt{n^2 + 2n} \right) \left( n + \sqrt{n^2 + 2n} \right)
   }{
     \left( n + \sqrt{n^2 + 2n} \right)
   } \\
&= \frac{-2n}{ \left( n + \sqrt{n^2 + 2n} \right) } \\
&= \frac{-2}{ \left( 1 + \sqrt{1 + 2/n} \right) }. \\
\end{align}
$$

Thus, by the Algebra Limit Theorem

$$
\begin{align}
\lim b_n
&= \frac{-2}{ \lim \left( 1 + \sqrt{1 + 2/n} \right) } \\
&= \frac{-2}{ 1 + 1 } \\
&= -1
\end{align}
$$

where the limit of the square root in the denominator follows from the result in
Exercise 2.3.1.b.

--------------------------------------------------------------------------------------------
### 2.3.7.

__Problem__. Give an example of each of the following, or state that such a request is
impossible by reference the proper theorem(s).

a. sequences $(x_n)$ and $(y_n)$, which both diverge, but whose sum $(x_n + y_n)$ converges;

b. sequences $(x_n)$ and $(y_n)$, where $(x_n)$ converges, $(y_n)$ diverges, and
   $(x_n + y_n)$ converges;

c. a convergent sequence $(b_n)$ with $b_n \ne 0$ for all $n$ such that $(1 / b_n)$
   diverges;

d. an unbounded sequence $(a_n)$ and a convergent sequence $(b_n)$ with $(a_n - b_n)$
   bounded;

e. two sequences $(a_n)$ and $(b_n)$, where $(a_n b_n)$ and $(a_n)$ converge but $(b_n)$
   does not.

__Solution__.

a. Let $x_n = (-1)^n$ and $y_n = (-1)^{n+1}$. Then $(x_n)$ and $(y_n)$ both diverge and
   $x_n + y_n = 0$ for all $n$ so that $(x_n + y_n)$ converges to $0.$

b. It is impossible to satisfy this request. If $(x_n)$ and $(x_n + y_n)$ both converge,
   then the Algebraic Limit Theorem implies that $(x_n + y_n - x_n) = (y_n)$ converges.

c. Let $b_n = 1/n$. Then $b_n \ne 0$ for any $n,$ $(b_n)$ converges to $0,$ and
   $(1/b_n) = (n)$ diverges.

d. It is impossible to satisfy this request. Since convergent sequences are bounded,
   $(b_n)$ convergent and $(a_n - b_n)$ bounded implies that $(a_n)$ is bounded because


   $$
   |a_n|
   = |(a_n - b_n) + b_n|
   \le |a_n - b_n| + |b_n|
   \le M_b + M_{a-b}
   $$

   where $M_b$ and $M_{a-b}$ are bounds for $(b_n)$ and $(a_n - b_n),$ respectively.

e. It is impossible to satisfy this request. If $(a_n b_n)$ and $(a_n)$ converge, then
   $(a_n b_n / a_n) = (b_n)$ converges by the Algebraic Limit Theorem.

--------------------------------------------------------------------------------------------
### 2.3.8.

Let $(x_n) \rightarrow x$ and let $p(x)$ be a polynomial.

#### 2.3.8.a.

__Problem__. Show that $p(x_n) \rightarrow p(x)$.

__Solution__. Let $N$ be the degree of $p(x)$. Observe that

$$
p(x_n) = \sum_{k=0}^N a_k x^k
$$

for coefficients $a_k$ with $a_N \ne 0$. By the Algebraic Limit Theorem,

$$
\lim p(x_n)
= \lim \sum_{k=0}^N a_k x_n^k
= \sum_{k=0}^N \lim (a_k x_n^k)
= \sum_{k=0}^N a_k \lim (x_n^k)
= \sum_{k=0}^N a_k (\lim x_n)^k
= \sum_{k=0}^N a_k x^k
= p(x).
$$

#### 2.3.8.b.

__Problem__. Find an example of a function $f(x)$ and a convergent sequence
$(x_n) \rightarrow x$ where the sequence $f(x_n)$ converges, but not to $f(x)$.

__Solution__. Consider the function

$$
f(x)
= \left\{\begin{array}{rl}
   x & \textrm{if $x \ne 0$} \\
   1 & \textrm{if $x = 0$}
  \end{array}\right.
$$

and the sequence $x_n = 1/n$. Then $(x_n) \rightarrow 0$ and $f(x_n) = x_n \rightarrow 0$,
but $f(0) = 1 \ne \lim f(x_n)$.

--------------------------------------------------------------------------------------------
### 2.3.9.

#### 2.3.9.a.

__Problem__. Let $(a_n)$ be a bounded (not necessarily convergent) sequence, and assume
$\lim b_n = 0$. Show that $\lim (a_n b_n) = 0$. Why are we not allowed to use the Algebraic
Limit Theorem to prove this?

__Solution__. Let $\epsilon > 0.$ Because $(a_n)$ is bounded, there exists $M > 0$ such
that $|a_n| \le M$ for all $n \in \N.$ Since $(b_n) \rightarrow 0$, that there exists
$N \in \N$ such that $|b_n| < \epsilon / M.$ Therefore, for $n \ge N,$
$|a_n b_n| < M (\epsilon / M) = \epsilon,$ which implies that $(a_n b_n)$ converges to $0.$

Note that we cannot use the Algebraic Limit Theorem because it requires that $(a_n)$
converges.

#### 2.3.9.b.

__Problem__. Can we conclude anything about the convergence of $(a_n b_n)$ if we assume
that $(b_n)$ converges to some nonzero limit $b?$

__Solution__. When $(b_n)$ converges to a nonzero limit, we can only conclude that
$(a_n b_n)$ is bounded.

Since $(a_n)$ and $(b_n)$ are both bounded, $|a_n b_n| \le M_a M_b$ where $M_a$ and $M_b$
are bounds for $(a_n)$ and $(b_n),$ respectively.

#### 2.3.9.c.

__Problem__. Use (a) to prove Theorem 2.3.3, part (iii), for the case when $a = 0$.

_Theorem 2.3.3 Part (iii)_. If $\lim a_n = a$ and $\lim b_n = b$, then
$\lim (a_n b_n) = ab.$

__Solution__. If $a = 0$, the conditions for part (a) are satisfied with the roles of $a_n$
and $b_n$ reversed: $\lim a_n = 0$ and $(b_n)$ is bounded (because it converges). Therefore,
part (a) implies that $(a_n b_n)$ converges to $0 = ab.$

--------------------------------------------------------------------------------------------
### 2.3.10.

__Problem__. Consider the following list of conjectures. Provide a short proof for those
that are true and a counterexample for any that are false.

a. If $\lim (a_n - b_n) = 0,$ then $\lim a_n = \lim b_n.$

b. If $(b_n) \rightarrow b,$ then $|b_n| \rightarrow |b|.$

c. If $(a_n) \rightarrow a$ and $(b_n - a_n) \rightarrow 0,$ then $(b_n) \rightarrow a.$

d. If $(a_n) \rightarrow 0$ and $|b_n - b| \le a_n$ for all $n \in \N$, then
   $(b_n) \rightarrow b.$

__Solution__.

a. The conjecture is false. Consider the counterexample $a_n = b_n = (-1)^n$.
   Then $a_n - b_n = 0$, so $\lim (a_n - b_n) = 0,$ but $(a_n) = (b_n)$ diverges.

b. Let $\epsilon > 0.$ Since $(b_n) \rightarrow b$, there exists $N \in \N$ such that
   $n \ge N$ implies that $|b_n - b| < \epsilon.$ Then $||b_n| - |b|| < \epsilon$ (because
   $||b_n| - |b|| \le |b_n - b|$ by the triangle inequality). Therefore, $|b_N$ converges
   to $|b|.$

c. Since $(a_n)$ and $(b_n - a_n)$ both converge, the Algebraic Limit Theorem implies that
   $\lim b_n = \lim (b_n - a_n) + a_n$ converges to $0 + a = a.$

d. Let $\epsilon > 0.$ Since $(a_n) \rightarrow 0,$ there exists $N \in \N$ such that
   $|a_n| < \epsilon$ for $n \ge N.$ Thus, for $n \ge N$,
   $|b_n - b| \le a_n \le |a_n| < \epsilon$, which implies that $(b_n)$ converges to $b.$

--------------------------------------------------------------------------------------------
### 2.3.11. Cesaro Means

#### 2.3.11.a.

__Problem__. Show that if $(x_n)$ is a convergent sequence, then the sequence given by the
averages

$$
y_n = \frac{x_1 + x_2 + \cdots + x_n}{n}
$$

also converges to the same limit.

__Solution__. Let $\epsilon > 0$ and $(x_n) \rightarrow x.$ Observe that

* $x_n$ is bounded by $M > 0$ (because $(x_n)$ converges), which implies that
  $|x_n - x| \le 2M$ for all $n \in \N.$; and

* there exists $N' \in \N$ such that $|x_n - x| < \epsilon / 2$ for all $n \ge N'.$

Choose $N > \max(N', 4MN' / \epsilon)$ and let $n \ge N$. Then

$$
\begin{align}
|y_n - x|
&= \left| \frac{x_1 + x_2 + \cdots + x_n}{n} - x \right| \\
&= \left| \frac{(x_1 - x) + (x_2 - x) + \cdots + (x_n - x)}{n} \right| \\
&\le \frac{|x_1 - x| + \cdots + |x_n - x|}{n} \\
&\le \frac{1}{n} (|x_1 - x| + \cdots + |x_{N'} - x|)
     + \frac{1}{n} (|x_{N'+1} - x| + \cdots + |x_n - x|).
\end{align}
$$

Since $|x_n - x| \le 2M$ for all $n$, the first parenthesis is bounded by $\epsilon / 2$
(because $2MN' / n \le 2MN' / N < \epsilon / 2$). The second parenthesis is also bounded by
$\epsilon / 2$ because $n \ge N > N'$ implies that $|x_n - x| < \epsilon / 2$ so that

$$
\frac{1}{n} (|x_{N'+1} - x| + \cdots + |x_n - x|)
< \frac{\epsilon (N-N')}{2n}
\le \frac{\epsilon (N-N')}{2N}
< \frac{\epsilon N}{2N}
= \frac{\epsilon}{2}.
$$

Thereefore, we can conclude that $|y_n - x| < \epsilon$ for $n \ge N$, which proves the
desired result.

#### 2.3.11.b.

__Problem__. Give an example to show that it is possible for the sequence $(y_n)$ of
averages to converge even if $(x_n)$ does not.

__Solution__.

_Example #1._ Let $x_n = \sqrt{n}$. Then $(x_n)$ does not converge but
$y_n = 1 / \sqrt{n} \rightarrow 0.$

_Example #2._ Let $x_n = (-1)^{n+1}$. Then $(x_n)$ does not converge but

$$
y_n
= \left\{\begin{array}{cl}
    1/n & \textrm{if $n$ is odd} \\
      0 & \textrm{if $n$ is even}. \\
  \end{array}\right.
$$

Thus, $|y_n| \le 1/n,$ so $(y_n) \rightarrow 0.$

--------------------------------------------------------------------------------------------
### 2.3.12.

A typical task in analysis is to decipher whether a property possess by every term in a
convergent sequence is necessarily inherited by the limit. Assume $(a_n) \rightarrow a,$
and determine the validity of each claim. Try to produce a counterexample for any that are
false.

#### 2.3.12.a.

__Problem__. If every $a_n$ is an upper bound for a set $B,$ then $a$ is also an upper
bound for $B.$

__Solution__. True. The result follows from the Order Limit Theorems. Let $b \in B$. Then
$a_n \ge b$ for all $n \in \N$, which implies that $a \ge b$ (by the Order Limit Theorems).
Since $b$ was arbitrary, $a \ge b$ for all $b \in B.$ In other words, $a$ is an upper bound
for $B.$

#### 2.3.12.b.

__Problem__. If every $a_n$ is in the complement of the interval $(0, 1),$ then $a$ is also
in the complement of $(0, 1).$

__Solution__. True. Suppose that $a \in (0, 1).$ Then $0 < a < 1$. In particular,
$a - 0$ and $(1 - a)$ are both strictly positive. Let $\epsilon = \min(a, 1-a) > 0$. Since
$(a_n) \rightarrow a$, there exists $N \in \N$ such that $|a_n - a| < \epsilon / 2.$
Therefore,

* $a_n \ge a - \epsilon / 2 \ge \epsilon - \epsilon / 2 = \epsilon / 2 > 0$

and

* $a_n \le a + \epsilon / 2 \le (1 - \epsilon) + \epsilon / 2 = 1 - \epsilon / 2 < 1.$

In other words, $a_n \in (0, 1),$ which contradicts the assumption that $a_n \notin (0, 1).$
Therefore, $a$ must be in the complement of $(0, 1).$

#### 2.3.12.c.

__Problem__. If every $a_n$ is rational, then $a$ is also rational.

__Solution__. False. Let $a_n$ be the best decimal approximations to $\pi$ with $n$ digits
to the right of the decimal point. Then each $a_n$ is rational, but the limit is irrational.

--------------------------------------------------------------------------------------------
### 2.3.13. Iterated Limits

Given a doubly indexed array $a_{mn}$ where $m, n \in \N,$ what should
$\lim_{m,n \rightarrow \infty} a_{mn}$ represent?

#### 2.3.13.a.

__Problem__. Let $a_{mn} = m / (m+n)$ and compute the _iterated_ limits

$$
\lim_{n \rightarrow \infty} \left( \lim_{m \rightarrow \infty} a_{mn} \right)
$$

and

$$
\lim_{m \rightarrow \infty} \left( \lim_{n \rightarrow \infty} a_{mn} \right).
$$

Define $\lim_{m,n \rightarrow \infty} a_{mn} = a$ to mean that for $\epsilon > 0$ there
exists an $N \in \N$ such that if both $m,n \ge N$, then $|a_{mn} - a| < \epsilon.$

__Solution__. TODO

#### 2.3.13.b.

__Problem__. Let $a_{mn} = 1 / (m+n).$ Does $\lim_{m,n \rightarrow \infty} a_{mn}$ exist in
this case? Do the two iterated limits exist? How do these three values compare? Answer
these same questions for $a_{mn} = mn / (m^2 + n^2).$

__Solution__. TODO

#### 2.3.13.c.

__Problem__. Produce an example where $\lim_{m,n \rightarrow \infty} a_{mn}$ exists but
where neither iterated limit can be computed.

__Solution__. TODO

#### 2.3.13.d.

__Problem__. Assume $\lim_{m,n \rightarrow \infty} a_{mn} = a,$ and assume that for each
fixed $m \in \N,$ $\lim_{n \rightarrow \infty} (a_{mn}) \rightarrow b_m.$ Show that
$\lim_{m \rightarrow \infty} b_m = a.$

__Solution__. TODO

#### 2.3.13.e.

__Problem__. Prove that if $\lim_{m,n \rightarrow \infty} a_{mn}$ exists and the iterated
limits both exist, then all three limits must be equal.

__Solution__. TODO

--------------------------------------------------------------------------------------------
