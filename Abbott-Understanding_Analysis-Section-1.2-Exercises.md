Understanding Analysis (S. Abbott): Section 1.2 Exercises
=========================================================

-------------------------------------------------------------------------------
### 1.2.1.

#### 1.2.1.a.

__Problem__. Prove that $\sqrt{3}$ is irrational. Does a similar argument
work to show $\sqrt{6}$ is irrational?

__Solution__. Proof by contradiction. Suppose that $\sqrt{3}$ is rational so
that $\sqrt{3} = p/q$ where $p$ and $q$ are relatively prime integers.
Then, $3 = p^2/q^2 \Rightarrow 3 q^2 = p^2$. Since $p$ and $q$ are
relatively prime, $3$ must be a factor of $p$, so $p = 3 r$ where $r$ is
an integer relatively prime to $q$. Substituting, we find that
$3 q^2 = 9 r^2 \Rightarrow q^2 = 3 r^2$, which implies that $3$ is also a
factor of $q$ contradicting our assumption that $p$ and $q$ are relatively
prime. Therefore, $\sqrt{3}$ is not rational.

#### 1.2.1.b.

__Problem__. Where does the proof of Theorem 1.1.1 break down if we try to use
it to prove that $\sqrt{4}$ is irrational?

__Solution__. If we apply the approach from Theorem 1.1.1 to the $\sqrt{4}$,
the step $4 q^2 = p^2$ only allows us to conclude that $p$ is even. For the
$\sqrt{4}$, $p$ even does not lead to a contradiction of the assumption that
$p$ and $q$ are relatively prime because $4 q^2 = 4 r^2$ only implies that
$q^2 = r^2$, which does not imply that $q$ is even.

-------------------------------------------------------------------------------
### 1.2.2.

__Problem__. Show that there is no rational number $r$ satisfying $2^r = 3$.

__Solution__. Proof by contradiction. Suppose that there exists a rational
number $r = p / q$ satisfying $2^r = 3$ with $p$ and $q \ne 0$ relatively
prime integers. Then, $2^{p/q} = 3 \Rightarrow 2^p = 3^q$, which implies that
either $p = 0 = q$ or 2 is a factor of 3. Both possibilities lead to a
contradiction. The first possibility contradicts the assumption that $r$ is a
rational number and the second possibility contradicts the fact that 3 is a
prime number.

-------------------------------------------------------------------------------
### 1.2.3.

Decide which of the following represent true statements about the
nature of sets. For any that are false, provide a specific example where the
statement in question does not hold.

#### 1.2.3.a.

__Problem__. If $A_1 \supseteq A_2 \supseteq A_3 \supseteq A_4 \cdots$ are
all sets containing an infinite number of elements, then the intersection
$\bigcap_{n=1}^\infty A_n$ is infinite as well.

__Solution__. This statement is false. Consider the sequence of nested
sets $A_n = [-1/n, 1/n]$. $\bigcap_{n=1}^\infty A_n = \{0\}$, which is finite.

#### 1.2.3.b.

__Problem__. If $A_1 \supseteq A_2 \supseteq A_3 \supseteq A_4 \cdots$ are
all finite, nonempty sets of real numbers, then the intersection
$\bigcap_{n=1}^\infty A_n$ is finite and nonempty.

__Solution__. This statement is true. Observe that there must be some $N$ such
that for $n \ge N$, $A_n = A_N$ because $A_1$ finite implies that
$A_{n+1} \subsetneq A_n$ for only a finite number of $n$. Moreover, because
all $A_n$ are nonempty, $A_N$ is nonempty. Since $A_n = A_N$ for $n \ge N$,
$\bigcap_{n=1}^\infty A_n = \bigcap_{n=N}^\infty A_n = A_N$. Therefore, we
can conclude that $\bigcap_{n=1}^\infty A_n$ is finite and nonempty.

#### 1.2.3.c.

__Problem__. $A \cap (B \cup C) = (A \cap B) \cup C$.

__Solution__. This statement is false. Consider the sets

* $A = \{ 1, 2 \}$

* $B = \{ 1 \}$

