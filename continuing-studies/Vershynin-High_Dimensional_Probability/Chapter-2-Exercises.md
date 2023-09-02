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
  Expected value of $X$ with respect to random variable $Y$: $\Esub{Y}{X}$

* $\newcommand{\Var}[1]{\operatorname{Var}{\left(#1\right)}}$
  Variance of $X$: $\Var{X}$

* $\newcommand{\normal}[2]{N\left({#1}, {#2}\right)}$
  Normal distribution with mean $\mu$ and variance $\sigma^2$: $\normal{\mu}{\sigma^2}$

* $\newcommand{\pois}[1]{\operatorname{Pois}\left({#1}\right)}$
  Poisson distribution with mean $\lambda$: $\pois{\lambda}$

--------------------------------------------------------------------------------------------

## 2.1. Why Concentration Inequalities?

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

## 2.2. Hoeffding's Inequality

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

__Solution__. Let $X_i$ be Bernoulli random variables that take the value 0 if the $i$-th
run of the algorithm is correct and 1 if the $i$-th run of the algorithm is incorrect.
Define $S_N = \sum_{i=1}^N X_i$, the random variable equal to the number of runs of the
algorithm that are incorrect. Note that $\E{S_N} = N(1/2 - \delta)$.

Observe that probability that the boosted algorithm is incorrect can be expressed as a tail
probability

$$
\Pr{S_N \ge N/2}
= \Pr{S_N - N(1/2 - \delta) \ge N \delta}
= \Pr{S_N - \E{S_N} \ge N \delta}.
$$

Hoeffding's inequality for general bounded random variables yields an upper bound for the
tail probability:

$$
\Pr{S_N \ge N/2}
\le e^{-2 N^2 \delta^2 / N}
= e^{-2 N \delta^2}.
$$

Therefore, if we choose $N \ge (1/2) \delta^{-2} \ln\left(\varepsilon^{-1}\right)$, the
probability that the boosted algorithm is incorrect is less than $\varepsilon$, which
implies that the probability that the boosted algorithm is correct is at least
$1 - \varepsilon$.

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

__Solution__. Let

$$
S_N = \frac{1}{N} \sum_{i=1}^N X_i.
$$

Then $\E{S_N} = \mu$ and $\Var{S_N} = \sigma^2 / N$. By Chebyshev's inequality,

$$
\Pr{|S_N - \mu| \ge t}
\le \frac{1}{(t / \Var{S_N})^2}
= \frac{\sigma^2}{N t^2}.
$$

Choosing $N \ge 4 \sigma^2 / \varepsilon^2 = O(\sigma^2 / \varepsilon^2)$ implies that

$$
\Pr{|S_N - \mu| \ge \varepsilon} \le 1/4.
$$

In other words, estimating the mean by computing $S_N$ using a sample of size
$N = O(\sigma^2 / \varepsilon^2)$ yields an $\varepsilon$-accurate estimate with probability
at least 3/4.

#### 2.2.9.b.

__Problem__. Show that a sample of size
$N = O\left( \log(\delta^{-1}) \sigma^2 / \varepsilon^2 \right)$ is sufficient to compute
an $\varepsilon$-accurate estimate with probability at least $1 - \delta$.

__Solution__. Let $M > 0$ be an even integer equal to the number of times we draw $R$
samples to estimate the mean $\mu$, let $S_{R,i}$ be the the arithmetic mean of the $i$-th
set of $R$ samples, and let $T_M$ be the median of $\{ S_{R,1}, \ldots, S_{R,M} \}$.
Using the same reasoning as in part (a), we can choose $R = O(\sigma^2 / \varepsilon^2)$ so
that $S_R$ is $\varepsilon$-accurate with probability at least 7/8. Observe that if
$T_M \ge \mu + \varepsilon$, then at least $M/2$ of the $S_{R,i}$ are greater than or equal
to $\mu + \varepsilon$, which implies that

$$
\Pr{T_M \ge \mu + \varepsilon}
\le \Pr{\textrm{at least $M/2$ of the $S_{R,i}$ are greater than or equal to
        $\mu + \varepsilon$}} \\
= \sum_{k=M/2}^M {M \choose k}
  \Pr{S_R \ge \mu + \varepsilon}^k \Pr{S_R < \mu + \varepsilon}^{M-k}
\le \sum_{k=M/2}^M {M \choose k} \Pr{|S_R - \mu| \ge \varepsilon}^k 1^{M-k} \\
\le \sum_{k=M/2}^M {M \choose k} \left( \frac{1}{8} \right)^k
\le {M \choose M/2}
  \sum_{k=M/2}^\infty \left( \frac{1}{8} \right)^k
= {M \choose M/2} \left(\frac{8}{7}\right) \left(\frac{1}{8}\right)^{M/2}.
$$

Using Stirling's approximation bounds,

$$
{M \choose M/2}
\le \sqrt{\frac{2}{\pi M}} \exp\left( \frac{1}{12M} - \frac{2}{12(M/2) + 1} \right)
  \left( \frac{M^M}{(M/2)^{M/2} (M/2)^{M/2}} \right)
\le \left(\frac{e^{1/24}}{\sqrt{\pi}}\right) 2^M.
$$

Therefore,

$$
\Pr{T_M \ge \mu + \varepsilon}
\le C \left( \frac{1}{2} \right)^{M/2},
$$

where $C = 8 e^{1/24} / 7 \sqrt{\pi}$.

Similar reasoning leads to an analogous bound for the probability that
$T_M \le \mu - \varepsilon$:

$$
\Pr{T_M \le \mu - \varepsilon}
\le C \left( \frac{1}{2} \right)^{M/2}.
$$

Combining these results yields

$$
\Pr{|T_M - \mu| \ge \varepsilon} \le 2C \left(\frac{1}{2}\right)^{M/2}.
$$

By choosing $M \ge -(2 \log 2) \log (\delta / 2C) = O(\log(\delta^{-1}))$, we find that
$T_M$ is a $\varepsilon$-accurate estimate for $\mu$ with probability at least $1 - \delta$
that requires only $N = O(MR) = O(\log(\delta^{-1}) \sigma^2 / \varepsilon^2)$ samples.

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
= \int_0^\infty e^{-t x} \p{x} dx
\le \int_0^\infty e^{-t x} dx
\le \left. -\frac{e^{-t x}}{t} \right|_{x=0}^{x=\infty}
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

_Remark_. The above choice of $\lambda$ minimizes $e^{\lambda t} \lambda^{-N}$ when
$t = \varepsilon N$. To see this, observe that to minimize
$e^{\lambda t} \lambda^{-N} = e^{\lambda t - N \ln \lambda}$, it is sufficient to minimize
the exponent. Setting the derivative of the exponent

$$
\frac{d}{d\lambda} \left( \lambda t - N \ln \lambda \right)
= t - \frac{N}{\lambda}
$$

to zero, we find that $\lambda_{\min} = N / t$. Therefore, for $t = \varepsilon N$,
$\lambda_{\min} = 1 / \varepsilon$.

--------------------------------------------------------------------------------------------

## 2.3. Chernoff's Inequality

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

## 2.4. Application: Degrees of Random Graphs

--------------------------------------------------------------------------------------------

### 2.4.2. (Bounding the degrees of sparse graphs)

__Problem__. Consider a random graph $G \sim G(n, p)$ with expected degrees $d = O(\log n)$.
Show that with high probability (say , 0.9), all the vertices of $G$ have degree
$O(\log n)$.

__Solution__. Let $d_i$ be the degree of vertex $i$. Then $d_i$ is the sum of $n - 1$
independent Bernoulli random variables (the indicators of the edges incident to $i$).
By Chernoff's inequality,

$$
\Pr{d_i \ge t} \le e^{-d} \left( \frac{e d}{t} \right)^t.
$$

Taking the union bound over all vertices,

$$
\Pr{\exists \ i \le n : d_i \ge t}
\le \sum_{i=1}^n \Pr{d_i \ge t}
\le n e^{-d} \left( \frac{e d}{t} \right)^t.
$$

Letting $t = C \ln n$, we obtain the bound

$$
\Pr{\exists \ i \le n : d_i \ge C \ln n}
\le n e^{-d} \left( \frac{e d}{C \ln n} \right)^{C \ln n}
= n e^{-d} \exp\left( (C \ln n) (1 + \ln d - \ln (C \ln n)) \right) \\
\le n^{1 + C (1 + \ln d - \ln (C \ln n))}
$$

Since $d = O(\ln n)$, there exists $D$ and $n_0$ such that

$$
d \le D \ln n
$$

for $n \ge n_0$. Assuming $n \ge n_0$,

$$
\ln d - \ln (C \ln n)
\le \ln (D \ln n) - \ln (C \ln n)
\le \ln D - \ln C.
$$

Let $p$ be the desired lower bound for the probability that all vertices have degree
less than $C \ln n$. Choosing $C$ sufficiently that large so that
$1 + C (1 + \ln D) - C \ln C \le \frac{\ln (1-p)}{\ln 2}$ (which is independent of $n$)
implies that

$$
n^{1 + C (1 + \ln d - \ln (C \ln n))}
\le n^{1 + C (1 + \ln D - \ln C)}
\le 2^{1 + C (1 + \ln D - \ln C)}
\le 1 - p.
$$

because $n \ge 2$ and $1 + C (1 + \ln D - \ln C) < 0$.

Therefore, we have the bound

$$
\Pr{\exists \ i \le n : d_i \ge C \ln n} \le 1 - p,
$$

which shows that the complementary event that all vertices have degree less than
$C \ln n = O(\log n)$ occurs with high probability (i.e., probability greater than $p$).

--------------------------------------------------------------------------------------------

### 2.4.3. (Bounding the degrees of very sparse graphs)

__Problem__. Consider a random graph $G \sim G(n, p)$ with expected degrees $d = O(1)$.
Show that with high probability (say, 0.9), all the vertices of $G$ have degree

$$
O\left( \frac{\log n}{\log \log n} \right).
$$

__Solution__. Following same initial reasoning from Problem 2.4.2, we have the bound

$$
\Pr{\exists \ i \le n : d_i \ge t}
\le \sum_{i=1}^n \Pr{d_i \ge t}
\le n e^{-d} \left( \frac{e d}{t} \right)^t
= n \left( C t \right)^{-t}
= n \exp \left( -t \ln (D t) \right)
$$

where $D$ is a constant and the second to last equality follows because $d = O(1)$.

Letting $t = \frac{C \ln n}{\ln \ln n}$, we obtain the bound

$$
\Pr{\exists \ i \le n : d_i \ge \frac{C \ln n}{\ln \ln n}}
\le n \exp \left( -\frac{C \ln n \ln \left(D \frac{C \ln n}{\ln \ln n} \right)}
                        {\ln \ln n} \right)
= n^{1 - \frac{C \ln \left(D \frac{C \ln n}{\ln \ln n} \right)}{\ln \ln n} } \\
\le n^{1 - \frac{C \ln \left(D C \ln n \right)}{\ln \ln n} }
= n^{1 - C \left( 1 + \frac{\ln D C}{\ln \ln n} \right) }
\le n^{1-C}.
$$

Let $p$ be the desired lower bound for the probability that all vertices have degree
less than $\frac{C \ln n}{\ln \ln n}$. Choosing $C \ge 1 - \frac{\ln(1-p)}{\ln 2}$
(which is independent of $n$) implies that $2^{1 - C} \le 1 - p$. Since $n \ge 2$ and
$1 - C < 0$, we arrive at the bound

$$
\Pr{ \exists \ i \le n : d_i \ge \frac{C \ln n}{\ln \ln n} }
\le n^{1-C}
\le 2^{1-C}
\le 1 - p.
$$

Therefore, the complementary event that all vertices have degree less than
$\frac{C \ln n}{\ln \ln n} = O\left( \frac{\log n}{\log \log n} \right)$ occurs with
high probability (i.e., probability greater than $p$).

--------------------------------------------------------------------------------------------

### 2.4.4. (Sparse graphs are not almost regular)

__Problem__. Consider a random graph $G \sim G(n, p)$ with expected degrees $d = o(\log n)$.
Show that, with high probability (say, 0.9), $G$ has a vertex with degree $10d$.

__Solution__. TODO

--------------------------------------------------------------------------------------------

### 2.4.5. (Very sparse graphs are far from being regular)

__Problem__. Consider a random graph $G \sim G(n, p)$ with expected degrees $d = O(1)$. Show
that, with high probability (say, 0.9), $G$ has a vertex whose degree is at least order

$$
\frac{\log n}{\log \log n}.
$$

__Solution__. TODO

--------------------------------------------------------------------------------------------

## 2.5. Sub-Gaussian Distributions

--------------------------------------------------------------------------------------------

### Tail Bound for the Standard Normal Distribution (Inequality 2.10)

__Problem__. Verify the following tail bound for the standard normal distribution.

$$
\Pr{|X| \ge t} \le 2 e^{-t^2/2}
$$

for all $t \ge 0$.

__Solution 1__. We consider the two cases $t \ge 1 / \sqrt{2 \pi}$ and
$t < 1 / \sqrt{2 \pi}$ separately. For the first case, the bound

$$
\Pr{X \ge t} \le \frac{1}{t \sqrt{2 \pi}} e^{-t^2/2}
$$

(which holds for all $t \ge 0$) implies that

$$
\Pr{X \ge t} \le e^{-t^2/2}
$$

for $t \ge 1 / \sqrt{2 \pi}$. Therefore, symmetry of the standard normal distribution about
$X = 0$ implies that $\Pr{|X| \ge t} \le 2 e^{-t^2/2}$.

For the case $t < 1 / \sqrt{2 \pi}$, observe that

$$
\Pr{|X| \ge t}
= 1 - \frac{1}{\sqrt{2 \pi}} \int_{-t}^t e^{-s^2/2} ds
\le 1 - \frac{2t e^{-t^2/2}}{\sqrt{2 \pi}}
\le \exp\left( -\frac{2t e^{-t^2/2}}{\sqrt{2 \pi}} \right)
$$

where the first inequality follows because $e^{-t^2/2}$ is the minimum of $e^{-s^2/2}$ on
the interval $[0, t]$ and the second inequality follows because $1 + x \le e^x$. We can
further bound the $\Pr{|X| \ge t}$ by observing that

$$
\frac{t^2}{2} - \alpha t \le 0
$$

when $0 \le t \le 2 \alpha$, which implies that

$$
-\frac{t^2}{2} \ge -t \sqrt{\frac{2}{\pi e}}
$$

when $0 \le t \le \sqrt{8 / \pi e}$. Therefore,

$$
\Pr{|X| \ge t}
\le \exp\left( -t e^{-t^2/2}\sqrt{\frac{2}{\pi}} \right)
\le \exp\left( -t e^{-1/2}\sqrt{\frac{2}{\pi}} \right)
= \exp\left( -t \sqrt{\frac{2}{\pi e}} \right)
\le e^{-t^2/2}
\le 2 e^{-t^2/2}
$$

when $0 \le t \le 1 / \sqrt{2 \pi} < \sqrt{8 / \pi e}$.

__Solution 2__. We consider the two cases $t \ge 1$ and $t < 1$ separately. For the first
case, the bound

$$
\Pr{X \ge t} \le \frac{1}{t \sqrt{2 \pi}} e^{-t^2/2}
$$

(which holds for all $t \ge 0$) implies that

$$
\Pr{X \ge t}
\le \frac{1}{\sqrt{2 \pi}} e^{-t^2/2}
\le e^{-t^2/2}
$$

for $t \ge 1$. Therefore, symmetry of the standard normal distribution about $X = 0$
implies that $\Pr{|X| \ge t} \le 2 e^{-t^2/2}$.

For the case $t < 1$, observe that $1 \le 2 e^{-1/2}$, which implies the desired result
because

$$
\Pr{|X| \ge t}
\le 1
\le 2 e^{-1/2}
\le 2 e^{-t^2/2}.
$$

--------------------------------------------------------------------------------------------

### 2.5.1. (Moments of the normal distribution)

__Problem__. Show that, for each $p \ge 1$, the random variable $X \sim \normal{0}{1}$
satisfies

$$
\Vert X \Vert_{L^p} = \left( \E{|X|^p} \right)^{1/p}
= \sqrt{2} \left( \frac{\Gamma((1+p) / 2)}{\Gamma(1/2)} \right)^{1/p}
$$

__Solution__. Observe that

$$
\E{|X|^p}
= \int_{-\infty}^\infty |x|^p \frac{1}{\sqrt{2 \pi}} e^{-x^2/2} dx
= \frac{\sqrt{2}}{\sqrt{\pi}} \int_0^\infty x^p e^{-x^2/2} dx
= \frac{\sqrt{2}}{\Gamma(1/2)} \int_0^\infty x^p e^{-x^2/2} dx.
$$

Using the change variables $s = x^2 / 2$,

$$
\int_0^\infty x^p e^{-x^2/2} dx
= 2^{(p-1) / 2} \int_0^\infty s^{p/2 - 1/2} e^{-s} ds
= 2^{(p-1) / 2} \Gamma((1+p) / 2).
$$

Combining these results, we obtain

$$
\E{|X|^p}
= \left( \frac{\sqrt{2}}{\Gamma(1/2)} \right) 2^{(p-1) / 2} \Gamma((1+p) / 2)
= \frac{2^{p/2} \Gamma((1+p) / 2)}{\Gamma(1/2)},
$$

which implies that

$$
\Vert X \Vert_{L^p}
= \left( \E{|X|^p} \right)^{1/p}
= \sqrt{2} \left( \frac{\Gamma((1+p) / 2)}{\Gamma(1/2)} \right)^{1/p}.
$$

--------------------------------------------------------------------------------------------
