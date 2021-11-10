# Lp Facts

:::{.proposition title="Dense subspaces of $L^2(I)$ "}
The following are dense subspaces of $L^2([0, 1])$ and $L^1(\RR)$:

- Bounded measurable functions with bounded support
- Simple functions
- Step functions
- $C_0([0, 1])$
- Smoothly differentiable functions $C_0^\infty([0, 1])$
- Smooth compactly supported functions $C_c^\infty$
:::

:::{.theorem title="?"}
\[
m(X) < \infty \implies \lim_{p\to\infty} \norm{f}_p = \norm{f}_\infty 
.\]
:::

:::{.proof title="?"}
Let $M = \norm{f}_\infty$.

- For any $L < M$, let $S = \theset{\abs{f} \geq L}$. 
- Then $m(S) > 0$ and

\[
\pnorm{f}p 
&= \left( \int_X \abs{f}^p \right)^{\frac 1 p} \\
&\geq \left( \int_S \abs{f}^p \right)^{\frac 1 p} \\
&\geq L ~m(S)^{\frac 1 p} \converges{p\to\infty}\to L \\
&\implies \liminf_p \pnorm{f}p \geq M
.\]

We also have
\[
\pnorm{f}p 
&=  \left( \int_X \abs{f}^p \right)^{\frac 1 p} \\
&\leq \left( \int_X M^p \right)^{\frac 1 p} \\
&= M ~m(X)^{\frac 1 p} \mapsvia{p\to\infty} M \\
&\implies \limsup_p \pnorm{f}p \leq M
.\]

:::

:::{.theorem title="Duals for $L^p$ spaces"}
For $1\leq p< \infty$, $(L^p)\dual \cong L^q$.
:::

:::{.proof title="$p=1$ case"}
?
:::

\todo[inline]{todo}

:::{.proof title="$p=2$ case"}
Use Riesz Representation for Hilbert spaces.
:::

:::{.proposition title="$L^1$ is not quite the dual of $L^\infty$."}
$L^1 \subset (L^\infty)\dual$, since the isometric mapping is always injective, but *never* surjective.
:::

