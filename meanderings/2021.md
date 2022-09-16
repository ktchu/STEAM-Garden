Mathematics (2021)
==================

*Author(s)*: Kevin Chu `<kevin@velexi.com>`

-------------------------------------------------------------------------------

2021-04-12: Multivariate Gaussian Random Variables
--------------------------------------------------

An $n$-dimensional multivariate Gaussian random variable $x$ is defined the
joint probability density

$$
  p(x) = \frac{1}{(2 \pi)^{n/2} |\Sigma|^{1/2}}
         \exp \left( -\frac{1}{2} (x - m)^T \Sigma^{-1} (x - m) \right)
$$

where $m$ and $\Sigma$ are the mean vector and covariance matrix of the
distribution. We use the notation $x \sim \mathcal{N}(m, \Sigma)$ to indicate
that a random variable has a multivariate Gaussian distribution with mean $m$
and covariance $\Sigma$.

### Properties of Multi-dimensional Gaussian Functions

A multi-dimensional Gausian function centered at $m$ is a function of the form

$$
  A \exp(-(x - m)^T C (x - m))
$$

where $A$ is the prefactor and $C$ is a positive definite matrix. Note that
$C$ positive definite implies that $C$ is symmetric.

#### Integral of Multi-dimensional Gaussian Functions

* _Unshifted Gaussian_

$$
  \int_{\mathbb{R}^n} \exp(-x^T C x) dx = \sqrt{\frac{\pi^n}{|C|}}
$$

_Proof_. Since $C$ is positive definite, the Cholesky decomposition can be used
to express it as $C = LL^T$ where $L$ is a lower triangular matrix. Using the
change of variables $y = L (x - m)$, we find that

$$
  \int_{\mathbb{R}^n} \exp(-x^T C x) dx
  = \int_{\mathbb{R}^n} \exp(-y^T y) |L^{-1}| dy
  = \frac{1}{|L|}
    \int_{\mathbb{R}^n} \exp \left( -\sum_{i=1}^n y_i^2 \right) dy \\
  = \frac{1}{|L|} \prod_{i=1}^n \int_\mathbb{R} e^{-y_i^2} dy
  = \sqrt{\frac{\pi^n}{|C|}}
$$

where the last step follows because $|C| = |L||L^T| = |L|^2$ and
$\int_\mathbb{R} e^{-z^2} dz = \sqrt{\pi}$.

* _Shifted Gaussian_

$$
  \int_{\mathbb{R}^n} \exp(-x^T C x + v^T x) dx
  = \sqrt{\frac{\pi^n}{|C|}} \exp \left( \frac{1}{4} v^T C^{-1} v \right)
$$

_Proof_. By completing the square, we can express the exponent as

$$
  -x^T C x + v^T x
  =  -(x - \frac{1}{2} C^{-1} v)^T C (x - \frac{1}{2} C^{-1} v)
    + \frac{1}{4} v^T C^{-1} v
$$

Therefore, the integral of a shifted Gaussian is the product of the integral
for an unshifted Gaussian and $\exp(v^T C^{-1} v/4)$, as desired.

#### Products of Multi-dimensional Gaussian Functions are Gaussian

Let $f(x)$ and $g(x)$ be Gaussian functions with positive definite matrices
$C_f$ and $C_g$, respectively, centers at $m_f$ and $m_g$, respectively, and
unit prefactor. Then, $f(x) g(x)$ is a Gaussian with positive definite matrix

$$
  C = C_f + C_g,
$$

center

$$
  m = C^{-1} \left( C_f m_f + C_g m_g \right),
$$

and prefactor equal to

$$
  \exp\left(
    -\frac{1}{2} (m_f - m_g)^T (C_f^{-1} + C_g^{-1})^{-1} (m_f - m_g)
  \right).
$$

_Commentary_

* The positive definite matrix of the product is simple sum of the individual
  positive definite matrices.

* The mean of the product is a weighted sum of the individual means.

* The prefactor is also a Gaussian function if either $m_f$ or $m_g$
  is interpreted as a variable.

_Proof_. The product $f(x) g(x)$ is an exponential with exponent equal to

$$
  -\frac{1}{2} (x - m_f)^T C_f (x - m_f)
  -\frac{1}{2} (x - m_g)^T C_g (x - m_g) \\
  = -\frac{1}{2} \left(
        x^T (C_f + C_g) x - 2 x^T (C_f m_f + C_g m_g)
      + (m_f^T C_f m_f + m_g^T C_g m_g)
    \right) \\
  = -\frac{1}{2} \left(
        (x - m)^T C (x - m)
      + (m_f^T C_f m_f + m_g^T C_g m_g - m^T C m)
    \right)
$$

where $C = C_f + C_g$ and $m = C^{-1} (C_f m_f + C_g m_g)$. Using the matrix
inverse formulas

$$
  C^{-1} = (C_f + C_g)^{-1}
  = C_f^{-1} - C_f^{-1} (C_f^{-1} + C_g^{-1})^{-1} C_f^{-1}
  = C_g^{-1} - C_g^{-1} (C_f^{-1} + C_g^{-1})^{-1} C_g^{-1},
$$

the $m^T C m$ term in the exponent can be expressed as

$$
  (m_f^T C_f + m_g^T C_g) C^{-1} C C^{-1} (C_f m_f + C_g m_g) \\
  = (m_f^T C_f + m_g^T C_g) C^{-1} (C_f m_f + C_g m_g) \\
  =   m_f^T C_f C^{-1} C_f m_f + m_g^T C_g C^{-1} C_g m_g
    + m_f^T C_f C^{-1} C_g m_g + m_g^T C_g C^{-1} C_f m_f \\
  =   m_f^T C_f C^{-1} C_f m_f + m_g^T C_g C^{-1} C_g m_g
    + 2 m_f^T C_f C^{-1} C_g m_g \\
  =   m_f^T C_f m_f - m_f^T (C_f^{-1} + C_g^{-1})^{-1} m_f
    + m_g^T C_g m_g - m_g^T (C_f^{-1} + C_g^{-1})^{-1} m_g
    + 2 m_f^T C_f C^{-1} C_g m_g.
$$

Combining this with the other constant terms in the exponent, we find that

