Understanding Analysis (S. Abbott): Section 1.3 Exercises
=========================================================

--------------------------------------------------------------------------------------------
### Notation

* $\newcommand{\N}{\mathbb{N}}$
  The set of natural numbers: $\N$

* $\newcommand{\Q}{\mathbb{Q}}$
  The set of rational numbers: $\Q$

* $\newcommand{\R}{\mathbb{R}}$
  The set of real numbers: $\R$

--------------------------------------------------------------------------------------------
### 1.3.1.

#### 1.3.1.a.

__Problem__. Write a formal definition in the style of Definition 1.3.2 for the _infimum_
or _greatest lower bound_ of a set.

__Solution__. A real number $s$ is the _greater lower bound_ for a set $A \subseteq \R$
if it meets the following two criteria:

  (i) $s$ is a lower bound for $A$;

  (ii) if $b$ is any lower bound for $A$, then $s \ge b$.

#### 1.3.1.b.

__Problem__. Now, state and prove a version of Lemma 1.3.8 for the greatest lower bound.

__Solution__.

_Lemma_. Assume $s \in \R$ is a lower bound for a set $A \subseteq \R$. Then, $s = \inf A$
if and only if, for every choice of $\epsilon > 0$, there exists an element $a \in A$
satisfying $s + \epsilon > a$.

_Proof_. $(\Rightarrow)$ Let $s = \inf A$ and $\epsilon > 0$. Then $s + \epsilon > s$, so
(ii) implies that $s + \epsilon$ cannot be a lower bound for $A$. Therefore, there exists
$a \in A$ such that $a < s + \epsilon$.

$(\Leftarrow)$ Let $s$ be a lower bound for $A$ with the property that $s + \epsilon$
is no longer a lower bound for $A$. Then any $b > s$ cannot be a lower bound for $A$
because $b = s + (b - s)$. Therefore, any lower bound $b$ for $A$ must be less than or
equal to $s$, which implies that $s$ satisfies the two criteria for $\inf A$.

--------------------------------------------------------------------------------------------
### 1.3.2.

Give an example of each of the following, or state that the request is impossible.

#### 1.3.2.a.

__Problem__. A set $B$ with $\inf B \ge \sup B$.

__Solution__. Let $B = \{ 0 \}$. $\inf B = 0 = \sup B$, which satisfies the desired
inequality.

#### 1.3.2.b.

__Problem__. A finite set that contains its infimum but not its supremum.

__Solution__. Not possible. For a finite set of real numbers, there is always an element
$x$ with the largest value. This element $x$ is the supremum for the set because it is an
upper bound for the set and any smaller value would be less than $x$. Therefore, the
supremum of any finite set of real numbers is contained in the set. Note that an analogous
line of reasoning shows that the same property holds for the infimum of finite sets of real
numbers.

#### 1.3.2.c.

__Problem__. A bounded subset of $\Q$ that contains its supremum but not its infimum.

__Solution__. Let $B = \Q \cap (0, 1] = \{ x \in \Q : 0 < x \le 1 \}$. This set satisfies
the desired properties because (1) $\inf B = 0 \notin B$ and (2) $\sup B = 1 \in B$.

--------------------------------------------------------------------------------------------
### 1.3.3.

#### 1.3.3.a.

__Problem__. Let $A$ be nonempty and bounded below, and define
$B = \{ b \in \R : b \textrm{ is a lower bound for } A \}$. Show that $\sup B = \inf A$.

__Solution__. First, note that $B$ is not empty because $A$ is nonempty and bounded
below. Observe that $B$ is bounded above because for any $a \in A$, $a \ge b$ for all
$b \in B$. Therefore, the Axiom of Completeness implies that $\sup B$ exists.

Let $s = \sup B$. To prove that $s$ is the infimum of $A$, we need to show (1) that
$s$ a lower bound for $A$ and (2) that if $l$ is any lower bound for $A$, then $l \le s$.

Suppose $s$ is not a lower bound for $A$, then there exists $a \in A$ such that $a < s$.
Since $s = \sup B$, Lemma 1.3.8. implies that there exists $b \in B$ such that $a < b$,
which contradicts the definition of $B$ as the set of all lower bounds of $A$ (i.e.,
$b \le a$ for all $a \in A$ and $b \in B$). Thus, $s$ is a lower bound for $A$. The second
condition for $s$ to be the infimum of $A$ is satisfied because any lower bound $b$ for $A$
is contained in $B$, which implies that $b \le s$ by the definition of $\sup B$. Since $s$
satisfies the two properties required of the infimum of $A$, $\sup B = \inf B$.

