High-Dimensional Probability (Vershynin): Exercises - Chapter 0
===============================================================

-------------------------------------------------------------------------------

### 0.0.3.

Check the following variance identities.

#### 0.0.3.a.

__Problem__. Let $Z_1, \ldots, Z_k$ be independent mean-zero random vectors
in $\mathbb{R}^n$. Show that

\[
\mathbb{E} \left\Vert \sum_{j=1}^k Z_j \right\Vert_2^2
= \sum_{j=1}^k \mathbb{E} \left\Vert Z_j \right\Vert_2^2
\]

__Solution__. Expressing the square of the norm as a dot product, we observe
that

\[
\left\Vert \sum_{j=1}^k Z_j \right\Vert_2^2
= \left( \sum_{j=1}^k Z_j \right) \cdot \left( \sum_{j=1}^k Z_j \right)
= \sum_{j=1}^k \left\Vert Z_j \right\Vert_2^2
  + \sum_{i,j = 1, i \ne j}^k Z_j \cdot Z_i
\]

Therefore, taking expectations yields

\[
\mathbb{E} \left\Vert \sum_{j=1}^k Z_j \right\Vert_2^2
= \mathbb{E} \left(
    \sum_{j=1}^k \left\Vert Z_j \right\Vert_2^2
  + \sum_{i,j = 1, i \ne j}^k Z_j \cdot Z_i
  \right)
= \sum_{j=1}^k \mathbb{E} \left\Vert Z_j \right\Vert_2^2
  + \sum_{i,j = 1, i \ne j}^k \mathbb{E} \left( Z_j \cdot Z_i \right)
= \sum_{j=1}^k \mathbb{E} \left\Vert Z_j \right\Vert_2^2
\]

where the second equality follows from the linearity of expectation and the
last equality follows from

\[
\mathbb{E} \left( Z_i \cdot Z_j \right)
= \mathbb{E} Z_i \cdot \mathbb{E} Z_j
= 0 \cdot 0 = 0.
\]

when $Z_i$ and $Z_j$ are independent.

#### 0.0.3.b.

__Problem__. Let $Z$ be a random vector in $\mathbb{R}^n$. Show that

\[
\mathbb{E} \left\Vert Z - \mathbb{E} Z \right\Vert_2^2
= \mathbb{E} \left\Vert Z \right\Vert_2^2
- \left\Vert \mathbb{E} Z \right\Vert_2^2
\]

__Solution__. Expressing the square of the norm as a dot product, we observe
that

\[
\left\Vert Z - \mathbb{E} Z \right\Vert_2^2
= \left( Z - \mathbb{E} Z \right) \cdot \left( Z - \mathbb{E} Z \right)
= \left\Vert Z \right\Vert_2^2
  - 2 Z \cdot \mathbb{E} Z + \left\Vert \mathbb{E} Z \right\Vert_2^2
\]

Therefore, taking expectations yields

\[
\mathbb{E} \left\Vert Z - \mathbb{E} Z \right\Vert_2^2
= \mathbb{E} \left\Vert Z \right\Vert_2^2
  - 2 \mathbb{E} \left( Z \cdot \mathbb{E} Z \right)
  + \left\Vert \mathbb{E} Z \right\Vert_2^2
= \mathbb{E} \left\Vert Z \right\Vert_2^2
  - 2 \mathbb{E} Z \cdot \mathbb{E} Z
  + \left\Vert \mathbb{E} Z \right\Vert_2^2 \\
= \mathbb{E} \left\Vert Z \right\Vert_2^2
  - 2 \left\Vert \mathbb{E} Z \right\Vert_2^2
  + \left\Vert \mathbb{E} Z \right\Vert_2^2
= \mathbb{E} \left\Vert Z \right\Vert_2^2
  - \left\Vert \mathbb{E} Z \right\Vert_2^2.
\]

-------------------------------------------------------------------------------
### 0.0.5. The sum of binomial coefficients

__Problem__. Prove the inequalities.

\[
\left( \frac{n}{m} \right)^m
\le {n \choose m}
\le \sum_{k=0}^m {n \choose k}
\le \left( \frac{e n}{m} \right)^m
\]

__Solution__. To prove the first inequality, observe that for $m < n$ and
$0 \le j < m$,

\[
\left( \frac{n}{m} \right) \le \left( \frac{n - j}{m - j} \right).
\]

Therefore,

\[
\left( \frac{n}{m} \right)^m
= \prod_{j=0}^{m-1} \left( \frac{n}{m} \right)
\le \prod_{j=0}^{m-1} \left( \frac{n - j}{m - j} \right)
= {n \choose m}
\]

The second inequality follows because $n \choose m$ is the last term in the
sum and all of the terms in the sum are positive.

To prove the final inequality, observe that

\[
{n \choose k}
= \frac{1}{k!} \prod_{j=0}^{k-1} (n - j)
\le \frac{n^k}{k!}
= \left( \frac{n}{m} \right)^k \left( \frac{m^k}{k!} \right)
\le \left( \frac{n}{m} \right)^m \left( \frac{m^k}{k!} \right),
\]

which implies that

\[
\sum_{k=0}^m {n \choose k}
\le \left( \frac{n}{m} \right)^m \sum_{k=0}^m \left( \frac{m^k}{k!} \right)
< \left( \frac{n}{m} \right)^m \sum_{k=0}^\infty \left( \frac{m^k}{k!} \right)
= \left( \frac{n}{m} \right)^m e^m
= \left( \frac{en}{m} \right)^m.
\]

-------------------------------------------------------------------------------
### 0.0.6. Improved covering

__Problem__. Check that, in Corollary 0.0.4,

\[
( C + C \epsilon^2 N)^{\lceil 1 / \epsilon^2 \rceil}
\]

Euclidean balls suffice. Here $C$ is a suitable absolute constant. (Note that
this bound is slightly stronger than $N^{\lceil 1 / \epsilon^2 \rceil}$ for
small $\epsilon$.)

__Solution__. TODO

-------------------------------------------------------------------------------