$$
  m_f^T C_f m_f + m_g^T C_g m_g - m^T C m \\
  =   m_f^T (C_f^{-1} + C_g^{-1})^{-1} m_f
    + m_g^T (C_f^{-1} + C_g^{-1})^{-1} m_g
    - 2 m_f^T C_f C^{-1} C_g m_g \\
  =   (m_f - m_g)^T (C_f^{-1} + C_g^{-1})^{-1} (m_f - m_g)
    + 2 m_f^T (C_f^{-1} + C_g^{-1})^{-1} m_g
    - 2 m_f^T C_f C^{-1} C_g m_g \\
  =   (m_f - m_g)^T (C_f^{-1} + C_g^{-1})^{-1} (m_f - m_g),
$$

where the last equality follows because rearrangement of the matrix inverse
formula $C^{-1} = C_f^{-1} - C_f^{-1} (C_f^{-1} + C_g^{-1})^{-1} C_f^{-1}$
yields

$$
  (C_f^{-1} + C_g^{-1})^{-1} - C_f C^{-1} C_g \\
  =   (C_f^{-1} + C_g^{-1})^{-1}
    - C_g + (C_f^{-1} + C_g^{-1})^{-1} C_f^{-1} C_g \\
  = (C_f^{-1} + C_g^{-1})^{-1} \left(
    I - (C_f^{-1} + C_g^{-1}) C_g + C_f^{-1} C_g
    \right) \\
  = (C_f^{-1} + C_g^{-1})^{-1} \left(
    I - C_f^{-1} C_g - I + C_f^{-1} C_g
    \right)
  = 0.
$$

Combining all these results, we arrive at the desired conclusion:

$$
  f(x) g(x)
  = \exp\left(
      -\frac{1}{2} (m_f - m_g)^T (C_f^{-1} + C_g^{-1})^{-1} (m_f - m_g)
    \right)
    \exp\left( -\frac{1}{2} (x - m)^T C (x - m) \right)
$$

with $C = C_f + C_g$ and $m = C^{-1} (C_f m_f + C_g m_g)$.

### Properties of Multivariate Gaussian Random Variables

Let $x$ and $y$ be jointly multivariate Gaussian random variables. Then the
distribution of $[x; y]$ (vertical concatenation of the vectors $x$ and $y$)
is

$$
  \left[ \begin{array}{c}
      x \\
      y
  \end{array} \right]
  \sim \mathcal{N}\left(
    \left[ \begin{array}{c}
        m_x \\
        m_y
    \end{array} \right],
    \left[ \begin{array}{cc}
        \Sigma_{xx} & \Sigma_{xy} \\
        \Sigma_{yx} & \Sigma_{yy}
    \end{array} \right]
  \right)
  = \mathcal{N}\left(
    \left[ \begin{array}{c}
        m_x \\
        m_y
    \end{array} \right],
    \left[ \begin{array}{cc}
        \Omega_{xx} & \Omega_{xy} \\
        \Omega_{yx} & \Omega_{yy}
    \end{array} \right]^{-1}
  \right),
$$

where $\Sigma_{yx} = \Sigma_{xy}^T$ because the covariance matrices must be
symmetric.

#### Marginal Distribution

The marginal distribution of $x$ is $\mathcal{N}(m_x, \Sigma_{xx})$.

_Proof_. Expanding the matrix product in the exponential of the Gaussian
for $[x; y]$ in terms of the $\Omega$s, we find that

$$
  -\frac{1}{2} [x - m_x; y - m_y] ^T \Sigma^{-1} [x - m_x; y - m_y] \\
  = -\frac{1}{2} (x - m_x)^T \Omega_{xx} (x - m_x)
    -(x - m_x)^T \Omega_{xy} (y - m_y)
    -\frac{1}{2} (y - m_y)^T \Omega_{yy} (y - m_y)
$$

To compute the marginal distribution of $x$, we integrate the probability
density function for $[x; y]$ over $y$. To simplify the calculation, we
shift $y$ so that its mean is located at 0:

$$
  - \frac{1}{2} [x - m_x; y] ^T \Sigma^{-1} [x - m_x; y] \\
  = -\frac{1}{2} (x - m_x)^T \Omega_{xx} (x - m_x)
    -(x - m_x)^T \Omega_{xy} y
    -\frac{1}{2} y^T \Omega_{yy} y
$$

Using the formula for the integral of a shifted Gaussian, we find that
$x \sim \mathcal{N}(m_x, \Sigma_{xx})$ as desired:

$$
  p(x)
  = \frac{1}{(2 \pi)^{n/2} |\Sigma|^{1/2}}
       \frac{(2 \pi)^{n_y/2}}{|\Omega_{yy}|^{1/2}}
       \exp \left( -\frac{1}{2} (x - m_x)^T \Omega_{xx} (x - m_x) \right)
       \exp \left( \frac{1}{2}
          (x - m_x)^T \Omega_{xy} \Omega_{yy}^{-1} \Omega_{xy}^T (x - m_x)
       \right) \\
  = \frac{ (2 \pi)^{n_y/2} }{ (2 \pi)^{n/2} |\Sigma|^{1/2} |\Omega_{yy}|^{1/2} }
       \exp \left(
          -\frac{1}{2} (x - m_x)^T
          (\Omega_{xx} - \Omega_{xy} \Omega_{yy}^{-1} \Omega_{xy}^T)
          (x - m_x)
       \right) \\
  = \frac{1}{(2 \pi)^{n_x/2} |\Sigma_{xx}|^{1/2}}
       \exp \left(
          -\frac{1}{2} (x - m_x)^T \Sigma_{xx}^{-1} (x - m_x)
       \right)
$$

where the last equation follows from matrix inversion formulas for 2x2 block
matrices

$$
  \Sigma_{xx}
    = (\Omega_{xx} - \Omega_{xy} \Omega_{yy}^{-1} \Omega_{xy}^T)^{-1}
$$

and determinant formulas for 2x2 block matrices

$$
  |\Sigma|^{-1}
  = \left| \begin{array}{cc}
         \Omega_{xx} & \Omega_{xy} \\
         \Omega_{yx} & \Omega_{yy}
       \end{array}
  \right|
  = \left| \Omega_{xx} - \Omega_{xy} \Omega_{yy}^{-1} \Omega_{yx} \right|
         |\Omega_{yy}|
  = |\Sigma_{xx}^{-1}| |\Omega_{yy}|
  = \frac{ |\Omega_{yy}| }{ |\Sigma_{xx}| }.
$$

#### Conditional Distribution

The conditional distribution of $x$ given $y$ is

