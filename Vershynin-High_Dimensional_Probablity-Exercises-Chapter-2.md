High-Dimensional Probability (Vershynin): Exercises - Chapter 2
===============================================================

--------------------------------------------------------------------------------------------

### Notation

* $\newcommand{\R}[0]{\mathbb{R}}$
  The set of real numbers: $\R$

* $\newcommand{\Pr}[1]{\mathbb{P}\left[{#1}\right]}$
  Probability of event $E$: $\Pr{E}$

* $\newcommand{\1}[1]{\mathbf{1}_{\left\{{#1}\right\}}}$
  Indicator for event $E$: $\1{E}$

* $\newcommand{\p}[1]{p\left({#1}\right)}$
  Probability density (or mass) function for a random variable $X$: $\p{x}$

* $\newcommand{\E}[1]{\mathbb{E}\left[{#1}\right]}$
  Expected value of $X$: $\E{X}$

* $\newcommand{\Esub}[2]{\mathbb{E}_{#1}\left[{#2}\right]}$
  Expected value of $XY$ with respect to $X$: $\Esub{X}{XY}$

--------------------------------------------------------------------------------------------

### 2.1.4. Truncated Normal Distribution

__Problem__. Let $g \sim N(0, 1)$. Show that, for all $t \ge 1$, we have

$$
\E{g^2 \1{g > t}}
= t \frac{1}{\sqrt{2 \pi}} e^{-t^2/2} + \Pr{g > t}
\le \left( t + \frac{1}{t} \right) \frac{1}{\sqrt{2 \pi}} e^{-t^2/2}.
$$

__Solution__.

$$
\E{g^2 \1{g > t}}
= \frac{1}{2} \E{g^2 \1{|g| > t}}
= \frac{1}{2} \int_t^\infty g^2 \frac{e^{-g^2/2}}{\sqrt{2 \pi}} dg \\
= \left. -\frac{1}{\sqrt{2 \pi}} g e^{-g^2/2} \right|_t^\infty
  + \int_t^\infty \frac{e^{-g^2/2}}{\sqrt{2 \pi}} dg
= \frac{1}{\sqrt{2 \pi}} t e^{-t^2/2} + \Pr{g > t}.
$$

where the second to last equality follows from integration by parts and the last equality
follows from the definition of the tail probability.

Using Proposition 2.1.2,

$$
\Pr{g > t} \le \frac{1}{t} \frac{1}{\sqrt{2 \pi}} e^{-t^2/2},
$$

we arrive at our desired result

$$
\E{g^2 \1{g > t}}
= \frac{1}{\sqrt{2 \pi}} t e^{-t^2/2} + \Pr{g > t}
\le \left( t + \frac{1}{t} \right) \frac{1}{\sqrt{2 \pi}} e^{-t^2/2}.
$$

--------------------------------------------------------------------------------------------

### 2.2.3. Bound for Hyperbolic Cosine

__Problem__. Show that $\cosh(x) \le e^{x^2/2}$ for all $x \in \R$.

__Solution__. Since the Taylor series for $e^{x}$ converges for all $x \in \R$, we can
derive the result by comparing the Taylor series for both $\cosh(x)$ and $e^{x^2/2}$:

$$
\cosh(x)
= \frac{1}{2}\left( e^{x} + e^{-x} \right)
= \frac{1}{2}\left(
    \sum_{n=0}^\infty \frac{x^n}{n!} + \sum_{n=0}^\infty \frac{(-x)^n}{n!}
  \right)
= \sum_{n=0}^\infty \frac{x^{2n}}{(2n)!} \\
e^{x^2/2}
= \sum_{n=0}^\infty \frac{1}{n!} \left( \frac{x^2}{2} \right)^n
= \sum_{n=0}^\infty \frac{x^{2n}}{2^{n} n!}.
$$

Observing that $2^n \le (2n) (2n-1) \cdots (n+1)$ for $n \ge 1$, we can conclude that

$$
\frac{x^{2n}}{(2n)!} \le \frac{x^{2n}}{2^{n} n!}
$$

for all $x \in \R$ and $n \ge 0$. Therefore, we can conclude that $\cosh(x) \le e^{x^2/2}$.

--------------------------------------------------------------------------------------------

### 2.2.7. Hoeffding's Inequality for General Bounded Random Variables

__Problem__. Let $X_1, \ldots, X_N$ be independent random variables with
$X_i \in [m_i, M_i]$ and $\E{X_i} = \mu_i$. Show that for any $t > 0$, we have

$$
\Pr{\sum_{i=1}^n (X_i - \mu_i) \ge t}
\le \exp \left( -\frac{K t^2}{\sum_{i=1}^n (M_i - m_i)^2} \right),
$$

where $K$ is a postive constant.

__Solution__. Letting $\lambda > 0$,

$$
\Pr{\sum_{i=1}^n (X_i - \mu_i) \ge t}
= \Pr{\lambda \sum_{i=1}^n (X_i - \mu_i) \ge \lambda t}
= \Pr{\exp\left( \lambda \sum_{i=1}^n (X_i - \mu_i) \right) \ge e^{\lambda t}}.
$$

Applying Markov's inequality to this last expression, we can conclude that

$$
\Pr{\sum_{i=1}^n (X_i - \mu_i) \ge t}
\le e^{-\lambda t} \ \E{\exp\left( \lambda \sum_{i=1}^n (X_i - \mu_i) \right)}
= e^{-\lambda t} \prod_{i=1}^n \E{e^{\lambda (X_i - \mu_i)}}.
$$

To bound $\E{e^{\lambda (X_i - \mu_i)}}$, we use a symmetrization argument. Introducing
an independent copy of $X_i$ to express $\mu_i$ and a Rademacher (symmetric Bernoulli)
variable $\varepsilon$,

$$
\E{e^{\lambda (X_i - \mu_i)}}
= \Esub{X}{e^{\lambda (X_i - \E{X_i'})}} \\
\le \Esub{X_i, X_i'}{e^{\lambda (X_i - X_i')}}
= \Esub{\varepsilon}{\Esub{X_i, X_i'}{e^{\lambda \varepsilon (X_i - X_i')}}}
= \Esub{X_i, X_i'}{\Esub{\varepsilon}{e^{\lambda \varepsilon (X_i - X_i')}}}
= \Esub{X_i, X_i'}{\cosh(\lambda (X_i - X_i'))} \\
\le \Esub{X_i, X_i'}{e^{\lambda^2 (X_i - X_i')^2 / 2}}
\le e^{\lambda^2 (M_i - m_i)^2 / 2},
$$

where the first inequality follows from the convexity of the exponential function and
Jensen's, the second inequality follows from the bound for the hyperbolic cosine, and the
third inequality follows because $|X_i - X_i'| \le M_i - m_i$ for all $X_i, X_i'$.

Substituting this bound into the inequality for $\Pr{\sum_{i=1}^n (X_i - \mu_i) \ge t}$, we
obtain

$$
\Pr{\sum_{i=1}^n (X_i - \mu_i) \ge t}
\le \exp\left(
      -\lambda t + \frac{\lambda^2}{2} \sum_{i=1}^n (M_i - m_i)^2
    \right)
$$

The right hand side of this inequality is minimized when
$\lambda = \frac{t}{\sum_{i=1}^n (M_i - m_i)^2}$, which yields the tail bound

$$
\Pr{\sum_{i=1}^n (X_i - \mu_i) \ge t}
\le \exp\left( -\frac{t^2}{2 \sum_{i=1}^n (M_i - m_i)^2} \right).
$$

_Remark_. It is possible to tighten the bound to

$$
\Pr{\sum_{i=1}^n (X_i - \mu_i) \ge t}
\le \exp\left( -\frac{2 t^2}{\sum_{i=1}^n (M_i - m_i)^2} \right).
$$

--------------------------------------------------------------------------------------------
