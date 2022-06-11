High-Dimensional Probability (Vershynin): Exercises - Chapter 1
===============================================================

--------------------------------------------------------------------------------------------

### 1.2.2. Generalization of integral identity

__Problem__. Prove the following extension of Lemma 1.2.1 which is valid for any random
variable $X$ (not necessarily non-negative):

\[
\mathbb{E} X
= \int_0^\infty \mathbb{P}\{ X > t \} dt
- \int_{-\infty}^0 \mathbb{P}\{ X < t \} dt
\]

__Solution__. For all real $x$, we have the identity

\[
  x = \int_0^\infty \mathbf{1}_{\{t < x \}} dt
    - \int_{-\infty}^0 \mathbf{1}_{\{t > x \}} dt.
\]

Substituting the random variable $X$ and taking expectation of both sides yields the
desired result

\[
  \mathbb{E} X
= \mathbb{E} \int_0^\infty \mathbf{1}_{\{t < X \}} dt
- \mathbb{E} \int_{-\infty}^0 \mathbf{1}_{\{t > X \}} dt
= \int_0^\infty \mathbb{E} \mathbf{1}_{\{t < X \}} dt
- \int_{-\infty}^0 \mathbb{E} \mathbf{1}_{\{t > X \}} dt
= \int_0^\infty \mathbb{P} \{t < X \} dt
- \int_{-\infty}^0 \mathbb{P} \{t > X \} dt.
\]

Changing the order of expection and integration is justified by the Fubini-Tonelli theorem.

--------------------------------------------------------------------------------------------

### 1.2.3. $p$-th moment via the tail

__Problem__. Let $X$ be a random varable and $p \in (0, \infty)$. Show that

\[
  \mathbb{E} |X|^p = \int_0^\infty p t^{p-1} \mathbb{P}\{ |X| > t \} dt
\]

whenever the right-hand side is finite.

__Solution__. Applying the integral identity to $|X|^p$, we find that

\[
  \mathbb{E} |X|^p
= \int_0^\infty \mathbb{P}\{ |X|^p > s \} ds.
\]

Using the change of variables $s = t^p$ yields the desired result:

\[
  \mathbb{E} |X|^p
= \int_0^\infty p t^{p-1} \mathbb{P}\{ |X|^p > t^p \} dt
= \int_0^\infty p t^{p-1} \mathbb{P}\{ |X| > t \} dt.
\]

--------------------------------------------------------------------------------------------

### 1.2.6. Chebyshev's Inequality

__Problem__. Deduce Chebyshev's inequality

\[
  \mathbb{P} \left\{ |X - \mu| \ge t \right\} \le \frac{\sigma^2}{t^2}
\]

by squaring both sides of the bound $|X - \mu| \ge t$ and applying Markov's
inequality.

__Solution__.

\[
  \mathbb{P} \left\{ |X - \mu| \ge t \right\}
= \mathbb{P} \left\{ |X - \mu|^2 \ge t^2 \right\}
\le \frac{\mathbb{E} |X - \mu|^2}{t^2}
= \frac{\sigma^2}{t^2}
\]

where the inequality follows from Markov's inequality and the last equality
follows from the definition of the variance.

--------------------------------------------------------------------------------------------

### 1.3.3. Expected Deviation Between Sample and Population Mean is $O(1 / \sqrt{N})$

__Problem__. Let $X_1, X_2, \ldots$ be a sequence of i.i.d. random varaibles
with mean $\mu$ and finite variance. Show that

\[
  \mathbb{E} \left| \frac{1}{N} \sum_{i=1}^N X_i - \mu \right|
= O\left(\ \frac{1}{\sqrt{N}} \right)
\]

as $N \rightarrow \infty$.

__Solution__. From the integral identity, we have

\[
  \mathbb{E} \left| \frac{1}{N} \sum_{i=1}^N X_i - \mu \right|
= \int_0^\infty
  \mathbb{P} \left\{
    \left| \frac{1}{N} \sum_{i=1}^N X_i - \mu \right| > t
  \right\} dt
= \int_0^\infty
  \mathbb{P} \left\{ |Z_N| > \frac{\sqrt{N}}{\sigma} t \right\} dt.
\]

Using the change of variables $s = t \sqrt{N} / \sigma $, the integral becomes

\[
  \int_0^\infty \frac{\sigma}{\sqrt{N}} \mathbb{P} \{ |Z_N| > s \} ds.
\]

By the Central Limit Theorem,

\[
\mathbb{P} \{ |Z_N| > s \}
\rightarrow \frac{2}{\sqrt{2 \pi}} \int_s^\infty e^{-x^2/2} dx
= \sqrt{\frac{2}{\pi}} \int_s^\infty e^{-x^2/2} dx
\]

as $N \rightarrow \infty$.

Therefore, in the limit of large $N$, the integral for the expectation (with constant
factors suppressed to reduce clutter) tends towards

\[
  \int_0^\infty \int_s^\infty e^{-x^2/2} dx ds
= \int_0^\infty \int_0^x e^{-x^2/2} ds dx
= \int_0^\infty e^{-x^2/2} \int_0^x ds dx
= \int_0^\infty x e^{-x^2/2} dx
= 1,
\]

where changing the order of integration leads to the first equality. Combining these
results yields the desired result

\[
\mathbb{E} \left| \frac{1}{N} \sum_{i=1}^N X_i - \mu \right|
\rightarrow \sigma \sqrt{\frac{2}{N \pi}}
= O\left(\ \frac{1}{\sqrt{N}} \right)
\]

as $N \rightarrow \infty$.

--------------------------------------------------------------------------------------------