_Alternate Partial Solution_. Note: the following solution assumes the existence of an
infimum for $A$. This logical weakness does not affect the previous solution.

Assume that $\inf A$ exists. Then $\inf A \ge b$ for all $b \in B$ because $\inf A$ is
greater than or equal to all lower bounds for $A$. In other words, $\inf A$ is an upper
bound for $B$. Therefore, $\sup B \le \inf A$ because $\sup B$ is less than or equal to all
upper bounds for $B$.

Now suppose that $\inf A$ is strictly greater than $\sup B$. Then there exists
$\epsilon > 0$ such that $\sup B + \epsilon < \inf A$, which implies that
$\sup B + \epsilon \le a$ for all $a \in A$. That is, $\sup B + \epsilon$ is a lower bound
for $A$. Thus, $\sup B + \epsilon \in B$, which implies that $\sup B + \epsilon \le \sup B$,
a contradiction. Therefore, we conclude that $\sup B = \inf A$.

#### 1.3.3.b.

__Problem__. Use (a) to explain why there is no need to assert greatest lower bounds exist
as part of the Axiom of Completeness.

__Solution__. For any nonempty set of real numbers $A$ that is bounded below, we can
construct the set $B$ of lower bounds for $A$. Part (a) demonstrates that $\sup B$
satisfies the properties of the infimum of $A$, which implies that $\inf A$ exists.
Since this construction is valid for _arbitrary_ nonempty sets that are bounded below,
there is no need for the Axiom of Completeness to include a separate assertion for the
existence of greatest lower bounds.

--------------------------------------------------------------------------------------------
### 1.3.4.

Let $A_1, A_2, A_3, \ldots$ be a collection of nonempty sets, each of which is bounded
above.

#### 1.3.4.a.

__Problem__. Find a formula for $\sup(A_1 \cup A_2)$. Extend this to
$\sup\left( \bigcup_{k=1}^n A_k \right)$.

__Solution__.

* $\sup(A_1 \cup A_2) = \max( \sup A_1, \sup A_2 )$.

  _Proof_. Observe that $\sup(A_1 \cup A_2) \ge a$ for all $a \in A_1 \cup A_2$. In
  particular, $\sup(A_1 \cup A_2) \ge a$ for $a \in A_1$, which implies that $s$ is an
  upper bound for $A_1$ so that $\sup(A_1 \cup A_2) \ge \sup A_1$. Similarly,
  $\sup (A_1 \cup A_2) \ge \sup A_2$. Therefore,
  $\sup(A_1 \cup A_2) \ge \max( \sup A_1, \sup A_2 )$.

  Next, observe that $\sup A_1 \ge a$ for all $a \in A_1$ and $\sup A_2 \ge a$ for all
  $a \in A_2$, which implies that $\max( \sup A_1, \sup A_2 ) \ge a$ for $a \in A_1$ or
  $a \in A_2$. In other words, $\max( \sup A_1, \sup A_2 ) \ge a$ for $a \in A_1 \cup A_2$.
  Therefore, $\max( \sup A_1, \sup A_2 )$ is an upper bound for $A_1 \cup A_2$ so that
  $\max( \sup A_1, \sup A_2 ) \ge \sup( A_1 \cup A_2 )$.

  Combining these results yields the proposed formula:
  $\sup( A_1 \cup A_2 ) = \max( \sup A_1, \sup A_2 )$.

* $\sup\left( \bigcup_{k=1}^n A_k \right) = \max_{k \in \N} \sup A_k$.

  _Proof_. The proof of this formula is a simple generalization of the proof for the case
  $n = 2$.

#### 1.3.4.b.

__Problem__. Consider $\sup\left( \bigcup_{k=1}^n A_k \right)$. Does the formula in (a)
extend to the infinite case?

__Solution__. The formula in part (a) extends to the infinite case _if_ we replace
$\max_k$ with $\sup_k$:

$$
\sup \left( \bigcup_{k=1}^\infty A_k \right) = \sup_k \sup A_k.
$$

To see that this formula is correct, let $s = \sup_k \sup A_k$. By the definition of $\sup$,
$s \ge \sup A_n$ for all $n \in \N$, which implies that $s$ is an upper bound for all $A_k$.
Therefore, $s$ is an upper bound for $\bigcup_{k=1}^\infty A_k$, so we can conclude that
$s \ge \sup \left( \bigcup_{k=1}^\infty A_k \right)$. To prove the reverse inequality,
observe that, for all $k \in \N$,
$\sup A_k \le \sup \left( \bigcup_{k=1}^\infty A_k \right)$ because
$A_k \subseteq \bigcup_{k=1}^\infty A_k$. Therefore,
$s \le \sup \left( \bigcup_{k=1}^\infty A_k \right).$ Combining the two inequalities
relating $s$ and $\sup \left( \bigcup_{k=1}^\infty A_k \right)$ yields the desired result.

