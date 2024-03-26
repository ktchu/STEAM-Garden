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
