AIME 2018 I
===========

--------------------------------------------------------------------------------------------
### 1.

__Problem__. The number $n$ can be written in base 14 as
$\underline{a}\ \underline{b}\ \underline{c},$ can be written in base 15 as
$\underline{a}\ \underline{c}\ \underline{b},$ and can be written in base 6 as
$\underline{a}\ \underline{c}\ \underline{a}\ \underline{c},$ where $a > 0$. Find the
base-10 representation of $n$.

__Solution #1__. From the representation of $n$ in base 14, 15, and 6, we have

$$
\begin{align}
n
&= 14^2 a + 14 b + c \\
&= 15^2 a + 15 c + b \\
&= 6^3 a + 6^2 c + 6 a + c
\end{align}
$$

Using these expressions, we can obtain two equation for the three unknowns:

$$
\begin{align}
14^2 a + 14 b + c &= 15^2 a + 15 c + b \\
15^2 a + 15 c + b &= 6^3 a + 6^2 c + 6 a + c
\end{align}
$$

(note that the third equation that could be formed from the expressions for $n$ is
redundant). Simplifying these equations yields

$$
\begin{align}
29 a - 13 b + 14 c &= 0 \\
3 a + b - 22 c &= 0.
\end{align}
$$

Solving these equations for $a$ and $b$ in terms of $c$, we find that
terms of $a$ yields

$$
\begin{align}
a &= 4 c \\
b &= 22 c - 3 a = 10 c.
\end{align}
$$

Since $a$ must be less than $6$, the only acceptable choice for $c$ is 1, which implies
that $a = 4$ and $b = 10$. Therefore $n = 925$.

__Remark__. Note that even though the system of equation is underdetermined, the problem
is solvable because there is only one solution $(a, b, c)$ that satisifes the constraints
that (1) $a$, $b$, and $c$ are integers and (2) $1 \le a < 6$, $0 \le b < 14$, and
$0 \le c < 6$.

__Solution #2__. From the representation of $n$ in base 14, 15, and 6, we have

$$
\begin{align}
n
&= 14^2 a + 14 b + c \\
&= 15^2 a + 15 c + b \\
&= 6^3 a + 6^2 c + 6 a + c
\end{align}
$$

From the first two representations of $n$, we obtain two congruence relations by
considering the $n \pmod{14}$ and $n \pmod{15}$:

* $c \equiv a + b + c \pmod{14}$, which is equivalent to $a + b \equiv 0 \pmod{14}$ and

* $b \equiv a - b + c \pmod{15}$, which is equivalent to $a -2b + c \equiv 0 \pmod{15}$.

Similarly, the second and third representations of $n$ imply that

* $c \equiv 3a + b + 3c \pmod{6}$, which is equivalent to $3a + b + 2c \equiv 0 \pmod{6}$.

The first congruence relation implies that $a + b = 14$ because $a \ne 0$ and 14 is the
only positive multiple of 14 less than or equal to 18 (the constraints $1 \le a \le 5$ and
$0 \le b \le 13$ imply that $a + b \le 18$).

Next, observe that the second and third congruences imply that 3 divides $(a - 2b + c)$ and
$(3a + b + 2c)$. Eliminating $c$ from these expressions, we find that 3 divides $(a + 5b)$,
which implies that 3 divides $(a + 2b)$. The only pairs $(a, b)$ satisfying $a + b = 14$,
$a + 2b$ divisible by 3, and the constraints on $a$ and $b$ are $(1, 13)$ and $(4, 10).$

Finally, we know that 15 divides $a - 2b +c$ from the second congruence. Considering each
of the possilities for $(a, b)$:

* $(a, b) = (1, 13)$ implies that $c \equiv 10 \pmod{15}$, which is not possible because
  $c < 6$;

* $(a, b) = (4, 10)$ implies that $c \equiv 1 \pmod{15}$, which implies that $c = 1$.

Therefore, $(a, b, c) = (4, 10, 1)$ and $n = 925$.

--------------------------------------------------------------------------------------------
