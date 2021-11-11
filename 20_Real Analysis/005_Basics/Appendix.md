---
order: 999
---

# Appendix

An alternative characterization of **uniform continuity**:
$$
\left\|\tau_{y} f-f\right\|_{u} \rightarrow 0 \text { as } y \rightarrow 0
$$

Lemma:
Measurability is not preserved by homeomorphisms.

> Counterexample: there is a homeomorphism that takes that Cantor set (measure zero) to a fat Cantor set

## Undergraduate Analysis Review

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

- **Urysohn's Lemma:**
For any two sets $A, B$ in a metric space or compact Hausdorff space $X$, there is a function $f:X \to I$ such that $f(A) = 0$ and $f(B) = 1$.

- Continuous compactly supported functions are
  - Bounded almost everywhere
  - Uniformly bounded
  - Uniformly continuous

    *Proof:*

    ![[figures/2019-12-19-16-49-56.png]]
		
- Uniform convergence allows commuting sums with integrals

- Closed subsets of compact sets are compact.

- Every compact subset of a Hausdorff space is closed


## Big Counterexamples


## Errata

- **Equicontinuity**:
If $\mathcal F \subset C(X)$ is a family of continuous functions on $X$, then $\mathcal F$ *equicontinuous* at $x$ iff

\[
\forall \varepsilon > 0 ~~\exists U \ni x \text{ such that } y\in U \implies \abs{f(y) - f(x)} < \varepsilon \quad \forall f\in \mathcal{F}
.\]

- **Arzela - Ascoli 1**:
If $\mathcal{F}$ is pointwise bounded and equicontinuous, then $\mathcal{F}$ is totally bounded in the uniform metric and its closure $\overline{\mathcal{F}} \in C(X)$ in the space of continuous functions is compact.

- **Arzela - Ascoli 2**:
If $\theset{f_k}$ is pointwise bounded and equicontinuous, then there exists a continuous $f$ such that $f_k \mapsvia{u} f$ on every compact set.




**Lemma:**
\[
f_k \converges{a.e.}\to f ,\quad
\norm{f_k}_p \leq M
\implies f\in L^p \text{ and } \norm{f}_p \leq M
.\]

> *Proof:* Apply Fatou to $\abs{f}^p$:
\[
\int \abs{f}^p = \int \liminf \abs{f_k}^p \leq \liminf \int \abs{f_k}^p = M
.\]

**Lemma:**
If $f$ is uniformly continuous, then
\[
\norm{\tau_h f - f}_p \converges{L^p}\to 0 \quad \text{for all } p
.\]

**Lemma**:
$\norm{\tau_h f - f}_p \to 0$ for every $p$.

> - i.e. "Continuity in $L^1$" holds for all $L^p$.
> - i.e. Translation operators are continuous.

> *Proof:*
> Take $g_k \in C_c^0 \to f$, then $g$ is uniformly continuous, so
\[
\norm{\tau_h f - f}_p
\leq \norm{\tau_h f - \tau_h g}_p + \norm{\tau_h g - g}_p + \norm{g - f}_p \to 0
.\]

**Lemma:**
For $f\in L^p, g\in L^q$, $f\ast g$ is uniformly continuous.

> *Proof*:
> Use Young's inequality
\[
\norm{\tau_h(f\ast g) - f\ast g}_\infty
&= \norm{(\tau_h f - f) \ast g}_\infty \leq \norm{\tau_hf - f}_p \norm{g}_q \to 0
.\]

**Lemma**:
If $\int f \phi = 0$ for every $\phi \in C_c^0$, then $f = 0$ almost everywhere.

> *Proof:*
> Let $A$ be an interval, choose $\phi_k \to \chi_A$, then $\int f \chi_A = 0$ for all intervals.
> So this holds for any Borel set $A$.
> Then just take $A_1 = \theset{f > 0}$ and $A_2 = \theset{f < 0}$, then $\int_\RR f = \int_{A_1} f + \int_{A_2}f = 0$.

## The Fourier Transform

**Some Useful Properties:**

\[
\widehat{f\ast g}(\xi)
&= \hat f(\xi) \cdot \hat g (\xi) \\
\widehat{\tau_h f}(\xi)
&= e^{2\pi i \xi \cdot h}\widehat{f}(\xi) \\
\widehat{e^{2\pi i \xi \cdot h}f(\xi)}
&= \tau_{-h}\widehat f(\xi) \\
\widehat{f \circ T}(\xi)
&= \abs{\det T}\inv (\hat f \circ T^{-t})(\xi) \\
\dd{}{\xi} \widehat{f}(\xi)
&= -2\pi i \cdot \widehat {\xi f} (\xi) \\
\widehat{\dd{}{\xi} f}(\xi)
&= 2\pi i \xi \cdot \widehat{f}(\xi)
.\]

**Some Useful Transform Pairs:**

\[
\text{Dirichlet:}
&& \chi_{\theset{-\frac{1}{2} \leq x \leq \frac{1}{2}}}
&\iff \mathrm{sinc}(\xi) \\
\text{Fejer:}
&& \chi_{\theset{-1 \leq x \leq 1}} (1 - \abs{x})
&\iff \mathrm{sinc}^2(\xi) \\
\text{Poisson:}
&& \frac{1}{\pi} \frac{1}{1+x^2}
&\iff e^{2\pi \abs{\xi}} \\
\text{Gauss-Weierstrass:}
&& e^{-\pi x^2}
&\iff e^{-\pi \xi^2}
.\]
