Understanding Analysis (S. Abbott): Section 1.4 Exercises
=========================================================

--------------------------------------------------------------------------------------------
### Notation

* $\newcommand{\Z}{\mathbb{Z}}$
  The set of integers: $\Z$

* $\newcommand{\Q}{\mathbb{Q}}$
  The set of rational numbers: $\Q$

* $\newcommand{\I}{\mathbb{I}}$
  The set of irrational numbers: $\I$

* $\newcommand{\R}{\mathbb{R}}$
  The set of real numbers: $\R$

--------------------------------------------------------------------------------------------
### 1.4.1.

Recall that $\I$ stands for the set of irrational numbers.

#### 1.4.1.a.

__Problem__. Show that if $a, b \in \Q$, then $ab$ and $a + b$ are elements of $\Q$ as well.

__Solution__. Let $a, b \in \Q$. Then $a = m/n$ and $b = p/q$ with $m, n, p, q \in \Z$.
Therefore,

$$
ab = \frac{mp}{nq} = \frac{M}{N}
$$

and

$$
a + b = \frac{m}{n} + \frac{p}{q} = \frac{P}{Q}
$$

with $M, N, P, Q \in \Z$. In other words, $ab$ and $a + b$ are both elements of $\Q$.

#### 1.4.1.b.

__Problem__. Show that if $a \in \Q$ and $t \in \I$, then $a + t \in \I$ and $at \in \I$ as
long as $a \ne 0$.

__Solution__. Suppose $at \in \Q$. Then $at = b$ with $b \in \Q$, which implies that
$t = b / a$ is a product of rational numbers. By part (a), $t \in \Q$ - a contradiction.
Therefore, $at \in \I$ (because $\Q \cup \I = \R$).

Similarly, suppose $a + t \in \Q$. Then $a + t = b$ with $b \in \Q$, which implies that
$t = b - a$ is a sum of rational numbers. By part (a), $t \in \Q$ - a contradiction.
Therefore, $a + t \in \I$.


#### 1.4.1.c.

__Problem__. Part (a) can be summarized by saying that $\Q$ is closed under addition and
multiplication. Is $\I$ closed under addition and multiplication? Given two irrational
numbers $s$ and $t$, what can we say about $s + t$ and $st$?

__Solution__. $\I$ is not closed under multiplication. As a counterexample, consider
$t = \sqrt{2}$. $t$ is in $\I$, but $t \cdot t = 2 \in \Q$. $\I$ is also not closed under
addition. As a counter example, consider $s = 2 + \sqrt{2}$ and $t = 1 - \sqrt{2}$. Both
$s$ and $t$ are in $\I$, but $s + t = 3 \in \Q$.

Given $s,t \in \I$, all we can say about $st$ and $s+t$ is that they are in
$\I \cup \Q = \R$.

--------------------------------------------------------------------------------------------
### 1.4.2.

__Problem__. Let $A \subseteq \R$ be nonempty and bounded above, and let $s \in \R$ have
the property that for all $n \in \N$, $s + \frac{1}{n}$ is an upper bound for $A$ and
$s - \frac{1}{n}$ is not an upper bound for $A$. Show $s = \sup A$.

__Solution__. First, we prove, by contradiction, that $s$ is an upper bound for $A$.
Suppose that $s$ is not an upper bound for $A$. Then there exists $a \in A$ such that
$s < a$. Since $a - s > 0$, the Archimedean Property implies that there exists $n$ such
that $1/n < a - s$. Rearranging this inequality yields $s + 1/n < a$ - a contradiction of
the assumption that $s + 1/n$ is an upper bound for $A$ for all $n \in \N$. Therefore,
$s$ must be an upper bound for $A$.

Next, we use Lemma 1.3.8 to show that $s = \sup A$. Let $\epsilon > 0$. Invoking the
Archimedean property, there exists $n$ such that $1/n < \epsilon$, which implies that
$s - 1/n > s - \epsilon$. By assumption, $s - 1/n$ is not an upper bound for $A$, so
$s - \epsilon$ cannot be an upper bound either. In other words, there exists $a \in A$
such that $a > s - 1/n > s - \epsilon$. Therefore, Lemma 1.3.8 allows us to conclude that
$s = \sup A$.

--------------------------------------------------------------------------------------------
### 1.4.3.

__Problem__. Prove that $\bigcap_{n=1}^\infty (0, 1/n) = \emptyset$. Notice that this
demonstrates that the intervals in the Nested Interval Property must be closed for the
conclusion of the theorem to hold. of the theorem to hold.

__Solution__. Suppose that $\bigcap_{n=1}^\infty (0, 1/n)$ is not empty.  Then, there
exists $x \in \bigcap_{n=1}^\infty (0, 1/n)$, which implies that $x \in (0, 1/n)$ for all
$n \in \N$. However, this conclusion contradicts the fact that $x \notin (0, 1/n)$ for all
$n  > 1/x$. Therefore, $\bigcap_{n=1}^\infty (0, 1/n)$ must be empty.

--------------------------------------------------------------------------------------------
### 1.4.4.

__Problem__. Let $a < b$ be real numbers and consider the set $T = \Q \cap [a, b]$. Show
$\sup T = b$.

__Solution__. Clearly, $b$ is an upper bound for $T$. Let $\epsilon > 0$. Consider the
set $(\max(a, b - \epsilon), b) \subset [a, b]$. Since $\Q$ is dense in $\R$, there exists
$x \in \Q$ such that $\max(a, b - \epsilon) < x < b$ no matter how small $\epsilon$ is.
In other words, for any $\epsilon > 0$, there exists $x \in T$ such that $t > b - \epsilon$,
which implies that $b = \sup T$ (by Lemma 1.3.8).

