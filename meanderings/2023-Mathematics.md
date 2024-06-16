Mathematics (2023)
==================

*Author(s)*: Kevin Chu `<kevin@velexi.com>`

--------------------------------------------------------------------------------------------

## Notation

* $\newcommand{\N}{\mathbb{N}}$
  The set of natural numbers: $\N$

* $\newcommand{\Z}{\mathbb{Z}}$
  The set of integers: $\Z$

* $\newcommand{\R}{\mathbb{R}}$
  The set of real numbers: $\R$

--------------------------------------------------------------------------------------------

## 2023-01-26. Inequality: $(1 + x)^n \le e^{nx}$ for $x \ge 0$

_Proof 1_.  The result follows immediately from the observation that $1 + x \le e^x$.

_Proof 2_. Let $x \ge 0$. Then

$$
\begin{align}
(1 + x)^n
&= \sum_{k=0}^n {n \choose k} x^k \\
&= \sum_{k=0}^n \left( \frac{n!}{k! (n-k)!} \right) x^k \\
&\le \sum_{k=0}^n \frac{n^k}{k!} x^k \\
&\le \sum_{k=0}^\infty \frac{(nx)^k}{k!} \\
&= e^{nx}.
\end{align}
$$

__Corollary__.  For $x > 0$, $(1 + x)^n < e^{nx}$.

__Corollary__.  For $n \in N$, $(1 + 1/n)^n < e < 3$.

_Proof_. Taking $x = 1/n$ yields the desired result.

__Corollary__.  For $n \in N$, $(1 + a/n)^n < 3^a$.

_Proof_. Taking $x = a/n$ yields the desired result.

--------------------------------------------------------------------------------------------
