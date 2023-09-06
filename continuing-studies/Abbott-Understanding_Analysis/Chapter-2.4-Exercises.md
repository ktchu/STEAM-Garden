Understanding Analysis (S. Abbott): Section 2.4 Exercises
=========================================================

--------------------------------------------------------------------------------------------
### Notation

* $\newcommand{\N}{\mathbb{N}}$
  The set of natural numbers: $\N$

* $\newcommand{\R}{\mathbb{R}}$
  The set of real numbers: $\R$

--------------------------------------------------------------------------------------------
### 2.4.1.

#### 2.4.1.a.

__Problem__. Prove that the sequence defined by $x_1 = 3$ and

$$
x_{n+1} = \frac{1}{4 - x_n}
$$

converges.

__Solution__. First, we use induction to prove that $(x_n)$ is bounded below by $1/4$ and
monotone decreasing. The base case is obvious: $x_1 = 3$ and $x_2 = 1$, so
$x_1, x_2 \ge 1/4$ and $x_2 \le x_1.$ Next, assume that $x_n, x_n+1 \ge 1/4$ and
$x_{n+1} \le x_n.$ Then we have

$$
x_{n+2} = \frac{1}{4 - x_{n+1}}
\ge \frac{1}{4}
$$

and

$$
x_{n+2} = \frac{1}{4 - x_{n+1}}
\le \frac{1}{4 - x_n}
= x_{n+1}
$$

Since $(x_n)$ is bounded and monotone, it converges by the Monotone Convergence Theorem.

#### 2.4.1.b.

__Problem__. Now that we know tht $\lim x_n$ exists, explain why $\lim x_{n+1}$ must also
exist and equal the same value.

__Solution__. The sequence $y_n = x_{n+1}$ is simply a shift of the original sequence, so
its convergence properties are exactly the same as $(x_n)$. In particular, $(y_n)$
converges and its limit is the same as $(x_n).$

#### 2.4.1.c.

__Problem__. Take the limit of each side of the recursive equation in part (a) to
explicitly compute $\lim x_n.$

__Solution__. Let $x = \lim x_n$. Taking the limits of both sides of the recursive
equation, we obtain the equation

$$
x = \frac{1}{4 - x},
$$

which yields the quadratic equation

$$
x^2 -4x + 1 = 0.
$$

The roots of this equation are $2 \pm \sqrt{3}.$ Since $(x_n) > 0$ implies that $x \ge 0$,
the limit is the positive root: $x = 2 + \sqrt{3}.$

--------------------------------------------------------------------------------------------
### 2.4.2.

#### 2.4.2.a.

__Problem__. Consider the recursively defined sequence $y_1 = 1,$

$$
y_{n+1} = 3 - y_n,
$$

and set $y = \lim y_n.$ Because $(y_n)$ and $(y_{n+1})$ have the same limit, taking the
limit across the recursvie equation gives $y = 3 - y.$ Solving for $y$, we conclude
$\lim y_n = 3/2.$

What is wrong with this argument?

__Solution__. We haven't established that $(y_n)$ has a limit, so it is not valid to take
the limit across the recursive equation. In fact, $(y_n)$ does not converge because

