Linear and Geometric Algebra (A. Macdonald): Chapter 4
======================================================

## Problems 4.4

-------------------------------------------------------------------------------

### 4.4.1

__Problem__. Let $\{ \mathbf{e}_1, \ldots, \mathbf{e}_n \}$ be an orthonormal
basis for an inner product space. Let
$\mathbf{v} = v_1 \mathbf{e}_1 + \cdots + v_n \mathbf{e}_n$. Show that
$|\mathbf{v}|^2 = v_1^2 + \cdots + v_n^2$.

__Solution__.

\[
|\mathbf{v}|^2 = \mathbf{v} \cdot \mathbf{v}
= \sum_{i,j} v_i v_j (\mathbf{e}_i \cdot \mathbf{e}_j)
= \sum_{i,j} v_i v_j \delta_{ij}
= \sum_{i} v_i^2.
\]

### 4.4.2

__Problem__. Let $\{ \mathbf{f}_1, \ldots, \mathbf{f}_n \}$ be an orthogonal,
but not necessarily orthonormal, basis for an inner product space $\mathbf{V}$.
Give an analog of the Fourier expansion for this basis.

__Solution__.

\[
\mathbf{v} =
  \frac{(\mathbf{v} \cdot \mathbf{f}_1)}{|\mathbf{f}_1|^2} \mathbf{f}_1
+ \cdots
+ \frac{(\mathbf{v} \cdot \mathbf{f}_n)}{|\mathbf{f}_n|^2} \mathbf{f}_n
\]

To see this, consider the orthonormal basis
$\{ \mathbf{e}_1, \ldots, \mathbf{e}_n \}$ constructed by normalizing the
basis $\{ \mathbf{f}_1, \ldots, \mathbf{f}_n \}$. The Fourier expansion of
an arbitrary vector $\mathbf{v}$ in terms of $\{ \mathbf{e}_i \}$ is given
by:

\[
\mathbf{v} =
  (\mathbf{v} \cdot \mathbf{e}_1) \mathbf{e}_1
+ \cdots
+ (\mathbf{v} \cdot \mathbf{e}_n) \mathbf{e}_n.
\]

Substituting the relation $\mathbf{e}_i = \mathbf{f}_i / |\mathbf{f}_i|$, we
obtain the above expansion in terms of $\{ \mathbf{f}_i \}$.

### 4.4.3

