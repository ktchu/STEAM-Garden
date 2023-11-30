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

__Problem__. TODO

__Solution__. TODO

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

__Solution__. TODO

--------------------------------------------------------------------------------------------
