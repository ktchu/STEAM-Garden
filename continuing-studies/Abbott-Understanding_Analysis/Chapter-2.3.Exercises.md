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

b. If $(x_n) \rightarrow x$, show that $(\sqrt{x_n}) \rightarrow x$.

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

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 2.3.7.

__Problem__. Give an example of each of the following, or state that such a request is
impossible by reference the proper theorem(s).

a. sequences $(x_n)$ and $(y_n)$, which both diverge, but whose sum $(x_n + y_n)$ converges;

b. sequences $(x_n)$ and $(y_n)$, where $(x_n)$ converges, $(y_n) diverges, and
   $(x_n + y_n)$ converges;

c. a convergent sequence $(b_n)$ with $b_n \ne 0$ for all $n$ such that $(1 / b_n)$
   diverges;

d. an unbounded sequence $(a_n)$ and a convergent sequence $(b_n)$ with $(a_n - b_n)$
   bounded;

e. two sequences $(a_n)$ and $(b_n)$, where $(a_n b_n)$ and $(a_n)$ converge but $(b_n)$
   does not.

__Solution__. TODO

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

__Solution__. TODO

#### 2.3.9.b.

__Problem__. Can we conclude anything about the convergence of $(a_n b_n)$ if we assume
that $(b_n)$ converges to some nonzero limit $b$?

__Solution__. TODO

#### 2.3.9.c.

__Problem__. Use (a) to prove Theorem 2.3.3, part (iii), for the case when $a = 0$.

_Theorem 2.3.3 Part (iii)_. TODO

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 2.3.10.

__Problem__. Consider the following list of conjectures. Provide a short proof for those
that are true and a counterexample for any that are false.

a. If $\lim (a_n - b_n) = 0,$ then $\lim a_n = \lim b_n.$

b. If $(b_n) \rightarrow b,$ then $|b_n| \rightarrow |b|.$

c. If $(a_n) \rightarrow 0$ and $(b_n - a_n) \rightarrow 0,$ then $(b_n) \rightarrow a.$

d. If $(a_n) \rightarrow 0$ and $|b_n - b| \le a_n$ for all $n \in \N$, then
   $(b_n) \rightarrow b.$

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 2.3.11. Cesaro Means

#### 2.3.11.a.

__Problem__. Show that if $(x_n)$ is a convergent sequence, then the sequence given by the
averages

$$
y_n = \frac{x_1 + x_2 + \cdots + x_n}{n}
$$

also converges to the same limit.

__Solution__. TODO

#### 2.3.11.b.

__Problem__. Give an example to show that it is possible for the sequence $(y_n)$ of
averages to converge even if $(x_n)$ does not.

__Solution__. TODO

--------------------------------------------------------------------------------------------