__Problem__. (Parseval's identity). Prove _Parseval's identity_ for an
orthonormal basis $\{ \mathbf{e}_i \}$:

\[
\mathbf{u} \cdot \mathbf{v} =
  (\mathbf{e}_1 \cdot \mathbf{u})(\mathbf{v} \cdot \mathbf{e}_1)
+ \cdots
+ (\mathbf{e}_n \cdot \mathbf{u})(\mathbf{v} \cdot \mathbf{e}_n)
\]

__Solution__.

Construct the Fourier expansion of $\mathbf{u}$ and $\mathbf{v}$ in terms of
$\{ \mathbf{e}_i \}$:

\[
\mathbf{u} = \sum_i (\mathbf{u} \cdot \mathbf{e}_i) \mathbf{e}_i \\
\mathbf{v} = \sum_i (\mathbf{v} \cdot \mathbf{e}_i) \mathbf{e}_i
\]

Then the dot product of $\mathbf{u}$ and $\mathbf{v}$ is equal to

\[
\mathbf{u} \cdot \mathbf{v}
= \left( \sum_i (\mathbf{u} \cdot \mathbf{e}_i) \mathbf{e}_i \right)
  \left( \cdot \sum_i (\mathbf{v} \cdot \mathbf{e}_i) \mathbf{e}_i \right)
= \sum_{i,j} (\mathbf{u} \cdot \mathbf{e}_i) (\mathbf{v} \cdot \mathbf{e}_j)
    (\mathbf{e}_i \cdot \mathbf{e}_j) \\
= \sum_{i,j} (\mathbf{u} \cdot \mathbf{e}_i) (\mathbf{v} \cdot \mathbf{e}_j)
    \delta_{ij}
= \sum_i (\mathbf{u} \cdot \mathbf{e}_i) (\mathbf{v} \cdot \mathbf{e}_i)
= \sum_i (\mathbf{e}_i \cdot \mathbf{u}) (\mathbf{v} \cdot \mathbf{e}_i)
\]

### 4.4.4

__Problem__. Use Gram-Schmidt orthogonalization to produce an _orthonormal_
set from the vectors $\mathbf{u}_1 = (1,1,0,1)$, $\mathbf{u}_2 = (3,1,1,-1)$,
$\mathbf{u}_3 = (0,1,-1,1)$.

__Solution__.

_First basis vector $\mathbf{e}_1$_.

\[
\mathbf{e}_1 = \mathbf{u}_1 / |\mathbf{u}_1| = (1,1,0,1) / \sqrt{3}
\]

_Second basis vector $\mathbf{e}_2$_.

\[
\mathbf{b}_2
= \mathbf{u}_2 - (\mathbf{u}_2 \cdot \mathbf{e}_1) \mathbf{e}_1
= (3,1,1,-1) - ((3,1,1,-1) \cdot (1,1,0,1)) (1,1,0,1) / 3 \\
= (3,1,1,-1) - (1,1,0,1) = (2,0,1,-2)
\]

\[
\mathbf{e}_2 = \mathbf{b}_2 / |\mathbf{b}_2| = (2,0,1,-2) / 3
\]

_Third basis vector $\mathbf{e}_3$_.

\[
\mathbf{b}_3
= \mathbf{u}_3
  - (\mathbf{u}_3 \cdot \mathbf{e}_1) \mathbf{e}_1
  - (\mathbf{u}_2 \cdot \mathbf{e}_2) \mathbf{e}_2 \\
= (0,1,-1,1)
  - ((0,1,-1,1) \cdot (1,1,0,1)) (1,1,0,1) / 3
  - ((0,1,-1,1) \cdot (2,0,1,-2)) (2,0,1,-2) / 9 \\
= (0,1,-1,1) - (2,2,0,2) / 3 + (2,0,1,-2) / 3
= (0,1,-2,-1) / 3
\]

\[
\mathbf{e}_3 = \mathbf{b}_3 / |\mathbf{b}_3|
= (0,1,-2,-1) / \sqrt{6}
\]

### 4.4.5

__Problem__. Use Gram-Schmidt orthogonalization to produce an _orthonormal_
set from the vectors $\mathbf{u}_1 = (1,2,3,4)$, $\mathbf{u}_2 = (-2,2,1,-1)$,
$\mathbf{u}_3 = (3,4,5,6)$.

__Solution__.

_First basis vector $\mathbf{e}_1$_.

\[
\mathbf{e}_1 = \mathbf{u}_1 / |\mathbf{u}_1| = (1,2,3,4) / \sqrt{30}
\]

_Second basis vector $\mathbf{e}_2$_.

\[
\mathbf{b}_2
= \mathbf{u}_2 - (\mathbf{u}_2 \cdot \mathbf{e}_1) \mathbf{e}_1
= (-2,2,1,-1) - ((-2,2,1,-1) \cdot (1,2,3,4)) (1,2,3,4) / 30 \\
= (-2,2,1,-1) - (1,2,3,4) / 30 = (-61, 58, 27, -34) / 30
\]

\[
\mathbf{e}_2 = \mathbf{b}_2 / |\mathbf{b}_2| = (-61, 58, 27, -34) / \sqrt{8970}
\]

_Third basis vector $\mathbf{e}_3$_.

\[
\mathbf{b}_3
= \mathbf{u}_3
  - (\mathbf{u}_3 \cdot \mathbf{e}_1) \mathbf{e}_1
  - (\mathbf{u}_2 \cdot \mathbf{e}_2) \mathbf{e}_2 \\
= (3,4,5,6)
  - ((3,4,5,6) \cdot (1,2,3,4)) (1,2,3,4) / 30
  - ((3,4,5,6) \cdot (-61, 58, 27, -34)) (-61, 58, 27, -34) / 8970 \\
= (3,4,5,6) - 5 (1,2,3,4) / 3 + 2 (-61, 58, 27, -34) / 897
= (358, 238, 18, -222) / 299
\]

\[
\mathbf{e}_3 = \mathbf{b}_3 / |\mathbf{b}_3|
= \frac{1}{14 \sqrt{299}} (179, 119, 9, -111)
\]

### 4.4.6

Consider the vectors $f_0(x) = 1, f_1(x) = x, \ldots, f_n(x) = x^n$ in
$C[-1, 1]$. They are linearly independent.

#### 4.4.6.a

__Problem__. Perform a Gram-Schmidt orthogonalization on $f_0, f_1, f_2$ to
obtain the polynomials $P_0, P_1, P_2$. Except for scalar factors,
$P_0, P_1, P_2, \ldots$ are called _Legendre polynomials_. They are widely
used in physics and engineering.

__Solution__.

\[
P_0(x) = f_0(x) = 1
\]

\[
P_1 (x)
= f_1(x) - \frac{f_1 \cdot f_0}{f_0 \cdot f_0} f_0(x)
= f_1(x) - \frac{\int_{-1}^1 f_1(x) f_0(x) dx}{\int_{-1}^1 f_0(x)^2 dx} f_0(x)
= x - \frac{\int_{-1}^1 x dx}{\int_{-1}^1 dx} = x - 0
= x
\]

\[
P_2 (x)
= f_2(x) - \frac{f_2 \cdot f_0}{f_0 \cdot f_0} f_0(x)
         - \frac{f_2 \cdot f_1}{f_1 \cdot f_1} f_1(x) \\
= f_2(x)
  - \frac{\int_{-1}^1 f_2(x) f_0(x) dx}{\int_{-1}^1 f_0(x)^2 dx} f_0(x)
  - \frac{\int_{-1}^1 f_2(x) f_1(x) dx}{\int_{-1}^1 f_1(x)^2 dx} f_1(x) \\
= x^2 - \frac{\int_{-1}^1 x^2 dx}{\int_{-1}^1 dx}
      - \frac{\int_{-1}^1 x^3 dx}{\int_{-1}^1 x^2 dx} x
= x^2 - \frac{1}{3} - 0 x
= x^2 - \frac{1}{3}
\]

#### 4.4.6.b

__Problem__. Find the Fourier expansion of $f(x) = a + b x + c x^2$ with
respect to $P_0, P_1, P_2$. Use Problem 4.4.2.

__Solution__.

\[
f(x)
=   \frac{(f \cdot P_0)}{(P_0 \cdot P_0)} P_0(x)
  + \frac{(f \cdot P_1)}{(P_1 \cdot P_1)} P_1(x)
  + \frac{(f \cdot P_2)}{(P_2 \cdot P_2)} P_2(x) \\
=   (a +  c / 3) P_0(x) + b P_1(x) + c P_2(x)
\]

### 4.4.7

#### 4.4.7.a

__Problem__. Suppose that the system of linear equations
$A \mathbf{x} = \mathbf{b}$ has a solution. Show that the system has a unique
solution in $\mathcal{N}(A)^{\perp}$. _Hint_. Decompose a solution using
Theorem 4.25e. For uniqueness, show that the difference between two solutions
in $\mathcal{N}(A)^{\perp}$ is in both $\mathcal{N}(A)$ and
$\mathcal{N}(A)^{\perp}$.

__Solution__. Let $\mathbf{x}^*$ be a solution to $A \mathbf{x} = \mathbf{b}$.
Then, $\mathbf{x}^*$ can be decomposed as a sum
$\mathbf{x}^* = \mathbf{x}_\perp + \mathbf{x}_\parallel$ where
$\mathbf{x}_\perp \in \mathcal{N}(A)^\perp$ and
$\mathbf{x}_\parallel \in \mathcal{N}(A)$. Since $A \mathbf{x}^* = \mathbf{b}$,

\[
A (\mathbf{x}_\perp + \mathbf{x}_\parallel)
= A \mathbf{x}_\perp + A \mathbf{x}_\parallel
= A \mathbf{x}_\perp
= \mathbf{b},
\]

where the second to last equality follows because
$\mathbf{x}_\parallel \in \mathcal{N}(A)$ implies that
$A \mathbf{x}_\parallel = \mathbf{0}$. Therefore,
$A \mathbf{x} = \mathbf{b}$ has a solution in $\mathcal{N}(A)^\perp$.

To show that $\mathbf{x}_\perp$ is unique, suppose that
$\mathbf{x}^\dagger \in \mathcal{N}(A)^\perp$ satisfies
$A \mathbf{x} = \mathbf{b}$. Then,

\[
A \mathbf{x}_\perp = A \mathbf{x}^\dagger
\Rightarrow A (\mathbf{x}_\perp - \mathbf{x}^\dagger) = 0
\Rightarrow \mathbf{x}_\perp - \mathbf{x}^\dagger \in \mathbf{N}(A).
\]

But $\mathbf{x}_\perp - \mathbf{x}^\dagger$ is also contained in
$\mathcal{N}(A)^\perp$ because $\mathcal{N}(A)^\perp$ is a linear space.
Therefore, $\mathbf{x}_\perp = \mathbf{x}^\dagger$ because $\mathbf{0}$ is the
only vector in the intersection of $\mathcal{N}(A)^\perp$ and $\mathcal{N}(A)$.

#### 4.4.7.b

__Problem__. Show that the solution of Part (a) is the solution of
$A \mathbf{x} = \mathbf{b}$ of minimum norm.

__Solution__. Let $\mathbf{x}^*$ be a solution of $A \mathbf{x} = \mathbf{b}$.
Then $A (\mathbf{x}^* - \mathbf{x}_\perp) = 0$, so
$\mathbf{x}^* - \mathbf{x}_\perp \in \mathcal{N}(A)$. Therefore,

\[
|\mathbf{x}^*|^2
= |(\mathbf{x}^* - \mathbf{x}_\perp) + \mathbf{x}_\perp|^2
= |\mathbf{x}^* - \mathbf{x}_\perp|^2 + |\mathbf{x}_\perp|^2
\ge |\mathbf{x}_\perp|^2,
\]

where the second inequality follows because $\mathbf{x}^* - \mathbf{x}_\perp$
and $\mathbf{x}_\perp$ are orthogonal.

### 4.4.8

Set $d(\mathbf{u}, \mathbf{v}) = |\mathbf{v} - \mathbf{u}|$. A set with a
scalar valued function $d$ satisfying the following properties (a)-(c)
is called a _metric space_. The problem shows that every inner product space
is a metric space.

#### 4.4.8.a

__Problem__. If $\mathbf{u} \ne \mathbf{v}$, then
$d(\mathbf{u}, \mathbf{v}) > 0$ and $d(\mathbf{u}, \mathbf{u}) = 0$.

__Solution__. The result follows from the property that $|\mathbf{u}| > 0$
if $\mathbf{u} \ne \mathbf{0}$ and $|\mathbf{0}| = 0$.

#### 4.4.8.b

__Problem__. Prove that $d(\mathbf{u}, \mathbf{v}) = d(\mathbf{v}, \mathbf{u})$.

__Solution__. The result follows because

\[
|\mathbf{u} - \mathbf{v}|
= \sqrt{(\mathbf{u} - \mathbf{v}) \cdot (\mathbf{u} - \mathbf{v})}
= \sqrt{(\mathbf{v} - \mathbf{u}) \cdot (\mathbf{v} - \mathbf{u})}
= |\mathbf{v} - \mathbf{u}|.
\]

#### 4.4.8.c

__Problem__. Prove that $d(\mathbf{u}, \mathbf{w}) \le
d(\mathbf{u}, \mathbf{v}) + d(\mathbf{v}, \mathbf{w})$.

__Solution__. The result follows from the triangle inequality for norms.

### 4.4.9

#### 4.4.9.a

__Problem__. Find the least squares line for the points (0, 1.5), (1, 2.5),
(2, 5.5), (3, 6.5), (4, 9.5), (5, 10.5).

__Solution__. The least squares line is the least squares solution to the
equation

\[
\left[ \begin{array}{cc}
0 & 1 \\
1 & 1 \\
2 & 1 \\
3 & 1 \\
4 & 1 \\
5 & 1
\end{array}
\right]

\left[ \begin{array}{c}
m \\
b
\end{array}
\right]

=

\left[ \begin{array}{c}
1.5 \\
2.5 \\
5.5 \\
6.5 \\
9.5 \\
10.5
\end{array}
\right]
\]

Inverting the normal equation associated with this least squares problem
yields $m = 1.914$ and $b = 1.214$, so the least squares line is
$y = 1.914 x + 1.214$ (to three decimal places in the coefficients).

#### 4.4.9.b

__Problem__. Graph the points and line from Part (a).

__Solution__. Skipped.

### 4.4.10

__Problem__. Write an expression for the quantity which is minimized by the
least squares line. Interpret the expression geometrically with a diagram in
the $xy$-plane. The expression should contain only the coordinates of the data
points. No vectors or matrices are allowed. You need not carry out the
minimization.

__Solution__. In vector form, the quantity minimized to find the least squares
line is

\[
\left|
  \mathbf{y} -
  \left[\begin{array}{cc}
    \mathbf{x} & \mathbf{1}
  \end{array}\right]
  \left[\begin{array}{c}
    m \\
    b
  \end{array}\right]
\right|^2
\]

Expanding this expression in terms of data points, we obtain the expression

\[
\sum_i \left( y_i - (m x_i + b) \right)^2.
\]

Geometrically, each term in this expression is the square of the difference
between the $y$ value of the $i$-th data point and the $y$ value of the least
square line at the $x$ value of the $i$-th data point. The full expression
is the sum of the squared errors.

### 4.4.11

Least squares is not limited to fitting data points to a line.

#### 4.4.11.a

__Problem__. Show that no quadratic polynomial $f(x) = a x^2 + b x + c$ passes
through the five points (1,0), (-1,4), (2,1), (-2,7), (3,3).

__Solution__. Three points uniquely determine a quadratic polynomial. The
quadratic polynomial points determined by the points (1,0), (-1,4), and (2,1)
satisfies:

\[
 a +  b + c = 0 \\
 a -  b + c = 4 \\
4a + 2b + c = 1
\]

Solving this system of equations, we find that the quadratic polynomial
determined by the first three points is $x^2 - 2x + 1$.

Neither (2,7) nor (3,3) lie on the quadratic polynomial because

\[
  2^2 - 2(2) + 1 = 1 \ne 7 \\
  3^2 - 2(3) + 1 = 4 \ne 3
\]

#### 4.4.11.b

__Problem__. Define and find the quadratic polynomial which provides the
"closest" fit to the points.

__Solution__. The quadratic polynomial that provides the "closest" fit to the
points in the least squares sense minimizes the following function.

\[
\left|
  \mathbf{y} -
  A \left[\begin{array}{c}
      a \\
      b \\
      c \\
    \end{array}\right]
\right|^2,
\]

where

\[
A = \left[\begin{array}{ccc}
      x_1^2 & x_1 & 1 \\
      \vdots & \vdots & \vdots \\
      x_n^2 & x_n & 1
    \end{array}\right]
\]

Minimization of this function is achieved by solving the normal equation

\[
A^* A \left[\begin{array}{c}
        a \\
        b \\
        c \\
      \end{array}\right]
= A^* \mathbf{y}.
\]

For the data points in Part (a),

\[
A = \left[\begin{array}{ccc}
      1 &  1 & 1 \\
      1 & -1 & 1 \\
      4 &  2 & 1 \\
      4 & -2 & 1 \\
      9 &  3 & 1
    \end{array}\right]
\]

and

\[
  \mathbf{y} = [0, 4, 1, 7, 3]^T.
\]

Solving the normal equation, we find that the best fit quadratic polynomial
(to two decimal places in the coefficients) is

\[
0.72 x^2 - 1.58 x + 1.23.
\]

### 4.4.12

__Problem__. Least squares is not limited to fitting data points to curves.

Suppose that we have data points $(x_k, y_k, z_k)$. We want to find the
equation $z = a x + b y + c$ of a plane which best fits the data in the least
squares sense. Write the matrix equation similar to

\[
\left[\begin{array}{cc}
  \mathbf{x} & \mathbf{1}
\end{array}\right]
\left[\begin{array}{c}
  m \\
  b
\end{array}\right]
= \mathbf{y}
\]

for this.

__Solution__. For the plane that best fits the data in the least squares sense,
the matrix equation analogous to the least square equation for the best fit
line is

\[
\left[\begin{array}{cc}
  \mathbf{x} & \mathbf{y} & \mathbf{1}
\end{array}\right]

\left[\begin{array}{c}
    a \\
    b \\
    c
\end{array}\right]

= \mathbf{z}
\]

### 4.4.13

#### 4.4.13.a

__Problem__. Recall that the least squares solution of
$A \mathbf{x} = \mathbf{b}$ are solutions of
$A \mathbf{x} = P_\mathbf{U} \mathbf{b}$ (Theorem 4.27a). Denote a least
squares solution by $\hat{\mathbf{x}}$. Justify the steps of this proof that

\[
A \hat{\mathbf{x}} = P_\mathbf{U} \mathbf{b} \Leftrightarrow
A^*A \hat{\mathbf{x}} = A^* \mathbf{b}.
\]

_Proof_

\[
A \hat{\mathbf{x}} = P_\mathbf{U} \mathbf{b} \Leftrightarrow \\
\mathbf{b} - A \hat{\mathbf{x}} \perp \mathbf{U} \Leftrightarrow \\
(\mathbf{b} - A \hat{\mathbf{x}}) \cdot \mathbf{u} = 0
  \text{ for all } \mathbf{u} \in \mathbf{U} \Leftrightarrow \\
(\mathbf{b} - A \hat{\mathbf{x}}) \cdot
  A \mathbf{x} = 0 \text{ for all } \mathbf{x} \Leftrightarrow \\
A^* (\mathbf{b} - A \hat{\mathbf{x}}) \cdot
  \mathbf{x} = 0 \text{ for all } \mathbf{x} \Leftrightarrow \\
A^* (\mathbf{b} - A \hat{\mathbf{x}}) = \mathbf{0} \Leftrightarrow \\
A^* A \hat{\mathbf{x}} = A^* \mathbf{b}.
\]

__Solution__.

_Step 1_. $\mathbf{b}$ can be expressed uniquely as
$\mathbf{b}_\parallel + \mathbf{b}_\perp$ where
$\mathbf{b}_\parallel \in \mathbf{U}$ and
$\mathbf{b}_\perp \in \mathbf{U}^\perp$. Since
$\mathbf{b} = P_\mathbf{U} \mathbf{b} + (I - P_\mathbf{U}) \mathbf{b}$
and $P_\mathbf{U} \mathbf{b} \in \mathbf{U}$,
$(I - P_\mathbf{U}) \mathbf{b} \in \mathbf{U}^\perp$. Therefore,

\[
(I - P_\mathbf{U}) \mathbf{b} = \mathbf{b} - P_\mathbf{U} \mathbf{b}
= \mathbf{b} - A \hat{\mathbf{x}}
\]

lies in $\mathbf{U}^\perp$, which implies that
$\mathbf{b} - A \hat{\mathbf{x}}$ is orthogonal to $\mathbf{U}$.

_Step 2_. By definition, any vector that is orthogonal to $\mathbf{U}$ has
zero dot product with all vectors $\mathbf{u} \in \mathbf{U}$.

_Step 3_. Since $\mathbf{U}$ is the span of the columns of $A$, any vector
$\mathbf{u} \in \mathbf{U}$ can be represented as a linear combination of
columns of $A$. In other words, $\mathbf{u} = A \mathbf{x}$ for some
$\mathbf{x}$. Therefore, the result of Step (2) implies that
$\mathbf{b} - A \hat{\mathbf{x}}$ is orthogonal to $A \mathbf{x}$ for all
$\mathbf{x}$.

_Step 4_. Recalling that the dot product of vectors can be expressed as matrix
multiplication, the left hand side of the result of Step (3) can be expressed
as

\[
(A \mathbf{x})^* (\mathbf{b} - A \hat{\mathbf{x}})
= \mathbf{x})^* A^* (\mathbf{b} - A \hat{\mathbf{x}})
= \mathbf{x}^* \left( A^* (\mathbf{b} - A \hat{\mathbf{x}}) \right).
\]

