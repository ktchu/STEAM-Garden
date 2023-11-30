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

(a) $\N$.

(b) $\Q \cap [0, 1]$.

(c) The Cantor set.

(d) $\{1 + 1/2^2 + 1/3^2 + \cdots + 1/n^2 : n \in \N\}$.

(e) $\{1, 1/2, 2/3, 3/4, 4/5, \ldots\}$.

__Solution__.

(a) $\N$ is not compact because the sequence $\{1, 2, 3, \ldots\}$ does not converge.

(b) $\Q \cap [0, 1]$ is not compact because it does not contain all of its limit points.
    As a counterexample, consider the sequence of decimal approximations to $\sqrt{2}$.

(c) The Cantor set is compact because it is closed and bounded. It is closed because it is
    the complement of a union of open sets (the removed sets).

(d) This set is not compact because the limit of the sequence of partial sums
    $S_n = 1 + 1/2^2 + 1/3^2 + \cdots + 1/n^2$ is $\pi^2 / 6$, but $\pi^2 / 6$ is not
    contained in the set.

(e) This set is compact because it is closed and bounded. It is closed because the only
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

(a) $K \cap F$

(b) $\overline{F^c \cup K^c}$

(c) $K \backslash F = \{ x \in K : x \notin F\}$

(d) $\overline{K \cap F^c}$

__Solution__.

(a) $K \cap F$ is compact because

  * $K \cap F$ is closed (because arbitrary intersections of closed sets are closed) and

  * $K \cap F$ is bounded because $K \cap F \subseteq K$.

  Therefore, $K$ is definitely compact and closed.

(b) By De Morgan's Laws, $\overline{F^c \cup K^c} = K \cap F$, so part (a) shows that
  $K \cap F$ must be both compact and closed.

(c) $K \backslash F$ is bounded because $K \backslash F \subseteq K$. However, it is not
  guaranteed to be closed, so it is not necessarily compact. As a counterexample, consider
  $K = [0, 2]$ and $F = [0, 1]$. Then $K \backslash F = (1, 2]$, which is not closed.

(d) By De Morgan's Law, $\overline{K \cap F^c} = K^c \cup F$, which is not guaranteed to be
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

(a) The arbitrary intersection of compact sets is compact.

(b) The arbitrary union of compact sets is compact.

(c) Let $A$ be arbitrary, and let $K$ be compact. Then, the intersection $A \cap K$ is
    compact.

(d) If $F_1 \supseteq F_2 \supseteq F_3 \supseteq F_4 \supseteq \cdots$ is a nested
    sequence of nonempty closed sets, then the intersection
    $\bigcap_{n=1}^\infty F_n \ne \emptyset$.

__Solution__.

(a) True. Let $K$ be the intersection of an arbitrary collection of compact sets. Then $K$
  closed because arbitrary intersections of closed sets are closed. Furthermore, $K$ is
  bounded because $K$ is contained in any set $A$ in the collection, which implies that it
  is bounded any bound for $A$. Therefore, $K$ is compact.

(b) False. Consider the collection of compact sets $A_n = [n-1, n]$ for $n \in \N$. Then
    $\bigcup_{n=1}^\infty A_n = [0, \infty)$, which is not bounded and so cannot be compact.

(c) False. Consider $A = (0, 1)$ and $K = [0, 2]$. Then $A \cap K = (0, 1)$, which is not
    closed and so cannot be compact.

(d) True. If all of the $F_n$ are unbounded, then clearly $\bigcap_{n=1}^\infty F_n$ is
    unbounded and therefore nonempty. If $F_n$ is bounded for some $n \in N$, then the
    $F_n, F_{n+1}, \ldots$ is a sequence of compact sets, so their intersection is nonempty
    by the Nested Compact Set Property.

--------------------------------------------------------------------------------------------
### 3.3.6.

__Problem__. This exercise is meant to illustrate the point made in the opening paragraph
to Section 3.3. Verify that the following three statements are true if every blank is
filled with the word "finite." Which are true if every blank is filled with the word
"compact." Which are true if every blank is filled in with the word "closed."

(a) Every (blank) set has a maximum.

(b) If $A$ and $B$ are (blank), then $A + B = \{ a + b : a \in A, b \in B \}$ is also
    (blank).

(c) If $\{ A_n : n \in \N \}$ is a collection of (blank) sets with the property that every
    finite subcollection has a nonempty intersection, then $\bigcap_{n=1}^\infty A_n$ is
    nonempty as well.

__Solution__. For all cases, assume nonempty sets of real numbers.

(a) For finite sets, this statement is true because we can list all of the elements of the
    set. For compact sets, this statement is true by the result of Exercise 3.3.1. For
    closed sets, this statement is not true because the set may be unbounded (e.g., $\N$).

(b) For finite sets, this statement is true because we can list all of the elements of
    $A + B$. For compact sets, this statement is true because the compactness of $A$ and
    $B$ combined with the Algebraic Limit Theorem for sequences imply that any sequence
    $(x_i)$ with $x_i \in A + B$ has a subsequence that converges to a limit in $A + B$.
    For closed sets, this statement is true because the closedness of $A$ and $B$ combined
    with the Algebraic Limit Theorem for sequences imply that any limit point of $A + B$
    is an element of $A + B$.

(c) TODO

--------------------------------------------------------------------------------------------
### 3.3.7.

__Problem__. TODO

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 3.3.8.

__Problem__. TODO

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 3.3.9.

__Problem__. TODO

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 3.3.10.

__Problem__. TODO

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 3.3.11.

__Problem__. TODO

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 3.3.12.

__Problem__. TODO

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 3.3.13.

__Problem__. TODO

__Solution__. TODO

--------------------------------------------------------------------------------------------
