Understanding Analysis (S. Abbott): Section 2.2 Exercises
=========================================================

--------------------------------------------------------------------------------------------
### Notation

* $\newcommand{\N}{\mathbb{N}}$
  The set of natural numbers: $\N$

* $\newcommand{\R}{\mathbb{R}}$
  The set of real numbers: $\R$

--------------------------------------------------------------------------------------------
### 2.2.1.

__Problem__. What happens if we reverse the order of the quantifiers in Definition 2.2.3?

_Definition_: A sequence $(x_n)$ _verconges_ to $x$ if _there exists_ an $\epsilon > 0$
such that _for all_ $N \in \N$ it is true that $n \ge N$ implies $|x_n - x| < \epsilon$.

Give an example of a vercongent sequence. Is there an example of a vercongent sequence that
is divergent? Can a sequence verconge to two different values? What exactly is being
described by this strange definition?

__Solution__. An example of a vercongent sequence is the sequence $x_n = (-1)^n$. This
sequence verconges to $x = 0$ because for $\epsilon = 2$ , $|x_n - 0| = 1 < \epsilon$ for
all $n \in \N$. Therefore, for any $N \in \N$, $n \ge N$ implies that
$|x_n - x| < \epsilon$.

The sequence $(x_n)$ is an example of a vercongent sequence that diverges because it does
not converge to any value.

Yes. A sequence can verconge to two different values. The sequence $(x_n)$ verconges to
$x = 1$ with a choice of $\epsilon = 3$ because $|x_n - 1| \le 2 < \epsilon$ for all
$n \in N$.

Vercongence describes bounded sequences.

--------------------------------------------------------------------------------------------
### 2.2.2.

__Problem__. Verify, using the definition of convergence of a sequence, that the following
sequences converge to the proposed limit.

a.
$$
\lim \frac{2n + 1}{5n + 4} = \frac{2}{5}.
$$

b.
$$
\lim \frac{2n^2}{n^3 + 3} = 0.
$$

c.
$$
\lim \frac{\sin(n^2)}{\sqrt[3]{n}} = 0.
$$

__Solution__.

a. Let $\epsilon > 0$. Choose $N \in \N$ with $N > \frac{3}{25 \epsilon}$. Observe that

$$
\begin{align}
\left| \frac{2n + 1}{5n + 4} - \frac{2}{5} \right|
&= \left| \frac{10n +5 -(10n + 8)}{5(5n + 4)} \right| \\
&= \frac{3}{5(5n + 4)} \\
&< \frac{3}{25n}.
\end{align}
$$

Therefore, $n \ge N$ implies that

$$
\left| \frac{2n + 1}{5n + 4} - \frac{2}{5} \right|
< \frac{3}{25 n}
\le \frac{3}{25 N}
< \epsilon.
$$

b. Let $\epsilon > 0$. Choose $N \in \N$ with $N > 2 / \epsilon$. If $n \ge N$, then

$$
\left| \frac{2n^2}{n^3 + 3} - 0 \right|
= \frac{2n^2}{n^3 + 3}
< \frac{2n^2}{n^3}
= \frac{2}{n}
\le \frac{2}{N}
< \epsilon.
$$

c. Let $\epsilon > 0$. Choose $N \in \N$ with $N > 1 / \epsilon^3$. If $n \ge N$, then

$$
\left| \frac{\sin(n^2)}{\sqrt[3]{n}} - 0 \right|
\le \left| \frac{1}{\sqrt[3]{n}} \right|
= \frac{1}{\sqrt[3]{n}}
\le \frac{1}{\sqrt[3]{N}}
< \epsilon.
$$

--------------------------------------------------------------------------------------------
### 2.2.3.

__Problem__. Describe what we would have to demonstrate in order to disprove each of the
following statements.

a. At every college in the United States, there is a student who is at least seven feet
   tall.

b. For all colleges in the United States, there exists a professor who gives every student
   a grade of either A or B.

c. There exists a college in the United States where every student is at least six feet
   tall.

__Solution__.

a. Show that there is at least one college where all students are less than seven feet tall.

