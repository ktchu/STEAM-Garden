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
