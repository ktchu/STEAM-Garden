Linear Algebra Notes
====================

_Author(s)_: Kevin Chu `<kevin@velexi.com>`

_Last Updated_: 2021-09-18

-------------------------------------------------------------------------------

References
----------
* S. Axler. "Linear Algebra Done Right". (2015)

-------------------------------------------------------------------------------

## 1. Vector Spaces

__Key Concepts__

* vector spaces

* subspaces

* sums and direct sums of subspaces

### 1.1. Definition of a Vector Space

(Definition) A vector space over a field $F$ is a set $V$ with addition and
scalar multiplication operations defined satisfying the following properties.

* _Closure properties_

  * $u + v \in V$ for all $u, v \in V$.

  * $au \in V$ for all $u \in V$ and $a \in F$.

* _Associative properties_

  * $(u + v) + w = u + (v + w)$ for all $u, v, w \in V$.

  * $a(bu) = (ab)u$ for all $u \in V$ and $a, b \in F$.

* _Commutativity under Addition_: $u + v = v + u$ for all $u, v \in V$.

* _Additive identity_: there exists and element $0 \in V$ where $v + 0 = v$
  for all $v \in V$.

* _Additive inverses_: for every $v \in V$, there exists a $w \in V$ such that
  $u + w = 0$.

* _Multiplicative Identity_: $1v = v$ for all $v \in V$.

* _Distributive Properties_

  * $a(u + v) = au + av$ for all $u, v \in V$ and $a \in F$.

  * $(a +b) u = au + bu$ for all $u \in V$ and $a, b \in F$.

### 1.2. Subspaces

* (Lemma) __Conditions for a Subspace__. Let $V$ be a vector space.
  $U \subset V$ is a vector space if and only if $U$ satisfies the following
  three conditions.

  * __Additive identity__: $0 \in U$.

  * __Closure under addition__: $u, v \in U$ implies that $u + v \in U$.

  * __Closure under scalar multiplication__: $u \in U$ and $a \in F$ implies
    that $au \in U$.

* __Sums of Subspaces__

  * (Definition) __Sum of Subsets__. Let $U_1, \ldots, U_n$ be subspaces of a
    vector space $V$. Define the sum of $U_1, \ldots, U_n$ by

    \[
      U_1 + \cdots + U_n
      = \{ u_1 + \cdots + u_n | u_i \in U_i \textrm{ for all } i \}
    \]

  * (Lemma) __Smallest Subspace Containing $U_1, \ldots, U_n$__.
    If $U_1, \ldots, U_n$ be subspaces of a vector space $V$,
    $U = U_1 + \cdots + U_n$ possesses the following properties.

    * $U$ a subspace.

    * $U$ is the smallest subspace containing $U_1, \ldots, U_n$.

  * (Remark) The sum of subspaces for vector spaces is analogous to the union
    of sets in set theory.

* __Direct Sums of Subspaces__

  * (Definition) __Direct Sum of Subspaces__. $U = U_1 + \cdots + U_n$ is a
    direct sum if each element of $U$ can be written only one way as a sum
    $u_1 + \cdots + u_n$ where $u_i \in U_i$ for all $i$.

  * (Notation) If $U = U_1 + \cdots + U_n$ is a direct sum, we use the
    notation $U = U_1 \oplus \cdots \oplus U_n$ to indicate that $U$ is a
    direct sum.

  * (Lemma) __Condition for a Direct Sum__. Let $U_1, \ldots, U_n$ be
    subspaces of a vector space $V$. The following two statements are
    equivalent.

    * $U_1 + \cdots + U_n$ is a direct sum.

    * $u_1 + \cdots + u_n = 0$ with $u_i \in U_i$ for all $i$ implies that
      $u_i = 0$ for all $i$.

  * (Lemma) __Direct Sum of Two Subspaces__. Let $U$ and $W$ be subspaces of
    a vector space $V$. $U + W$ is a direct sum if and only if
    $U \cap W = \{0\}$.

    * _Proof_. ($\Rightarrow$) Let $v \in \ U \cap W$. Observe that
      $v + (-v) \in U + W$ and $v + (-v) = 0$. Since $U + W$ is a direct sum,
      the previous theorem implies that $v = 0 = -v$. Therefore,
      $U \cap W = \{0\}$.

      ($\Leftarrow$) Let $u \in U$ and $w \in W$ such that $u + w = 0$. Then
      $u = -w$, which implies that $u, w \in U \cap W$. Therefore, $u = 0 = w$.
      Since this holds for all $u \in U$ and $w \in W$, the previous theorem
      implies that $U + W$ is a direct sum.

  * (Remark) A direct sum of subspaces for vector spaces is analogous to a
    union of disjoint sets in set theory.

