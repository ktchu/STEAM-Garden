Randomized Algorithms (R. Motwani & P. Raghavan): Chapter 6 Exercises
=====================================================================

--------------------------------------------------------------------------------------------
### Notation

* $\newcommand{\Pr}[1]{\mathbb{P}\left[{#1}\right]}$
  Probability of event $E$: $\Pr{E}$

* $\newcommand{\E}[1]{\mathbb{E}\left[{#1}\right]}$
  Expected value of $X$: $\E{X}$

--------------------------------------------------------------------------------------------
### Exercise 6.1.

Let $G$ be the complete graph $K_n$ on $n$ vertices. Let $u$ and $v$ be two vertices in $G$.

#### 6.1.1.

__Problem__. Prove that the expected number of steps in a simple random walk that begins
at $u$ and ends upon first reaching $v$ is $n-1$.

__Solution__.  Define the random variable $S_{ij}$ to be the number of steps between $i$
and $j$ for any acyclic path from $i$ to $j$. Note that $S_{ii} = 0$ for all $i$.

Using a first-step analysis, we can compute the desired expected value as

$$
\begin{align}
\E{S_{uv}}
&= 1 + \left(
          \Pr{\textrm{first step ends at $v$}} \E{S_{vv}}
        + \Pr{\textrm{first step ends at $w \ne v$}} \E{S_{wv}}
        \right) \\
&= 1 + \Pr{\textrm{first step ends at $w \ne v$}} \E{S_{wv}}
\end{align}
$$

Observing that $\E{S_{wv}} = \E{S_uv}$ for all $w \ne v$ (because they are all equivalent)
and that

$$
\Pr{\textrm{first step ends at $w \ne v$}} = (n-2) / (n-1),
$$

the first-step analysis equation becomes

$$
\E{S_{uv}} = 1 + \left(\frac{n-2}{n-1}\right) \E{S_{uv}}.
$$

Solving this equation for $\E{S_{uv}}$ yields the desired result.

#### 6.1.2.

__Problem__. Prove that the expected number of steps to visit all the vertices in $G$
starting from $u$ is $(n-1) H_{n-1}$ where $H_n = \sum_{j=1}^n 1/j$ it the $n$-th Harmonic
number.

__Solution__. TODO

--------------------------------------------------------------------------------------------
