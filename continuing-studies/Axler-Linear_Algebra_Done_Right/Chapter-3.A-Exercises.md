Linear Algebra Done Right (S. Axler): Exercises 3.A
===================================================

--------------------------------------------------------------------------------------------
### Notation

* $\newcommand{\R}[0]{\mathbb{R}}$
  The set of real numbers: $\R$

* $\newcommand{\maps}[2]{\mathcal{L}\left(#1,#2\right)}$
  The set of linear maps from $V$ to $W$: $\maps{V}{W}$

--------------------------------------------------------------------------------------------
### 1.

__Problem__. Suppose $b, c \in \mathbb{R}$. Define
$T: \mathbb{R}^3 \rightarrow \mathbb{R}^2$ by

$$
T(x, y, z) = (2x - 4y + 3z + b, 6x + cxyz).
$$

Show that $T$ is linear if and only if b = c = 0.

__Solution__.

($\Rightarrow$) If $T$ is linear, then

$$
( 2 \lambda x - 4 \lambda y + 3 \lambda z + b, 6 \lambda x + c \lambda^3 x y z)
= \lambda ( 2 x - 4 y + 3 z + b, 6 x + c x y z)
$$

for all $(x, y, z) \in \mathbb{R}^3$ and all $\lambda \in \mathbb{R}$.
Considering each component independently,

$$
2 \lambda x - 4 \lambda y + 3 \lambda z + b = \lambda (2 x - 4 y + 3 z  + b)
$$

and
$$
6 \lambda x + c \lambda^3 x y z = \lambda (6 x + c x y z)
$$

The equation for the first component simplifies to $b = \lambda b$, which
implies that $b = 0$ because we can choose $\lambda \ne 1$. The equation for
the second component simplifies to

$$
c \lambda^3 x y z = c \lambda x y z,
$$

which implies that $c = 0$ because we can choose $x, y, z \ne 0$ and
$\lambda \ne 0, 1$.

($\Leftarrow$) If $b = c = 0$, then

$$
T(x_1 + x_2, y_1 + y_2, z_1 + z_2)
= ( 2 (x_1 + x_2) - 4 (y_1 + y_2) + 3 (z_1 + z_2), 6 (x_1 + x_2) ) \\
=   ( 2 x_1 - 4 y_1 + 3 z_1, 6 x_1 )
  + ( 2 x_2 - 4 y_2 + 3 z_2, 6 x_2 )
= T(x_1) + T(x_2)
$$

and
$$
T(\lambda x, \lambda y, \lambda z)
= ( 2 \lambda x - 4 \lambda y + 3 \lambda z, 6 \lambda x )
= \lambda (2 x - 4 y + 3 z, 6 x)
= \lambda T(x),
$$

which shows that $T$ is linear.

--------------------------------------------------------------------------------------------
### 2.

__Problem__. Suppose $b, c \in \mathbb{R}$. Define
$T: \mathcal{P}(\mathbb{R}) \rightarrow \mathbb{R}^2$ by

$$
Tp = \left(
  3 p(4) + 5 p'(6) + b p(1) p(2),
  \int_{-1}^2 x^3 p(x) dx + c \sin p(0)
\right).
$$

Show that $T$ is linear if and only if b = c = 0.

__Solution__.

($\Rightarrow$) If $T$ is linear, then

$$
\left(
  3 \lambda p(4) + 5 \lambda p'(6) + b (\lambda p(1)) (\lambda p(2)),
  \int_{-1}^2 x^3 \lambda p(x) dx + c \sin (\lambda p(0))
\right) \\
= \lambda \left(
  3 p(4) + 5 p'(6) + b p(1) p(2),
  \int_{-1}^2 x^3 p(x) dx + c \sin p(0)
  \right)
$$

for all $p \in \mathcal{P}(\mathbb{R})$ and all $\lambda \in \mathbb{R}$.
Considering each component independently,

$$
3 \lambda p(4) + 5 \lambda p'(6) + b (\lambda p(1)) (\lambda p(2))
= \lambda (3 p(4) + 5 p'(6) + b p(1) p(2))
$$

and

$$
\int_{-1}^2 x^3 \lambda p(x) dx + c \sin (\lambda p(0))
= \lambda \int_{-1}^2 x^3 p(x) dx + c \sin p(0)
$$

The equation for the first component simplifies to

$$
\lambda^2 b p(1) p(2) = \lambda b p(1) p(2)
$$

which implies that $b = 0$ because we can choose $\lambda \ne 0, 1$ and $p$
to be a polynomial that has neither 1 nor 2 as roots. The equation for the
second component simplifies to

$$
c \sin (\lambda p(0)) = c \lambda \sin p(0)
$$

Choosing $p$ to be a polynomial such that $p(0)$ is not a multiple of $\pi$(which implies
that $\sin p(0) \ne 0$) and $\lambda$ such that $|\lambda \sin p(0)| > 1$ guarantees that
$\sin (\lambda p(0)) \ne \lambda \sin p(0)$. Therefore, we can conclude that $c = 0$.

($\Leftarrow$) If $b = c = 0$, then

$$
T(p_1 + p_2)
= \left(
  3 \lambda (p_1 + p_2)(4) + 5 \lambda (p_1 + p_2)'(6),
  \int_{-1}^2 x^3 \lambda (p_1 + p_2)(x) dx
  \right) \\
= \left(
  3 \lambda p_1(4) + 5 \lambda p_1'(6),
  \int_{-1}^2 x^3 \lambda p_1(x) dx
  \right)
+ \left(
  3 \lambda p_2(4) + 5 \lambda p_2'(6),
  \int_{-1}^2 x^3 \lambda p_2(x) dx
  \right)
= T(x_1) + T(x_2)
$$

and
$$
T(\lambda p)
= \left(
  3 \lambda p(4) + 5 \lambda p'(6),
  \int_{-1}^2 x^3 \lambda p(x) dx
  \right)
= \lambda \left(
  3 p(4) + 5 p'(6),
  \int_{-1}^2 x^3 p(x) dx
  \right)
= \lambda T(p),
$$

which shows that $T$ is linear.

--------------------------------------------------------------------------------------------
### 3.

__Problem__. Suppose that $T \in \mathcal{L}(\mathbb{F}^n, \mathbb{F}^m)$.
Show that there exist scalars $A_{j,k} \in \mathbb{F}$ for $j = 1, \ldots, m$
and $k = 1, \ldots, n$ such that

$$
T(x_1, \ldots, x_n) = \left(
  A_{1,1} x_1 + \cdots + A_{1,n} x_n,
  \ldots
  A_{m,1} x_1 + \cdots + A_{m,n} x_n,
\right)
$$

for every $(x_1, \ldots, x_n) \in \mathbb{F}^n$.

__Solution__. For each $1 \le k \le n$, let $A_{j,k}$ be defined by

$$
T(\delta_{1k}, \ldots, \delta_{nk}) = (A_{1,k}, \ldots, A_{m, k}),
$$

where the $\delta_{jk}$ is the Kronecker delta function.

Observing that any $(x_1, \ldots, x_n) \in \mathbb{F}^n$ can be expressed
as $\sum_{k=1}^n x_k (\delta_{1k}, \ldots, \delta_{nk})$, the linearity of
$T$ implies that

$$
T(x_1, \ldots, x_n)
= \sum_{k=1}^n x_k T(\delta_{1k}, \ldots, \delta_{nk})
= \sum_{k=1}^n x_k (A_{1,k}, \ldots, A_{m, k})
= \sum_{k=1}^n (A_{1,k} x_k, \ldots, A_{m, k} x_k) \\
= \left( \sum_{k=1}^n A_{1,k} x_k, \ldots, \sum_{k=1}^n A_{m, k} x_k \right),
$$

which is the desired result.

--------------------------------------------------------------------------------------------
### 4.

__Problem__. Suppose $T \in \mathcal{L}(V, W)$ and $v_1, \ldots, v_m$ is a list
of vectors in $V$ such that $T v_1, \ldots, T v_m$ is a linearly independent
list in $W$. Prove that $v_1, \ldots, v_m$ is linearly independent.

__Solution__. If

$$
0 = a_1 v_1 + \cdots + a_m v_m,
$$

then

$$
T 0
= T (a_1 v_1 + \cdots + a_m v_m)
= a_1 (T v_1) + \cdots + a_m (T v_m).
$$

Because $T v_1, \ldots, T v_m$ are linearly independent, $a_i = 0$ for all $i$,
which implies that $v_1, \ldots, v_m$ are linearly independent.

--------------------------------------------------------------------------------------------
### 5.

__Problem__. Prove the assertion in 3.7. Show that $\maps{V}{W}$ is a vector space.

__Solution__. $\maps{V}{W}$ is a vector space because it satisfies the properties of a
vector space.

* _commutativity_. Inherited from commutativity of addition in $W$. For all $v \in V$,

  $$
  (S+T) v = Sv + Tv = Tv + Sv = (T+S) v.
  $$

* _associativity_. Inherited from associativity of addition in $W$. For all $v \in V$,

  $$
  ((T_1 +T_2) + T_3) v
  = (T_1 + T_2) v + T_3 v
  = (T_1 v + T_2 v) + T_3 v \\
  = T_1 v + (T_2 v + T_3 v)
  = T_1 v + (T_2 + T_3) v
  = (T_1 + (T_2 + T_3)) v.
  $$

* _additive identity_.  The zero map, $\mathbf{0}$ defined by $\mathbf{0} v = 0$ for all
  $v \in V$ to is the additive identity. For all $v \in V$,

  $$
  (S + \mathbf{0}) v = Sv + \mathbf{0}v = Sv + 0 = S v.
  $$

* _additive inverse_. Let $S \in \maps{V}{W}$. Define $T$ by $T v = -S v$ for all $v \in V$.
  Then $T$ is the the additive inverse of $S$ because for all $v \in V$

  $$
  (S + T) v = Sv + Tv = Sv + -Sv = 0 = \mathbf{0} v,
  $$

  where $\mathbf{0}$ is the zero map.

* _multiplicative identity_. The scalar $1$ is the multiplicative identity for
  $\maps{V}{W}$. For all $S \in \maps{V}{W}$ and $v \in V$,

  $$
  (1S) v = 1 (S v) = Sv.
  $$

* _distributive properties_. For all $a, b \in F$, $S, T \in \maps{V}{W}$, and $v \in V$,

  $$
  (a (S + T)) v
  = a ((S + T) v)
  = a (S v + T v)
  = a (Sv) + a (Tv)
  = (aS) v + (aT) v
  = (aS + aT) v
  $$

  and

  $$
  ((a + b) S) v
  = (a + b) (Sv)
  = a (Sv) + b (Sv)
  = (aS) v + (bS) v
  = (aS + bS) v.
  $$

--------------------------------------------------------------------------------------------
### 6.

__Problem__. Prove the assertion in 3.9. Show that products of linear maps have the
following algebraic properties: associativity, identity, and distributive properties.

__Solution__.

* _associativity_. Follows directly from the definition of the product of linear maps.
 For all $T_1 \in \maps{U}{V_1}$, $T_2 \in \maps{V_1}{V_2}$, $T_3 \in \maps{V_3}{W}$,
 and $u \in U$,

  $$
  ((T_1 T_2) T_3) u
  = (T_1 T_2) (T_3 u)
  = T_1 (T_2 (T_3 u))
  = T_1 (T_2 T_3) u))
  = (T_1 (T_2 T_3)) u
  $$

* _identity_. For all $S \in \maps{V}{W}$ and $v \in V$,

  $$
  (IS) v = I (Sv) = Sv
  $$

  and

  $$
  (SI) v = S (Iv) = Sv.
  $$

* _distributive properties_.  Follows directly from the definition of the product of
  linear maps and vector space properties spaces of linear maps.
  For all $S, S_1, S_2 \in \maps{U}{V}$, $T, T_1, T_2 \in \maps{V}{W}$, and $u \in U$,

  $$
  ((S_1 + S_2) T) u
  = (S_1 + S_2) (Tu)
  = S_1 (Tu) + S_2 (Tu)
  = (S_1 T) u + (S_2 T) u
  = (S_1 T + S_2 T) u
  $$

  and

  $$
  (S (T_1 + T_2)) u
  = S ((T_1 + T_2) u)
  = S (T_1 u + T_2 u)
  = S (T_1 u) + S (T_2 u)
  = (S T_1) u + (S T_2) u
  = (S T_1 + S T_2) u.
  $$

With these algebraic properties of products of linear maps, spaces of linear maps
$\maps{V}{W}$ are mathematical _rings_.

--------------------------------------------------------------------------------------------
### 7.

__Problem__. Show that every linear map from a 1-dimensional vector space to
itself is multiplication by some scalar. More precisely, prove that if
$\dim V = 1$ and $T \in \mathcal{L} (V, V)$, then there exists
$\lambda \in \mathbb{F}$ such that $T v = \lambda v$ for all $v \in V$.

__Solution__. Let $T \in \maps{V}{V}$ and $u \in V$. Since $\dim V = 1$, all vectors in $V$
must be scalar multiples of $u$. In particular, $T u = \lambda u$. Consider an arbitrary
vector $v = ku \in V$. Linearity of $T$ implies that

$$
T v = T (ku) = k (Tu) = k (\lambda u) = \lambda (ku) = \lambda v.
$$

--------------------------------------------------------------------------------------------
### 8.

__Problem__. Give an example of a function $\varphi: \mathbb{R}^2 \rightarrow \mathbb{R}$
such that

$$
\varphi(av) = a \varphi(v)
$$

for all $a \in \mathbb{R}$ and all $v \in \mathbb{R}^2$ but $\varphi$ is not
linear.

[The exercise above and the next exercise show that neither homogeneity
nor additivity alone is enough to imply that a function is a linear map.]

__Solution__. Define $\varphi(v) = \| v \|_2$. Then

$$
\varphi(av) = \| av \|_2 = a \| v \|_2 = a \varphi(v).
$$

To see that $\varphi$ is not linear, consider $u = (1, 0)$ and $v = (0, 1)$. Then
$\varphi(u + v) = \| u + v \|_2 = \sqrt{2}$ but
$\varphi(u) + \varphi(v) = \| u \|_2 + \| v \|_2 = 2$.

--------------------------------------------------------------------------------------------
### 9.

__Problem__. Give an example of a function
$\varphi: \mathbb{C} \rightarrow \mathbb{C}$ such that

$$
\varphi(w + z) = \varphi(w) + \varphi(z)
$$

for all $w, z \in \mathbb{C}$ but $\varphi$ is not linear.

[There also exists a function $\varphi: \mathbb{R} \rightarrow \mathbb{R}$
such that $\varphi$ satisfies the additivity condition above but $\varphi$
is not linear. However, showing the existence of such a function involves
considerably more advanced tools.]

__Solution__. TODO

--------------------------------------------------------------------------------------------
### 10.

__Problem__. Suppose $U$ is a subspace of $V$ with $U \ne V$. Suppose
$S \in \mathcal{L} (U, W)$ and $S \ne 0$ (which means that $S u \ne 0$ for
some $u \in U$). Define $T: V \rightarrow W$ by

$$
T v = \left\{
  \begin{array}{ll}
    S v & \textrm{if $v \in U$} \\
    0   & \textrm{if $v \in V$ and $v \notin U$}.
  \end{array}
\right.
$$

Prove that $T$ is not a linear map on $V$.

__Solution__. Let $u \in U$ such that $Su \ne 0$. Since $U \ne V$, we there exists
$v \notin U$.  Then $u + v \notin U$ (otherwise, $(u+v) - u = v \in U$), so $T(u+v) = 0$.
Observe that $Tu + Tv = Su + 0 = Su \ne 0$. Therefore, $T(u+v) \ne Tu + Tv$, so $T$ is not
a linear map.

--------------------------------------------------------------------------------------------
### 11.

__Problem__. Suppose $V$ is finite-dimensional. Prove that every linear map on
a subspace of $V$ can be extended to a linear map on $V$. In other words,
show that if $U$ is a subspace of $V$ and $S \in \mathcal{L} (U, W)$, then
there exists $T \in \mathcal{L} (V, W)$ such that $T u = S u$ for all $u \in U$.

__Solution__. Let $B = \{u_1, \ldots, u_m\}$ be a basis for $U$ and let
$\{v_1 = u_1, v_2 = u_2, \ldots v_m = um, v_{m+1}, \ldots, v_n\}$ be an extension of $B$
to a basis for $V$. Define $w_1, \ldots, w_n$ as follows.

* For $1 \le i \le m$, $w_i = S u_i$.

* For $m +1 \le i \le n$, choose $w_i$ to be an arbitrary vector in $W$.

Then exists a unique $T \in \maps{V}{W}$ such that $T v_i = w_i$.

Now, consider $u \in U$. Expressing $u$ in terms of the basis $B$,

$$
u = a_1 u_1 + \cdots + a_m u_m.
$$

Applying the linear map $T$, we find that

$$
T u
= a_1 T u_1 + \cdots + a_m T u_m
= a_1 w_1 + \cdots + a_m w_m
= a_1 S u_1 + \cdots + a_m S u_m
= S (a_1 u_1 + \cdots + a_m u_m)
= S u,
$$

which show that $T$ is an extension of the $S$ to a linear map on $V$.

--------------------------------------------------------------------------------------------
### 12.

__Problem__. Suppose $V$ is finite-dimensional with $\dim V > 0$, and suppose
$W$ is infinite-dimensional. Prove that $\mathcal{L} (V, W)$ is
infinite-dimensional.

__Solution__. Consider any finite set of linear maps $T_1, \ldots, T_k \in
\mathcal{L} (V, W)$. Since $V$ is finite-dimensional, it has a finite basis
$v_1, \ldots, v_n$. Each map $T_i$ is uniquely defined by $T_i v_j = w_{i,j}$.
Since $W$ is infinite-dimensional, there exists a $w^*$ such that $w^*$ is
not in the span of $w_{1, 1}, \ldots, w_{1, k}$. Consider any linear map
$T^*$ such that $T^* v_1 = w^*$. $T^*$ cannot be a linear combination of
$T_1, \ldots, T_k$ because $w^*$ is not a linear combination of
$w_{1, 1}, \ldots, w_{1, k}$. Therefore, any finite set of linear maps
cannot span $\mathcal{L} (V, W)$, which implies that $\mathcal{L} (V, W)$
is infinite-dimensional.

--------------------------------------------------------------------------------------------
### 13.

__Problem__. Suppose $v_1, \ldots, v_m$ is a linearly dependent list of
vectors in $V$. Suppose also that $W \ne \{0\}$. Prove that there exist
$w_1, \ldots, w_m \in W$ such that no $T \in \mathcal{L}(V, W)$ satisfies
$T v_k = w_k$ for each $k = 1, \ldots, m$.

__Solution__. Since $v_1, \ldots, v_m$ is a set of linearly dependent vectors, repeated
application of the Linear Dependence Lemma implies that it contains a subset of vectors
$v_{i_1}, \ldots, v_{i_l}$ satsifying

* $l < m$ and

* the set $v_j, v_{i_1}, \ldots, v_{i_l}$ is linearly dependent for any
  $j \notin \{i_1, \ldots, i_l\}$.

Without loss of generality, let $v_1, \ldots, v_l$ be linearly independent subset of
$v_1, \ldots, v_m$ satisfying the above properties. Then, there exist $a_1, \ldots, a_l$
such that

$$
v_m = a_1 v_1 + \cdots + a_l v_l.
$$

Arbitrarily select $w_1, \ldots, w_{m-1}$ with $w_1 \ne 0$. Select $b_1 \ne a_1$ and define

$$
w_m = b_1 w_1 + a_2 w_2 + \cdots + a_l w_l.
$$

Suppose that there exists $T \in \maps{V}{W}$ where $T v_i = w_i$ for $1 \le i \le m$.
Then

$$
T v_m
= T (a_1 v_1 + a_2 v_2 + \cdots + a_l v_l)
= a_1 (T v_1) + \cdots + a_l (T v_l)
= a_1 w_1 + \cdots + a_l w_l \\
\ne b_1 w_1 + \cdots + a_l w_l
= w_m,
$$

contradicting our assumption that there exists a $T \in \maps{V}{W}$ such that
$T v_i = w_i$ for $1 \le i \le m$.

Therefore, we have constructed a set $w_1, \ldots, w_m$ satisfying the desired property.

--------------------------------------------------------------------------------------------
### 14.

__Problem__. Suppose $V$ is finite-dimensional with $\dim V \ge 2$. Prove that
there exist $S, T \in \mathcal{L} (V, V)$ such that $ST \ne TS$.

__Solution__. Let $V = \R^2$ and $e_1, e_2$ be the standard basis for $\R^2$. Consider the
linear maps $S, T \in \maps{V}{V}$ defined by

$$
S e_1 = e_1
S e_2 = 0
$$

$$
T e_1 = 0
T e_2 = e_1
$$

Then

$$
(ST) e_2 = S (T e_2) = S e_1 = e_1
$$

but

$$
(TS) e_2 = T (S e_2) = T 0 = 0.
$$

Therefore $ST \ne TS$.

--------------------------------------------------------------------------------------------
