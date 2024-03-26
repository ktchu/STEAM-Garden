Understanding Analysis (S. Abbott): Section 5.2 Exercises
=========================================================

--------------------------------------------------------------------------------------------
### Notation

* $\newcommand{\Q}{\mathbb{Q}}$
  The set of rational numbers: $\Q$

* $\newcommand{\R}{\mathbb{R}}$
  The set of real numbers: $\R$

--------------------------------------------------------------------------------------------
### 5.2.1.

__Problem__. Supply proofs for parts (i) and (ii) of Theorem 5.2.4

_Theorem 5.2.4 (Algebraic Differentiability Theorem)_. Let $f$ and $g$ be function defined
on an interval $A$, and assume both are differentiable at some point $c \in A$. Then

(i) $(f + g)'(c) = f'(c) + g'(c)$

(ii) $(kf)'(c) = kf'(c)$, for all $k \in \R$

__Solution__.

(i) Observe that the difference quotient can be rewritten as

$$
\frac{(f+g)(x) - (f+g)(c)}{x - c}
= \frac{f(x) - f(c) + g(x) - g(c)}{x - c}
= \frac{f(x) - f(c)}{x-c} + \frac{g(x) - g(c)}{x - c}.
$$

Therefore, by the functional-version of the Algebraic Limit Theorem,

$$
\lim_{x \rightarrow c} \frac{(f+g)(x) - (f+g)(c)}{x - c}
=   \lim_{x \rightarrow c} \frac{f(x) - f(c)}{x-c}
  + \lim_{x \rightarrow c} \frac{g(x) - g(c)}{x - c}
= f'(c) + g'(c)
$$

where the last equality follows because $f$ and $g$ are both differentiable.

(ii) Observe that the difference quotient can be rewritten as

