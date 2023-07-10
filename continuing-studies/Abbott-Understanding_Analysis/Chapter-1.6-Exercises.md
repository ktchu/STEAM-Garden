Understanding Analysis (S. Abbott): Section 1.6 Exercises
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
### 1.6.1.

__Problem__. Show that $(0, 1)$ is uncountable if and only if $\R$ is uncountable. This
shows that Theorem 1.6.1 is equivalent to Theorem 1.5.6.

__Solution__. Exercise 1.5.4 shows that $(a, b) \sim \R$. Taking $a = 0$ and $b = 1$ shows
that $(0, 1) \sim \R$. Therefore, $(0, 1)$ and $\R$ have the same cardinality, which
implies that $(0, 1)$ is uncountable if and only if $\R$ is uncountable.

--------------------------------------------------------------------------------------------
### 1.6.2.

#### 1.6.2.a.

__Problem__. Explain why the real number $x = .b_1 b_2 b_3 b_4 \ldots$ cannot be $f(1)$.

__Solution__. $b_1 \ne a_{11}$ by construction, so $f(1) \ne x$.

#### 1.6.2.b.

__Problem__. Now, explain by $x \ne f(2)$, and in general why $x \ne f(n)$ for any
$n \in \N$.

__Solution__. Similarly, $b_2 \ne a_{22}$ by construction, so $f(2) \ne x$. The same
argument applies for any $n \in \N$, so $f(n) \ne x$ for any $n \in \N$.

#### 1.6.2.c.

__Problem__. Point out the contradiction that arises from these observations and conclude
that $(0, 1)$ is uncountable.

__Solution__. $x \in (0, 1)$ but $f(n) \ne x$ for any $n \in \N$, which contradicts the
assumption that $f$ is onto. Thus, we conclude that $f$ is not onto, which implies that
$(0, 1)$ is not countable. Since $(0, 1)$ is an infinite set, it must be uncountable.

--------------------------------------------------------------------------------------------
### 1.6.3.

Supply rebuttals to the following complaints about the proof of Theorem 1.6.1.

### 1.6.3.a.

__Problem__. Every rational number has a decimal expansion, so we could apply this same
argument to show that the set of rational numbers between $0$ and $1$ is uncountable.
However, because we know that any subset of $\Q$ must be countable, the proof of Theorem
1.6.1 must be flawed.

__Solution__. There exist numbers with decimal expansions that are not rational numbers -
for instance, decimal expansions of irrational numbers. Therefore, finding a number whose
decimal expansion is not in the set $f(1), f(2), f(3), \ldots$ is not a contradiction.

### 1.6.3.b.

__Problem__. Some numbers have _two_ different decimal representations. Specifically, any
decimal expansion that terminates can also be written with repeating $9$'s. For instance,
$1/2$ can be written as $.5$ or $.4999\ldots$. Doesn't this cause some problems?

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 1.6.4.

__Problem__. Let $S$ be the set consisting of all sequences of $0$'s and $1$'s. Observe
that $S$ is not a particular sequence, but rather a large set whose elements are sequences;
namely,

$$
S = \{ (a_1, a_2, a_3, \ldots) : a_n = 0 \textrm{ or } 1 \}.
$$

As an example, the sequence $(1, 0, 1, 0, 1, 0, 1, 0, \ldots)$ is an element of $S$, as is
the sequence (1, 1, 1, 1, 1, 1, \ldots)$.

Give a rigorous argument showing that $S$ is uncountable.

__Solution__. Cantor's diagonalization method with the function

$$
f(n)
= \left\{\begin{array}{ll}
0 & \textrm{if } a_{nn} = 1 \\
1 & \textrm{if } a_{nn} = 0
\end{array}\right.
$$

yields the desired result.

--------------------------------------------------------------------------------------------
### 1.6.5.

#### 1.6.5.a.

__Problem__. Let $A = \{a, b, c\}$. List the eight elements of $P(A)$. (Do not forget that
$\emptyset$ is considered to be a subset of every set.)

__Solution__. $\emptyset$, $\{a\}$, $\{b\}$, $\{c\}$, $\{a, b\}$, $\{a, c\}$, $\{b, c\}$,
$\{a, b, c\}$.

#### 1.6.5.b.

__Problem__. If $A$ is finite with $n$ elements, show that $P(A)$ has $2^n$ elements.

__Solution__. Let $A = (a_1, a_2, \ldots, a_n)$. Consider the map $f$ from $P(A)$ to
$n$-tuples of $0$'s and $1$'s defined as follows:

$$
f(S)_i
= \left\{\begin{array}{ll}
0 & \textrm{if } a_n \notin S \\
1 & \textrm{if } a_n \in S
\end{array}\right.
$$

Observe that $f$ is 1-1 and onto.

* If $y$ is an $n$-tuple of $0$'s and $1$'s, then $S$ consisting of the elements of $A$
  where $y_i$ is $1$ maps to $y$. Thus, $f$ is onto.

* If $f(S_1) = f(S_2)$, then $S_1$ and $S_2$ are both equal to the set of elements of $A$
  where $f(S_1)_i$ is $1$. Thus, $f$ is 1-1.

Therefore, $P(A)$ and the set of $n$-tuples of $0$'s and $1$'s have the same cardinality.
Since the latter has $2^n$ elements, so must $P(A)$.

--------------------------------------------------------------------------------------------
### 1.6.6.

#### 1.6.6.a.

__Problem__. Using the particular set $A = \{a, b, c\}$, exhibit two different 1-1
mappings from $A$ into $P(A)$.

__Solution__.

$$
\begin{align}
f(a) &= \{a\} \\
f(b) &= \{b\} \\
f(c) &= \{c\} \\
\end{align}
$$

$$
\begin{align}
g(a) &= \{b\} \\
g(b) &= \{c\} \\
g(c) &= \{a\} \\
\end{align}
$$

#### 1.6.6.b.

__Problem__. Letting $C = \{1, 2, 3, 4\}$, produce an example of a 1-1 map
$g: C \rightarrow P(C)$.

__Solution__.

$$
\begin{align}
g(1) &= \{1\} \\
g(2) &= \{2\} \\
g(3) &= \{3\} \\
g(4) &= \{4\} \\
\end{align}
$$

#### 1.6.6.c.

__Problem__. Explain why, in parts (a) and (b), it is impossible to construct mappings that
are _onto_.

__Solution__. For any finite set $A$, it is only possible to construct mappings _onto_ sets
with cardinality no greater than the cardinality of $A$. The power set of a finite set $A$
always has a strictly greater cardinality than the cardinality of $A$ because $2^n > n$ for
all $n \in \N$. Therefore, it is impossible to construct mappings from finite sets onto
their power sets.

--------------------------------------------------------------------------------------------
