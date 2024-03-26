AIME 2014 I
===========

--------------------------------------------------------------------------------------------
### 14.

__Problem__. Let $m$ be the largest real solution to the equation

$$
\frac{3}{x-3} + \frac{5}{x-5} + \frac{17}{x-17} + \frac{19}{x-19}
= x^2 - 11 x - 4
$$

There are positive integers $a$, $b$, and $c$ such that $m = a + \sqrt{b + \sqrt{c}}$.
Find $a + b + c$.

__Solution__. Observe that

$$
\begin{align}
\frac{3}{x-3} + \frac{5}{x-5} + \frac{17}{x-17} + \frac{19}{x-19}
&= \left( \frac{x}{x-3} + \frac{x}{x-5} + \frac{x}{x-17} + \frac{x}{x-19} \right)
 -\left( \frac{x-3}{x-3} + \frac{x-5}{x-5} + \frac{x-17}{x-17} + \frac{x-19}{x-19} \right)
 \\
&= \left( \frac{x}{x-3} + \frac{x}{x-5} + \frac{x}{x-17} + \frac{x}{x-19} \right) - 4 \\
&= x \left( \frac{1}{x-3} + \frac{1}{x-5} + \frac{1}{x-17} + \frac{1}{x-19} \right) - 4,
\end{align}
$$

so

$$
x \left( \frac{1}{x-3} + \frac{1}{x-5} + \frac{1}{x-17} + \frac{1}{x-19} \right)
= x^2 - 11 x
= x (x - 11).
$$

Thus, $x = 0$ is one solution to the equation. Notice that the middle pair of terms in the
parenthesis on the right hand side can be combined to form

$$
\frac{2(x-11)}{(x-11)^2 - 6^2}.
$$

Similarly, the first and last terms in the parenthesis can be combined to form

$$
\frac{2(x-11)}{(x-11)^2 - 8^2}.
$$

$$
2 (x-11) \left[ \frac{1}{(x-11)^2-6^2} + \frac{1}{(x-11)^2-8^2} \right]
= x - 11,
$$

which yields $x = 11$ as a second solution. Letting $z = (x-11)^2$ and rearranging, the
remaining solutions must satisfy

$$
\begin{align}
0
&= (z - 6^2) (z - 8^2) - 2 ( 2 z - 10^2 ) \\
&= z^2 - 104 z + (48^2 + 2 \cdot 10^2) \\
&= z^2 - 104 z + 4 (24^2 + 50) \\
&= z^2 - 104 z + 4 (24^2 + 48 + 1 + 1) \\
&= z^2 - 104 z + 4 (25^2 + 1).
\end{align}
$$

Using the quadratic formula,

$$
\begin{align}
z
&= \frac{104 \pm \sqrt{104^2 - 4^2 (25^2 + 1)}}{2} \\
&= \frac{104 \pm \sqrt{4^2 \cdot 26^2 - 4^2 (25^2 + 1)}}{2} \\
&= 52 \pm 2 \sqrt{26^2 - 25^2 - 1} \\
&= 52 \pm 2 \sqrt{50},
\end{align}
$$

which implies that the last two solutions for $x$ are

$$
x = 11 + \sqrt{52 \pm 2\sqrt{50}}.
$$

Therefore, the largest solution to the original equation is
$x = 11 + \sqrt{52 + 2\sqrt{50}} = 11 + \sqrt{52 + \sqrt{200}}$,
so the answer to the problem is $11 + 52 + 200 = 263$.

--------------------------------------------------------------------------------------------
