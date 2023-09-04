Understanding Analysis (S. Abbott): Section 4.3 Exercises
=========================================================

--------------------------------------------------------------------------------------------
### Notation

* $\newcommand{\N}{\mathbb{N}}$
  The set of natural numbers: $\N$

* $\newcommand{\R}{\mathbb{R}}$
  The set of real numbers: $\R$

--------------------------------------------------------------------------------------------
### 4.3.1.

Let $g(x) = \sqrt[3]{x}.$

#### 4.3.1.a.

__Problem__. Prove that $g$ is continuous at $c = 0.$

__Solution__. Let $\epsilon > 0.$ Choose $\delta = \epsilon^3.$ Then for $|x - 0| < \delta$,
we have $|g(x) - g(0)| = |\sqrt[3]{x} - 0| = |\sqrt[3]{x}| < \sqrt[3]{\delta} = \epsilon,$
which implies that $g$ is continuous at $c = 0.$

#### 4.3.1.b.

__Problem__. Prove that $g$ is continuous at a point $c \ne 0.$ (The identity
$a^3 - b^3 = (a-b)(a^2 + ab + b^2)$ will be helpful.)

__Solution__. Let $\epsilon > 0.$ Since $c \ne 0$, choose
$\delta = \min(\epsilon \sqrt[3]{c^2}, |c|).$ Then for $|x - c| < \delta$, we have

$$
\begin{align}
|g(x) - g(c)|
&= |\sqrt[3]{x} - \sqrt[3]{c}| \\
&= \left| \frac{x - c}{\sqrt[3]{x^2} + \sqrt{3}{cx} + \sqrt[3]{c^2}} \right| \\
&< \frac{|x - c|}{\sqrt[3]{c^2}} \\
&< \frac{\epsilon \sqrt[3]{c^2}}{\sqrt[3]{c^2}} = \epsilon
\end{align}
$$

where the first inequality follows because $\delta \le |c|$ implies that $c$ and $x$ have
the same sign which ensures that $\left( \sqrt[3]{x^2} + \sqrt{3}{cx} \right)$ is strictly
positive. Thus, we conclude that $g$ is continuous at $c.$

--------------------------------------------------------------------------------------------
