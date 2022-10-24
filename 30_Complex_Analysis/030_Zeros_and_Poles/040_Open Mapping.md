---
title: Open Mapping Theorem
---

Idea: maximum modulus plus Rouche.

# Open Mapping Theorem

:::{.corollary title="Open Mapping"}
Any holomorphic non-constant map is an open map.
:::

:::{.proof title="Using Rouché"}

![](figures/2021-12-14_16-26-16.png)

:::

:::{.proof title="using the argument principle"}

![](figures/2022-01-02_02-14-55.png)

![](figures/2021-12-14_17-24-45.png)


:::

:::{.proof title="using local degrees"}

![attachments/Pasted image 20211215022640.png](attachments/Pasted%20image%2020211215022640.png)

:::


## Exercises

:::{.exercise title="No bijective conformal maps from a disc to an annulus"}
Show that there is no bijective conformal map from $A\da \ts{0< \abs{z} < 1}$ to $B\da \ts{1<\abs{z} < 2}$.

#complex/exercise/completed

:::

:::{.solution}
Suppose toward a contradiction that such an injective map $f: A\to B$.
Since $f(A) \subseteq B$ which is bounded, $f$ is bounded and thus any singularities in $A$ are removable.
So $f$ extends holomorphically to $F: \DD\to \bar{B}$, and since $F$ is an open map, $F(\DD) \subseteq B$.
Write $w_0 \da F(0) \in B$, then by surjectivity there is a $z_0\in A$ such that $f(z_0) = w_0$.
Since $F = f$ on $A$, we also have $F(z_0) = w_0$.
Since $A$ is open, $z_0$ is interior, and since $z_0\neq 0$ we can separate $z_0$ and zero by disjoint open sets $U$ and $V$.
Since $F$ is open, $F(U), F(V)$ are open in $B$ and contain $w_0$.
Then $F(U) \intersect F(V)$ is an open set containing $w_0$, so there is a disc $D_\eps(w_0)$ in $F(U)$ and $F(V)$.
But then $F(\DD_\eps(w_0))$ is an open set intersecting $U$ and $V$, contradicting that they were disjoint.
:::

:::{.exercise title="?"}
Prove that if $f$ is holomorphic on a connected open set $\Omega$ and $f^2(z) = \bar{f(z)}$ then $f$ is constant.

#complex/exercise/completed

:::

:::{.solution}
Write $F(z) \da f^3(z)$ so that
\[
F(z) = f^2(z) f(z) = \bar{f(z)}f(z) = \abs{f(z)}^2
.\]
Since $F$ is also holomorphic on $\Omega$ and this calculation shows $F(\Omega) \subseteq \Omega$, $F$ must be constant by the open mapping theorem.
So $f^3(z) = c$ for some $c$, forcing $f$ to be constant as well.
:::

