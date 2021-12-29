# PDEs

:::{.definition title="The Dirichlet Problem"}
Given a bounded piecewise continuous function $u:S^1\to \RR$, is there a unique extension to a continuous harmonic function $\tilde u: \DD\to \RR$?

:::

:::{.remark}
More generally, this is a boundary value problem for a region where the *values* of the function on the boundary are given.
Compare to prescribing conditions on the normal vector on the boundary, which would be a Neumann BVP.
Why these show up: a harmonic function on a simply connected region has a harmonic conjugate, and solutions of BVPs are always analytic functions with harmonic real/imaginary parts.
:::

:::{.example title="Dirichlet problem on the strip"}
See section 27, example 1 in Brown and Churchill.
On the strip $(x, y)\in (0, \pi) \cross (0, \infty)$, set up the BVP for temperature on a thin plate with no sinks/sources:
\[
\laplacian T = 0 && T(0, y) = 0,\, T(\pi, y) = 0 \,\,\forall y \\ \\
T(x, 0) = \sin(x) && T(x, y) \converges{y\to\infty}\too 0
.\]

Then the following function is harmonic on $\RR^2$ and satisfies that Dirichlet problem:
\[
T(x ,y) = e^{-y} \sin(x) = \Re(-ie^{iz}) = \Im(e^{iz})
.\]
:::
