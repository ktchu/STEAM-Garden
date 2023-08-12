Understanding Analysis (S. Abbott): Section 1.5 Exercises
=========================================================

--------------------------------------------------------------------------------------------
### Notation

* $\newcommand{\N}{\mathbb{N}}$
  The set of natural numbers: $\N$

* $\newcommand{\Z}{\mathbb{Z}}$
  The set of integers: $\Z$

* $\newcommand{\Q}{\mathbb{Q}}$
  The set of rational numbers: $\Q$

* $\newcommand{\I}{\mathbb{I}}$
  The set of irrational numbers: $\I$

* $\newcommand{\R}{\mathbb{R}}$
  The set of real numbers: $\R$

--------------------------------------------------------------------------------------------
### 1.5.1.

__Problem__. Finish the following proof for Theorem 1.5.7.

_Theorem 1.5.7_. If $A \subseteq B$ and $B$ is countable, then $A$ is either countable or
finite.

Assume B is a countable set. Thus, there exists $f: \N \rightarrow B$, which is 1-1 and
onto. Let $A \subseteq B$ be an infinite subset of $B$. We must show that $A$ is countable.

Let $n_1 = \min\{n \in \N : f(n) \in A\}$. As a start to a definition of
$g: \N \rightarrow A$, set $g(1) = f(n_1)$. Show how to inductively continue this process
to produce a 1-1 function $g$ from $\N$ onto $A$.

__Solution__. Let $n_k = \min \{ n \in \N : f(n) \in A \textrm{ and } n > n_{k-1} \}$ and
define $g(k) = f(n_k)$. First, observe that

$$
\begin{align}
g(k) = g(l)
&\Rightarrow f(n_k) = f(n_l) \\
&\Rightarrow n_k = n_l \\
&\Rightarrow k = l,
&\end{align}
$$

where the first line follows from the definition of $g$, the second line follows because
$f$ is 1-1, and the last line follows because $\{ n_k \}$ is a strictly increasing
sequence by construction. Thus, we can conclude that $g$ is 1-1.

Next, suppose $a \in A$. Then thre exists $n \in \N$ such that $f(n) = a$ because $f$
is onto. Let $k$ be the number of elements of $A$ in $\{ f(1), f(2), \ldots, f(n-1) \}$.
Then $g(k) = f(n_{k+1}) = f(n) = a$ by construction. Therefore, $g$ is onto.

--------------------------------------------------------------------------------------------
### 1.5.2.

__Problem__. Review the proof of Theorem 1.5.6, part (ii) showing that $\R$ is uncountable,
and then find the flaw in the following erroneous proof that $\Q$ is uncountable.

Assume, for contradiction, that $\Q$ is countable. Thus we can write
$\Q = \{r_1, r_2, r_3, \ldots \}$ and, as before, construct a nested sequence of closed
intervals with $r_n \notin I_n$. Our construction implies
$\bigcap_{n=1}^\infty I_n = \emptyset$ while NIP implies that
$\bigcap_{n=1}^\infty I_n \ne \emptyset$. This contradiction implies that $\Q$ must
therefore be uncountable.

__Solution__. $\Q$ does not satisfy AoC, so NIP does not hold for $\Q$.

--------------------------------------------------------------------------------------------
### 1.5.3.

Use the following outline to supply proofs for the statements in Theorem 1.5.8.

_Theorem 1.5.8_.

(i) If $A_1, A_2, \ldots, A_m$ are each countable sets, then the union
$A_1 \cup A_2 \cup \cdots \cup A_m$ is countable.

(ii) If $A_n$ is a countable set for each $n \in \N$, then $\bigcup_{n=1}^\infty A_n$ is
countable.

#### 1.5.3.a.

__Problem__. First, prove statement (i) for two countable sets, $A_1$ and $A_2$. Example
1.5.3 (ii) may be a useful reference. Some technicalities can be avoided by first replacing
$A_2$ with the set $B_2 = A_2 \backslash A_1 = \{x \in A_2 : x \notin A_1\}$. The point of
this is that the union $A_1 \cup B_2$ is equal to $A_1 \cup A_2$ and the sets $A_1$ and
$B_2$ are disjoint. (What happens if $B_2$ is finite?).

