Understanding Analysis (S. Abbott): Section 3.2 Exercises
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
### 3.2.1.

#### 3.2.1.a.

__Problem__. Where in the proof of Theorem 3.2.3 part (ii) does the assumption that the
collection of open sets be _finite_ get used?

__Solution__. The assumption that the collection of open sets is finite is used to ensure
that $\epsilon$ is well-defined because infinite sets of real numbers are not guaranteed
have a minimum. Note that it is not possible to replace $\min$ with $\inf$ because
$\epsilon = \inf\{\epsilon_1, \epsilon_2, \epsilon_3, \ldots \}$ where $\epsilon_i > 0$
could be equal to $0$, which precludes the possibility of finding an
$\epsilon$-neighborhood contained in all of the $O_n$.

#### 3.2.1.b.

__Problem__. Give an example of a countable collection of open sets
$\{O_1, O_2, O_3, \ldots\}$ whose intersection $\cap_{n=1}^\infty O_n$ is closed, not
empty and not all of $\R$.

__Solution__. Let $O_n = (-1/n, 1/n)$. Then

$$
\bigcap_{n=1}^\infty O_n = [0],
$$

which satisfies the desired conditions.

--------------------------------------------------------------------------------------------
### 3.2.2.

Let

$$
A = \left\{ (-1)^n + \frac{2}{n}: n = 1, 2, 3, \ldots \right\}
$$

and

$$
B = \left\{ x \in \Q: 0 < x < 1 \right\}.
$$

Answer the following questions for each set.

a. What are the limit points?

b. Is the set open? Closed?

c. Does the set contain any isolated points?

d. Find the closure of the set.

#### Set A

a. The limit points of $A$ are $-1$ and $1$.

b. $A$ is neither open nor closed.

c. Yes. All of the points in $A$ are isolated points.

d. The closure of $A$ is $A \cup \{-1, 1\}$.

#### Set B

a. The limit points of $B$ are all of the points in $[0, 1]$. Since $\Q$ is dense in $\R$,
   all intervals about $x \in B$ contains rational numbers not equal to $x$, so all
   points in $B$ are limit points. All irrational numbers in $[0, 1]$ are limit points of
   rational numbers in $[0, 1]$; in other words, they are limit points of $B$. Therefore,
   all of $[0, 1]$ are limit points of $B$.

b. $B$ is neither open nor closed. If $x \in B$, then any interval about $x$ contains
   $y \in \R \backslash \Q$, so $B$ cannot be open. Since any irrational number in
   $[0, 1]$ is a limit point of $\Q$, $B$ is not closed.

c. No. All of the points in $B$ are limit points.

d. The closure of $B$ is $[0, 1]$.

--------------------------------------------------------------------------------------------
### 3.2.3.

__Problem__. Decide whether the following sets are open, closed, or neither. If a set is
not open, find a point in the set for which there is no $\epsilon$-neighborhood contained
in the set. If a set is not closed, find a limit point that is not contained in the set.

a. $\Q$

b. $\N$

c. $\{ x \in \R : x \ne 0 \}$

d. $\{ 1 + 1/4 + 1/9 + \cdots + 1/n^2 : n \in \N \}$

e. $\{ 1 + 1/2 + 1/3 + \cdots + 1/n : n \in \N \}$

__Solution__.

a. $\Q$ is neither open nor closed. $\Q$ is not open because $1 \in \Q$ but
   $(1 - \epsilon, 1 + \epsilon)$ is not contained in $\Q$ for any choice of
   $\epsilon > 0$. $\Q$ is not closed because $\sqrt{2}$ is a limit of rational decimal
   approxmations but $\sqrt{2} \notin \Q$.

b. $\N$ is closed but not open. $\N$ has no limit points because each $n \in \N$ is an
   isolated point.  Since $\N$ has no limit points, it contains all of its limits points.
   Thus, $\N$ is closed. $\N$ is not open because $1 \in \N$ but
   $(1 - \epsilon, 1 + \epsilon)$ is not contained in $\N$ for any choice of $\epsilon > 0$.

c. $\{ x \in \R : x \ne 0 \}$ is open but not closed. It is open because it is the union of
   the two open sets $(-\infty, 0)$ and $(0, \infty)$. It is not closed because $0$ is a
   limit point of the set that is not in the set.

d. $\{ 1 + 1/4 + 1/9 + \cdots + 1/n^2 : n \in \N \}$ is neither open nor closed. It is not
   open because every element in the set is isolated, which implies that for each $x$ in
   the set $V_\epsilon(x)$ is not contained in the set for any $\epsilon > 0$. The set is
   not closed because the series $1 + 1/4 + 1/9 + \cdots$ converges to $\pi^2/6$, which is
   not an element of the set.

