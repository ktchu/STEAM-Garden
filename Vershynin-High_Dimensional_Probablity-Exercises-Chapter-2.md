High-Dimensional Probability (Vershynin): Exercises - Chapter 2
===============================================================

--------------------------------------------------------------------------------------------

### Notation

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

* $\newcommand{\Esub}[2]{\mathbb{E}_{#1}\left[{#2}\right]}$
  Expected value of $XY$ with respect to $X$: $\Esub{X}{XY}$

* $\newcommand{\Var}[1]{\operatorname{Var}{\left(#1\right)}}$
  Variance of $X$: $\Var{X}$

* $\newcommand{\normal}[2]{N\left({#1}, {#2}\right)}$
  Normal distribution with mean $\mu$ and variance $\sigma^2$: $\normal{\mu}{\sigma^2}$

* $\newcommand{\pois}[1]{\operatorname{Pois}\left({#1}\right)}$
  Poisson distribution with mean $\lambda$: $\pois{\lambda}$

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
an independent copy of $X_i$ to express $\mu_i$ and a symmetric Bernoulli (Rademacher)
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

### 2.2.8. (Boosting Randomized Algorithms)

__Problem__. Imagine we have an algorithm for solving some decision problem (e.g., is a
given number $p$ a prime?). Suppose that the algorithm makes a decision at random and
returns the correct answer with probability $1/2 + \delta$, for some $\delta > 0$, which is
just a bit better than a random guess. To improve the performance, we run the algorithm
$N$ times and take the majority vote. Show that, for any $\varepsilon \in (0, 1)$, the
answer is correct with probability at least $1 - \varepsilon$, as long as
$N \ge (1/2) \delta^{-2} \ln(\varepsilon^{-1})$.

__Solution__. TODO

--------------------------------------------------------------------------------------------

### 2.2.9. (Robust Estimation of the Mean)

Suppose that we want to estimate the mean $\mu$ of a random variable $X$ from a sample
$X_1, \ldots, X_N$ drawn independently from the distribution of $X$. We want an
$\varepsilon$-accurate estimate, i.e., one that falls in the interval
$(\mu - \varepsilon,\mu + \varepsilon)$.

#### 2.2.9.a.

__Problem__. Show that a sample of size $N = O(\sigma^2 / \varepsilon^2)$ is sufficient
to compute an $\varepsilon$-accurate estimate with probability at least 3/4, where
$\sigma^2 = \Var{X}$.

__Solution__. TODO

#### 2.2.9.b.

__Problem__. Show that a sample of size
$N = O\left( \log(\delta^{-1}) \sigma^2 / \varepsilon^2 \right)$ is sufficient to compute
an $\varepsilon$-accurate estimate with probability at least $1 - \delta$.

__Solution__. TODO

--------------------------------------------------------------------------------------------

### 2.2.10. (Small Ball Probabilities)

Let $X_1, \ldots, X_N$ be _non-negative_ independent random variables with
continuous distributions. Assume that the densities of $X_i$ are uniformly bounded by 1.

#### 2.2.10.a.

__Problem__. Show that the MGF of $X_i$ satisfies

$$
\E{\exp(-t X_i)} \le \frac{1}{t}
$$

for all $t > 0$.

__Solution__. For $t > 0$,

$$
\E{\exp(-t X_i)}
= \int_{-\infty}^\infty e^{-t x} \p{x} dx
\le \int_{-\infty}^\infty e^{-t x} dx
\le \left. -\frac{e^{-t x}}{t} \right|_{-\infty}^\infty
= \frac{1}{t}
$$

#### 2.2.10.b.

__Problem__. Deduce that, for any $\varepsilon > 0$, we have

$$
\Pr{\sum_{i=1}^N X_i \le \varepsilon N} \le (e \varepsilon)^N.
$$

__Solution__. For $t > 0$, consider

$$
\Pr{\sum_{i=1}^N X_i \le t} = \Pr{-\sum_{i=1}^N X_i \ge -t}.
$$

Multiplying by $\lambda > 0$, exponentiating, and applying Markov's inequality and
independence of the $X_i$, we obtain

$$
\Pr{\sum_{i=1}^N X_i \le t} \le e^{\lambda t} \prod_{i=1}^N \E{e^{-\lambda X_i}}.
$$

Using the bound from part (a),

$$
\Pr{\sum_{i=1}^N X_i \le t} \le \frac{e^{\lambda t}}{\lambda^{N}}
$$

Choosing $\lambda = 1 / \varepsilon$ and substituting $t = \varepsilon N$ yields

$$
\Pr{\sum_{i=1}^N X_i \le \varepsilon N}
\le e^{\varepsilon N / \varepsilon} \varepsilon^N
= \left( e \varepsilon \right)^N.
$$


--------------------------------------------------------------------------------------------

### 2.3.2. (Chernoff's Inequality - Lower Tails)

__Problem__. Modify the proof of Theorem 2.3.1 to obtain the following bound on the lower
tail. For any $t < \mu$, we have

$$
\Pr{S_N \le t} \le e^{-\mu} \left(\frac{e \mu}{t} \right)^t
$$

__Solution__. Observe that for $\lambda > 0$, $S_N \le t$ is equivalent to

$$
e^{-\lambda S_N} \ge e^{-\lambda t}.
$$

Therefore, Markov's inequality and independence imply that

$$
\Pr{e^{-\lambda S_N} \ge e^{-\lambda t}}
\le e^{\lambda t} \prod_{i=1}^N \E{e^{-\lambda X_i}}.
$$

Since $X_i$ is a Bernoulli random variable with probability $p_i$,

$$
\E{e^{-\lambda X_i}}
= p_i e^{-\lambda} + (1 - p_i)
= 1 + p_i \left( e^{-\lambda} - 1 \right)
\le \exp\left( p_i \left( e^{-\lambda} - 1 \right) \right),
$$

which implies that

$$
\prod_{i=1}^N \E{e^{-\lambda X_i}}
\le \exp\left( \left( e^{-\lambda} - 1 \right) \sum_{i=1}^N p_i \right)
= \exp\left( \left( e^{-\lambda} - 1 \right) \mu \right).
$$

Therefore,

$$
\Pr{S_N \le t}
\le e^{\lambda t} \exp\left( \left( e^{-\lambda} - 1 \right) \mu \right).
$$

Since this bound holds for any $\lambda > 0$, we can choose
$\lambda = -\ln(t / \mu)$, which is positive because $t < \mu$. With this value of
$\lambda$, we obtain the desired bound

$$
\Pr{S_N \le t} \le e^{-\mu} \left( \frac{e \mu}{t} \right)^t.
$$

--------------------------------------------------------------------------------------------

### 2.3.3. (Poisson Tails)

__Problem__. Let $X \sim \pois{\lambda}$. Show that, for any $t > \lambda$, we have

$$
\Pr{X \ge t} \le e^{-\lambda} \left(\frac{e \lambda}{t} \right)^t.
$$

__Solution__. Let $S_N$ be a sequence of sums of independent Bernoulli random variables
such that $\max_{i \le N} p_{N,i} \rightarrow 0$ and $\E{S_N} \rightarrow \lambda < \infty$
as $N \rightarrow \infty$ so that $S_N \rightarrow \pois{\lambda} $ in distribution as
$N \rightarrow \infty$. From Chernoff's inequality,

$$
\Pr{S_N \ge t} \le e^{-\lambda} \left( \frac{e \lambda}{t} \right)^t
$$

for all $N$. Therefore,

$$
\Pr{X \ge t}
= \lim_{N \rightarrow \infty} \Pr{S_N \ge t}
\le e^{-\lambda} \left( \frac{e \lambda}{t} \right)^t.
$$

--------------------------------------------------------------------------------------------

### 2.3.5. (Chernoff's Inequality: small deviations)

__Problem__. Show that, in the setting of Theorem 2.3.1, for $\delta \in (0, 1]$ we have

$$
\Pr{|S_N - \mu| \ge \delta \mu} \le 2 e^{-c \mu \delta^2}
$$

where $c > 0$ is an absolute constant.

__Solution__. When $S_N \ge \mu$, we have

$$
\Pr{S_N - \mu \ge \delta \mu} = \Pr{S_N \ge (1 + \delta) \mu}.
$$

From the proof of Chernoff's inequality before selecting a value for $\lambda > 0$, we
can conclude that

$$
\Pr{S_N - \mu \ge \delta \mu}
\le e^{-\lambda (1 + \delta) \mu} \exp\left( \left(e^\lambda - 1 \right) \mu \right).
$$

Using the bound $e^x \le 1 + (1 + \alpha)x$ for $0 \le x \le \alpha/2$ with
$\alpha = \delta/2$, we obtain

$$
\Pr{S_N - \mu \ge \delta \mu}
\le e^{-\lambda (1 + \delta) \mu} e^{\lambda (1 + \delta/2) \mu}
= e^{-\lambda \mu \delta / 2}.
$$

Choosing $\lambda = \delta / 4$ yields

$$
\Pr{S_N - \mu \ge \delta \mu}
\le e^{-\mu \delta^2 / 8}.
$$

For the case $S_N \le \mu$, we have

$$
\Pr{\mu - S_N \ge \delta \mu} = \Pr{S_N \le (1 - \delta) \mu}.
$$

Proceeding as in the solution to Exercise 2.3.2 yields

$$
\Pr{\mu - S_N \ge \delta \mu}
\le e^{\lambda (1 - \delta) \mu} \exp\left( \left(e^{-\lambda} - 1 \right) \mu \right).
$$

Since $\lambda > 0$, $e^{-\lambda} \le 1 - \lambda + \lambda^2/2$, which implies that

$$
\Pr{\mu - S_N \ge \delta \mu} \le e^{-\lambda \mu (\delta - \lambda / 2)}.
$$

Choosing $\lambda = \delta$ yields

$$
\Pr{\mu - S_N \ge \delta \mu}
\le e^{-\mu \delta^2 / 2}
\le e^{-\mu \delta^2 / 8}.
$$

Combining the one-sided concentration bounds, we obtain the desired two-sided
concentration bound

$$
\Pr{|S_N - \mu| \ge \delta \mu} \le 2 e^{-c \mu \delta^2}
$$

with $c = 1/8$.

--------------------------------------------------------------------------------------------

### 2.3.6. (Poisson distribution near the mean)

__Problem__. Let $X \sim \pois{\lambda}$. Show that for $t \in (0, \lambda]$, we jhave

$$
\Pr{|X - \lambda| \ge t} \le 2 \exp\left( -\frac{c t^2}{\lambda} \right).
$$

__Solution__. Let $S_N$ be a sequence of sums of independent Bernoulli random variables
such that $\max_{i \le N} p_{N,i} \rightarrow 0$ and $\E{S_N} \rightarrow \lambda < \infty$
as $N \rightarrow \infty$ so that $S_N \rightarrow \pois{\lambda} $ in distribution as
$N \rightarrow \infty$. From Chernoff's inequality for small deviations

$$
\Pr{|S_N - \lambda| \ge t}
\le 2 \exp\left( -c \lambda \left(\frac{t}{\lambda}\right)^2 \right)
= 2 \exp\left( -\frac{c t^2}{\lambda} \right).
$$

for all $N$. Therefore,

$$
\Pr{|X - \lambda| \ge t}
= \Pr{X - \lambda \le -t} + \Pr{X -\lambda \ge t}
=   \lim_{N \rightarrow \infty} \Pr{S_N - \lambda \le -t}
  + \lim_{N \rightarrow \infty} \Pr{S_N - \lambda \ge t} \\
= \lim_{N \rightarrow \infty}
  \left( \Pr{S_N - \lambda \le -t} + \Pr{S_N - \lambda \ge t} \right)
= \lim_{N \rightarrow \infty} \Pr{|S_N - \lambda| \ge t}
\le 2 \exp\left( -\frac{c t^2}{\lambda} \right).
$$

--------------------------------------------------------------------------------------------

### 2.3.8. (Normal approximation to the Poisson distribution)

__Problem__. Let $X \sim \pois{\lambda}$. Show that, as $\lambda \rightarrow \infty$, we
have

$$
\frac{X - \lambda}{\sqrt{\lambda}} \rightarrow \normal{0}{1} \textrm{ in distribution}.
$$

__Solution__. Let $X_i \sim \pois{1}$ and $X = \sum_{i=1}^\lambda X_i$. Then
$X \sim \pois{\lambda}$ (which can be shown by computing the moment generating
function of $X$). Therefore, by the Central Limit Theorem,

$$
\frac{X - \lambda}{\sqrt{\lambda}} \rightarrow \normal{0}{1}
\textrm{ in distribution}.
$$

--------------------------------------------------------------------------------------------