b. Show that there is at least one college where all professors give at least one student
   a grade below B.

c. Show that all colleges at least one student is less than six feet tall.

--------------------------------------------------------------------------------------------
### 2.2.4.

__Problem__. Give an example of each or state that the request is impossible. For any that
are impossible, give a compelling argument for why that is the case.

a. A sequence with an infinite number of ones that does not converge to one.

b. A sequence with an infinite number of ones that converges to a limit not equal to one.

c. A divergent sequence such that for every $n \in N$ it is possible to find $n$
   consecutive ones somewhere in the sequence.

__Solution__.

a. $x_n = (-1)^n$ satisfies the request.

b. Impossible. TODO

c. Let

   $$
   S_n = n + \sum_{k=1}^n k.
   $$

   Then the sequence defined by

   $$
   x_m
   = \left\{\begin{array}{ll}
        0 & \textrm{if $m = S_n$ for some $n$} \\
        1 & \textrm{otherwise}
     \end{array}\right.
   $$

   satisfies the desired request. By construction, $n$ consecutive ones preceed each
   the zero that appears at $x_{S_n}$, and the sequence diverges because there are an
   infinite number of zeros and ones after any term in the sequence.

--------------------------------------------------------------------------------------------
### 2.2.5.

__Problem__. Let $\lfloor x \rfloor$ be the greatest integer less than or equal to $x$. For
example $\lfloor \pi \rfloor = 3$ and $\lfloor 3 \rfloor = 3$. For each sequence, find
$\lim a_n$ and verify it with the definition of convergence.

a. $a_n = \lfloor 5 / n \rfloor$

b. $a_n = \lfloor (12 + 4n) / 3n \rfloor$

c. Reflecting on these examples, comment on the statement following Definition 2.2.3. that
   "the smaller the $\epsilon$-neighborhood, the larger $N$ may have to be."

__Solution__.

a. TODO

b. TODO

c. TODO

--------------------------------------------------------------------------------------------
### 2.2.6.

__Problem__. Prove Theorem 2.2.7.

 TODO: insert theorem

To get started, assume $(a_n) \rightarrow a$ and also that $(a_n) \rightarrow b$. Now
argue that $a = b$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 2.2.7.

Here are two useful definitions:

(i) A sequence $(a_n)$ is _eventually_ in a set $A \subseteq \R$ if there exists an
    $N \in \N$ such that $a_n \in A$ for all $n \ge N$.

(ii) A sequence $(a_n)$ is _frequently_ in a set $A \subseteq \R$ if, for every $N \in \N$,
     there exists an $n \ge \N$ such that $a_n \in A$.

__Problem__.

a. Is the sequence $(-1)^n$ eventually or frequently in the set $\{ 1 \}$?

b. Which definition is stronger? Does frequently imply eventually or does eventually imply
   frequently?

c. Give an alternate rephrasing of Definition 2.2.3B using either frequently or eventually.
   Which is the term we want?

d. Suppose an infinite number of terms of a sequence $(x_n)$ are equal to $2$. Is $(x_n)$
   necessarily eventually in the interval $(1.9, 2.1)$? Is it frequently in $(1.9, 2.1)$?

__Solution__.

a. TODO

b. TODO

c. TODO

d. TODO

--------------------------------------------------------------------------------------------
### 2.2.8.

For some additional practice with nested qualifiers, consider the following invented
definition:

  Let's call a sequence $(x_n)$ _zero-heavy_ if there exists $M \in \N$ such that for all
  $N \in \N$ there exists $n$ satisfying $N \le n \le N + M$ where $x_n = 0$.

__Problem__.

a. Is the sequence $(0, 1, 0, 1, 0, 1, \ldots)$ zero heavy?

b. If a sequence zero-heavy does it necessarily contain an infinite number of zeros? If
   not, provide a counterexample.

c. If a sequence contains an infinite number of zeros, is it necessarily zero-heavy? If
   not, provide a counterexample.

d. Form the logical negation of the above definition. That is, complete the sentence:
   A sequence is _not_ zero-heavy if $\ldots$

--------------------------------------------------------------------------------------------
