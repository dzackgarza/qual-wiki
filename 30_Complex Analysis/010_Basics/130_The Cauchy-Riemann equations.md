---
order: 130
---

# The Cauchy-Riemann equations

:::{.exercise title="Cauchy-Riemann iff holomorphic"}
Show that $f = u+iv$ with $u, v\in C^1(\RR)$ satisfying the Cauchy-Riemann equations on $\Omega$, then $f$ is holomorphic on $\Omega$ with
\[
f'(z) = \dd{f}{x} = {1\over i} \dd{f}{y} = {1\over 2}\qty{u_x + iv_x}
.\]
Conversely, show that if $f$ is holomorphic, then $f$ satisfies the Cauchy-Riemann equations.
:::

:::{.solution}
Holomorphic $\implies$ CR:

Suppose $f'(z_0)$ exists for all $z_0\in \CC$, so the following limit exists:
\[
f'(z_0) \da \lim_{h\to 0, h\in \CC} {f(z_0 + h) - f(z_0) \over h}
.\]
Approach along $\ts{t + 0i \st t\in \RR}$:
\[
f'(z_0) = f'(x_0, y_0) = \lim_{t\to 0, t\in \RR} {f(x_0 + t, y_0) - f(x_0, y_0) \over t} \da f_x(x_0, y_0)
.\]
Approach along $\ts{0 + ti \st t\in \RR}$:
\[
f'(z_0) = f'(x_0, y_0) = \lim_{t\to 0, t\in \RR} {f(x_0, y_0 + t) - f(x_0, y_0) \over it} \da {1\over i} f_y(x_0, y_0)
.\]
Thus
\[
if_x = f_y \implies i(u_x + i v_x) = u_y + i v_y \\ 
\implies -v_x + iu_x = u_y + iv_y \\ 
\implies u_x = v_y,\, u_y = -v_x
.\]


CR $\implies$ holomorphic:
A straightforward but messy calculation, not likely to be useful for quals!

:::

:::{.exercise title="Polar CR equations"}
Show that in polar coordinates, the CR equations take the following form:
\[  
\frac{\partial u}{\partial r}=\frac{1}{r} \frac{\partial v}{\partial \theta} \quad \text { and } \quad \frac{1}{r} \frac{\partial u}{\partial \theta}=-\frac{\partial v}{\partial r}
.\]

:::

:::{.solution}
Setting 
\[
z = re^{i\theta} = r(\cos(\theta) + i\sin(\theta) ) = x+iy
\]
yields $x=r\cos(\theta), y=r\sin(\theta)$, one can identify
\[
x_r = \cos(\theta)&, x_\theta = -r\sin(\theta) \\
y_r = \sin(\theta)&, y_\theta = r\cos(\theta)
.\]

Now apply the chain rule:
\[
u_r 
&= u_x x_r + u_y y_r \\
&= v_y x_r -v_x y_r && \text{CR}\\
&= v_y \cos(\theta) - v_x \sin(\theta) \\
&= {1\over r}\qty{ v_y r\cos(\theta) - v_x r\sin(\theta) } \\
&= {1\over r}\qty { v_y y_\theta + v_x x_\theta} \\
&= {1\over r} v_\theta
.\]
Similarly,
\[
v_r
&= v_x x_r + v_y y_r \\
&= v_x \cos(\theta) + v_y\sin(\theta) \\
&= -u_y\cos(\theta) + u_x\sin(\theta) && \text{CR} \\
&= {1\over r}\qty{ -u_y r\cos(\theta) + u_x r\sin(\theta)} \\
&= {1\over r}\qty{ -u_y y_\theta - u_x x_0 } \\
&= -{1\over r} u_\theta
.\]

Thus
\[
\frac{\partial u}{\partial r}=\frac{1}{r} \frac{\partial v}{\partial \theta} \quad \text { and } \quad \frac{\partial v}{\partial r}=-\frac{1}{r} \frac{\partial u}{\partial \theta} \\
.\]

:::
