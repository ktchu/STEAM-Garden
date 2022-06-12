High-Dimensional Probability (Vershynin): Exercises - Chapter 2
===============================================================

--------------------------------------------------------------------------------------------

### Notation

* $\newcommand{\Pr}[1]{{\mathbb{P}\left[{#1}\right]}}$
  Probability of event $E$: $\Pr{E}$

* $\newcommand{\1}[1]{{\mathbf{1}_{\left\{{#1}\right\}}}}$
  Indicator for event $E$: $\1{E}$

* $\newcommand{\p}[1]{{p\left({#1}\right)}}$
  Probability density (or mass) function for a random variable $X$: $\p{x}$

* $\newcommand{\E}[1]{{\mathbb{E}\left[{#1}\right]}}$
  Expected value of $X$: $\E{X}$

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