* $C = \{ 2, 3 \}$

Then, $A \cap (B \cup C) = \{ 1, 2 \}$ but $(A \cap B) \cup C = \{ 1, 2, 3 \}$.

#### 1.2.3.d.

__Problem__. $A \cap (B \cap C) = (A \cap B) \cap C$.

__Solution__. This statement is true.

Suppose $x \in A \cap (B \cap C)$. Then, $x \in A$ and $x \in B \cap C$. Since
$x \in B \cap C$ implies that $x \in B$, $x \in A \cap B$. $x \in B \cap C$
also implies that $x \in C$. In other words, $x \in (A \cap B) \cap C$, so we
can conclude that $A \cap (B \cap C) \subseteq (A \cap B) \cap C$. Analogous
logic yields containment in the opposite direction. Therefore,
$A \cap (B \cap C) = (A \cap B) \cap C$.

#### 1.2.3.e.

__Problem__. $A \cap (B \cup C) = (A \cap B) \cup (A \cap C)$.

__Solution__. This statement is true.

Suppose $x \in A \cap (B \cup C)$. Then, $x \in A$ and $x \in B \cup C$. Because
$x \in B \cup C$ implies that $x \in B$ or $x \in C$, $x \in A \cap B$ or
$x \in A \cap C$. Therefore, $x \in (A \cap B) \cup (A \cap C)$, which implies
that $A \cap (B \cup C) \subseteq (A \cap B) \cup (A \cap C)$.

Suppose $x \in (A \cap B) \cup (A \cap C)$. Then, $x \in A \cap B$ or
$x \in A \cap C$. In either case, $x \in A$. Moreover, we can conclude that
$x \in B \cup C$ because

* $x \in A \cap B$ implies that $x \in B$ and

* $x \in A \cap C$ implies that $x \in C$.

Therefore, $x \in A \cap (B \cup C)$, which implies that
$(A \cap B) \cup (A \cap C) \subseteq A \cap (B \cup C)$.

Together, the containment results yield the desired equality:
$A \cap (B \cup C) = (A \cap B) \cup (A \cap C)$.

-------------------------------------------------------------------------------
### 1.2.4.

__Problem__. Produce an infinite collection of sets $A_1, A_2, A_3, \ldots$
with the property that every $A_i$ has an infinite number of elements and
$A_i \cap A_j = \emptyset$ for all $i \ne j$, and
$\bigcup_{i=1}^\infty A_i = \mathbb{N}$.

__Solution__. Let $P = \{ p_1, p_2, \ldots \}$ be the set of prime numbers
ordered so that $p_i < p_{i+1}$. Define $A_1 = \{1\}$ and

\[
  A_{n+1} = \{k p_n : k \in \mathbb{N} \} - \bigcup_{i = 1}^{n} A_i.
\]

That is, $A_{n+1}$ contains the multiples of the $n$-th prime number that are
not also multiples of a smaller prime.

This collection of sets satisfies our requirements. First,
$\bigcup_{i = 1}^\infty A_i = \mathbb{N}$ because every natural number is
equal to 1 or is a multiple of some prime number. To see that
$A_i \cap A_j = \emptyset$ when $i \ne j$, suppose $x \in A_i$. If $i < j$, then
$x \in A_i$ implies that $x \in \bigcup_{l=1}^{j-1} A_l$ so that $x \notin A_j$
by construction. If $i > j$, then the definition of $A_i$ implies that
$x \notin A_l$ for $l < i$. In particular, $x \notin A_j$. In both cases,
$A_i \cap A_j = \emptyset$, as desired.

-------------------------------------------------------------------------------
### 1.2.5. (De Morgan's Laws)

#### 1.2.5.a.

__Problem__. If $x \in (A \cap B)^c$, explain why $x \in A^c \cup B^c$. This
shows that $(A \cap B)^c \subseteq A^c \cup B^c$.

__Solution__. TODO

#### 1.2.5.b.

__Problem__. Prove the reverse inclusion $(A \cap B)^c \supseteq A^c \cup B^c$,
and conclude that $(A \cap B)^c = A^c \cup B^c$.

