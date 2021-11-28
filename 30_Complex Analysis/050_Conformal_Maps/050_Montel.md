# Montel

:::{.definition title="Normal Families"}
A family $\mcf = \ts{f_j}_{j\in J}$ of holomorphic functions on $\Omega$ is **normal** if every sequence of functions from $\mcf$ has a locally uniformly convergent subsequence (so they converge on every compact subset of $\Omega$).
:::

:::{.definition title="Uniform boundedness and equicontinuity"}
A family $\mcf$ of holomorphic functions is **uniformly bounded on compact subsets of $\Omega$** iff for each compact $K \subseteq \Omega$ if
\[
\exists M>0 \text{ such that } \abs{f(z)} < M \qquad \forall z\in K,\,\forall f\in \mcf
.\]
It is **equicontinuous** on $K$ if 
\[
\forall \eps>0,\, \exists \delta = \delta(\eps) \text{ such that } z,w\in K,\, \abs{z-w}< \delta \implies \abs{f(z) - f(w)} < \eps \quad \forall f\in \mcf
.\]
:::

:::{.example title="?"}
If $f_k:[0,1]\to \RR$ is a family of differentiable functions with a uniform constant $M$ with $\abs{f_k'} \leq M$ for all $f\in \mcf$, then $\ts{f_k}$ is equicontinuous.
To prove this, apply the MVT.
:::

:::{.example title="?"}
The family $f_k(x) = x^k$ is not equicontinuous, since fixing $x_0 \in (0, 1)$ we have $\abs{f_k(x_0) - f_k(1)} \convergesto{k\to \infty} 1 > \eps$.
:::

:::{.example title="?"}
$f_k(x) = (\sin k x)$ is uniformly bounded but not equicontinuous on $(0, 1)$ since it has no convergent subsequence on any compact subset.
:::

:::{.remark}
Equicontinuity is uniform continuity, where the uniformity extends across all $f\in \mcf$.
The following is a stark difference between holomorphic and smooth functions, and is used in the Riemann mapping theorem:
:::

:::{.theorem title="Montel's theorem"}
If $\mcf$ is a family of locally uniformly bounded holomorphic functions on $\Omega$, then

- $\mcf$ is a normal family by Arzela-Ascoli, and
- $f$ is locally equicontinuous (so equicontinuous on every compact subset).
:::

:::{.slogan}
Locally uniformly bounded families are normal.
:::


:::{.proposition title="Equicontinuity + pointwise convergence implies uniform convergence"}
If $\ts{f_n}$ is equicontinuous on $K$ a compact set and $f_n\to f$ pointwise, then $f_n\to f$ uniformly.
:::


:::{.proof title="?"}
Fix $\eps$, it suffices to find an $n= n(\eps)$ to bound $\norm{f_n - f}_{\infty, K } < \eps$.

:::


