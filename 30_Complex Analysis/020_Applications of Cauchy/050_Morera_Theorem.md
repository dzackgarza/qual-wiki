## Morera's Theorem 

:::{.theorem title="Morera's Theorem" ref="Morera"}
If $f$ is continuous on a domain $\Omega$ and $\int_T f = 0$ for every triangle $T\subset \Omega$, then $f$ is holomorphic.
:::

:::{.slogan}
If every integral along a triangle vanishes, implies holomorphic.
:::

:::{.corollary title="Sufficient condition for a sequence to converge to a holomorphic function"}
If \( \ts{ f_n }_{n\in \NN} \) is a holomorphic sequence on a region \( \Omega  \) which uniformly converges to $f$ on every compact subset $K \subseteq \Omega$, then $f$ is holomorphic, and $f_n' \to f'$ uniformly on every such compact subset $K$.
:::

:::{.proof title="?"}
Commute limit with integral and apply Morera's theorem.
:::

:::{.remark}
This can be applied to series of the form $\sum_k f_k(z)$.
:::