--------------------------------------------------------------------------------------------
### 1.3.5.

As in Example 1.3.7, let $A \subseteq \R$ be nonempty and bounded above,
and let $c \in \R$. This time define the set $cA = \{ ca : a \in A \}$.

#### 1.3.5.a.

__Problem__. If $c \ge 0$, show that $\sup(cA) = c \sup A$.

__Solution__. First, observe that $cA$ is bounded above because if $M$ is an upper bound
for $A$, then $cM$ is an upper bound for $cA$. Therefore, the Axiom of Completeness implies
that $\sup(cA)$ exists.

Next, let $s = \sup A$. Then $s \ge a$ for all $a \in A$, which implies that $cs \ge ca$
for all $a \in A$. Therefore, $cs$ is an upper bound for $cA$. Now, let $b$ be an arbitrary
upper bound for $cA$. Then $b \ge ca$ for all $a \in A$, which implies that $b/c$ is an
upper bound for $A$ because $b/c \ge a$ for all $a \in A$. By the definition of $\sup A$,
$b/c \ge \sup A = s$, so we can conclude that $b \ge cs$. Therefore, $cs$ satisfies the two
properties required of the least upper bound of $cA$. In other words, $\sup(cA) = c \sup A$.

_Alternate Proof for $\sup(cA) = c \sup A$_. Let $\epsilon > 0$ and consider
$s = \sup(cA)$. Then, Lemma 1.3.8 implies the existence of $ca \in cA$ such that
$ca > s - c \epsilon$, or equivalently that $a > s/c - \epsilon$. Therefore, applying
Lemma 1.3.8 again, we can conclude that $\sup A = s/c$, which yields the desired result.

#### 1.3.5.b.

__Problem__. Postulate a similar type of statement for $\sup(cA)$ for the case $c < 0$.

__Solution__. If $c < 0$, then $\sup(cA) = c \inf A$.

_Proof_. Let $s = \inf A$. Then $s \le a$ for all $a \in A$, which implies that
$cs \ge ca$ for all $a \in A$. Therefore, $cs$ is an upper bound for $cA$. Now, let $b$
be an arbitrary upper bound for $cA$. Then $b \ge ca$ for all $a \in A$, which implies that
$b/c$ is a lower bound for $A$ because $b/c \le a$ for all $a \in A$. By the definition of
$\inf A$, $b/c \le \inf A = s$, so we can conclude that $b \ge cs$. Therefore, $cs$
satisfies the two properties required of the least upper bound of $cA$. In other words,
$\sup(cA) = c \inf A$.

--------------------------------------------------------------------------------------------
### 1.3.6.

Given sets $A$ and $B$, define

$$
A + B = \{ a + b : a \in A \textrm{ and } b \in B \}.
$$

Follow these steps to prove that if $A$ and $B$ are nonempty and bounded above then
$\sup(A + B) = \sup A + \sup B$.

#### 1.3.6.a.

__Problem__. Let $s = \sup A$ and $t = \sup B$. Show $s + t$ is an upper bound for $A + B$.

__Solution__. Let $x \in A + B$. Then there exist $a \in A$ and $b \in B$ such that
$x = a + b$. By the definition of the supremum, $a \le s$ and $b \le t$, so $x \le s + t$.
Therefore, $s + t$ is an upper bound for $A+B$.

#### 1.3.6.b.

__Problem__. Now let $u$ be an arbitrary upper bound for $A + B$, and temporarily fix
$a \in A$. Show $t \le u - a$.

__Solution__. Since $u$ is an upper bound for $A + B$, $u \ge a + b$ for all $b \in B$,
which implies that $u - a$ is an upper bound for $B$. Therefore, $t \le u - a$ by the
definition of supremum.

#### 1.3.6.c.

__Problem__. Finally, show $\sup(A + B) = s + t$.

__Solution__. Rearranging the last inequality from 1.3.6b, we find that $u - t \ge a$ for
all $a \in A$, so we can conclude that $u - t$ is an upper bound for $A$, which implies
that $u - t \ge s$. Therefore, $u \ge s + t$ and $s + t$ satisfies the two criteria needed
to show that it is the supremum of $A + B$.

