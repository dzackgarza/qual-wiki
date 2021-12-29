---
order: 999
---

# Exercises

:::{.exercise title="Injectivity relates to derivatives"}
Show that if $z_0$ is a zero of $f'$ of order $n$, then $f$ is $(n+1)$-to-one in a neighborhood of $z_0$.

#work/exercise

:::

:::{.exercise title="Zero derivative implies constant"}
Show that if $f' = 0$ on a domain $\Omega$, then $f$ is constant on $\Omega$

#completed/exercise

:::

:::{.solution}
Write $f = u + iv$, then $0 = 2 f' = u_x + iv_x = u_y - iu_y$, so $\grad u = \grad v = 0$.
Show $f$ is constant along every straight line segment $L$ by computing the directional derivative $\grad u \cdot \vector v = 0$ along $L$ connecting $p, q$.
Then $u(p) = u(q) = a$ some constant, and $v(p) = v(q) = b$, so $f(z) = a+bi$ everywhere.
:::

:::{.exercise title="f and fbar holomorphic implies constant"}
Show that if $f$ and $\bar{f}$ are both holomorphic on a domain $\Omega$, then $f$ is constant on $\Omega$.

#completed/exercise

:::

:::{.solution}
\envlist

- Strategy: show $f'=0$.
- Write $f = u + iv$. 
  Since $f$ is analytic, it satisfies CR, so 
  \[
  u_x = v_y && u_y = -v_x
  .\]

- Similarly write $\bar f = U + iV$ where $U = u$ and $V = -v$.
  Since $\bar f$ is analytic, it also satisfies CR , so
\[
U_x = V_y && U_y = -V_x \\ \\
\implies u_x = -v_y && u_y = v_x
.\]

- Add the LHS of these two equations to get $2u_x = 0 \implies u_x = 0$.
  Subtract the right-hand side to get $-2v_x = 0 \implies v_x = 0$

- Since $f$ is analytic, it is holomorphic, so $f'$ exists and satisfies $f' = u_x + iv_x$.
  But by above, this is zero.
- By the previous exercise, $f'=0 \implies f$ is constant.
:::

:::{.exercise title="SS 1.13: Constant real/imaginary/magnitude implies constant"}
If $f$ is holomorphic on $\Omega$ and any of the following hold, then $f$ is constant:

1. $\Re(f)$ is constant.
2. $\Im(f)$ is constant.
3. $\abs{f}$ is constant.

#completed/exercise

:::

:::{.solution}
**Part 3**:

- Write $\abs{f} = c \in \RR$.
- If $c=0$, done, so suppose $c>0$.
- Use $f\bar{f} = \abs{f}^2 = c^2$ to write $\bar{f}=c^2/f$.
- Since $\abs{f(z)} = 0 \iff f(z) = 0$, we have $f\neq 0$ on $\Omega$, so $\bar{f}$ is analytic.
- Similarly $f$ is analytic, and $f,\bar{f}$ analytic implies $f'=0$ implies $f$ is constant. 

:::
