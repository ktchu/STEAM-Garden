Linear Algebra Done Right (S. Axler): Exercises 3.C
===================================================

--------------------------------------------------------------------------------------------
### Notation

* $\newcommand{\R}{\mathbb{R}}$
  The set of real numbers: $\R$

* $\newcommand{\C}{\mathbb{C}}$
  The set of complex numbers: $\C$

* $\newcommand{\F}{\mathbb{F}}$
  An arbitrary scalar field:$\F$

* $\newcommand{\null}{\operatorname{null}}$
  The null space of $T$: $\null T$

* $\newcommand{\range}{\operatorname{range}}$
  The range of $T$: $\range T$

* $\newcommand{\maps}[2]{\mathcal{L}\left(#1,#2\right)}$
  The set of linear maps from $V$ to $W$: $\maps{V}{W}$

* $\newcommand{\P}[2][]{\mathcal{P}_{#1}\left(#2\right)}$
  The space of polynomials over of field $\F$: $\P{\F}$

*  The space of polynomials of degree at most $m$ over of field $\F$: $\P[m]{\F}$

* $\newcommand{\M}[1]{\mathcal{M}\left(#1\right)}$
  The matrix of a linear map $T \in \maps{V}{W}$ (with respect to specified bases for $V$
  and $W$): $\M{T}$

--------------------------------------------------------------------------------------------
### 1.

__Problem__. Suppose that $V$ and $W$ are finite-dimensional and $T \in \maps{V}{W}$. Show
that with respect to each choice of bases of $V$ and $W$, the matrix of $T$ has at least
$\dim \range T$ nonzero entries.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 2.

__Problem__. Suppose $D \in \maps{\P[3]{\R}}{\P[2]{\R}}$ is the differentiation map defined
by $Dp = p'$. Find a basis of $\P[3]{\R}$ and a basis of $\P[2]{\R}$ such that the matrix
of $D$ with respect to these bases is

$$
\begin{pmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 \\
\end{pmatrix}.
$$

[Compare the exercise above eto Example 3.3.4. The next exercise generalizes the exercise
above.]

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 3.

__Problem__. Suppose $V$ and $W$ are finite-dimensional and $T \in \maps{V}{W}$. Prove
that there exist a basis of $V$ and a basis of $W$ such that with respect to these bases,
all entries of $\M{T}$ are 0 except that the entries in row $j$, column $j$, equal 1 for
$1 \le j \le \dim \range T$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 4.

__Problem__. Suppose $v_1, \ldots, v_m$ is a basis of $V$ and $W$ is finite-dimensional.
Suppose $T \in \maps{V}{W}$. Prove that there exists a basis $w_1, \ldots, w_n$ of $W$
such that all the entries in the first column of $\M{T}$ (with respect to the bases
$v_1, \ldots, v_m$ and $w_1, \ldots, w_n$) are 0 except for possibly a 1 in the first row,
first column.

[In this exercise, unlike Exercise 3, you are given the basis of $V$ instead of being able
to choose a basis of $V$.]

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 5.

__Problem__. Suppose $w_1, \ldots, w_n$ is a basis of $W$ and $V$ is finite-dimensional.
Suppose $T \in \maps{V}{W}$. Prove that there exists a basis $v_1, \ldots, v_m$ of $V$
such that all the entries in the first row of $\M{T}$ (with respect to the bases
$v_1, \ldots, v_m$ and $w_1, \ldots, w_n$) are 0 except for possibly a 1 in the first row,
first column.

[In this exercise, unlike Exercise 3, you are given the basis of $W$ instead of being able
to choose a basis of $W$.]

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 6.

__Problem__. Suppose $V$ and $W$ are finite-dimensional and $T \in \maps{V}{W}$. Prove that
$\dim \range T = 1$ if and only if there exist a basis of $V$ and a basis of $W$ such that
with respet to these bases, all entries of $\M{T}$ equal 1.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 7.

__Problem__. TODO

__Solution__. TODO

--------------------------------------------------------------------------------------------
