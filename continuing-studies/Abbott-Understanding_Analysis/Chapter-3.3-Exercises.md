Understanding Analysis (S. Abbott): Section 3.3 Exercises
=========================================================

--------------------------------------------------------------------------------------------
### Notation

* $\newcommand{\N}{\mathbb{N}}$
  The set of natural numbers: $\N$

* $\newcommand{\Q}{\mathbb{Q}}$
  The set of rational numbers: $\Q$

* $\newcommand{\R}{\mathbb{R}}$
  The set of real numbers: $\R$

* $\newcommand{\I}{\mathbb{I}}$
  The set of irrational numbers: $\I$

--------------------------------------------------------------------------------------------
### 3.3.1.

__Problem__. Show that if $K$ is compact and nonempty, then $\sup K$ and $\inf K$ both
exist and are elements of $K$.

__Solution__. Since $K$ is compact and nonempty, it is closed and bounded. The boundedness
of $K$ implies that $\sup K$ exists (by the Axiom of Completeness). By Lemma 1.3.8, for all
$n$, there exists $x_n \in K$ such that $\sup K - 1/n < x_n \le \sup K$, so we can
construct a sequence $(x_n)$ whose limit is $\sup K$. In other words, $\sup K$ is a limit
point of $K$, which implies that $\sup K \in K$ because $K$ is closed.

An analogous argument implies that $\inf K$ exists and is an element of $K$.

--------------------------------------------------------------------------------------------
### 3.3.2.

__Problem__. Decide which of the following sets are compact. For those that are not
compact, show how Definition 3.3.1 breaks down. In other words, give an example of a
sequence contained in the given set that does not possess a subsequence converging to a
llmit in the set.

a) $\N$.

b) $\Q \cap [0, 1]$.

c) The Cantor set.

d) $\{1 + 1/2^2 + 1/3^2 + \cdots + 1/n^2 : n \in \N\}$.

e) $\{1, 1/2, 2/3, 3/4, 4/5, \ldots\}$.

__Solution__.

a) $\N$ is not compact because the sequence $\{1, 2, 3, \ldots\}$ does not converge.

b) $\Q \cap [0, 1]$ is not compact because it does not contain all of its limit points.
   As a counterexample, consider the sequence of decimal approximations to $\sqrt{2}$.

c) The Cantor set is compact because it is closed and bounded. It is closed because it is
   the complement of a union of open sets (the removed sets).

d) This set is not compact because the limit of the sequence of partial sums
   $S_n = 1 + 1/2^2 + 1/3^2 + \cdots + 1/n^2$ is $\pi^2 / 6$, but $\pi^2 / 6$ is not
   contained in the set.

e) This set is compact because it is closed and bounded. It is closed because the only
   limit point of the set is $1$, which is contained in the set.

   TODO: why do we know that $1$ is the only limit point?

--------------------------------------------------------------------------------------------
### 3.3.3.

__Problem__. Prove the converse of Theorem 3.3.4 by showing that if a set is
$K \subseteq \R$ is closed and bounded, then it is compact.

__Solution__. Let $(x_i)$ be a sequence where $x_i \in K$. Since $K$ is bounded, the
Bolzano-Weierstrass Theorem implies that $(x_i)$ has a convergent subsequence $(x_{i_j})$.
Because $K$ is closed, the limit $x$ of $(x_{i_j})$ must be an element of $K$. In other
words, any sequence of $(x_i)$ contains a subsequence that converges to a limit in $K$.
Therefore, $K$ is compact.

--------------------------------------------------------------------------------------------
### 3.3.4.

__Problem__. Assume $K$ is compact and $F$ is closed. ecide if the following sets are
definitely compact, definitely closed, both, or neither.

a) $K \cap F$

b) $\overline{F^c \cup K^c}$

c) $K \backslash F = \{ x \in K : x \notin F\}$

d) $\overline{K \cap F^c}$

__Solution__.

a) $K \cap F$ is compact because

   * $K \cap F$ is closed (because arbitrary intersections of closed sets are closed) and

   * $K \cap F$ is bounded because $K \cap F \subseteq K$.

   Therefore, $K$ is definitely compact and closed.

b) By De Morgan's Laws, $\overline{F^c \cup K^c} = K \cap F$, so part (a) shows that
   $K \cap F$ must be both compact and closed.

c) $K \backslash F$ is bounded because $K \backslash F \subseteq K$. However, it is not
   guaranteed to be closed, so it is not necessarily compact. As a counterexample, consider
   $K = [0, 2]$ and $F = [0, 1]$. Then $K \backslash F = (1, 2]$, which is not closed.

