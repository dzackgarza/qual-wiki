# Maximum modulus principle

:::{.theorem title="Maximum modulus principle"}
Suppose $f$ is holomorphic on $\Omega$.
If $f$ has a relative maximum at $z_0\in\Omega$, then $f$ is constant in a neighborhood of $z_0$.
If $\Omega$ is a bounded connected domain with $f$ continuous on $\Omega$ and $\bd \Omega$, then either $f$ is constant or $M \da \max_{z\in \Omega}\abs{f(z)}$ is only attained by some $z\in \bd\Omega$.
:::

:::{.proof title="by the open mapping theorem"}
Use that $z\mapsto \abs{z}$ is an open map away from $z=0$.
If $f$ is holomorphic, by the open mapping theorem it is an open map.
If $f$ attains a maximum at an interior point $z_0$, then there is some neighborhood $U\ni z_0$ where $\abs{f(U)}$ is open in $\RR$ -- but such an interval contains values larger than $\abs{f(z_0)}$, contradicting maximality at $z_0$.
:::

:::{.proof title="by the mean value theorem"}
Let $z_0\in\Omega$ and
pick any $R$ such that $\DD_R(z_0) \subseteq \Omega$.
We have
\[
f(z_0) 
&= {1\over 2\pi i}\oint_{\abs{\xi-z_0} = R} {f(\xi) \over \xi-z_0} \dz \\
&= {1\over 2\pi i}\int_0^{2\pi} {f(Re^{it} + z_0) \over Re^{it} } iRe^{it} \dt \\
&= {1\over 2\pi} \int_0^{2\pi } f(Re^{it} + z_0) \dt
,\]
so 
\[
\abs{f(z_0)} \leq {1\over 2\pi}\int_0^{2\pi }\abs{f(Re^{it} + z_0 )} \dt \leq \max_{t \in [0, 2\pi]} \abs{f(Re^{it} + z_0) }
.\]
Setting $z_R$ to be the point $Re^{it} + z_0$ that maximizes this last term, we have $f(z_0) \leq f(z_R)$.
Since this holds for all $R$, this implies $f(z_0) = f(z_R)$ for every $R$, making $f$ constant on $\DD_R(z_0)$.
By the identity principle $f$ is constant on $\Omega$.
:::

:::{.theorem title="Minimum modulus principle"}
Suppose  $f$ is holomorphic and nonvanishing on $\Omega$.
If any interior point $z_0\in \Omega^\circ$ is a relative minimum for $f$, then $f$ is constant.
If $f$ is nonconstant, then the minimum must occur on $\bd\Omega$.
:::

:::{.proof title="?"}
Suppose $f\neq 0$ on $G$.
If $f(z) = 0$ for some $z\in \bd G$, we're done, so suppose $f\neq 0$ on $\bar G$.
Then $1/f$ is holomorphic on $G$ and continuous on $\bar G$, so $\max_{z\in \bar G}\abs{1/f(z)} = \max_{z\in \bd G} \abs{1/f(z)}$.
:::

# Exercises

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

