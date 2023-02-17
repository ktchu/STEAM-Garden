Linear and Geometric Algebra (A. Macdonald): Chapter 5.2 Problems
=================================================================
--------------------------------------------------------------------------------------------
### 5.2.1.

__Problem__. Show geometrically that vectors $\mathbf{u}$, $\mathbf{v}$,
$\mathbf{w}$ in $\mathbb{R}^3$ are linearly independent if and only if
$\mathbf{u} \wedge \mathbf{v} \wedge \mathbf{w} \ne \mathbf{0}$.

__Solution__. If $\mathbf{u}$, $\mathbf{v}$, and $\mathbf{w}$ are linearly
independent, they do not all lie in the same plane or line. Therefore, the
geometric solid formed by placing them tail-to-tail has a nonzero volume,
which implies that
$\mathbf{u} \wedge \mathbf{v} \wedge \mathbf{w} \ne \mathbf{0}$.

If $\mathbf{u} \wedge \mathbf{v} \wedge \mathbf{w} \ne \mathbf{0}$, the solid
parallelipiped formed by placing $\mathbf{u}$, $\mathbf{v}$, and $\mathbf{w}$
tail-to-tail has a nonzero volume, which implies that the three vectors do not
lie the same plane or line. Therefore, they are linearly independent.

--------------------------------------------------------------------------------------------
### 5.2.2.

__Problem__. Let

$$
\begin{align}
\mathbf{u} &= u_1 \mathbf{e}_1 + u_2 \mathbf{e}_2 + u_3 \mathbf{e}_3, \\
\mathbf{v} &= v_1 \mathbf{e}_1 + v_2 \mathbf{e}_2 + v_3 \mathbf{e}_3, \\
\mathbf{w} &= w_1 \mathbf{e}_1 + w_2 \mathbf{e}_2 + w_3 \mathbf{e}_3.
\end{align}
$$

Show that $(\mathbf{u} \wedge \mathbf{v}) \wedge \mathbf{w}$ is equal to

$$
( u_1 v_2 w_3 - u_1 v_3 w_2
+ u_2 v_3 w_1 - u_2 v_1 w_3
+ u_3 v_1 w_2 - u_3 v_2 w_1)
(\mathbf{e}_1 \wedge \mathbf{e}_2 \wedge \mathbf{e}_3).
$$

Compare with equation (5.2):

$$
\mathbf{u} \wedge \mathbf{v}
= (u_1 v_2 - u_2 v_1) (\mathbf{e}_1 \wedge \mathbf{e}_2).
$$

Computing $\mathbf{u} \wedge (\mathbf{v} \wedge \mathbf{w})$ gives the
same result, consistent with associativity.

The problem shows that the outer product of three vectors is always a scalar
multiple of $\mathbf{e}_1 \wedge \mathbf{e}_2 \wedge \mathbf{e}_3$. We already
knew this from Exercise 5.5b. The scalar multiple is the oriented volume of the
parallelipiped with sides $\mathbf{u}$, $\mathbf{v}$, $\mathbf{w}$.

__Solution__.

$$
\mathbf{u} \wedge \mathbf{v}
= (u_3 v_2 - u_2 v_3) (\mathbf{e}_3 \wedge \mathbf{e}_2) +
  (u_1 v_3 - u_3 v_1) (\mathbf{e}_1 \wedge \mathbf{e}_3) +
  (u_2 v_1 - u_1 v_2) (\mathbf{e}_2 \wedge \mathbf{e}_1)
$$

$$
(\mathbf{u} \wedge \mathbf{v}) \wedge \mathbf{w}
= \left(
    (u_3 v_2 - u_2 v_3) (\mathbf{e}_3 \wedge \mathbf{e}_2) +
    (u_1 v_3 - u_3 v_1) (\mathbf{e}_1 \wedge \mathbf{e}_3) + \\
    (u_2 v_1 - u_1 v_2) (\mathbf{e}_2 \wedge \mathbf{e}_1)
  \right) \wedge
(w_1 \mathbf{e}_1 + w_2 \mathbf{e}_2 + w_3 \mathbf{e}_3)
$$

Expanding this product and retaining only the nonzero terms (i.e., terms that
contain all three unit vectors), we find that

$$
(\mathbf{u} \wedge \mathbf{v}) \wedge \mathbf{w} = \\
  (u_3 v_2 w_1 - u_2 v_3 w_1)
  (\mathbf{e}_3 \wedge \mathbf{e}_2 \wedge \mathbf{e}_1) +
  (u_1 v_3 w_2 - u_3 v_1 w_2)
  (\mathbf{e}_1 \wedge \mathbf{e}_3 \wedge \mathbf{e}_2) +
  (u_2 v_1 w_3 - u_1 v_2 w_3)
  (\mathbf{e}_2 \wedge \mathbf{e}_1 \wedge \mathbf{e}_3)
$$

Aligning orientations of the base trivector and rearranging terms, we arrive
at the desired result:

$$
(\mathbf{u} \wedge \mathbf{v}) \wedge \mathbf{w}
= (u_1 v_2 w_3 - u_1 v_3 w_2 + u_2 v_3 w_1 - u_2 v_1 w_3 +
   u_3 v_1 w_2 - u_3 v_2 w_1)
  (\mathbf{e}_1 \wedge \mathbf{e}_2 \wedge \mathbf{e}_3)
$$

--------------------------------------------------------------------------------------------
