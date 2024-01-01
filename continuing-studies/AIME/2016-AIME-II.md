AIME 2016 II
============

--------------------------------------------------------------------------------------------
### 14.

__Problem__. Equilateral $\triangle ABC$ has side length $600$. Points $P$ and $Q$ lie
outside the plane of $\triangle ABC$ and are on opposite sides of the plane. Furthermore,
$PA = PB = PC$, and $QA = QB = QC$, and the planes of $\triangle PAB$, and $\triangle QAB$
form a $120^\circ$ dihedral angle (the angle between the two planes). There is a point $O$
whose distance from each of $A$, $B$, $C$, $P$, and $Q$ is $d$. Find $d$.

__Solution__. To simplify the problem, consider an equilateral triangle with a side length
of $2$. Observations:

1. $P$ and $Q$ both lie on the line perpendicular to the plane containing $\triangle ABC$
   passing through the centroid of $\triangle ABC$.

2. The line segment $PQ$ has length $2d$.

3. $\triangle PAQ$ is a right triangle because the distance from the midpoint of $PQ$ to
   $A$ is equal to the half $PQ$

4. Let $M$ be the midpoint of $AB$. Then $\triangle PMQ$ is a triangle with a $120^\circ$ at
   vertex $M$.

5. $\triangle PAB$ is an isoceles triangle. 

Let $x = PA$ and $y = QA$.

* #2 implies that $x^2 + y^2 = 4d^2$

* #5 implies that $(PM)^2 = x^2 - 1$ and $(QM)^2 = y^2 - 1$

* #4 implies that

  $$
  \begin{align}
  4d^2 
  &= (PM)^2 + (QM)^2 - 2 (PM) (QM) \cos 120^\circ \\
  &= (PM)^2 + (QM)^2 + (PM) (QM) \\
  &= x^2 + y^2 - 2 + \sqrt{(x^2 - 1)(y^2 - 1)}
  \end{align}
  $$

Together these two equations imply that

$$
4 = (x^2 - 1)(y^2 - 1) = x^2 y^2 - (x^2 + y^2) + 1 = x^2 y^2 - 4d^2 + 1,
$$

which simplifies to

$$
x^2 y^2 = 3 + 4d^2
$$

Finally, the altitude of right triangle $\triangle PAQ$ is equal to $xy / 2d$. Since the
distance between the centroid of a triangle to any vertex is $2/3$ the length of the
median from that vertex to the opposite side, $\frac{xy}{2d} = \frac{2 \sqrt{3}}{3}$.

Therefore,

$$
\left(\frac{4d}{\sqrt{3}}\right)^2 = 3 + 4d^2,
$$

which implies that $d = 3/2$. Scaling the problem so that the equilateral triangle has side
length $600$, we obtain the solution $d = 450$.

--------------------------------------------------------------------------------------------