$$
y_n
= \left\{ \begin{array}{cl}
  1 & \textrm{for $n$ odd} \\
  2 & \textrm{for $n$ even} \\
  \end{array} \right.
$$

which can be proven by induction.

#### 2.4.2.b.

__Problem__. This time set $y_1 = 1$ and $y_{n+1} = 3 - \frac{1}{y_n}.$ Can the strategy
in (a) be applied to compute the limit of this sequence?

__Solution__. Yes, we can employ the strategy from (a) because this sequence converges.

Using induction, we can prove that $(y_n)$ is monotone increasing and bounded between
$1$ and $3.$ Since $y_1 = 1$ and $y_2 = 2$, $y_2 \ge y_1$ and $1 \le y_1, y_2 \le 3$. Next,
assume that $y_{n+1} \ge y_n$ and $1 \le y_n, y_{n+1} \le 3.$ Then

$$
y_{n+2} = 3 - \frac{1}{y_{n+1}}.
$$

The inductive hypothesis $1 \le y_{n+1} \le 3$ implies that $y_{n+2}$ satisfies the same
bounds

$$
1 < 2 \le y_{n+2} \le 3 - \frac{1}{3} < 3.
$$

The inductive hypothesis $y_{n+1} \ge y_n$ implies that

$$
3 - \frac{1}{y_{n+1}} \ge 3 - \frac{1}{y_n},
$$

which yields $y_{n+1} \ge y_{n+1}.$ Therefore, $(y_n)$ is monotone and bounded, so it
converges by the Monotone Convergence Theorem.

Letting $y = \lim y_n$ and applying the strategy from (a), we obtain the equation

$$
y = 3 - \frac{1}{y}
$$

which has the positive solution $y = (3 + \sqrt{5}) / 2.$

--------------------------------------------------------------------------------------------
### 2.4.3.

#### 2.4.3.a.

__Problem__. Show that

$$
\sqrt{2}, \sqrt{2 + \sqrt{2}}, \sqrt{2 + \sqrt{2 + \sqrt{2}}}, \ldots
$$

converges and find the limit.

__Solution__. Define the sequence recursively by $x_1 = \sqrt{2}$ and
$x_{n+1} = \sqrt{2 + x_n}$. Using induction, we can show that $(x_n)$ is monotone
increasing and bounded with $0 \le x_n \le 2.$ The base case is readily established because
$x_1 = \sqrt{2}$ and $x_2 = \sqrt{2 + \sqrt{2}}$ imply that

* $x_2 \ge x_1$,

* $0 \le x_1 = \sqrt{2} \le 2$, and

* $0 \le x_2 = \sqrt{2 + \sqrt{2}} \le \sqrt{2 + 2} = 2$.

Assume that $x_n$ and $x_{n+1}$ satisfy $x_{n+1} \ge x_n$ and $0 \le x_n, x_{n+1} \le 2$.
Then

* $x_{n+2} = \sqrt{2 + x_{n+1}} \ge \sqrt{2 + x_n} = x_{n+1}$

* $x_{n+2} = \sqrt{2 + x_{n+1}} \ge \sqrt{2} > 0$, and

* $x_{n+2} = \sqrt{2 + x_{n+1}} \le \sqrt{2 + 2} = 2,$

which shows that $(x_n)$ is monotone increasing and bounded. Thus, by the Monotone
Convergence Theorem, $(x_n)$ converges.

Letting $x = \lim x_n$, we can take the limit across the recursion equation to obtain the
following equation:

$$
x = \sqrt{2 + x},
$$

which has solutions $x = -1$ and $x = 2$. By the Order Limit Theorem, $x_n \ge 0$ implies
that $x \ge 0$, so the limit is $x = 2.$

#### 2.4.3.b.

__Problem__. Does the sequence

$$
\sqrt{2}, \sqrt{\sqrt{2}}, \sqrt{\sqrt{\sqrt{2}}}, \ldots
$$

converges? If so, find the limit.

__Solution__. Yes. The sequence converges. Define the sequence recursively by
$x_1 = \sqrt{2}$ and $x_{n+1} = \sqrt{x_n}$. Using induction, we can show that $(x_n)$ is
monotone decreasing and bounded with $1/2 < x_n < 2.$ The base case is readily established
because $x_1 = \sqrt{2}$ and $x_2 = \sqrt{\sqrt{2}}$ imply that

* $x_2 \le x_1$,

* $1/2 < x_1 = \sqrt{2} < 2$, and

* $1/2 < x_2 = \sqrt{\sqrt{2}} = 2^{1/4} < 2^0 < 2$.

Assume that $x_n$ and $x_{n+1}$ satisfy $x_{n+1} \ge x_n$ and $1/2 < x_n, x_{n+1} < 2$.
Then

* $x_{n+2} = \sqrt{x_{n+1}} \le \sqrt{x_n} = x_{n+1}$

* $x_{n+2} = \sqrt{x_{n+1}} > \sqrt{\sqrt{1/2}} > \sqrt{1/2}$, and

* $x_{n+2} = \sqrt{x_{n+1}} < \sqrt{2} < 2,$

which shows that $(x_n)$ is monotone decreasing and bounded. Thus, by the Monotone
Convergence Theorem, $(x_n)$ converges.

Letting $x = \lim x_n$, we can take the limit across the recursion equation to obtain the
following equation:

$$
x = \sqrt{x},
$$

which has solutions $x = 1$ and $x = 0$. By the Order Limit Theorem, $x_n > 1/2$ implies
that $x \ge 1/2$, so the limit is $x = 1.$

--------------------------------------------------------------------------------------------
### 2.4.4.

The following two results suggest that we could have used the Monotone Convergence Theorem
in place of the Axiom of Completeness (AoC) as our starting axiom for building a proper
theory of the real numbers.

#### 2.4.4.a.

__Problem__. In Section 1.4 we used the Axiom of Completeness (AoC) to prove the
Archimedean Property of $\R$ (Theorem 1.4.2). Show that the Monotone Convergence Theorem
can also be used to prove the Archimedean Property without making use of any AoC.

__Solution__. Let $x \in \R$. Suppose that there does not exist an $n \in \N$ such that
$n > x$. In other words, $x \ge n$ for all $n \in \N$. That is, $x$ is an upper bound for
the sequence $a_n = n.$ Since $a_n$ is monotone increasing and bounded above, it must
converge (by the Monotone Convergence Theorem). Let $a = \lim a_n.$ Then there exists
$N \in \N$ such that $|a_n - a| < 1/2$ whenever $n \ge N.$ Suppose that $m \ge N$. Then
$|m - a| = |a_m - a| < 1/2$, which implies that $1/2 < (m + 1) - a = a_{m+1} - a$ (because
$-1/2 < m - a < 1/2$). However, $(m + 1) > m \ge N$ requires that
$|(m + 1) - a| = |a_{m+1} - a| < 1/2,$ so we have arrived at a contradiction. Therefore,
the Archimedean Property must be true.

#### 2.4.4.b.

__Problem__. Use the Monotone Convergence Theorem to supply a proof for the Nested Interval
Property (Theorem 1.4.1) that doesn't make use of AoC.

__Solution__. Let $I_n = [a_n, b_n]$ satisfy the conditions for the Nested Interval
Property. Consider $(a_n),$ the sequence of lower endpoints of the intervals. By
definition, $(a_n)$ is monotone increasing (because the $I_n$ are nested). Moreover, $(a_n)$
is bounded above by $b_1$ (because $a_n \le b_n \le b_1$). Thus, the Monotone Convergence
Theorem implies that $(a_n)$ converges. A similar argument shows that $(b_n)$ also
converges. Let $a = \lim a_n$ and $b = \lim b_n.$ Then the Order Limit Theorem implies that
$a \le b$ (because $a_n \le b_n$ for all $n$), so $I = [a, b]$ is not empty. Furthermore,
$I \subseteq I_n$ for all $n$ (because $a \ge a_n$ and $b \le b_n$ for all $n$), so
$I \subseteq \bigcap_{n=1}^\infty I_n$. Therefore, $\bigcap_{n=1}^\infty I_n$ cannot be
empty because it contains a nonempty subset, which proves the Nested Interval Property.

--------------------------------------------------------------------------------------------
### 2.4.5.

Let $x_1 = 2$, and define

$$
x_{n+1} = \frac{1}{2} \left( x_n + \frac{2}{x_n} \right)
$$

#### 2.4.5.a.

__Problem__. Show that $x_n^2$ is always greater than or equal to $2,$ and then use this to
prove that $x_n - x_{n+1} \ge 0.$ Conclude that $\lim x_n = \sqrt{2}.$

__Solution__. Observe that

$$
x_{n+1}
= \frac{1}{2} \left( x_n + \frac{2}{x_n} \right)
= \frac{\sqrt{2}}{2} \left( \frac{x_n}{\sqrt{2}} + \frac{\sqrt{2}}{x_n} \right)
\le \frac{\sqrt{2}}{2} \cdot 2
= \sqrt{2}
$$

where the inequality follows because the minimum value of $f(x) = x + 1/x$ is $2$
(which follows from the observation that $(\sqrt{x} - 1/\sqrt{x})^2 \ge 0$). Thus, we can
conclude that

$$
x_n - x_{n+1}
= x_n - \frac{1}{2} \left( x_n + \frac{2}{x_n} \right)
= \frac{x_n}{2} - \frac{1}{x_n}
\ge \frac{\sqrt{2}}{2} - \frac{1}{\sqrt{2}}
= 0.
$$

Therefore, $(x_n)$ is monotone decreasing and bounded below (by $\sqrt{2}$), so the
Monotone Convergence Theorem implies that it converges.

Letting $x = \lim x_n$ and taking the limit across the recursion equation, we obtain the
equation

$$
x = \frac{1}{2} \left( x + \frac{2}{x} \right),
$$

which has the solutions $x = \pm \sqrt{2}.$ Since the Order Limit Theorem implies that
$x \ge \sqrt{2}$, the limit of $(x_n)$ must be the positive solution to the equation.

#### 2.4.5.b.

__Problem__. Modify the sequence $(x_n)$ so that it converges to $\sqrt{c}.$

__Solution__. Let $x_1 = c,$ and define the recurrence relation

$$
x_{n+1} = \frac{1}{2} \left( x_n + \frac{c}{x_n} \right).
$$

The proof for convergence and derivation of the limit are identical to the proof in part
(a) with $2$ replace with $c$ in all locations except for the the factor of $1/2$ in the
recursion equation.

--------------------------------------------------------------------------------------------
### 2.4.6. Arithmetic-Geometric Mean

#### 2.4.6.a.

__Problem__. Explain why $\sqrt{xy} \le (x + y) / 2$ for any two positive real numbers $x$
and $y.$. (The geometric mean is always less than the arithmetic mean.)

__Solution__. For any positive real numbers $x$ and $y,$ observe that
$\left( \sqrt{x} - \sqrt{y} \right)^2 \ge 0,$ which implies that
$x - 2 \sqrt{xy} + y \ge 0$. Rearranging this inequality yields the desired result.

#### 2.4.6.b.

__Problem__. Now let $0 \le x_1 \le y_1$ and define

$$
x_{n+1} = \sqrt{x_n y_n}
$$

and

$$
y_{n+1} = \frac{x_n + y_n}{2}.
$$

Show $\lim x_n$ and $\lim y_n$ both exists and are equal.

__Solution__. First, observe that by the AM-GM inequality, $x_n \le y_n$ for all $n$.
From this observation, we can conclude that $(x_n)$ is monotone increasing and $(y_n)$ is
monotone decreasing:

* $x_{n+1} = \sqrt{x_n y_n} \ge \sqrt{x_n^2} = x_n$ and

* $y_{n+1} = (x_n + y_n) / 2 \le (y_n + y_n) / 2 = y_n.$

Moreover, $(x_n)$ is bounded above by $y_1$ because $x_n \le y_n \le y_1$. Similarly,
$(y_n)$ is bounded below by $x_1$ because $y_n \ge x_n \ge x_1$. Therefore, both $(x_n)$
and $(y_n)$ are monotone and bounded, so the Monotone Convergence Theorem implies that they
both converge.

Let $x = \lim x_n$ and $y = \lim y_n$. Taking the limit across both recursion equations,
we obtain the following equations for $x$ and $y$:

$$
\begin{align}
x &= \sqrt{xy} \\
y &= \frac{x + y}{2} \\
\end{align}
$$

which both lead to the conclusion that $x = y.$

--------------------------------------------------------------------------------------------
### 2.4.7. Limit Superior

Let $(a_n)$ be a bounded sequence.

#### 2.4.7.a.

__Problem__. Prove that the sequence defined by $y_n = \sup\{ a_k : k \ge n \}$ converges.

__Solution__. Observe that $y_n$ is a monotone decreasing sequence because $A \subseteq B$
implies that $\sup A \le \sup B$ and $\{ a_k : k \ge n+1 \} \subseteq \{ a_k : k \ge n \}.$
Furthermore, because $(a_n)$ is bounded, there exists $M \le a_n$ for all $n,$ which
implies that $M \le a_n \le y_n$ for all $n.$ Thus, we can conclude that $(y_n)$ is bounded.
Therefore, since $(y_n)$ is monotone and bounded, it converges by the Monotone Convergence
Theorem.

#### 2.4.7.b.

__Problem__. The _limit superior_ of $(a_n),$ or $\lim \sup a_n,$ is defined by

$$
\lim \sup a_n = \lim y_n,
$$

where $y_n$ is the sequence from part (a) of this exercise. Provide a reasonable definition
of $\lim \inf a_n$ and briefly explain why it always exists for any bounded sequence.

__Solution__. $\lim \inf a_n = \lim z_n$ where $z_n = \inf \{ a_k : k \ge n \}.$ Using
reasoning analogous to part (a), $\lim \inf a_n$ always exists because $z_n$ is monotone
increasing and bounded.

#### 2.4.7.c.

__Problem__. Prove that $\lim \inf a_n \le \lim \sup a_n$ for every bounded sequence, and
give an example of a sequence for which the inequality is strict.

__Solution__. Observe that $z_n \le y_n$ (by the definition of $\sup$ and $\inf$).
Therefore, $\lim z_n \le \lim y_n$ by the Order Limit Theorem.

As an example where $\lim \inf a_n$ is strictly less than $\lim \sup a_n,$ consider the
sequence $a_n = (-1)^n$. Then $\lim \inf a_n = -1$ and $\lim \sup a_n = 1.$

#### 2.4.7.d.

__Problem__. Show that $\lim \inf a_n = \lim \sup a_n$ if and only if $\lim a_n$ exists. In
this case, all three share the same value.

__Solution__. ($\Rightarrow$). Suppose that $\lim \inf a_n = \lim \sup a_n = a.$ Let
$\epsilon > 0.$ Then there exists $N_z, N_y$ such that $n \ge N_z$ implies that
$|z_n - a| < \epsilon / 3$ and $n \ge N_y$ implies that $|y_n - a| < \epsilon / 3.$ Let
$N = \max(N_z, N_y).$ Then for $n \ge N,$

$$
|y_n - z_n|
= |y_n - a + a - z_n|
\le |y_n - a| + |a - z_n|
< \frac{2 \epsilon}{3}.
$$

Next, observe that

$$
z_n = \inf\{a_k : k \ge n\}
\le a_n
\le \sup\{a_k : k \ge n\} = y_n,
$$

which implies that $|a_n - z_n| \le |y_n - z_n| < 2 \epsilon / 3.$

Thus, we can conclude that

$$
|a_n - a|
= |a_n - z_n + z_n - a|
\le |a_n - z_n| + |z_n - a|
< \frac{2 \epsilon}{3} + \frac{\epsilon}{3}
= \epsilon,
$$

which shows that $(a_n)$ converges to $a$ and all three limits have the same value.

($\Leftarrow$). Suppose that $\lim a_n = a.$ Let $\epsilon > 0.$ Then there exist
$N \in \N$ such that $|a_n - a| < \epsilon / 2$ for all $n \ge N,$ which implies that
$a - \epsilon / 2 < a_n < a + \epsilon/ 2$ for all $n \ge N.$ By the definition
$z_n = \inf\{ a_k : k \ge n \},$

* $z_n < a + \epsilon / 2$ because $z_n$ a lower bound for $\{ a_k : k \ge n \},$ and

* $z_n \ge a - \epsilon / 2$ because $z_n$ is no less than any lower bound for
  $\{ a_k : k \ge n \}$ and $a - \epsilon / 2$ is one such lower bound.

Since $a + \epsilon / 2 < a + \epsilon$ and $a - \epsilon / 2 > a - \epsilon$ (strict
inequalities), we can conclude that $a - \epsilon < z_n < a + \epsilon.$ for $n \ge N.$
In other words, for sufficiently large $n$, $|z_n - a| < \epsilon,$ which shows that
$(z_n) \rightarrow a.$ An analogous argument shows that $(y_n)$ also converges to $a,$
which yields the desired result: $\lim \inf a_n = \lim \sup a_n.$

--------------------------------------------------------------------------------------------
### 2.4.8.

__Problem__. For each series, find an explicit formula for the sequence of partial sums and
determine if the series converges.

(a)
$$
\sum_{n=1}^\infty \frac{1}{2^n}
$$

(b)
$$
\sum_{n=1}^\infty \frac{1}{n(n+1)}
$$

(c)
$$
\sum_{n=1}^\infty \log \left( \frac{n+1}{n} \right)
$$

__Solution__.

(a)

$$
s_n
= \sum_{k=1}^n \frac{1}{2^k}
= \frac{1/2 - 1/2^{n+1}}{1/2}
= 1 - \frac{1}{2^n}.
$$

Therefore, $s_n$ converges to $1.$

(b)

$$
s_n
= \sum_{k=1}^n \frac{1}{k (k+1)}
= \sum_{k=1}^n \frac{1}{k} - \frac{1}{k+1}
= 1 - \frac{1}{n+1}
$$

Therefore, $s_n$ converges to $1.$

(c)

$$
s_n
= \sum_{k=1}^n \log\left( \frac{k + 1}{k} \right)
= \sum_{k=1}^n \log(k + 1) - \log(k)
= \log(n+1) - \log(1)
= \log(n+1)
$$

Therefore, $s_n$ diverges as $n \rightarrow \infty.$

--------------------------------------------------------------------------------------------
### 2.4.9.

__Problem__. Complete the proof of Theorem 2.4.6 by showing that if the series
$\sum_{n=0}^\infty 2^n b_{2^n}$ diverges, then so does $\sum_{n=0}^\infty b_n.$ Example
2.4.5 may be a useful reference.

_Theorem 2.4.6 (Cauchy Condensation Test)_. Suppose $(b_n)$ is decreasing and satisfies
$b_n \ge 0$ for all $n \in N.$ Then, the series $\sum_{n=1}^\infty b_n$ converges if and
only if the series

$$
\sum_{n=0} 2^n b_{2^n} = b_1 + 2 b_2 + 4 b_4 + 8 b_8 + 16 b_{16} + \cdots
$$

converges.

__Solution__. ($\Rightarrow$) Define

$$
t_k = \sum_{n = 0}^k 2^n b_{2^n}.
$$

Suppose that $(t_k)$ diverges. Let $M > 0.$ Since $(t_k)$ is monotone increasing, it must
be unbounded (otherwise the Monotone Convergence Theorem would imply that $(t_k)$
converges). Thus, there exists $k \in \N$ such that $t_k > 2M,$ which implies that for
$n \ge 2^k,$

$$
\begin{align}
s_n
&> s_{2^k} \\
&= b_1 + b_2 + b_3 + b_4 + \cdots + b_{2^k} \\
&= b_1 + b_2 + (b_3 + b_4) + \cdots
 + (b_{2^{k-1} + 1} + b_{2^{k-1} + 2} + \cdots + b_{2^k}) \\
&\ge b_1 + b_2 + (b_4 + b_4) + \cdots + (b_{2^k} + b_{2^k} + \cdots + b_{2^k}) \\
&= b_1 + b_2 + 2 b_4 + \cdots + 2^{k-1} b_{2^k} \\
&= \frac{b_1}{2} + \frac{1}{2} \sum_{n=0}^k 2^k b_{2^k} \\
&> \frac{b_1}{2} + M \\
&> M.
\end{align}
$$

Therefore, $s_n$ is unbounded, which implies that it does not converge.

--------------------------------------------------------------------------------------------
### 2.4.10. Infinite Products

A close relative of infinite series is the _infinite product_

$$
\prod_{n=1}^\infty b_n = b_1 b_2 b_3 \cdots
$$

which is understood in terms of its sequence of _partial products_

$$
p_m = \prod_{n=1}^m b_n = b_1 b_2 b_3 \cdots b_m.
$$

Consider the special class of infinite products of the form

$$
\prod_{n=1}^\infty (1 + a_n) = (1 + a_1) (1 + a_2) (1 + a_3)  \cdots,
$$

where $a_n \ge 0.$

#### 2.4.10.a.

__Problem__. Find an explicit formula for the sequence of partial products in the case where
$a_n = 1/n$ and decide whether the sequence converges. Write out the first few terms in
the sequence of partial products in the case where $a_n = 1/n^2$ and make a conjecture
about the convergence of this sequence.

__Solution__. When $a_n = 1/n,$ observe that

$$
1 + a_n
= 1 + \frac{1}{n}
= \frac{n + 1}{n}.
$$

Thus,

$$
p_m
= (1 + a_1) (1 + a_2) \cdots (1 + a_m)
= \left( \frac{2}{1} \right) \left( \frac{3}{2} \right) \cdots \left( \frac{m+1}{m} \right)
= m + 1,
$$

which implies that the sequence of partial products $p_m$ diverges.

When $a_n = 1/n^2,$ observe that

$$
1 + a_n
= 1 + \frac{1}{n^2}
= \frac{n^2 + 1}{n^2}.
$$

The first few partial products are

$$
\begin{align}
p_1
&= \frac{2}{1} = 2 \\
p_2
&= \left( \frac{5}{4} \right) \left( \frac{2}{1} \right) = \frac{5}{2} = 2.5 \\
p_3
&= \left( \frac{10}{9} \right) p_2 = \frac{25}{9} \approx 2.78 \\
p_4
&= \left( \frac{17}{16} \right) p_3 = \frac{425}{144} \approx 2.95 \\
p_5
&= \left( \frac{26}{25} \right) p_4 = \frac{221}{72} \approx 3.07 \\
\end{align}
$$

Conjecture: the sequence $(p_m)$ converges because the gaps between successive partial
products appears to be decreasing.

#### 2.4.10.b.

__Problem__. Show, in general, that the sequence of partial products converges if and only
if $\sum_{n=1}^\infty a_n$ converges. (The inequality $1 + x \le 3^x$ for positive $x$ will
be useful in one direction.)

__Solution__. ($\Rightarrow$) Suppose that $\sum_{n=1}^\infty a_n$ converges. Then,
recalling that $1 + x \le e^x \le 3^x$,

$$
p_m
= \prod_{n=1}^m (1 + a_n)
\le \prod_{n=1}^m 3^{a_n}
= 3^{\sum_{n=1}^m a_n}
$$

Since $a_n \ge 0,$ the partial sume $s_m = \sum_{n=1}^m a_n$ is a monotone increasing
sequence. Thus, the sequence of partial products $p_m$ is a monotone increasing sequence.
Moreover, $(p_m)$ is bounded above by $3^s$ where $s = \sum{n=1}^\infty s_n.$ Therefore,
the infinite product converges.

($\Leftarrow$) Suppose that $\prod_{n=1}^\infty (1 + a_n)$ converges. Then, the sequence
of partial products $(p_m)$ is bounded by $M > 0.$ Observe that

$$
p_m
= \prod_{n=1}^m (1 + a_n)
\ge 1 + \sum_{n=1}^m a_n.
$$

Thus, we can conclude that the partial sums $s_m$ are bounded from above because

$$
s_m = \sum_{n=1}^m a_n \le p_n - 1 \le M - 1.
$$

Therefore, $(s_m)$ is monotone increasing (because $a_n \ge 0$) and bounded, so the
Monotone Convergence Theorem implies that it must converge.

--------------------------------------------------------------------------------------------
