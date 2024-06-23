---
tags: integrals, prime-counting-function
---

--------------------------------------------------------------------------------------------
2024-06-23: Interesting Integral Involving the Prime-Counting Function
======================================================================

_Author(s)_: Kevin Chu `<kevin@velexi.com>`

_Last Updated_: 2024-06-23

--------------------------------------------------------------------------------------------
## Problem (shared by Akilan Paramasivam)

Evaluate the integral

$$
\int_{\ln 2}^\infty \frac{\pi\left( e^x \right) dx}{e^{2x} - 1}
$$

where $\pi(z)$ is the _prime-counting function_ and is equal to the number of prime numbers
less than or equal to $z$.

This problem showed up at a recent Stanford Math Tournament.

--------------------------------------------------------------------------------------------
## Solution

Let $I$ denote the value of the integral. Using the change of variable $y = e^x$, the
integral may be expressed as

$$
I = \int_2^\infty \frac{\pi(y) dy}{y (y^2 - 1)}.
$$

Observe that this integral converges because $0 < \pi(y) < y$ for all $y$, which implies
that

$$
\begin{align}
I
&< \frac{1}{2} \int_2^\infty \frac{y dy}{y(y^2-1)} \\
&= \frac{1}{2} \int_2^\infty \frac{dy}{(y^2-1)} \\
&= \frac{1}{2} \int_2^\infty \left[ \frac{-1}{y+1} + \frac{1}{y-1} \right] dy \\
&= \frac{1}{2} \left. \ln\left( \frac{y-1}{y+1} \right) \right|_2^\infty \\
&= \frac{1}{2} \ln 3 < \infty
\end{align}
$$

Using partial fractions to decompose $1/y(y^2-1)$, $I$ becomes

$$
I = \frac{1}{2} \int_2^\infty \pi(y)
    \left[\frac{1}{y+1} - \frac{2}{y} + \frac{1}{y-1} \right] dy
$$

Since $\pi(y) = \sum_{n=1}^{\pi(y)} 1$, we can express the integral as the
integral of a sum

$$
I = \frac{1}{2} \int_2^\infty \sum_{n=1}^{\pi(y)}
    \left[\frac{1}{y+1} - \frac{2}{y} + \frac{1}{y-1} \right] dy.
$$

Observe that for arbitrary integrands $f(y, n)$ we can reverse the order of the integral
and sum (when the integral converges):

$$
\int_2^\infty \sum_{n=1}^{\pi(y)} f(y, n) dy
= \sum_{n=1}^\infty \int_{\min\{y: \pi(y) = n\}}^\infty f(y, n) dy
$$

Since $\min\{y: \pi(y) = n\}$ is equal to the prime $p$ such that $\pi(p) = n$, the last
expression can be rewritten as a sum over the prime numbers:

$$
\sum_{\textrm{$p$ prime}}^\infty \int_p^\infty f(y, n) dy.
$$

Using this observation, $I$ can be expressed the sum

$$
\begin{align}
I
&= \frac{1}{2} \sum_{\textrm{$p$ prime}}^\infty
     \int_p^\infty \left[\frac{1}{y+1} - \frac{2}{y} + \frac{1}{y-1} \right] dy \\
&= \frac{1}{2} \sum_{\textrm{$p$ prime}}^\infty
     \left. \ln\left(\frac{y^2 - 1}{y^2} \right) \right|_p^\infty \\
&= \frac{1}{2} \sum_{\textrm{$p$ prime}}^\infty
     \ln\left(\frac{p^2}{p^2 - 1} \right) \\
&= \frac{1}{2} \sum_{\textrm{$p$ prime}}^\infty
     \ln\left(\frac{1}{1 - 1/p^2} \right) \\
&= \frac{1}{2} \ln \prod_{\textrm{$p$ prime}}^\infty
     \left( \frac{1}{1 - 1/p^2} \right).
\end{align}
$$

Expanding the factors in the product using geometric series and recognizing that the
resulting product over infinite sums is equal to a sum over all natural numbers:

$$
\prod_{\textrm{$p$ prime}}^\infty \left( \frac{1}{1 - 1/p^2} \right)
= \prod_{\textrm{$p$ prime}}^\infty \left( \sum_{k=0}^\infty \frac{1}{p^{2k}} \right)
= \sum_{n=1}^\infty \frac{1}{n^2}
= \frac{\pi^2}{6}.
$$

Thus, we find that $I = \frac{1}{2} \ln \frac{\pi^2}{6}$.

--------------------------------------------------------------------------------------------
## References

* [Euler Product (Wikipedia)](https://en.wikipedia.org/wiki/Euler_product)

--------------------------------------------------------------------------------------------