Converting the matrix multiplication back to a dot product, we obtain the
desired result:

\[
A^* (\mathbf{b} - A \hat{\mathbf{x}}) \cdot \mathbf{x} = 0
\]

for all $\mathbf{x}$.

_Step 5_. If the dot product of a vector with all vectors $\mathbf{x}$ is
equal to 0, then the vector is equal to zero. Therefore,

\[
A^* (\mathbf{b} - A \hat{\mathbf{x}}) = \mathbf{0}.
\]

_Step 4_. Carrying out the multiplications in the result of Step (5) and
rearranging the equation yields the desired result

\[
A^* A \hat{\mathbf{x}} = A^* \mathbf{b}.
\]

#### 4.4.13.b

__Problem__. Find the least squares solution of

\[
 x + 2y = 6 \\
2x -  y = 5 \\
3x + 2y = 0 \\
\]

using the normal equation.

Solving the normal equation is not the most practical way to find least squares
solutions. For this see Problem 9.7.4.

__Solution__. The matrix equation equivalent to the systemr of equations is

\[
\left[\begin{array}{cc}
  1 &  2 \\
  2 & -1 \\
  3 &  2
\end{array}\right]

\left[\begin{array}{c}
    x \\
    y
\end{array}\right]

=

\left[\begin{array}{c}
    6 \\
    5 \\
    0
\end{array}\right]
\]

