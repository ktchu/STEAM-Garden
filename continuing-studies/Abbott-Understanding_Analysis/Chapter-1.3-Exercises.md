Understanding Analysis (S. Abbott): Section 1.3 Exercises
=========================================================

-------------------------------------------------------------------------------
### 1.3.1.

#### 1.3.1.a.

__Problem__. Write a formal definition in the style of Definition 1.3.2 for the
_infimum_ or _greatest lower bound_ of a set.

__Solution__. TODO

#### 1.3.1.b.

__Problem__. Now, state and prove a version of Lemma 1.3.8 for the greatest
lower bound.

__Solution__. TODO

-------------------------------------------------------------------------------
### 1.3.2.

Give an example of each of the following, or state that the request is
impossible.

#### 1.3.2.a.

__Problem__. A set $B$ with $\inf B \ge \sup B$.

__Solution__. Let $B = \{ 0 \}$. $\inf B = 0 = \sup B$, which satisfies the
desired inequality.

#### 1.3.2.b.

__Problem__. A finite set that contains its infimum but not its supremum.

__Solution__. Not possible. For a finite set of real numbers, there is always
an element $x$ with the largest value. This element $x$ is the supremum for the
set because it is an upper bound for the set and any smaller value would be
less than $x$. Therefore, the supremum of any finite set of real numbers is
contained in the set. Note that an analogous line of reasoning shows that the
same property holds for the infimum of finite sets of real numbers.

#### 1.3.2.c.

__Problem__. A bounded subset of $\mathbb{Q}$ that contains its supremum but
not its infimum.

__Solution__. Let $B = \{ x \in \mathbb{Q} : 0 < x \le 1 \}$. This set
satisfies the desired properties because (1) $\inf B = 0 \notin B$ and
(2) $\sup B = 1 \in B$.

-------------------------------------------------------------------------------
### 1.3.3.

#### 1.3.3.a.

__Problem__. Let $A$ be nonempty and bounded below, and define
$B = \{ b \in \mathbb{R} : b \textrm{ is a lower bound for } A \}$. Show that
$\sup B = \inf A$.

__Solution__. First, $\inf A \ge b$ for all $b \in B$ because $\inf A$ is
greater than or equal to all lower bounds for $A$. In other words, $\inf A$ is
an upper bound for $B$. Therefore, $\sup B \le \inf A$ because $\sup B$ is
less than or equal to all upper bounds for $B$.

To prove the reverse inequality $\sup B \ge \inf A$, consider
$x = \sup B + \epsilon$ for any value of $\epsilon > 0$. If $x < \inf A$, then
$x$ is a lower bound for $A$. In other words, $x \in B$, which implies that
$x = \sup B + \epsilon \le \sup B$, a contradiction. Therefore, we conclude
that $\sup B + \epsilon \ge \inf A$ for every $\epsilon > 0$, which implies
that $\sup B \ge \inf A$.

Taken toegher, the inequalities yield the desired result: $\sup B = \inf A$.

#### 1.3.3.b.

__Problem__. Use (a) to explain why there is no need to assert greatest lower
bounds exist as part of the Axiom of Completeness.

__Solution__. For any nonempty set of real numbers $A$ that is bounded below,
we can construct the set $B$ of lower bounds for $A$. Observe that $B$ is
bounded above because for any $a \in A$, $a \ge b$ for all $b \in B$, by
construction. Therefore, the Axiom of Completeness implies that $\sup B$ exists.
By part (a) of this problem, $\inf A$ exists because it is equal to $\sup B$.
Since this construction is valid for _arbitrary_ $A$, there is no need for the
Axiom of Completeness to include a separate assertion for the existence of
greatest lower bounds.

-------------------------------------------------------------------------------
### 1.3.4.

Let $A_1, A_2, A_3, \ldots$ be a collection of nonempty sets, each of which is
bounded above.

#### 1.3.4.a.

__Problem__. Find a formula for $\sup(A_1 \cup A_2)$. Extend this to
$\sup\left( \bigcup_{k=1}^n A_k \right)$.

__Solution__. $\sup(A_1 \cup A_2) = \max( \sup A_1, \sup A_2 )$.
$\sup\left( \bigcup_{k=1}^n A_k \right) = \max_{k \in \mathbb{N}} \sup A_k$.

#### 1.3.4.b.

__Problem__. Consider $\sup\left( \bigcup_{k=1}^n A_k \right)$. Does the
formula in (a) extend to the infinite case?

__Solution__. No the formula in part (a) does not extend to the infinite case
$\max_{k \in \mathbb{N}} A_k$ is not guaranteed to exist. However, relpacing
$\max$ with $\sup$ eliminates this problem. The formula in part (a) can be
generalized to $\sup \left( \bigcup_{k=1}^\infty A_k \right) = \sup_k \sup A_k$.

To see that this formula is correct, let $S = \sup_k \sup A_k$. Observe that
$S > \sup A_n$ for all $n \in \mathbb{N}$, which implies that $S$ is an upper
bound for all $A_k$. Therefore, $S$ is an upper bound for
$\bigcup_{k=1}^\infty A_k$, so we can conclude that
$S \ge \sup \left( \bigcup_{k=1}^\infty A_k \right)$. To prove the reverse
inequality, note that $\sup \left( \bigcup_{k=1}^\infty A_k \right)$ implies
that $\sup \left( \bigcup_{k=1}^\infty A_k \right) \ge \sup A_k$ for all
$k \in \mathbb{N}$. Otherwise, there would be some $A_k$ that contains elements
strictly greater than $\sup \left( \bigcup_{k=1}^\infty A_k \right)$. Therefore,
$\sup \left( \bigcup_{k=1}^\infty A_k \right) \ge \sup_k \sup A_k = S$. The
desired result follows by combining the two inequalities relating $S$ and
$\sup \left( \bigcup_{k=1}^\infty A_k \right)$.

