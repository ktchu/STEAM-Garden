Linear and Geometric Algebra (A. Macdonald): Chapter 5
======================================================

## Exercises: Section 5.1

-------------------------------------------------------------------------------

### 5.1.

__Problem__. Let $\mathbf{B}$ be an oriented area. Identify
$(-1) \mathbf{B}$ geometrically.

__Solution__. $(-1) \mathbf{B}$ is an oriented area that is parallel to
$\mathbf{B}$, has the same norm as $\mathbf{B}$, and has the opposite
orientation.

### 5.2.

__Problem__. Let $\mathbf{B}$ be a nonzero oriented area. Let $\mathbf{C} $ be
another oriented area in the same plane. Show that $\mathbf{C}$ is a scalar
multiple of $\mathbf{B}$.

__Solution__. Let $b = |\mathbf{B}| \ne 0$ and $c = |\mathbf{C}|$. Then
$(c / b) \mathbf{B}$ is an oriented area area parallel to $\mathbf{B}$ with
norm equal to $(c / b) b = c$. Therefore, $(c / b) \mathbf{B}$ and
$\mathbf{C}$ are parallel and have the same norm. If $\mathbf{B}$ and
$\mathbf{C}$ have the same orientation, then $(c / b) \mathbf{B} = \mathbf{C}$.
If they have opposite orientations, then $-(c / b) \mathbf{B} = \mathbf{C}$.
In either case, $\mathbf{C}$ is scalar multiple of $\mathbf{B}$.

### 5.3.

__Problem__. Prove vector space Axiom V6 for oriented areas:
$a (b \mathbf{B}) = (ab) \mathbf{B}$.

__Solution__. $b \mathbf{B}$ is an oriented area parallel to $\mathbf{B}$
with norm $|b|$ times $|\mathbf{B}|$. $a (b \mathbf{B})$ is an oriented
area with norm $|a|$ times $|b \mathbf{B}|$, so it has norm $|ab|$ times
$|\mathbf{B}|$. $(ab) \mathbf{B}$ is also an oriented area with norm $|ab|$
times $|\mathbf{B}|$, so $|a (b \mathbf{B})| = |(ab) \mathbf{B}|$. It is
straightforward to check that $a (b \mathbf{B})$ and $(ab) \mathbf{B}$ have
the same orientation for all four cases of the sign of $a$ and $b$. Since
$a (b \mathbf{B})$ and $(ab) \mathbf{B}$ are parallel, have the same norm, and
have the same orientation, they are equal.

### 5.4.

__Problem__. Prove Eq. (5.3).

\[
\mathbf{u} \wedge \mathbf{v}
=   (u_3 v_2 - u_2 v_3) \mathbf{e}_3 \wedge \mathbf{e}_2
  + (u_1 v_3 - u_3 v_1) \mathbf{e}_1 \wedge \mathbf{e}_3
  + (u_2 v_1 - u_1 v_2) \mathbf{e}_2 \wedge \mathbf{e}_1
\]

__Solution__. Expanding $\mathbf{u}$ and $\mathbf{v}$ in terms of an
orthonormal basis $\{ \mathbf{e}_1, \mathbf{e}_2, \mathbf{e}_3 \}$ and using
the properties of the outer product from Theorem 5.2, we find that

\[
\mathbf{u} \wedge \mathbf{v}
=        (u_1 \mathbf{e}_1 + u_2 \mathbf{e}_2 + u_3 \mathbf{e}_3)
  \wedge (v_1 \mathbf{e}_1 + v_2 \mathbf{e}_2 + v_3 \mathbf{e}_3) \\
=    u_1 v_1 \mathbf{e}_1 \wedge \mathbf{e}_1
  +  u_1 v_2 \mathbf{e}_1 \wedge \mathbf{e}_2
  +  u_1 v_3 \mathbf{e}_1 \wedge \mathbf{e}_3 \\

  +  u_2 v_1 \mathbf{e}_2 \wedge \mathbf{e}_1
  +  u_2 v_2 \mathbf{e}_2 \wedge \mathbf{e}_2
  +  u_2 v_3 \mathbf{e}_2 \wedge \mathbf{e}_3 \\

  +  u_3 v_1 \mathbf{e}_3 \wedge \mathbf{e}_1
  +  u_3 v_2 \mathbf{e}_3 \wedge \mathbf{e}_2
  +  u_3 v_3 \mathbf{e}_3 \wedge \mathbf{e}_3 \\

=    0
  -  u_1 v_2 \mathbf{e}_2 \wedge \mathbf{e}_1
  +  u_1 v_3 \mathbf{e}_1 \wedge \mathbf{e}_3 \\

  +  u_2 v_1 \mathbf{e}_2 \wedge \mathbf{e}_1
  +  0
  -  u_2 v_3 \mathbf{e}_3 \wedge \mathbf{e}_2 \\

  -  u_3 v_1 \mathbf{e}_1 \wedge \mathbf{e}_3
  +  u_3 v_2 \mathbf{e}_3 \wedge \mathbf{e}_2
  +  0 \\

=   (u_3 v_2 - u_2 v_3) \mathbf{e}_3 \wedge \mathbf{e}_2
  + (u_1 v_3 - u_3 v_1) \mathbf{e}_1 \wedge \mathbf{e}_3
  + (u_2 v_1 - u_1 v_2) \mathbf{e}_2 \wedge \mathbf{e}_1.
\]

The second equality follows from the distributive property of the outer
product. The third equality follows because $\mathbf{u} \wedge \mathbf{u} = 0$
and $\mathbf{u} \wedge \mathbf{v} = -\mathbf{v} \wedge \mathbf{u}$.

-------------------------------------------------------------------------------
