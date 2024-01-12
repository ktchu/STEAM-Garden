Understanding Analysis (S. Abbott): Section 3.4 Exercises
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
### 3.4.1.

__Problem__. If $P$ is a perfect set and $K$ is compct, is the intersection $P \cap K$
always compact? Always perfect?

__Solution__. $P \cap K$ is always compact. Observe that $P \cap K$ is closed because $P$
and $K$ are both closed and the intersection of closed sets is closed. Furthermore,
$P \cap K$ is bounded because $P \cap K \subset K$ and $K$ is bounded. Therefore, $P \cap K$
is compact.

$P \cap K$ is not always perfect. As a counterexample, consider $P = [0, 1]$ and
$K = \{ 1/2 \}$. Then $P \cap K = \{ 1/2 \}$, which is not perfect because it contains the
isolated point $1/2$.

--------------------------------------------------------------------------------------------
### 3.4.2.

__Problem__. Does there exists a perfect set consisting of only rational numbers?

__Solution__. No. Any subset of $\Q$ must be finite or countable but any perfect set must
be uncountable.

--------------------------------------------------------------------------------------------
