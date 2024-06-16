---
tags: infinite-series
---

--------------------------------------------------------------------------------------------

2024-06-15: Interesting Infinite Alternating Series
===================================================

_Author(s)_: Kevin Chu `<kevin@velexi.com>`

_Last Updated_: 2024-06-15

--------------------------------------------------------------------------------------------
## Problem (shared by Akilan Paramasivam)

Find the value of

$$
1 - \frac{1}{4} + \frac{1}{7} - \frac{1}{10} + \cdots
$$

--------------------------------------------------------------------------------------------
## Solution

Define the function

$$
f(x) = \sum_{n=0} \frac{(-1)^n x^{3n + 1}}{3n + 1}.
$$

Then the value of the original alternating series is equal $f(1)$. Observe that

$$
f'(x) = \sum_{n=0} (-1)^n x^{3n} = \frac{1}{1 + x^3}.
$$

The Fundamental Theorem of Calculus implies that

$$
f(1) = \int_0^1 \frac{dx}{1 + x^3}
$$

because f(0) = 1. Using partial fractions, express the integrand as a sum of reciprocals of
expressions that are linear in $x$:

$$
\frac{1}{1 + x^3}
= \frac{1}{3} \left[
    \frac{e^{-2 i \pi / 3}}{x - e^{i \pi / 3}}
    + \frac{1}{x - e^{3 i \pi / 3}}
    + \frac{e^{2 i \pi / 3}}{x - e^{-i \pi / 3}}
  \right]
$$

Performing the integration yields,

$$
\begin{align}
f(1)
&= \frac{1}{3} \left[
       \left. e^{-2 i \pi / 3} \ln\left( x - e^{i \pi / 3} \right) \right|_0^1
     + \left. \ln\left( x - e^{3 i \pi / 3} \right) \right|_0^1
     + \left. e^{2 i \pi / 3} \ln\left( x - e^{-i \pi / 3} \right) \right|_0^1
   \right] \\
&= \frac{1}{3} \left[
       e^{-2 i \pi / 3} \left(
         \ln\left( e^{-i \pi / 3} \right)
       - \ln\left( e^{-2 i \pi / 3} \right)
       \right)
     + \left( \ln 2 - \ln 1 \right)
     + e^{2 i \pi / 3} \left(
         \ln\left( e^{i \pi / 3} \right)
       - \ln\left( e^{2 i \pi / 3} \right)
       \right)
   \right] \\
&= \frac{1}{3} \left[
       \frac{i \pi e^{-2 i \pi / 3}}{3}
     + \ln 2
     - \frac{i \pi e^{2 i \pi / 3}}{3}
   \right] \\
&= \frac{1}{3} \ln 2
 + \frac{\pi}{3 \sqrt{3}}
\end{align}
$$

--------------------------------------------------------------------------------------------
## Generalizations

* This approach seems like it should work for any series of the form

$$
\sum_{n=0} \frac{(-1)^n}{kn + 1}.
$$

--------------------------------------------------------------------------------------------
