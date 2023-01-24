---
tags: calculus, integrals
---

--------------------------------------------------------------------------------------------

Inside Interesting Integrals Notes
==================================

_Author(s)_: Kevin Chu `<kevin@velexi.com>`

_Last Updated_: 2022-05-04

## References

* Nahin. "Inside Interesting Integrals". (2020)

--------------------------------------------------------------------------------------------

## 1. TODO

--------------------------------------------------------------------------------------------

## 2. 'Easy' Integrals

### Summary of Tricks

* Use basic substitution.
* Flip the direction of the integration variable.
* Use partial fractions to simplify fractions with denominators that can be factored.
* Add an odd function to an integral of an even function over a symmetric domain.
* For integrals involving an integer parameter $n$, look for a recursion equation that
  relates integrals for consecutive values of $n$.
* Euler's Log-Sine Integral

### 2.3. Euler's Log-Sine Integral

$$
I = \int_0^{\pi/2} \ln \left( a \sin x \right) dx
$$

Observe that

$$
\int_0^{\pi/2} \ln ( a \sin x ) dx
= \int_0^{\pi/2} \ln ( a \cos x ) dx
$$

because the integrands take on the same value over the domain of integration (alternatively,
the substitution $y = \pi/2 - x$ leads to the same conclusion). Therefore,

$$
\begin{align}
2 I
&= \int_0^{\pi/2} \ln ( a \sin x ) dx
 + \int_0^{\pi/2} \ln ( a \cos x ) dx \\
&= \int_0^{\pi/2} \ln ( 2 a \sin x \cos x ) dx
                + \ln \left( \frac{a}{2} \right) dx \\
&= \int_0^{\pi/2} \ln ( \sin 2x ) dx
 + \int_0^{\pi/2} \ln \left( \frac{a}{2} \right) dx \\
&= \int_0^{\pi/2} \ln ( \sin 2x ) dx
 + \frac{\pi}{2} \ln \left( \frac{a}{2} \right).
\end{align}
$$

Using the substitution $y = 2x$, the integral in the last line becomes

$$
\frac{1}{2} \int_0^\pi \ln ( \sin y ) dy
= \int_0^\frac{\pi}{2} \ln ( \sin y ) dy = I
$$

where the first equality follows because $\sin y$ is symmetric about $y = \pi/2$. Combining
these results, we find that

$$
I = \frac{\pi}{2} \ln \left( \frac{a}{2} \right).
$$

--------------------------------------------------------------------------------------------
