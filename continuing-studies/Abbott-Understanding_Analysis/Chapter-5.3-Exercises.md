Understanding Analysis (S. Abbott): Section 5.3 Exercises
=========================================================

--------------------------------------------------------------------------------------------
### Notation

* $\newcommand{\Q}{\mathbb{Q}}$
  The set of rational numbers: $\Q$

* $\newcommand{\R}{\mathbb{R}}$
  The set of real numbers: $\R$

--------------------------------------------------------------------------------------------
### 5.3.1.

__Problem__. Recall from Exercise 4.4.9 that a function $f: A \rightarrow \R$ is Lipschitz
on $A$ if there exists an $M > 0$ such that

$$
\left|
  \frac{f(x) - f(y)}{x - y}
\right|
\le M
$$

for all $x \ne y$ in $A$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 5.3.2.

__Problem__. Let $f$ be differentiable on an interval $A$. If $f'(x) \ne 0$ on $A$, show
that $f$ is one-to-one on $A$. Provide an example to show that the converse statement need
not be true.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 5.3.3.

Let $h$ be a differentiable function defined on the interval $[0, 3]$, and assume that
$h(0) = 1$, $h(1) = 2$, and $h(3) = 2$.

#### 5.3.3.a.

__Problem__. Argue that there exists a point $d \in [0, 3]$ where $h(d) = d$.

__Solution__. TODO

#### 5.3.3.b.

__Problem__. Argue that at some point $c$ we have $h'(c) = 1/3$.

__Solution__. TODO

#### 5.3.3.c.

__Problem__. Argue that $h'(x) = 1/4$ at some point in the domain.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 5.3.4.

Let $f$ be differentiable on an intervale $A$ containing zero, and assume $(x_n)$ is a
sequence in $A$ with $(x_n) \rightarrow 0$ and $x_n \ne 0$.

#### 5.3.4.a.

__Problem__. If $f(x_n) = 0$ for all $n \in N$, show $f(0) = 0$ and $f'(0) = 0$.

__Solution__. TODO

#### 5.3.4.b.

__Problem__. Add the assumption that $f$ is twice-differentiable at zero and show that
$f''(0) = 0$ as well.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 5.3.5.

#### 5.3.5.a.

__Problem__. Supply the details for the proof of Cauchy's Generalized Mean Value Theorem
(Theorem 5.3.5).

_Theorem_: TODO

__Solution__. TODO

#### 5.3.5.b.

__Problem__. Give a graphical interpretation of the Generalized Mean Value Theorem
analogous to the one given for the Mean Value Theorem at the beginning of Section 5.3.
(Consider $f$ and $g$ as parametric equations for a curve.)

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 5.3.6.

#### 5.3.6.a.

__Problem__. Let $g: [0, a] \rightarrow \R$ be differentiable, $g(0) = 0$, and
$|g'(x)| \le M$ for all $x \in [0, a]$. Show $|g(x)| \le Mx$ for all $x \in [0, a]$.

__Solution__. The Mean Value Theorem implies that there exists $y \in (0, x)$ such that

$$
g'(y) = \frac{g(x) - g(0)}{x - 0} = \frac{g(x)}{x}.
$$

Therefore, $|g(x)| = |g'(y)| x \le M x$.

#### 5.3.6.b.

__Problem__. Let $h: [0, a] \rightarrow \R$ be twice differentiable, $h'(0) = h(0) = 0$ and
$|h''(x)| \le M$ for all $x \in [0, a]$. Show $|h(x)| \le M x^2 / 2$ for all $x \in [0, a]$.

__Solution__. Applying part (a) to $h'(x)$, we know that $|h'(x)| \le Mx$ for all
$x \in [0, a]$. Let $x \in [0, a]$ and divide $[0, x]$ into $N$ intervals $[x_{i-1}, x_i]$
of equal size $\gamma = x/N$. On the $i$-th interval, the Mean Value Theorem implies that
there exists $z_i \in (x_{i-1}, x_i)$ such that

$$
h'(z_i) = \frac{h(x_i) - h(x_{i-1})}{\gamma}
$$

Rearranging this equation and taking absolute values, we find that

$$
\begin{align}
|h(x_i)|
&= | h(x_{i-1}) + \gamma h'(z_i) | \\
&\le |h(x_{i-1})| + \gamma |h'(z_i)| \\
&\le |h(x_{i-1})| + M \gamma z_i \\
&\le |h(x_{i-1})| + M \gamma x_i
\end{align}
$$

where the second line follows from the triangle inequality, the third line follows
from the bound $|h'(x)| < M x$, and the last line follows because $z_i < x_i$. Combining
these inequalities yields

