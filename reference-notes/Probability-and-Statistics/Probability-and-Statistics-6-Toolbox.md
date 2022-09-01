Probability and Statistics: Toolbox
===================================

*Author(s)*: Kevin Chu `<kevin@velexi.com>`

__Last Updated__: 2022-07-24

--------------------------------------------------------------------------------------------

## 0. Notation

* $\newcommand{\R}{\mathbb{R}}$
  The set of real numbers: $\R$

* $\newcommand{\Pr}[1]{\mathbb{P}\left[{#1}\right]}$
  Probability of event $E$: $\Pr{E}$

* $\newcommand{\1}[1]{\mathbf{1}_{\left\{{#1}\right\}}}$
  Indicator for event $E$: $\1{E}$

* $\newcommand{\p}[1]{p\left({#1}\right)}$
  Probability density (or mass) function for a random variable $X$: $\p{x}$

* $\newcommand{\E}[1]{\mathbb{E}\left[{#1}\right]}$
  Expected value of $X$: $\E{X}$

* $\newcommand{\Var}[1]{\operatorname{Var}{\left(#1\right)}}$
  Variance of $X$: $\Var{X}$

* $\newcommand{\sd}[1]{\sigma{\left(#1\right)}}$
  Standard deviation of $X$: $\sd{X}$

* $\newcommand{\Cov}[1]{\operatorname{Cov}{\left(#1\right)}}$
  Covariance of $X$: $\Cov{X}$

--------------------------------------------------------------------------------------------

## 1. Toolbox

### Symmetric Bernoulli/Rademacher Distribution

* __Definition__. A random variable $X$ has a _symmetric Bernoulli distribution_ or
  _Rademacher_ distribution if it takes only two values 1 and -1 each with probability
  $1/2$:

  $$
  \Pr{X = -1} = \Pr{X = 1} = \frac{1}{2}.
  $$

### Symmetrization Tricks

* __Distribution of $X - X'$ is Even__. Let $X$ and $X'$ be i.i.d. random variables with
  the same distribution. Then the probability density function for $Y = X - X'$ is an even
  function: $\p{y} = \p{-y}$.

  _Proof_. Let $f(x)$ be the probability density for $X$ and $X'$. Consider the cumulative
  distributions function $G(y)$ for $Y$:

  $$
  G(y)
  = \Pr{Y \le y}
  = \int_{-\infty}^\infty f(x) \left( \int_{x-y}^{\infty} f(x') dx' \right) dx
  $$

  Differentiating with respect to $y$, we find that

  $$
  \p{y} = \frac{dG}{dy}
  = \int_{-\infty}^\infty f(x) f(x-y) dx.
  $$

  Evaluating the probability density at $-y$, we see that

  $$
  \p{-y}
  = \int_{-\infty}^\infty f(x) f(x+y) dx
  = \int_{-\infty}^\infty f(t-y) f(t) dt,
  $$

  where the last equality follows from the substitution $t = x + y$.

  Therefore, $\p{y} = \p{-y}$, as desired.

### Approximating Probability Distributions of Functions of Random Variables

Let $X$ be a random variable and $f(x)$ be function. If $X$ is sufficiently concentrated
near $\mu = \E{X}$ and $f(x)$ is sufficiently well-approximated by its Taylor series
expansion about $x = \mu$, then we can approximate $\E{f(X)}$ and $\Var{f(x)}$ by

$$
\E{f(X)} = f(\mu) + \frac{1}{2} f''(\mu) \Var{X} + O\left( \E{(X - \mu)^3} \right) \\
\Var{f(X)} = (f'(\mu))^2 \Var{X} - \frac{1}{4} (f''(\mu))^2 \Var{X}^2
           + O\left( \E{(X - \mu)^3} \right)
$$

_Proof_. Expanding $f(X)$ as a Taylor series of $f(X)$ about $X = \mu$,

$$
f(X) = f(\mu) + f'(\mu) (X - \mu) + \frac{1}{2} f'(\mu) (X - \mu)^2
     + O\left( (X - \mu)^3 \right)
$$

Taking expectations and recognizing that $\E{X - \mu} = 0$ and $\E{(X - \mu)^2} = \Var{X}$,
we obtain the desired result for the $\E{f(X)}$:

$$
\E{f(X)}
= f(\mu) + f'(\mu) \E{X - \mu} + \frac{1}{2} f''(\mu) \E{(X - \mu)^2}
  + O\left( \E{(X - \mu)^3} \right) \\
= f(\mu) + \frac{1}{2} f''(\mu) \Var{X} + O\left( \E{(X - \mu)^3} \right)
$$

To derive an approximation for the variance of $f(X)$, we begin by approximating the second
moment of $f(X)$:

$$
\E{( f(X) )^2}
= \E{\left(
  f(\mu) + f'(\mu) (X - \mu) + \frac{1}{2} f''(\mu) (X - \mu)^2
  + O\left( (X - \mu)^3 \right)
  \right)^2} \\
= \E{
  (f(\mu))^2 + 2 f(\mu) f'(\mu) (X - \mu)
  + \left( f'(\mu)^2 + f(\mu) f''(\mu) \right) (X - \mu)^2
  + O\left( (X - \mu)^3 \right)
  } \\
= (f(\mu))^2 + \left( f'(\mu)^2 + f(\mu) f''(\mu) \right) \Var{X}
  + O\left( \E{(X - \mu)^3} \right)
$$

where we have used $\E{X - \mu} = 0$ to eliminate the first-order term in the last
expression. Substituting this expression into the formula for the variance, we find

$$
\Var{f(X)}
\approx \E{(f(X))^2} - \E{f(X)}^2 \\
= \left( (f(\mu))^2 + \left( (f'(\mu))^2 + f(\mu) f''(\mu) \right) \Var{X} \right)
- \left( (f(\mu))^2 + f(\mu) f''(\mu) \Var{X}
       + \frac{1}{4} ( f''(\mu) )^2 (\Var{X})^2 \right) \\
= (f'(\mu))^2 \Var{X} - \frac{1}{4} ( f''(\mu) )^2 (\Var{X})^2,
$$

where the approximation error is $O\left( \E{(X - \mu)^3} \right)$.

--------------------------------------------------------------------------------------------

## 2. References

1. R. Vershynin. "High-Dimensional Probability". (2018)

2. M.J. Wainwright. "High-Dimensional Statistics: A Non-Asymptotic Viewpoint". (2019)

--------------------------------------------------------------------------------------------

[----------------------------------- INTERNAL LINKS -----------------------------------]: #

[----------------------------------- EXTERNAL LINKS -----------------------------------]: #