e. $\{ 1 + 1/2 + 1/3 + \cdots + 1/n : n \in \N \}$ is closed but not open. It is not open
   open because every element in the set is isolated, which implies that for each $x$ in
   the set $V_\epsilon(x)$ is not contained in the set for any $\epsilon > 0$. The set is
   closed because it has no limit points (which follows because all of its elements are
   isolated and $1 + 1/2 + 1/3 + \cdots$ is the harmonic series and so diverges).

--------------------------------------------------------------------------------------------
### 3.2.4.

Let $A$ be nonempty and bounded above so that $s = \sup A$ exists.

### 3.2.4.a.

__Problem__. Show that $s \in \overline{A}$.

__Solution__. By Lemma 1.3.8, there exists $a \in A$ such that $a > s - \epsilon$ for any
$\epsilon > 0$. Consider a sequence $(a_n)$ constructed by selecting $a_n > s - 1/n$.
Then $(a_n)$ converges to $s$, so $s$ is a limit point of $A$. Since $\overline{A}$
contains all of the limits points of $A$, $s \in \overline{A}$.

### 3.2.4.b.

__Problem__. Can an open set contain its supremum?

__Solution__. No. Let $O$ be an open set with supremum $s$. Any $\epsilon$-neighborhood
of $s$ must contain points $x$ satisfying $s < x < s + \epsilon$. None of these points can
be elements of $O$ because $y \in O$ implies that $y \le s$ (by definition of the supremum).
Therefore, no $\epsilon$-neighborhood of $s$ can be completely contained in $O$, which
implies that $s \notin O$.

--------------------------------------------------------------------------------------------
### 3.2.5.

__Problem__. Prove Theorem 3.2.8.

_Theorem 3.2.8._ A set  $F \subseteq \R$ is closed if and only if every Cauchy sequence
contained in $F$ has a limit that is also an element of $F$.

__Solution__. $(\Rightarrow)$ Suppose $F$ is closed. Consider a sequence $(a_n)$ contained
in $F$. $(a_n)$ converges (because it is Cauchy). Let $a = \lim_{n \rightarrow \infty} a_n$.
Then $a \in F$ because $a$ is a limit point of $F$ and $F$ is closed (which implies that
it contains all of its limit points).

$(\Leftarrow)$ Suppose every Cauchy sequence contained in $F$ has a limit in $F$. Let $x$
be a limit point of $F$. Then there exists a sequence $(a_n)$ contained in $F$ with
$(a_n) \rightarrow x$ and $a_n \ne x$ for all $n \in \N$ (Theorem 3.2.5). Since $(a_n)$
convergent sequences are Cauchy, $x \in F$ (by assumption). Therefore, $F$ contains all of
its limit points, which implies that $F$ is closed.

--------------------------------------------------------------------------------------------
### 3.2.6.

Decide whether the following statements are true or false. Provide counterexamples for
those that are false, and supply proofs for those that are true.

#### 3.2.6.a.

__Problem__. An open set that contains every rational number must necessarily be all of
$\R$.

__Solution__. True. TODO

#### 3.2.6.b.

__Problem__. The Nested Interval Property remains true if the term "closed interval" is
replaced by "closed set".

__Solution__. False. Consider the nested sequence of sets $I_n = [n, \infty)$. Each $I_n$
is closed because it contains all of its limit points. However,
$\cap_{n=1}^\infty I_n = \emptyset$ because for any $x > 0$, $x \notin I_n$ for
$n \ge \lceil x \rceil$.

#### 3.2.6.c.

__Problem__. Every nonempty open set contains a rational number.

__Solution__. True. Let $O$ be a nonempty open set. Then there exists $x \in O$ (because
$O$ is not empty). $O$ is open, so there exists an $\epsilon$-neighborhood $V_\epsilon(x)$
of $x$ that is completely contained in $O$. Take $y, z \in V_\epsilon(x)$ with $y < z$.
Since $\Q$ is dense in $\R$, there exists a rational number
$q \in V_\epsilon(x) \subseteq O$, which proves the desired result.

#### 3.2.6.d.

__Problem__. Evdery bounded infinite closed set contains a rational number.

__Solution__. TODO

#### 3.2.6.e.

__Problem__. The Cantor set is closed.

__Solution__. True. Observe that

$$
\begin{align}
C
&= [0, 1] \backslash
   \left[
     \left( \frac{1}{3}, \frac{2}{3} \right) \cup
     \left( \frac{1}{9}, \frac{2}{9} \right) \cup
     \left( \frac{7}{9}, \frac{8}{9} \right) \cup
     \cdots
   \right] \\
&= [0, 1] \cap
   \left[
     \left( \frac{1}{3}, \frac{2}{3} \right) \cup
     \left( \frac{1}{9}, \frac{2}{9} \right) \cup
     \left( \frac{7}{9}, \frac{8}{9} \right) \cup
     \cdots
   \right]^c \\
&= \left[ (-\infty, 0)^c \cap (1, \infty)^c \right] \cap
   \left[
     \left( \frac{1}{3}, \frac{2}{3} \right)^c \cap
     \left( \frac{1}{9}, \frac{2}{9} \right)^c \cap
     \left( \frac{7}{9}, \frac{8}{9} \right)^c \cap
     \cdots
   \right] \\
