# Useful Facts

:::{.definition title="Acyclic"}
A chain complex $C$ is **acyclic** if and only if $H_*(C) = 0$.
:::


:::{.proposition title="Algebra Facts"}
\envlist

- Free $\implies$ projective $\implies$ flat $\implies$ torsionfree (for finitely-generated \(R\dash\)modules)
  - Over $R$ a PID: free $\iff$ torsionfree
:::

:::{.remark}
Notational conventions:

- Finite direct products: \( \bigoplus \)
- Cohomological indexing: $C^i, \bd^i$
- Homological indexing: $C_i, \bd_i$
- Right-derived functors $R^iF$.
  - Come from left-exact functors
  - Require *injective* resolutions
  - Extend to the right: $0 \to F(A) \to F(B) \to F(C) \to L_1 F(A) \cdots$
- Left-derived functors $L_i F$.
  - Come from right-exact functors
  - Require *projective* resolutions
  - Extend to the left: $\cdots L_1F(C) \to F(A) \to F(B) \to F(C) \to 0$

- Colimits:
  - Examples: coproducts, direct limits, cokernels, initial objects, pushouts
  - Commute with left adjoints, i.e. $L(\colim F_i) = \colim LF_i$.
- Examples of limits:
  - Products, inverse limits, kernels, terminal objects, pullbacks
  - Commute with right adjoints. i.e. $R(\colim F_i) = \colim RF_i$.
:::

![[100_Homological Algebra/Hom and Ext]]

![[100_Homological Algebra/Tensor and Tor]]


## Universal Properties

:::{.proposition title="Universal Property of the Quotient for Groups"}
If $f: G\to K$ and $H\normal G$ (so that $G/H$ is defined), then the map $f$ descends to the quotient if and only if $H \subseteq \ker(f)$.
:::

:::{.proposition title="Kernels as pullbacks and cokernels as pushouts"}
The kernel $\ker f$ of a morphism $f$ can be characterized as a cartesian square, and the cokernel $\coker f$ as a cocartesian square:

\begin{tikzcd}
	K \\
	& {\ker f} && \textcolor{rgb,255:red,92;green,92;blue,214}{A} && 0 \\
	\\
	& 0 && \textcolor{rgb,255:red,92;green,92;blue,214}{B} && {\coker f} \\
	&&&&&& C
	\arrow[dotted, from=2-6, to=4-6]
	\arrow[from=2-4, to=2-6]
	\arrow["f"', color={rgb,255:red,92;green,92;blue,214}, from=2-4, to=4-4]
	\arrow["0"', dotted, from=4-4, to=4-6]
	\arrow["\lrcorner"{anchor=center, pos=0.125, rotate=180}, draw=none, from=4-6, to=2-4]
	\arrow["{\exists !}"', dashed, from=4-6, to=5-7]
	\arrow[curve={height=12pt}, from=4-4, to=5-7]
	\arrow[curve={height=-12pt}, from=2-6, to=5-7]
	\arrow[dotted, from=2-2, to=2-4]
	\arrow[from=4-2, to=4-4]
	\arrow[dotted, from=2-2, to=4-2]
	\arrow["\lrcorner"{anchor=center, pos=0.125}, draw=none, from=2-2, to=4-4]
	\arrow[curve={height=-12pt}, from=1-1, to=2-4]
	\arrow[curve={height=12pt}, from=1-1, to=4-2]
	\arrow["{\exists !}"', dashed, from=1-1, to=2-2]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsOCxbMywxLCJBIixbMjQwLDYwLDYwLDFdXSxbNSwxLCIwIl0sWzMsMywiQiIsWzI0MCw2MCw2MCwxXV0sWzUsMywiXFxjb2tlciBmIl0sWzYsNCwiQyJdLFsxLDEsIlxca2VyIGYiXSxbMSwzLCIwIl0sWzAsMCwiSyJdLFsxLDMsIiIsMCx7InN0eWxlIjp7ImJvZHkiOnsibmFtZSI6ImRvdHRlZCJ9fX1dLFswLDFdLFswLDIsImYiLDIseyJjb2xvdXIiOlsyNDAsNjAsNjBdfSxbMjQwLDYwLDYwLDFdXSxbMiwzLCIwIiwyLHsic3R5bGUiOnsiYm9keSI6eyJuYW1lIjoiZG90dGVkIn19fV0sWzMsMCwiIiwwLHsic3R5bGUiOnsibmFtZSI6ImNvcm5lciJ9fV0sWzMsNCwiXFxleGlzdHMgISIsMix7InN0eWxlIjp7ImJvZHkiOnsibmFtZSI6ImRhc2hlZCJ9fX1dLFsyLDQsIiIsMCx7ImN1cnZlIjoyfV0sWzEsNCwiIiwwLHsiY3VydmUiOi0yfV0sWzUsMCwiIiwwLHsic3R5bGUiOnsiYm9keSI6eyJuYW1lIjoiZG90dGVkIn19fV0sWzYsMl0sWzUsNiwiIiwxLHsic3R5bGUiOnsiYm9keSI6eyJuYW1lIjoiZG90dGVkIn19fV0sWzUsMiwiIiwxLHsic3R5bGUiOnsibmFtZSI6ImNvcm5lciJ9fV0sWzcsMCwiIiwxLHsiY3VydmUiOi0yfV0sWzcsNiwiIiwxLHsiY3VydmUiOjJ9XSxbNyw1LCJcXGV4aXN0cyAhIiwyLHsic3R5bGUiOnsiYm9keSI6eyJuYW1lIjoiZGFzaGVkIn19fV1d)

:::

## Adjunctions


:::{.definition title="Adjoints"}
\todo[inline]{todo}
:::


:::{.proposition title="Tensor-Hom Adjunction"}
For a fixed $M\in \bimod{R}{S}$, there is an adjunction
\[
\adjunction{ \wait \tensor_R M }{\Hom_S(M, \wait)}{ \modsright{R} } { \modsright{S} }
,\]
so for $Y \in \bimod{A}{R}$ and $Z \in \bimod{B}{S}$, there is a (natural) isomorphism in \( \bimod{B}{A} \):
\[
\Hom_S(X \tensor_R M, Z) \mapsvia{\sim} \Hom_R( X, \Hom_S(M, Z) )
.\]
:::

:::{.proposition title="Forgetful Adjunctions"}
Let \( F: \mods{R} \to \mods{\ZZ} \) be the forgetful functor, then there are adjunctions
\[
\adjunction{F}{ \Hom_\ZZ(R, \wait)} {\mods{R} } {\mods{\ZZ} } \\ \\
\adjunction{R\tensor_\ZZ \wait }{F}{ \mods{\ZZ} }{ \mods{R} }
.\]

:::


