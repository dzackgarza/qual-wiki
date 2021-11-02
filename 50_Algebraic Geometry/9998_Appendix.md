# Appendix


:::{.remark}
A bunch of stuff I always forget!
:::


:::{.definition title="Classical AG"}
\envlist


- A **section** is just an element $s\in \mcf(U)$.

- A **stalk** of a (pre)sheaf $\mcf$ at a point $p$ is defined as
\[
\mcf_p \da \colim_{p\ni U_i} (\mcf(U_i), \res_{ij})
.\]

- A **germ** $\tilde f_p$ at a point $p$ is an element in a stalk $\mcf_p$.
  It can concretely be described as
  \[
  \tilde f_p = [(U\ni p, s\in \mcf(U))]/\sim && (U, s)\sim (V, t) \iff \exists W \subseteq U \intersect V,\, \ro{s}{W} = \ro{t}{W}
  .\]



:::



:::{.definition title="Colimit of a diagram"}
Given a diagram $J$ in a category $\cat{C}$, regard it as a functor $F: \cat{J}\to \cat{C}$ where $\cat{J}$ is the diagram category of $J$.
Then the **colimit** of $J$ is defined as the initial object in the category of co-cones over $F$.

- A **co-cone** of $F$ is an $N\in \Ob(\cat{C})$ and a family of morphisms $\ts{ \psi_X: F(X)\to N\st X\in \Ob(\cat{J})}$.

- The **category of co-cones** over $F$ is the comma category $F \downarrow \Delta$, where $\Delta: \cat{C} \to \Fun(\cat{J}, \cat{C})$ is the diagonal functor sending $N\in \Ob(\cat{C})$ to the constant functor to $N$:
\[
\Delta(N):\cat{J} &\to \cat{C} \\
X &\mapsto N
.\]

- The **comma category** generalizes slice categories: given categories and functors
\[
\cat{A} \mapsto{S} \cat{C} \mapsfrom{T} \cat{B}
,\]
the comma category $S\downarrow T$ is given by triples $(A, B, h: S(A)\to T(B))$ making the obvious diagrams commute:

\begin{tikzcd}
	{A_0} && {A_1} &&& {S(A_0)} && {S(A_1)} \\
	&& {} \\
	{B_0} && {B_1} &&& {T(B_0)} && {T(B_1)}
	\arrow["{S(f)}", from=1-6, to=1-8]
	\arrow["{h_1}", from=1-8, to=3-8]
	\arrow["{h_1}"', from=1-6, to=3-6]
	\arrow["{T(g)}"', from=3-6, to=3-8]
	\arrow["f", from=1-1, to=1-3]
	\arrow["g", from=3-1, to=3-3]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsOSxbNSwwLCJTKEFfMCkiXSxbNSwyLCJUKEJfMCkiXSxbNywwLCJTKEFfMSkiXSxbNywyLCJUKEJfMSkiXSxbMCwwLCJBXzAiXSxbMiwwLCJBXzEiXSxbMCwyLCJCXzAiXSxbMiwyLCJCXzEiXSxbMiwxXSxbMCwyLCJTKGYpIl0sWzIsMywiaF8xIl0sWzAsMSwiaF8xIiwyXSxbMSwzLCJUKGcpIiwyXSxbNCw1LCJmIl0sWzYsNywiZyJdXQ==)

Taking $\cat{C} = A$, $S = \id_{\cat{A}}$, and $\cat B \da \pt$ to be a 1-object category with only the identity morphism forces $X\da T(\pt) \in \Ob(\cat{A})$ to be a single object and $(\cat A \downarrow X)$ is the usual slice category over $X$.
:::