--------------------------------------------------------------------------------------------
### 1.4.5.

__Problem__. Using Exercise 1.4.1, supply a proof for Corollary 1.4.4 by consider the real
numbers $a - \sqrt{2}$ and $b - \sqrt{2}$.

_Corollary 1.4.4_. Given any two real numbers $a < b$, there exists an irrational number
$t$ satisfying $a < t < b$.

__Solution__. Since $a < b$, $a - \sqrt{2} < b - \sqrt{2}$. As a consequence of the density
of rational numbers in $\R$, there exists a rational number $r$ such that
$a - \sqrt{2} < r < b - \sqrt{2}$.  Therefore, $a < r + \sqrt{2} < b$. From Problem
1.4.1.b, $r + \sqrt{2} \in \I$, which yields the desired result.

--------------------------------------------------------------------------------------------
### 1.4.6.

Recall that a set $B$ is _dense_ in $\R$ if an element of $B$ can be found between any two
real numbers $a < b$. Which of the following sets are dense in $\R$? Take $p \in \Z$ and
$q \in N$ in every case.

#### 1.4.6.a.

__Problem__. The set of all rational numbers $p/q$ with $q \le 10$.

__Solution__. This set is not dense in $\R$. Since $q \le 10$, $|p/q| \ge 0.1$ for all
$p \in \Z$ and $q \in \N$ when $p \ne 0$ and $p/q = 0$ when $p = 0$. Therefore, the set
$[0.01, 0.02] \subset \R$ contains no elements of the set of all rational numbers $p/q$
with $q \le 10$.

#### 1.4.6.b.

__Problem__. The set of all rational numbers $p/q$ with $q$ a power of $2$.

__Solution__. This set is dense in $\R$. TODO: Proof

#### 1.4.6.c.

__Problem__. The set of all rational numbers $p/q$ with $10|p| \ge q$.

__Solution__. This set is not dense in $\R$ because it is a subset of the set defined in
Problem 1.4.6.a. The same interval $[0.01, 0.02]$ contains no elements the set.

--------------------------------------------------------------------------------------------
### 1.4.7.

__Problem__. Finish the proof of Theorem 1.4.5 by showing that the assumption
$\alpha^2 > 2$ leads to a contradiction of the fact that $\alpha = \sup T$.

__Solution__. Suppose $\alpha^2 > 2$. Observe that

$$
\left( \alpha - \frac{1}{n} \right)^2
= \alpha^2 - \frac{2 \alpha}{n} + \frac{1}{n^2}
> \alpha^2 - \frac{2 \alpha}{n}.
$$

Choosing $n_0 > \frac{2 \alpha}{\alpha^2 - 2}$ implies that
$\left( \alpha - \frac{1}{n_0} \right)^2 > 2$. Therefore,
$\left( \alpha - \frac{1}{n_0} \right) < \alpha$ is an upper bound for $T$, which
contradicts the fact that $\alpha$ is the _least_ upper bound for $T$.

Since $\alpha^2$ cannot be greater than or less than 2, it must be exactly equal to 2.

--------------------------------------------------------------------------------------------
### 1.4.8.

Give an example of each or state that the request is impossible. When a request is
impossible, provide a compelling argument for why this is the case.

#### 1.4.8.a.

__Problem__.  Two sets $A$ and $B$ with $A \cap B = \emptyset$, $\sup A = \sup B$,
$\sup A \notin A$ and $\sup B \notin $B$.

__Solution__. TODO

#### 1.4.8.b.

__Problem__.  A sequence of nested open intervals
$J_1 \supseteq J_2 \supseteq J_3 \supseteq \cdots$ with $\cap_{n=1}^\infty J_n$ nonempty
but containing only a finite number of elements.

__Solution__. Let $J_n = (-1/n, 1/n)$. Clearly, $0 \in J_n$ for all $n$, so
$\cap_{n=1}^\infty J_n$ is nonempty. However, $x \notin \cap_{n=1}^\infty J_n$ for any
nonzero $x$ because $x \notin J_n$ for $n > 1/x$. Therefore,
$\cap_{n=1}^\infty J_n = \{0\}$ contains a finite number of elements.

#### 1.4.8.c.

__Problem__.  A sequence of nested unbounded closed intervals
$L_1 \supseteq L_2 \supseteq L_3 \supseteq \cdots$ with $\cap_{n=1}^\infty L_n = \emptyset$.
(An unbounded closed interval has the form $[\alpha, \infty) = \{x \in \R : x \ge a \}$.)

__Solution__. Let $L_n = [n, \infty)$. Observe that $L_n$ contains only positive elements
for all $n \in \N$, which implies that $\cap_{n=1}^\infty L_n$ can contain only positive
elements. Suppose there exists $x > 0$ such that $x \in L_n$ for all $n$. By the
Archimedean Property, there exists $n_0 \in \N$ such that $n_0 > x$, which implies that
$x \notin L_n$ for $n > n_0$, contracting the assumption $x \in L_n$ for all $n$. Therefore,
$\cap_{n=1}^\infty L_n = \emptyset$.

#### 1.4.8.d.

__Problem__.  A sequence of closed (not necessarily nested) intervals
$I_1, I_2, I_3, \ldots$ with the property that $\cap_{n=1}^\infty I_n \ne \emptyset$ for
all $N \in \N$, but $\cap_{n=1}^\infty I_n = \emptyset$.

__Solution__. This request is impossible. Consider the sequence of closed sets defined by

$$
K_n = \cap_{k=1}^n
$$

TODO

--------------------------------------------------------------------------------------------