The normal equation for this matrix equation is

\[
\left[\begin{array}{ccc}
  1 &  2 & 3 \\
  2 & -1 & 2
\end{array}\right]
\left[\begin{array}{cc}
  1 &  2 \\
  2 & -1 \\
  3 &  2
\end{array}\right]

\left[\begin{array}{c}
    x \\
    y
\end{array}\right]

=

\left[\begin{array}{ccc}
  1 &  2 & 3 \\
  2 & -1 & 2
\end{array}\right]
\left[\begin{array}{c}
    6 \\
    5 \\
    0
\end{array}\right]
\]

which simplifies to

\[
\left[\begin{array}{cc}
  14 & 6 \\
   6 & 9
\end{array}\right]

\left[\begin{array}{c}
    x \\
    y
\end{array}\right]

=

\left[\begin{array}{c}
    16 \\
     7
\end{array}\right]
\]

Therefore, the least squares solution to the original system of equations is:
$x = 17/15$, $y = 1/45$.

### 4.4.14

If $\mathcal{N}(A) = \{ \mathbf{0} \}$, then $A^* A$ is invertible
(Problem 3.2.6c). Thus the normal equation has the unique solution
$\mathbf{x} = (A^* A)^{-1} A \mathbf{b}$. This is also the unique least squares
solution to $A \mathbf{x} = \mathbf{b}$.

