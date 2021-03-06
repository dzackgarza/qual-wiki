---
order: 1
---

# Basics

:::{.remark}
Summary of useful qual tips:

- Slightly obvious but good to remember:
  - Subgroups of abelian groups are automatically normal.
  - If $N$ is normal in $G$, then $N$ is normal in any subgroup containing it.
  - If $N\leq G$ is the unique group of order $\size N$, then $N$ is normal (since any conjugate must have the same size).
  - Using the subgroup correspondence: if $L/H\leq G/H$ then $L\leq G$ has size $\size (L/H)\size H$.
- Sizes and structure:
  - Quotienting by bigger groups yields smaller indices:

\begin{tikzcd}
	1 & H & K & G \\
	\\
	{\size G = [G: 1]} & {[G:H]} & {[G:K]} & {[G:G] = 1}
	\arrow["\leq", hook, from=1-1, to=1-2]
	\arrow[""{name=0, anchor=center, inner sep=0}, "\leq", hook, from=1-2, to=1-3]
	\arrow["\leq", hook, from=1-3, to=1-4]
	\arrow["\geq", from=3-4, to=3-3]
	\arrow[""{name=1, anchor=center, inner sep=0}, "\geq", from=3-3, to=3-2]
	\arrow["\geq", from=3-2, to=3-1]
	\arrow["{[G, \wait]}", shorten <=9pt, shorten >=9pt, Rightarrow, from=0, to=1]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsOCxbMCwwLCIxIl0sWzEsMCwiSCJdLFsyLDAsIksiXSxbMywwLCJHIl0sWzAsMiwiXFxzaXplIEcgPSBbRzogMV0iXSxbMSwyLCJbRzpIXSJdLFsyLDIsIltHOktdIl0sWzMsMiwiW0c6R10gPSAxIl0sWzAsMSwiXFxsZXEiLDAseyJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6InRvcCJ9fX1dLFsxLDIsIlxcbGVxIiwwLHsic3R5bGUiOnsidGFpbCI6eyJuYW1lIjoiaG9vayIsInNpZGUiOiJ0b3AifX19XSxbMiwzLCJcXGxlcSIsMCx7InN0eWxlIjp7InRhaWwiOnsibmFtZSI6Imhvb2siLCJzaWRlIjoidG9wIn19fV0sWzcsNiwiXFxnZXEiXSxbNiw1LCJcXGdlcSJdLFs1LDQsIlxcZ2VxIl0sWzksMTIsIltHLCBcXHdhaXRdIiwwLHsic2hvcnRlbiI6eyJzb3VyY2UiOjIwLCJ0YXJnZXQiOjIwfX1dXQ==)

  - $x$ is central iff $[x] = \ts{e}$.
  - Unions aren't (generally) subgroups, intersections always are.
  - Coprime order subgroups intersect trivially.
  - Distinct subgroups of order $p^n, p^m$ can intersect trivially *or* in subgroups of order $p^{\ell}$.
- Conjugacy:
  - Sizes of conjugacy classes divide $\size  G$ (by orbit-stabilizer).
  - Conjugate subgroups have equal cardinality.
  - Normal subgroups absorb conjugacy classes, and are thus unions of conjugacy classes.
  - Reasoning about conjugacy classes: in $S_n$ they're precisely determined by cycle type, i.e. a partition of $n$.
  - Remembering the class equation: for literally any group action $\phi: G\actson X$, one has $X = \Fix(\phi) \disjoint' \Orb(x_i)$ as a disjoint union of fixed points and nontrivial orbits, since orbits partition $X$.
    Then take your action to be $G\actson G$ by $\phi: g.x\da gxg\inv$ to get $\Fix(\phi) = Z(G)$ and $\Orb(x_i) = \ts{gx_ig\inv} = [x_i]$ the conjugacy classes.
    Now apply orbit stabilizer to get $\Orb(x) \cong G/\Stab(x)$ where $\Stab(x) = Z(x) = C_G(x)$ the centralizer.
- Cosets:
  - Cosets partition a group.
  - Anything dealing with indices $[G:H]$: try just listing the cosets.
  - $aH = bH \iff ab\inv \in H$.
  - Showing subgroup containment: $K \subseteq H$ iff $kH = H$ for all $k\in K$.
- Sylows:
  - If $S_p$ is normal, then $S_p$ is characteristic.
    This is useful if $H\leq G$ and $P\in\Syl_p(H)$ is normal in $H$, then $P$ is also normal in $G$.

