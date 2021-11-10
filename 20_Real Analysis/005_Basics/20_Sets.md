---
order: 20
---

# Sets

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

## Functions

:::{.proposition title="Existence of Smooth Compactly Supported Functions"}
There exist smooth compactly supported functions, e.g. take 
\[
f(x) = e^{-\frac{1}{x^2}} \chi_{(0, \infty)}(x)
.\]
:::

#todo Proof
