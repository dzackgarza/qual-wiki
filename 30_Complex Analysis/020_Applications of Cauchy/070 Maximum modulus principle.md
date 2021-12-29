# Maximum modulus principle

:::{.theorem title="Minimum modulus principle"}
If $f$ is a non-constant analytic function on a bounded open set $G$ and is continuous on $\bar{G}$, then either $f$ has a zero in $G$ or $|f|$ assumes its minimum value on $\partial G$.
:::

:::{.proof title="?"}
Suppose $f\neq 0$ on $G$.
If $f(z) = 0$ for some $z\in \bd G$, we're done, so suppose $f\neq 0$ on $\bar G$.
Then $1/f$ is holomorphic on $G$ and continuous on $\bar G$, so $\max_{z\in \bar G}\abs{1/f(z)} = \max_{z\in \bd G} \abs{1/f(z)}$.
:::

## Exercises

:::{.exercise title="SS 3.2.15"}
Suppose $f$ is continuous and nonzero on $\bar\DD$ and holomorphic on $\DD$.
Show that if $\abs{f(z)} = \abs{z}$ for all $\abs{z} = 1$ then $f$ is constant.

#complex/exercise/completed

:::

:::{.solution}
If $f$ has no zeros in $\DD$, apply the MMP to $1/f$ to get $\abs{f} = 1$ on all of $\DD$.
By Cauchy-Riemann (or the open mapping theorem), if $\abs{f}$ is constant, $f$ is constant.
:::

:::{.exercise title="?"}
Let $f: \Omega\to \CC$ be holomorphic and suppose there is a $z_0 \in \Omega$ with $\abs{f(z_0)}\leq \abs{f(z)}$ for all $z\in \Omega$.
Show that either $f(a) = 0$ or $f$ is constant.

#complex/exercise/completed 

:::

:::{.solution}
Suppose $f(z_0)\neq 0$, then the inequality forces there to be no zeros in $\Omega$.
So $g(z) \da 1/f(z)$ is nonzero and holomorphic on $\Omega$ and $\abs{g(z)}\leq \abs{1\over f(z_0)} \da \abs{g(z_0)}$.
Since $z_0\in \Omega$, the MMP forces $g$ to be constant, and thus so is $f$.
:::

:::{.exercise title="?"}
Show that if $\Re(f(z)) \geq 0$ for all $z\in \CC$, then $f$ is constant.

#complex/exercise/completed

:::

:::{.solution}
Define $g(z) \da e^{-f(z)}$, then
\[
\abs{g(z)} = e^{-\Re(f(z))} \leq e^0 = 1
.\]
Since $g$ is entire and bounded, $g$ is constant and thus so is $f$.
:::

:::{.exercise title="?"}
Show that if $f$ is constant on any closed disk $r\bar\DD$ for $r<1$, then $f$ is constant on $\DD$.

#complex/exercise/completed

:::

:::{.solution}
By MMP applied to $r\bar \DD$, since $f$ achieves its maximum on the interior $r\DD$, $f$ is necessarily constant.

:::

:::{.exercise title="?"}
Suppose $f$ is entire and $f^{(n)}$ is bounded on $\CC$.
Show that $f$ is a polynomial of degree at most $n$.

#complex/exercise/completed

:::

:::{.solution}
By Liouville or MMP, $f^{(n)}$ is bounded and entire and thus constant.
Integrating a constant $n$ times yields a polynomial of degree t most $n$.

:::

:::{.exercise title="Bounded harmonic functions"}
Find all harmonic functions $u:\DD\to \CC$ such that $u(1/2) = 2$ and $\abs{u(z)}\geq 2$ for all $\abs{z} \leq 1$.

#complex/exercise/completed

:::

:::{.solution}
Since $1/2 \in \ts{\abs{z}\leq 1}$ is an interior point of $\DD$, by the MMP if $u$ is nonconstant then $u(1/2) = 2$ can not be a relative maximum for $u$ on $\DD$.
:::