__Solution__. TODO

#### 1.2.5.c.

__Problem__. Show $(A \cup B)^c = A^c \cap B^c$ by demonstrating inclusion both
ways.

__Solution__. TODO

-------------------------------------------------------------------------------
### 1.2.6.

#### 1.2.6.a.

__Problem__. Verify the triangle inequality in the special case where $a$ and
$b$ have the same sign.

__Solution__. If $a$ and $b$ have the same sign, then $|a + b| = |a| + |b|$.
Therefore, $|a + b| \le |a| + |b|$, so $a$ and $b$ satisfy the triangle
inequality.

#### 1.2.6.b.

__Problem__. Find an efficient proof for all the cases at once by first
demonstrating $(a + b)^2 \le (|a| + |b|)^2$.

__Solution__. Observe that

\[
  (a + b)^2
  = a^2 + b^2 + 2 a b
  = |a|^2 + |b|^2 + 2 a b
  \le |a|^2 + |b|^2 + 2 |a b|
  = |a|^2 + |b|^2 + 2 |a| |b|
  = (|a| + |b|)^2
\]

Taking the square root of both sides of this equation, we arrive at the
triangle inequality: $|a + b| \le |a| + |b|$.

#### 1.2.6.c.

__Problem__. Prove $|a - b| \le |a - c| + |c - d| + |d - b|$ for all
$a$, $b$, $c$, and $d$.

__Solution__. Express $a - b$ as

\[
  a - b
  = a - c + c - d + d - b
  = (a - c) + (c - d) + (d - b).
\]

Applying the triangle inequality two times yields the desired result.

#### 1.2.6.d.

__Problem__. Prove $\left| |a| - |b| \right| \le |a - b|$. (The unremarkable
identity $a = a - b + b$ may be useful.)

__Solution__. Applying the triangle inequality to the identity
$a = a - b + b = (a - b) + b$, we find that

\[
  |a| \le |a - b| + |b| \Rightarrow |a| - |b| \le |a - b|.
\]

Switching the roles of $a$ and $b$,

\[
  |b| \le |b - a| + |a|
  \Rightarrow |b| - |a| \le |b - a|
  \Rightarrow |a| - |b| \ge -|b - a| = -|a - b|.
\]

Combining these inequalities yields the desired result:

\[
  ||a| - |b|| \le |a - b|.
\]

-------------------------------------------------------------------------------
### 1.2.7.

Given a function $f$ and a subset $A$ of its domain, let $f(A)$ represent the
range of $f$ over the set $A$; that is $f(A) = \{f(x) : x \in A\}$.

#### 1.2.7.a.

__Problem__. Let $f(x) = x^2$. If $A = [0, 2]$ (the closed interval
$\{x \in \mathbb{R} : 0 \le x \le 2\}$) and $B = [1, 4]$, find $f(A)$ and
$f(B)$. Does $f(A \cap B) = f(A) \cap f(B)$ in this case?  Does
$f(A \cup B) = f(A) \cup f(B)$?

__Solution__. For this case, $f(A \cap B) = f(A) \cap f(B)$:

* $f(A \cap B) = f([1, 2]) = [1, 4]$

* $f(A) \cap f(B) = f([0, 2]) \cap f([1, 4]) = [0, 4] \cap [1, 16] = [1, 4]$.

For this case, $f(A \cup B) = f(A) \cup f(B)$:

* $f(A \cup B) = f([0, 4]) = [0, 16]$

* $f(A) \cup f(B) = [0, 4] \cup [1, 16] = [0, 16]$.

#### 1.2.7.b.

__Problem__. Find two sets $A$ and $B$ for which
$f(A \cap B) \ne f(A) \cap f(B)$.

__Solution__. Let $A = [-1, 2]$ and $B = [-2, 1]$. Then,
$f(A \cap B) \subsetneq f(A) \cap f(B)$:

* $f(A \cap B) = f([-1, 1]) = [0, 1]$

* $f(A) \cap f(B) = f([-1, 2]) \cap f([-2, 1]) = [0, 4] \cap [0, 4] = [0, 4]$