d) By De Morgan's Law, $\overline{K \cap F^c} = K^c \cup F$, which is not guaranteed to be
   closed, so it is not necessarily compact. As a counterexample, consider $K = [-2, 2]$ and
   $F = [-1, 1]$. Then

   $$
   K^c \cup F
   = (-\infty, -2) \cup (2, \infty) \cup [-1, 1],
   $$

   which is not closed.

--------------------------------------------------------------------------------------------
### 3.3.5.

__Problem__. Decide whether the following propositions are true or false. If the claim is
valid, supply a short proof, and if the claim is false, provide a counterexample.

a) The arbitrary intersection of compact sets is compact.

b) The arbitrary union of compact sets is compact.

c) Let $A$ be arbitrary, and let $K$ be compact. Then, the intersection $A \cap K$ is
   compact.

d) If $F_1 \supseteq F_2 \supseteq F_3 \supseteq F_4 \supseteq \cdots$ is a nested
   sequence of nonempty closed sets, then the intersection
   $\bigcap_{n=1}^\infty F_n \ne \emptyset$.

__Solution__.

a) True. Let $K$ be the intersection of an arbitrary collection of compact sets. Then $K$
  closed because arbitrary intersections of closed sets are closed. Furthermore, $K$ is
  bounded because $K$ is contained in any set $A$ in the collection, which implies that it
  is bounded any bound for $A$. Therefore, $K$ is compact.

b) False. Consider the collection of compact sets $A_n = [n-1, n]$ for $n \in \N$. Then
   $\bigcup_{n=1}^\infty A_n = [0, \infty)$, which is not bounded and so cannot be compact.

c) False. Consider $A = (0, 1)$ and $K = [0, 2]$. Then $A \cap K = (0, 1)$, which is not
   closed and so cannot be compact.

d) True. If all of the $F_n$ are unbounded, then clearly $\bigcap_{n=1}^\infty F_n$ is
   unbounded and therefore nonempty. If $F_n$ is bounded for some $n \in N$, then the
   $F_n, F_{n+1}, \ldots$ is a sequence of compact sets, so their intersection is nonempty
   by the Nested Compact Set Property.

--------------------------------------------------------------------------------------------
### 3.3.6.

__Problem__. This exercise is meant to illustrate the point made in the opening paragraph
to Section 3.3. Verify that the following three statements are true if every blank is
filled with the word "finite." Which are true if every blank is filled with the word
"compact." Which are true if every blank is filled in with the word "closed."

a) Every (blank) set has a maximum.

b) If $A$ and $B$ are (blank), then $A + B = \{ a + b : a \in A, b \in B \}$ is also
   (blank).

c) If $\{ A_n : n \in \N \}$ is a collection of (blank) sets with the property that every
   finite subcollection has a nonempty intersection, then $\bigcap_{n=1}^\infty A_n$ is
   nonempty as well.

__Solution__. For all cases, assume nonempty sets of real numbers.

a) For finite sets, this statement is true because we can list all of the elements of the
   set. For compact sets, this statement is true by the result of Exercise 3.3.1. For
   closed sets, this statement is not true because the set may be unbounded (e.g., $\N$).

b) For finite sets, this statement is true because we can list all of the elements of
   $A + B$. For compact sets, this statement is true because the compactness of $A$ and
   $B$ combined with the Algebraic Limit Theorem for sequences imply that any sequence
   $(x_i)$ with $x_i \in A + B$ has a subsequence that converges to a limit in $A + B$.
   For closed sets, this statement is true because the closedness of $A$ and $B$ combined
   with the Algebraic Limit Theorem for sequences imply that any limit point of $A + B$
   is an element of $A + B$.

c) TODO

--------------------------------------------------------------------------------------------
### 3.3.7.

As some more evidence of the surprising nature of the Cantor set, follow these steps to
show that the sum $C + C = \{ x + y : x, y \in C \}$ is equal to the closed interval
$[0, 2]$. (Keep in mind that $C$ has zero length and contains no intervals).

Because $C \subseteq [0, 1]$, $C + C \subseteq [0, 2]$, we only need to prove the reverse
inclusion $[0, 2] \subseteq \{ x + y, : x, y \in C \}$. Thus, given $s \in [0, 2]$, we must
find two elements $x, y \in C$ satisfying $x + y = s$.

#### 3.3.7.a.

