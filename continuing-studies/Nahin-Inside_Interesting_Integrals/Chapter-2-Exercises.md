# Inside Interesting Integrals (Nahin): Chapter 2

--------------------------------------------------------------------------------------------
## 2.1.a

$$
\int_1^\infty \frac{1}{(x + a) \sqrt{x - 1}} dx
$$

__Solution__. Use the substitution $y = \sqrt{x-1}$. Then $dy = dx / 2 \sqrt{x-1}$, so the
integral becomes

$$
2 \int_0^\infty \frac{1}{y^2 + a + 1} dy
= \frac{2}{\sqrt{a+1}} \int_0^\infty \frac{1}{z^2 + 1} dz
= \frac{2}{\sqrt{a+1}} \left. \tan^{-1} z \right|_0^\infty
= \frac{\pi}{\sqrt{a+1}}
$$

where the first equality follows from the substitution $z = y \sqrt{a+1}$.

--------------------------------------------------------------------------------------------
