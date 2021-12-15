# Maximum modulus principle

:::{.theorem title="Minimum modulus principle"}
If $f$ is a non-constant analytic function on a bounded open set $G$ and is continuous on $\bar{G}$, then either $f$ has a zero in $G$ or $|f|$ assumes its minimum value on $\partial G$.
:::

:::{.proof title="?"}
Suppose $f\neq 0$ on $G$.
If $f(z) = 0$ for some $z\in \bd G$, we're done, so suppose $f\neq 0$ on $\bar G$.
Then $1/f$ is holomorphic on $G$ and continuous on $\bar G$, so $\max_{z\in \bar G}\abs{1/f(z)} = \max_{z\in \bd G} \abs{1/f(z)}$.
:::


:::{.exercise title="?"}
Suppose $f$ is holomorphic on $\DD$ with $\abs{f} = 1$ on $S^1$.
Show that $f$ is either constant or has a zero in $\DD$.
:::

:::{.solution}
If $f$ has no zeros in $\DD$, apply the MMP to $1/f$ to get $\abs{f} = 1$ on all of $\DD$.
By Cauchy-Riemann, if $\abs{f}$ is constant, $f$ is constant.
:::



