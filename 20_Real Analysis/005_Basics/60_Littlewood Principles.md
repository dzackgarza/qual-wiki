---
order: 60
---

# Littlewood's Principles ("Almost" Theorems)

:::{.theorem title="Egorov's Theorem"}
Let $E \subseteq \RR^d$ be measurable of positive finite measure with $f_k\to f$ almost everywhere on $E$.
Then for every $\eps > 0$ there is a closed $A_\eps \subseteq E$ with $\mu(E\sm A_\eps) < \eps$ and $f_k\to f$ uniformly on $A_\eps$.
:::

:::{.proof title="of Egorov"}

![figures/2021-06-11_18-07-43.png](figures/2021-06-11_18-07-43.png)

![figures/2021-06-11_18-07-58.png](figures/2021-06-11_18-07-58.png)

:::

:::{.theorem title="Lusin's Theorem"}
If $f$ is measurable and finite-valued on $E$ with $\mu(E) < \infty$ then for every $\eps>0$ there exists a closed set $F_\eps$ with
\[
F_\eps \subset F && \mu(E - F_\eps) \leq \eps
\]
where $f$ restricted to $F_\eps$ is continuous.

> Note: this means that the separate function $\tilde f \da \ro{f}{F_\eps}$ is continuous, not that the function $f$ defined on all of $E$ is continuous at points of $F_\eps$.

:::

:::{.proof title="of Lusin"}

![figures/2021-06-11_18-04-52.png](figures/2021-06-11_18-04-52.png)

:::
