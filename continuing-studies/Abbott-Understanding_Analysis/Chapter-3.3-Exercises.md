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

* (a) $\N$.

* (b) $\Q \cap [0, 1]$.

* (c) The Cantor set.

* (d) $\{1 + 1/2^2 + 1/3^2 + \cdots + 1/n^2 : n \in \N\}$.

* (e) $\{1, 1/2, 2/3, 3/4, 4/5, \ldots\}$.

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

__Problem__. TODO

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 3.3.4.

__Problem__. TODO

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 3.3.5.

__Problem__. TODO

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 3.3.6.

__Problem__. TODO

__Solution__. TODO

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
