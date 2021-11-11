---
order: 20
---

# Basics

## Compactness
    
:::{.theorem title="Folland 0.25"}
For $E \subseteq (X, d)$ a metric space, TFAE:

- $E$ is complete and totally bounded.
- $E$ is sequentially compact: Every sequence in $E$ has a subsequence that converges to a point in $E$.
- $E$ is compact: every open cover has a finite subcover.

Note that $E$ is complete as a metric space with the induced metric iff $E$ is closed in $X$, and $E$ is bounded iff it is totally bounded.
:::


## Topology / Sets

:::{.proposition title="Compact if and only if sequentially compact for metric spaces"}
Metric spaces are compact iff they are sequentially compact, (i.e. every sequence has a convergent subsequence).
:::

#todo Proof

:::{.proposition title="A unit ball that is not compact"}
The unit ball in $C([0, 1])$ with the sup norm is not compact.
:::

:::{.proof title="?"}
Take $f_k(x) = x^n$, which converges to $\chi(x=1)$. 
The limit is not continuous, so no subsequence can converge.
:::

:::{.theorem title="Heine-Borel"}
$X\subseteq \RR^n$ is compact $\iff X$ is closed and bounded.
:::

:::{.proposition title="Geometric Series"}
\[
\sum_{k=0}^\infty x^k = \frac 1 {1-x} \iff \abs{x} < 1
.\]
:::

:::{.corollary title="?"}
\[
\sum_{k=0}^\infty \frac 1 {2^k} = 1
.\]
:::

:::{.proposition title="?"}
Singleton sets in $\RR$ are closed, and thus $\QQ$ is an $F_\sigma$ set.
:::

:::{.lemma title="?"}
Any nonempty set which is bounded from above (resp. below) has a well-defined supremum (resp. infimum).
:::

## Smallness for sets

:::{.proposition title="Finite unions of nowhere dense sets are still nowhere dense"}
A *finite* union of nowhere dense is again nowhere dense.
:::

:::{.theorem title="Baire"}
$\RR$ is a **Baire space**, i.e. $\RR$ can not be written as a countable union of nowhere dense sets.
:::

:::{.proposition title="?"}
The Cantor set is closed with empty interior.
:::

:::{.proof title="?"}
Its complement is a union of open intervals, and can't contain an interval since intervals have positive measure and $m(C_n)$ tends to zero.
:::

:::{.corollary title="?"}
The Cantor set is nowhere dense.
:::

## Smallness for functions

:::{.proposition title="Existence of Smooth Compactly Supported Functions"}
There exist smooth compactly supported functions, e.g. take 
\[
f(x) = e^{-\frac{1}{x^2}} \chi_{(0, \infty)}(x)
.\]
:::

- **Arzela - Ascoli 1**:
If $\mathcal{F}$ is pointwise bounded and equicontinuous, then $\mathcal{F}$ is totally bounded in the uniform metric and its closure $\overline{\mathcal{F}} \in C(X)$ in the space of continuous functions is compact.

- **Arzela - Ascoli 2**:
If $\theset{f_k}$ is pointwise bounded and equicontinuous, then there exists a continuous $f$ such that $f_k \mapsvia{u} f$ on every compact set.

#todo Proof



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
