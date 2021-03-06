---
order: 30
---

# Continuity

:::{.remark}
Some inclusions on the real line:

- Differentiable with a bounded derivative $\subset$ Lipschitz continuous $\subset$ absolutely continuous $\subset$ uniformly continuous $\subset$ continuous
    
Proofs: 

- Mean Value Theorem, 
- Triangle inequality, 
- Definition of absolute continuity specialized to one interval, 
- Definition of uniform continuity

:::

:::{.lemma title="Function discontinuous on the rationals"}
There is a function discontinuous precisely on $\QQ$.
:::

:::{.proof title="?"}
$f(x) = \frac 1 n$ if $x = r_n \in \QQ$ is an enumeration of the rationals, and zero otherwise.
The limit at every point is 0.
:::

:::{.proposition title="No functions discontinuous on the irrationals"}
There *do not* exist functions that are discontinuous precisely on $\RR\setminus \QQ$.
:::

:::{.proof title="?"}
$D_f$ is always an $F_\sigma$ set, which follows by considering the oscillation $\omega_f$.
Use that $\omega_f(x) = 0 \iff f$ is continuous at $x$, and $D_f = \union_n A_{\frac 1 n}$ where $A_\varepsilon = \theset{\omega_f \geq \varepsilon}$ is closed.
:::

:::{.remark}
An alternative characterization of **uniform continuity**:
$$
\left\|\tau_{y} f-f\right\|_{u} \rightarrow 0 \text { as } y \rightarrow 0
$$
:::

:::{.proposition title="Lipschitz implies uniformly continuous"}
If $f$ is Lipschitz on $X$, then $f$ is uniformly continuous on $X$.

Supposing that
\[
\norm{f(x) - f(y)} \leq C \norm{x-y}
,\]
for a fixed $\eps$ take $\delta(\eps) \da \eps/C$, then
\[
\norm{f(x) - f(y)}
&\leq C \norm{x-y} \\
&\leq C \delta \\
&= C \qty{\eps/C} \\
&= \eps
.\]
:::

:::{.theorem title="Heine-Cantor"}
Every continuous function $f:X\to Y$ where $X$ is a compact metric space is uniformly continuous.
As a result, if $f:U\to \RR$ is continuous, then $f$ is uniformly continuous on any $K \subseteq U$ compact.
:::

:::{.proof title="?"}
Fix $\eps>0$, we'll find a $\delta$ that works for all $x\in X$ uniformly.
For every $x\in X$, pick a $\delta_x$ neighborhood satisfying the conditions for (assumed) continuity.
Take an open cover by $\delta_x/2$ balls, extract a finite subcover, take $\delta$ the minimal radius.
:::

:::{.definition title="Equicontinuity"}
If $\mathcal F \subset C(X)$ is a family of continuous functions on $X$, then $\mathcal F$ *equicontinuous* at $x$ iff

\[
\forall \varepsilon > 0 ~~\exists U \ni x \text{ such that } y\in U \implies \abs{f(y) - f(x)} < \varepsilon \quad \forall f\in \mathcal{F}
.\]

:::