$$
\begin{align}
|h(x)|
&= |h(x_N)| \\
&\le |h(x_{N-1})| + M \gamma x_N \\
&\le |h(x_{N-2})| + M \gamma (x_{N-1} + x_N) \\
&\ \ \vdots \\
&\le |h(x_0)| + M \gamma \sum_{i=1}^N x_i \\
\end{align}
$$

Recalling that $x_0 = 0$, $h(0) = 0$, and $x_i = i\gamma$, we obtain

$$
|h(x)|
\le M \gamma^2 \sum_{i=1}^N i
= M \gamma^2 \left( \frac{N(N+1)}{2} \right)
= \frac{M x^2}{2} ( 1 + 1/N )
$$

where the last equality follows by substituting $\gamma = x/N$. Taking the limit as
$N \rightarrow \infty$, we conclude that $|h(x)| \le M x^2 / 2$ (by the Order Limit
Theorem). Since $x$ is arbitrary in $[0, a]$, $|h(x)| \le M x^2 / 2$ for all $x \in [0, a]$.

#### 5.3.6.c.

__Problem__. Conjecture and prove an analogous result for a function that is differentiable
three times on $[0, a]$.

__Solution__.

_Conjecture_. Let $h: [0, a] \rightarrow \R$ be three times differentiable,
$h''(0) = h'(0) = h(0) = 0$ and $|h'''(x)| \le M$ for all $x \in [0, a]$. Then
$|h(x)| \le M x^3 / 6$ for all $x \in [0, a]$.

_Proof_. Following the same reasoning as in part (b) yields the following bound on $|h(x)|$
when the interval $[0, x]$ is divided into $N$ equal-size parts:

$$
\begin{align}
|h(x)|
&\le \gamma \sum_{i=1}^N |h'''(z_i)| \\
&\le \gamma \sum_{i=1}^N \frac{1}{2} M z_i^2 \\
&\le \gamma \sum_{i=1}^N \frac{1}{2} M x_i^2 \\
&= \frac{1}{2} M \gamma \sum_{i=1}^N x_i^2
\end{align}
$$

where $z_i \in (x_{i-1}, x_i)$. Recalling that $x_i = i \gamma$, we obtain

$$
\begin{align}
|h(x)|
&\le \frac{1}{2} M \gamma^3 \sum_{i=1}^N i^2 \\
&= \frac{1}{2} M \gamma^3 \left( \frac{(2N+1)(N+1)N}{6} \right) \\
&= \frac{1}{6} M x^3 (1 + 1/2N) (1 + 1/N)
\end{align}
$$

Taking the limit as $N \rightarrow \infty$ yields the desired result
$|h(x)| \le M x^3 / 6$ for all $x \in [0, a]$.

--------------------------------------------------------------------------------------------
### 5.3.7.

__Problem__. A _fixed point_ of a function $f$ is a value $x$ where $f(x) = x$. Show that
if $f$ is differentiable on an interval with $f'(x) \ne 1$, then $f$ can have at most one
fixed point.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 5.3.8.

__Problem__. Assume $f$ is continuous on an interval containing zero and differentiable for
all $x \ne 0$. If $\lim_{x \rightarrow 0} f'(x) = L$, show $f'(0)$ exists and equals $L$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 5.3.9.

__Problem__. Assume $f$ and $g$ are as described in Theorem 5.3.6, but now add the
assumption that $f$ and $g$ are differentiable at $a$, and $f'$ and $g'$ are continuous
at $a$ with $g'(a) \ne 0$. Find a short proof for the $0/0$ case of L'Hospital's Rule
under this stronger hypothesis.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 5.3.10.

__Problem__. Let $f(x) = x \sin(1/x^4) e^{-1/x^2}$ and $g(x) = e^{1/x^2}$. Using the
familiar properties of these functions, compute the limit as $x$ approaches zero of
$f(x)$, $g(x)$, $f(x) / g(x)$, and $f'(x) / g'(x)$. Explain why the results are surprising
but not in conflict with the content of Theorem t.3.6.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 5.3.11.

#### 5.3.11.a.

__Problem__. Use the Generalized Mean Value Theorem to furnish a proof of the $0/0$ case
of L'Hospital's Rule (Theorem 5.3.6).

__Solution__. TODO

#### 5.3.11.b.

__Problem__. If we keep the first part of the hypothesis of Theorem 5.3.6 the same but we
assume that

$$
\lim_{x \rightarrow a} \frac{f'(x)}{g'(x)} = \infty,
$$

does it necessarily follow that

$$
\lim_{x \rightarrow a} \frac{f(x)}{g(x)} = \infty?
$$

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 5.3.12.

__Problem__. If $f$ is twice differentiable on an open interval containing $a$ and $f''$ is
continuous at $a$, show

$$
\lim_{h \rightarrow 0} \frac{f(a + h) - 2 f(x) + f(a - h)}{h^2} = f''(a).
$$

__Solution__. TODO

--------------------------------------------------------------------------------------------