__Problem__. Show that there exist $x_1, y_1 \in C_1$ for which $x_1 + y_1 = s$. Show in
general that, for an arbitrary $n \in \N$, we can always find $x_n, y_n \in C$ for which
$x_n + y_n = s$.

__Solution__. Let $s \in [0, 2]$. To show that $s = x_1 + y_1$ with $x_1, y_1 \in C_1$, we
consider the following six cases.

* $0 \le s \le 1/3$. $x_1 = 0$ and $y_1 = s - x_1 \in [0, 1/3]$ satisfies the desired
  conditions.

* $1/3 < s \le 2/3$. $x_1 = 1/3 \in [0, 1/3]$ and $y_1 = s - x_1 \in [0, 1/3]$ satisfies
  the desired conditions.

* $2/3 < s \le 1$. $x_1 = 2/3 \in [2/3, 1]$ and $y_1 = s - x_1 \in [0, 1/3]$ satisfies the
  desired conditions.

* $1 < s \le 4/3$. $x_1 = 1/3 \in [0, 1/3]$ and $y_1 = s - x_1 \in [2/3, 1]$ satisfies the
  desired conditions.

* $4/3 < s \le 5/3$. $x_1 = 2/3 \in [2/3, 1]$ and $y_1 = s - x_1 \in [2/3, 1]$ satisfies the
  desired conditions.

* $5/3 < s \le 2$. $x_1 = 1 \in [2/3, 1]$ and $y_1 = s - x_1 \in [2/3, 1]$ satisfies the
  desired conditions.

For arbitrary $n \in \N$, we generalize this approach. Break the interval $[0, 2]$ into
intervals of size $1/3^n$. For the first interval $[0, 1/3^n]$, $x_n = 0$ and
$y_n = s \in [0, 1/3^n]$ satisfies the desired conditions. The remaining $2 \cdot 3^n - 1$
intervals are of the form $(k / 3^n, (k+1) / 3^n]$ with $1 \le k \le 2 \cdot 3^n - 1$. We

__TODO__

#### 3.3.7.b.

__Problem__. Keeping in mind that the sequences $(x_n)$ and $(y_n)$ do not necessarily
converge, show how they can nevertheless be used to produce the desired $x$ and $y$ in $C$
satisfying $x + y = s$.

__Solution__. Since $(x_n)$ is bounded (because $C$ is bounded), the Bolzano-Weierstrass
theorem implies that it contains a convergent subsequence $(x_{n_k})$. Consider the
subsequence $(y_{n_k})$ of $(y_n)$. Since $(y_{n_k})$ is bounded, it contains a convergent
subsequence $(y_{n_{k_l}})$. Since $(x_{n_{k_l}})$ is a subsequence of $(x_{n_k})$, it is
also convergent.  $x$ and $y$ be the limits of $(x_{n_{k_l}})$ and $(y_{n_{k_l}})$,
respectively. Since the Cantor set is closed, $x$ and $y$ must be elements of of $C$.
By the Algebraic Limit Theorem, $x_{n_{k_l}} + y_{n_{k_l}} \rightarrow x + y$ as
$l \rightarrow \infty$. Since $x_{n_{k_l}} + y_{n_{k_l}} = s$ by construction, $x + y = s$,
which proves the desired result.

--------------------------------------------------------------------------------------------
### 3.3.8.

Let $K$ and $L$ be nonempty compact sets, and define

$$
d = \inf \{ |x - y| : x \in K \textrm{ and } y \in Y \}.
$$

It turns out to be a reasonable definition of the _distance_ between $K$ and $L$.

### 3.3.8.a.

__Problem__. If $K$ and $L$ are disjoint, show $d > 0$ and that $d = |x_0 - y_0|$ for some
$x_0 \in K$ and $y_0 \in L$.

__Solution__. TODO

### 3.3.8.b.

__Problem__. Show that it's possible to have $d = 0$ if we assume only that the disjoint
sets $K$ and $L$ are closed.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 3.3.9.

Follow these steps to prove the final implication of Theorem 3.3.8.

Assume $K$ satisfies (i) and (ii), and let $\{ O_\lambda : \lambda \in \Lambda \}$ be an
open cover for $K$. For contradiction, let's assume that no finite subcover exists. Let
$I_0$ be a closed interval containing $K$.

#### 3.3.9.a.

__Problem__. Show that there exists a nested sequence of closed intervals
$I_0 \supseteq I_1 \supseteq I_2 \supseteq \cdots$ with the property that, for each $n$,
$I_n \cap K$ cannot be finitely covered and $\lim |I_n| = 0$.

