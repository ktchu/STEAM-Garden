Understanding Analysis (S. Abbott): Section 2.2 Exercises
=========================================================

--------------------------------------------------------------------------------------------
### Notation

* $\newcommand{\N}{\mathbb{N}}$
  The set of natural numbers: $\N$

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

__Solution__. TODO

--------------------------------------------------------------------------------------------
