# Surfaces and Manifolds

:::{.remark}
The most common spaces appearing in this theory:

- $\SS ^2$, 
- $\TT^2 \definedas  S^1\cross S^1$, 
- $\RP^2$
- $\KK$ the Klein bottle
- $\bbm$ the Möbius Strip
- $\Sigma_n \definedas \#_{i=1}^n \TT^2$.

The first 4 can be obtained from the following pasting diagrams:

![Pasting Diagrams for Surfaces](PastingDiagrams.png)

:::

## Classification of Surfaces

:::{.theorem title="Classification of Surfaces"}
The set of surfaces under connect sum forms a monoid with the presentation
\[  
\gens{ \SS^2, \RP^2, \TT \suchthat \SS^2 = 0, 3\RP^2 = \RP^2 + \TT^2} = \ts{ \Sigma_{g, n} \st g, n \in \ZZ^{\geq 0} } 
.\]
where $\Sigma_{g, n}$ is a surface of genus $g$ with $n$ discs removed to form boundary components.

Surfaces are classified up to homeomorphism by orientability and $\chi$, or equivalently "genus" 

- In orientable case, actual genus, $g$ equals the number of copies of $\TT^2$.
- In nonorientable case, $k$ equals the number of copies of $\RP^2$.

In each case, there is a formula
\[  
\chi(X) = 
\begin{cases}
2-2g - b & \text{orientable} \\
2 - k & \text{non-orientable}.
\end{cases}
\]
:::

:::{.proposition title="Polygon Models for Surfaces"}
Every surface can be obtained as the identification space of a polygon labeled with sides \( \alpha_i, \beta_i, \rho_i \).

![figures/image_2021-04-08-19-40-14.png](figures/image_2021-04-08-19-40-14.png)

![figures/image_2021-04-08-19-40-31.png](figures/image_2021-04-08-19-40-31.png)

![figures/image_2021-04-08-19-40-41.png](figures/image_2021-04-08-19-40-41.png)

:::

\todo[inline]{Examples, general procedure?}

:::{.fact table="Table of surfaces possible for a given Euler characteristic"}

| Orientable?  | $-4$       | $-3$        | $-2$       | $-1$        | $0$                  | $1$     | $2$         |
| ------------ | ---        | ----        | ----       | ---         | ---                  | ---     | ---         |
| Yes          | $\Sigma_3$ | $\emptyset$ | $\Sigma_2$ | $\emptyset$ | $\TT^2, S^1\cross I$ | $\DD^2$ | $\SS^2$     |
| No           | ?          | ?           | ?          | ?           | $\KK, \bbm$          | $\RP^2$ | $\emptyset$ |

:::

:::{.proposition title="Inclusion-Exclusion"}
\[  
X = U\cup V \implies \chi(X) = \chi(U) + \chi(V) - \chi (U\cap V)
.\]
:::
:::{.proof}
Todo
:::
\todo{Proof.}

:::{.corollary title="Euler for Connect Sums"}
\[  
\chi(A \# B) = \chi(A) + \chi(B) - 2
.\]
:::
:::{.proof}
Set $U= A, B=V$, then by definition of the connect sum, $A\cap B = \SS^2$ where $\chi(\SS^2) = 2$
:::

:::{.proposition title="Decomposing $\RP^2$"}
\[  
\RP^2 = \bbm \disjoint_{\id_{\bd \bbm}} \bbm
.\]
:::

:::{.proposition title="Decomposing a Klein Bottle"}
\[  
\KK \cong \RP^2 \# \RP^2
.\]
:::
:::{.proof}
Todo
:::
\todo{Proof.}

:::{.proposition title="Rewriting a Klein Bottle"}
\[  
\RP^2 \# \KK \cong \RP^2 \# \TT^2
.\]
:::
:::{.proof}
Todo
:::
\todo{Proof.}

## Manifolds

:::{.remark}
To show something is not a manifold, try looking at local homology. 
Can use point-set style techniques like removing points, i.e. $H_1(X, X-\pt)$; this should essentially always yield $\ZZ$ by excision arguments.
:::

:::{.proposition title="Dimension vanishing for homology of manifolds"}
If $M^n$ is a closed and connected $n\dash$manifold, then $H^{\geq n} X = 0$.
:::

:::{.proposition title="Top homology for manifolds"}
If $M^n$ is a closed connected manifold, then $H_n = \ZZ$ and $\tor(H_{n-1}) = 0$.
More generally, 
\[
\begin{cases}
\ZZ & M^n \text{ is orientable } 
\\
0 & \text{else}.
\end{cases}
\]
:::

:::{.proposition title="Poincaré Duality for manifolds"}
For $M^n$ a closed orientable manifold without boundary and $\FF$ a field,
\[
H_k(M^n; \FF) \cong H^{n-k}(M^n; \FF)
\iff
M^n \text{ is closed and orientable}
.\]

:::

:::{.proposition title="Relative Poincaré Duality for manifolds"}
If $M^n$ is a closed orientable manifold with boundary then 
\[
H_k(M^n; \ZZ) \cong H^{n-k}(M^n, \del M^n; \ZZ)
.\]
:::

:::{.proposition title="Known Euler characteristics"}
If $M^n$ is closed and $n$ is odd, then $\chi(M^n) = 0$.
:::

:::{.proof title="?"}
Todo.
Uses Poincaré duality?
:::
\todo[inline]{Proof!}

:::{.proposition title="Nondegenerate intersection pairings"}
For $M^n$ closed and orientable, the intersection pairing is nondegenerate modulo torsion.
:::

:::{.proposition title="Orientation covers"}
For any manifold $X$ there exists a covering space $p: \tilde X_o\to X$, the **orientation cover**, where any map $Y\to X$ factors through $\tilde X_o$.
If $X$ is nonorientable, then $p$ is a double cover.
:::

:::{.theorem title="Lefschetz Duality"}
Todo
:::
\todo[inline]{Statement of Lefschetz duality.}

### 3-Manifolds, and Knot Complements

:::{.fact}
Every $\CC\dash$manifold is canonically orientable.
:::

:::{.proposition title="Homology of 3-manifolds"}
Let $M^3$ be a 3-manifold, then its homology is given by the following (by cases):

- Orientable: $H_* = (\ZZ, \ZZ^r, \ZZ^r, \ZZ)$

- Nonorientable: $H_* = (\ZZ, \ZZ^r, \ZZ^{r-1} \oplus \ZZ_2, \ZZ)$

:::

:::{.proposition title="Homotopy type of knot complements"}
For $K$ a knot, $S^3\sm K$ is a $K(\pi, 1)$, and $\RR^3 \sm K \homotopic S^2 \vee \qty{S^3 \sm K}$.
Moreover, if $K$ is nullhomologous and $X$ is any 3-manifold, 
\[
H_1\qty{X\sm \nu(K)} \cong H_1 X \cross \ZZ
\]
where $\nu(K)$ is a tubular neighborhood of $K$.
:::

:::{.proof title="?"}
Todo
:::
\todo[inline]{todo}

:::{.proposition title="Homology of knot complements in $S^3$"}
For $K$ a knot,
\[
H_*(S^3 \sm K) = [\ZZ, \ZZ, 0, 0, \cdots]
.\]
:::

:::{.proof}
Apply Mayer-Vietoris, taking $S^3 = n(K) \cup (S^3-K)$, where $n(K) \homotopic S^1$ and $S^3-K \cap n(K) \homotopic T^2$. 
Use the fact that $S^3-K$ is a connected, open 3-manifold, so $H^3(S^3-K) =0$.
:::