$$
  \mathcal{N} \left(
      m_x + \Sigma_{xy} \Sigma_{yy}^{-1} (y - m_y),
      \Sigma_{xx} - \Sigma_{xy} \Sigma_{yy}^{-1} \Sigma_{yx}
  \right)
  =
  \mathcal{N} \left(
      m_x - \Omega_{xx}^{-1} \Omega_{xy} (y - m_y),
      \Omega_{xx}^{-1}
  \right)
$$

_Proof_. The conditional distribution of $x$ given $y$ is equal to the joint
probability density $p(x, y)$ divided by the marginal probability density
$p(y)$. The exponent of this quotient is equal to

$$
     -\frac{1}{2} [x - m_x; y - m_y] ^T \Sigma^{-1} [x - m_x; y - m_y]
    + \frac{1}{2} (y - m_y) ^T \Sigma_{yy}^{-1} (y - m_y) \\
  = - \frac{1}{2} (x - m_x)^T \Omega_{xx} (x - m_x)
    - (x - m_x)^T \Omega_{xy} (y - m_y)
    - \frac{1}{2} (y - m_y)^T \Omega_{yy} (y - m_y) \\
    + \frac{1}{2} (y - m_y) ^T \Sigma_{yy}^{-1} (y - m_y) \\
  =  -\frac{1}{2} (x - m_x)^T \Omega_{xx} (x - m_x)
    - (x - m_x)^T \Omega_{xy} (y - m_y)
    - \frac{1}{2} (y - m_y)^T \Omega_{yy} (y - m_y) \\
    + \frac{1}{2}
        (y - m_y)^T
        (\Omega_{yy} - \Omega_{yx} \Omega_{xx}^{-1} \Omega_{xy})
        (y - m_y) \\
  =  -\frac{1}{2} (x - m_x)^T \Omega_{xx} (x - m_x)
    - (x - m_x)^T \Omega_{xy} (y - m_y)
    - \frac{1}{2}
        (y - m_y)^T \Omega_{yx} \Omega_{xx}^{-1} \Omega_{xy} (y - m_y) \\
  =  -\frac{1}{2} (x - m)^T \Omega_{xx} (x - m)
    + \frac{1}{2} \left(
          (y - m_y)^T \Omega_{yx} \Omega_{xx}^{-1} \Omega_{xy} (y - m_y)
        - (y - m_y)^T \Omega_{yx} \Omega_{xx}^{-1} \Omega_{xy} (y - m_y)
      \right) \\
  =  -\frac{1}{2} (x - m)^T \Omega_{xx} (x - m)
$$

where $m = m_x - \Omega_{xx}^{-1} \Omega_{xy} (y - m_y)$. The prefactor for
the exponential is equal to

$$
  \frac{1}{(2 \pi)^{n/2} |\Sigma|^{1/2}} (2 \pi)^{n_y/2} |\Sigma_{yy}|^{1/2}
  = \frac{1}{(2 \pi)^{n_x/2}} |\Omega_{xx}|^{1/2}
  = \frac{1}{(2 \pi)^{n_x/2} |\Omega_{xx}^{-1}|^{1/2}}
$$

where the second equality follows from determinant formulas for 2x2 block
matrices

$$
  |\Sigma|^{-1}
  = \left| \begin{array}{cc}
         \Omega_{xx} & \Omega_{xy} \\
         \Omega_{yx} & \Omega_{yy}
       \end{array}
  \right|
  = |\Omega_{xx}|
    \left| \Omega_{yy} - \Omega_{yx} \Omega_{xx}^{-1} \Omega_{xy} \right|
  = |\Omega_{xx}| |\Sigma_{yy}^{-1}|
  = \frac{ |\Omega_{xx}| }{ |\Sigma_{yy}| }.
$$

Combining these results we find that the conditional probability density of $x$
given $y$ is

$$

  p(x|y)
  = \frac{1}{(2 \pi)^{n_x/2} |\Omega_{xx}^{-1}|^{1/2}}
    \exp \left( -\frac{1}{2} (x - m)^T \Omega_{xx} (x - m) \right)
$$

which is the probability density for the multivariate Gaussian distribution

$$
  \mathcal{N} \left(
      m_x - \Omega_{xx}^{-1} \Omega_{xy} (y - m_y),
      \Omega_{xx}^{-1}
  \right).
$$

Matrix inversion formulas for 2x2 block matrices yield the equivalent
distribution

$$
  \mathcal{N} \left(
      m_x + \Sigma_{xy} \Sigma_{yy}^{-1} (y - m_y),
      \Sigma_{xx} - \Sigma_{xy} \Sigma_{yy}^{-1} \Sigma_{yx}
  \right).
$$

-------------------------------------------------------------------------------

2021-04-12: Properties of Matrix Determinant
--------------------------------------------

### Formulas for Block Matrices

#### 2x2 Triangular Block Matrices

$$
  \det \left( \begin{array}{cc}
    A & 0 \\
    C & D
  \end{array} \right)
  = \det(A) \det(D)
  = \det \left( \begin{array}{cc}
    A & B \\
    0 & D
  \end{array} \right)
$$

_Proof_. Observe that an lower triagular block matrix can be decomposed as

$$
  \left( \begin{array}{cc}
    A & 0 \\
    C & D
  \end{array} \right)
  = \left( \begin{array}{cc}
    A & 0 \\
    C & I
  \end{array} \right)
  \left( \begin{array}{cc}
    I & 0 \\
    0 & D
  \end{array} \right)
$$

The result for upper triangular block matrices follows because the determinants
of the matrices on the right-hand side are $\det(A)$ and $\det(D)$,
respectively. The result for lower triangular matrices is analogous.

#### 2x2 Block Matrices

If $A$ is invertible, then

$$
  \det \left( \begin{array}{cc}
    A & B \\
    C & D
  \end{array} \right)
  = \det(A) \det(D - C A^{-1} B)
$$

If $D$ is invertible, then

$$
  \det \left( \begin{array}{cc}
    A & B \\
    C & D
  \end{array} \right)
  = \det(A - B D^{-1} C) \det(D)
$$

_Proof_. When $A$ is invertible, observe that a 2x2 block matrix can be
decomposed as

$$
  \left( \begin{array}{cc}
    A & B \\
    C & D
  \end{array} \right)
  = \left( \begin{array}{cc}
    A & 0 \\
    C & I
  \end{array} \right)
  \left( \begin{array}{cc}
    I & A^{-1} B \\
    0 & D - C A^{-1} B
  \end{array} \right)
$$

The result follows because the determinants of the matrices on the right-hand
side are $\det(A)$ and $\det(D - C A^{-1} B)$, respectively.