#### 4.4.14.a

__Problem__. Show that $\mathcal{N}(A) = \{ \mathbf{0} \}$ for the $n \times 2$
matrix on the left side of

\[
\left[\begin{array}{cc}
  \mathbf{x} & \mathbf{1}
\end{array}\right]
\left[\begin{array}{c}
  m \\
  b
\end{array}\right]
= \mathbf{y}
\]

Note that by the nature of the problem, the $x$'s are distinct.

__Solution__. Assume $n > 1$, then there are at least two rows in

\[
\left[\begin{array}{cc}
  \mathbf{x} & \mathbf{1}
\end{array}\right]
\]

Suppose that $(a,b) \in \mathcal{N}(A)$. Then,

\[
a \mathbf{x} + b \mathbf{1} = \mathbf{0}.
\]

In particular,

\[
a x_1 + b = 0 \\
a x_2 + b = 0
\]

which implies that $a (x_1 - x_2) = 0$. Since the $x$'s are distinct, $a = 0$,
which implies that $b = 0$. Therefore, $\mathbf{0}$ is the only vector in
$\mathcal{N}(A)$, so $\mathcal{N}(A) = \{ \mathbf{0} \}$.

#### 4.4.14.b

__Problem__. Show that the least squares solution to

\[
\left[\begin{array}{cc}
  \mathbf{x} & \mathbf{1}
\end{array}\right]
\left[\begin{array}{c}
  m \\
  b
\end{array}\right]
= \mathbf{y},
\]

