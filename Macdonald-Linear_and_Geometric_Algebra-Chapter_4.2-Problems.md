Linear and Geometric Algebra (A. Macdonald): Chapter 4
======================================================

## Problems 4.2

-------------------------------------------------------------------------------

### 4.2.1.

__Problem__. Let $A$ be an $n \times m$ matrix, $\mathbf{x} \in \mathbb{R}^m$,
and $\mathbf{y} \in \mathbb{R}^n$. Show that
\[
A \mathbf{x} \cdot \mathbf{y}
= \mathbf{x} \cdot A^* \mathbf{y}.
\]

Use $\Sigma$ notation.

__Solution__.
\[
A \mathbf{x} \cdot \mathbf{y}
= \sum_{i=1}^n ( A \mathbf{x} )_i y_i
= \sum_{i=1}^n \left(\sum_{j=1}^m A_{ij} x_j \right) y_i \\
= \sum_{i=1}^n \sum_{j=1}^m A_{ij} x_j y_i
= \sum_{i=1}^n \sum_{j=1}^m x_j A_{ij} y_i
= \sum_{j=1}^m x_j \left( \sum_{i=1}^n A_{ij} y_i \right) \\
= \sum_{j=1}^m x_j \left(\sum_{i=1}^n A^*_{ji} y_i \right)
= \sum_{j=1}^m x_j ( A^* \mathbf{y} )_j
= \mathbf{x} \cdot A^* \mathbf{y}
\]

### 4.2.2.

Let $\mathbf{v}_1, \ldots, \mathbf{v}_k$ be vectors in
$\mathbb{R}^n$. Place the $\mathbf{v}$'s in an $n \times k$ matrix $A$ as
columns: $A = [\mathbf{v}_1 \ldots \mathbf{v}_k]$.

#### 4.2.2.a.

__Problem__. Describe the entries of the $k \times k$ matrix $A^* A$ in terms
of the $\mathbf{v}$'s.

__Solution__.
\[
A_{ij} = \mathbf{v}_i \cdot \mathbf{v}_j
= \mathbf{v}_j \cdot \mathbf{v}_i = A_{ji}
\]

#### 4.2.2.b.

__Problem__. Give a test for the $\mathbf{v}$'s being orthonormal.

__Solution__. The $\mathbf{v}$'s are orthonormal iff $A^* A = I_k$, the
identity matrix for $k \times k$ matrices.

-------------------------------------------------------------------------------
