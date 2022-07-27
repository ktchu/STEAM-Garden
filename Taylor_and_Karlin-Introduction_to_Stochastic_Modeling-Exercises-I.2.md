An Introduction to Stochastic Modeling (Taylor and Karlin): Exercises 1.2
=========================================================================

--------------------------------------------------------------------------------------------
## 0. Notation

* $\newcommand{\Pr}[1]{{\mathbb{P}\left[{#1}\right]}}$
  Probability of event $E$: $\Pr{E}$

* $\newcommand{\1}[1]{{\mathbf{1}_{\left\{{#1}\right\}}}}$
  Indicator for event $E$: $\1{E}$

* $\newcommand{\p}[1]{{p\left({#1}\right)}}$
  Probability density (or mass) function for a random variable $X$: $\p{x}$

* $\newcommand{\E}[1]{{\mathbb{E}\left[{#1}\right]}}$
  Expected value of $X$: $\E{X}$

* $\newcommand{\Var}[1]{{\operatorname{Var}}{\left(#1\right)}}$
  Variance of $X$: $\Var{X}$

--------------------------------------------------------------------------------------------
### 2.1.

__Problem__. Let $A$ and $B$ be arbitrary, not necessarily disjoint, events. Use the law of
total probability to verify the formula

$$
\Pr{A} = \Pr{AB} + \Pr{AB^c},
$$

where $B^c$ is the complementary event to $B$. (That is, $B^c$ occurs if and only if $B$
does not occur).

__Solution__.  $B$ and $B^c$ are disjoint, so the formula is a direct application of the
law of total probability.

--------------------------------------------------------------------------------------------
### 2.2.

__Problem__. Let $A$ and $B$ be arbitrary, not necessarily disjoint, events. Establish
the general addition law

$$
\Pr{A \cup B} = \Pr{A} + \Pr{B} - \Pr{AB}.
$$

__Solution__.  By the law of total probability,

$$
\Pr{A \cup B}
= \Pr{(A \cup B) \cap A} + \Pr{(A \cup B) \cap A^c}
= \Pr{A} + \Pr{B \cap A^c}
$$

where the last equality follows because $(A \cup B) \cap A = A$ and
$(A \cup B) \cap A^c = (A \cap A^c) \cup (B \cap A^c) = B \cap A^c$. Applying the law of
total probability to $B$,

$$
\Pr{B} = \Pr{B \cap A} + \Pr{(B \cap A^c}.
$$

Combining these two results yields the desired result.

--------------------------------------------------------------------------------------------
### 2.3.

#### 2.3.a.

__Problem__. Plot the distribution function

$$
F(x) = \left\{
\begin{array}{ll}
0   & \textrm{for $x \le 0$} \\
x^3 & \textrm{for $0 < x < 1$} \\
1   & \textrm{for $x \ge 1$}.
\end{array}
\right.
$$

__Solution__. TODO

#### 2.3.b.

__Problem__. Determine the corresponding density function $f(x)$ in the three regions
(i) $x \le 0$, (ii) $0 < x < 1$, and (iii) $1 \le x$.

__Solution__.

* In region (i), $f(x) = F'(x) = 0$.

* In region (ii), $f(x) = F'(x) = 3 x^2$.

* In region (iii), $f(x) = F'(x) = 0$.

#### 2.3.c.

__Problem__. What is the mean of the distribution?

__Solution__. The mean of the distribution is given by
$\int_0^1 x (3x^2) dx = \int_0^1 3x^3 dx = 3/4$.

#### 2.3.d.

__Problem__. If $X$ is a random variable following the distribution specified in (a),
evaluate $\Pr{1/4 \le X \le 3/4}$.

__Solution__. $\Pr{1/4 \le X \le 3/4} = F(3/4) - F(1/4) = 13/32$.

--------------------------------------------------------------------------------------------
### 2.4.

Let $Z$ be a discrete random variable having possible values 0, 1, 2, and 3 and probability
mass function $p(0) = 1/4$, $p(1) = 1/2$, $p(2) = 1/8$, and $p(3) = 1/8$.

#### 2.4.a.

__Problem__. Plot the corresponding distribution function.

__Solution__. TODO

#### 2.4.b.

__Problem__. Determine the mean $\E{Z}$.

__Solution__. TODO

#### 2.4.c.

__Problem__. Determine the variance $\Var{Z}$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 2.5.

__Problem__. Let $A$, $B$, and $C$ be arbitrary events. Establish the addition law

$$
\Pr{A \cup B \cup C}
= \Pr{A} + \Pr{B} + \Pr{C} - \Pr{AB} - \Pr{AC} - \Pr{BC} + \Pr{ABC}.
$$

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 2.6.

Let $X$ and $Y$ be independent random variables having distribution functions $F_X$ and
$F_Y$, respectively.

#### 2.6.a.

__Problem__. Define $Z = \max(X, Y)$ to be the larger of the two. Show that
$F_Z(z) = F_X(z) F_Y(z)$ for all $z$.

__Solution__. TODO

#### 2.6.b.

__Problem__. Define $W = \min(X, Y)$ to be the smaller of the two. Show that
$F_W(w) = 1 - (1 - F_X(w)) (1 - F_Y(w))$ for all $w$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 2.7.

Suppose that $X$ is a random variable having the probability density function

$$
f(x) = \left\{
\begin{array}{ll}
R x^{R-1} & \textrm{for $0 < x < 1$} \\
0         & \textrm{elsewhere},
\end{array}
\right.
$$

where $R > 0$ is a fixed parameter.

#### 2.7.a.

__Problem__. Determine the distribution function $F_X(x)$.

__Solution__. TODO

#### 2.7.b.

__Problem__. Determine the mean $\E{X}$.

__Solution__. TODO

#### 2.7.c.

__Problem__. Determine the variance $\Var{X}$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 2.8.

__Problem__. A random variable $V$ has the distibution function

$$
F(v) = \left\{
\begin{array}{ll}
0             & \textrm{for $v < 0$} \\
1 - (1 - v)^A & \textrm{for $0 < v < 1$} \\
1             & \textrm{for $v > 1$}, \\
\end{array}
\right.
$$

where $A > 0$ is a parameter. Determine the density function, mean, and variance.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 2.9.

__Problem__. Determine the distribution function, mean, and variance corresponding to the
triangular density.

$$
f(x) = \left\{
\begin{array}{ll}
x   & \textrm{for $0 \le x \le 1$} \\
2-x & \textrm{for $1 \le x \le 2$} \\
0   & \textrm{elsewhere.}
\end{array}
\right.
$$

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 2.10.

Let $\1{A}$ be the indicator random variable associated with an event $A$, defined to be
one if $A$ occurs, and zero otherwise. Define $A^c$, the complement of event $A$, to be
the event that occurs when $A$ does not occur.

#### 2.10.a.

__Problem__. Show that $\1{A^c} = 1 - \1{A}$.

__Solution__. TODO

#### 2.10.b.

__Problem__. Show that $\1{A \cap B} = \1{A} \1{B} = \min(\1{A}, \1{B})$.

__Solution__. TODO

#### 2.10.c.

__Problem__. Show that $\1{A \cup B} = \max(\1{A} \1{B})$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