:::

:::{.remark}
For any $p$ dividing the order of $G$, $\mathrm{Syl}_p(G)$ denotes the *set* of Sylow$\dash p$ subgroups of $G$.
:::




## Definitions

:::{.fact}
An set morphism that is *either* injective or surjective between sets of the same size is automatically a bijection.
It turns out that a group morphism between groups of the same size that is either injective or surjective is automatically a bijection, and the inverse is automatically a group morphism, so bijective group morphisms are isomorphisms.

:::

:::{.fact title="Bezout's Identity"}
If $a, b\in \ZZ$ with $\gcd(a, b) = d$, then there exist $s,t\in \ZZ$ such that
\[
as + bt = d
.\]

This $d$ can be computed using the extended Euclidean algorithm.

:::

:::{.remark}
Useful context clue!
In particular, this works when $a, b$ are coprime and $d=1$, since you can write $x^1 = x^{as + bt} = x^{as}x^{bt}$ to get interesting information about orders of elements.
If you see "coprime" in a finite group question, try the division algorithm.
:::

:::{.definition title="Order"}
The **order** of an element $g\in G$, denoted $n \da o(g)$, is the smallest $n\in \ZZ^{\geq 0}$ such that $g^n = e$.
:::

:::{.exercise title="?"}
Show that the order of any element in a group divides the order of the group.
:::

:::{.definition title="Group Presentation"}
An expression of the form $G = \gens{S \st R}$ where $S$ is a set of elements and $R$ a set of words defining relations means that $G \da F[S] / \cl_n(R)$ where $F[S]$ is the free group on the set $S$ and $\cl_n(R)$ is the normal closure, the smallest normal subgroup of $F[S]$ containing $R$.
:::

:::{.remark}
Finding morphisms between presentations: if $G$ is presented with generators $g_i$ with relations $r_i$ and $H$ is any group containing elements $h_i$ also satisfying $r_i$, there is a group morphism
\[
\phi: G &\to H \\
g_i &\mapsto h_i \quad \forall i
.\]
Why this exists: the presentation yields a surjective morphism $\pi: F(g_i) \to G$ with $G\cong F(g_i) / \ker \pi$.
Define a map $\psi: F(g_i) \to H$ where $g_i\mapsto h_i$, then since the $h_i$ satisfy the relations $r_i$, $\ker \pi \subseteq \ker \psi$.
So $\psi$ factors through $\ker \pi$ yielding a morphism $F/\ker \pi \to H$.
:::

## Subgroups

:::{.definition title="Subgroup"}
A subset $H\subseteq G$ is a **subgroup** iff

1. Closure: $HH \subset H$
2. Identity: $e\in H$
3. Inverses: $g\in H \iff g\inv \in H$.
:::

:::{.definition title="Subgroup Generated by a Subset"}
If $H\subset G$, then $\gens{H}$ is the smallest subgroup containing $H$:
\[
\gens{H} = \intersect \theset{H\suchthat H\subseteq M \leq G} M = \theset{ h_1^{\pm 1} \cdots h_n^{\pm 1} \suchthat n\geq 0, h_i \in H}
\]
where adjacent $h_i$ are distinct.
:::

:::{.definition title="Commutator"}
The **commutator subgroup** of $G$ is denoted $[G, G] \leq G$.
It is the subgroup *generated* by all elementary commutators:
\[
[G, G] \da \gens{ aba\inv b\inv \st a, b\in G } 
.\]
It is the smallest normal subgroup $N\normal G$ such that $G/N$ is abelian, so if $H\leq G$ and $G/H$ is abelian, $H\subseteq [G, G]$.

> Note that elements in $[G, G]$ are generally *products* of elementary commutators, and not elementary themselves, since we're taking the group generated by them.

:::

:::{.proposition title="One-step subgroup test"}
If $H \subseteq G$ and $a,b\in H \implies ab\inv\in H$, then $H\leq G$.
:::

:::{.proof title="of the one-step subgroup test"}
\envlist

- Identity: $a=b=x\implies xx\inv=e\in H$
- Inverses: $a=e, b=x \implies x\inv \in H$.
- Closure: let $x, y\in H$, then $y\inv \in H$ by above, so $xy = x(y\inv )\inv \in H$.
:::

:::{.exercise title="On subgroups"}
\envlist

