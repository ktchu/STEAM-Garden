Linear Algebra Done Right (S. Axler): Exercises 3.B
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

--------------------------------------------------------------------------------------------
### 1.

__Problem__. Give an example of a linear map $T$ such that $\dim \null T = 3$ and
$\dim \range T = 2$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 2.

__Problem__. Suppose $V$ is a vector space and $S, T \in \maps{V}{V}$ are such that

$$
\range S \subset \null T.
$$

Prove that $(ST)^2 = 0$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 3.

Suppose $v_1, \ldots, v_m$ is a list of vectors in $V$. Define
$T \in \maps{\F^m}{V}$ by

$$
T(z_1, \ldots, z_m) = z_1 v_1 + \cdots + z_m v_m.
$$

#### 3.a.

__Problem__. What property of $T$ corresponds to $v_1, \ldots, v_m$ spanning $V$?

__Solution__. TODO

#### 3.b.

__Problem__. What property of $T$ corresponds to $v_1, \ldots, v_m$ being linearly
independent?

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 4.

__Problem__. Show that

$$
\{ T \in \maps{\R^5}{\R^4} : \dim \null T > 2 \}
$$

is not a subspace of $\maps{\R^5}{\R^4}$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 5.

__Problem__. Give an example of a linear map $T: \R^4 \rightarrow \R^4$ such that

$$
\range T = \null T.
$$

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 6.

__Problem__. Prove that there does not exist a linear map $T: \R^5 \rightarrow \R^5$ such
that

$$
\range T = \null T.
$$

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 7.

__Problem__. Suppose $V$ and $W$ are finite-dimentional with $2 \le \dim V \le \dim W$.
Show that $\{ T \in \maps{V}{W} : T \textrm{ is not injective} \}$ is not a subspace of
$\maps{V}{W}$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 8.

__Problem__. Suppose $V$ and $W$ are finite-dimentional with $\dim V \ge \dim W \ge 2$.
Show that $\{ T \in \maps{V}{W} : T \textrm{ is not surjective} \}$ is not a subspace of
$\maps{V}{W}$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 10.

__Problem__. Suppose $v_1, \ldots, v_n$ spans $V$ and $T \in \maps{V}{W}$. Prove that the
list $T v_1, \ldots, T v_n$ spans $\range T$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 11.

__Problem__. Suppose $S_1, \ldots, S_n$ are injective linear maps such that
$S_1 S_2 \cdots S_n$ makes sense. Prove that $S_1 S_2 \cdots S_n$ is injective.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 12.

__Problem__. Suppose that $V$ is finite-dimensional and that $T \in \maps{V}{W}$. Prove
that there exists a subspace $U$ of $V$ such that $U \cap \null T = \{0\}$ and
$\range T = \{Tu : u \in U\}$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 13.

__Problem__. Suppose $T$ is a linear map from $\F^4$ to $\F^2$ such that

$$
\null T = \{ (x_1, x_2, x_3, x_4) \in \F^4 : x_1 = 5 x_2, x_3 = 7 x_4 \}.
$$

Prove that $T$ is surjective.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 14.

__Problem__. Suppose $U$ is a 3-dimensional subspace of $\R^8$ and that $T$ is a linear map
from $\R^8$ to $\R^5$ such that $\null T = U$. Prove that $T$ is surjective.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 15.

__Problem__. Prove that there does not exist a linear map from $\F^5$ to $\F^2$ whose null
space equals

$$
\{ (x_1, x_2, x_3, x_4, x_5) \in \F^5 : x_1 = 3 x_2, x_3 = x_4 = x_5 \}.
$$

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 16.

__Problem__. Suppose there exists a linear map on $V$ whose null space and range are both
finite-dimensional. Prove that $V$ is finite-dimensional.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 17.

__Problem__. Suppose $V$ and $W$ are both finite-dimensional. Prove that there exists an
injective linear map from $V$ to $W$ if and only if $\dim V \le \dim W$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 18.