-------------------------------------------------------------------------------

## 2. Finite-Dimensional Vector Spaces

__Key Concepts__

* span

* linear independence

* bases

* dimension

### 2.1. Span and Linear Independence

* (Definition) __Linear Combination__. A linear combination of a set of vectors
  $v_1, \ldots, v_n \in V$ over a field $F$ is a sum of the form

  \[
    a_1 v_1 + \cdots + a_n v_n,
  \]

  where $a_1, \ldots, a_n \in F$.

* (Definition) __Span__. The span of a set of vectors $v_1, \ldots, v_n \in V$
  is the set of all linear combinations of the set of vectors.

  \[
    \operatorname{span}(v_1, \ldots, v_n) =
      \{ a_1 v_1 + \cdots + a_n v_n | a_1, \ldots, a_n \in F \}
  \]

  * _Edge Case_: the span of the empty set is $\{ 0 \}$.

* (Lemma) __Smallest Subspace Containing $v_1, \ldots v_n$__.
  $\operatorname{span}(v_1, \ldots, v_n)$ possesses the following properties.

  * $\operatorname{span}(v_1, \ldots, v_n)$ is a subspace.

  * $\operatorname{span}(v_1, \ldots, v_n)$ is the smallest subspace
    containing $v_1, \ldots, v_n$.

* (Definition) __Linear Independence__. Vectors $v_1, \ldots, v_n \in V$
  are linearly independent when

  \[
    a_1 v_1 + \cdots + a_n v_n = 0
    \Longleftrightarrow
    a_i = 0 \textrm{ for all } i.
  \]

  * _Edge Case_: an empty set of vectors is linearly independent.

  * _Linearly Dependence_. A set of vectors that is not linearly independent
    is _linearly dependent_.

* (Lemma) __Linear Dependence Lemma__. If $v_1, \ldots, v_n \in V$ is a set
  of linearly dependent vectors, there exists $j \in \{1, \ldots, n\}$ such
  that

  * $v_j \in \operatorname{span}(v_1, \ldots, v_{j-1})$

  * if $v_j$ is removed from the $v_1, \ldots, v_n$, the span of the
    remaining list of vectors is equal to
    $\operatorname{span}(v_1, \ldots, v_n)$.

* (Lemma) __|Linearly Independent Set| $\le$ |Spanning Set|__. For a
  finite-dimensional vector space, the size of every linearly independent
  set of vectors is less than or equal to the size of every spanning set
  of vectors.

### 2.2. Basis

* (Definition) __Basis__. A set of vectors $v_1, \ldots, v_n \in V$ is a
  _basis_ for $V$ if (1) it is linearly independent and (2) it spans $V$.

* (Lemma) __Unique Expansion Property for a Basis__. A set of vectors
  $v_1, \ldots, v_n \in V$ is a basis for $V$ if and only if every $v \in V$
  can be expressed as a unique linear combination of $v_1, \ldots, v_n$.

* (Lemma) __Spanning Sets Contain a Basis__. Every spanning set of vectors in
  a vector space $V$ contains a basis for $V$.

  * (Corollary) Every finite-dimensional vector space has a basis.

* (Lemma) __Linearly Independent Sets Can be Extended to a Basis__. Every
  linearly independent set of vectors in a vector space $V$ can be extended to
  a basis for $V$.

* (Lemma) Every subspace $U$ of a vector space $V$ is part of a direct sum
  equal to $V$.

  * _Sketch of proof for finite-dimensional vector spaces_. Let $U$ be subspace
    of $V$. $U$ is finite-dimensional, so it has a basis. Extend the basis for
    $U$ to a basis for $V$. The vectors used to extend the basis for $U$ form
    a basis for a subspace $W$. It is straightforward to show that
    $U \oplus W = V$.

  * (Remark) This result can be proven for infinite-dimensional vector spaces
    using more advanced mathematical machinery.

