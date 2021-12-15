# $L^p$ Spaces

:::{.warnings}
$L^p$ convergence does not imply pointwise convergence or even a.e. convergence -- instead, if $f_k\to f$ in $L^p$, there is some *subsequence* that converges to $f$ a.e.

:::

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

:::{.proposition title="?"}
\[
f_k \converges{\ae}\to f \text{ and }
\norm{f_k}_p \leq M
\implies f\in L^p \text{ and } \norm{f}_p \leq M
.\]
:::

:::{.proof title="?"}
*Proof:* Apply Fatou to $\abs{f}^p$:
\[
\int \abs{f}^p = \int \liminf \abs{f_k}^p \leq \liminf \int \abs{f_k}^p = M
.\]
:::

:::{.proposition title="Continuity in $L^1$ holds for all $L^p$, translation operators are continuous"}
\[
f \text{ uniformly continuous }: \quad
\norm{\tau_h f - f}_{L^p(X)} \convergesto{h\to 0} 0 && \forall p
.\]
:::

:::{.proof title="?"}
Take $g_k \in C_c^0 \to f$, then $g$ is uniformly continuous, so
\[
\norm{\tau_h f - f}_p
\leq \norm{\tau_h f - \tau_h g}_p + \norm{\tau_h g - g}_p + \norm{g - f}_p \to 0
.\]
:::

:::{.proposition title="?"}
\[
(f, g) \in L^p\times L^q \implies f\convolve g \text{ uniformly continuous}
.\]
:::

:::{.proof title="?"}
Use Young's inequality
\[
\norm{\tau_h(f\ast g) - f\ast g}_\infty
&= \norm{(\tau_h f - f) \ast g}_\infty \leq \norm{\tau_hf - f}_p \norm{g}_q \to 0
.\]

:::