__Problem__. Suppose $V$ and $W$ are both finite-dimensional. Prove that there exists an
surjective linear map from $V$ to $W$ if and only if $\dim V \ge \dim W$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 19.

__Problem__. Suppose $V$ and $W$ are both finite-dimensional and that $U$ is a subspace of
$V$. Prove that there exists $T \in \maps{V}{W}$ such that $\null T = U$ if and only if
$\dim U \ge \dim V - \dim W$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 20.

__Problem__. Suppose $V$ and $W$ are both finite-dimensional and that $T \in \maps{V}{W}$.
Prove that $T$ is injective if and only if there exists $S \in \maps{V}{W}$ such that
$ST$ is the identity map on $V$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 21.

__Problem__. Suppose $V$ and $W$ are both finite-dimensional and that $T \in \maps{V}{W}$.
Prove that $T$ is surjective if and only if there exists $S \in \maps{V}{W}$ such that
$TS$ is the identity map on $W$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 22.

__Problem__. Suppose $U$ and $V$ are finite-dimensional vector spaces and
$S \in \maps{V}{W}$ and $T \in \maps{U}{V}$. Prove that

$$
\dim \null ST \le \dim \null S + \dim \null T.
$$

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 23.

__Problem__. Suppose $U$ and $V$ are finite-dimensional vector spaces and
$S \in \maps{V}{W}$ and $T \in \maps{U}{V}$. Prove that

$$
\dim \range ST \le \min\{ \dim \range S, \dim \range T \}.
$$

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 24.

__Problem__. Suppose $W$ is finite-dimensional and $T_1, T_2 \in \maps{V}{W}$. Prove that
$\null T_1 \subset \null T_2$ if and only if there exists $S \in \maps{W}{W}$ such that
$T_2 = S T_1$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 25.

__Problem__. Suppose $V$ is finite-dimensional and $T_1, T_2 \in \maps{V}{W}$. Prove that
$\range T_1 \subset \range T_2$ if and only if there exists $S \in \maps{V}{V}$ such that
$T_1 = T_2 S$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 26.

__Problem__. Suppose $D \in \maps{\P{\R}}{\P{\R}}$ is such that $\deg Dp = (\deg p) - 1$
for every nonconstant polynomial $p \in \P{\R}$. Prove that $D$ is surjective.

[The notation $D$ is used above to remind you of the differentiation map that sends a
polynomial $p$ to $p'$. Without knowing the formula for the derivative of a polynomial
(except that it reduces the degree by 1), you can use the exercise above to show that for
every polynomial $q \in \P{\R}$, there exists a polynomial $p \in \P{\R}$ such that
$p' = q$.]

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 27.

__Problem__. Suppose $p \in \P{\R}$. Prove that there exists a polynomial $q \in \P{\R}$
such that $5q'' + 3q' = p$.

[This exercise can be done without linear algebra, but it's more fun to do it using linear
algebra.]

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 28.

__Problem__. Suppose $T \in \maps{V}{W}$, and $w_1, \ldots, w_m$ is a basis of $\range T$.
Prove that there exist $\varphi_1, \ldots, \varphi_m \in \maps{V}{\F}$ such that

$$
T v = \varphi_1(v) w_1 + \cdots \varphi_m(v) w_m
$$

for every $v \in V$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 29.

__Problem__. Suppose $\varphi \in \maps{V}{\F}$. Suppose $u \in V$ is not in
$\null \varphi$. Prove that

$$
V = \null \varphi \oplus \{au : a \in \F \}.
$$

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 30.

__Problem__. Suppose $\varphi_1$ and $\varphi_2$ are linear maps from $V$ to $\F$ that have
the same null space. Show that there exists a constant $c \in \F$ such that
$\varphi_1 = c \varphi_2$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 31.

__Problem__. Give an example of two linear maps $T_1$ and $T_2$ from $\R^5$ to $\R^2$ that
have the same null space but are such that $T_1$ is not a scalar multiple of $T_2$.

__Solution__. TODO

--------------------------------------------------------------------------------------------
