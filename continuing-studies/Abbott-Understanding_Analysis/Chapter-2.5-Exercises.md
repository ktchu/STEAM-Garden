Understanding Analysis (S. Abbott): Section 2.5 Exercises
=========================================================

--------------------------------------------------------------------------------------------
### Notation

* $\newcommand{\N}{\mathbb{N}}$
  The set of natural numbers: $\N$

* $\newcommand{\R}{\mathbb{R}}$
  The set of real numbers: $\R$

--------------------------------------------------------------------------------------------
### 2.5.1.

__Problem__. Give an example of each of the following, or argue that such a request is
impossible.

(a) A sequence that has a subsequence that is bounded but contains no subsequence that
converges.

(b) A sequence that does not contain $0$ or $1$ as a term but contains subsequences
converging to each of these values.

(c) A sequence that contains subsequences converging to every point in the infinite set
$\{1, 1/2, 1/3, 1/4, 1/5, \ldots\}.$

(d) A sequence that contains subsequences converging to every point in the infinite set
$\{1, 1/2, 1/3, 1/4, 1/5, \ldots\},$ and no subsequences converging to points outside of
this set.

__Solution__.

(a) This request is impossible to satisfy because the Bolzano-Weierstrauss Theorem
requires that the bounded subsequence has a convergent subsequence $(x_n).$ Since $(x_n)$
is also a subsequence of the original sequence, the original sequence contains a convergent
subsequence.

(b) The following sequence satisfies the request:

$$
\left(
  \frac{1}{3}, \frac{2}{3}, \frac{1}{4}, \frac{3}{4}, \frac{1}{5}, \frac{4}{5}, \ldots
\right)
$$

(c) The following sequence satisfies the request:

$$
\left(
  1, \frac{1}{2}, 1, \frac{1}{2}, \frac{1}{3}, 1, \frac{1}{2}, \frac{1}{3}, \frac{1}{4},
  \ldots
\right)
$$


(d) This request is impossible to satisfy because TODO

IDEA. We can always construct a subsequence that converges to $0.$

--------------------------------------------------------------------------------------------
### 2.5.2.

Decide whether the following propositions are true or false, providing a short
justification for each conclusion.

#### 2.5.2.a.

__Problem__. If every proper subsequence of $(x_n)$ converges, then $(x_n)$ converges as
well.

__Solution__. This proposition is true. Consider the proper subsequence $(y_n)$ formed by
removing the first element of $(x_n).$ By assumption $(y_n)$ converges. Since the $(y_n)$
is just a shift of the $(x_n),$ the sequence $(x_n)$ must also converge.

#### 2.5.2.b.

__Problem__. If $(x_n)$ contains a divergent subsequence, then $(x_n)$ diverges.

__Solution__. This proposition is true because Theorem 2.5.2 requires that all subsequences
of convergent sequences converge.

#### 2.5.2.c.

__Problem__. If $(x_n)$ is bounded and diverges, then there exist two subsequences of
$(x_n)$ that converge to different limits.

__TODO__: Is there a shorter justificaton based on contrapositive argument?

__Solution__. This proposition is true. Since $(x_n)$ is bounded, the Bolzano-Weierstrass
Theorem implies that $(x_n)$ contains a convergent subsequence. Let $x$ be the limit of the
convergent subsequence. Choose $\epsilon > 0$ such that $(x - \epsilon) \ge \inf x_n$ or
$(x + \epsilon) \le \sup x_n$ (both $\inf$ and $\sup$ exist because $(x_n)$ is bounded). In
other words, we choose $\epsilon$ so that the the complement of interval
$(x - \epsilon, x + \epsilon)$  in $[\inf x_n, \sup x_n]$ is not empty. Since $(x_n)$ is
not convergent, for every $N \in \N$ we can find $n \ge N$ such that $|x_n - x| > \epsilon.$
Consider the subsequence of $(x_n)$ formed by finding a subsequence of $\{1, 2, 3, \ldots\}$
satisfying $|x_n - x| > \epsilon.$ This subsequence is bounded (because $(x_n)$ is bounded),
so it contains a convergent subsequence $(y_{n_k}).$ Let
$y = \lim_{k \rightarrow \infty} y_{n_k}.$ Then $y \ne x$ because for sufficiently large
$k,$ $|y_{n_k} - y| < \epsilon / 2$ which implies that

$$
|x - y|
\ge ||x - y_{n_k}| - |y - y_{n_k}||
\ge \epsilon - \epsilon / 2
> 0,
$$

where the lower bound on $|x - y_{n_k}|$ follows because $(y_{n_k})$ is a subsequence
of a sequence consisting of terms in $(x_n)$ that are greater than $\epsilon$ away from
$x.$

#### 2.5.2.d.

__Problem__. If $(x_n)$ is monotone and contains a convergent subsequence, then $(x_n)$
converges.

__Solution__. This proposition is true. It is straightforward to prove the contrapositive.
If $(x_n)$ is monotone and diverges, then it is unbounded. Since any subsequence of a
monotone unbounded sequence must also be unbounded, they all must diverge.

--------------------------------------------------------------------------------------------
### 2.5.3.

#### 2.5.3.a.

__Problem__. Prove that if an infinite series converges, then the associative property
holds. Assume $a_1 + a_2 + a_3 + a_4 + a_5 + \cdots$ converges to a limit $L$ (i.e., the
sequence of partial sums $(s_n) \rightarrow L$). Show that any regrouping of the terms

$$
(a_1 + a_2 + \cdots + a_{n_1})
+ (a_{n_1+1} + \cdots + a_{n_2})
+ (a_{n_2+1} + \cdots + a_{n_3})
+ \cdots
$$

leads to a series that also converges to $L.$

