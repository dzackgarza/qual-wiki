---
order: 125
---

# Delbar and the Laplacian

:::{.definition title="del and delbar operators"}
\[
\del \da \del_z \da {1\over 2}\qty{\del_x - i \del_y}
\quad
\text{ and }
\quad
\delbar
\da \del_{\bar z}
={1\over 2}\qty{ \del_x + i\del_y}
.\]
Moreover, the 1-form corresponding to $f$ can be written as 
\[
df = \del f + \delbar f = \dd{F}{z} \dz + \dd{F}{\zbar}\dzbar
.\]

Written slightly more explicitly:
\[
\dd{F}{z} = {1\over 2}\qty{\dd{F}{x} + {1\over i}\dd{F}{y} } && 
\dd{F}{\zbar} = {1\over 2}\qty{\dd{F}{x} - {1\over i}\dd{F}{y} } 
.\]

:::

:::{.proposition title="Holomorphic iff delbar vanishes"}
$f$ is holomorphic at $z_0$ iff $\delbar f(z_0) = 0$:
\[
2\delbar f 
&\da (\del_x + i \del_y) (u+iv) \\
&= u_x + iv_x + iu_y - v_y \\
&= (u_x - v_y) + i(u_y + v_x) \\
&= 0 && \text{by Cauchy-Riemann}
.\]
:::

### Harmonic Functions and the Laplacian

:::{.definition title="Laplacian and Harmonic Functions"}
A real function of two variables $u(x, y)$ is **harmonic** iff it is in the kernel of the Laplacian operator:
\[  
\Delta u \definedas \qty{\dd{^2}{x^2} + \dd{^2}{y^2}}u = 0
.\]
:::

:::{.proposition title="Cauchy-Riemann implies holomorphic"}
If $f = u+iv$ with $u, v\in C^1(\RR)$ satisfying the Cauchy-Riemann equations on $\Omega$, then $f$ is holomorphic on $\Omega$ and 
\[
f'(z) = \del f = {1\over 2}\qty{u_x + iv_x}
.\]
:::

:::{.proposition title="Holomorphic functions have harmonic components"}
If $f(z) = u(x, y) + iv(x, y)$ is holomorphic, then $u, v$ are harmonic.
:::

:::{.proof title="?"}
\envlist

- By CR, 
\[
u_x = v_y && u_y = -v_x
.\]

- Differentiate with respect to $x$: 
\[
u_{xx} = v_{yx} && u_{yx} = -v_{xx}
.\]
- Differentiate with respect to $y$:
\[
u_{xy} = v_{yy} && u_{yy} = -v_{xy}
.\]
- Clairaut's theorem: partials are equal, so
\[
u_{xx} - v_{yx} = 0 \implies u_{xx} + u_{yy} = 0 \\ \\
v_{xx} + u_{yx} = 0 \implies v_{xx} + v_{yy} = 0 \\ \\
.\]



:::

:::{.fact}
A function harmonic $u$ on all of $\RR^2$ and bounded is necessarily constant.
This follows from writing $f=u+iv$, which will then be a bounded entire function and thus constant by Liouville, which then must have constant real part.
:::

:::{.exercise title="?"}
Show that if $u,v$ are harmonic conjugates, then

- $u^2-v^2$ is harmonic
- $u_x$ is harmonic.
:::

:::{.solution}
Write $f=u+iv$, which is analytic.

- $f^2$ is analytic, and $f^2 = (u+iv)^2 = u^2 - v^2 + i (2uv)$, which necessarily has harmonic components.

- $f'$ is analytic and one can write $f' = u_x + iv_x$, which has harmonic components.
:::