Now, explain how the more general statement in (i) follows.

__Solution__. Since $A_1$ is countable, there exists a 1-1 and onto map
$f: \N \rightarrow A_1$.

If $B_2$ is finite, then $B_2 = \{b_1, b_2, \ldots, b_N\}$ where $N$ is the number of
elements in $B_2$. Define the map $g: \N \rightarrow A_1 \cup B_2$ by

$$
g(n)
= \left\{\begin{array}{ll}
  b_i    && \textrm{if $n \le N$} \\
  f(n-N) && \textrm{if $n > N$}. \\
\end{array}\right.
$$

$g$ is 1-1 because no two $n$ map to the same value. Suppose $c \in A_1 \cup B_2$, then
$c \in A_1$ or $c \in B_2$. In the former case, $c = a_i$ for some $i$, so
$g(i+N) = f(i) = c$ by construction. In the latter case, $c = b_i$ for some $i$, so
$g(i) = c$.  Thus, $g$ is onto. Since $g$ is 1-1 and onto, $\N \sim A_1 \cup B_2$ and hence
$A_1 \cup B_2 = A_1 \cup A_2$ is countable.

If $B_2$ is infinite, then there exists a 1-1 and onto map $h: \N \rightarrow B_2$. Define
the map $g: \N \rightarrow A_1 \cup B_2$ by

$$
g(n)
= \left\{\begin{array}{ll}
  f(n / 2)     && \textrm{if $n$ is even} \\
  h((n-1) / 2) && \textrm{if $n$ is odd}. \\
\end{array}\right.
$$

$g$ is 1-1 because no two $n$ map to the same value by definition of $f$ and $h$. Suppose
$c \in A_1 \cup B_2$, then $c \in A_1$ or $c \in B_2$. In the former case, $c = f(i)$ for
some $i$, so $h(2i) = f(i) = c$ by construction. In the latter case, $c = h(i)$ for some
$i$, so $g(2i + 1) = h(i) = c$. Thus, $g$ is onto. Since $g$ is 1-1 and onto,
$\N \sim A_1 \cup B_2$ and hence $A_1 \cup B_2 = A_1 \cup A_2$ is countable.

The result for finite unions of countable sets follows directly from induction.

#### 1.5.3.b.

__Problem__. Explain why induction _cannot_ be used to prove part (ii) of Theorem 1.5.8
from part (i).

__Solution__. Induction cannot be used to prove part (ii) of Theorem 1.5.8 because
induction can only be used to prove a statement is true for any _finite_ value of $n$.
The limiting case $n \rightarrow \infty$ is not covered by induction.

#### 1.5.3.c.

__Problem__. Show how rearranging $\N$ into the two-dimensional array

$$
\begin{array}{cccccc}
 1 &  3 &  6 & 10 & 15 & \cdots \\
 2 &  5 &  9 & 14 & \cdots & \\
 4 &  8 & 13 & \cdots & & \\
 7 & 12 & \cdots & & & \\
11 & \cdots & & & & \\
 \vdots & & & & & \\
\end{array}
$$

leads to a proof of Theorem 1.5.8 (ii).

__Solution__. As in part (a), we first construct a collection of disjoint sets with the
same infinite union: $B_1 = A_1$,
$B_n = A_n \backslash \left( \bigcup_{k=1}^{n-1} A_k \right)$. Then the $B_n$ are disjoint
and $\bigcup_{n=1}^\infty A_n = \bigcup_{n=1}^\infty B_n$.

If all of the $B_n$ are infinite, then we can arrange the elements of $B_n$ in the
following manner:

$$
\begin{array}{cccccc}
 b_{11} & b_{12} & b_{13} & b_{14} & b_{15} & \cdots \\
 b_{21} & b_{22} & b_{23} & b_{24} & \cdots & \\
 b_{31} & b_{32} & b_{33} & \cdots & & \\
 b_{41} & b_{42} & \cdots & & & \\
 b_{51} & \cdots & & & & \\
 \vdots & & & & & \\
\end{array}
$$

Let $f(n)$ be equal to the element $b_{ij}$ that is in the same position as $n$ in the
two-dimensional array. Then $f$ is a 1-1 map from $\N$ onto $\bigcup_{n=1}^\infty B_n$.

* $f$ is 1-1. Because the $B_n$ are disjoint, each element of $\bigcup_{n=1}^\infty$ shows
  up only once in the two-dimensional array. Thus, each value of $n$ maps to only a single
  $b_{ij}$.

* $f$ is onto. Let $b \in \bigcup_{k=1}^\infty B_k$, so it resides somewhere in the
  two-dimensional array. By construction, the value of $n$ in the corresponding
  two-dimensional array formed by elements of $\N$ maps to $b$.

Therefore, $f$ is 1-1 and onto, so $N \sim \bigcup_{n=1}^\infty B_n$ and hence
$\bigcup_{n=1}^\infty B_n = \bigcup_{n=1}^\infty A_n$ is countable.

If any of the $B_n$ are finite, let $C$ be the union of all of the finite $B_n$. If $C$
is infinite, then we can construct a new countable collection of countable sets by adding
$C$ and removing all of the $B_n$ that are finite. The same reasoning as above shows that
$\bigcup_{n=1}^\infty A_n$ is countable. If $C$ is finite, let $N$ be the number of
elements in $C$. We first map the natural numbers $\{ 1, 2, \ldots, N \}$ to $C$. Then, we
start the two-dimensional grid with $N+1$ and use the same reasoning as above to conclude
that $\bigcup_{|B_n| = \infty} B_n = \bigcup_{n=1}^\infty A_n \backslash C$ is countable.
Finally, we can conclude that $\bigcup_{n=1}^\infty A_n$ is countable because the union
of a finite set and a countable set is countable.

--------------------------------------------------------------------------------------------
### 1.5.4.

#### 1.5.4.a.

__Problem__. Show $(a, b) \sim \R$ for any interval $(a, b)$.

__Solution__. Define

$$
f(x) = \frac{x - (a+b) / 2}{(x-a)(x-b)}.
$$

Then

$$
\begin{align}
f'(x)
&= \frac{1}{(x-a)(x-b)} - \frac{2 (x - (a+b) / 2)^2}{(x-a)^2(x-b)^2}  \\
&= \frac{1}{(x-a)^2(x-b)^2}
   \left( x^2 - (a+b)x + ab - 2x^2 + 2 (a+b) x - \frac{(a+b)^2}{2} \right) \\
&= \frac{1}{(x-a)^2(x-b)^2} \left( -x^2 + (a+b)x + ab - \frac{(a+b)^2}{2} \right) \\
&= \frac{1}{(x-a)^2(x-b)^2}
   \left(
     -\left( x - \frac{a+b}{2} \right)^2
     + \frac{(a+b)^2}{4} + ab - \frac{(a+b)^2}{2}
   \right) \\
&= \frac{1}{(x-a)^2(x-b)^2}
   \left(
     -\left( x - \frac{a+b}{2} \right)^2 - \frac{(a-b)^2}{4}
   \right) \\
&= -\frac{1}{(x-a)^2(x-b)^2}
   \left(
     \left( x - \frac{a+b}{2} \right)^2 + \frac{(a-b)^2}{4}
   \right).
\end{align}
$$

Observe that

* $f \rightarrow \infty$ as $x \rightarrow a$,

* $f \rightarrow -\infty$ as $x \rightarrow b$, and

* $f$ is strictly decreasing because $f'$ is strictly negative.

Therefore, $f$ is a 1-1 and onto function from the interval $(a, b)$ to $\R$.

#### 1.5.4.b.

__Problem__. Show that any unbounded interval like $(a, \infty) = \{ x : x > a \}$ has the
same cardinality as $\R$ as well.

__Solution__. Let $f(x) = \ln(x-a)$. Then $f'(x) = (x-a)^{-1}$ for $x > a$.

Observe that

* $f \rightarrow -\infty$ as $x \rightarrow a$,

* $f \rightarrow \infty$ as $x \rightarrow \infty$, and

* $f$ is strictly increasing because $f'$ is strictly positive.

Therefore, $f$ is a 1-1 and onto function from the interval $(a, b)$ to $\R$.

#### 1.5.4.c.

__Problem__. Using open intervals makes it more convenient to produce the required 1-1,
onto functions, but it is not really necessary. Show that $[0, 1) \sim (0, 1)$ by
exhibiting a 1-1 onto function between the two sets.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 1.5.5.

#### 1.5.5.a.

__Problem__. Why is $A \sim A$ for every set $A$?

__Solution__. The identity function $f(a) = a$ for all $a \in A$ is 1-1 and onto.

#### 1.5.5.b.

__Problem__. Given sets $a$ and $B$, explain why $A \sim B$ is equivalent to asserting
$B \sim A$?

__Solution__. $A \sim B$ implies the existence of a 1-1 function $f$ from $A$ onto $B$.
Since $f$ is 1-1 and onto, the inverse function $g(b) = a$ when $f(a) = b$ is well-defined
because (1) for each $b \in B$, there exists an $a \in A$ such that $f(a) = b$ and (2)
for each $b \in B$, there exists only one $a$ such that $f(a) = b$. $g$ is 1-1 because
$g(b) = g(c)$ implies $b = f(g(b)) = f(g(c)) = c$. $g$ is onto because for each $a \in A$,
there exists a $b \in B$ such that $f(a) = b$. In other words, for each $a \in A$, there
exists a $b \in B$ such that $g(b) = a$. Thus, $g$ is 1-1 and onto, so $B \sim A$.

#### 1.5.5.c.

__Problem__. For three sets $A$, $B$, and $C$, show that $A \sim B$ and $B \sim C$ implies
$A \sim C$. These three properties are what is meant by saying that $\sim$ is an
_equivalence relation_.

__Solution__. Since $A \sim B$ and $B \sim C$, there exist 1-1 and onto maps
$f: A \rightarrow B$ and $b: B \rightarrow C$. Define $h = g \circ f$. Suppose that
$h(a) = h(a')$. Then

$$
g(f(a)) = g(f(a'))
\Rightarrow f(a) = f(a')
\Rightarrow a = a'
$$

where the implications follow because $g$ and $f$ are 1-1. Thus, $h$ 1-1. Now, let
$c \in C$. Then there exists $b \in B$ such that $g(b) = c$. Similarly, there exists
$a \in A$ such that $f(a) = b$. Combining these observations, there exist $a \in A$ such
that $h(a) = g(f(a)) = g(b) = c$, which implies that $h$ is onto. Since there exists a 1-1
function $h$ from $A$ onto $C$, we can conclude that $A \sim C$.

--------------------------------------------------------------------------------------------
### 1.5.6.

#### 1.5.6.a.

__Problem__. Give an example of a countable collection of disjoint open intervals.

__Solution__. $I_n = (n, n+1)$ for all $n \in \N$.

#### 1.5.6.b.

__Problem__. Given an example of an uncountable collection of disjoint open intervals, or
argue that no such collection exists.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 1.5.7.

Consider the open interval $(0, 1)$, and let $S$ be the set of points in the open unit
square; that is $S = \{ (x,y) : 0 < x,y < 1 \}$.

#### 1.5.7.a.

__Problem__. Find a 1-1 function that maps $(0, 1)$ into, but not necessarily onto, $S$.
(This is easy.)

__Solution__. $f(x) = (x, x)$ is a 1-1 from $(0, 1)$ to $S$.

#### 1.5.7.b.

__Problem__. Use the fact that every real number has a decimal expansion to produce a 1-1
function that maps $S$ into $(0, 1)$. Discuss whether the formulated function is onto.
(Keep in mind that any terminating decimal expansion such as $.235$ represents the same
real number as $.2349999\ldots$ .)

__Solution__. To avoid redundancy, use the terminating decimal expansion for $x \in (0, 1)$
that has such an expansion. Using the decimal expansions of $x$ and $y$, define the
map from $S$ to $(0, 1)$ by $f(x, y) = .x_1 y_1 x_2 y_2 \ldots$ where
$x = .x_1 x_2 \ldots$ and $y = .y_1 y_2 \ldots.$ Then $f$ is 1-1 because every number
in $(0, 1)$ has a unique decimal representation with unique even and odd decimal places.

$f$ is not onto. Consider $z = .105$. Since we all numbers with terminating decimal
expansions are represented in terminated form, $f(x, y) = z$ only if $(x, y) = (0.15, 0)$.
However, $(0.15, 0)$ is not in $S$, so there is no $(x, y)$ that $f$ maps to $z$.

The Schroder-Bernstein Theorem discussed in Exercise 1.5.11 can now be applied to
conclude that $(0,1) \sim S$.

--------------------------------------------------------------------------------------------
### 1.5.8.

__Problem__. Let $B$ be a set of positive real numbers with the property that adding
together any finite subset of elements from $B$ always gives a sum of $2$ or less. Show
that $B$ must be finite or countable.

__Solution__. Observe that the bound of $2$ on finite sums of elements of $B$ implies that
$b \le 2$ for all $b \in B$. Suppose $B$ is uncountable. Let $I_n = (2^{-n}, 2^{-(n-1)}]$
be a countable set of disjoint sets whose union is with interval $(0, 2]$. Then

$$
\begin{align}
B
&= B \cap (0, 2] \\
&= B \cap \left( \bigcup_{n=1}^\infty \cap I_n \right) \\
&= \bigcup_{n=1}^\infty B \cap I_n.
\end{align}
$$

Since $B$ is uncountable, $B \cap I_n$ must be uncountable for at least one $n$ (note
that we really only need that $B \cap I_n$ is infinite). Taking $N = 2^{n+1}$ elements
$\{ b_1, \ldots, b_N \}$ from $B \cap I_n$, we obtain the contradiction that the finite sum
$\sum_{i=1}^N b_i > 2^{n+1} 2^{-n} = 2$ since $b_i > 2^{-n}$ for each $b_i$ in the sum.

--------------------------------------------------------------------------------------------
### 1.5.9.

A real number $x \in \R$ is called _algebraic_ if there exists integers
$a_0, a_1, a_2, \ldots, a_n \in \Z$, not all zero, such that

$$
a_n x^n + a_{n-1} x^{n-1} + \cdots + a_1 x + a_0 = 0.
$$

Said another way, a real number is algebraic if it is the root of a polynomial with integer
coefficients. Real numbers that are no algebraic are called _transcendental_ numbers.
Reread the last paragraph of Section 1.1. The final question posed here is closely related
to the question of whether transcendental numbers exist.

### 1.5.9.a.

__Problem__. Show that $\sqrt{2}$, $\sqrt[3]{2}$, and $\sqrt{3} + \sqrt{2}$ are algebraic.

__Solution__.

$\sqrt{2}$ is a root of $x^2 - 2$.

$\sqrt[3]{2}$ is a root of $x^3 - 2$.

To find a polynomial that has $\sqrt{3} + \sqrt{2}$ as a root, observe that

$$
(x - (\sqrt{3} + \sqrt{2}) (x + (\sqrt{3} + \sqrt{2})
= x^2 - (5 + 2 \sqrt{6})
= (x^2 - 5) - 2 \sqrt{6}
$$

Thus multiplying this expression by $(x^2 - 5) + 2 \sqrt{6}$ yields the polynomial

$$
((x^2 - 5) - 2 \sqrt{6}) ((x^2 - 5) + 2 \sqrt{6})
= (x^2 - 5)^2 - 24
= x^4 - 10 x^2 + 1.
$$

By construction $\sqrt{3} + \sqrt{2}$ is a root of this last polynomial.

### 1.5.9.b.

__Problem__. Fix $n \in \N$, and let $A_n$ be the algebraic numbers obtained as roots of
polynomials with integer coefficients that have degree $n$. Using the fact that every
polynomial has a finite number of roots, show that $A_n$ is countable.

__Solution__. There is a 1-1 and onto map from $(n+1)$-tuples of integers to polynomials of
degree $n$ with integer coefficients. Thus, the set of degree $n$ polynomials is countable
because the set of $(n+1)$-tuples of integers is countable. Since every polynomial has a
finite number of roots, the set of roots of $n$-th degree polynomials $A_n$ is a countable
union of finite sets, which implies that it is countable.

### 1.5.9.c.

__Problem__. Now, argue that the set of all algebraic numbers is countable. What may we
conclude about the set of transcendental numbers?

__Solution__. The set of algebraic numbers is the union of $A_n$ over all $n \in N$, so
it is a countable union of countable sets. Therefore, the set of algebraic numbers is
countable. Since $\R$ is uncountable and $\R$ is the union of algebraic and transcendental
numbers, the set of transcendental numbers must be uncountable.

--------------------------------------------------------------------------------------------
### 1.5.10.

### 1.5.10.a.

__Problem__. Let $C \subseteq [0, 1]$ be uncountable. Show that there exists $a \in (0, 1)$
such that $C \cap [a, 1]$ is uncountable.

__Solution__. Let $a_n = 1/2^n$ for $n \ge \{0\} \cup \N$. Suppose that $C \cap [a_n, 1]$
is finite or countable for all $n$. Observing that $\bigcup_{n=1}^\infty [a_n, 1] = [0, 1]$,

$$
C \cap [0, 1]
= C \cap \left( \bigcup_{n=1}^\infty [a_n, 1] \right)
= \bigcup_{n=1}^\infty C \cap [a_n, 1].
$$

In other words, $C \cap [0, 1]$ is countable because it is a countable union of finite or
countable sets - a contradiction with the assumption that $C \cap [0, 1]$ is uncountable.
Therefore, $C \cap [a_n, 1]$ must be uncountable for some $a_n$, which yields the desired
result.

### 1.5.10.b.

__Problem__. Now let $A$ be the set of all $a \in (0, 1)$ such that $C \cap [a, 1]$ is
uncountable, and set $\alpha = \sup A$. Is $C \cap [\alpha, 1]$ an uncountable set?

__Solution__. No. As a counterexample, consider $C = [0, 1]$. Then $C \cap [a, 1] = [a, 1]$
for all $a \in (0, 1)$. Thus, $A = (0, 1)$. However, $\alpha = \sup A = 1$ and
$C \cap [1, 1] = \{1\}$ is finite.

### 1.5.10.c.

__Problem__. Does the statement in (a) remain true if "uncountable" is replaced by
"infinite"?

__Solution__. No. Consider $C = \{ 1, 1/2, 1/2^2, \ldots \}$. Observe that $C \cap [a, 1]$
contains only the powers of $1/2$ that are no less than $a$. If $a > 0$, there are only a
finite number of powers of $1/2$ greater than or equal to $a$. Therefore, $C \cap [a, 1]$
is finite for all $a \in (0, 1)$.

--------------------------------------------------------------------------------------------
### 1.5.11. Schoder-Bernstein Theorem

Assume there exists a 1-1 function $f : X \rightarrow Y$ and another 1-1 function
$g : Y \rightarrow X$. Follow the steps to show that there exists a 1-1, onto function
$h: X \rightarrow Y$ and hence $X \sim Y$.

The strategy is to partition $X$ and $Y$ into components

$$
  X = A \cup A' \textrm{ and } Y = B \cup B'
$$

with $A \cap A' = \emptyset$ and $B \cap B' = \emptyset$, in such a way that $f$ maps $A$
onto $B$, and $g$ maps $B'$ onto $A'$.

#### 1.5.11.a.

__Problem__. Explain how achieving this would lead to a proof that $X \sim Y$.

__Solution__. With partitions of $X$ and $Y$ satisfying the above properties, $f$ is a 1-1
map from $A$ onto $B$ and $g$ is a 1-1 map from $B'$ onto $A'$. Thus, we can define

$$
h(x) = \left\{
          \begin{array}{rl}
            f(x)      & \textrm{for $x \in A$} \\
            g^{-1}(x) & \textrm{for $x \in A'$}
          \end{array}
        \right.
$$

Note that $g^{-1}$ is well-defined because $g$ is 1-1 and onto. Defined in this manner,
$h$ is 1-1 and onto for the following reasons.

* $h$ is 1-1. For $x \in A$, $h$ is 1-1 because $f$ is 1-1. For $x \in A'$, $h$ is 1-1
  because $g$ is 1-1 and onto, which implies the existence of an inverse function
  $g^{-1}$ having the same properties (in particular, $g^{-1}$ is 1-1).

* $h$ is onto. For $y \in B$, $h$ is onto because $f$ is and onto. For $y \in B'$, $h$ is
  onto because $g$ is 1-1 and onto, which implies the existence of an inverse function
  $g^{-1}$ having the same properties (in particular, $g^{-1}$ is onto).

#### 1.5.11.b.

__Problem__. Set $A_1 = X \backslash g(Y) = \{ x \in X : x \notin g(Y) \}$ (what happens if
$A_1 = \emptyset$?) and inductively define a sequence of sets letting $A_{n+1} = g(f(A_n))$.
Show that $\{ A_n : n \in \N \}$ is a pairwise disjoint collection of subsets of $X$, while
$\{ f(A_n) : n \in \N \}$ is a similar collection in $Y$.

__Solution__. Let $A_1 = X \backslash g(Y) = \{ x \in X : x \notin g(Y) \}$. If
$A_1 = \emptyset$, then $g$ is onto, which implies that $X \sim Y$ because $g$ is a 1-1 and
onto map from $Y$ to $X$. If $A_1 \ne \emptyset$, we can define a sequence of sets
$A_{n+1} = g(f(A_n))$. We can inductively prove that $\{ A_n : n \in \N \}$ is a pairwise
disjoint collection of subsets of $X$. Clearly $A_1$ and $A_2$ are disjoint because
each $x_2 \in A_2$ is equal to $x_2 = g(f(x_1))$ for some $x_1 \in A_1$. Thus,
$x_2 \in g(Y)$, so it cannot be in $A_1$. For the inductive step, assume that
$A_1, A_2, \ldots, A_{n-1}$ are pairwise disjoint. Consider $x_n \in A_n$. Then
$x_n = g(f(x_{n-1}))$ for some $x_{n-1} \in A_{n-1}$. By the same reasoning as for
$x \in A_2$, $x_n$ cannot be an element of $A_1$. Suppose $x_n \in A_m$ for
$2 \le m \le {n-1}$. Then $x_n = g(f(x_{m-1}))$ for some $x_{m-1} \in A_{m-1}$, which
implies that $g(f(x_{n-1})) = g(f(x_{m-1}))$. Thus, $x_{n-1} = x_{m-1}$ because $f$ and $g$
are both 1-1. However, this contradicts our assumption that $A_1, A_2, \ldots, A_{n-1}$
are disjoint (because $m-1$ is strictly less than $n-1$). In other words, $x_n$ cannot be
an element of $A_m$ for $m \le n-1$, so $A_n$ is pairwise disjoint from
$A_1, A_2, \ldots, A_{n-1}$. Therefore, we can conclude that $\{ A_n : n \in \N \}$ is a
pairwise disjoint collection of subsets of $X$.

That the $\{ f(A_n) : n \in \N \}$ are a disjoint collection of subsets of $Y$ follows
because $f$ is 1-1 (because 1-1 functions map disjoint subsets of $X$ to disjoint subsets
of $Y$).

#### 1.5.11.c.

__Problem__. Let $A = \cup_{n=1}^\infty A_n$ and $B = \cup_{n=1}^\infty f(A_n)$. Show that
$f$ maps $A$ onto $B$.

__Solution__. Let $y \in B$. Then $y \in f(A_n)$ for some $n$, which implies that there
exists $x \in A_n$ such that $y = f(x)$. Therefore, $f$ maps $A$ onto $B$.

#### 1.5.11.d.

__Problem__. Let $A' = X \backslash A$ and $B' = Y \backslash B$. Show $g$ maps $B'$ onto
$A'$.

__Solution__. Let $x \in A'$. Then $x \in \bigcap_{n=1}^\infty X \backslash A_n$. In
particular, $x \in A_1$, so $x \in g(Y)$. In other words, there exists $y \in Y$ such that
$g(y) = x$. Suppose $y \in B$. Then $y \in f(A_n)$ for some $n$, which implies that
$g(y) \in A_{n+1}$ -- contradicting the assumption that $x \in A'$. Therefore, $y \in B'$,
so we can conclude that $g$ maps $B'$ onto $A'$.

--------------------------------------------------------------------------------------------
