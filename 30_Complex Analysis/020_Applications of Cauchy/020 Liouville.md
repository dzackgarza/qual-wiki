# Liouville's Theorem

:::{.theorem title="Liouville's Theorem" ref="Liouville"}
If $f$ is entire and bounded, $f$ is constant.
:::

:::{.proof title="of Liouville"}
\envlist

- Since $f$ is bounded, $f(z) \leq M$ uniformly on $\CC$.
- Apply Cauchy's estimate for the 1st derivative:
\[
\abs{f'(z)} \leq { 1! \norm{f}_{C_R} \over R } \leq {M \over R}\converges{R\to\infty}\too 0
,\]
  so $f'(z) = 0$ for all $z$.
:::

:::{.proof title="of Liouville, alternative"}

![](figures/2021-12-14_16-51-04.png)

:::

:::{.exercise title="?"}
![figures/image_2021-05-17-11-54-14.png](figures/image_2021-05-17-11-54-14.png)

#work 

:::

:::{.exercise title="?"}
Show that an entire doubly periodic function is constant.

#work 

:::

:::{.exercise title="?"}
Show that if $f, g$ are entire with $\abs{f(z)}\leq \abs{g(z)}$, then $f(z) = cg(z)$ for some constant $c$.

#completed

:::

:::{.solution}
Write $h \da f/g$, so $h$ is meromorphic with $\abs h \leq 1$.
Moreover, $h$ can only have singularities where $g (z_k) = 0$, but is bounded by 1 in punctured neighborhoods about any such $z_k$.
So any such singularities are removable, and $h$ extends over the singularities by Riemann's removable singularity theorem to give an entire function.
Now $h$ is bounded and entire, thus constant, so $c = h = f/g \implies f=cg$.
:::