- Show that the intersection of two subgroups is again a subgroup.
  - Hint: one-step subgroup test.
- Show that if $H\da C_m, K\da C_n \leq G$ are cyclic, then $H \intersect K = C_{d}$ where $d \da \gcd(m, n)$.
- Show that the intersection of two subgroups with coprime orders is trivial.
- Show that the union of two subgroups $H, K$ is a subgroup iff $H \subset K$, and so is generally *not* a subgroup.
- Show that subgroups with the *same* prime order are either equal or intersect trivially.
- **Important for Sylow theory**: show (perhaps by example) that if $S_1, S_2$ are distinct subgroups of order $p^k$, then it's possible for their intersection to be trivial **or** for them to intersect in a subgroup of order $p^\ell$ for $1\leq \ell \leq k-1$.
- Give a counterexample where $H,K\leq G$ but $HK$ is not a subgroup of $G$.
:::

## Conjugacy

:::{.definition title="Conjugacy class"}
The **conjugacy class** of $h$ is defined as 
\[
C(h) \da \ts{ ghg\inv \st g\in G } 
.\]
:::

:::{.remark}
$[e] = \ts{ e }$ is always in a conjugacy class of size one -- this is useful for counting and divisibility arguments.
Conjugacy classes are **not** subgroups in general, since they don't generally contain $e$.
However, by orbit-stabilizer and the conjugation action, their sizes always divide the order of $G$.

**Useful qual fact**: $[x] = \ts{ x } \iff x\in Z(G)$, i.e. having a trivial conjugacy class is the same as being central.
:::

:::{.definition title="Conjugate subgroups"}
Two subgroups $H, K \leq G$ are **conjugate** iff there exists some $g\in G$ such that $gHg\inv = K$.
Note that all conjugate subgroups have the same cardinality.
:::

:::{.exercise title="?"}
Show that the size of a conjugacy class divides the order of a group.
:::

:::{.exercise title="?"}
Show that if $H < G$ is a proper subgroup, then $\Union_{g\in G} gHg\inv \subset G$ is a proper subset.

> Hint: consider the intersection and count.
> Try Orbit-stabilizer?

:::