#### 1.2.7.c.

__Problem__. Show that, for an arbitrary function
$g : \mathbb{R} \rightarrow \mathbb{R}$, it is always true that
$g(A \cap B) \subseteq g(A) \cap g(B)$ for all set $A, B \subseteq \mathbb{R}$.

__Solution__. Let $y \in g(A \cap B)$. Then, there exists $x \in A \cap B$
such that $g(x) = y$. Since $x \in A$ and $x \in B$, $y = g(x) \in g(A)$ and
$y = g(x) \in g(B)$. Therefore, $y \in g(A) \cap g(B)$, so we can conclude that
$g(A \cap B) \subseteq g(A) \cap g(B)$.

#### 1.2.7.d.

__Problem__. Form and prove a conjecture about the relationship between
$g(A \cup B)$ and $g(A) \cup g(B)$ for an arbitrary function $g$.

__Solution__. _Conjecture_: $g(A \cup B) = g(A) \cup g(B)$. To prove this
conjecture, we show that $g(A \cup B) \subset g(A) \cup g(B)$ and
$g(A) \cup g(B) \subset g(A \cup B)$.

$g(A \cup B) \subset g(A) \cup g(B)$. Suppose $y \in g(A \cup B)$. Then,
there exists $x \in A \cup B$ such that $y = g(x)$. $x \in A \cup B$ implies
that $x \in A$ or $x \in B$, so $y = g(x) \in g(A)$ or $y = g(x) \in g(B)$.
Therefore, $y \in g(A) \cup g(B)$ so that $g(A \cup B) \subset g(A) \cup g(B)$.

$g(A) \cup g(B) \subset g(A \cup B)$. Suppose $y \in g(A) \cup g(B)$. Then,
there exists $y \in g(A)$ or $y \in g(B)$. If $y \in g(A)$, then there exists
$x \in A$ such that $y = g(x)$; if $y \in g(B)$, then there exists $x \in B$
such that $y = g(x)$. Combining these cases, we can conclude that there exists
an $x \in A$ or $x \in B$ such that $y = g(x)$. In other words, there exists
an $x \in A \cup B$ such that $y = g(x)$. Therefore, $y \in g(A \cup B)$ so
that $g(A) \cup g(B) \subset g(A \cup B)$.

-------------------------------------------------------------------------------
### 1.2.8.

Here are two important definitions related to a function $f : A \rightarrow B$. The function is _one-to-one_ (1-1) if $a_1 \ne a_2$ in $A$ implies that
$f(a_1) \ne f(a_2)$ in $B$. The function $f$ is _onto_ if, given any $b \in B$,
it is possible to find an element $a \in A$ for which $f(a) = b$.

Give an example for each or state that the request is impossible.

#### 1.2.8.a.

__Problem__. $f : \mathbb{N} \rightarrow \mathbb{N}$ that is 1-1 but not onto.

__Solution__. TODO

#### 1.2.8.b.

__Problem__. $f : \mathbb{N} \rightarrow \mathbb{N}$ that is onto but not 1-1.

__Solution__. TODO

#### 1.2.8.c.

__Problem__. $f : \mathbb{N} \rightarrow \mathbb{Z}$ that is 1-1 and onto.

__Solution__. TODO

-------------------------------------------------------------------------------
### 1.2.9.

Given a function $f : D \rightarrow \mathbb{R}$ and a subset
$B \subseteq \mathbb{R}$, let $f^{-1}(B)$ be the set of allp oints from the
domain $D$ that get mapped into $B$; that is,
$f^{-1}(B) \{ x \in D : f(x) \in B\}$. This set is called the _preimage_ of
$B$.

#### 1.2.9.a.

__Problem__. Let $f(x) = x^2$. If $A$ is the closed interval $[0, 4]$ and
$B$ is the closed interval $[-1, 1]$, find $f^{-1}(A)$ and $f^{-1}(B)$. Does
Does $f^{-1}(A \cap B) = f^{-1}(A) \cap f^{-1}(B)$ in this case?  Does
$f^{-1}(A \cup B) = f^{-1}(A) \cup f^{-1}(B)$?