__Solution__. Observe that sequence of the partial sums $(t_k)$ of any regrouping of the
terms is a subsequence of ithe partial sums $(s_n).$ Since any subsequences of a convergent
sequence must converge to the same limit, $(t_k) \rightarrow L,$ which yields the desired
result.

#### 2.5.3.b.

__Problem__. Compare this result to the example discussed at the end of Section 2.1 where
infinite addition was shown not to be associative. Why doesn't our proof in (a) apply to
this example?

__Solution__. The sequence $\sum{n=1}^\infty (-1)^n$ discussed at the end of Section 2.1
does not converge, so part (a) does not apply.

--------------------------------------------------------------------------------------------
### 2.5.4.

__Problem__. The Bolzano-Weierstrass Theorem is extremely important, and so is the strategy
employed in the proof. To gain some more experience with this technique, assume the Nested
Interval Property is true and use it to provide a proof of the Axiom of Completeness. To
prevent the argument from being circuluar, assume also that $(1/2^n) \rightarrow 0.$ (Why
precisely is this last assumption needed to avoid circularity?)

__Solution__. TODO

We need to assume that $(1/2^n) \rightarrow 0$ because proving this result relies on the
Monotone Convergence Theorem which is a consequence of the Axiom of Completeness.

--------------------------------------------------------------------------------------------
### 2.5.5.

__Problem__. Assume $(a_n)$ is a bounded sequence with the property that every convergent
subsequence of $(a_n)$ converges to the same limit $a \in \R.$ Show that $(a_n)$ must
converge to $a.$

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 2.5.6.

__Problem__. Use a similar strategy to the one in Example 2.5.3 to show $\lim b^{1/n}$
exists for all $b \ge 0$ and find the value of the limit. (The results in Exercise 2.3.1
may be assumed.)

__Solution__. If $b \le 1,$ then the sequence $(b^{1/n})$ is monotone increasing. Since
$b \le 1$ also implies that $b^{1/n} \le 1$ for all $n,$ $(b^{1/n})$ is bounded above.
Therefore, $(b^{1/n})$ converges by the Monotone Convergence Theorem.

If $b > 1,$ then the sequence $(b^{1/n})$ is monotone decreasing. Since $b > 1$ also
implies that $b^{1/n} > 1$ for all $n,$ $(b^{1/n})$ is bounded below. Again, the Monotone
Convergence Theorem requires that $(b^{1/n})$ converges.

Consider the subsequence $(b^{1/2n})$. Since $(b^{1/n})$ and $(b^{1/2n})$ have the same
limit $l$ and $b^{1/2n} = \sqrt{b^{1/n}},$ $l$ satisfies the equation $l = \sqrt{l}$
(where the result from Exercise 2.3.1 is used to conclude that
$\sqrt{b^{1/n}} \rightarrow \sqrt{l}$.) Therefore, $l = 1$ or $l = 0.$ When $b = 0,$, then
$b^{1/n} = 0$ for all $n,$ which implies that the limit exists and is equal to $0.$ When
$b > 0,$ $b^{1/n}$ is strictly positive. In this case, $\lim b^{1/n} = 1.$

--------------------------------------------------------------------------------------------
### 2.5.7.

__Problem__. Extend the result proved in Example 2.5.3 to the case $|b| < 1;$ that is,
show $\lim (b^n) = 0$ if and only if $-1 < b < 1.$

__Solution__. If $-1 < b < 1$, then the argument in Example 2.5.3 shows that
$|b|^n \rightarrow 0$. From the definition of convergence, for every $\epsilon > 0$ there
exists $N \in \N$ such that $n \ge N$ implies that $| |b|^n | < \epsilon$. Since
$|b^n - 0| = |b^n| = ||b|^n|$, the convergence of the sequence $(|b|^n)$ to $0$ implies
that $\lim (b^n) = 0$.

To show that $\lim(b_n) \ne 0$ when $b > 1$ or $b < -1$, we need to consider three cases:
$b = 1$, $b = -1$, $|b| > 1$. If $b = 1$, then $b^n = 1$ for all $n$, so
$\lim (b^n) = 1 \ne 0$. If $b = -1$, then the subsequences
$(b^0, b^2, b^4, \ldots) \rightarrow 1$ and $(b^1, b^3, b^5, \ldots) \rightarrow -1$
converge to different limits, so $(b^n)$ diverges. If $|b| > 1$, then the sequence $(b^n)$
is unbounded (because for any $M > 0$, $n \ge \ln M / \ln |b|$ implies that
$|b^n| = |b|^n > M$), so $(b_n)$ diverges.

--------------------------------------------------------------------------------------------
### 2.5.8.

Another way to prove the Bolzano-Weierstrass Theorem is to show that every sequence
contains a monotone subsequence. A useful device in this endeavor is the notion of a
_peak term_. Given a sequence $(x_n),$ a particular term $x_m$ is a peak term if no later
term in the sequence exceeds it; i.e., if $x_m \ge x_n$ for all $n \ge m.$

#### 2.5.8.a.

__Problem__. Find examples of sequences with zero, one, and two peak terms. Find an example
of a sequence with infinitely many peak terms that is not monotone.

__Solution__. TODO

#### 2.5.8.b.

__Problem__. Show that eery sequence contains a monotone subsequence and explain how this
furnishes a new proof of the Bolzano-Weierstrass Theorem.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 2.5.9.

__Problem__. Let $(a_n)$ be a bounded sequence, and define the set

$$
S = \{ x \in \R: x < a_n \textrm{ for infinitely  many terms $a_n$} \}.
$$

Show that there exists a subsequence $(a_{n_k})$ converging to $s = \sup S.$ (This is a
direct proof of the Bolzano-Weierstrass Theorem using the Axiom of Completeness.)

__Solution__. TODO

--------------------------------------------------------------------------------------------
