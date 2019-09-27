Linear and Geometric Algebra (A. Macdonald): Chapter 4
======================================================

## Problems 4.2

-------------------------------------------------------------------------------

### 4.2.1

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

-------------------------------------------------------------------------------
