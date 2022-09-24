---
tags: inequalities
---

--------------------------------------------------------------------------------------------

2022-09-24: Useful Inequalities
===============================

_Author(s)_: Kevin Chu `<kevin@velexi.com>`

_Last Updated_: 2022-09-24

--------------------------------------------------------------------------------------------

If $|x| \le \left( \frac{\sqrt{5} - 1}{2} \right)^{1/2}$, then

$$
\frac{1}{\sqrt{1 - x^2}} \le 1 + x^2.
$$

_Proof_. Consider the polynomial inequality

$$
f(x) = (1 - x^2) (1 + x^2)^2 - 1 \ge 0,
$$

which is equivalent to the desired inequality. Expanding the products, we find that

$$
\begin{align}
f(x)
&= x^2 - x^4 - x^6 \\
&= x^2 \left(1 - x^2 - x^4 \right).
\end{align}
$$

Therefore, the real roots of $f(x)$ are 0 and the square roots of the positive roots of the
quadratic

$$
g(y) = y^2 + y - 1.
$$

From the quadratic formula, the roots of $g(y)$ are

$$
\frac{-1 \pm \sqrt{5}}{2}.
$$

The only positive root of $g(y)$ is

$$
\frac{-1 + \sqrt{5}}{2},
$$

so the real roots of $f(x)$ are 0, $-\left( \frac{-1 + \sqrt{5}}{2} \right)^{1/2}$, and
$\left( \frac{-1 + \sqrt{5}}{2} \right)^{1/2}$. Since the roots except for 0 are all simple,
$f(x)$ changes sign at each of the nonzero roots. Since $f(1) = -1$ is negative and
$\left( \frac{\sqrt{5} - 1}{2} \right)^{1/2} < 1$, we can conclude that $f(x)$ is
nonnegative on the closed interval
$\left[ 0, \left( \frac{\sqrt{5} - 1}{2} \right)^{1/2} \right]$. Analogous reasoning based
on the observations that $f(-1) = -1$ and
$-\left( \frac{\sqrt{5} - 1}{2} \right)^{1/2} > -1$ implies that $f(x)$ is nonnegative on
the closed interval $\left[ -\left( \frac{\sqrt{5} - 1}{2} \right)^{1/2}, 0 \right]$.
Therefore, $f(x) \ge 0$ when $|x| \le \left( \frac{\sqrt{5} - 1}{2} \right)^{1/2}$, which
is the desired result.

--------------------------------------------------------------------------------------------
