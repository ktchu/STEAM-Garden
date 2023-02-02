An Introduction to Stochastic Modeling (Taylor and Karlin): Exercises 1.3
=========================================================================

--------------------------------------------------------------------------------------------
## 0. Notation

* $\newcommand{\Pr}[1]{{\mathbb{P}\left[{#1}\right]}}$
  Probability of event $E$: $\Pr{E}$

* $\newcommand{\p}[1]{{p\left({#1}\right)}}$
  Probability density (or mass) function for a random variable $X$: $\p{x}$

* $\newcommand{\E}[1]{{\mathbb{E}\left[{#1}\right]}}$
  Expected value of $X$: $\E{X}$

* $\newcommand{\Var}[1]{{\operatorname{Var}}{\left(#1\right)}}$
  Variance of $X$: $\Var{X}$

--------------------------------------------------------------------------------------------
### 3.1.

__Problem__. Consider tossing a fair coin five times and counting the total number of heads
that appear. What is the probability that this total is three?

__Solution__.

$$
\Pr{\textrm{three heads appear out of five tosses}}
= {5 \choose 3}\left( \frac{1}{2} \right)^5
= \frac{5}{16}
$$

--------------------------------------------------------------------------------------------
### 3.2.

__Problem__. A fraction $p = 0.05$ of the items coming off a production process are
defective. If a random sample of 10 items is taken from the output of the process, what is
the probability that the sample contains exactly one defective item? What is the probaility
that the sample contains one or fewer defective items?

__Solution__.

$$
\Pr{\textrm{exactly one defective item}}
= {10 \choose 1} p (1-p)^9
\approx 0.315
$$

$$
\Pr{\textrm{one or fewer defective item}}
= (1-p)^10 + {10 \choose 1} p (1-p)^9
\approx 0.914
$$

--------------------------------------------------------------------------------------------
### 3.3.

__Problem__. A fraction $p = 0.05$ of the items coming off a production process are
defective. The output of the process is sampled, one by one, in a random manner. What is
the probability that the first defective item found is the tenth item sampled?

__Solution__.

$$
\Pr{\textrm{first defective item is the tenth item sampled}}
= (1-p)^9 p
\approx 0.0315
$$

--------------------------------------------------------------------------------------------
### 3.4.

__Problem__. A Poisson distributed random variable $X$ has a mean of $\lambda = 2$. What
is the probability that $X$ equals 2? What is the probability that $X$ is less than or
equal to 2?

__Solution__.

$$
\Pr{X = 2}
= \frac{\lambda^2 e^{-\lambda}}{2!}
= 2 e^{-2}
\approx 0.271
$$

$$
\Pr{X \le 2}
= \frac{\lambda^0 e^{-\lambda}}{0!}
  + \frac{\lambda^1 e^{-\lambda}}{1!}
  + \frac{\lambda^2 e^{-\lambda}}{2!}
= e^{-2} \left( 1 + 2 + \frac{2^2}{2} \right)
\approx 0.677
$$

--------------------------------------------------------------------------------------------
### 3.5.

__Problem__. The number of bacteria in a prescribed area of a slide containing a sample of
well water has a Poisson distribution with paramerter 5. What is the probability that the
slide shows 8 or more bacteria?

__Solution__. Let $X$ be a random variable representing the number of bacteria observed in
the area of the slide. Then

$$
\Pr{X \ge 8}
= 1 - \sum_{k=0}^8 \frac{\lambda^k e^{-\lambda}}{k!}
= 1 - e^{-8} \sum_{k=0}^8 \frac{8^k}{k!}
\approx 0.407
$$

--------------------------------------------------------------------------------------------
### 3.6.

The discrete uniform distribution on $\{ 1, \ldots, n \}$ corresponds to the probability
mass function

$$
\p(k)
= \left\{
    \begin{array}{cl}
    \frac{1}{n} & \textrm{for $k = 1, \ldots, n$} \\
    0 & \textrm{elsewhere}.
    \end{array}
  \right.
$$

#### 3.6.a

__Problem__. Determine the mean and variance.

__Solution__.

$$
\E{k}
= \frac{1}{n} \left( \sum_{k=1}^n k \right)
= \frac{1}{n} \left( \frac{n(n+1)}{2} \right)
= \frac{n+1}{2}
$$

$$
\begin{align}
\Var{k}
&= \E{k^2} - \E{k}^2 \\
&= \frac{1}{n} \left( \sum_{k=1}^n k^2 \right) - \left( \frac{n+1}{2} \right)^2 \\
&= \frac{1}{n} \left( \frac{n (n+1) (2n+1)}{6} \right) - \left( \frac{n+1}{2} \right)^2 \\
&= \frac{(n+1) (2n+1)}{6} - \left( \frac{n+1}{2} \right)^2 \\
&= \frac{n^2 - 1}{12}
\end{align}
$$

#### 3.6.b

__Problem__. Suppose $X$ and $Y$ are independent random variables, each having the discrete
uniform distribution on $\{0, \ldots, n \}.$ Determine the probability mass function for
the sum $Z = X + Y$.

__Solution__. The probability mass function for $Z$ is the discrete convolution of the
probability mass functions of $X$ and $Y$:

$$
\begin{align}
\Pr{Z=k}
&= \sum_{i=1}^n p(i) p(k-i) \\
&= \frac{\textrm{(number of terms where $1 \le i, k-i \le n$)}}{n^2} \\
&= \left\{
     \begin{array}{cl}
        \frac{\min(k - 1, 2n - k + 1)}{n^2} & \textrm{for $2 \le k \le 2n$} \\
                                  0 & \textrm{elsewhere.}
     \end{array}
   \right.
\end{align}
$$

#### 3.6.c

__Problem__. Under the assumptions of (b), determine the probability mass function for the
minimum $U = \min\{ X, Y \}$.

__Solution__. For $1 \le k \le n$, $U = k$ if and only if one of the three mutually
exclusive events occur:

* $X = k$ and $Y > k$,
* $Y = k$ and $X > k$, or
* $X = k$ and $Y = k$.

Therefore, by the addition law for probability

$$
\begin{align}
\Pr{U = k}
&= \Pr{\textrm{$X = k$ and $Y > k$}}
 + \Pr{\textrm{$Y = k$ and $X > k$}}
 + \Pr{\textrm{$X = k$ and $Y = k$}} \\
&= \left(\frac{1}{n}\right) \left(\frac{n-k}{n}\right)
 + \left(\frac{n-k}{n}\right) \left(\frac{1}{n}\right)
 + \frac{1}{n^2} \\
&= \frac{2 (n - k) + 1}{n^2}.
\end{align}
$$

For $k \le 0$ or $k \ge n$, $\Pr{U = k} = 0$.

Note that

$$
\sum_{k=1}^n \Pr{U = k}
= \frac{1}{n^2} \sum_{k=1}^n 2(n-k) + 1
= \frac{1}{n^2} \left( 2 \frac{n (n - 1)}{2} + n \right)
= 1
$$

as required for a probability mass function.

--------------------------------------------------------------------------------------------