__Solution__. TODO

#### 3.3.9.b.

__Problem__. Argue that there exists an $x \in K$ such that $x \in \I_n$ for all $n$.

__Solution__. TODO

#### 3.3.9.c.

__Problem__. Because $x \in K$, there must exist an open set $O_{\lambda_0}$ from the
original collection that contains $x$ as an element. Explain how this leads to the desired
contradiction.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 3.3.10.

__Problem__. TODO

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 3.3.11.

__Problem__. Consider each of the sets listed in Exercise 3.3.2. For each one that is not
compact, find an open cover for which there is no finite subcover.

__Solution__.

a) The sets $O_n = (n - 1/3, n + 1/3)$ for $n = 1, 2, 3, \ldots$ are an open cover of
   $\N$ with no finite subcover.

b) TODO
   an open cover of $\Q \cap [0, 1]$.

d) Let $s_n = \sum_{i=1}^n 1/i^2$ for $n \in \N$ and define

   $$
   O_n = \left( s_n - \frac{1}{3(n+1)^2}, s_n + \frac{1}{3(n+1)^2} \right)
   $$

   Clearly, $\{ O_1, O_2, \ldots \}$ are an open cover for
   $S = \{1 + 1/2^2 + 1/3^2 + \cdots + 1/n^2 : n \in \N\}$.

   Observe that $s_{n+1} = s_n + 1 / (n+1)^2$, which implies that

   $$
   \begin{align}
   s_{n+1} - \frac{1}{3(n+2)^2}
   &> s_{n+1} - \frac{1}{3(n+1)^2} \\
   &= s_n + \frac{1}{(n+1)^2} - \frac{1}{3(n+1)^2} \\
   &= s_n + \frac{2}{3(n+1)^2} \\
   &> s_n + \frac{1}{3(n+1)^2}.
   \end{align}
   $$

   It follows that $O_n \cap O_{n+1} = \emptyset$ for all $n$, so each $O_n$ contains only
   a single point in $S$. Therefore, $\{ O_n \}$ contains no finite subcover for $S$.

--------------------------------------------------------------------------------------------
### 3.3.12.

__Problem__. Using the concept of open covers (and explicitly avoiding the
Bolzano-Weierstrass Theorem), prove that every bounded infinite set has a limit point.

__Solution__. Let $S$ be an infinite bounded set. Suppose that $S$ has no limit points.
Then $S$ is closed (because it contains all of its non-existent limit points), so it must
be compact. Let $S_1 = S$ and consider the open cover
$\Omega_1 = \{ (s - 1, s + 1) : s \in S_1 \}$. Since $S_1$ is compact, $\Omega_1$ contains
a finite subcover. Observe that at least one of the open intervals in the finite subcover,
say $(s_1 - 1, s_1 + 1)$, must be infinite because $S_1$ is infinite. Recursively define
$S_{n+1} = S_n \cap (s_n - 1/n, s_n + 1/n)$ where $s_n \in S_n$ such that

* $(s_n - 1/n, s_n + 1/n)$ is an interval in the finite subcover contained in the open
  cover $\Omega_n = \{ (s - 1/n, s + 1/n) : s \in S_n \}$ for $S_n$ and

* $(s_n - 1/n, s_n + 1/n)$ contains an infinite number of points from $S_n$.

Note this recursive procedure is well-defined because $S_{n+1}$ is compact whenever $S_n$
is compact (because the intersection of a closed set with an open set is closed and the
intersection of a finite number of bounded sets is bounded). Furthermore, note that
$S = S_1 \supset S_2 \supset S_3 \supset \cdots$ is a nested sequence of infinite sets, so
$s_n \in S$ for all $n$.

Now, consider a sequence $(a_n)$ constructed by selecting one element $a_n$ from each $S_n$.
Then $(a_n)$ is a Cauchy sequence because $a_n \in (s_N - 1/N, s_N + 1/N)$ for $n > N$
implies that $|a_n - a_m| < 2/N$ whenever $n, m > N$ (so choosing $N > 2/\epsilon$ yields
the required condition $|a_n - a_m| < \epsilon$ for any $\epsilon > 0$). Therefore, $(a_n)$
converges, which implies that $S$ has a limit point because $a_n \in S$ for all $n$. This
conclusion contradicts our assumption that $S$ has no limit points, so it must be the case
that $S$ has at least one limit point.

--------------------------------------------------------------------------------------------
### 3.3.13.

__Problem__. TODO

__Solution__. TODO

--------------------------------------------------------------------------------------------