### 2.3. Dimension

* (Lemma) __All bases for $V$ have the same number of vectors__. Every basis
  for a finite-dimensional vector space $V$ contains the same number of
  vectors.

* (Definition) __Dimension__. The _dimension_ of a vector space $V$ is the
  number of vectors in any basis.

* (Lemma) __Bound on Dimension of Subspace__. If $U$ is a subspace of a
  finite-dimensional vector space $V$, $\dim U \le \dim V$.

* (Lemma) __Criteria for a Basis__. Let $V$ be a finite-dimensional vector
  space.

  * Any linearly independent set of vectors containing $\dim V$ vectors is a
    basis.

  * Any spanning set of vectors containing $\dim V$ vectors is a basis.

* (Lemma) __Dimension of Sum of Subspaces__. If $U_1$ and $U_2$ be subspaces
  of a finite-dimensional vector space,

  \[
    \dim (U_1 + U_2) = \dim U_1 + \dim U_2 - \dim (U_1 \cap U_2)
  \]

-------------------------------------------------------------------------------

## 3. Finite-Dimensional Vector Spaces

__Key Concepts__

* Fundamental Theorem of Linear Maps

* matrix representation of a linear map

* isomorphic vector spaces

* product spaces

* quotient spaces

* dual spaces

### 3.1. Linear Maps

* (Definition) __Linear Map__. A linear map from $V$ to $W$ is a function
  $T: V \rightarrow W$ with the following properties.

  * _Addivity_: $T(u + v) = Tu + Tv$ for all $u, v \in V$

  * _Homogeneity_: $T(\lambda v) = \lambda (Tv)$ for all $v \in V$ and
    $\lambda \in F$.

* (Lemma) __Vector Space of Linear Maps__. The set of all linear maps from $V$
  to $W$ is a vector space. It is denoted $\mathcal{L}(V, W)$.

* (Lemma) __Linear Maps are Uniquely Defined by Images of Basis Vectors__.
  Let $v_1, \ldots, v_n$ be a basis for $V$ and $w_1, \ldots, w_n \in W$.
  There exists a unique linear map $T: V \rightarrow W$ such that $T v_j = w_j$
  for all $j$.

* (Definition) __Product of Linear Maps__. Let $T \in \mathcal{L}(U, V)$ and
  $S \in \mathcal{L}(V, W)$. The _product_ $ST$ is defined by $(ST)(u) = S(Tu)$

  * (Remark) For the product of two linear maps to be well-defined, the
    codomain of the first map must be the same as the domain of the second map.

  * (Lemma) $ST$ is an element of $\mathcal{L}(U, W)$.

  * (Remark) The product of linear maps posesses the following algebraic
    properties. Note: taken together with additive properties of linear maps,
    these multiplicative properties imply that the space of linear maps has a
    _ring_ structure.

    * _Associativity_: $(T_1 T_2) T_3 = T_1 (T_2 T_3)$ whenever the product
      is well-defined (i.e., domains and codomains are compatible).

    * _Identity_: $TI = IT = T$ where $I$ is the identity map (defined on
      the appropriate vector space depending on where $I$ appears in the
      equation).

    * _Distributive Properties_

      \[
      (S_1 + S_2) T = S_1 T + S_2 T \\
      S (T_1 + T_2) = S T_1 + S T_2,
      \]

      where $S, S_1, S_2 \in \mathcal{L}(V, W)$ and
      $T, T_1, T_2 \in \mathcal{L}(U, V)$.

### 3.2. Null Spaces and Ranges

* (Definition) __Null Space__. The _null space_ of a linear map
  $T \in \mathcal{L}(V, W)$ is the set of vectors $v \in V$ that map to 0:

  \[
    \operatorname{null} T = \{v \in V | Tv = 0\}
  \]

* (Definition) __Range__. The _range_ of a linear map $T \in \mathcal{L}(V, W)$
  is the set of vectors $w \in W$ that are mapped to by some $v \in V$:

  \[
    \operatorname{range} T = \{Tv | v \in V \}
  \]

* (Definition) __Injective__. A function $T: V \rightarrow W$ is _injective_
  if $T(u) = T(v)$ implies that $u = v$.

* (Definition) __Surjective__. A function $T: V \rightarrow W$ is _surjective_
  if its range equals $W$.