is the solution to

\[
\left[ \begin{array}{cc}
\sum_i x_i^2 & \sum_i x_i \\
\sum_i   x_i & n
\end{array}\right]

\left[ \begin{array}{c}
\hat{m} \\
\hat{b}
\end{array}\right]
=
\left[ \begin{array}{c}
\sum_i x_i y_i \\
\sum_i y_i
\end{array}\right].
\]

Solving for $\hat{m}$ and $\hat{b}$ using Eq. (3.11) gives

\[
\hat{m} = \frac{n \sum x_i y_i - \sum x_i \sum y_i}
               {n \sum x_i^2 - (\sum x_i)^2} \\
\hat{b} = \frac{\sum y_i \sum x_i^2 - \sum x_i \sum x_i y_i}
               {n \sum x_i^2 - (\sum x_i)^2}
\]

This pair of formulas is used to compute the least squares line
$y = \hat{m} x + \hat{b}$.

__Solution__. The normal equation associated with the least square problem is

\[
\left[\begin{array}{c}
  \mathbf{x}^T \\
  \mathbf{1}^T
\end{array}\right]
\left[\begin{array}{cc}
  \mathbf{x} & \mathbf{1}
\end{array}\right]
\left[\begin{array}{c}
  \hat{m} \\
  \hat{b}
\end{array}\right]
=
\left[\begin{array}{c}
  \mathbf{x}^T \\
  \mathbf{1}^T
\end{array}\right]
\mathbf{y}.
\]

