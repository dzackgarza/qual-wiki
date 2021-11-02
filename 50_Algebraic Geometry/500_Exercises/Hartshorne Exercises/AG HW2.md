## Problem Set 2

## II.1

:::{.exercise title="II.1.8"}
For any open $U \subseteq X$ show that the functor
\[
\globsec{U, \wait}: \Sh(X) \to \Ab\Grp
\]
is left-exact, but need not be exact.
:::

:::{.solution}
We're given exactness of
\[
\xi: 0 \to \mcf_1 \mapsvia{f} \mcf_2 \mapsvia{g} \mcf_3 \to 0
,\]
which (e.g. ) is data of the form


\begin{tikzcd}
	U && {\mcf_1(U)} && {\mcf_2(U)} \\
	\\
	V && {\mcf_1(V)} && {\mcf_2(V)}
	\arrow[""{name=0, anchor=center, inner sep=0}, "{\iota_{UV}}", hook, from=3-1, to=1-1]
	\arrow[""{name=1, anchor=center, inner sep=0}, "{\mcf_1\mid^U_V}", from=1-3, to=3-3]
	\arrow["{\mcf_2\mid^U_V}", from=1-5, to=3-5]
	\arrow["{f_V}", from=1-3, to=1-5]
	\arrow["{f_U}"', from=3-3, to=3-5]
	\arrow["f", shorten <=14pt, shorten >=14pt, Rightarrow, from=0, to=1]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsNixbMiwwLCJcXG1jZl8xKFUpIl0sWzAsMCwiVSJdLFswLDIsIlYiXSxbMiwyLCJcXG1jZl8xKFYpIl0sWzQsMiwiXFxtY2ZfMihWKSJdLFs0LDAsIlxcbWNmXzIoVSkiXSxbMiwxLCJcXGlvdGFfe1VWfSIsMCx7InN0eWxlIjp7InRhaWwiOnsibmFtZSI6Imhvb2siLCJzaWRlIjoidG9wIn19fV0sWzAsMywiXFxSZXNfMShVLCBWKSJdLFs1LDQsIlxcUmVzXzIoVSwgVikiXSxbMCw1LCJmX1YiXSxbMyw0LCJmX1UiLDJdLFs2LDcsImYiLDAseyJzaG9ydGVuIjp7InNvdXJjZSI6MjAsInRhcmdldCI6MjB9fV1d)

Applying $\Gamma(X; \wait)$, we want to show exactness of
\[
\xi_X: 0 \to \mcf_1(X) \mapsvia{f_X} \mcf_2(X) \mapsvia{g_X} \mcf_3(X) \to \cdots
.\]

**Exactness at $f_X$**:

- Use that $f$ is exact $\iff \ker f = \mathbf 0$ as a sheaf, so
\[
(\ker f)(U) = (\mathbf 0)(U) = 0 \in \CRing
.\]
  - Use that 
  \[
(\ker f)(U) &\da \ker f_U \da \ker( \mcf_1(U) \mapsvia{f_U} \mcf_2(U)) \\
\implies
\ker f_X &= (\ker f)(X) = (\mathbf 0)(X) = 0
  .\]

- Why this works: the kernel presheaf is already a sheaf, so we can use the presheaf assignment $(\ker f)(U) = \ker f_U$ directly.
  This won't work for the cokernel sheaf, since the image presheaf needs to be sheafified.

Alternatively, a direct argument that $f_X$ is injective:

- A fact we'll need: $\xi$ is exact iff locally exact.
  Sketch of situation, there are commutative squares for all $p\in X$:

\begin{tikzcd}
	{\xi:} && 0 && {\mcf_1} && {\mcf_2} && {\mcf_3} && 0 \\
	\\
	{\xi_X:} && {?} && {\mcf_1(X)} && {\mcf_2(X)} && {\mcf_3(X)} && {?} \\
	\\
	{\xi_p:} && 0 && {(\mcf_1)_p} && {(\mcf_2)_p} && {(\mcf_3)_p} && 0
	\arrow[from=5-3, to=5-5]
	\arrow["{f_p}"', hook, from=5-5, to=5-7]
	\arrow["{g_p}"', two heads, from=5-7, to=5-9]
	\arrow[from=5-9, to=5-11]
	\arrow["{\mcf_1\mid^X_p}", from=3-5, to=5-5]
	\arrow["{\mcf_2\mid^X_p}", from=3-7, to=5-7]
	\arrow["{\mcf_3\mid^X_p}", from=3-9, to=5-9]
	\arrow[from=3-3, to=3-5]
	\arrow["{f_X}", from=3-5, to=3-7]
	\arrow["{g_X}", from=3-7, to=3-9]
	\arrow[from=3-9, to=3-11]
	\arrow[from=1-3, to=1-5]
	\arrow["f", hook, from=1-5, to=1-7]
	\arrow["g", two heads, from=1-7, to=1-9]
	\arrow[from=1-9, to=1-11]
	\arrow["{\Gamma(X;\wait)}", Rightarrow, from=1-7, to=3-7]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsMTgsWzIsMiwiPyJdLFs0LDIsIlxcbWNmXzEoWCkiXSxbNiwyLCJcXG1jZl8yKFgpIl0sWzgsMiwiXFxtY2ZfMyhYKSJdLFsxMCwyLCI/Il0sWzQsNCwiKFxcbWNmXzEpX3AiXSxbNiw0LCIoXFxtY2ZfMilfcCJdLFs4LDQsIihcXG1jZl8zKV9wIl0sWzIsNCwiMCJdLFsxMCw0LCIwIl0sWzAsMiwiXFx4aV9YOiJdLFswLDQsIlxceGlfcDoiXSxbNCwwLCJcXG1jZl8xIl0sWzAsMCwiXFx4aToiXSxbNiwwLCJcXG1jZl8yIl0sWzgsMCwiXFxtY2ZfMyJdLFsyLDAsIjAiXSxbMTAsMCwiMCJdLFs4LDVdLFs1LDYsImZfcCIsMix7InN0eWxlIjp7InRhaWwiOnsibmFtZSI6Imhvb2siLCJzaWRlIjoidG9wIn19fV0sWzYsNywiZ19wIiwyLHsic3R5bGUiOnsiaGVhZCI6eyJuYW1lIjoiZXBpIn19fV0sWzcsOV0sWzEsNSwiXFxSZXNfMShYLCBwKSJdLFsyLDYsIlxcUmVzXzIoWCwgcCkiXSxbMyw3LCJcXFJlc18zKFgsIHApIl0sWzAsMV0sWzEsMiwiZl9YIl0sWzIsMywiZ19YIl0sWzMsNF0sWzE2LDEyXSxbMTIsMTQsImYiLDAseyJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6InRvcCJ9fX1dLFsxNCwxNSwiZyIsMCx7InN0eWxlIjp7ImhlYWQiOnsibmFtZSI6ImVwaSJ9fX1dLFsxNSwxN10sWzE0LDIsIlxcR2FtbWEoWDtcXHdhaXQpIiwwLHsibGV2ZWwiOjJ9XV0=)


- Write the kernel out:
\[
\ker f_X \da \ts{ s\in \mcf_1(X) \st f_X(s) = 0 \in \mcf_2(X)}
.\]
- Suppose $s\in \mcf_1(X)$ and $f_X(s) = 0$ in $\mcf_2(X)$.
  Then
  \[
  (\mcf_2 \mid^X_p \circ f_X )(s) &= \mcf_2\mid^X_p( 0) = 0 \in (\mcf_2)_p \text{ Ring mor, 0 to 0}\\
  \implies (f_p \circ \mcf_1 \mid^X_p(s) &= (\mcf_2 \mid^X_p \circ f_X)(s) = 0 \text{ by commutativity} \\
  \implies \mcf_1 \mid^X_p (s) &= 0 \text{ left-cancel $f_p$ since mono}
  ,\]
  which holds for all $p$.

- Claim: by the sheaf condition on $\mcf_1$, $s= 0 \in \mcf_1(X)$.

  - Fix $p$. 
    For $s\in \mcf_1(X)$, write a representative $\mcf_1\mid^X_p(s) = [U, \tilde s\in \mcf_1(U)]$.

  > Recall $(U_1, s_1) \sim (U_2, s_2) \in \mcf_p \iff$ they're both equivalent to $(W, t)$ where $W \subseteq U_1 \intersect U_2$ and
  \[
  \mcf_1 \mid^{U_1}_W (s_1) = t = \mcf_1\mid^{U_2}_W (s_2)
  .\]

  - Then $s_p \da \mcf_1 \mid^X_p(s) = 0 \sim (W, 0) \in (\mcf_1)_p$ means there exists some $W_p$ and a lift $\tilde s(p) = 0 \in \mcf_1(W_p)$ with $\mcf_1\mid^{W_p}_p(\tilde s(p)) = s_p$.

  - But this holds for all $p$, and $\ts{W_p}_{p\in X} \covers X$, so by the sheaf gluing axiom for $\mcf_1$, $\ts{ \tilde s(p) \in \mcf_1(W_p) \st p\in X}$ glue to a unique $\tilde s\in \mcf_1(X)$, and by uniqueness, $\tilde s = s = 0 \in \mcf_1(X)$.

**Exactness at $g_X$**:

- We want to show $\ker g_X = \im f_X$.
  First show $\im f_X \subseteq \ker g_X$, and let $s \in \im f_X \subseteq \mcf_2(X)$.

- A small diagram chase:

\begin{tikzcd}
	&& \textcolor{rgb,255:red,92;green,92;blue,214}{f_X\inv(s)} && \textcolor{rgb,255:red,92;green,92;blue,214}{s} && {\ell \da g_X(s)} \\
	0 && {\mcf_1(X)} && {\mcf_2(X)} && {\mcf_3(X)} && {?} \\
	\\
	0 && {(\mcf_1)_p} && {(\mcf_2)_p} && {(\mcf_3)_p} \\
	&& \textcolor{rgb,255:red,92;green,92;blue,214}{\mcf_1\mid^U_p(f_X\inv(s))} && \textcolor{rgb,255:red,92;green,92;blue,214}{t \da \mcf_2\mid^U_p(s)} && 0
	\arrow["{f_X}", from=2-3, to=2-5]
	\arrow[from=2-1, to=2-3]
	\arrow["{g_X}", from=2-5, to=2-7]
	\arrow["{\mcf_1\mid^U_p}"{description}, from=2-3, to=4-3]
	\arrow[from=4-1, to=4-3]
	\arrow["{f_p}"', from=4-3, to=4-5]
	\arrow["{g_p}"', from=4-5, to=4-7]
	\arrow["{\mcf_3\mid^U_p}", from=2-7, to=4-7]
	\arrow["{\mcf_2\mid^U_p}"{description}, from=2-5, to=4-5]
	\arrow[from=2-7, to=2-9]
	\arrow[color={rgb,255:red,92;green,92;blue,214}, curve={height=-30pt}, dotted, maps to, from=1-5, to=5-5]
	\arrow[color={rgb,255:red,92;green,92;blue,214}, dashed, maps to, from=1-3, to=1-5]
	\arrow[color={rgb,255:red,92;green,92;blue,214}, curve={height=18pt}, dotted, maps to, from=1-3, to=5-5]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsMTUsWzAsMSwiMCJdLFsyLDEsIlxcbWNmXzEoWCkiXSxbNCwxLCJcXG1jZl8yKFgpIl0sWzYsMSwiXFxtY2ZfMyhYKSJdLFsyLDMsIihcXG1jZl8xKV9wIl0sWzQsMywiKFxcbWNmXzIpX3AiXSxbNiwzLCIoXFxtY2ZfMylfcCJdLFswLDMsIjAiXSxbOCwxLCI/Il0sWzQsMCwicyIsWzI0MCw2MCw2MCwxXV0sWzIsMCwiZl9YXFxpbnYocykiLFsyNDAsNjAsNjAsMV1dLFs2LDAsIlxcZWxsIFxcZGEgZ19YKHMpIl0sWzQsNCwidCBcXGRhIFxcbWNmXzJcXG1pZF5VX3AocykiLFsyNDAsNjAsNjAsMV1dLFs2LDQsIjAiXSxbMiw0LCJcXG1jZl8xXFxtaWReVV9wKGZfWFxcaW52KHMpKSIsWzI0MCw2MCw2MCwxXV0sWzEsMiwiZl9YIl0sWzAsMV0sWzIsMywiZ19YIl0sWzEsNCwiXFxtY2ZfMVxcbWlkXlVfcCIsMV0sWzcsNF0sWzQsNSwiZl9wIiwyXSxbNSw2LCJnX3AiLDJdLFszLDYsIlxcbWNmXzNcXG1pZF5VX3AiXSxbMiw1LCJcXG1jZl8yXFxtaWReVV9wIiwxXSxbMyw4XSxbOSwxMiwiIiwxLHsiY3VydmUiOi01LCJjb2xvdXIiOlsyNDAsNjAsNjBdLCJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJtYXBzIHRvIn0sImJvZHkiOnsibmFtZSI6ImRvdHRlZCJ9fX1dLFsxMCw5LCIiLDEseyJjb2xvdXIiOlsyNDAsNjAsNjBdLCJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJtYXBzIHRvIn0sImJvZHkiOnsibmFtZSI6ImRhc2hlZCJ9fX1dLFsxMCwxMiwiIiwxLHsiY3VydmUiOjMsImNvbG91ciI6WzI0MCw2MCw2MF0sInN0eWxlIjp7InRhaWwiOnsibmFtZSI6Im1hcHMgdG8ifSwiYm9keSI6eyJuYW1lIjoiZG90dGVkIn19fV1d)


- Push $s$ into $(\mcf_2)_p$ and pull back to $f_X\inv(s) \in \mcf_1(X)$, by commutativity, the former is in $\im f_p$, so
\[
\mcf_1\mid^U_p(s) \in \im f_p = \ker g_p
.\]

- Then push $s \mapsvia{g_X} \ell$, so $\mcf_3 \mid^U_p(\ell) = 0$ by commutativity.
  Since this is true for all stalks at all $p$, $\ell = 0\in \mcf_3(X)$, so $\ell \in \ker g_X$.

**A counterexample:**

The exponential SES, assembled from groups:

\begin{tikzcd}
	0 && \ZZ && {\GG_a(\CC)} && {\GG_m(\CC\units)} && 0 && \in\Grp \\
	&&&& {} \\
	0 && {\ul{\ZZ}} && {\Hol_X(\wait)} && {\Hol_X(\wait)\units} && 0 && {\in \Sh(X, \Grp), X \da \CC\units} \\
	\\
	0 && \ZZ && {\Hol_X(X)} && {\Hol_X(X)\units} && 0 && {\in \CRing}
	\arrow[from=1-1, to=1-3]
	\arrow[from=1-3, to=1-5]
	\arrow["{\exp: z \mapsto e^{2\pi i z}}", from=1-5, to=1-7]
	\arrow[from=1-7, to=1-9]
	\arrow[from=3-7, to=3-9]
	\arrow[from=5-7, to=5-9]
	\arrow["\exp", from=5-5, to=5-7]
	\arrow["\exp", from=3-5, to=3-7]
	\arrow[from=3-3, to=3-5]
	\arrow[from=5-3, to=5-5]
	\arrow[from=3-1, to=3-3]
	\arrow[from=5-1, to=5-3]
	\arrow["{\Gamma(X; \wait)}"{description}, Rightarrow, from=3-5, to=5-5]
	\arrow[squiggly, from=1-5, to=3-5]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsMTksWzAsMCwiMCJdLFsyLDAsIlxcWloiXSxbNCwwLCJcXEdHX2EoXFxDQykiXSxbNiwwLCJcXEdHX20oXFxDQ1xcdW5pdHMpIl0sWzgsMCwiMCJdLFsxMCwwLCJcXGluXFxHcnAiXSxbMCwyLCIwIl0sWzIsMiwiXFx1bHtcXFpafSJdLFs0LDIsIlxcSG9sX1goXFx3YWl0KSJdLFs2LDIsIlxcSG9sX1goXFx3YWl0KVxcdW5pdHMiXSxbOCwyLCIwIl0sWzEwLDIsIlxcaW4gXFxTaChYLCBcXEdycCksIFggXFxkYSBcXENDXFx1bml0cyJdLFswLDQsIjAiXSxbMiw0LCJcXFpaIl0sWzQsNCwiXFxIb2xfWChYKSJdLFs2LDQsIlxcSG9sX1goWClcXHVuaXRzIl0sWzgsNCwiMCJdLFsxMCw0LCJcXGluIFxcQ1JpbmciXSxbNCwxXSxbMCwxXSxbMSwyXSxbMiwzLCJcXGV4cDogeiBcXG1hcHN0byBlXnsyXFxwaSBpIHp9Il0sWzMsNF0sWzksMTBdLFsxNSwxNl0sWzE0LDE1LCJcXGV4cCJdLFs4LDksIlxcZXhwIl0sWzcsOF0sWzEzLDE0XSxbNiw3XSxbMTIsMTNdLFs4LDE0LCJcXEdhbW1hKFg7IFxcd2FpdCkiLDEseyJsZXZlbCI6Mn1dLFsyLDgsIiIsMSx7InN0eWxlIjp7ImJvZHkiOnsibmFtZSI6InNxdWlnZ2x5In19fV1d)

Here $\Hol_X(\wait)\units$ denotes the multiplicatively invertible functions, i.e. nonvanishing functions.


But if the bottom sequence were exact, then every invertible holomorphic function would have a logarithm on all of $\CC\units$, but for example the identity function does not.

:::

:::{.exercise title="II.1.14"}
Let $\mcf \in \Sh(X)$ and $s\in \mcf(U)$ be a section, and define 
\[
\supp s &\da \ts{p\in U \st s_p \neq 0} \subseteq U \\
\supp \mcf &\da \ts{p\in X\st \mcf_p\neq 0} \subseteq  X
,\]
where $s_p$ denotes the germ of $s$ in the stalk $\mcf_p$.
Show that $\supp s$ is closed in $U$ but $\supp \mcf$ need not be closed in $X$.

:::

:::{.solution}

**$\supp(s)$ is closed**:

- Write
\[
\supp(s) \da \ts{p\in U \st \mcf\mid^U_p(s) \neq 0} \subseteq U \\
\implies 
\supp(s)^c \da U\sm \supp(s) \da \ts{p\in U \st \mcf\mid^U_p(s) = 0} \subseteq U \\
.\]

- Now use that if $p\in U$ with $s=0$ in the stalk at $p$, then $s=0$ in an open neighborhood $W_p$ of $p$ with $W_p \subseteq U\sm \supp(s)$, so every such $p$ is interior.

**$\supp(\mcf)$ is not closed**:

- Take the skyscraper sheaf: take the constant sheaf on a point $q\in X$, then push it forward along the inclusion of $q$:

\begin{tikzcd}
	{\ul{A}} && {q^* \ul{A}} \\
	\\
	q && X
	\arrow["q", hook, from=3-1, to=3-3]
	\arrow["{q^*}", from=1-1, to=1-3]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsNCxbMCwyLCJxIl0sWzIsMiwiWCJdLFswLDAsIlxcdWx7QX0iXSxbMiwwLCJxXiogXFx1bHtBfSJdLFswLDEsInEiLDAseyJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6InRvcCJ9fX1dLFsyLDMsInFeKiJdXQ==)

- Then check
\[
q^* \ul{A}(U) = 
\begin{cases}
A & q\in U 
\\
0 & \text{else}.
\end{cases}
,\quad (q^* \ul{A})_p = 
\begin{cases}
A & p=q 
\\
0 & \text{else}.
\end{cases}
\]

- Now invert this construction by taking the sheaf
\[
\mcf \da \sheafify{\not q^* \ul{A}}:
\sheafify{U \mapsto
\begin{cases}
A & q\not\in U 
\\
0 & q\in U.
\end{cases}
}
\]
- $\not q^*\ul{A}$ and $\mcf$ have the same stalks, and a computation shows
\[
(\not q^*\ul{A})_p = 
\begin{cases}
A & p\neq q
\\
0 & p=q.
\end{cases}
.\]

- Then for a fixed $q\in X$, we have $\supp \mcf = X \sm \cl_X(\ts{ q})$.
  - Why: if there is some neighborhood $U\ni p$ that doesn't meet $q$, then $\mcf\mid^X_U(V) = A$ for every $V \subseteq U$, so the colimit stabilizes and is equal to $A$.
  - Conversely, if every neighborhood of $p$ meets $q$, then $\mcf \mid^X_U(V) = 0$ for every $V \subseteq U$ (including $U$), so the colimit stabilizes to zero.

- Now concretely take $X \da \AA^1\slice k$ and $q=0$, then $\ts{0} = V(x)$ for $x\in k[x]$ is closed, so $\cl_X(\ts{0}) = \ts{0}$.
- Thus 
\[
\supp \mcf = \AA^1 \sm \cl_X(\ts{0}) = \AA^1\smz = D(x)
\]
is open and not closed when $k$ is infinite.
:::

:::{.exercise title="II.1.17"}
Let $X\in \Top, A\in \Ab\Grp, p\in X$ and define the skyscraper sheaf as
\[
\iota_p(A)(U) \da 
\begin{cases}
A & p\in U 
\\
0 & \text{else}.
\end{cases}
\]
Show that the stalk $\iota_p(A)_q = A$ when $q\in \cl_X(\ts{p})$ and 0 otherwise, and that there is an equality of sheaves $\iota_p(A) = \iota_*(\ul{A})$ where $\iota: \cl_X(\ts{p}) \injects X$ is the inclusion.

:::

:::{.solution}
Computation of stalks: see previous problem.

That $\iota_p A \da(U\mapsto A \chi_{p\in U})$ is *equal* to $\iota_* \ul{A}$ the pushforward sheaf:

- Note that $\ul{A}$ on $\ts{p}$ is given by 
\[
\ul{A}(U)
\da
\Top(U, a)
=
\begin{cases}
A & U = \ts{p}  
\\
0 & U = \emptyset.
\end{cases}
.\]

- Now check
\[
\iota_* \ul{A}(U) 
\da \ul{A} (\iota\inv(U))
&=
\begin{cases}
A & \iota\inv(U) = p 
\\
0 & \iota\inv(U) = \emptyset.
\end{cases}
\\
&=
\begin{cases}
A & U \ni \iota(p) = p
\\
0 & U\not\ni \iota(p) = p
\end{cases}
\]

- Now take the identity maps as the components of a morphism $\iota_p A\to \iota_* \ul{A}$, which induces the identity on stalks, making these sheaves equal.

:::


## II.2

:::{.exercise title="II.2.1"}
Let $A\in \Ring$ and $X\da \spec(A)$, and for $f\in A$ let $D(f) \da V(\gens{f})^c$.
Show that there is an isomorphism of ringed spaces
\[
(D(f), \ro{\OO_X}{D(f)}) \mapsvia{\sim} \spec(A_f)
.\]
:::


:::{.strategy}
\envlist

- Take $\iota: A\to A_f$ and induced maps $\iota^*: \spec A_f \to \spec A$.
- Use $\spec A\localize{S} \cong \ts{p\in \spec A \st p \intersect S = \emptyset }$
  - So $\spec A_f = \ts{p\in \spec A \st p \not\contains \gens{f}}$.
- Construct $\psi \da \iota^*$, check $D(g/f^k) \mapsvia{\psi} D(gf)$ and $D(g) \mapsvia{\psi\inv} D(g/1)$.
- Use $\OO_{\spec A}\ro{}{D(f)}(D(g)) = (A_f)_g$ and define $\psi^\# = \id$.
:::


:::{.solution}

Recall: for $I\normal A$ any ideal,
\[
V(I) = \ts{p\in \spec A \st p\contains I} \\
D(I) \da V(I)^c = \ts{p\in \spec A \st p\not\contains I}
,\]
and there is a correspondence
\[
i: A&\mapsto A_f \\
a &\mapsto \tv{a\over 1}
\\ \\
\adjunction{i_*}{i^*}
{ 
\ts{p\in \spec A \st p \intersect \ts{f^n} = \emptyset}}
{\spec A_f} \\
p \mapsto \gens{i(p)} = \ts{p'/s \st p'\in p, s\in \ts{f^n} }\\
i\inv(q) \mapsfrom q = \ts{g/f^n}\normal A_f
,\]
i.e. prime ideals of $A_S$ are prime ideals of $A$ not meeting $S$.

Let $Y\da \spec A \localize{f}$.
Need
\[
f&\in \Top(D(f), Y)\\
f^\# &\in \Mor_{\Sh\slice X}(\OO_{Y}, f^* \ro{\OO_X}{D(f)})
.\]

- Use the commutative algebra fact: primes of localizations lift to primes not intersecting the local set.
  Let $i: A\to A_f$ be the ring morphism $a\mapsto a/1$, this induces
\[
\spec A\localize{f} 
&\mapsvia{i^*} 
\ts{p\in \spec A\st p \intersect \ts{f^n}_{n\geq 1} = \emptyset } \\
&= \ts{p\in \spec A \st p \not\contains \gens{f}} \\
&\da D(\gens{f}) = D(f)
.\]

  Here $i^*(q) = i\inv(q)$ is $i_*(p) = \gens{i(p)}$.

- So take $\psi: \spec A_f \to D(f)$ to be $i^*$, which is a bijection.

- Check this is a homeomorphism: it's an open map, since
\[
D(g/f^k ) &\mapsvia{\psi} D(gf) \\
D(g) &\mapsvia{\psi\inv} D(g/1)
,\]

- Then $\psi^\#\da \id$ induces an isomorphism of sheaves: check that on distinguished opens,

\[
D(g) \subseteq Y \implies 
\psi^* \ro{\OO_X}{D(f)}(D(g)) 
&\da 
\ro{\OO_X}{D(f)}(\psi\inv( D(g)) ) \\
&=
\ro{\OO_X}{D(f)}( D(g/1) ) \\
&=
(A_f)_{g/1}
,\]
using that $\OO_X(D(h)) = k[X]_{h}$, so the coordinate ring of $D(f)$ is $A_f$.

- Similarly,
\[
\OO_{\spec A_f}(D(g)) = (A_f)_g
,\]
  and these are equal.

- Now for any $U \subseteq \spec A_f$, taken an open cover by distinguished opens $D(g_k)\covers U$; then the sections of each sheaf agree on each $D(g_k)$ and using the sheaf axioms they glue to agreeing sections on $U$, so this induces an isomorphism of sheaves.

:::

:::{.exercise title="II.2.3"}
Note that $(X, \OO_X)\in \Sch$ is **reduced** iff $\OO_X(U)$ has no nilpotents, and for $A\in \Ring$ define $A^{\red}\da A/\sqrt{0}$ to be $A$ modulo its ideal of nilpotents.

a. Show that $X$ is reduced iff for every $p\in X$, the local ring $\OO_{X, p}$ has no nilpotents.

b. Let $\OO_X^{\red}$ be the sheafification of $U \mapsto \OO_X(U)^\red$.
    Show that $X_\red \da (X, \OO_X^\red)$ is a scheme, and there is a morphism of schemes $X_\red \mapsvia{\red} X$ which induces a homeomorphism $\abs{X_\red}\to \abs{X}$ on underlying topological spaces.

c. Let $X \mapsvia{f} Y\in \Sch$ with $X$ reduced.
  Show that there is a unique morphism $X \mapsvia{g} Y_\red$ such that $f$ is the composition:

\begin{tikzcd}
	X && Y \\
	\\
	&& {Y_\red}
	\arrow["f", from=1-1, to=1-3]
	\arrow["\red"', from=3-3, to=1-3]
	\arrow["{\exists !g}"', from=1-1, to=3-3]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsMyxbMCwwLCJYIl0sWzIsMCwiWSJdLFsyLDIsIllfXFxyZWQiXSxbMCwxLCJmIl0sWzIsMSwiXFxyZWQiLDJdLFswLDIsIlxcZXhpc3RzICFnIiwyXV0=)

:::

:::{.strategy}
Part a:

- Zero in every stalk implies zero by the sheaf axiom.
- 

Part b:

- Cover by affines.
- $\nilrad{R} \leq \mfp$ for every $\mfp \in \spec R$.
- $R_\red \da R/\nilrad{R}$ is a quotient, and localization commutes with quotients.
- Maps $R\to S$ with $S$ reduced factor through $R_\red$.
- Sheafification has the same stalks, and isomorphism on stalks iff isomorphism of sheaves.
- Pushforwards of reduces sheaves are reduced.
:::

:::{.solution title="1"}
$\implies$:
If $\OO_{X, p}$ has nilpotents, pick $s$ with $s^n\in 0 \in \OO_{X, p}$.
This lifts to some $s^n = 0 \in \OO_X(U)$, so $s$ is nilpotent in $\OO_X(U)$, a contradiction.

$\impliedby$:
If $s\in \OO_X(U)$ has nilpotents, then $\OO_X\mid^X_p(s^n) = 0$ in the stalk, making $s$ nilpotent in the stalk.

:::

:::{.solution title="2"}

:::

:::{.exercise title="II.2.5"}
Describe $\spec \ZZ$ and show it is terminal in $\Sch$, i.e. each $X\in \Sch$ admits a unique morphism $X\to \spec \ZZ$.
:::

:::{.strategy}

\envlist

- An adjunction inducing an equivalence:
\[
\adjunction{\Globsec{\wait}}{\spec(\wait)}{\Sch\op}{\CRing}\hspace{6em}
\\ \\
\Mor_{{\Sch}}(X, \text{Spec}(R)) \cong \Mor_{{\CRing}}(R, \Gamma(X;\mathcal{O}_X))
.\]

:::

:::{.exercise title="II.2.7"}
Let $X\in \Sch$ and for $x\in X$ let $\OO_x$ be the local ring at $x$ and $\mfm_x$ its maximal ideal.
Let $\kappa(x) \da \OO_x/\mfm_x$ be the residue field at $x$.

Then for $k$ any field, show that giving a morphism $\spec(k) \to X \in \Sch$ is equivalent to giving a point $x\in X$ and an inclusion $\kappa(x) \injects k$.

\[
x^2 - y^q = 1 && x^p - y^2 = 1
.\]
\[
x^2 - y^q = 1 && x^p - y^2 = 1
.\]
:::

:::{.strategy}
?
:::

:::{.warnings}
- The image presheaf isn't necessarily a sheaf.
- Filtered direct limits are exact.
- Finite limits commute with filtered colimits in most categories
- Right adjoints preserve colimits
- $\Hom(\wait, \wait): \cat{C}\op \times \cat{C}\to \cat{C}$ is continuous (for regular limits, noting limits in $\cat C\op$ are colimits in $\cat C$).
- Right adjoints preserve limits, left adjoints preserve colimits.
  Sheafification is left adjoint to the forgetful functor, so right exact, so preserves colimits
  - So exact in presheaves implies exact in sheaves, but exact in shaves only implies left-exact in presheaves.
  Sheaf cohomology measures how much the presheaf fails exactness.
:::

