## Meromorphic Functions

:::{.definition title="Meromorphic"}
A function $f:\Omega\to\CC$ is *meromorphic* iff there exists a sequence $\theset{z_n}$ such that

- $\theset{z_n}$ has no limit points in $\Omega$.
- $f$ is holomorphic in $\Omega\setminus\theset{z_n}$.
- $f$ has poles at the points $\theset{z_n}$.

Equivalently, $f$ is holomorphic on $\Omega$ with a discrete set of points delete which are all poles of $f$.
:::

:::{.theorem title="Meromorphic implies rational"}
Meromorphic functions on $\CC$ are rational functions.
:::

:::{.proof title="?"}
Consider $f(z) - P(z)$, subtracting off the principal part at each pole $z_0$, to get a bounded entire function and apply Liouville.
:::

:::{.theorem title="Improved Taylor Remainder Theorem"}
If $f$ is analytic on a region $\Omega$ containing $z_0$, then $f$ can be written as
\[
f(z)
=\left(\sum_{k=0}^{n-1} \frac{f^{(k)}\left(z_{0}\right)}{k !}\left(z-z_{0}\right)^{k}\right)+ 
R_{n}(z)\left(z-z_{0}\right)^{n}
,\]
where $R_n$ is analytic.
:::

