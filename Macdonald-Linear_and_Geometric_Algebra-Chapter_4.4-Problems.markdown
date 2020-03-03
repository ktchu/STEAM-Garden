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

-------------------------------------------------------------------------------