Carrying out the matrix multiplications on the left hand side of the equation,
we obtain

\[
\left[\begin{array}{c}
  \mathbf{x}^T \\
  \mathbf{1}^T
\end{array}\right]
\left[\begin{array}{cc}
  \mathbf{x} & \mathbf{1}
\end{array}\right]
=
\left[\begin{array}{cc}
  \mathbf{x}^T \mathbf{x} & \mathbf{x}^T \mathbf{1} \\
  \mathbf{1}^T \mathbf{x} & \mathbf{1}^T \mathbf{1}
\end{array}\right]
=
\left[\begin{array}{cc}
  \sum_i x_i^2 & \sum_i x_i \\
  \sum_i x_i & n
\end{array}\right]
\]

Carrying out the matrix multiplications on the right hand side of the equation,
we obtain

\[
\left[\begin{array}{c}
  \mathbf{x}^T \\
  \mathbf{1}^T
\end{array}\right]
\mathbf{y}
=
\left[\begin{array}{c}
  \mathbf{x}^T \mathbf{y} \\
  \mathbf{1}^T \mathbf{y}
\end{array}\right]
=
\left[\begin{array}{c}
  \sum_i x_i y_i \\
  \sum_i y_i
\end{array}\right]
\]

Substituting these matrices back into the normal equation yields the desired
matrix equation for $\hat{m}$ and $\hat{b}$.

Using the formula for the inverse of a 2 x 2 matrix, we have

\[
\left[ \begin{array}{cc}
\sum_i x_i^2 & \sum_i x_i \\
\sum_i   x_i & n
\end{array}\right]^{-1}
=
\frac{1}{n\sum_i x_i^2 - (\sum_i x_i)^2}
\left[ \begin{array}{cc}
  n         & -\sum_i x_i \\
-\sum_i x_i & \sum_i x_i^2
\end{array}\right]
\]

so that the solution $[\hat{m}, \hat{b}]^T$ is given by

\[
\frac{1}{n\sum_i x_i^2 - (\sum_i x_i)^2}
\left[ \begin{array}{cc}
  n         & -\sum_i x_i \\
-\sum_i x_i & \sum_i x_i^2
\end{array}\right]

\left[\begin{array}{c}
  \sum_i x_i y_i \\
  \sum_i y_i
\end{array}\right].
\]

Carrying out the matrix multiplications yields the formulas for $\hat{m}$ and
$\hat{b}$.

-------------------------------------------------------------------------------
