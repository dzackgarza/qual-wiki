---
order: 999
---

# Appendix

- Some inclusions on the real line:

    - Differentiable with a bounded derivative $\subset$ Lipschitz continuous $\subset$ absolutely continuous $\subset$ uniformly continuous $\subset$ continuous
    
    - Proofs: Mean Value Theorem, Triangle inequality, Definition of absolute continuity specialized to one interval, Definition of uniform continuity

- **Bolzano-Weierstrass**:
Every bounded sequence has a convergent subsequence.

- **Heine-Borel**:
$$
X \subseteq \RR^n \text{ is compact }
\iff
X \text{ is closed and bounded}
.$$

- **Baire Category Theorem:**
If $X$ is a complete metric space, then $X$ is a Baire space:

  - For any sequence $\theset{U_k}$ of open, dense sets, $\intersect_k U_k$ is also dense.
  - $X$ is *not* a countable union of nowhere-dense sets

- **Nested Interval Characterization of Completeness:**
$\RR$ being complete $\implies$ for any sequence of intervals $\theset{I_n}$ such that $I_{n+1} \subseteq I_n$, $\intersect I_n \neq \emptyset$.

- **Convergence Characterization of Completeness:**
$\RR$ being complete is equivalent to "absolutely convergent implies convergent" for sums of real numbers.

- Compacts subsets $K \subseteq \RR^n$ are also *sequentially compact*, i.e. every sequence in $K$ has a convergent subsequence.

- Closed subsets of compact sets are compact.

- Every compact subset of a Hausdorff space is closed


- **Urysohn's Lemma:**
For any two sets $A, B$ in a metric space or compact Hausdorff space $X$, there is a function $f:X \to I$ such that $f(A) = 0$ and $f(B) = 1$.

- Continuous compactly supported functions are
  - Bounded almost everywhere
  - Uniformly bounded
  - Uniformly continuous

    *Proof:*

    ![[figures/2019-12-19-16-49-56.png]]
		
- Uniform convergence allows commuting sums with integrals


:::{.proposition title="?"}
\[
f_k \converges{\ae}\to f \text{ and }
\norm{f_k}_p \leq M
\implies f\in L^p \text{ and } \norm{f}_p \leq M
.\]
:::

:::{.proof title="?"}
*Proof:* Apply Fatou to $\abs{f}^p$:
\[
\int \abs{f}^p = \int \liminf \abs{f_k}^p \leq \liminf \int \abs{f_k}^p = M
.\]
:::

:::{.proposition title="Continuity in $L^1$ holds for all $L^p$, translation operators are continuous"}
\[
f \text{ uniformly continuous }: \quad
\norm{\tau_h f - f}_{L^p(X)} \convergesto{h\to 0} 0 && \forall p
.\]
:::

:::{.proof title="?"}
Take $g_k \in C_c^0 \to f$, then $g$ is uniformly continuous, so
\[
\norm{\tau_h f - f}_p
\leq \norm{\tau_h f - \tau_h g}_p + \norm{\tau_h g - g}_p + \norm{g - f}_p \to 0
.\]
:::

:::{.proposition title="?"}
\[
(f, g) \in L^p\times L^q \implies f\convolve g \text{ uniformly continuous}
.\]
:::

:::{.proof title="?"}
Use Young's inequality
\[
\norm{\tau_h(f\ast g) - f\ast g}_\infty
&= \norm{(\tau_h f - f) \ast g}_\infty \leq \norm{\tau_hf - f}_p \norm{g}_q \to 0
.\]

:::

:::{.proposition title="?"}
\[
\inner{f}{\phi} \da \int f \cdot \phi = 0 \quad \forall \phi\in C_c^0 \implies f \eqae 0
.\]
:::

:::{.proof title="?"}
Let $A$ be an interval, choose $\phi_k \to \chi_A$, then $\int f \chi_A = 0$ for all intervals.
So this holds for any Borel set $A$.
Then just take $A_1 = \theset{f > 0}$ and $A_2 = \theset{f < 0}$, then $\int_\RR f = \int_{A_1} f + \int_{A_2}f = 0$.
:::


