# Montel

:::{.definition title="Normal Families"}
A family $\mcf = \ts{f_j}_{j\in J}$ of holomorphic functions on $\Omega$ is **normal** if every sequence of functions from $\mcf$ has a locally uniformly convergent subsequence (so they converge on every compact subset of $\Omega$).
:::

:::{.definition title="Uniform boundedness and equicontinuity"}
A family $\mcf$ of holomorphic functions is **uniformly bounded on compact subsets of $\Omega$** iff for each compact $K \subseteq \Omega$ if
\[
\exists M>0 \text{ such that } \abs{f(z)} < M \qquad \forall z\in K,\,\forall f\in \mcf
.\]
:::

:::{.definition title="Equicontinuity"}
A family $\mcf$ of holomorphic functions is **equicontinuous** on $K$ if 
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

:::{.example title="Negating equicontinuity"}
To negate equicontinuity, show that there exists $\eps>0$ and a bad tuple $(x, y, f\in \mcf)$ such that for any $\delta$, we can arrange $\abs{x-y} < \delta$ to be small but $\abs{f(x) - f(y)} > \eps$ is large.
This produces sequences $x_k, y_k, f_k$ with $\abs{x_k-y_k}\to 0$ but $\abs{f_k(x_k) - f_k(y_k)} > \eps$.
:::

:::{.theorem title="Arzela-Ascoli"}
A subset $\mcf \subset C[a, b]$ is a compact subset of continuous functions $\iff \mcf$ is bounded and equicontinuous.
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

:::{.remark}
This says that a sequence of holomorphic functions avoiding the exterior of a disc contains a locally uniformly convergent subsequence.
In particular, the limit is holomorphic.
:::

:::{.proposition title="Equicontinuity + pointwise convergence implies uniform convergence"}
If $\ts{f_n}$ is equicontinuous on $K$ a compact set and $f_n\to f$ pointwise, then $f_n\to f$ uniformly.
:::

:::{.proof title="?"}
Fix $\eps$, it suffices to find an $n= n(\eps)$ to bound $\norm{f_n - f}_{\infty, K } < \eps$.
A standard $\eps/3$ argument works: write
\[
\abs{f_n(x) - f(x) } \leq \abs{f_n(x) - f_n(y)} + \abs{f_n(y) - f(y)} + \abs{f(y) - f_n(y)}
.\]

Use equicontinuity to bound $\abs{f_n(x) - f_n(y)}$ for all $n\geq N_0 = N_0(\eps)$, for all $x,y\in K$.
This takes care of the 1st and 3rd terms.

For the 2nd term, cover $K$ by $\delta\dash$balls and by compactness obtain a finite cover $B_{\delta}(y_k)\covers K$.
Then $x\in B_\delta(y)$ for $y=y_j$ for some $j$, and in this ball use pointwise convergence of $f_n\to f$. 
:::

