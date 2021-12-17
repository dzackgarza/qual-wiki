# Removable Singularities 


:::{.theorem title="Riemann's removable singularity theorem"}
If $z_0$ is an isolated singularity of $f(z)$ and $\abs{f(z)}$ is bounded near $z_0$, then $z_0$ is removable.

More generally, TFAE:

- $f$ extends holomorphically over $z_0$, i.e. there is a function $F$ such that $\ro{F}{\Omega\sm\ts{z_0}} = f$
- $f$ extends continuously over $z_0$.
- There exists *some* neighborhood of $z_0$ on which $f$ is bounded.
- $\lim_{z\to z_0}(z-z_0)f(z) = 0$.

:::


:::{.remark}
Showing a singularity $z_0$ of $f$ is removable: it suffices to show 

- Expand $f(z) = \sum_{k\in \ZZ} c_k z^k$ and show $z_k=0$ for $k<0$.
- Show $\lim_{z\to z_0}f(z) \neq \infty$
:::

