# Problem Set 2

## The Spin group

:::{.problem title="?"}

- a: Show that for each $n \geq 2$, the group $\SO_n$ has a unique connected 2 -fold covering space. Call this space $\Spin(n)$

- b: Use the group structure of $\SO_n$ to induce a group structure on $\Spin(n)$.

- c: What familiar space is $\Spin(3) ?$ Also, show that as topological groups, $\Spin(3) \cong S U(2)$.

:::


:::{.solution title="Part a"}
This is clear for $n=2$ since $\SO_2$ is diffeomorphic to $S^1$, so $\pi_1 \SO_2 = \ZZ$, which has a unique subgroup of index $[\ZZ: 2\ZZ] = 2$. 
By the correspondence between connected covering spaces of $X$ and conjugacy classes of subgroups of $\pi_1 X$, this implies the existence of a unique degree 2 connected covering space $\Spin_2$.


It now suffices to show that $\pi_1 \SO_n = \ZZ/2\ZZ$ for $n\geq 3$, since this also has a unique subgroup of index 2 (namely the trivial group), which corresponds to a degree 2 covering space.

There is a cofiber sequence
\[
\SO_{n-1}\to \SO_n \to S^{n-1}
,\]
so consider the long exact sequence in homotopy.
Since $k\geq 2$ and $\pi_k S^n = 1$ for $k\leq n-1$, we have

\begin{tikzcd}
	&&&& \cdots \\
	\\
	{\pi_2 \SO_{n-1}} && {\pi_2 \SO_{n}} && \textcolor{rgb,255:red,214;green,92;blue,92}{\pi_2 S^n = 1} \\
	\\
	{\pi_1 \SO_{n-1}} & {} & {\pi_1 \SO_{n}} && \textcolor{rgb,255:red,214;green,92;blue,92}{\pi_1S^n = 1}
	\arrow[from=3-1, to=3-3]
	\arrow[from=3-3, to=3-5]
	\arrow[from=3-5, to=5-1]
	\arrow["\cong", color={rgb,255:red,92;green,214;blue,214}, from=5-1, to=5-3]
	\arrow[from=5-3, to=5-5]
	\arrow[from=1-5, to=3-1]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsOCxbMCw0LCJcXHBpXzEgXFxTT197bi0xfSJdLFsxLDRdLFsyLDQsIlxccGlfMSBcXFNPX3tufSJdLFs0LDQsIlxccGlfMVNebiA9IDEiLFswLDYwLDYwLDFdXSxbMCwyLCJcXHBpXzIgXFxTT197bi0xfSJdLFsyLDIsIlxccGlfMiBcXFNPX3tufSJdLFs0LDIsIlxccGlfMiBTXm4gPSAxIixbMCw2MCw2MCwxXV0sWzQsMCwiXFxjZG90cyJdLFs0LDVdLFs1LDZdLFs2LDBdLFswLDIsIlxcY29uZyIsMCx7ImNvbG91ciI6WzE4MCw2MCw2MF19LFsxODAsNjAsNjAsMV1dLFsyLDNdLFs3LDRdXQ==)

So $\pi_1 \SO_{n-1} \cong \pi_1 \SO_n$ for $n\geq 2$, and we're reduced to computing $\pi_1 \SO_3$.
There is a homeomorphism
\[
\Psi: \SO_3 &\to \RP^3 \\
(\vector v, \phi) &\mapsto [\phi\vector v]
,\]
which represents a rotation in $\RR^3$ as an axis $(\vector v, \phi) \in S^2 \cross [-\pi, \pi]$ where $\vector v$ is a unit vector representing an axis of rotation and $\phi$ is an angle.
We're now reduced to computing $\pi_1 \RP^3$.
Using the standard cell complex for $\RP^n$, we have
\[
H^k(\RP^n; \ZZ) = 
\begin{cases}
\ZZ & k=0,3
\\
\ZZ/2\ZZ & k=1
\\
0 & \text{else},
\end{cases}
\]
and in particular, $H^1(\RP^3) = \ZZ/2\ZZ$.
Finally, by the Hurewicz theorem, there is an isomorphism $\pi_1(\RP^3) \iso H^1(\RP^3; \ZZ)$.

:::

:::{.solution title="Part b"}
Let $\phi: \Spin_n\to \SO_n$ be the covering map shown to exist in (a), then the claim is that the following lifts exist:

\begin{tikzcd}
	&&&& {\Spin_n} \\
	\\
	{\Spin_n\times\Spin_n} && {\SO_n\times\SO_n} && {\SO_  n}
	\arrow["{\varphi\times \varphi}", from=3-1, to=3-3]
	\arrow["{(g,h) \mapsto g\cdot h}", from=3-3, to=3-5]
	\arrow["\varphi"', from=1-5, to=3-5]
	\arrow[dashed, from=3-1, to=1-5]
	\arrow[dashed, from=3-3, to=1-5]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsNCxbMCwyLCJcXFNwaW5fblxcdGltZXNcXFNwaW5fbiJdLFsyLDIsIlxcU09fblxcdGltZXNcXFNPX24iXSxbNCwyLCJcXFNPXyAgbiJdLFs0LDAsIlxcU3Bpbl9uIl0sWzAsMSwiXFx2YXJwaGlcXHRpbWVzIFxcdmFycGhpIl0sWzEsMiwiKGcsaCkgXFxtYXBzdG8gZ1xcY2RvdCBoIl0sWzMsMiwiXFx2YXJwaGkiLDJdLFswLDMsIiIsMix7InN0eWxlIjp7ImJvZHkiOnsibmFtZSI6ImRhc2hlZCJ9fX1dLFsxLDMsIiIsMSx7InN0eWxlIjp7ImJvZHkiOnsibmFtZSI6ImRhc2hlZCJ9fX1dXQ==)

Then the map $\Spin_n\times \Spin_n\to \Spin_n$ yields the desired group structure.
Explicitly, we can write this map as
\[
\Spin_n \times \Spin_n &\to \Spin_n \\
(g, h) &\mapsto \phi\inv( \phi(g) \cdot \phi(h))
.\]

That this lift exists is a consequence of the lifting lemma, using that \[
f_* \pi_1(\Spin_n\times \Spin_n) \subseteq \phi_* \pi_1(\Spin_n)
\]
where $f: \Spin_n\times\Spin_n\to \SO_n$ is the lower composite.
This condition is trivially satisfied since $\Spin_n$ is simply connected, so $\pi_1(\Spin_n\times \Spin_n) = \pi_1(\Spin_n) \times \pi_1(\Spin_n) = 1$.

The group axioms follow readily:

- The identity is $\phi\inv(e)$, since for $g, h\in \Spin_n$,
\[
a \phi\inv(e) = \phi\inv(\phi(a) \cdot e ) = \phi(\phi\inv(a)) = a
,\]
where in the last step we've used surjectivity of $\phi$.

- Switching to additive notation momentarily, inverses are given by $-a\da \phi\inv(-\phi(a))$:
\[
a \cdot \phi\inv(-\phi(a)) = \phi\inv\qty{ \phi(a) + \phi\phi\inv(-\phi(a))}
=\phi\inv\qty{\phi(a) + (-\phi(a))} = \phi\inv(e)
.\]

- Associativity follows similarly.

:::

:::{.solution title="Part c" .foldopen}
$\Spin_3 \to \SO_3$ is a covering space which is simply connected, and is thus the universal cover.
Since $\SO_3 \iso \RP^3$ topologically and the universal cover of $\RP^3$ is $S^3$, we have $\Spin_3\iso S^3$ topologically.

To see that $\Spin_3\cong \SU_2$ as topological groups, note that we can write
\[
\SU_2 = \ts{A_{z, w} \da \matt z {-\bar w} w {\bar z} \in \Mat(2\times 2; \CC) \st \det A_{z, w} = 1}
,\]
so $\abs{z}^2 + \abs{w}^2 = 1$ for any such matrix.

First let $Q = \gens{\vector 1, \vector i, \vector j, \vector k}$ denote the quaternions and define a map
\[
\Psi: \SU_2 &\to Q \\
A_{z, w} &\mapsto q_{z, w} \da a\vector 1 + b\vector i + c\vector j + d\vector k
\]
where $z = a+ib$ and $w=c +id$.
Note that $\norm{q_{z, w}} = \abs{a}^2 + \abs{b}^2 + \abs{c}^2 + \abs{d}^2 = \abs{z}^2 + \abs{w}^2 = 1$, so the image is in fact the unit quaternions $\hat Q$.
The claim is that $\Psi$ is a diffeomorphism and a group homomorphism on the underlying additive groups.

Given this claim, we can further define
\[
\Phi: \hat{Q} &\to \SO_3 \\
q &\mapsto (\vector v\mapsto qvq\inv)
.\]
which is an isometry of $\RR^3$ and thus yields a rotation.




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
