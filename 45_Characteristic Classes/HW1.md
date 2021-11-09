# Problem Set 1

## 1

:::{.problem title="?"}
With the definition of a vector bundle from class, show that the vector space operations define continuous maps:

\[
&+: E \fiberprod{B} E \rightarrow E \\
&\times: \mathbb{R} \times E \rightarrow E
\]
:::

:::{.remark}
Definition of vector bundle: need charts $(U, \phi)$ with $\phi: \pi\inv(U) \to U\times\RR^n$ which when restricted to a fiber $F_b$ yields an isomorphism $F_b \iso \RR^n$.
What are these maps??
:::

:::{.solution}
?
:::


## 2. 

:::{.problem title="?"}
Suppose you are given the following data:

- Topological spaces $B$ and $F$

- A set $E$ and a map of sets $\pi: E \rightarrow B$

- An open cover $\mathcal{U}=\left\{U_{i}\right\}$ of $B$ and for each $i$ a bijection $\phi: \pi^{-1}\left(U_{i}\right) \rightarrow U_{i} \times F$ so that $\pi \circ \phi_{i}=\pi$.

Give conditions on the maps $\phi_{i}$ so that there is a topology on $E$ making $\phi: E \rightarrow B$ into a fiber bundle with $\left\{\left(U_{i}, \phi_{i}\right)\right\}$ as an atlas.

:::

:::{.solution}
?
:::

## 3. 

:::{.problem title="?"}
An *oriented $n$-dimensional vector bundle* is a vector bundle $\pi: E \rightarrow B$ together with an orientation of each fiber $E_{b}$, so that these orientations are continuous in the following sense. 

For each $b \in B$ there is a chart $(U, \phi)$ with $b \in U$ and $\phi: \pi^{-1}(U) \rightarrow U \times \mathbb{R}^{n}$ so that for all $b^{\prime} \in U$,
\[
\left.\phi\right|_{E_{b^{\prime}}}: E_{b^{\prime}} \rightarrow \mathbb{R}^{n}
\]
is orientation-preserving. 


Show that given an oriented $n$-dimensional vector bundle there is an induced principal $G L_{+}\left(\mathbb{R}^{n}\right)$-bundle (the "bundle of oriented frames"), and conversely given a principal $G L_{+}\left(\mathbb{R}^{n}\right)$-bundle there is an induced oriented $n$-plane bundle.



:::

:::{.solution}
?
:::

## 4. 

:::{.problem title="?"}
A Riemannian metric on a vector bundle $\pi: E \rightarrow B$ is an inner product $\langle\cdot, \cdot\rangle_{b}$ on each fiber $E_{b}$ of $E$, which is continuous in the sense that the induced map $E \oplus E=E \times_{B} E \rightarrow \mathbb{R}$ is continuous. 

Show that given a Riemannian metric on a vector bundle, there is an induced principal $O(n)$-bundle (the "bundle of orthonormal frames"), and conversely given a principal $O(n)$-bundle there is an induced vector bundle with Riemannian metric.



:::

:::{.solution}
?
:::

## 5. 

:::{.problem title="?"}
What operation on principal $O(n)$-bundles corresponds to dualizing a vector bundle? What about the direct sum of vector bundle?
:::

:::{.solution}
?
:::

## 6. 

:::{.problem title="?"}
For nice spaces $X$ (e.g. CW complexes) and abelian groups $G$, there is a canonical isomorphism 
\[
\check{H}^{i}(X ; G) \cong H^{i}(X ; G)
\]
between Čech and singular cohomology of $X$ with coefficients in $G$. 

> A nice, readable proof can be found in Frank Warner's Foundations of Differential Manifolds and Lie Groups, Chapter 5. 
> In the rest of this problem, cohomology either means Čech cohomology or singular cohomology after applying this isomorphism.
 

- a: Let $\pi: E \rightarrow B$ be an $n$-dimensional vector bundle, or equivalently, a principal $G L(n, \mathbb{R})$-bundle, given by a Čech cocycle $\phi \in H^{1}(B ; G L(n, \mathbb{R}))$. Show that the sign of the determinant 
\[
\sgn\det: \GL_n(\mathbb{R}) \rightarrow\{\pm 1\} \cong \mathbb{Z} / 2 \mathbb{Z}
\]
induces a map
  \[
  \check{H}^{1}(B ; G L(n, \mathbb{R})) \rightarrow \check{H}^{1}(B ; \mathbb{Z} / 2 \mathbb{Z})
  ,\]
  and so $\phi$ induces an element $w_{1}(E) \in H^{1}(B ; \mathbb{Z} / 2 \mathbb{Z})$.

- b: Compute $w_{1}$ for the trivial line bundle (1-dimensional vector bundle) over the circle and for the Möbius band.

- c: Prove that (for nice spaces) a line bundle $\pi: E \rightarrow B$ is trivial if and only if $w_{1}(E)=0 \in$ $H^{1}(B ; \mathbb{Z} / 2 \mathbb{Z})$ 

:::

:::{.solution}
?
:::

## 7. 

:::{.problem title="?"}
Show that the exact sequence of abelian topological groups


$$
0 \rightarrow \mathbb{Z} \rightarrow \mathbb{R} \rightarrow S^{1}=G L(1, \mathbb{C}) \rightarrow 0
$$

induces an exact sequence in Čech cohomology

$$
\check{H}^{1}(B, \mathbb{Z}) \rightarrow \breve{H}^{1}(B, \mathbb{R}) \rightarrow \check{H}^{1}\left(B ; S^{1}\right) \stackrel{\delta}{\rightarrow} \check{H}^{2}(B ; \mathbb{Z})
$$

Given a complex line bundle (principal $G L(1, \mathbb{C})$-bundle) $\pi: E \rightarrow B$ coming from the cocycle data $\phi \in H^{1}(B ; G L(1, \mathbb{C}))$, let $c_{1}(E)=\delta(\phi)$. Compute $c_{1}(E)$ for some complex line bundle over $S^{2}$.
:::

:::{.solution}
?
:::