* (Lemma) __Null Space and Range are Subspaces__.

  * The null space of a linear map is a subspace of $V$.

  * The range of a linear map is a subspace of $W$.

* (Lemma) __Null Space of Injective Linear Maps is $\{0\}$__. A linear map is
  injective if and only if $\operatorname{null} T = \{ 0 \}$.

* (Theorem) __Fundamental Theorem of Linear Maps__.

  If $V$ be a finite-dimensional vector space and $T \in \mathcal{L}(V, W)$,

  \[
    \dim V = \dim \operatorname{null} T + \dim \operatorname{range} T
  \]

  * (Corollary) If $\dim V > \dim W$, $T$ is not injective.

    * (Application) A homogeneous system of linear equations has more than one
      solution if there are more variables than equations.

  * (Corollary) If $\dim V < \dim W$, $T$ is not surjective.

    * (Application) An inhomogeneous system of linear equations has no solution
      for some constant terms if there are more equations than variables.

### 3.3. Matrix Representations

* (Definition) __Matrix__. An _$m \times n$ matrix_ is a rectangular array
  of elements of a field $F$ with $m$ rows and $n$ columns:

  \[
    A =
      \left[ \begin{array}{ccc}
        A_{1,1} & \cdots & A_{1,n} \\
          \vdots &        &   \vdots \\
        A_{m,1} & \cdots & A_{m,n}
      \end{array} \right]
  \]

  * (Notation) $F^{m,n}$ (with $m, n$ positive) denotes the set of all
    $m \times n$ matrices with entries in $F$.

  * (Lemma) $F^{m,n}$ is a vector space with dimension $mn$.

* (Definition) __Matrix of a Linear Map__. Let $T \in \mathcal{L}(V, W)$,
  $\{v_1, \ldots, v_n\}$ be a basis for $V$, and $\{w_1, \ldots, w_m\}$ be a
  basis for $W$. The _matrix representation_ of $T$ with respect to these bases
  is the $m \times n$ matrix $\mathcal{M}(T)$ with entries $A_{i,j}$ defined
  by

  \[
    T v_j
    = A_{1,j} w_1 + \cdots + A_{m,j} w_m
    = \sum_{i=1}^m A_{i,j} w_i
  \]

* (Definition) __Matrix Product__. Let $A$ be an $m \times n$ matrix and $B$
  be an $n \times p$ matrix. The matrix product $AC$ is defined to be the
  $m \times p$ matrix with entries given by

  \[
    (AC)_{i,j} = \sum_{k=1}^n A_{i,k} C_{k,j}.
  \]

* (Lemma) __Equivalence of Matrix and Linear Map Operations__. With appropriate
  choices for the definition of matrix addition, scalar multiplication for
  matrices, and matrix multiplication, the matrix representation of the result
  of an operation on linear maps is equal to the equivalent operation applied
  to the matrix representations of the linear maps.

  * _Sums of linear maps_:
      $\mathcal{M}(S + T) = \mathcal{M}(S) + \mathcal{M}(T)$

  * _Scalar multiplication of linear maps_:
      $\mathcal{M}(\lambda S) = \lambda \mathcal{M}(S)$

  * _Product of linear maps_:
      $\mathcal{M}(ST) = \mathcal{M}(S) \mathcal{M}(T)$

* (Lemma) __Expressions for Matrix Product Entries__

  * _Dot Product of Row and Column_. $(AC)_{i,j}$ is equal to the dot product
    of the $i$-th row of $A$ with the $j$-th column of $C$.

  * _Matrix Product with Column_. The $j$-th column of $AC$ is equal to the
    matrix product of the matrix $A$ with the $j$-th column of $C$.

  * _Matrix Product with Row_. The $i$-th row of $AC$ is equal to the
    matrix product of the $i$-th row of $A$ with the matrix $C$.

  * _Linear Combination of Columns_. The $j$-th column of $AC$ is equal to
    the linear combination of the columns of $A$ with the $j$-th column of
    $C$ as the coefficients in the linear combination.

  * _Linear Combination of Rows_. The $i$-th row of $AC$ is equal to
    the linear combination of the rows of $C$ with the $i$-th row of
    $A$ as the coefficients in the linear combination.

-------------------------------------------------------------------------------
