# Hurwitz 

:::{.definition title="Locally uniform convergence"}
Say a sequence $f_k\to f$ **locally uniformly** on $\Omega$ if $f_k\to f$ uniformly on every compact subset.
Equivalently, $f_k \to f$ uniformly on any bounded subset of strictly positive distance to $\bd \Omega$.
:::

:::{.definition title="Univalent"}
A function $f:\Omega\to \CC$ is **univalent** iff $f$ is holomorphic and injective.
These are exactly the conformal maps of $\Omega$ to other domains.
:::

:::{.theorem title="Hurwitz"}
Suppose $\ts{f_k}$ is a sequence of holomorphic functions on $\Omega$ converging locally uniformly to $f$ on $\Omega$ and $f$ has a zero of order $n$ at $z_0$.
Then there exists some $\delta$ such that for $k\gg 1$, $f_k$ has exactly $n$ zeros in the disc $\ts{\abs{z-z_0} < \delta}$, counted with multiplicity.
Moreover, these zeros converge to $z_0$ as $k\to \infty$.
:::

:::{.slogan}
The zeros of the sequence converge to the zeros of the limit.
:::

:qa
:::{.theorem title="Hurwitz 2"}
If $\ts{f_k}$ are univalent functions on $\Omega$ converging normally to $f$, then either

- $f$ is univalent, or
- $f$ is constant.

:::