#### 1.3.6.d.

__Problem__. Construct another proof of this same fact using Lemma 1.3.8.

__Solution__. Let $\epsilon > 0$. Defining $s = \sup A$ and $t = \sup B$, Lemma 1.3.8
implies that there exist $a \in A$ and $b \in B$ such that $a > s - \epsilon/2$ and
$b > t - \epsilon/2$. Therefore, $s + t - \epsilon < a + b \in A + B$, so Lemma 1.3.8
implies that $s + t = \sup(A +B)$.

--------------------------------------------------------------------------------------------
### 1.3.7.

__Problem__. Prove that if $a$ is an upper bound for $A$, and if $a$ is also an element of
$A$, then it must be that $a = \sup A$.

__Solution__. By the definition of $\sup A$,

* $a \le \sup A$ because $a \in A$ and

* $a \ge \sup A$ because $a$ is an upper bound for $A$.

Together, these two inequalities imply that $a = \sup A$.

--------------------------------------------------------------------------------------------
### 1.3.8.

Compute, without proofs, the suprema and infima (if they exist) of the following sets.

#### 1.3.8.a.

__Problem__. $\{ m/n : m, n \in \N \textrm{ with } m < n \}$

__Solution__.

$\sup = 1$. Taking $n = m+1$, $m/n$ gets arbitrarily close to $1$ as $m \rightarrow \infty$.

$\inf = 0$. Taking $m = 1$, $m/n$ gets arbitrarily close to $0$ as $n \rightarrow \infty$.

#### 1.3.8.b.

__Problem__. $\{ (-1)^m / n : m, n \in \N \}$

__Solution__.

$\sup = 1$. Achieved when $m = 0$, $n = 1$.

$\inf = -1$. Achieved when $m = 1$, $n = 1$.

#### 1.3.8.c.

__Problem__. $\{ n / (3n + 1) : n \in \N \}$

__Solution__.

$\sup = 1/3$. As $n \rightarrow \infty$, $n / (3n+1)$ gets arbitrarily close to $1/3$.

$\inf = 1/4$. Achieved when $n = 1$.

#### 1.3.8.d.

__Problem__. $\{ m / (m + n) : m, n \in \N \}$

__Solution__.

$\sup = 1$. For any fixed $n$, $m / (m+n)$ gets artibrarily close to $1$ as
$m \rightarrow \infty$.

$\inf = 0$. Taking $m = 1$, $m / (m+n) = 1 / (1+n)$ gets arbitrarily close to $0$ as
$n \rightarrow \infty$.

--------------------------------------------------------------------------------------------
### 1.3.9.

#### 1.3.9.a.

__Problem__. If $\sup A < \sup B$, show that there exists an element $b \in B$
that is an upper bound for $A$.

__Solution__. Let $\epsilon = (\sup B - \sup A) / 2$. Since $\sup A \ne \sup B$,
$\epsilon > 0$. Lemma 1.3.8 implies that there exists $b \in B$ such that
$b > \sup B - \epsilon$. $b$ is an upper bound for $A$ because
$\sup B - \epsilon = \sup A + \epsilon > \sup A \ge a$ for all $a \in A$.

#### 1.3.9.b.

__Problem__. Give an example to show that this is not always the case if we
only assume $\sup A \le \sup B$.

__Solution__. Let $A = [0, 1]$ and $B = (0, 1)$. Then $\sup A = \sup B$. Observe that
$1 \in A$ and $b \in B$ implies that $b < 1$. Therefore, no element in $B$ can be an upper
bound for $A$.

--------------------------------------------------------------------------------------------
### 1.3.10.

The _Cut Property_ of the real numbers is the following:

If $A$ and $B$ are nonempty, disjoint sets with $A \cup B = \R$ and $a < b$ for all
$a \in A$ and $b \in B$, then there exists $c \in \R$ such that $x \le c$ whenever
$x \in A$ and $x \ge c$ whenever $x \in B$.

#### 1.3.10.a.

__Problem__. Use the Axiom of Completeness to prove the Cut Property.

__Solution__. Let $A$ and $B$ satisfy the conditions in the statement of the Cut Property.
Take any $b \in B$. Then $a < b$ for all $a \in A$. Thus, $A$ is bounded above. By the
Axiom of Completeness, $A$ has a least upper bound $\sup A$. $\sup A$ is the number in
$\R$ with the desired properties.

* $a \le \sup A$ for all $a \in A$ because $\sup A$ is an upper bound for $A$.