The result for $D$ invertible is analogous and follows from the decomposition

$$
  \left( \begin{array}{cc}
    A & B \\
    C & D
  \end{array} \right)
  = \left( \begin{array}{cc}
    A - B D^{-1} C & B D^{-1} \\
    0 & I
  \end{array} \right)
  \left( \begin{array}{cc}
    I & 0 \\
    C & D
  \end{array} \right).
$$

### Bounds

* For positive definite matrices,

  $$
    tr(I - A^{-1}) \le \log \det(A) \le tr(I - A)
  $$

  with equality if and only if $A = I$.

* For positive definite matrices,

  $$
    \frac{n}{tr(A^{-1})}
    \le \det(A)^{1/n}
    \le \frac{1}{n} tr(A)
    \le \sqrt{\frac{1}{n} tr(A^2)}.
  $$

  These inequalities follow from the relationship between the harmonic mean,
  geometric mean, arithmetic mean, and root mean square:

  $$
    HM \le GM \le AM \le RMS
  $$

### References

* [Wikipedia: Determinant][wikipedia-determinant]

[------------------------- REFERENCES 2021-04-12 -------------------------]: #

[wikipedia-determinant]: https://en.wikipedia.org/wiki/Determinant

-------------------------------------------------------------------------------

2021-04-11: Matrix Inversion Formulas
-------------------------------------

_Last Updated_: 2021-04-12

### Matrix Inverse Formulas for 2x2 Block Matrices

Let $M$ be an invertible matrix expressed in 2x2 block form as

$$
  \left(\begin{array}{cc}
    A & B \\
    C & D
  \end{array}\right).
$$

Let $M^{-1}$ be expressed in 2x2 block form as

$$
  \left(\begin{array}{cc}
    W & X \\
    Y & Z
  \end{array}\right)
$$

Then $W$, $X$, $Y$, and $Z$ can be explicitly computed as

$$
  W = (A - B D^{-1} C)^{-1} \\
  X = -A^{-1} B Z = - W B D^{-1} \\
  Y= -Z C A^{-1} = - D^{-1} C W \\
  Z = (D - C A^{-1} B)^{-1}
$$

_Proof_

$M M^{-1} = I$ implies the following matrix equations for $A$, $B$, $C$,
$D$, $W$, $X$, $Y$, $Z$:

$$
  AW + BY = I \\
  AX + BZ = 0 \\
  CW + DY = 0 \\
  CX + DZ = I
$$

Using the first and second equations, we can solve for $W$ and $X$ in terms
of $Y$ and $Z$:

$$
  W = A^{-1} (I - B Y) \\
  X = -A^{-1} B Z.
$$

Substituting these expressions into the last two equations and rearranging
yield

$$
  Z = (D - C A^{-1} B)^{-1} \\
  Y = -(D - C A^{-1} B)^{-1} C A^{-1} = -Z C A^{-1}
$$

Alternatively, starting with the third and fourth equations, we can solve for
$Y$ and $Z$ in terms of $W$ and $X$:

$$
  Z = D^{-1} (I - C X) \\
  Y = -D^{-1} C W.
$$

Substituting these expressions into the first two equations and rearranging
yield

$$
  W = (A - B D^{-1} C)^{-1} \\
  X = -(A - B D^{-1} C)^{-1} B D^{-1} = -W B D^{-1}
$$

Together, these results lead to the desired expressions for $W$, $X$, $Y$, and
$Z$.

### Woodbury Formula

Let $M = Z + U W V^T$ be an invertible matrix with $Z$ and $W$ invertible
square matrices, then

$$
  M^{-1} = Z^{-1} - Z^{-1} U (W^{-1} + V^T Z^{-1} U)^{-1} V^T Z^{-1}
$$

_Proof_. Consider the matrix

$$
  A = \left(\begin{array}{cc}
            Z   & U       \\
            V^T & -W^{-1}
          \end{array}\right)
$$

Then the matrix inversion formula for block matrices implies that $A^{-1}$
is given by

$$
  A^{-1}
  = \left(\begin{array}{cc}
        (Z + U W V^T)^{-1}
          & Z^{-1} U (W^{-1} + V^T Z^{-1} U)^{-1} \\
        (W^{-1} + V^T Z^{-1} U)^{-1} V^T Z^{-1}
          & (-W^{-1} - V^T Z^{-1} U)^{-1}
      \end{array}\right)
$$

Note that the upper diagonal element of $A^{-1}$ is equal to $M^{-1}$ and
that we have chosen to express the off-diagonal elements in terms of
$(-W^{-1} - V^T Z^{-1} U)^{-1}$ instead of $M^{-1}$. Since the upper
diagonal block of $A A^{-1} = I$, we have

$$
  Z M^{-1} + U (W^{-1} + V^T Z^{-1} U)^{-1} V^T Z^{-1} = I
$$

Solving for $M^{-1}$, we arrive at the Woodbury formula

$$
  M^{-1} = Z^{-1} - Z^{-1} U (W^{-1} + V^T Z^{-1} U)^{-1} V^T Z^{-1}
$$

#### Corollary: Sherman-Morrison Formula

If $M = Z + u v^T$ where $u$ and $v$ are rank-1, then the Woodbury formula
implies that

$$
  M^{-1} = Z^{-1} - \frac{ Z^{-1} u v^T Z^{-1} }{1 + v^T Z^{-1} u}.
$$

#### Corollary: $(A + B)^{-1} = A^{-1} - A^{-1} (A^{-1} + B^{-1})^{-1} A^{-1}$

Taking $U$ and $V$ to be the identity matrices in the Woodbury formula yields
the desired result. Note that the result is symmetric, so $(A + B)^{-1}$ may
also be expressed as $B^{-1} - B^{-1} (B^{-1} + A^{-1})^{-1} B^{-1}$.
### References

* [Matrix Inversion Lemmas][lienart-matrix-inversion-lemmas]

[------------------------- REFERENCES 2021-04-11 -------------------------]: #

[lienart-matrix-inversion-lemmas]: https://tlienart.github.io/pub/csml/mtheory/matinvlem.html

-------------------------------------------------------------------------------

2021-04-03: Taylor's Theorems
-----------------------------

### Taylor's Theorem

Let $f: \mathbb{R} \rightarrow \mathbb{R}$ be differentiable $k$ times at the
point $a$, then Taylor's theorem states that there exists a function
$h_k: \mathbb{R} \rightarrow \mathbb{R}$ such that

