# Problem Sets


## Problem Set 1

:::{.remark}
All problems are sourced from Hartshorne.
:::

## Chapter 2, Section 1


:::{.remark}
List of useful facts used:

- Morphisms of sheaves commute with restrictions: if $\phi: \mcf\to \mcg$ then for any $s\in \mcf(U)$ and $V \subseteq U$, $\Res(U, V)(\phi(s)) = \phi(\Res(U, V)(s))$.
- $\phi$ is an isomorphism iff $\phi_p$ are all isomorphisms.
- Elements of stalks $\mcf_p:$ equivalence classes $[U, s\in \mcf(U)]$.
- The induced map on stalks: $\phi_p([U, s]) \da [U, \phi(U)(s)]$.
- A surjection of sheaves need not induce a surjection on sections.
- The colimit diagram:


\begin{tikzcd}
	& \bullet \\
	\vdots && \vdots \\
	{U_1} && {F(U_1)} \\
	&&&& {\forall O} && {\colim_{i} F(U_i)} \\
	{U_2} && {F(U_2)} \\
	\vdots && \vdots \\
	& \bullet
	\arrow["f", from=5-1, to=3-1]
	\arrow["{F(f)}"', from=3-3, to=5-3]
	\arrow["{\psi_2}"', from=5-3, to=4-7]
	\arrow["{\psi_1}", from=3-3, to=4-7]
	\arrow["{\psi'_1}"', from=3-3, to=4-5]
	\arrow["{\psi'_2}", from=5-3, to=4-5]
	\arrow["{\exists !}", dashed, from=4-5, to=4-7]
	\arrow[dotted, no head, from=1-2, to=7-2]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsMTIsWzAsMiwiVV8xIl0sWzAsNCwiVV8yIl0sWzIsMiwiRihVXzEpIl0sWzIsNCwiRihVXzIpIl0sWzAsMSwiXFx2ZG90cyJdLFswLDUsIlxcdmRvdHMiXSxbMiw1LCJcXHZkb3RzIl0sWzIsMSwiXFx2ZG90cyJdLFs2LDMsIlxcY29saW1fe2l9IEYoVV9pKSJdLFs0LDMsIlxcZm9yYWxsIE8iXSxbMSwwLCJcXGJ1bGxldCJdLFsxLDYsIlxcYnVsbGV0Il0sWzEsMCwiZiJdLFsyLDMsIkYoZikiLDJdLFszLDgsIlxccHNpXzIiLDJdLFsyLDgsIlxccHNpXzEiXSxbMiw5LCJcXHBzaSdfMSIsMl0sWzMsOSwiXFxwc2knXzIiXSxbOSw4LCJcXGV4aXN0cyAhIiwwLHsic3R5bGUiOnsiYm9keSI6eyJuYW1lIjoiZGFzaGVkIn19fV0sWzEwLDExLCIiLDIseyJzdHlsZSI6eyJib2R5Ijp7Im5hbWUiOiJkb3R0ZWQifSwiaGVhZCI6eyJuYW1lIjoibm9uZSJ9fX1dXQ==)

- Colimits are initial co-cones, where $I$ is initial if $I\to X$ for any $X$.
  AKA direct limits.

- Filtered colimits commute with finite limits.
  - In particular, monomorphisms are pullbacks, so finite limits, and stalks are filtered colimits.
    So injections of sheaves induce injections on stalks.
:::


:::{.remark}
Recommended problems:

- 1.1
- 1.2
- 1.3
- 1.4
- 1.5

:::

:::{.problem title="1.1"}
Let $A$ be an abelian group, and define the *constant presheaf* associated to $A$ on the topological space $X$ to be the presheaf $U \mapsto A$ for all $U \neq \emptyset$, with restriction maps the identity. 

Show that the constant sheaf $\mca$ defined in Hartshorne is the sheafification of this presheaf.
:::

:::{.solution}
Let $X\in \Top$ be a space.
Recapping the definitions, define the constant presheaf as
\[
\ul{A}^\pre(U) \da 
\begin{cases}
A & U\neq \emptyset 
\\
0 & \text{else}.
\end{cases}
\quad \res^1(U, V) \da 
\begin{cases}
\id_A  & U\neq \emptyset 
\\
0 & \text{else}.
\end{cases}
.\]

Then define the constant *sheaf* as
\[
\ul{A}(U) \da \Hom_{\Top}(U, A)\quad \res^2(U, V)(f) \da \ro{f}{V}
.\]

We're then tasked with finding a morphism of sheaves 
\[
\Psi: (\ul{A}^\pre)^+ \mapsvia{\sim} \Hom_{\Top}(\wait, A)
,\]
which we'll also want to have an inverse morphism and this define an isomorphism in $\Sh(X)$.

We'll use the implicitly stated fact in Hartshorne that $\Hom_{\Top}(U, A) = A^{\oplus n}$ where $n \da \# \pi_0(X)$ is the number of connected components of $U$.
Suppose first that $n=1$, so $X$ is connected, and define the following morphism of groups:
\[
\Psi_U: (\ul{A}^\pre)(U) = A &\too \Hom_\Top(U, A)\\
a_0 &\mapsto \left\{ { \begin{aligned} \varphi_{a_0}: U \to A \\ x \mapsto a_0, \end{aligned} } \right.
\]
which maps a group element $a_0$ to the constant function on $U$ sending every point to $a_0 \in A$.
The claim is that the following diagram commutes in the category $\Presh(X)$ (in both directions) for all $U$ and $V$:

\begin{tikzcd}
	&& {f(U)} && f \\
	&& {a_0} && { \begin{aligned} \varphi_{a_0}: U &\to A \\ x &\mapsto a_0 \end{aligned} } \\
	U && {(\ul{A}^\pre)(U) = A} && {\Hom_\Top(U, A)} \\
	\\
	V && {(\ul{A}^\pre)(V) = A} && {\Hom_\Top(V, A)} \\
	&& {a_0} && { \begin{aligned} \varphi_{a_0}: V &\to A \\ x &\mapsto a_0 \end{aligned} } \\
	&& {f(V)} && f
	\arrow[hook, from=5-1, to=3-1]
	\arrow["{\Psi_U}", from=3-3, to=3-5]
	\arrow["{\Psi_V}", from=5-3, to=5-5]
	\arrow["{\res^1(U, V)}"', from=3-3, to=5-3]
	\arrow["{\res^2(U, V)}", from=3-5, to=5-5]
	\arrow[maps to, from=2-3, to=2-5]
	\arrow[maps to, from=1-5, to=1-3]
	\arrow[maps to, from=7-5, to=7-3]
	\arrow[maps to, from=6-3, to=6-5]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsMTQsWzAsMiwiVSJdLFswLDQsIlYiXSxbMiwyLCIoXFx1bHtBfV5cXHByZSleKyhVKSJdLFsyLDQsIihcXHVse0F9XlxccHJlKV4rKFYpIl0sWzQsMiwiXFxIb21fXFxUb3AoVSwgQSkiXSxbNCw0LCJcXEhvbV9cXFRvcChVLCBBKSJdLFsyLDEsImFfMCJdLFs0LDEsIlxcdmFycGhpX3thXzB9OiBVXFx0byBBIFxcXFx4XFxtYXBzdG8gYV8wIl0sWzQsMCwiZiJdLFsyLDAsImYoVSkiXSxbMiw1LCJhXzAiXSxbNCw1LCJcXHZhcnBoaV97YV8wfTogVlxcdG8gQSBcXFxceFxcbWFwc3RvIGFfMCJdLFs0LDYsImYiXSxbMiw2LCJmKFYpIl0sWzEsMCwiIiwwLHsic3R5bGUiOnsidGFpbCI6eyJuYW1lIjoiaG9vayIsInNpZGUiOiJ0b3AifX19XSxbMiw0LCJcXHBzaV9VIl0sWzMsNSwiXFxwc2lfViJdLFsyLDMsIlxccmVzXjEoVSwgVikiLDJdLFs0LDUsIlxccmVzXjIoVSwgVikiXSxbNiw3LCIiLDAseyJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJtYXBzIHRvIn19fV0sWzgsOSwiIiwwLHsic3R5bGUiOnsidGFpbCI6eyJuYW1lIjoibWFwcyB0byJ9fX1dLFsxMiwxMywiIiwwLHsic3R5bGUiOnsidGFpbCI6eyJuYW1lIjoibWFwcyB0byJ9fX1dLFsxMCwxMSwiIiwwLHsic3R5bGUiOnsidGFpbCI6eyJuYW1lIjoibWFwcyB0byJ9fX1dXQ==)

Here we've specified simultaneously what $\Psi$ and $\Psi\inv$ prescribe on opens $U, V$, and abuse notation slightly by writing $\Hom_{\Top}(\wait, A)$ for the sheaf it represents and its underlying presheaf.

- That this commutes follows readily, since running the diagram counterclockwise yields $\res^1(U, V) = \id_A$, so the composition \[
(A \mapsvia{\res^1(U, V)} A \mapsvia{\Psi_V} \Hom(V, A)) = (A \mapsvia{\Psi_V} \Hom(V, A))
\]
  sends an element $a_0\in A$ to the constant function $\varphi_{a_0, V}: V\to A$.
  Running the diagram clockwise yields 
\[
(A \mapsvia{\Psi_U} \Hom(U, A) \mapsvia{\res^2(U, V)} \Hom(V, A))
,\]
  which sends $a_0$ to the constant function $\varphi_{a_0, U}: U\to A$ sending everything to $a_0$, which then gets sent to $\ro{\varphi_{a_0, U}}{V}: V\to A$ sending everything to $a$.
  Since $\ro{\varphi_{a_0}}{V}(x) = \varphi_{a_0, V}(x) = a$ for every $x\in U$, these functions are equal.

- That the reverse maps $\Psi_U\inv$ are well-defined follows from the fact that $U$ is connected: the continuous image of a connected set is connected. Since $A$ is given the discrete topology, any subset with 2 or more elements in disconnected, so each function $f\in \Hom(U, A)$ is necessarily a constant function and $f(U) = \ts{a}$ is a singleton.

- $\Psi_U, \Psi_U\inv$ clearly compose to the identity in either order, so $\Psi_U$ defines an isomorphism of abelian groups.

As a consequence, we get a well-defined morphism of presheaves $\ul{A}^\pre(\wait) \to \ro{ \Hom(\wait, A)}{\Presh}$, and by the sheafification adjunction we can lift this to a morphism of sheaves:
\[
\adjunction{\mcf \mapsto \mcf^+ }{\mcg \mapsto \ro{\mcf}{\Presh} }{\Presh(X)}{\Sh(X)}
,\]
which reads
\[
\Hom_{\Presh}(\mcf, \ro{\mcg}{\Presh}) &\mapsvia{\sim} \Hom_{\Sh}(\mcf^+, \mcg) \\
\Psi &\mapsto \tilde \Psi
,\]
and since $\Psi$ was an isomorphism, so is $\tilde \Psi$.


> It remains to handle the $n\geq 2$, case when (say) $U = U_1 \disjoint U_2$ has more than 1 connected component.
> Actually, is it even true that adjunctions preserve isomorphisms...?
> Todo: help??

-------

Alternatively, consider the map $\Psi$ defined on presheaves -- by the universal property, we get some sheaf morphism $\tilde\Psi$, which we can show is an isomorphism by showing its induced map on stalks is an isomorphism.
This amounts to showing the following map is a group isomorphism:
\[
\Psi_p: (\ul{A}^\pre(\wait))_p \mapsvia{\sim} \Hom_\Top(\wait, A)_p
.\]

First we identify the LHS:
\[
(\ul{A}^\pre(\wait))_p \da \colim_{U\ni p} \ul{A}^\pre(U) = \colim_{U\ni p} A = A
.\]

(todo: show $A$ satisfies the universal property for a colimit)

Identifying the RHS, we have equivalence classes $[U\ni p, s: U\to A]$

- Injectivity: that $\Psi_p$ is injective follows from the fact that $\ker \psi_p \da \ts{a\in A \st \Psi_p(a) = e}$, where $e$ is the identity in the right-hand side stalk, which is represented by the class $[U, f_e:U\to A]$ where $f_e(x) \da e_A$, the identity of $A$, for every $x\in U$.

- Surjectivity: that $\Psi_p$ is surjective follows from the fact that every fixed $f: U\to A$ for $A$ discrete is constant on connected components.
Use that $p$ is contained in a connected component $U_1 \ni p$, then $[U, f] \sim [U_1, \ro{f}{U_1}] \da [U_1, g]$ to get that $g$ is now a constant function of $U_1$.
So $g(x) = a$ for some $a\in A$, so $g = \Psi_p(a)$ is in the image.


--- 

Alternatively:

- Show that $\ul{A}$ satisfies the universal property of $(\ul{A}^\pre)^+$: we need to produce a morphism $\theta: (\ul{A}^\pre) \to \ul{A}$ such that for any $\mcg\in \Sh(X)$ and morphism of presheaves $\varphi: \ul{A}^\pre \to \ro{\mcg}{\pre}$ we can produce a unique morphism $\tilde \varphi$ of sheaves making the following diagram commute:

\begin{tikzcd}
	{\ul{A}^{\pre}} && {\ro{\mcg}{\pre}} && {\in \Presh(X)} \\
	\\
	{\ul{A}} && \mcg && {\in\Sh(X)}
	\arrow["\varphi", from=1-1, to=1-3]
	\arrow["\theta"', from=1-1, to=3-1]
	\arrow["{\ro{\wait}{\pre}}"', from=3-3, to=1-3]
	\arrow["{\exists! \tilde \varphi}"', dashed, from=3-1, to=3-3]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsNixbMCwyLCJcXHVse0F9Il0sWzAsMCwiXFx1bHtBfV57XFxwcmV9Il0sWzIsMCwiXFxyb3tcXG1jZ317XFxwcmV9Il0sWzIsMiwiXFxtY2ciXSxbNCwwLCJcXGluIFxcUHJlc2goWCkiXSxbNCwyLCJcXGluXFxTaChYKSJdLFsxLDIsIlxcdGhldGEiXSxbMSwwLCJcXHRoZXRhIiwyXSxbMywyLCJcXHJve1xcd2FpdH17XFxwcmV9IiwyXSxbMCwzLCJcXGV4aXN0cyEgXFx0aWxkZSBcXHRoZXRhIiwyLHsic3R5bGUiOnsiYm9keSI6eyJuYW1lIjoiZGFzaGVkIn19fV1d)

- To define $\tilde \varphi$, it suffices to define morphisms of the form 
\[
\tilde\varphi(U): \ul{A}(U) &\to\mcg(U) \\
f & \mapsto \tilde\varphi(U)(f)
\]
- Take a map $f\in \ul{A}(U) \da \Hom_\Top(U, A)$.
  Write $U \da \disjoint U_i$ as a union of connected components.
  Use that $f$ is constant on connected components since $A$ is discrete, so $f(U_i) = a_i$ for some elements $a_i \in A \in \Ab\Grp$.


- Plug the $U_i$ into $\ul{A}^\pre$ to get morphisms
\[
\varphi(U_i): \ul{A}^\pre(U_i)= A \to \ro{\mcg}{\pre}(U_i) && \in \Ab\Grp
\]

- Write $b_i \da \varphi(U_i)(a_i) \in \ro{\mcg}{\pre}(U_i) = \mcg(U_i)$.

\begin{tikzcd}
	{a_i} &&& {b_i \da \varphi(U_i)(a_i)} \\
	& {\ul{A}^{\pre}(U_i) = A} && {\ro{\mcg}{\pre}(U_i)} && {\in \Presh(X)} \\
	\\
	& {\Hom(U_i, A)} && {\mcg(U_i)} && {\in\Sh(X)} \\
	& f && {b_i} && {}
	\arrow["{\varphi(U_i)}", from=2-2, to=2-4]
	\arrow["\theta"', from=2-2, to=4-2]
	\arrow["{\ro{\wait}{\pre}}"', from=4-4, to=2-4]
	\arrow["{\exists! \tilde \varphi}"', dashed, from=4-2, to=4-4]
	\arrow[curve={height=-24pt}, dashed, maps to, from=5-2, to=1-1]
	\arrow[dashed, maps to, from=1-1, to=1-4]
	\arrow[maps to, from=5-2, to=5-4]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsMTEsWzEsMywiXFxIb20oVV9pLCBBKSJdLFsxLDEsIlxcdWx7QX1ee1xccHJlfShVX2kpID0gQSJdLFszLDEsIlxccm97XFxtY2d9e1xccHJlfShVX2kpIl0sWzMsMywiXFxtY2coVV9pKSJdLFs1LDEsIlxcaW4gXFxQcmVzaChYKSJdLFs1LDMsIlxcaW5cXFNoKFgpIl0sWzUsNF0sWzEsNCwiZiJdLFswLDAsImFfaSJdLFszLDAsImJfaSBcXGRhIFxcdmFycGhpKFVfaSkoYV9pKSJdLFszLDQsImJfaSJdLFsxLDIsIlxcdmFycGhpKFVfaSkiXSxbMSwwLCJcXHRoZXRhIiwyXSxbMywyLCJcXHJve1xcd2FpdH17XFxwcmV9IiwyXSxbMCwzLCJcXGV4aXN0cyEgXFx0aWxkZSBcXHZhcnBoaSIsMix7InN0eWxlIjp7ImJvZHkiOnsibmFtZSI6ImRhc2hlZCJ9fX1dLFs3LDgsIiIsMCx7ImN1cnZlIjotNCwic3R5bGUiOnsidGFpbCI6eyJuYW1lIjoibWFwcyB0byJ9LCJib2R5Ijp7Im5hbWUiOiJkYXNoZWQifX19XSxbOCw5LCIiLDAseyJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJtYXBzIHRvIn0sImJvZHkiOnsibmFtZSI6ImRhc2hlZCJ9fX1dLFs3LDEwLCIiLDIseyJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJtYXBzIHRvIn19fV1d)

- Since $\mcg$ is in fact a sheaf, by unique gluing there exists a unique element $b \in \mcg(U)$ such that $\ro{b}{U_i} = b_i$.
  So define $\tilde\varphi(U)(f) \da b$.

- Now define the map $\theta: \ul{A}^\pre(U_i) \to \Hom(U_i, A)$ sending $a_i$ to the constant function $f_{i}(x)\da a_i$.
  Since $\ul{A}$ is a sheaf, there is a well defined $F\in \Hom(U, A)$ such that $\ro{F}{U_i} = f_i$.
  So for $a\in \ul{A}^\pre(U)$ set $\theta(a) = F \in \ul{A}(U)$.

- This makes the relevant diagram commute: if $a\in A = \ul{A}^\pre(U)$, then $b\da \phi(U)(a) \in \mcg(U)$.
  On the other hand, $\theta(a)$ is the constant function $f_a: x\mapsto a$ (on every connected component of $U$), and setting $F \da \tilde\phi(f_a)\in \mcg(U)$, we have $F \da b$.

:::

:::{.problem title="1.2"}
(a) For any morphism of sheaves $\varphi: \mcf \rightarrow \mcg$, show that for each point $p$ that $\ker (\varphi)_{p}=$ $\operatorname{ker}\left(\varphi_{p}\right)$ and $\im(\varphi)_{p} = \im\left(\varphi_{p}\right)$.

(b) Show that $\varphi$ is injective (resp. surjective) if and only if the induced map on the stalks $\varphi_{p}$ is injective (resp. surjective) for all $p$.

(c) Show that a sequence of sheaves and morphisms 
\[
\cdots \mcf^{i-1} \mapsvia{\varphi^{i-1}} \mcf^i \mapsvia{\varphi^{i}} \mcf^{i+1} \to \cdots
\]
is exact if and only if for each $P \in X$ the corresponding sequence of stalks is exact as a sequence of abelian groups.
:::

:::{.proof title="of 1, kernels"}
\envlist

- Write $K\in \Sh(X)$ for the kernel sheaf $U \mapsto \ker \qty{ \mcf(U) \mapsvia{\phi(U)} \mcg(U) }$, 
- We then want to show $K_p = \ker\qty{\mcf_p \mapsvia{\phi_p} \mcg_p}$, an equality of sets in $\Ab\Grp$.
  So we just do it!
  - Addendum: this works because both are subsets of the same abelian group, $\mcf_p$.
- We can write
\[
\phi_p: \mcf_p &\to \mcg_p \\
[U, s] &\mapsto [U, \phi(U)(s)]
,\]
and note that the zero element in a stalk is the equivalence class $[U, 0]$ where $0\in \Ab\Grp$ is the zero object.
Thus
\[
\ker \phi_p 
&\da \ts{ x\in \mcf_p \st \phi_p(x) = 0 \in \mcg_p } \\
& = \ts{ [U, s] \in \mcf_p \st [U, \phi(U)(s)] = [U, 0] } \\
& = \ts{ [U, s] \in \mcf_p \st \phi(U)(s) = 0 } \\
& = \ts{ [U, s] \in \mcf_p \st s \in \ker \phi(U) } \\
&= \ts{ [U, s] \st s\in \ker{\qty{\mcf(U) \mapsvia{\phi(U)} \mcg(U) } } } \\
&\da \ts{[U, s] \st s\in K(U)} \\
&\da K_p 
.\]


:::

:::{.proof title="of 1, images"}
\envlist

- Write $\mci$ for the sheaf $\im \phi$ which sends $U\mapsto \im\qty{\mcf(U) \mapsvia{\phi(U)} \mcg(U)}$.
- We want to show $\mci_p = \im\qty{\mcf_p \mapsvia{\phi_p} \mcg_p}$, where both are subsets of $\mcg_p$.
- So we show set equality:
\[
\im (\phi_p)
&= \ts{ y\in \mcg_p \st \exists x\in \mcf_p,\, \phi_p(x) = y } \\
&= \ts{ [U, t] \in \mcg_p \st \exists [U, s] \in \mcf_p,\, \phi_p([U, s]) = [U, t] } \\
&= \ts{ [U, t] \in \mcg_p \st \exists s\in \mcf(U),\, \phi(U)(s) = t } \\
&= \ts{ [U, t] \in \mcg_p \st t\in \im\qty{\mcf(U) \mapsvia{\phi(U)}  \mcg(U) }} \\
&\da \ts{ [U, t] \in \mcg_p \st t \in \mci(U) } \\
&\da \mci_p
.\]

:::

:::{.proof title="of 2, injectivity"}
$\implies$:

- Use that injectivity of a morphism $\phi$ of sheaves is *defined* to hold exactly when $\ker \phi = 0$ is the constant zero sheaf.
- Now use (1):
\[
0 = \ker(\phi) \implies 0 = \ker(\phi)_p = \ker(\phi_p) && \forall p
.\]


- If $\ker \phi = 0$, so $\phi$ is injective, then $\ker \phi_p = 0$ for all $p$, so $\ker \phi_p$ is injective.

$\impliedby$:

- Conversely, suppose $\ker \phi_p = 0$ for all $p$; we want to show $\ker \phi(U) = 0$ for all $U$.
- So fix $U\ni p$, we want to show
\[
s\in K(U) \da \ker\qty{\mcf(U) \mapsvia{\phi(U)} \mcg(U)}
\implies s = 0 \in \mcf(U)
.\]
- We have $\phi(U)(s) = 0$, so 
\[
\phi_p([U, s]) \da [U, \phi(U)(s)] = [U, 0] \in \mcg_p \implies [U, s] \in \ker (\phi_p)
.\]
- By injectivity of $\phi_p$, we have $[U, s] = 0 \in \mcf_p$.
- So there is some open $U_p$ with $U \contains U_p \ni p$ and $\Res(U, U_p)(s) = 0$ in $\mcf(U_p)$.
- Then $\ts{U_p }_{p\in U} \covers U$, and since $\mcf$ is a sheaf, by existence of gluing these glue to an $F \in \mcf(U)$ with $\Res(U, U_p)(F) = 0$ for each $p$.
  By uniqueness of gluing, $0 = F = s$. 

:::

:::{.proof title="of 2, surjectivity"}
$\implies$:

- Suppose $\phi$ is surjective, then by definition $\im \phi = \mcg$ is an equality of sheaves.
- So $(\im \phi)(U) = \mcg(U)$ for all $U$.
- Let $[U, t]\in \mcg_p$, so $t\in \mcg(U)$.
- Then $t\in (\im \phi)(U)$, so there exists an $s\in \mcf(U)$ such that $\phi(U)(s) = t$.
- Then $[U, s] \mapsto [U, \phi(U)(s)] = [U, t]$, under $\phi_p$, making $\phi_p$ surjective.

$\impliedby$:

- Suppose $\phi_p$ is surjective for all $p$, fix $U$, and let $t \in \mcg(U)$.
  We want to produce an $s\in \mcf(U)$ such that $\phi(U)(s) = t$.

- For $p\in U$, the image of $t$ in the stalk of $\mcg$ is of the form $[U_p, t_p] \in \mcg_p$ where $t_p \in \mcg(U_p)$.
- Since $\phi_p: \mcf_p \surjects \mcg_p$, we can find some pair $[U_p, s_p]$ mapping to $[U_p, t_p]$ under $\phi_p$, so $\phi(U_p)(s_p) = t_p$.
  - Note that $\Res(U, U_p)(t) = t_p$.
  - Note: may need to pull back to some $\tilde U_p$, then take a common refinement in both germs?
- Now $\ts{U_p}_{p\in U}\covers U$, so using existence of gluing for $\mcf$ we have some $s\in \mcf(U)$ with $\Res(U, U_p)(s) = s_p$ for all $p$.
- Claim: $\phi(U)(s) = t$.
  \[
  \Res(U, U_p)( \phi(s) ) &= \phi(\Res(U, U_p)(s)) \\ &= \phi(s_p) \\ &= t_p \\ &= \Res(U, U_p)(t)
  && \forall p\in U
  ,\]
  so $\phi(s) = t$ by uniqueness of gluing of $\mcg$.
:::

:::{.proof title="of 3, exactness"}
$\implies$:
Assuming exactness of sheaves,
\[
\ker(\mcf^{i+1}) = \im(\mcf^{i}) \iff
\ker(\mcf^{i+1})_p = \im(\mcf^{i})_p && \forall p
.\]


$\impliedby$:
Assuming exactness on stalks, write
\[
\ker(\mcf^{i+1})_p 
&= \ker(\mcf^{i+1}_p) && \text{by 1 } \\
&= \im(\mcf^{i}_p) && \text{exactness, by assumption} \\
&= \im(\mcf^{i})_p && \text{by 1}
.\]

:::


:::{.problem title="1.3"}
(a) 
Let $\varphi: \mcf\to\mcg$ be a morphism of sheaves on $X$. Show that $\varphi$ is surjective if and only if the following condition holds: 

    For every open set $U \subseteq X$, and for every $s\in \mcg(U)$, there is a cover $\ts{U_i}$ of $U$ and elements $t_i \in \mcf(U_i)$ such that $\varphi(t_i) = \ro{s}{U_i}$ for all $i$.

(b) Give an example of a surjective morphism of sheaves $\varphi: \mcf \rightarrow \mcg$, and an open set $U$ such that $\varphi(U): \mcf(U) \rightarrow \mcg(U)$ is not surjective.
:::


:::{.proof title="of 1"}

$\implies$:

- If $\phi: \mcf \surjects \mcg$, then $\phi_p: \mcf_p \surjects \mcg_p$ for all $p$, since $\im(\phi_p) = (\im \phi)_p = \mcg_p$, using problem 1.2.
- Fix $U \subseteq X$ and $s\in \mcg(U)$, we want
  - To produce a cover $\ts{U_i}\covers U$, 
  - To find $t_i\in \mcf(U_i)$, and
  - To show that $\phi(t_i) = \Res(U, U_i)(s)$ for all $i$.

- Fix $p$, and take the image of $s$ in the stalk of $\mcg$ to get $[U_p, s_p] \in \mcg_p$ with $s_p \in \mcg(U_p)$ and $\Res(U, U_p)(s) = s_p$.
  Note that $\ts{U_p}_{p\in U}\covers U$.
- By surjectivity on stalks, these pull back to $[U_p, t_p]\in \mcf_p$ with $t_p \in \mcf(U_p)$ and $\phi_p([U_p, t_p]) \da [U_p, \phi(U_p)(t_p)] = [U_p, s_p]$.
- Then $s_p \in \im(\mcf(U_p) \mapsvia{\phi(U_p)} \mcg(U_p ))$ and $\phi(t_p) = s_p = \Res(U, U_p)(s)$.

$\impliedby$:

- If $\ts{U_i}\covers U$ with $\phi(t_i) = \Res(U, U_i)(s)$ for all $i$, then the $t_i$ glue to a unique section $t\in \mcf(U)$ since $\mcf$ is a sheaf.
- Moreover $\Res(U, U_i)( \phi(t) ) = \phi(\Res(U, U_i)(t)) = \phi(t_i) = \Res(U, U_i)(s)$ for all $i$, and by unique gluing for $\mcg$ we have $\phi(t) = s$.
- So $\phi(U): \mcf(U) \to \mcg(U)$ is surjective for all $U$, making $\im(\phi(U)) = \mcg(U)$
- So $\im \phi = \mcg$ as sheaves since they make the same assignment to every open set $U$, making $\phi: \mcf\to\mcg$ surjective by definition.

:::


:::{.proof title="of 2"}
\envlist

- Take $X \da \ts{a,b,c}$ a 3-point space with the topology $\tau_X \da \ts{\emptyset, \ts{a}, \ts{b}, \ts{a,b}, X}$.
- Take $\mcf \da \ul{A}$ for some nontrivial $A\in \Ab\Grp$.
  We have the stalks
  
  - $\mcf_a = A$
  - $\mcf_b = A$
  - $\mcf_c = A$
  

- Take $\mcg \da \ul{A}(a) \times \ul{A}(b)$, the skyscraper sheaves at $a$ and $b$ respectively, where
\[
\ul{A}(x)(U) \da 
\begin{cases}
A &  x\in U
\\
0 & \text{ else} .
\end{cases}
\]
  Note that the stalks are given by $\ul{A}(x)_x = A$ and $\ul{A}(x)_y = 0$ for $y\neq x$, so

  - $\mcg_a = A\cross 0$
  - $\mcg_b = 0 \cross A$
  - $\mcg_c = 0 \cross 0$.

- Now define $\phi: \mcf \to \mcg$ by specifying $\phi(U):\mcf(U) \to \mcg(U)$ for all $U$ in the following way:

\begin{tikzcd}
	& {\Open(X)} &&&& {\ul{A}} &&&& {\ul{A}(a) \times \ul{A}(b)} \\
	& {X = \ts{a,b,c}} &&&& A &&&& {A^{\times 2}} \\
	& {\ts{a,b}} &&&& A &&&& {A^{\times 2}} \\
	{\ts{a}} && {\ts{b}} && A && A && {A\times 0} && {0\times A} \\
	& \emptyset &&&& 0 &&&& 0
	\arrow[from=5-2, to=4-1]
	\arrow[from=5-2, to=4-3]
	\arrow[from=4-1, to=3-2]
	\arrow[from=4-3, to=3-2]
	\arrow[from=3-2, to=2-2]
	\arrow[from=2-6, to=3-6]
	\arrow[from=3-6, to=4-5]
	\arrow[from=3-6, to=4-7]
	\arrow[from=4-7, to=5-6]
	\arrow[from=4-5, to=5-6]
	\arrow[from=2-10, to=3-10]
	\arrow[from=3-10, to=4-9]
	\arrow[from=3-10, to=4-11]
	\arrow[from=4-11, to=5-10]
	\arrow[from=4-9, to=5-10]
	\arrow[color={rgb,255:red,92;green,214;blue,214}, curve={height=-18pt}, dashed, from=2-6, to=2-10]
	\arrow[color={rgb,255:red,92;green,214;blue,214}, curve={height=-18pt}, dashed, from=3-6, to=3-10]
	\arrow[color={rgb,255:red,92;green,214;blue,214}, curve={height=-18pt}, dashed, from=4-5, to=4-9]
	\arrow[color={rgb,255:red,92;green,214;blue,214}, curve={height=-18pt}, dashed, from=4-7, to=4-11]
	\arrow[color={rgb,255:red,92;green,214;blue,214}, curve={height=-18pt}, dashed, from=5-6, to=5-10]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsMTgsWzEsMSwiWCA9IFxcc3R7YSxiLGN9Il0sWzEsMiwiXFx0c3thLGJ9Il0sWzAsMywiXFx0c3thfSJdLFsyLDMsIlxcdHN7Yn0iXSxbMSw0LCJcXGVtcHR5c2V0Il0sWzUsMSwiQSJdLFs1LDIsIkEiXSxbNCwzLCJBIl0sWzYsMywiQSJdLFs1LDQsIjAiXSxbOCwzLCJBXFx0aW1lcyAwIl0sWzEwLDMsIjBcXHRpbWVzIEEiXSxbOSwyLCJBXntcXHRpbWVzIDJ9Il0sWzksMSwiQV57XFx0aW1lcyAyfSJdLFs5LDQsIjAiXSxbNSwwLCJcXHVse0F9Il0sWzksMCwiXFx1bHtBfShhKSBcXHRpbWVzIFxcdWx7QX0oYikiXSxbMSwwLCJcXE9wZW4oWCkiXSxbNCwyXSxbNCwzXSxbMiwxXSxbMywxXSxbMSwwXSxbNSw2XSxbNiw3XSxbNiw4XSxbOCw5XSxbNyw5XSxbMTMsMTJdLFsxMiwxMF0sWzEyLDExXSxbMTEsMTRdLFsxMCwxNF0sWzUsMTMsIiIsMSx7ImN1cnZlIjotMywiY29sb3VyIjpbMTgwLDYwLDYwXSwic3R5bGUiOnsiYm9keSI6eyJuYW1lIjoiZGFzaGVkIn19fV0sWzYsMTIsIiIsMSx7ImN1cnZlIjotMywiY29sb3VyIjpbMTgwLDYwLDYwXSwic3R5bGUiOnsiYm9keSI6eyJuYW1lIjoiZGFzaGVkIn19fV0sWzcsMTAsIiIsMSx7ImN1cnZlIjotMywiY29sb3VyIjpbMTgwLDYwLDYwXSwic3R5bGUiOnsiYm9keSI6eyJuYW1lIjoiZGFzaGVkIn19fV0sWzgsMTEsIiIsMSx7ImN1cnZlIjotMywiY29sb3VyIjpbMTgwLDYwLDYwXSwic3R5bGUiOnsiYm9keSI6eyJuYW1lIjoiZGFzaGVkIn19fV0sWzksMTQsIiIsMSx7ImN1cnZlIjotMywiY29sb3VyIjpbMTgwLDYwLDYwXSwic3R5bGUiOnsiYm9keSI6eyJuYW1lIjoiZGFzaGVkIn19fV1d)

- Note that the induced maps on stalks are surjective, since $\phi_p: A \to A, 0$ is either the identity or the zero map.
  But e.g. for $\ts{a, b}$ we have $A\mapsto A^{\times 2}$, which can not be surjective.

  > Question: what is this map? Apparently its image is the diagonal...?

:::


:::{.problem title="1.4"}
(a) Let $\varphi: \mcf\to \mcg$ be a morphism of presheaves such that $\varphi(U): \mcf(U) \to \mcg(U)$ is injective for each $U$. 
Show that the induced map $\varphi^+: \mcf^+ \to \mcg^+$of associated sheaves is injective.

(b) Use part (a) to show that if $\varphi: \mcf\to\mcg$ is a morphism of sheaves, then $\im\varphi$ can be naturally identified with a subsheaf of $\mcg$, as mentioned in the text.
:::



:::{.proof title="of a"}
\envlist

- $\phi: \mcf \to \mcg$ is injective iff $\phi_p:\mcf_p \to \mcg_p$ is injective for all $p$.
- Sheafification induces a map $\phi^+: \mcf^+_p \to \mcg^+_p$
- The sheafification has the same stalks, so $\mcf^+_p = \mcf_p$ and $\mcg^+_p = \mcg_p$.
- So in fact $\phi^+_p = \phi_p$.
  Since $\phi^+_p$ is thus injective on all stalks, $\phi^+$ is injective on sheaves.
:::


:::{.proof title="of b"}
\envlist

- Noting that on opens $(\im \phi)(U) \subseteq \mcg(U)$ is an inclusion of abelian groups, so define a morphism of sheaves by $\iota(U): (\im \phi)(U) \to \mcg(U)$ using this inclusion.
  - By definition, it suffices to show $\ker \iota = 0$ as a sheaf.
  - By 1.2.2, it suffices to show $(\ker \iota)_p = 0$ on all stalks.
  - By 1.2.1, $(\ker \iota)_p = \ker(\iota_p)$, so it suffices to show $\iota_p$ is injective for all $p$.

- Now use that 
\[
\ker(\iota_p) = \colim_{U\ni p} (\ker \phi)(\iota(U)) = \colim_{U\ni p} 0 = 0
,\]
  since all of the $\iota(U)$ are injective, so 0 satisfies the universal property for this colimit.
  So we're done.

:::




:::{.problem title="1.5"}
Show that a morphism of sheaves is an isomorphism if and only if it is both injective and surjective.
:::


:::{.proof title="?"}
\envlist

Problem: surjections of sheaves don't induce surjections ons sections!

- $\phi:\mcf \to\mcg$ being injective means that $(\ker \phi) = 0$ as sheaves, and surjective means $(\im \phi) = \mcg$.
- Thus $\phi(U): \mcf(U) \to \mcg(U)$ is injective, since $(\ker \phi)(U) = 0(U) = 0$, and surjective since $\im (\phi(U)) = (\im \phi)(U) = \mcg(U)$.
  This $\phi(U)$ is an isomorphism in abelian groups, and has an left and right inverse $\phi\inv(U): \mcg(U) \to \mcf(U)$.

- So we have a diagram:


\begin{tikzcd}
	{\mcf(U)} && {\mcg(U)} && {\mcf(U)} \\
	\\
	{\mcf(V)} && {\mcg(V)} && {\mcf(V)}
	\arrow["{\phi(U)}", from=1-1, to=1-3]
	\arrow["{\phi(V)}", from=3-1, to=3-3]
	\arrow["{\Res_{\mcf}(U, V)}"', from=1-1, to=3-1]
	\arrow["{\Res_{\mcg}(U, V)}"{description}, from=1-3, to=3-3]
	\arrow["{\phi(U)\inv}", from=1-3, to=1-5]
	\arrow["{\phi(V)\inv}"', from=3-3, to=3-5]
	\arrow["{\Res_{\mcf}(U, V)}", from=1-5, to=3-5]
	\arrow["{\id_{\mcf(U)}}"{description}, curve={height=-30pt}, from=1-1, to=1-5]
	\arrow["{\id_{\mcf(V)}}"{description}, curve={height=30pt}, from=3-1, to=3-5]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsNixbMCwwLCJcXG1jZihVKSJdLFswLDIsIlxcbWNmKFYpIl0sWzIsMCwiXFxtY2coVSkiXSxbMiwyLCJcXG1jZyhWKSJdLFs0LDAsIlxcbWNmKFUpIl0sWzQsMiwiXFxtY2YoVikiXSxbMCwyLCJcXHBoaShVKSJdLFsxLDMsIlxccGhpKFYpIl0sWzAsMSwiXFxSZXNfe1xcbWNmfShVLCBWKSIsMl0sWzIsMywiXFxSZXNfe1xcbWNnfShVLCBWKSIsMV0sWzIsNCwiXFxwaGkoVSlcXGludiJdLFszLDUsIlxccGhpKFYpXFxpbnYiLDJdLFs0LDUsIlxcUmVzX3tcXG1jZn0oVSwgVikiXSxbMCw0LCJcXGlkX3tcXG1jZihVKX0iLDEseyJjdXJ2ZSI6LTV9XSxbMSw1LCJcXGlkX3tcXG1jZihWKX0iLDEseyJjdXJ2ZSI6NX1dXQ==)

- Both squares form a morphism of sheaves, so the right square assembles to $\phi\inv: \mcg\to\mcf$
- Moreover $(\phi\inv \circ \phi)(\mcf)(U) = \id_{\mcf(U)}$ and similarly in the other order, so $\phi\inv \circ \phi= \id_{\mcf}$
  Similarly $(\phi\circ \phi\inv)(\mcg)(U) = \id_{\mcg(U)}$ and $(\phi\inv \circ \phi) = \id_{\mcg}$.
- Then by definition an isomorphism of sheaves is a morphism with a two-sided inverse, so we're done.
:::

