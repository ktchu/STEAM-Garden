Control Theory
==============

*Author(s)*: Kevin Chu `<kevin@velexi.com>`

__Last Updated__: 2022-01-13

-------------------------------------------------------------------------------

Preface
-------

* This document is written using GitHub Markdown.  It is best viewed using a
  Markdown viewer that supports GitHub Markdown:

  * [Chrome Markdown Viewer][chrome-markdown-viewer]

    * _Note_: be sure to enable the following extension settings

      * Automatically allow access on the following sites
        * `file:///*`

      * Allow access to file URLS

  * [Atom Editor](https://atom.io/)

-------------------------------------------------------------------------------

Table of Contents
-----------------

1. [Ideal Control Law Design][#1]

    1.1. [Theoretical Framework][#1.1]

    1.2. [Computational Methods][#1.2]

    1.3. [Special Case: Linear Systems][#1.3]

2. [State Estimation][#2]

3. [Stochastic Control Law Design][#3]

    3.1. [General Theory][#3.1]

    3.2. [Special Case: Linear Systems][#3.2]

4. [References][#4]

-------------------------------------------------------------------------------

## 1. Ideal Control Law Design

### 1.1. Theoretical Framework

#### 1.1.1. Terminology and Notation

##### Mathematical Notation

* $[t_0, t_f]$: time interval of interest

* $\dot{y}(t) \equiv \frac{dy}{dt}$: time derivative of $y(t)$

* $(\partial F / \partial x)$: Jacobian of $F$ with respect to $x$. To
  facilitate expression of quantities in terms of matrix products, we use the
  following conventions for the Jacobian:

  * the gradient of a scalar function is represented as a row matrix;

  * the Jacobian of vector function is represented so that the $i$-th row of
    of the matrix is the gradient of the $i$-th component of the vector
    function.

##### Terminology

* $x(t)$: state vector trajectory

* $u(t)$: control vector trajectory

* $\lambda(t)$: Lagrange multiplier (vector) trajectory

* $f(x, u, t)$: time rate of change of the state vector

* $\phi(x, t)$: terminal cost function

* $\mathcal{L}(x, u, t)$: cost per unit time (Lagrangian)

* $\mathcal{H}(x, u, \lambda, t)$: modified cost per unit time (Hamiltonian)
  that includes a cost associated with enforcing the constraint that the state
  vector's trajectory satisfies the system's dynamical equations

* $J(x, u, t)$: cost function

* $J_H(x, u, \lambda, t)$: modified cost function (includes Lagrange
  multiplier term)

#### 1.1.2. Optimization Problem

Control law design can be framed as an optimization problem: minimize the cost
function of a dynamical system (constrained to satisfy a known evolution
equation) over a specified time interval.

Mathematically, the cost function to be optimized can be expressed as

\[
J(x, u, t)
= \phi(x(t_f), t_f) + \int_{t_0}^{t_f} \mathcal{L}(x(t), u(t), t) dt
\]

where $t_0$ and $t_f$ are the endpoints of the time interval of interest. When
the cost function includes both a terminal cost term and an integral term, it
is said to be of _Bolza type_. Cost functions with only a terminal cost term or
only an integral term are of _Mayer type_ or _Lagrangian type_, respectively.

We seek a control law $u(t)$ that minimizes the cost function subject to the
constraint that the dynamics of the system satisfy an evolution equation of
the form

\[
\dot{x}(t) = f(x, u, t).
\]

#### 1.1.3. Euler-Lagrange Equations for Optimal Control Law

Using the calculus of variations, we can derive conditions required for $u(t)$
to be optimal.

First, we use the method of Lagrange multipliers to allow to us to treat $x(t)$
as an _unconstrained_ variable in the analysis while ensuring that the system's
dynamics are satisfied. Adding a Lagrange multiplier term for each dynamical
equation, we obtain the modified cost function

\[
J_H(x, u, t)
= J(x, u, t)
  + \int_{t_0}^{t_f} \lambda^T(t) \left[ f(x, u, t) - \dot{x}(t) \right] dt \\
= \phi(x(t_f), t_f)
  + \int_{t_0}^{t_f} \mathcal{L}(x, u, t)
                     + \lambda^T(t) \left[ f(x, u, t) - \dot{x}(t) \right] dt
\]

Next, we take the first variation of $J_H$ with respect to variations in
$u(t)$, $x(t)$, and $\lambda(t)$:

\[
\delta J_H
= \frac{\partial \phi}{\partial x} \delta x(t_f)
  + \int_{t_0}^{t_f}
    \frac{\partial \mathcal{L}}{\partial u} \delta u
    + \frac{\partial \mathcal{L}}{\partial x} \delta x
    + \lambda^T \frac{\partial f}{\partial u} \delta u
    + \lambda^T \frac{\partial f}{\partial x} \delta x
    - \lambda^T \delta \dot{x}
    + (\delta \lambda)^T \left[ f - \dot{x} \right] dt \\
= \frac{\partial \phi}{\partial x} \delta x(t_f)
  + \int_{t_0}^{t_f}
      \left[
        \frac{\partial \mathcal{L}}{\partial u}
      + \lambda^T \frac{\partial f}{\partial u}
      \right] \delta u
    + \left[
        \frac{\partial \mathcal{L}}{\partial x}
      + \lambda^T \frac{\partial f}{\partial x}
      \right] \delta x
    - \lambda^T \delta \dot{x}
    + (\delta \lambda)^T \left[ f - \dot{x} \right] dt
\]

where $\delta u(t)$, $\delta x(t)$, and $\delta \lambda(t)$ are the variations
in $u(t)$, $x(t)$, and $\lambda(t)$, respectively, and we have suppressed
functional dependencies, in places, to reduce clutter.

To obtain an expression for $\delta J_H$ involving only variations in $u$, $x$,
and $\lambda$ (but not their time derivatives), we integrate the term involving
$\delta \dot{x}$ by parts to shift the time derivative from $\delta x$ to
$\lambda$:

\[
\int_{t_0}^{t_f} \lambda^T \delta \dot{x} dt
  = \lambda^T (t_f) \delta x(t_f) - \lambda^T (t_0) \delta x(t_0)
    - \int_{t_0}^{t_f} \dot{\lambda}^T x dt \\
  = \lambda^T (t_f) \delta x(t_f) - \int_{t_0}^{t_f} \dot{\lambda}^T x dt,
\]

where we have used the fact that specification of the initial conditions
$x(t_0)$ for the state vector implies that $\delta x(t_0) = 0$.

Substituting this expression into the equation for $\delta J_H$ and rearranging,
we arrive at

\[
\delta J_H(x, u, t)
= \left[
    \frac{\partial \phi}{\partial x} (t_f) - \lambda^T (t_f)
  \right] \delta x(t_f)
  + \int_{t_0}^{t_f}
      \left[
        \frac{\partial \mathcal{L}}{\partial u}
      + \lambda^T \frac{\partial f}{\partial u}
      \right] \delta u
    + \left[
        \frac{\partial \mathcal{L}}{\partial x}
      + \lambda^T \frac{\partial f}{\partial x}
      + \dot{\lambda}^T
      \right] \delta x
    + (\delta \lambda)^T \left[ f - \dot{x} \right] dt
\]

Because the first variation must equal zero at an optimum of $J_H$ and the
variations $\delta u$, $\delta x$, and $\delta \lambda$ are all independent
and unconstrained, we require that the factors multiplying each of the
variations be identically zero on the entire time interval $[t_0, t_f]$.
Therefore, the necessary conditions for an optimal solution are

\[
\frac{\partial \phi}{\partial x}(t_f) - \lambda^T (t_f) = 0 \\

\frac{\partial \mathcal{L}}{\partial u}
+ \lambda^T \frac{\partial f}{\partial u} = 0 \\

\frac{\partial \mathcal{L}}{\partial x}
+ \lambda^T \frac{\partial f}{\partial x}
+ \dot{\lambda}^T = 0 \\

f - \dot{x} = 0
\]

Reorganizing these equations, we arrive at the _Euler-Lagrange equations_ for
the optimization problem:

* Dynamical equations for the system:

  \[
    \dot{x} - f = 0
  \]

* Dynamical equations for the Lagrange multiplier:

  \[
    \dot{\lambda}^T
    + \frac{\partial \mathcal{L}}{\partial x}
    + \lambda^T \frac{\partial f}{\partial x}
    = 0
  \]

  subject to the terminal condition

  \[
    \lambda^T (t_f) = \frac{\partial \phi}{\partial x} (t_f).
  \]

* Optimality condition for the control law $u(t)$:

  \[
    \frac{\partial \mathcal{L}}{\partial u}
    + \lambda^T \frac{\partial f}{\partial u} = 0
  \]


To simplify the structure of these equations, we can define a modified cost per
unit time that includes a cost associated with enforcing the constraint that
the state vector's trajectory satisfies the system's dynamical equations

\[
\mathcal{H}(x, u, \lambda, t) = \mathcal{L}(x, u, t) + \lambda^T(t) f(x, u, t).
\]

Rearranging the necessary conditions and expressing the results in terms of
$\mathcal{H}$, we find that the optimal control $u(t)$, state vector $x(t)$,
and Lagrange multipler $\lambda(t)$ must satisfy the following
differential-algebraic system of equations.

* Dynamical equations for sytem (a direct result of implicitly embedding them
  in the modified cost function via the method of Lagrange multipliers):

  \[
    \dot{x}(t)
    = f(x, u, t)
    = \left(
        \frac{\partial \mathcal{H}}{\partial \lambda}
      \right)^T (x, u, \lambda, t)
  \]

  with specified initial conditions $x(t_0) = x_0$.

* Dynamical equations for Lagrange multiplier:

  \[
    \dot{\lambda} (t)
    = -\left(
        \frac{\partial \mathcal{H}}{\partial x}
      \right)^T (x, u, \lambda, t)
  \]

  with specified terminal conditions

  \[
    \lambda(t_f) = \left( \frac{\partial \phi}{\partial x} \right)^T (t_f).
  \]

* Stationarity of $\mathcal{H}$ with respect to control law $u(t)$:

  \[
    \frac{\partial \mathcal{H}}{\partial u} = 0.
  \]

These equations are _Hamilton equations_ for the optimization problem.

#### 1.1.4. Additional Comments

___Alternate Equations for Optimal Control Law___

__TODO__

___Connection to the Hamiltonian Formulation of Classical Mechanics___

In the Hamiltonian formulation of classical mechanics, the dynamical equations
for generalized coordinates and generalized momenta are given by

\[
\dot{q}(t) = \left( \frac{\partial H}{\partial p} \right)^T \\
\dot{p}(t) = -\left( \frac{\partial H}{\partial q} \right)^T
\]

where $q$ and $p$ are generalized coordinates and momenta, respectively.
Making the associations $q \rightarrow x$, $p \rightarrow \lambda$ and
$H \rightarrow \mathcal{H}$, we find that the structure of the dynamical
equations for the state vector $x(t)$ and the Lagrange multiplier $\lambda(t)$
is identical to the structure of the Hamilton's equations of motion:

\[
\dot{x}(t) = \left( \frac{\partial \mathcal{H}}{\partial \lambda} \right)^T \\

\dot{\lambda}(t) = -\left( \frac{\partial \mathcal{H}}{\partial x} \right)^T.
\]

It is in this sense that $\mathcal{H}$ is the Hamiltonian for the system.

As in classical mechanics, the structure of the dynamical equations leads to
the useful property that $\mathcal{H}$ is a conserved quantity (i.e., its time
derivative is zero) when the control law $u(t)$ is optimal and the Hamiltonian
has no explicit dependence on time:

\[
\frac{d \mathcal{H}}{dt} (x, u, \lambda, t)
=   \frac{\partial \mathcal{H}}{\partial t}
  + \frac{\partial \mathcal{H}}{\partial x} \dot{x}
  + \frac{\partial \mathcal{H}}{\partial \lambda} \dot{\lambda}
  + \frac{\partial \mathcal{H}}{\partial u} \dot{u} \\
=   \frac{\partial \mathcal{H}}{\partial t}
  + \frac{\partial \mathcal{H}}{\partial x}
    \left( \frac{\partial \mathcal{H}}{\partial \lambda} \right)^T
  + \frac{\partial \mathcal{H}}{\partial \lambda}
    \left( - \frac{\partial \mathcal{H}}{\partial x} \right)^T
  + \frac{\partial \mathcal{H}}{\partial u} \dot{u}
= 0
\]

where we have used the facts that (1) the inner product of two vectors is
independent of the order of the vectors and (2) the absence of explicit time
dependence for $\mathcal{H}$ and the optimality of the control law imply that
$\partial \mathcal{H} / \partial t$ and $\partial \mathcal{H} / \partial u$
are both zero. Note that the condition that $\mathcal{H}$ has no explicit
dependence on time is satisified if both the Lagrangian $\mathcal{L}$ and time
rate of change of the state $f$ have no explicit dependence on time.

It is important to recognize that the Hamiltonian is _not_ defined as the
Legendre transformation of the Lagrangian $\mathcal{L}(x, u, t)$ (as is the
case for in classical mechanics).
Rather,
the key to the transformation between the Lagrangian and the Hamiltonian lies
in combining (with signs chosen appropriately) the Lagrangian with a term that
is the product of the conjugate variable (e.g., generalized momentum or
Lagrange multiplier) and a quantity that, through application of the
Euler-Lagrange equations, yields the Hamilton equations.

In classical mechanics, there is no explicit function for the time evolution of
$q(t)$, so we choose the sign on $L$ to be negative and the quantity
multiplying the conjugate variable $p$ to be $\dot{q}(t)$:
$H(p, q, \dot{q}, t) = p \dot{q} - L(q, \dot{q}, t)$. This choice yields
Hamilton's equations of motion.

* $\left( \frac{\partial H}{\partial p} \right)^T = \dot{q}$

* The Euler-Lagrange equations imply that the conjugate variable should
  be defined as $p(t) = \partial L / \partial \dot{q}$ so that

  \[
    \dot{p}(t) = -\left( \frac{\partial H}{\partial q} \right)^T.
  \]

* $H$ is independent of $\dot{q}$ because
  $\partial H / \partial \dot{q} = -p + \partial L / \partial \dot{q} = 0$.

Note that the fact that $H$ is the Legendre transformation of $L$ is a
_consequence_ of the choice of $p$ _required_ by the structure of the Hamilton
equations in classical mechanics - in general, $H$ and $L$ are _not_ related
by a Legendre transformation.

In the context of optimal control theory, the dynamical equations for the
state are explicitly specified, so we choose the sign on $L$ to be positive
and the quantity multiplying the conjugate variable $\lambda$ to be
$f(x, u, t)$:

\[
\mathcal{H}(x, u, \lambda, t) = \mathcal{L}(x, u, t) + \lambda^T f(x, u, t).
\]

This choice yields the Hamilton equations for the optimization problem.

* $\left( \frac{\partial H}{\partial \lambda} \right)^T = f = \dot{x}$ where
  the last equality follows from the system's dynamical equations.

* The Euler-Lagrange equations imply that the conjugate variable $\lambda(t)$
  satisfies the dynamical equation

  \[
    \left( \frac{\partial \mathcal{H}}{\partial x} \right)^T
    = \left( \frac{\partial \mathcal{L}}{\partial x}
      + \lambda^T \frac{\partial f}{\partial x} \right)^T
    = -\dot{\lambda}
  \]

* $H$ is independent of $\dot{x}$ because $\partial H / \partial \dot{x} = 0$.

Note that $\mathcal{H}$ is _not_ the Legendre transformation of $\mathcal{L}$
because the purpose of the added term $\lambda^T f$ is not intended to change
any of the independent variables in $\mathcal{L}$.

### 1.2. Computational Methods

#### 1.2.1. Parametric Methods

__TODO__

#### 1.2.2. Split State-Control Iterative Methods

One intuitively appealing approach for computationally solving the
Euler-Lagrange equations is to use the following procedure to iteratively
refine a numerical approximation to the control law $u(t)$.

* Start with a reasonable estimate $u_0(t)$ for the control law.

* Repeat the following steps until $u_k(t)$ satisfies a reasonable stopping
  criteria is satisfied.

    * Given $u_k(t)$, use the dynamical equations $\dot{x} = f$ for the system
      to compute the the next approximate solution to the state vector
      $x_k(t)$.

    * Given $u_k(t)$ and $x_k(t)$, use the dynamical equations fo the Lagrange
      multiplier to compute the next approximate solution to the Lagrange
      multiplier trajectory $\lambda_(t)$.

    * Use $u_k(t)$, $x_k(t)$, and $\lambda_k(t)$ to compute a refinement of
      the control law $u_{k+1}(t)$.

__Approaches for Updating the Control Law__

There are many options for updating the control law $u_k(t)$. The following are
a few reasonable possibilities.

* _Steepest Descent_. Adjust $u_k(t)$ in the direction opposite the gradient
  of $\mathcal{H}$ with respect to $u$ (i.e.,
  $(\partial \mathcal{H} / \partial u)^T$):

  \[
  u_{k+1}(t)
  =   u_k(t)
   - \epsilon_k(t)
     \left(
       \frac{\partial \mathcal{H}}{\partial u}
     \right)^T (x_k, u_k, \lambda_k, t).
  \]

  Note that $\epsilon_k$ is a function of time to allow the control law at
  different times to be refined at different rates (e.g., to mitigate the
  typically large impact of changes to the control law at late times to the
  terminal cost).

* _Newton-Raphson Algorithm_. When $u_k(t)$ is close to an optimal solution
  (under assumptions of convexity near the optimum), $\mathcal{H}_{uu}$ is
  positive (or negative) definite. In particular, it is invertible. Therefore,
  we can use the Newton-Raphson algorithm to iterate more quickly towards the
  optimal solution:

  \[
  u_{k+1}(t)
  =   u_k(t)
   - \mathcal{H}_{uu}(x_k, u_k, \lambda_k, t)
     \left(
       \frac{\partial \mathcal{H}}{\partial u}
     \right)^T (x_k, u_k, \lambda_k, t).
  \]

* _Generalized Gradient Algorithms_. The Newton-Raphson algorithm is
  computationally expensive because it involves calculation of
  $\mathcal{H}_{uu}$ at each iteration. As an alternative, an approximate
  Jacobian $K_k$ of $\partial \mathcal{H} / \partial u$ can be used to update
  $u_k(t)$:

  \[
  u_{k+1}(t)
  =   u_k(t)
   - K_k
     \left(
       \frac{\partial \mathcal{H}}{\partial u}
     \right)^T (x_k, u_k, \lambda_k, t).
  \]

  There are many choice for $K_k$ that typically trade-off (1) simplicity of
  the computation of $K_k$ with (2) increases in the number of iterations
  required to reach a suitably accurate solution to the Euler-Lagrange
  equations.

__Stopping Criterion Options__

Because $\partial H / \partial u = 0$ is the condition for optimality of the
control law $u_k(t)$, typical stopping criteria are based on checking whether
a function of $\partial H / \partial u$ is sufficiently close to zero. For
example, one possible stopping criteria could be when the time integral of the
max norm of $\partial H / \partial u$ is sufficiently close to 0:

\[
\int_{t_0}^{t_f} \left\Vert \frac{\partial H}{\partial u} \right\Vert_\infty dt.
\]

#### 1.2.3. Combined State-Control Iterative Methods

__TODO__

### 1.3. Special Case: Linear Systems

__TODO__

-------------------------------------------------------------------------------

## 2. State Estimation

-------------------------------------------------------------------------------

## 3. Stochastic Control Design

-------------------------------------------------------------------------------

## 4. References

1. R.F. Stengel. "Optimal Control And Estimation" (1994).

-------------------------------------------------------------------------------

[-----------------------------INTERNAL LINKS-----------------------------]: #

[#1]: #1-ideal-control-law-design
[#1.1]: #11-theoretical-framework
[#1.2]: #12-computational-methods
[#1.3]: #13-special-case-linear-systems

[#2]: #2-state-estimation

[#3]: #3-stochastic-control-law-design
[#3.1]: #31-general-theory
[#3.2]: #32-special-case-linear-systems

[#4]: #4-references

[-----------------------------EXTERNAL LINKS-----------------------------]: #

[chrome-markdown-viewer]: https://chrome.google.com/webstore/detail/markdown-viewer/ckkdlimhmcjmikdlpkmbgfkaikojcbjk