$$
  f(x) = \sum_{n=0}^{k} \frac{f^{(n)} (a)}{n!} (x - a)^n + h_k(x) (x - a)^k
$$

where $h_k(x) \rightarrow 0$ as $x \rightarrow a$.

__Comments__

* $h_k(x) (x - a)^k$ is called the Peano form of the remainder.

__Proof__. We can prove Taylor's theorem by induction. When $k = 1$, define
$h_1(x)$ as

$$
  h_1(x) = \frac{f(x) - f(a)}{x - a} - f'(a).
$$

Since $f$ is 1-time differentiable at $a$,

$$
  f'(a) = \lim_{x \rightarrow a} \frac{f(x) - f(a)}{x - a}
$$

which implies that $h_1(x) \rightarrow 0$ as $x \rightarrow a$. Rearranging the
definition of $h_1(x)$ yields the desired result for the case $k = 1$.

Now, suppose that Taylor's theorem holds for functions that are $k$-times
differentiable at $a$. Let $f$ be a function that is $(k+1)$-times
differentiable at $a$. Consider the function $g(x)$ defined by

$$
  g(x) = \frac{f(x) - f(a)}{x - a}
$$

Since $g(a) = f'(a)$, $g$ is $k$-times differentiable at $a$. Therefore,
the inductive hypothesis implies that $g(x)$ satisfies Taylor's theorem

$$
  g(x) = \sum_{n=0}^k \frac{g^{(n)} (a)}{n!} (x - a)^n + H(x) (x - a)^k
$$

where $H(x) \rightarrow 0$ as $x \rightarrow a$.

Repeatedly differentiating $g(x) (x - a) = f(x) - f(a)$, we find that the
first $k$ derivatives of $g(x)$ satisfy the recurrence relation for

$$
  n g^{(n-1)}(x) + g^{(n)}(x) (x - a) = f^{(n)}(x)
$$

which implies that $n g^{(n-1)}(a) = f^{(n)}(a)$.

Substibuting this relationship between the derivatives of $g(x)$ and $f(x)$
at $a$ into the definition of $g(x)$, we se that

$$
  f(x)
  = f(a) + g(x) (x - a)
  = f(a) + \sum_{n=0}^k \frac{g^{(n)} (a)}{n!} (x - a)^{n+1} +
    H(x) (x - a)^{k+1} \\
  = f(a) + \sum_{n=0}^k \frac{f^{(n+1)} (a)}{(n+1)!} (x - a)^{n+1} +
    H(x) (x - a)^{k+1} \\
  = \sum_{n=0}^{k+1} \frac{f^{(n)} (a)}{n!} (x - a)^{n} +
    H(x) (x - a)^{k+1},
$$

which shows that Taylor's theorem holds for functions that are
$(k+1)$-times differentiable at $a$.

### Taylor's Theorem With Remainder

Under slightly stronger smoothness assumptions, we can derive explicit
formulas for the remainder term.

Let $f: \mathbb{R} \rightarrow \mathbb{R}$ be differentiable $k + 1$ times on
the open interval $(a, x)$ with $f^{(k)}$ continuous on the closed interval
$[a, x]$, then Taylor's theorem _with remainder_ states that

$$
  f(x) = \sum_{n=0}^{k} \frac{f^{(n)} (a)}{n!} (x - a)^n + R_k(x)
$$

where remainder term $R_k(x)$ can be expressed explicitly as a polynomial of
degree $k + 1$.

* __Lagrange Form__. The Lagrange form of the remainder is

  $$
    R_k(x) = \frac{f^{(k+1)} (\xi_L)}{(k + 1)!} (x - a)^{k + 1}
  $$

  where $\xi_L \in (a, x)$.

* __Cauchy Form__. The Cauchy form of the remainder is

  $$
    R_k(x) = \frac{f^{(k+1)} (\xi_C)}{k!} (x - \xi_C)^k (x - a)
  $$

  where $\xi_C \in (a, x)$.

* __General Form__. If $G(t)$ is continuous on $[a, x]$ and is differentiable
  with non-vanishing derivative on $(a, x)$, then

  $$
    R_k(x) = \frac{f^{(k+1)} (\xi_G)}{k!} (x - \xi_G)^k
             \frac{G(x) - G(a)}{G'(\xi_G)}
  $$

  and $\xi_G \in (a, x)$. The Lagrange and Cauchy forms of the remainder
  follow by choosing $G(x) = (x - a)^{k+1}$ (__TODO__: fix form of $G(x)$ for
  Lagrange form) and $G(x) = x$, respectively.

__Proof__. To prove Taylor's theorem with remainder, consider the function

$$
  F(t) = \sum_{n=0}^k \frac{f^{(n)}(t)}{n!} (x - t)^n
$$

where $f$ is function that is $(k+1)$-differentiable. Note that

$$
  F(x) - F(a)
  = f(x) - \sum_{n=0}^k \frac{f^{(n)}(a)}{n!} (x - a)^n
  = R_k(x).
$$

For $G(t)$ continuous on $[a, x]$ and differentiable with non-vanishing
derivative on $(a, x)$, Cauchy's mean value theorem implies that there exists
$\xi$ such that

$$
  (G(x) - G(a)) F'(\xi) = (F(x) - F(a)) G'(\xi) = R_k(x) G'(\xi)
$$

Therefore,

$$
  R_k(x) = F'(\xi) \frac{G(x) - G(a)}{G'(\xi)}.
$$

Observe that

$$
  F'(t)
  = \sum_{n=0}^k \frac{f^{(n+1)}(t)}{n!} (x - t)^n
  - \sum_{n=1}^k \frac{f^{(n)}(t)}{(n-1)!} (x - t)^{n-1} \\
  = \frac{f^{(k+1)}(t)}{k!} (x - t)^k
  + \sum_{n=0}^{k-1} \frac{f^{(n+1)}(t)}{n!} (x - t)^n
  - \sum_{n=1}^k \frac{f^{(n)}(t)}{(n-1)!} (x - t)^{n-1} \\
  = \frac{f^{(k+1)}(t)}{k!} (x - t)^k
  + \sum_{n=0}^{k-1} \frac{f^{(n+1)}(t)}{n!} (x - t)^n
  - \sum_{n=0}^{k-1} \frac{f^{(n+1)}(t)}{n!} (x - t)^{n} \\
  = \frac{f^{(k+1)}(t)}{k!} (x - t)^k.
$$

