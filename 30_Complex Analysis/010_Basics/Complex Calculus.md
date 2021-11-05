# Complex Calculus


:::{.fact}
Various differentials:
\[
dz &= dx + i~dy \\
d\bar z &= dx - i~dy \\ \\
f_z &= f_x = f_y / i
.\]

Integral of a complex exponential:
\[
\int_{0}^{2 \pi} e^{i \ell x} d x
&=\left\{\begin{array}{ll}
{2 \pi} & {\ell=0} \\ 
{0} & \text{else}
\end{array}\right.
.\]

:::

:::{.remark}
When parameterizing integrals $\int_\gamma f(z)\dz$, parameterize $\gamma$ by $\theta$ and write $z=re^{i\theta}$ so $\dz = ire^{i\theta}\dtheta$.
:::

:::{.warnings}
$f(z) = \sin(z), \cos(z)$ are unbounded on $\CC$!
An easy way to see this: they are nonconstant and entire, thus unbounded by Liouville.

:::

:::{.example title="?"}
You can show $f(z) = \sqrt{z}$ is not holomorphic by showing its integral over $S^1$ is nonzero.
This is a direct computation:
\[
\int_{S^1} z^{1/2} \dz 
&= \int_0^{2\pi} (e^{i\theta})^{1/2} ie^{i\theta} \dtheta \\
&= i \int_0^{2\pi} e^{i3\theta \over 2}\dtheta \\
&= i \qty{2\over 3i} e^{i3\theta \over 2}\evalfrom_{0}^{2\pi} \\
&= {2\over 3}\qty{e^{3\pi i - 1}} \\
&= -{4\over 3}
.\]

Note an issue: a different parameterization yields a different (still nonzero) number
\[
\cdots 
&= \int_{-\pi}^{\pi} (e^{i\theta})^{1/2} ie^{i\theta} \dtheta \\
&= {2\over 3}\qty{ e^{3\pi i \over 2} - e^{-3\pi i \over 2}} \\
&= -{4i\over 3}
.\]
This is these are paths that don't lift to closed loops on the Riemann surface defined by $z\mapsto z^2$.
:::