* $b \ge \sup A$ for all $b \in B$ because each $b \in $B$ is an upper bound for $A$,
  which implies $\sup A \le b$ because $\sup A$ is the _least_ upper bound.

#### 1.3.10.b.

__Problem__. Show that the implication goes the other way; that is, assume $\R$ possesses
the Cut Property and let $E$ be a nonempty set that is bounded above. Prove that $\sup E$
exists.

__Solution__. Let $B$ be the set of upper bounds for $E$. That is,
$B = \{ b \in \R : b \ge x \textrm{ for all } x \in E\}$. Then $B \cup B^c = \R$. Observe
that $b^c \le b$ for all $b^c \in B^c$ and $b \in B$. Otherwise, $b^c > b$ for some
$b^c \in B^c$ and $b \in B$, which would imply that $b^c > b \ge x$ for all $x \in E$
contradicting the definition of $B$ as the set of all upper bounds for $E$. By the Cut
Property, there exists $c \in \R$ such that $c \ge b^c$ for all $b^c \in B^c$ and $c \le b$
for all $b \in B$.

$c$ satisfies the properties of a least upper bound for $E$.

* $c \in B$ (that is, $c$ is an upper bound for $E$). To prove this result, suppose that
  $c \notin B$, then there exists $x \in E$ such that $c < x$ because $c$ is not an upper
  bound for $E$. Since $c$ is strictly less than $x$, there exists $y \in \R$ such that
  $c < y < x$. Observe that $y$ cannot be in $B$ because $b \ge x > y$ for all $b \in B$
  (by the definition of $B$). On the other hand, $y$ cannot be in $B^c$ because the Cut
  Property implies that $y > x \ge b^c$ for all $b^c \in B^c$. Together, these inequalities
  imply that $y \notin B \cup B^c = \R$, a contradiction. Therefore, $c$ must be an
  element of $B$ and so is an upper bound for $E$.

* $c \le b$ for any upper bound $b$ of $E$. This result follows directly from the
  definition of $B$ and the Cut Property - any upper bound $b$ of $E$ is an element of $B$
  and $c \le b$ for all $b \in B$.

#### 1.3.10.c.

__Problem__. The punchline of parts (a) and (b) is that the Cut Property could be used in
place of the Axiom of Completeness as the fundamental axiom that distinguishes the real
numbers from the rational numbers. To drive this point home, give a concrete example
showing that the Cut Property is not a valid statement when $\R$ is replaced by $\Q$.

__Solution__. Let $A = \{x \in \Q : x \le \sqrt{2} \}$ and
$B = \{x \in \Q : x \ge \sqrt{2} \}$. Then $A \cup B = \Q$. However, the only number $c$
that satisfies the property that $x \le c$ whenever $x \in A$ and $x \ge c$ whenever
$x \in B$ is $c = \sqrt{2}$, which is not a rational number.

--------------------------------------------------------------------------------------------
### 1.3.11.

Decide if the following statements about suprema and infima are true or false.
Give a short proof for those that are true. For any that are false, supply an
example where the claim in question does not appear to hold.

#### 1.3.11.a.

__Problem__. If $A$ and $B$ are nonempty, bounded, and satisfy $A \subseteq B$, then
$\sup A \le \sup B$.

__Solution__. True. Since $A \subseteq B$, $a \in B$ for all $a \in A$, which implies that
$a \le \sup B$ for all $a \in A$. Therefore, $\sup B$ is an upper bound for $A$, so
$\sup A \le \sup B$ by the definition of $\sup A$.

#### 1.3.11.b.

__Problem__. If $\sup A < \inf B$ for sets $A$ and $B$, then there exists a $c \in \R$
satisfying $a < c < b$ for all $a \in A$ and $b \in B$.

__Solution__. True. Since $\sup A \ne \inf B$, $c = (\sup A + \inf B) / 2$ satisfies
$\sup A < c < \inf B$. By the definition of $\sup$ and $\inf$,

$$
a \le \sup A < c < \inf B \le b
$$

for all $a \in A$ and $b \in B$.

#### 1.3.11.c.

__Problem__. If there exists a $c \in \R$ satistfying $a < c < b$ for all $a \in A$ and
$b \in B$, then $\sup A < \inf B$.

__Solution__. False. Consider the sets $A = (0, 1)$ and $B = (1, 2)$. Then $a < 1 < b$ for
all $a \in A$ and $b \in B$, but $\sup A = 1 = \inf B$.

--------------------------------------------------------------------------------------------
