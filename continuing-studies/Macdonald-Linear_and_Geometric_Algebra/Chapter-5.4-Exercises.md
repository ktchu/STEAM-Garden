Linear and Geometric Algebra (A. Macdonald): Chapter 5.4 Exercises
==================================================================
--------------------------------------------------------------------------------------------
### Notation

* $\newcommand{\R}{\mathbb{R}}$
  The set of real numbers: $\R$

* $\newcommand{\G}{\mathbb{G}}$
  The geometric algebra in $n$ dimensions: $\G^n$

* $\newcommand{\vec}[1]{\mathbf{#1}}$
  A vector $\vec{u}$

* $\newcommand{\e}{\mathbf{e}}$
  A basis vector $\e_i$

* $\newcommand{\i}{\mathbf{i}}$
  The pseudoscalar $\i$ of $\G^2$

* $\newcommand{\I}{\mathbf{I}}$
  The pseudoscalar $\I$ of $\G^n$

* $\newcommand{\blade}[1]{\mathbf{#1}}$
  A blade $\blade{B}$

--------------------------------------------------------------------------------------------
### 5.13.

__Problem__. The bases $\{ \e_1, \e_2 \}$ and $\{ \e'_1, \e'_2 \}$ are related by

$$
\begin{align}
\e'_1 &=   \cos \theta \ \e_1 + \sin \theta \ \e_2 \\
\e'_2 &= - \sin \theta \ \e_1 + \cos \theta \ \e_2.
\end{align}
$$

Show that $\i' = \i$ algebraically.

__Solution__.

$$
\begin{align}
\i'
&= \e'_1 \e'_2 \\
&= (\cos \theta \ \e_1 + \sin \theta \ \e_2) (- \sin \theta \ \e_1 + \cos \theta \ \e_2) \\
&= -\cos \theta \ \e_1 \e_1 + \cos^2 \theta \ \e_1 \e_2
 - \sin^2 \theta \ \e_2 \e_1 + \sin \theta \cos \theta \ \e_2 \e_2 \\
&= -\cos \theta \sin \theta
 + ( \cos^2 \theta + \sin^2 \theta ) \e_1 \e_2
 + \sin \theta \cos \theta \\
&= \e_1 \e_2 \\
&= \i
\end{align}
$$

--------------------------------------------------------------------------------------------
### 5.14.

#### 5.14.a.

__Problem__. The square of a real scalar cannot be negative. This rule does not extend to
multivectors, for $\i^2 = -1$. Prove this key property of $\i$.

__Solution__.

$$
\i^2
= (\e_1 \e_2) (\e_1 \e_2)
= \e_1 (\e_2 \e_1) \e_2
= -(\e_1 \e_1) (\e_2 \e_2)
= -1
$$

#### 5.14.b.

__Problem__. Compute $\i^0, \i^1, \i^2, \i^3, \i^4, \i^5, \i^6, \i^7, \i^8, \i^9$.

__Solution__.

$$
\begin{align}
\i^0 &= 1 \\
\i^1 &= \i \\
\i^2 &= (\i)(\i) = -1 \\
\i^3 &= (\i^2)(\i) = -\i \\
\i^4 &= (\i^3)(\i) = (-\i)(\i) = -\i^2 = 1\\
\i^5 &= (i^4)(\i) = (1)(\i) = \i \\
\i^6 &= (i^5)(\i) = (\i)(\i) = \i^2 = -1 \\
\i^7 &= (i^6)(\i) = (-1)(\i) = -\i \\
\i^8 &= (i^7)(\i) = (-\i)(\i) = -\i^2  = 1\\
\i^9 &= (i^8)(\i) = (1)(\i) = \i \\
\end{align}
$$

--------------------------------------------------------------------------------------------
### 5.15.

__Problem__. Let $\{ \e_1, \e_2, \e_3 \}$ be an orthonormal basis for $\R^3.$ Then
$\I = \e_1 \e_2 \e_3$ is a _unit pseudoscalar_ for $\G^3.$ Once again, $\I$ is independent,
except for sign, of the orthonormal basis. Show that $\I^2 = -1.$ But note: In $\G^4$,
$\I^2 = +1.$

__Solution__.

$$
\begin{align}
\I^2
&= (\e_1 \e_2 \e_3) (\e_1 \e_2 \e_3) \\
&= \e_1 \e_2 (\e_3 \e_1) \e_2 \e_3 \\
&= -\e_1 \e_2 (\e_1 \e_3) \e_2 \e_3 \\
&= -\e_1 (\e_2 \e_1) \e_3 \e_2 \e_3 \\
&= \e_1 (\e_1 \e_2) \e_3 \e_2 \e_3 \\
&= (\e_1 \e_1) \e_2 \e_3 \e_2 \e_3 \\
&= \e_2 \e_3 \e_2 \e_3 \\
&= \e_2 (\e_3 \e_2) \e_3 \\
&= -\e_2 (\e_2 \e_3) \e_3 \\
&= -(\e_2 \e_2) (\e_3 \e_3) \\
&= -1
\end{align}
$$

--------------------------------------------------------------------------------------------
### 5.16.

__Problem__. Compute:

a. $e^{\i \pi / 4}$

b. $e^{\i \pi / 2}$

c. $e^{\i 2 \pi}$

__Solution__. TODO

a.

$$
e^{\i \pi / 4}
= \cos(\pi/4) + \i \sin(\pi/4)
= \frac{\sqrt{2}}{2} + \i \frac{\sqrt{2}}{2}
$$

b.

$$
e^{\i \pi / 2}
= \cos(\pi/2) + \i \sin(\pi/2)
= 0 + \i
= \i
$$

c.

$$
e^{\i 2 \pi}
= \cos(2 \pi) + \i \sin(2 \pi)
= 1 + 0 \i
= 1
$$

--------------------------------------------------------------------------------------------
### 5.17.

__Problem__. Prove the following properties of $e^{\i \theta}$.

a. $e^{\i \theta_1} e^{\i \theta_2} = e^{\i (\theta_1 + \theta_2)}$

b. $\left( e^{\i \theta} \right)^{-1}= e^{-\i \theta}$

__Solution__.

a.
$$
\begin{align}
e^{\i \theta_1} e^{\i \theta_2}
&= (\cos \theta_1 + \i \sin \theta_1)
   (\cos \theta_2 + \i \sin \theta_2) \\
&= (\cos \theta_1 \cos \theta_2 - \sin \theta_1 \sin \theta_2)
 + \i (\cos \theta_1 \sin \theta_2 + \sin \theta_1 \cos \theta_2) \\
&= \cos (\theta_1 + \theta_2) + \i \sin(\theta_1 + \theta_2) \\
&= e^{\i (\theta_1 + \theta_2)}
\end{align}
$$

b. From part (a),

$$
\begin{align}
(e^{\i \theta}) (e^{-\i \theta}) = e^{i(\theta - \theta)} = e^0 = 1.
\end{align}
$$

Therefore, $(e^{\i \theta})^{-1} = e^{-\i \theta}$.

--------------------------------------------------------------------------------------------