Substituting this expression evaluated at $t = \xi$ into the equation for
$R_k(x)$ yields the desired result

$$
  R_k(x) = \frac{f^{(k+1)}(\xi)}{k!} (x - \xi)^k \frac{G(x) - G(a)}{G'(\xi)}.
$$

__Alternate Proof__. We can also prove Taylor's theorem with remainder for the
general form by induction. When $k = 0$, Cauchy's mean value theorem implies
that there exists $\xi \in (a, x)$ such that

$$
  (G(x) - G(a)) f'(\xi) = (f(x) - f(a)) G'(\xi)
$$

for $G(x)$ continuous on $[a, x]$ and differentiable (with nonzero derivative)
on $(a, x)$. Therefore,

$$
  f(x) = f(a) + f'(\xi) (x - \xi)^0 \frac{G(x) - G(a)}{G'(\xi)},
$$

which shows that the theorem holds for $k = 0$.

Now, suppose that Taylor's theorem with remainder holds for functions that are
$k$-times differentiable on $(a, x)$ with $(k-1)$-st derivative continuous on
$[a, x]$. Let $f$ be a function that is $(k+1)$-times differentiable on
$(a, x)$ with $f^{(k)}$ continuous on $[a, x]$. Consider the $g(x) = f'(x)$.
Since $g(x)$ satisfies the inductive hypothesis, Taylor's theorem with
remainder implies that

$$
  g(x) = \sum_{n=0}^{k-1} \frac{g^{(n)} (a)}{n!} (x - a)^n + R(x)
$$

with