$$
\frac{(kf)(x) - (kf)(c)}{x - c}
= \frac{k(f(x) - f(c)}{x - c}
$$

for all $k \in \R$. Therefore, by the functional-version of the Algebraic Limit Theorem,

$$
\lim_{x \rightarrow c} \frac{(kf)(x) - (kf)(c)}{x - c}
= \lim_{x \rightarrow c} \frac{k(f(x) - f(c))}{x-c}
= kf'(c)
$$

where the last equality follows because $f$ is differentiable.

--------------------------------------------------------------------------------------------
### 5.2.2.

__Problem__. Exactly one of the following requests is impossible. Decide which it is, and
provide examples of the other three. In each case, let's assume the functions are defined
on all of $\R$.

(a) Functions $f$ and $g$ not differentiable at zero but where $fg$ is differentiable at
    zero.

(b) A function $f$ not differentiable at zero and a function $g$ differentiable at zero
    where $fg$ is differentiable at zero.

(c) A function $f$ not differentiable at zero and a function $g$ differentiable at zero
    where $f + g$ is differentiable at zero.

(d) A function $f$ differentiable at zero but not differentiable at any other point.

__Solution__.

(a) Consider $f(x) = g(x) = |x|$. $f = g$ is not differentiable at zero (because the limit
of the difference quotients from the left and right are not equal). However,
$fg = |x|^2 = x^2$ is differentiable.

(b) Consider $f(x) = |x|$ and $g(x) = 0$. Then $f$ is not differentiable, $g$ is
differentiable, and $fg = g = 0$ is differentiable.

(c) This request is impossible. If $g$ and $f + g$ are differentiable, then the Algebraic
Differentiability Theorem implies that $f = f + g + (-1)g$ must be differentiable.

(d) Consider the following variation of the Modified Dirichlet Function:

$$
f(x)
= \left\{\begin{array}{cl}
    x^2 & x \in \Q \\
    0 & x \notin \Q
  \end{array}\right.
$$

For $c \in \Q$ and $c \ne 0$, consider the two sequences $(x_n) \rightarrow c$ with
$x_n \in \Q$ and $(y_n) \rightarrow c$ with $y_n \notin \Q$. Then the sequence of
difference quotients computed from $(x_n)$ converges to $2c$

$$
\lim_{n \rightarrow \infty} \frac{f(x_n) - f(c)}{x_n - c}
= \lim_{n \rightarrow \infty} \frac{x_n^2 - c^2}{x_n - c}
= \lim_{n \rightarrow \infty} x_n + c
= 2c
$$

but the sequence of difference quotients computed from $(y_n)$ diverges

$$
\lim_{n \rightarrow \infty} \frac{f(y_n) - f(c)}{y_n - c}
= \lim_{n \rightarrow \infty} \frac{0 - c^2}{y_n -c}
= -\infty,
$$

which implies that $f$ is not differentiable for $x \in \Q$ when $x \ne 0$.

For $c \notin \Q$, the sequence of difference quotients computed from $(x_n)$ diverges

$$
\lim_{n \rightarrow \infty} \frac{f(x_n) - f(c)}{x_n - c}
= \lim_{n \rightarrow \infty} \frac{x_n^2 - 0}{x_n - c}
= \infty
$$

but the sequence of difference quotients computed from $(y_n)$ converges to 0

$$
\lim_{n \rightarrow \infty} \frac{f(y_n) - f(c)}{y_n - c}
= \lim_{n \rightarrow \infty} \frac{0 - 0}{y_n -c}
= \lim_{n \rightarrow \infty} 0
= 0,
$$

which implies that $f$ is not differentiable for $x \notin \Q$.

Finally, if $c = 0$, then the difference quotient satisfies the bound

$$
\left| \frac{f(x) - f(c)}{x - c} \right|
= \left| \frac{f(x)}{x} \right|
\le |x|.
$$

Therefore, the limit of the difference quotient as $x$ approaches $0$ exists and is equal
to $0$.

--------------------------------------------------------------------------------------------
### 5.2.3.

#### 5.2.3.a.

__Problem__. Use Definition 5.2.1 to produce the proper formula for the derivative of
$h(x) = 1/x$.

__Solution__. Observe that the difference quotient for $h$ at $c$ is

$$
\frac{h(x) - h(c)}{x - c}
= \frac{1/x - 1/c}{x - c}
= \frac{c - x}{xc(x - c)}
= \frac{-1}{xc}
$$

Taking the limit as $x$ approaches $c$, the Algebraic Limit Theorem implies that
$h'(c) = -1/c^2$.

#### 5.2.3.b.

__Problem__. Conbine the result in part (a) with the Chain Rule (Theorem 5.2.5) to supply
a proof for part (iv) of Theorem 5.2.4.

_Theorem 5.2.4 (Algebraic Differentiability Theorem)_. Let $f$ and $g$ be function defined
on an interval $A$, and assume both are differentiable at some point $c \in A$. Then

(iv) $(f/g)'(c) = \frac{g(c) f'(c) - f(c) g'(c)}{[g(c)]^2}$ provided that $g(c) \ne 0$.

__Solution__. Let $k(x) = h(g(x))$. From part (iii) of the Algebraic Differentiability
Theorem,
$(fk)'(c) = f'(c) k(c) + f(c) k'(c)$. The Chain Rule implies that

$$
k'(c)
= h'(g(c)) g'(c)
= \left( \frac{-1}{[g(c)]^2} \right) g'(c).
$$

Substituting the expressions for $k$ and $k'$,

$$
\begin{align}
(f/g)'(c)
&= \frac{f'(c)}{g(c)} + f(c) \left( \frac{-1}{[g(c)]^2} \right) g'(c) \\
&= \frac{f'(c)}{g(c)} - \frac{f(c) g'(c)}{[g(c)]^2} \\
&= \frac{g(c) f'(c) - f(c) g'(c)}{[g(c)]^2}
\end{align}
$$

#### 5.2.3.c.

__Problem__. Supply a direct proof of Theorem 5.2.5 (iv) by algebraically manipulating the
difference quotient for $(f/g)$ in a style similar to the proof of Theorem 5.2.5 (iii).

__Solution__. Assuming that $g(c) \ne 0$, observe that the difference quotient of $(f/g)$
at $c$ is

$$
\begin{align}
\frac{(f/g)(x) - (f/g)(c)}{x-c}
&= \frac{f(x) / g (x) - f(c) / g(c)}{x-c} \\
&= \frac{1}{g(x) g(c)}
   \left(\frac{f(x) g (c) - f(c) g(x)}{x-c} \right) \\
&= \frac{1}{g(x) g(c)}
   \left(\frac{f(x) g (c) - f(c) g(c) + f(c) g(c) - f(c) g(x)}{x-c} \right) \\
&= \frac{1}{g(x) g(c)}
   \left(\frac{f(x) g (c) - f(c) g(c)}{x-c} + \frac{f(c) g(c) - f(c) g(x)}{x-c} \right) \\
&= \frac{1}{g(x) g(c)}
   \left(g(c) \frac{f(x) - f(c)}{x-c} - f(c) \frac{g(x) - g(c)}{x-c} \right).
\end{align}
$$

Taking the limit as $x$ approaches $c$, the Algebraic Limit Theorem and the
differentiability of $f$ and $g$ at $c$ imply that

$$
(f/g)'(c) = \frac{g(c) f'(c) - f(c) g'(c)}{[g(c)^2]}
$$

where we have used the fact that differentiability of $g$ at $c$ implies that $g$ is
continuous at $c$.

--------------------------------------------------------------------------------------------
### 5.2.4.

Follow these steps to provide a slightly modified proof of the Chain Rule.

#### 5.2.4.a.

__Problem__. Show that a function $h: A \rightarrow \R$ is differentiable at $a \in A$ if
and only if there exists a function $l: A \rightarrow \R$ which is continuous at $a$ and
satisfies

$$
h(x) - h(a) = l(x)(x-a)
$$

for all $x \in A$.

__Solution__. TODO

#### 5.2.4.b.

__Problem__. Use this criterion for differentiability (in both directions) to prove
Theorem 5.2.5.

_Theorem 5.2.5 (Chain Rule)_. Let $f: A \rightarrow \R$ and $g: B \rightarrow \R$ satisfy
$f(A) \subseteq B$ so that the composition $g \circ f$ is defined. If $f$ is differentiable
at $c \in A$ and if $g$ is differentiable at $f(c) \in B$, then $g \circ f$ is
differentiable at $c$ with $(g \circ f)'(c) = g'(f(c)) \cdot f'(c)$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 5.2.5.

Let

$$
f_a(x)
= \left\{\begin{array}{cl}
    x^a & \textrm{if $x > 0$} \\
    0 & \textrm{if $x \le 0$} \\
  \end{array}\right.
$$

#### 5.2.5.a.

__Problem__. For which values of $a$ is $f$ continuous at zero?

__Solution__. TODO

#### 5.2.5.b.

__Problem__. For which values of $a$ is $f$ differentiable at zero? In this case, is the
derivative function continuous?

__Solution__. TODO

#### 5.2.5.c.

__Problem__. For which values of $a$ is $f$ twice-differentiable?

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 5.2.6.

Let $g$ be defined on an interval $A$, and let $c \in A$.

#### 5.2.6.a.

__Problem__. Explain why $g'(c)$ in Definition 5.2.1 could have been given by

$$
g'(c) = \lim_{h \rightarrow 0} \frac{g(c+h) - g(c)}{h}.
$$

__Solution__. TODO

#### 5.2.6.b.

__Problem__. Assume $A$ is open. If $g$ is differentiable at $c \in A$, show

$$
g'(c) = \lim_{h \rightarrow 0} \frac{g(c+h) - g(c-h)}{2h}.
$$

__Solution__. Observe that the difference quotient in the above limit can be rewritten as

$$
\begin{align}
\frac{g(c+h) - g(c-h)}{2h}
&= \frac{g(c+h) - g(c) + g(c) - g(c-h)}{2h} \\
&= \frac{1}{2} \left[ \frac{g(c+h) - g(c)}{h} + \frac{g(c) - g(c-h)}{h} \right] \\
&= \frac{1}{2} \left[ \frac{g(c+h) - g(c)}{h} + \frac{g(c - h) - g(c)}{-h} \right] \\
\end{align}
$$

Taking the limit as $h$ approaches $0$, the Algebraic Limit Theorem and differentiability
of $g$ at $c$ imply that

$$
\begin{align}
\lim_{h \rightarrow 0} \frac{g(c+h) - g(c-h)}{2h}
&= \frac{1}{2} \left[
      \lim_{h \rightarrow 0} \frac{g(c+h) - g(c)}{h}
    + \lim_{h \rightarrow 0} \frac{g(c - h) - g(c)}{-h}
  \right] \\
&= \frac{1}{2} \left[
      \lim_{h \rightarrow 0} \frac{g(c+h) - g(c)}{h}
    + \lim_{-h \rightarrow 0} \frac{g(c-h) - g(c)}{-h}
  \right] \\
&= \frac{1}{2} \left[
      \lim_{h \rightarrow 0} \frac{g(c+h) - g(c)}{h}
    + \lim_{k \rightarrow 0} \frac{g(c+k) - g(c)}{k}
  \right] \\
&= \frac{1}{2} (g'(c) + g'(c)) \\
&= g'(c)
\end{align}
$$

where the third to last equality follows from the definition of the derivative in part (a).

--------------------------------------------------------------------------------------------
### 5.2.7.

Let

$$
g_a(x)
= \left\{\begin{array}{cl}
    x^a \sin(1/x) & \textrm{if $x \ne 0$} \\
                0 & \textrm{if $x = 0$}.
  \end{array}\right.
$$

Find a particular (potentially noninteger) value so for $a$ so that

(a) $g_a$ is differentiable on $\R$ but such that $g_a'$ is unbounded on $[0, 1]$

(b) $g_a$ is differentiable on $\R$ with $g_a'$ continuous but not differentiable at zero.

(c) $g_a$ is differentiable on $\R$ and $g_a'$ is differentiable on $\R$, but such that
    $g_a''$ is not continuous at zero.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 5.2.8.

Review the definition of uniform continuity (Definition 4.4.4). Given a differentiable
function $f: A \rightarrow \R$, let's say that $f$ is _uniformly differentiable_ on $A$
if, given $\epsilon > 0$ there exists a $\delta > 0$ such that

$$
\left| \frac{f(x) - f(y)}{x-y} - f'(y)\right| < \epsilon
$$

whenever $0 < |x-y| < \delta$.

#### 5.2.8.a.

__Problem__. Is $f(x) = x^2$ uniformly differentiable on $\R$? How about $g(x) = x^3$?

__Solution__. TODO

#### 5.2.8.b.

__Problem__. Show that if a function is uniformly differentiable on an interval $A$, then
the derivative must be continuous on $A$.

__Solution__. TODO

#### 5.2.8.c.

__Problem__. Is there a theorem analogous to Theorem 4.4.7 for differentiation? Are
functions that are differentiable on a closed intervale $[a, b]$ necessary uniformly
differentiable?

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 5.2.9.

Decide whether each conjecture is true or false. Provide an argument for those that are
true and a counterexample for each one that is false.

#### 5.2.9.a.

__Problem__. If $f'$ exists on an interval and is not constant, then $f'$ must take on some
irrational values.

__Solution__. TODO

#### 5.2.9.b.

__Problem__. If $f'$ exists on an open interval and there is some point $c$ where
$f'(c) > 0$, then there exists a $\delta$-neighborhood $V_\delta(c)$ around $c$ in which
$f'(x) > 0$ for all $x \in V_\delta(x)$.

__Solution__. TODO

#### 5.2.9.a.

__Problem__. If $f$ is differentiable on an interval containing zero and if
$\lim_{x \rightarrow 0} f'(x) = L$, then it must be that $L = f'(0)$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 5.2.10.

__Problem__. Recall that a function $f: (a, b) \rightarrow \R$ is _increasing_ on $(a, b)$
if $f(x) \le f(y)$ whenever $x < y$ in $(a, b)$. A familiar mantra from calculus is that a
differentiable function is increasing if its derivative is positive, but this statement
requires some sharpening in order to be completely accurate.

Show that the function

$$
g(x)
= \left\{\begin{array}{ll}
    x/2 + x^2 \sin(1/x) & \textrm{if $x \ne 0$} \\
    0                   & \textrm{if $x = 0$} \\
  \end{array}\right.
$$

is differentiable on $\R$ and satisfies $g'(0) > 0$. Now, prove that $g$ is _not_
increasing over any interval containing $0$.

In the next section we will see that $f$ is indeed increasing on $(a, b)$ if and only if
$f'(x) \ge 0$ for all $x \in (a, b)$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 5.2.11.

Assume that $g$ is differentiable on $[a, b]$ and satisfies $g'(a) < 0 < g'(b)$.

#### 5.2.11.a.

__Problem__. Show that there exists a point $x \in (a, b)$ where $g(a) > g(x)$, and a point
$y \in (a, b)$ where $g(y) < g(b)$.

__Solution__. TODO

#### 5.2.11.b.

__Problem__. Now complete the proof of Darboux's Theorem started earlier.
$y \in (a, b)$ where $g(y) < g(b)$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 5.2.12. (Inverse functions)

__Problem__. If $f: [a,b] \rightarrow \R$ is one-to-one, then there exists an inverse
function $f^{-1}$ defined on the range of $f$ given by $f^{-1}(y) = x$ where $y = f(x)$.
In Exercise 4.5.8 we saw that if $f$ is continuous on $[a, b]$, then $f^{-1}$ is continuous
on its domain. Let's add the assumption that $f$ is differentiable on $[a, b]$ with
$f'(x) \ne 0$ for all $x \in [a, b]$. Show $f^{-1}$ is differentiable with

$$
(f^{-1})'(y) = \frac{1}{f'(x)}
$$

where $y = f(x)$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
