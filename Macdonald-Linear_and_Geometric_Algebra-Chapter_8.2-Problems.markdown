Linear and Geometric Algebra (A. Macdonald): Chapter 8
======================================================

## Problems 8.2

-------------------------------------------------------------------------------

### 8.2.7

#### c.

Suppose $\mathrm{f}$ is normal. Then
\[
|\mathrm{f} (\mathbf{u})|^2
= \mathrm{f} (\mathbf{u}) \cdot \mathrm{f} (\mathbf{u})
= \mathbf{u} \cdot \mathrm{f^*f} (\mathbf{u})
= \mathbf{u} \cdot \mathrm{ff^*} (\mathbf{u})
= \mathrm{f^*} (\mathbf{u}) \cdot \mathrm{f^*} (\mathbf{u})
= |\mathrm{f^*} (\mathbf{u})|^2
\]
for all $\mathbf{u}$.

Now suppose that $|\mathrm{f} (\mathbf{u})|^2 = |\mathrm{f^*} (\mathbf{u})|^2$
for all $\mathbf{u}$. Then
\[
|\mathrm{f} (\mathbf{u + v})|^2 = |\mathrm{f^*} (\mathbf{u + v})|^2
\]
for all $\mathbf{u}$, $\mathbf{v}$. Expanding both sides, we find that
\[
|\mathrm{f} (\mathbf{u})|^2 + |\mathrm{f} (\mathbf{v})|^2
+ 2 \mathrm{f} (\mathbf{u}) \cdot \mathrm{f} (\mathbf{v})
=
|\mathrm{f^*} (\mathbf{u})|^2 + |\mathrm{f^*} (\mathbf{v})|^2
+ 2 \mathrm{f^*} (\mathbf{u}) \cdot \mathrm{f^*} (\mathbf{v}),
\]
which reduces to
\[
\mathrm{f} (\mathbf{u}) \cdot \mathrm{f} (\mathbf{v})
= \mathrm{f^*} (\mathbf{u}) \cdot \mathrm{f^*} (\mathbf{v}).
\]
Therefore,
\[
\mathbf{u} \cdot \mathrm{f^*f} (\mathbf{v})
= \mathbf{u} \cdot \mathrm{ff^*} (\mathbf{v}).
\]
Since this relation holds for all choices of $\mathbf{u}$,
\[
\mathrm{f^*f} (\mathbf{v}) = \mathrm{ff^*} (\mathbf{v})
\]
for all $\mathbf{v}$, which implies that $\mathrm{f}$ is normal.

-------------------------------------------------------------------------------