$$
  R(x) = \frac{g^{(k)} (\xi)}{(k-1)!} (x - \xi)^{k-1}
         \frac{G(x) - G(a)}{G'(\xi)}.
$$

__TODO__: work out the details of an induction-based proof.

### References

* [Wikipedia: Taylor's Theorem][wikipedia-taylors-theorem]

[------------------------- REFERENCES 2021-04-03 -------------------------]: #

[wikipedia-taylors-theorem]: https://en.wikipedia.org/wiki/Taylor's_theorem

-------------------------------------------------------------------------------

2021-03-30: Review of Mean Value Theorems
-----------------------------------------

### Mean Value Theorem

If $f$ is continuous on the closed interval $[a, b]$ and differentiable on the
open interval $(a, b)$, then there exists $c \in (a, b)$ such that

$$
  f'(c) = \frac{f(b) - f(a)}{b - a}
$$

__Proof__

Let $h(x) = f(x) - r x$ with $r$ chosen so that $h(a) = h(b)$. Then,

$$
  r = \frac{f(b) - f(a)}{b - a}.
$$

$h(x)$ is differentiable on $(a, b)$, so Rolle's theorem implies that there
exists a $c \in (a, b)$ such that $h'(c) = f'(c) - r = 0$. Therefore,

$$
  f'(c) = r = \frac{f(b) - f(a)}{b - a}.
$$

### Cauchy's Mean Value Theorem

Cauchy's mean value theorem is a generalization of the mean value theorem.

If $f$ and $g$ are continuous on the closed interval $[a, b]$ and
differentiable on the open interval $(a, b)$, then there exists
$c \in (a, b)$ such that

$$
  (f(b) - f(a)) g'(c) = (g(b) - g(a)) f'(c).
$$

If $g(a) \ne g(b)$ and $g'(c) \ne 0$, then the above expression can be written
in a form analogous to the basic mean value theorem:

$$
  \frac{f'(c)}{g'(c)} = \frac{f(b) - f(a)}{g(b) - g(a)}
$$

__Proof__.

The proof of Cauchy's mean value theorem parallels the proof of the mean value
theorem.

* _Case_: $g(a) \ne g(b)$. Let $h(x) = f(x) - r g(x)$ with $r$ chosen so that
  $h(a) = h(b)$. Then,

  $$
    r = \frac{f(b) - f(a)}{g(b) - g(a)}.
  $$

  Since $f(x)$ and $g(x)$ are differentiable on $(a, b)$, $h(x)$ is also
  differentiable on $(a, b)$, so Rolle's theorem implies that there exists a
  $c \in (a, b)$ such that $h'(c) = f'(c) - r g'(c) = 0$. Rearranging this
  equation yields the desired result:

  $$
    (f(b) - f(a)) g'(c) = (g(b) - g(a)) f'(c).
  $$

* _Case_: $g(a) = g(b)$. Then Rolle's theorem implies that there exists
  $c \in (a, b)$ such that $g'(c) = 0$. For this choice of $c$,
  $(f(b) - f(a)) g'(c) = 0 = (g(b) - g(a)) f'(c)$.

__Notes__

* Cauchy's mean value theorem is also known as the "extended mean value
  theorem".

### References

* [Wikipedia: Mean Value Theorem][wikipedia-mean-value-theorem]

[------------------------- REFERENCES 2021-03-30 -------------------------]: #

[wikipedia-mean-value-theorem]: https://en.wikipedia.org/wiki/Mean_value_theorem

-------------------------------------------------------------------------------

2021-03-29: Partial Sum of Exponential Series
---------------------------------------------

### Closed-Form Expression $\sum_{k=0}^r \frac{x^k}{k!}$

The partial sum of an exponential series expressed in terms of the incomplete
gamma function

$$
  \sum_{k=0}^r \frac{x^k}{k!} = e^x \frac{\Gamma(r + 1, x)}{\Gamma(r + 1)}
$$

where the incomplete gamma function is defined as

$$
  \Gamma(s, x) = \int_x^\infty t^{s-1} e^{-t} dt.
$$

_Proof_

$$
  \sum_{k=0}^r \frac{x^k}{k!}
  = e^x - \sum_{k=r+1}^\infty \frac{x^k}{k!}
  = e^x \left( 1 - e^{-x} \sum_{k=r+1}^\infty \frac{x^k}{k!} \right)
  = e^x \left( 1 - \sum_{k=r+1}^\infty \frac{e^{-x} x^k}{k!} \right)
$$

Using the recurrence relation for the lower incomplete gamma function

$$
  \gamma(k + 1, x) = k \gamma(k, x) - e^{-x} x^k.
$$

we can express the sum in the parentheses as a telescoping sum

$$
  \sum_{k=r+1}^\infty \frac{e^{-x} x^k}{k!}
  = \sum_{k=r+1}^\infty \frac{k\gamma(k, x)}{k!} - \frac{\gamma(k + 1, x)}{k!}
  = \sum_{k=r+1}^\infty \frac{\gamma(k, x)}{(k-1)!} -
                        \frac{\gamma(k + 1, x)}{k!}
  = \frac{\gamma(r + 1, x)}{r!}
  = \frac{\gamma(r + 1, x)}{\Gamma(r + 1)}
$$

Substituting into the expression for the partial sum, we find that

$$
  \sum_{k=0}^r \frac{x^k}{k!}
  = e^x \left[ 1 - \frac{\gamma(r + 1, x)}{\Gamma(r + 1)} \right]
  = e^x \left[ \frac{\Gamma(r + 1)  - \gamma(r + 1, x)}{\Gamma(r + 1)} \right]
  = e^x \frac{\Gamma(r + 1, x)}{\Gamma(r + 1)}
$$

### Bounds on the Tail Series $\sum_{k=r}^\infty \frac{x^k}{k!}$

$$
  \frac{x^r}{r!}
  \le \sum_{k=r}^\infty \frac{x^k}{k!}
  \le e^x \frac{x^r}{r!}
$$

* _Proof based on Taylor's Theorem_. From Taylor's Theorem with remainder
  (centered at $x = 0$),

  $$
    e^x = \sum_{k=0}^{r-1} \frac{x^k}{k!} + g(\xi) \frac{x^r}{r!}
  $$

  where $g(x) = \left( \frac{d}{dx} \right)^r e^x = e^x$ and
  $\xi \in [0, x]$.

  Therefore,

  $$
    \frac{x^r}{r!}
    \le e^x - \sum_{k=0}^{r-1} \frac{x^k}{k!} = \sum_{k=r}^\infty \frac{x^k}{k!}
    \le e^x \frac{x^r}{r!}
  $$

* _Calculus-Free Proof of Upper Bound_

  $$
    \sum_{k=r}^\infty \frac{x^k}{k!}
    = \frac{x^r}{r!}
      \left(1 + \frac{x}{r + 1} + \frac{x^2}{(r + 2)(r + 1)} + \cdots \right)
    \le \frac{x^r}{r!}
        \sum_{n=0}^\infty \frac{x^n}{n!}
    = e^x \frac{x^r}{r!}
  $$

#### Tighter Upper Bound on Series $\sum_{k=r}^\infty \frac{x^k}{k!}$

When $x < r + 1$, we can use a geometric series to bound the factor in
parenthesis in the above calculus-free analysis to obtain a tighter upper
bound on the tail series.

$$
  \sum_{k=r}^\infty \frac{x^k}{k!}
  = \frac{x^r}{r!}
    \left(1 + \frac{x}{r + 1} + \frac{x^2}{(r + 2)(r + 1)} + \cdots \right) \\
  \le \frac{x^r}{r!}
      \sum_{n=0}^\infty \left( \frac{x}{r + 1} \right)^n
  = \left( \frac{x^r}{r!} \right) \left( \frac{r + 1}{r + 1 - x} \right)
$$

### References

* [Approximations for the partial sums of exponential series][stack-exchange-171241]

[------------------------- REFERENCES 2021-03-29 -------------------------]: #

[stack-exchange-171241]: https://math.stackexchange.com/questions/171241/approximations-for-the-partial-sums-of-exponential-series

-------------------------------------------------------------------------------

2021-03-29: Recurrence Relations for Incomplete Gamma Functions
---------------------------------------------------------------

The upper incomplete gamma function $\Gamma(s, x)$ is defined as

$$
  \Gamma(s, x) = \int_x^\infty t^{s-1} e^{-t} dt.
$$

The lower incomplete gamma function $\gamma(s, x)$ is defined as

$$
  \gamma(s, x) = \int_0^x t^{s-1} e^{-t} dt.
$$

Both satisfy recurrence relations in $s$ that are straightforward to prove
using integration by parts.

$$
  \Gamma(s + 1, x) = s \Gamma(s, x) + x^s e^{-x} \\
  \gamma(s + 1, x) = s \gamma(s, x) - x^s e^{-x}
$$


### References

* [Wikipedia: Incomplete gamma function][wikipedia-incomplete-gamma-function]

[------------------------- REFERENCES 2021-03-29 -------------------------]: #

[wikipedia-incomplete-gamma-function]: https://en.wikipedia.org/wiki/Incomplete_gamma_function

-------------------------------------------------------------------------------

2021-03-20: Reciprocal Bases and Their Properties
-------------------------------------------------

_Last Updated_: 2021-04-24

### Definition of Reciprocal Basis

Let $\mathbf{B} = \{\mathbf{b}_1, \mathbf{b}_2, \ldots, \mathbf{b}_n\}$ be a
basis for a lattice in $\mathbb{R}^n$. The reciprocal basis
$\mathbf{B}^* = \{\mathbf{b}_1^*, \mathbf{b}_2^*, \ldots, \mathbf{b}_n^*\}$ is
defined by the relations:

$$
  \mathbf{b}_i \cdot \mathbf{b}_j^* = \delta_{ij}
$$

where $\delta_{ij}$ is the Kronecker delta.

### Representation of Reciprocal Basis Vectors

#### Linear Algebra Approach

Construct the matrix $\mathbf{B}$ defined with the $i$-th column equal to the
$i$-th basis vector:

$$
  \mathbf{B}
  = \left[ \mathbf{b}_1 | \mathbf{b}_2 | \cdots | \mathbf{b}_n \right].
$$

Then the reciprocal basis vectors are the columns of the inverse of the matrix
$\mathbf{B}^{-1}$:

$$
  \mathbf{b}_j^* = \mathbf{B}^{-1} \mathbf{e}_i
$$

where $\mathbf{e}_i$ is the $i$-th standard basis vector.

#### Geometric Algebra Approach

Reciprocal basis vectors can be explicitly defined using the outer product in
geometric algebra.

$$
  \mathbf{b}_i^* = (-1)^{i-1}
                   (\mathbf{b}_1 \wedge \cdots \wedge \tilde{\mathbf{b}}_i
                                 \wedge \cdots \wedge \mathbf{b}_n)
                   (\mathbf{b}_1 \wedge \cdots \wedge \mathbf{b}_n)^{-1}
$$

where $\tilde{\mathbf{b}}_i$ indicates that $\mathbf{b}_i$ is omitted from the
outer product.

### Hyperplane Representations

The reciprocal basis $\mathbf{B}^*$ is convenient for representing hyperplanes
when the basis $\mathbf{B}$ is used to define a set of coordinate axes for
$\mathbb{R}^n$ (i.e., when $\mathbf{B}$ is used to define the coordinate
representation for points in $\mathbb{R}^n$).

Let $H$ be an $(n-1)$-dimensional hyperplane in $\mathbb{R}^n$. Suppose that
$H$ intersects the $i$-th coordinate axis $\mathbf{b}_i$ at coordinate
$\alpha_i$ (i.e., the intersection of $H$ with the axis $\mathbf{b}_i$
occurs at $\alpha_i \mathbf{b}_i$). Define $\mathbf{d}^*$:

$$
  \mathbf{d}^* = \alpha_1^* \mathbf{b}_1^* + \cdots
               + \alpha_n^* \mathbf{b}_n^*
$$

where $\alpha_i^* = 1 / \alpha_i$. Then hyperplane $H$ is defined by the
set of points $\mathbf{x} \in \mathbb{R}^n$ that satisfy the equation:

$$
  \mathbf{d}^* \cdot \mathbf{x} = 1.
$$

#### __Proof__

* $\mathbf{d}^*$ is orthogonal to the hyperplane $H$.

  _Proof_. It suffices to show that $\mathbf{d}^*$ is orthogonal to $(n-1)$
  linearly independent vectors that lie within $H$ (i.e., a basis for $H$).
  Note that differences of the intersections of $H$ with the coordinate axis
  readily provide a set of linearly independent vectors within $H$. In
  particular, the difference of all coordinate axis intersections with
  $\alpha_1 \mathbf{b}_1$ form a set of $(n-1)$ indepdendent vectors:
  $(\alpha_i \mathbf{b}_i - \alpha_1 \mathbf{b}_1)$ for $2 \le i \le n$.

  By direct verification, we see that $\mathbf{d}^*$ is orthogonal to this
  basis for $H$:

  $$
    \mathbf{d}^* \cdot (\alpha_i \mathbf{b}_i - \alpha_1 \mathbf{b}_1)
    = \sum_{j=1}^n \alpha_j^* \mathbf{b}_j^* \cdot
                   (\alpha_i \mathbf{b}_i - \alpha_1 \mathbf{b}_1) \\
    = \sum_{j=1}^n \alpha_j^* \alpha_i (\mathbf{b}_j^* \cdot \mathbf{b}_i)
                 - \alpha_j^* \alpha_1 (\mathbf{b}_j^* \cdot \mathbf{b}_1)
    = \sum_{j=1}^n
    \alpha_j^* \alpha_i \delta_{ij} - \alpha_j^* \alpha_1 \delta_{1j} \\
    = \alpha_i^* \alpha_i - \alpha_1^* \alpha_1
    = 1 - 1 = 0
  $$

* Let $\mathbf{x}$ be a point in the hyperplane $H$. Then
  $\mathbf{x} - \alpha_1^* \mathbf{b}_1$ is a vector that lies in $H$ and
  is orthogonal to $\mathbf{d}^*$:

  $$
    0 = \mathbf{d}^* \cdot (\mathbf{x} - \alpha_1 \mathbf{b}_1)
      = \mathbf{d}^* \cdot \mathbf{x}
      - \sum_{j=1}^n \alpha_j^* \mathbf{b}_j^* \cdot \alpha_1 \mathbf{b}_1
      = \mathbf{d}^* \cdot \mathbf{x}
      - \alpha_1^* \alpha_1 (\mathbf{b}_j^* \cdot \mathbf{b}_1)
      = \mathbf{d}^* \cdot \mathbf{x} - 1.
  $$

  Rearranging this equation yields the desired equation for $\mathbf{x}$.

#### Remarks

* _Intersections of $H$ with Coordinate Axes_. As desired, the intersections
  of $H$ with the coordinate axes satisfy the hyperplane equation.

  $$
    \mathbf{d}^* \cdot (\alpha_i \mathbf{b}_i)
    = \sum_{j=1}^n (\alpha_j^* \mathbf{b}_j^*) \cdot
                   (\alpha_i \mathbf{b}_i)
    = \sum_{j=1}^n \alpha_j^* \alpha_i \delta_{ij}
    = \alpha_i^* \alpha_i = 1
  $$

* _$1/|\mathbf{d}^*|$ is Distance of origin from $H$_. The distance of the
  origin from the hyperplane $H$ is the length of the projection of the vector
  of any point in $H$ to the origin onto the unit normal for $H$. In
  particular, it is equal to the length of the projection of
  $\alpha_1 \mathbf{b}_1$ onto $\mathbf{d}^* / |\mathbf{d}^*|$:

  $$
    \alpha_1 \mathbf{b}_1 \cdot \frac{\mathbf{d}^*}{|\mathbf{d}^*|}
    = \frac{(\alpha_1 \mathbf{b}_1) \cdot \mathbf{d}^*}{|\mathbf{d}^*|}
    = \frac{1}{|\mathbf{d}^*|}
  $$

### Application to X-ray Crystallography

In crystallography, the unit cell is defined by a set of basis vectors for the
crystal lattice structure. The lattice points generated by integer linear
combinations of the basis vectors define the location of physically equivalent
reference positions within the crystal.

The reciprocal lattice consisting of integer linear combinations the reciprocal
basis vectors plays a crucial role in the analysis of X-ray diffractograms.
By Bragg's law, the angles of diffractogram peaks is inversely related to
integer multiples of the distance of equivalent physical planes within the
crystal.

Observe that for physically equivalent planes, the plane closest to the origin
always corresponds to a lattice point in the reciprocal lattice where the
coefficients are relatively prime. Reciprocal lattice points $(h, k, l)$ where
the coefficients have a greatest common factor $m$ corresopnd to planes whose
distance to the origin (in real-space) is equal $d / m$ where $d$ is the
distance to the origin of the reciprocal lattice point $(h/m, k/m, l/m)$.

Combining these observations about the reciprocal lattice with Bragg's law,
we can conclude that all reciprocal lattice points lead to potential peaks
a crystal's X-ray diffractogram. Note, however, that not all peaks
corresponding to reciprocal lattice points may be present in an X-ray
diffactogram due to phase cancellation effects from atoms within a unit cell.
Phase cancellations have two distinct origins.

* "Extinction rules" arise from symmetry properties of atoms in the unit cell
  and are not affected by the specific composition of or the location of atoms
  within the unit cell.

* Peaks predicted by the reciprocal lattice may also be be absent if the
  structure factor is equal to (or near) zero for the particular arrangement
  of atoms within the unit cell.

-------------------------------------------------------------------------------