&= \left[
     (-\infty, 0)^c \cap
     (1, \infty)^c \cap
     \left( \frac{1}{3}, \frac{2}{3} \right)^c \cap
     \left( \frac{1}{9}, \frac{2}{9} \right)^c \cap
     \left( \frac{7}{9}, \frac{8}{9} \right)^c \cap
     \cdots
   \right] \\
&= \left[
     (-\infty, 0) \cup
     (1, \infty) \cup
     \left( \frac{1}{3}, \frac{2}{3} \right) \cup
     \left( \frac{1}{9}, \frac{2}{9} \right) \cup
     \left( \frac{7}{9}, \frac{8}{9} \right) \cup
     \cdots
   \right]^c \\
\end{align}
$$

Since the union of an arbitrary collection of open sets is open, $C$ is closed (because
it is the complement of an open set).

--------------------------------------------------------------------------------------------
### 3.2.10.

__Problem__. Only one of the following three descriptions can be realized. Provide an
example that illustrates the viable description, and explain why the other two cannot exist.

(i) A countable set contained in $[0, 1]$ with no limit points.

(ii) A countable set contained in $[0, 1]$ with no isolated points.

(iii) A set with an uncountable number of isolated points.

__Solution__.

(i) A set with this property is not possible because any countable set $A$ can be used to
construct a sequence $(x_i)$ containing all of the points in the set (because there must
exist a bijective map between $\N$ and $A$). Since $A \subset [0, 1]$, $(x_i)$ must be
bounded, so the Bolzano-Weierstrass Theorem implies that $(x_i)$ has a convergent
subsequence. Moreover, this subsequence is not eventually constant because the original
sequence $(x_i)$ has no repeated terms. Let $x$ be the limit of the subsequence. If $x$ is
a term in the subsequence, we can remove it from the subsequence without changing the limit
of the subsequence. Therefore, $x$ is a limit point for $A$.

(ii) $\Q \cap [0, 1]$ is a countable set with no isolated points.

(iii) A set $A$ with this property is not possible because any set of isolated points in
$[0, 1]$ divides $[0, 1]$ into a collection consisting of disjoint intervals that are all
open except for two half-open intervals of the form $[0, a)$ and $(b, 1]$. Discarding the
half-open interval with an upper bound of $1$, we can construct a bijection between $A$ and
the intervals by mapping $a \in A$ to the interval that has $a$ as an upper bound.
Identifying each of these disjoint intervals with a rational number contained in the
interval creates a bijection between $A$ and a subset of $\Q$. Therefore, $A$ must be
finite or countable - it cannot be uncountable.

--------------------------------------------------------------------------------------------
### 3.2.11.

#### 3.2.11.a.

__Problem__. Prove that $\overline{A \cup B} = \overline{A} \cup \overline{B}$

__Solution__. TODO

#### 3.2.11.b.

__Problem__. Does this result about closures extend to infinite unions of sets?

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 3.2.15.

A set $A$ is called an $F_\sigma$ set if it can be written as the countable union of closed
sets. A set $B$ is called $G_\delta$ set if it can be written as the countable intersection
of open sets.

#### 3.2.15.a.

__Problem__. Show that a closed interval $[a, b]$ is a $G_\delta$ set.

__Solution__. Since

$$
[a, b] = \bigcap_{n=1}^\infty \left( a - \frac{1}{n}, b + \frac{1}{n} \right),
$$

$[a, b]$ is a $G_\delta$ set.

#### 3.2.15.b.

__Problem__. Show that the half-open interval $(a, b]$ is both a $G_\delta$ and $F_\sigma$
set.

__Solution__. Observe that

$$
(a, b] = \bigcap_{n=1}^\infty \left( a, b + \frac{1}{n} \right)
$$

and

$$
(a, b] = \bigcup_{n=1}^\infty \left[ a + \frac{1}{n}, b \right].
$$

The former shows that $(a, b]$ is a $G_\delta$ set; the latter shows that $(a, b]$ is a
$F_\sigma$ set.

#### 3.2.15.c.

__Problem__. Show that $\Q$ is an $F_\sigma$ set, and the set of irrationals $\I$ form a
$G_\delta$ set.

__Solution__. Let $q_1, q_2, q_3, \ldots$ be an enumeration of the rational numbers. Then
$\Q = \cup_{n=1}^\infty [q_i, q_i]$. Since isolated points are closed sets, $\Q$ is
$F_\sigma$. $\I = \Q^c$, so the set of irrational numbers is equal to

$$
\bigcap_{n=1}^\infty [q_i, q_i]^c,
$$

which is a countable intersection of open sets (because complements of closed sets are
open). Thus, $\I$ is $G_\delta$.

--------------------------------------------------------------------------------------------
