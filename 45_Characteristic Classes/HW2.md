# Problem Set 2

## The Spin group

:::{.problem title="?"}

- a: Show that for each $n \geq 2$, the group $\SO_n$ has a unique connected 2 -fold covering space. Call this space $\Spin(n)$

- b: Use the group structure of $\SO_n$ to induce a group structure on $\Spin(n)$.

- c: What familiar space is $\Spin(3) ?$ Also, show that as topological groups, $\Spin(3) \cong S U(2)$.

:::


:::{.solution title="Part a"}
It suffices to show that $\pi_1 \SO_n = \ZZ/2\ZZ$ for $n\geq 2$, since this has a unique subgroup of index 2 (namely the trivial group), which corresponds to a covering space of degree 2.
There is a cofiber sequence
\[
\SO_{n-1}\to \SO_n \to S^{n-1}
.\]


:::


## Spin Lifts

:::{.problem title="?"}
For non-injective (or non-effective) structure groups $G$, we imposed an extra requirement that the lifts $\phi_{i j} \to G$ of the transition maps $\phi_{i j}: U_{i} \cap U_{j} \to \Homeo(F, F)$ form a cocycle. 

Give an example of an oriented $n$-plane bundle with transition maps $\phi_{i j}$ which do lift to $\Spin(n)$ but where the lifts cannot be chosen to satisfy the cocycle condition. 

> Hint: decompose the sphere as a union of two hemispheres and consider the Čech cocycle induced by a generator of $\pi_{1}(\SO_3)=\ZZ / 2 \ZZ$, say. This corresponds to an oriented 3-plane bundle over $S^{2}$, and does not lift to a Spin-bundle. Further divide the sphere into open sets so that the intersection of each pair is contractible. Observe that you can lift the cocycle on each of these intersections, but that the lifts do not form a cocycle.


:::

## More on existence of $\Spin$ structures

:::{.problem title="?"}
- a:
Show that there is an exact sequence of Čech cohomology groups
\[
\check{H}^{1}(X ; \ZZ / 2 \ZZ) \to \check{H}^{1}(X, \Spin_n \to \check{H}^{1}(X ; \SO_n) \stackrel{\delta}{\to} \check{H}^{2}(X ; \ZZ / 2 \ZZ)
\]

- b:
Given an $\SO_n$-bundle $P$ coming from $\alpha \in \check{H}^{1}(X ; \SO_n)$, let $w_{2}(P)=\delta(\alpha)$. Deduce that $P$ admits a lift to a $\Spin_n$-bundle if and only if $w_{2}(P)=0$.

- c:
Compute $w_{2}$ for your example in the previous problem.

- d:
Extend the exact sequence from part a to an exact sequence
\[
0 \to \check{H}^{1}(X ; \ZZ / 2 \ZZ) \to \check{H}^{1}(X; \Spin_n) \to \check{H}^{1}(X ; \SO_n) \stackrel{\delta}{\to} \check{H}^{2}(X ; \ZZ / 2 \ZZ)
,\]
and deduce that if an $\SO_n$-bundle $E$ admits a $\Spin_n$-lift then the set of lifts form an affine space for $H^{1}(X; \ZZ / 2 \ZZ)$.

:::

## Segal, Proposition 2.1.

- a:
Suppose that $F: \cat{C} \to \cat{D}$ is a functor. Show that there is an induced continuous map of nerves
\[
\mathcal{N F}: \nerve{\cat C} \to \nerve{\cat D}
.\]

- b:
Suppose that $F_{0}, F_{1}: \mathscr{C} \to \mathscr{D}$ are functors and $\eta$ is a natural transformation from $F_{0}$ to $F_{1}$. Show that $\nerve{ F_{0} }$ and $\nerve{F_{1} }$ are homotopic. 

  > Hint: think of $\eta$ as a map from $\mathscr{C} \times(\bullet \to \bullet)$ to $\mathscr{D}$.

- c:
Give another proof that if $\mathscr{C}$ has an initial (or terminal) object then $\mathscr{C}$ is contractible.

## Spin structures again.

- a:
Let $f: G \to H$ be a continuous homomorphism of (reasonable) topological groups. Show that for appropriate choices of $\B G$ and $\B H$ there is an induced fibration $\B G \to \B H$. 

  > Hint: choose any $E G$ and $E H$ and observe that $G$ acts on $E G \times E H$, using $f$.

- b:
Setting $G=\Spin_n$ and $H=\SO_n$, what is the fiber of the fibration $\B \Spin_n \to \B \SO_n$?

- c:
Show that this fibration is principal (see the section in Hatcher on Postnikov towers).

- d:
Give another construction of the obstruction $w_{2}$ to existence of a $\Spin$-structure and another proof that the set of $\Spin$-structures on an oriented vector bundle $E$ with $w_{2}(E)=0$ is in bijection with $H_{1}(B ; \ZZ / 2 \ZZ)$.


:::{.solution title="a" .foldopen}
Make $H$ into a left $G\dash$space by $g\cdot x \da f(g)x$, and note that $G$ itself is a right $G\dash$space.
Then the mixing construction shows that any principal $G\dash$bundle $P\to X$ can be induced to an $H\dash$bundle $P\mix{G} H \to X$.
So take $\EG\to \BG$, a principal $G\dash$bundle, and induce to the $H\dash$bundle $\EG \mix{G} H\to X$.
Now setting $P = \E H$ and $X = \B H$ in this construction yields $\E G \mix{G} \E H \to \B H$.
Quotienting by the $G\dash$action yields $(\E G \mix{G} \E H)/G \to \B H$, i.e. $\B G \times \E H/G \to \B H$, and ???


:::


:::{.solution title="b" .foldopen}
Fact: If $G_1\to G_2$ is a group morphism, then there is a fiber sequence
\[
\hofib(f) \homotopic G_2/G_1 \to G_1\to G_2
.\]


:::


:::{.solution title="c"}

:::


:::{.solution title="d"}

:::