__Solution__. TODO

#### 1.2.9.b.

__Problem__. The good behavior of preimages demonstrated in (a) is completely
general. Show that for an arbitrary function
$g : \mathbb{R} \rightarrow \mathbb{R}$, it is always true that
$g^{-1}(A \cap B) = g^{-1}(A) \cap g^{-1}(B)$ and
$g^{-1}(A \cup B) = g^{-1}(A) \cup g^{-1}(B)$ for all sets
$A, B \subseteq \mathbb{R}$.

__Solution__. TODO

-------------------------------------------------------------------------------
### 1.2.10.

Decide which of the following are true statements. Provide a short
justification for those that are valid and a counterexample for those that are
not.

#### 1.2.10.a.

__Problem__. Two real numbers satisfy $a < b$ if and only if $a < b + \epsilon$
for every $\epsilon > 0$.

__Solution__. TODO

#### 1.2.10.b.

__Problem__. Two real numbers satisfy $a < b$ if $a < b + \epsilon$ for every
$\epsilon > 0$.

__Solution__. TODO

#### 1.2.10.c.

__Problem__. Two real numbers satisfy $a \le b$ if and only if
$a < b + \epsilon$ for every $\epsilon > 0$.

__Solution__. TODO

-------------------------------------------------------------------------------
### 1.2.11.

Form the logical negation of each claim. One trivial way to do this is to
simply add "It is not the case that..." in front of each assertion. To make
this interesting, fashion the negation into a positive statement that avoids
the word "not" altogether. In each case, make an intuitive guess as to whether
the claim or its negation is the true statement.

#### 1.2.11.a.

__Problem__. For all real numbers satisfying $a < b$, there exists an
$n \in \mathbb{N}$ such that $a + 1/n < b$.

__Solution__. TODO

#### 1.2.11.b.

__Problem__. There exists a real number $x > 0$ such that $x < 1/n$ for all
$n \in \mathbb{N}$.

__Solution__. TODO

#### 1.2.11.c.

__Problem__. Between every two distinct real numbers, there is a rational
number.

__Solution__. TODO

-------------------------------------------------------------------------------
### 1.2.12.

Let $y_1 = 6$ and foreach $n \in \mathbb{N}$ define $y_{n+1} = (2 y_n - 6) / 3$.

#### 1.2.12.a.

__Problem__. Use induction to prove that the sequence satisfies $y_n > -6$
for all $n \in \mathbb{N}$.

__Solution__. TODO

#### 1.2.12.b.

__Problem__. Use another induction argument to show the sequence
$(y_1, y_2, y_3, \ldots)$ is decreasing.

__Solution__. TODO

-------------------------------------------------------------------------------
### 1.2.13.

For this exercise, assume Exercise 1.2.5 has been successfully completed.

#### 1.2.13.a.

__Problem__. Show how induction can be used to conclude that

\[
  \left( A_1 \cup A_2 \cup \cdots \cup A_n \right)^c
  = A_1^c \cap A_2^c \cap \cdots \cap A_n^c
\]

for any finite $n \in \mathbb{N}$.

__Solution__. TODO

#### 1.2.13.b.

__Problem__. It is tempting to appeal to induction to conclude

\[
  \left( \bigcup_{i=1}^\infty A_i \right)^c = \bigcap_{i=1}^\infty A_i^c,
\]

but induction does not apply here. Indcution is used to prove that a particular
statement holds for every value of $n \in \mathbb{N}$, but this does not imply
the validity of the infinite case. To illustrate this point, find an example
of a collection of sets $B_1, B_2, B_3, \ldots$ where
$\bigcap_{i=1}^n B_i \ne \emptyset$ is true for every $n \in \mathbb{N}$, but
$\bigcap_{i=1}^\infty B_i \ne \emptyset$ failes.

__Solution__. TODO

#### 1.2.13.c.

__Problem__. Nevertheless, the infinite version of De Morgan's Law stated in
(b) is a valid statement. Provide a proof that does not use induction.

__Solution__. TODO

-------------------------------------------------------------------------------
