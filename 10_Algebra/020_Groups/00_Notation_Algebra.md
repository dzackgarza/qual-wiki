---
order: 0
---

# Notation

## Standard Subsets

- $\mcp(X), 2^X \da \Hom_\Set(\ts{0, 1}, X)$ all define the powerset of $X$.

- Commuting: 
\[
[g, h], [gh] && \text{Commutator of elements} \\
&& \da ghg\inv \in G \\
\\
[G,H], [GH] && \text{Commutator of subgroups} \\
&& \da \gens{ \ts{ [gh] \st g \in G,\, h \in H } } \leq G 
.\]

- Central:
\[
Z(G) && \text{Center of a group} \\
&&\da \ts{ x\in G \st \forall g\in G,\, gxg ^{-1} = x } \subseteq G \\
\\
C_G(x), Z(x) && \text{Centralizer of an element} \\
&& \da \ts{g\in G \st [g, x] = 1} \subseteq G \\
\\
C_G(H), Z_G(H) && \text{Centralizer of a subgroup} \\
&& \da \ts{g\in G \st [g, x] = 1\,\, \forall h\in H} = \Intersect_{h\in H} C_H(h) \subseteq G \\
\\
[h], \Conj(h) && \text{Conjuacy class of an element} \\
&& \da \ts{ ghg ^{-1} \st g\in G} \leq G \subseteq G \\
\\
.\]

- Normal:
\[
N_G(H) && \text{Normalizer of a subgroup} \\
&& \da \ts{ g\in G \st gHg ^{-1} = H } \subseteq G 
.\]

- Automorphisms:
\[
\Inn(G) && \text{Inner automorphisms} \\
&& \da \ts{ \varphi _g(x) \da gxg ^{-1} } \subseteq \Aut(G) \\
\\
\Out(G) && \text{Outer automorphisms}\\
&& \da \Aut(G) / \Inn(G) \from \Aut(G) 
.\]




## Group Actions

\[
g\cdot x, g\actson x && \text{The action of a group on a set} \\
&& \da \phi(g)(x) \text{ where } \phi: G\to \Aut_\Set(X) \in \Grp \\
\\
\Orb(x), Gx && \text{Orbit} \\
&& \da \theset{g\cdot x \suchthat g\in G} \subseteq X  \\
\\
\Stab(x), \Stab_G(x), G_x && \text{Stabilizer} \\
&& \da \ts{ g \in G \st g\cdot x=x } \leq G \\ \\
X/G && \text{Set of orbits} \\
&& \da \ts{\Orb(x) \st x\in X} \subseteq 2^X \\
\\
\Fix(X),\Fix_G(X),  X^G 
&& \text{Set of fixed points}\\
&&
\da \theset{x\in X \suchthat g\cdot x = x\, \forall g\in G} \subseteq X 
.\]



