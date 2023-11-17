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
