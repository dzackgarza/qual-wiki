---
order: 999
---

# Exercises

:::{.exercise title="Zero derivative implies constant"}
Show that if $f' = 0$ on a domain $\Omega$, then $f$ is constant on $\Omega$

#complex/exercise/completed

:::

:::{.solution}
Write $f = u + iv$, then $0 = 2 f' = u_x + iv_x = u_y - iu_y$, so $\grad u = \grad v = 0$.
Show $f$ is constant along every straight line segment $L$ by computing the directional derivative $\grad u \cdot \vector v = 0$ along $L$ connecting $p, q$.
Then $u(p) = u(q) = a$ some constant, and $v(p) = v(q) = b$, so $f(z) = a+bi$ everywhere.
:::

:::{.exercise title="f and fbar holomorphic implies constant"}
Show that if $f$ and $\bar{f}$ are both holomorphic on a domain $\Omega$, then $f$ is constant on $\Omega$.

#complex/exercise/completed

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

#complex/exercise/completed

:::

:::{.solution}
**Part 3**:

- Write $\abs{f} = c \in \RR$.
- If $c=0$, done, so suppose $c>0$.
- Use $f\bar{f} = \abs{f}^2 = c^2$ to write $\bar{f}=c^2/f$.
- Since $\abs{f(z)} = 0 \iff f(z) = 0$, we have $f\neq 0$ on $\Omega$, so $\bar{f}$ is analytic.
- Similarly $f$ is analytic, and $f,\bar{f}$ analytic implies $f'=0$ implies $f$ is constant. 

:::

:::{.exercise title="?"}
Show that if $f$ is holomorphic in $\DD_r(a)$ and $a$ is a zero of $f$ of multiplicity $n$, then $f^{(k)}(a) = 0$ for $k\leq n-1$ and $f^{(n)}(a) \neq 0$.
Show that this is an iff.

#complex/exercise/completed

:::

:::{.solution}
$\implies$:
Suppose the first $m-1$ derivatives vanish.
Then
\[
f(z) = \sum_{k\geq 0} c_k (z-a)^k = \sum_{k\geq m+1} c_k (z-a)^k = (z-a)^m \sum_{k\geq m+1} c_k (z-a)^{k-m} = (z-a)^m (c_m + c_{m+1}(z-a) + \cdots) \da (z-a)^m g(z)
,\]
using that $c_k \approx f^{(k)}(a)$.
Noting that $g(a) = c_m \neq 0$, we have $f(z) = (z-a)^m g(z)$ where $g$ is nonvanishing in a neighborhood of $a$, making $a$ a zero of $f$ of order $m$.

Conversely, if $a$ is an order $m$ zero, then $f(z) = (z-a)^m h(z)$ for $h$ nonvanishing near $a$.
So as above, writing 
\[
f(z) = \sum_{k\geq 0} c_k (z-a)^k = \sum_{k\leq m} c_k (z-a)^k + (z-a)^m g(z)
,\]
we have
\[
0 = f(z) - (z-a)^m h(z) = \sum_{k \leq m} c_k (z-a)^k + (z-a)^m(g(z) - h(z))
.\]
But this is a power series expansion of the zero function, and by uniqueness of power series we have $c_k = 0$ for $k\leq m-1$ and $g(z) = h(z)$.
In particular, $g(a) = c_{m}$ by definition, and $g(a) = h(a) \neq 0$.
:::