-------------------------------------------------------------------------------
### 1.3.5.

As in Example 1.3.7, let $A \subseteq \mathbb{R}$ be nonempty and bounded above,
and let $c \in \mathbb{R}$. This time define the set $cA = \{ ca : a \in A \}$.

#### 1.3.5.a.

__Problem__. If $c \ge 0$, show that $\sup(cA) = c \sup A$.

__Solution__. TODO

#### 1.3.5.b.

__Problem__. Postulate a similar type of statement for $\sup(cA)$ for the case
$c < 0$.

__Solution__. TODO

-------------------------------------------------------------------------------
### 1.3.6.

Given sets $A$ and $B$, define
$A + B = \{ a + b : a \in A \textrm{ and } b \in B \}$. Follow these steps to
prove that if $A$ and $B$ are nonempty and bounded above then
$\sup(A + B) = \sup A + \sup B$.

#### 1.3.6.a.

__Problem__. Let $s = \sup A$ and $t = \sup B$. Show $s + t$ is an upper bound
for $A + B$.

__Solution__. TODO

#### 1.3.6.b.

__Problem__. Now let $u$ be an arbitrary upper bound for $A + B4$, and
temporarily fix $a \in A$. Show $t \le u - a$.

__Solution__. TODO

#### 1.3.6.c.

__Problem__. Finally, show $\sup(A + B) = s + t$.

__Solution__. TODO

#### 1.3.6.d.

__Problem__. Construct another proof of this same fact using Lemma 1.3.8.

__Solution__. TODO

-------------------------------------------------------------------------------
### 1.3.7.

__Problem__. Prove that if $a$ is an upper bound for $A$, and if $a$ is also
an element of $A$, then it must be that $a = \sup A$.

__Solution__. TODO

-------------------------------------------------------------------------------
### 1.3.8.

Compute, without proofs, the suprema and infima (if they exist) of the
following sets.

#### 1.3.8.a.

__Problem__. $\{ m/n : m, n \in \mathbb{N} with m < n \}$

__Solution__. TODO

#### 1.3.8.b.

__Problem__. $\{ (-1)^m / n : m, n \in \mathbb{N} \}$

__Solution__. TODO

#### 1.3.8.c.

__Problem__. $\{ n / (3n + 1) : n \in \mathbb{N} \}$

__Solution__. TODO

#### 1.3.8.d.

__Problem__. $\{ m / (m + n) : m, n \in \mathbb{N} \}$

__Solution__. TODO

-------------------------------------------------------------------------------
### 1.3.9.

#### 1.3.9.a.

__Problem__. If $\sup A < \sup B$, show that there exists an element $b \in B$
that is an upper bound for $A$.

__Solution__. TODO

#### 1.3.9.b.

__Problem__. Give an example to show that this is not always the case if we
only assume $\sup B \le \sup B$.

__Solution__. TODO

-------------------------------------------------------------------------------
### 1.3.10.

The _Cut Property_ of the real numbers is the following:

If $A$ and $B$ are nonempty, disjoing sets with $A \cup B = \mathbb{R}$ and
$a < b$ for all $a \in A$ and $b \in B$, then there exisgts $c \in \mathbb{R}$
such that $x \le c$ whenever $x \in A$ and $x \ge c$ whenever $x \in B$.

#### 1.3.10.a.

__Problem__. Use the Axiom of Completeness to prove the Cut Property.

__Solution__. TODO

#### 1.3.10.b.

__Problem__. Show that the implication goes the other way; that is, assume
$\mathbb{R}$ possesses the Cut Property and let $E$ be a nonempty set that is
bounded above. Prove that $\sup E$ exists.
only assume $\sup B \le \sup B$.

__Solution__. TODO

#### 1.3.10.c.

__Problem__. The punchline of parts (a) and (B) is that the Cut Property could
be used in place of the Axiom of Completeness as the fundamental axiom that
distinguishes the real numbers from the rational numbers. To drive this point
home, give a concrete example showing that the Cut Property is not a valid
statement when $\mathbb{R}$ is replaced by $\mathbb{Q}$.

__Solution__. TODO

-------------------------------------------------------------------------------
### 1.3.11.

Decide if the following statements about suprema and infima are true or false.
Give a short proof for those that are true. For any that are false, supply an
example where the claim in question does not appear to hold.

#### 1.3.11.a.

__Problem__. If $A$ and $B$ are nonempty, bounded, and satisfy $A \subseteq B$,
then $\sup A \le \sup B$.

__Solution__. TODO

#### 1.3.11.b.

__Problem__. If $\sup A < \inf B$ for sets $A$ and $B$, then there exists a
$c \in \mathbb{R}$ satisfying $a < c < b$ for all $a \in A$ and $b \in B$.

__Solution__. TODO

#### 1.3.11.c.

__Problem__. If there exists a $c \in \mathbb{R}$ satistfying $a < c < b$ for
all $a \in A$ and $b \in B$, then $\sup A < \inf B$.

__Solution__. TODO

-------------------------------------------------------------------------------