:::{.solution}
Strategy: bound the cardinality.
All conjugates of $H$ have the same cardinality, say $\size  H = m$.
Suppose there are $n$ distinct conjugates of $H$.
Then they intersect only at the identity, so count their elements:
\[
\size  \Union_{g\in G} gHg\inv = 1 + n(m-1)
.\]
Use that $n = [G: N_G(H)]$ by Orbit-Stabilizer, and $N_G(H) \leq G \implies n \leq n' \da [G:H]$.
Now note $n'm = \size  H[G:H] = \size  G$ by Lagrange:
\[
\size  \Union_{g\in G} gHg\inv 
&= 1 + n(m-1) \\
&\leq 1 + n'(m-1) \\
&= 1 + n'm -n' \\
&= 1 + \size  G - n' \\
&= \size  G - (n' - 1) \\
&< \size  G && \iff n' \da [G:H] > 1
.\]
:::

:::{.exercise title="?"}
Show that normal groups absorb conjugacy classes: if $N\normal G$ and $[g_i]$ is a conjugacy class in $g$, either $[g_i] \subseteq N$ or $[g_i] \intersect N = \emptyset$.
:::

:::{.exercise title="?"}
Prove that the size of a conjugacy class of $g_i$ is the index of its centralizer, $[G: Z(g_i)] \da [G: C_G(g_i)]$.
:::

### Normal Subgroups

:::{.definition title="Normal subgroup"}
A subgroup $N\leq G$ is **normal** iff $gH = Hg$ for every $g\in G$, or equivalently $gHg\inv = H$ for all $g$, so $H$ has only itself as a conjugate.
We denote this by $N\normal G$.
Equivalently, for every inner automorphism $\psi \in \Inn(G)$, $\psi(N) = N$.
:::

:::{.proposition title="Normal iff disjoint union of conjugacy classes"}
$N\normal G \iff N = \disjoint' [h_i]$ is a disjoint union of conjugacy classes, where the index set for this union is one $h_i$ from each conjugacy class.
:::

:::{.proof title="?"}
Note that $C(h_i) = \ts{ gh_i g\inv \st g\in G }$, and $gh_i g\inv \in H$ since $H$ is normal, so $C(h_i) \subseteq G$ for all $i$.
Conversely, if $C(h_i) \subseteq H$ for all $h_i \in H$, then $gh_ig\inv \in H$ for all $i$ and $H$ is normal.
:::

:::{.exercise title="?"}
\envlist

- Show that if $H, K \normal G$ and $H\intersect K = \emptyset$, then $hk=kh$ for all $h\in H,k\in K$.
- Show that if $H,K\normal G$ are normal subgroups that intersect trivially, then $[H, K] = 1$ (so $hk = kh$ for all $k$ and $h$).

:::

:::{.exercise title="?"}
Prove that if $G$ is a $p\dash$group, every subgroup $N\normal G$ intersects the center $Z(G)$.

> Hint: use the class equation.

:::

:::{.solution}
\envlist

Easy solution:

- Use that $\size  H \mod p = 1$ since $H\leq G$ and $G$ is a $p\dash$group.
- Then use that $H$ is a union of conjugacy classes, and since $e\in H$ there is at least one class of size 1, so
\[
\size  H = \size  \disjoint' [h_i] = \size  [e] + \sum' \size  [h_i] \\
\implies 0 \equiv \size  H \equiv 1 + \sum' \size [h_i] \mod p
,\]
and since each $\size  [h_i]$ divides $\size  H$, not all can be of size $p^\ell$ since then the sum would be $0\mod p$.
So at least one other $\size  [h_i] = 1$, making that $h_i$ central.

Another solution:

- Idea: use the class equation to force $p$ to divide $\size (H \intersect Z(G))$.
  Applying it to $H$ yields
\[
H = Z(H) \disjoint_{i=1}^m [h_i]
,\]
where the $[h_i]$ are conjugacy classes of size greater than 1.

- Now use that $Z(H) = Z(G) \intersect H$, and since $p$ divides the LHS the result will follow if $p$ divides the size of the disjoint union on the RHS.
- This is true because each $\size [h_i] \neq 1$ and $[h_i]$ divides $\size  H$ which divides $\size  G$ which is a power of $p$.
  So $p\divides \size  [h_i]$ for each $i$.

:::


## Centralizing and Centers

:::{.definition title="Centralizer"}
The **centralizer of an element** is defined as 
\[
Z(h) \da C_G(h) \da \ts{ g\in G \st ghg\inv = h } 
,\]
the elements of $G$ the stabilize $h$ under conjugation.

The **centralizer of a subset** $H$ is defined as
\[
Z(H) \da C_G(H) \da \Intersect_{h\in H} C_G(h) \da \theset{g\in G \suchthat ghg\inv = h ~\forall h\in H}
,\]
the elements of $G$ that simultaneously stabilize all of $H$ pointwise under conjugation.
:::

:::{.definition title="Normalizer"}
\[
N_G(H) = \theset{g\in G \suchthat gHg\inv = H} = \Union_{M\in S} M, \quad S \da \theset{H\suchthat H \normal M \leq G} 
\]
Contrast to the centralizer: these don't have to fix $H$ pointwise, but instead can permute elements of $H$.
:::

:::{.remark}
$C_G(H) \normal N_G(H)$ for any $H$.
The main difference between these is that $C_G(S)$ has to centralize $H$ pointwise, where $N_G(H)$ allows the weaker condition of centralizing $H$ as a set (potentially permuting elements within $H$).

This is maybe easier to remember for Lie algebras: there
\[
C_{\lieg}(\lieh) = \ts{x\in \lieg \st [xh] = 0 \,\forall h\in \lieh }
N_{\lieg}(\lieh) = \ts{x\in \lieg \st [xh] \in \lieh \,\forall h\in \lieh }
.\]
So $[x, \wait]_{\lieh} = 0$ for central $x$ and $\im [x, \wait]_{\lieh} \subseteq \lieh$ for normal elements.
:::

:::{.definition title="Center"}
The **center** of $G$ is defined as
\[
Z(G) = \ts{ g\in G \st [g, h] = e \, \forall h\in H}
= \ts{ g\in G \st Z(g) = G } 
,\]
the subgroup of *central* elements:
those $g\in G$ that commute with every element of $G$.
:::

:::{.exercise title="?"}
\envlist

- Show that if $G/Z(G)$ is cyclic then $G$ is abelian.
- Show that $G/N$ is abelian iff $[G, G] \leq N$.
- Show that normal subgroups are not necessarily contained in $Z(G)$.
  - Hint: consider the order 3 subgroup of $S_3$.
:::


:::{.solution}
The $G/Z(G)$ theorem:

- Write $H\da Z(G)$ and $G/H = \gens{xH}$ as a cyclic quotient.
- Fix $a, b\in G$, then $aH = x^n H$ and $bH = x^m H$.
- So $ax^{-n} = h_1, bx^{-m} = h_2$ where the $h_i$ are now central.
- Now write $ab = (x^n h_1)(x^m h_2) = ba$ by commuting everything.
:::


## Cosets

:::{.proposition title="Tower law for subgroups"}
\[
K\leq H \leq G \implies [G: K] = [G:H] [H: K]
.\]
:::

:::{.proposition title="Quotients by bigger subgroups yield smaller quotients"}
If $H\leq K \leq G$, then 
\[
\size  G = [G:1] \geq [G:H] \geq [G:K] \geq [G:G] = 1
.\]
In particular, If $H, K\leq G$ are just arbitrary, since $H \intersect K \leq H, K$ we have $[H: H \intersect K] \geq [G:H] \text{ and } [G:K]$.
:::

:::{.proof title="?"}
Write $G/H \intersect K \da G/J = \ts{ h_1J, \cdots, h_m J  }$ as distinct cosets where $m\da [G:H]$ and the $h_i$ are all in $H$.
Then $i\neq j\implies h_i h_j\inv \not \in H \intersect K$, but $h_i h_j\inv \in H$ since subgroups are closed under products and inverses, which forces $h_i h_j\inv \not\in K$.
So $h_i K \neq h_j K$, meaning there are at least $m$ cosets in $G/K$, so $[G:K] \geq m$.
:::

:::{.proposition title="Cosets are equal or disjoint"}
Any two cosets $xH, yH$ are either equal or disjoint.
:::

:::{.proof title="?"}
\envlist

- $x\in xH$, since $e\in H$ because $H$ is a subgroup and we can take $h=e$ to get $x = xe \da xh \in xH$.
- The reverse containment is clear, so $G = \Union_{x\in G} xH$ is a union of its cosets.
- Suppose toward a contradiction that $\ell \in xH \intersect yH$ we'll show $xH = yH$.
- Write $\ell =xh_1 =yh_2$ for some $h_i$, then
\[
xh_1 = yh_2 &\implies x = yh_2 h_1\inv \\
xh_3\in xH &\implies xh_3 = (yh_2h_1\inv) h_3 \in yH
,\]
  so $xH \subseteq yH$.

- A symmetric argument shows $y_H \subseteq xH$.[^df_p80_identical_disjoint]

[^df_p80_identical_disjoint]: 
See full argument: D&F p.80.

:::

:::{.theorem title="The Fundamental Theorem of Cosets"}
\[
aH = bH \iff a\inv b \in H \iff b\inv a\in H
.\]
:::

:::{.proof title="?"}
[^df_p80_identical_disjoint]
\[
aH = bH \iff a\in bH \iff a=bh \text{ for some } h \iff b\inv a = h \iff ba\inv \in H
.\]
:::

:::{.definition title="Index of a subgroup"}
The **index** $[G: H]$ of a subgroup $H\leq G$ is the number of left (or right) cosets $gH$.
:::

:::{.remark title="Common coset trick"}
If you can reduce a problem to showing $X \subseteq H$, it suffices to show $xH = H$ for all $x\in X$.
:::

:::{.remark}
Cosets form an equivalence relation and thus partition a group.
Nice trick: write $G/H = \ts{ g_1 H, g_2 H,\cdots, g_n H }$, then $G = \disjoint_{i\leq n} g_i H$.
:::

:::{.theorem title="Counting Cosets"}
If $H\normal G$ and $G$ is finite then
\[
[G: H] = \abs{G/H} = {\abs G \over \abs H}
.\]
:::

:::{.exercise title="?"}
Show that if $G$ is finite then $\abs{G}/\abs{H} = [G: H]$.
:::

## Special Groups

:::{.definition title="The Dihedral Group"}
A **dihedral group** of order $2n$ is given by 
\[
D_n = \gens{r, s \suchthat r^n, s^2, rsr\inv = s\inv } = \gens{r, s \st r^n, s^2, (rs)^2 }
\]
The $r$ is a cycle of length $n$, and $s$ is a reflection.

Examples of explicit cycle presentations:

- $D_4 = \gens{(1,2,3,4), (1,3)}$ which is a $2\pi/4$ rotation and a reflection through the diagonal line $y=-x$ in a square.
- $D_5 = \gens{(1,2,3,4,5), (1,5)(2,4)}$ which is a $2\pi/5$ rotation and a reflection about the line through vertex $3$ in a pentagon.
:::

:::{.definition title="The Quaternion Group"}
The **Quaternion group** of order 8 is given by
\[
Q &= \gens{x,y,z \suchthat x^2 = y^2 = z^2 = xyz = -1} \\
  &= \gens{x, y \suchthat  x^4 = y^4, x^2 = y^2, yxy\inv = x\inv}
\]
Mnemonic: multiply clockwise to preserve sign, counter-clockwise to negate sign.
Everything squares to $-1$, and the triple product is $-1$:

\begin{tikzcd}
	&& {-1} \\
	\\
	&& i \\
	\\
	\\
	k &&& {} & j
	\arrow["{ki=j}"', from=3-3, to=6-5]
	\arrow["{ij=k}"', from=6-5, to=6-1]
	\arrow["{jk=i}"', from=6-1, to=3-3]
	\arrow["{ik=-j}"', curve={height=30pt}, dashed, from=6-1, to=6-5]
	\arrow["{kj=-i}"', curve={height=30pt}, dashed, from=6-5, to=3-3]
	\arrow["{ji=-k}"', curve={height=30pt}, dashed, from=3-3, to=6-1]
	\arrow["{ijk=-1}"', from=3-3, to=1-3]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsNSxbMiwyLCJpIl0sWzMsNV0sWzAsNSwiayJdLFs0LDUsImoiXSxbMiwwLCItMSJdLFswLDMsImtpPWoiLDJdLFszLDIsImlqPWsiLDJdLFsyLDAsImprPWkiLDJdLFsyLDMsImlrPS1qIiwyLHsiY3VydmUiOjUsInN0eWxlIjp7ImJvZHkiOnsibmFtZSI6ImRhc2hlZCJ9fX1dLFszLDAsImtqPS1pIiwyLHsiY3VydmUiOjUsInN0eWxlIjp7ImJvZHkiOnsibmFtZSI6ImRhc2hlZCJ9fX1dLFswLDIsImppPS1rIiwyLHsiY3VydmUiOjUsInN0eWxlIjp7ImJvZHkiOnsibmFtZSI6ImRhc2hlZCJ9fX1dLFswLDQsImlqaz0tMSIsMl1d)

:::

:::{.definition title="Transitive Subgroup"}
A subgroup $H\leq S_n$ is **transitive** iff its action on $\theset{1, 2, \cdots, n}$ is transitive, i.e. for each pair $(i, j)$ there is some element $\sigma\in H$ such that $\sigma(i) = j$.
Note that $\sigma$ may not fix other elements, and can have other effects!
:::

:::{.definition title="p-groups"}
If $\abs{G} = p^k$, then $G$ is a **p-group.**
:::

### Cyclic Groups

:::{.theorem title="Subgroups of Cyclic Groups"}
$G$ is cyclic of order $n \da \size  G$ iff $G$ has a unique subgroup of order $d$ for each $d$ dividing $n$.
:::

:::{.proof title="?"}
$\impliedby$:
Use that $\sum_{d\divides n} \phi(d) = n$, and that there are at most $\phi(d)$ elements of order $d$, forcing equality.

$\implies$:
If $G = \gens{ a }$ with $a^n=e$, then for each $d\divides n$ take $H_d \da \gens{ a^{n\over d} }$ for existence.
:::

:::{.exercise title="?"}
\envlist

- Show that any cyclic group is abelian.
- Show that every subgroup of a cyclic group is cyclic.
- Show that $$\phi(n) = n \prod_{p\mid n}\qty{1 - {1\over p}}.$$
- Compute $\aut(\ZZ/n\ZZ)$ for $n$ composite.
- Compute $\aut(\qty{\ZZ/p\ZZ}^n)$.
:::

### Symmetric Groups

:::{.definition title="The symmetric group"}
The transposition presentation:
\[
S_n \da \gens{ \sigma_1, \cdots, \sigma_{n-1} \st \sigma_i^2, [\sigma_i, \sigma_j]\, (j\neq i+1), \sigma_i \sigma_{i+1} \sigma_i = \sigma_{i+1} \sigma_i \sigma_{i+1} } 
.\]

:::

:::{.definition title="The sign homomorphism"}
Writing a cycle as a product of transpositions,
the map defined by
\[
\sgn: S_n &\to (\ZZ/2, +) \\
\prod_{i\leq 2k} (a_i b_i) &\mapsto 0 \\
\prod_{i\leq 2k+1} (a_i b_i) &\mapsto 1
.\]
:::

:::{.remark}
\envlist

- The kernel is the alternating group:
  - **Even** cycles
  - For a single cycle: has **odd** length
  - Have an **even** number of even length cycles.
  - Can be written as an **even** number of transpositions.
  - Examples: $(1,2,3)$ or $(1,2)(3,4)$ in $S_4$.
  - Non-examples: $(1,2)$ or $(1,2,3,4)$ in $S_4$, since they have an odd number of even length cycles.
- The fiber over 1 is everything else:
  - **Odd** cycles
  - For a single cycle: has **even** length
  - Have an **odd** number of even length cycles.
  - Can be written as an **odd** number of transpositions

> Mnemonic: the cycle parity of a $k\dash$cycle is the usual integer parity of $k-1$.

:::

:::{.definition title="Alternating Group"}
The **alternating group** is the subgroup of **even** permutations, i.e.
\[
A_n \definedas \theset{\sigma \in S_n \suchthat \sgn(\sigma) = 0}
.\] 
These are the permutations with an even number of even length cycles.
:::

:::{.proposition title="$A_n$ is generated by 3-cycles"}
For $n\geq 3$, $A_n$ is generated by 3-cycles.
:::

:::{.proof title="?"}
Every 3-cycle $(abc)$ is even, and thus in $A_n$.
Given an arbitrary even permutation $(t_1\ldots t_{2k})$, it decomposes into a product of an odd number of transpositions $(t_{2j-1} t_{2j})$.
So it suffices to write every such transposition as a 3-cycle.
There are only 3 cases the occur:

- $(ab)(ab) = ()$
- $(ab)(ac) = (abc)$
- $(ab)(cd) = (abc)(adc)$.

:::

:::{.example title="Explicit alternating group"}
\[
A_3 =
\ts{ \id, (1,2,3), (1,3,2) } 
,\]
which has cycle types $(1,1,1)$ and $(3)$.

\[
A_4 =
& \{\id, \\
& (1,3)(2,4),
(1,2)(3,4),
(1,4)(2,3), \\
& (1,2,3),
(1,3,2), \\
& (1,2,4),
(1,4,2), \\
& (1,3,4),
(1,4,3), \\
& (2,3,4),
(2,4,3) \}
,\]
which has cycle types $(1,1,1,1), (2,2), (3, 1)$.

$A_5$ is too big to write down, but has cycle types

- $(1,1,1,1,1)$
- $(2,2,1)$
- $(3,1,1)$
- $(5)$
:::

:::{.fact title="Some useful facts"}
\envlist

- $\sigma \circ (a_1 \cdots a_k)\circ \sigma^{-1} = (\sigma(a_1), \cdots \sigma(a_k))$
- Conjugacy classes are determined by cycle type
- The order of a cycle is its length.
- The order of an element is the least common multiple of the sizes of its disjoint cycles.
- Disjoint cycles commute.
- $A_{n\geq 5}$ is *simple*.

:::

## Exercises

:::{.exercise title="?"}
\envlist

- Show that if $G$ is a finite group acting transitively on a set $X$ with at least two elements,
then there exists $g \in G$ which fixes no point of $X$.
- Let $p$ be prime.
  For each abelian group $K$ of order $p^2$, how many subgroups $H\leq \ZZ^{\times 3}$ are there with $\ZZ^3/H \cong K$?
- Let $\size  G = pq$, with $p,q$ distinct primes.
  Show that $G$ has a nontrivial proper normal subgroup, and if $p\not\equiv 1\mod q$ and $q\not \equiv 1 \mod p$ then $G$ is abelian.

- Let $G$ be a finite group and let $p$ be the smallest prime dividing $\size  G$, and assume $G$ has a normal subgroup of order $p$.
  Show that $H \subset Z(G)$.

- Let $G$ be finite and $P$ a Sylow 2-subgroup.
  Assume $P$ is cyclic and generated by $x$.
  Show that the sign of the permutation of $G$ corresponding to $x\mapsto gx$ is 1, and deduce that $G$ has a nontrivial quotient of order 2.

:::
