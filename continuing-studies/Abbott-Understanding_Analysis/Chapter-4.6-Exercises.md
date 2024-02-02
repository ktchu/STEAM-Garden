Understanding Analysis (S. Abbott): Section 4.6 Exercises
=========================================================

--------------------------------------------------------------------------------------------
### Notation

* $\newcommand{\N}{\mathbb{N}}$
  The set of natural numbers: $\N$

* $\newcommand{\R}{\mathbb{R}}$
  The set of real numbers: $\R$

--------------------------------------------------------------------------------------------
### 4.6.1.

__Problem__. Recall the following functions and their sets of discontinuities.

* Dirichlet's function

  $$
  g(x) = \left\{\begin{array}{cl}
           1 & \textrm{if $x \in \Q$} \\
           0 & \textrm{if $x \notin \Q$} \\
         \end{array}\right.
  $$

  $D_g = \R$

* Modified Dirichlet's function

  $$
  h(x) = \left\{\begin{array}{cl}
           x & \textrm{if $x \in \Q$} \\
           0 & \textrm{if $x \notin \Q$} \\
         \end{array}\right.
  $$

  $D_h = \R \backslash \{ 0 \}$

* Thomae's function

  $$
  t(x) = \left\{\begin{array}{cl}
           1   & \textrm{if $x = 0$} \\
           1/n & \textrm{if $x = m/n \in \Q \backslash \{0\}$ is in lowest terms with
                         $n > 0$} \\
           0   & \textrm{if $x \notin \Q$} \\
         \end{array}\right.
  $$

  $D_t = \Q$

Using modifications of the these functions, construct a function $f: \R \rightarrow \R$ so
that

a) $D_f = \Z^c$

b) $D_f = \{x : 0 < x \le 1 \}$


__Solution__.

a)
   $$
   f(x) = \left\{\begin{array}{ll}
           x - \lfloor x \rfloor
             & \textrm{if $x \in \Q$ and $x - \lfloor x \rfloor < 1/2$} \\
           x - \lfloor x \rfloor - 1
             & \textrm{if $x \in \Q$ and $x - \lfloor x \rfloor \ge 1/2$} \\
           0
             & \textrm{if $x \notin \Q$} \\
         \end{array}\right.
   $$

   TODO: add discussion about why

b)
   $$
   f(x) = \left\{\begin{array}{ll}
           0 & \textrm{if $x < 0$} \\
           x & \textrm{if $x \in \Q \cap [0, 1]$} \\
           0 & \textrm{if $x \in \I \cap [0, 1]$} \\
           1 & \textrm{if $x > 1$} \\
         \end{array}\right.
   $$

   TODO: add discussion about why

--------------------------------------------------------------------------------------------
### 4.6.2.

__Problem__. Given a countable set $A = \{a_1, a_2, a_3, \ldots \}$, define $f(a_n) = 1/n$
and $f(x) = 0$ for all $x \notin A$. Find $D_f$.

__Solution__. $D_f = A$. $f$ is continuous at all points $x \notin A$ because $x \notin A$
implies that $x$ must lie between two points in the set $A$. In other words, $x$ is an
element of an interval that contains no points in $A$. $f(y) = 0$ for any point $y$ in that
interval, so $f$ is continous at $x$ when $x \notin A$. For $x = a_n \in A$, construct a
sequence $(x_k)$ with $x_k \ne a_n$ for all $k$ such that $(x_k) \rightarrow a_n$ as
$k \rightarrow \infty$ (we can construct such a sequence by selecting $x_k$ from an open
interval around $a_n$ that does not contain any of the other elements of $A$). Then

$$
\lim_{k \rightarrow \infty} f(x_k) = 0 \ne 1/n = f(a_n),
$$

so $f$ is discontinuous at $a_n$.

--------------------------------------------------------------------------------------------
