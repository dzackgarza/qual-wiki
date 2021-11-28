# Rouché 

:::{.theorem title="Rouché's Theorem" ref="Rouche"}
If

- $f, g$ are meromorphic on $\Omega$
- $\gamma \subset \Omega$ is a toy contour winding about each zero/pole of $f, g$ exactly once,
- $\abs{g} < \abs{f}$ on $\gamma$

then
\[
\Ind_{z=0}(f\circ \gamma)(z) = \Ind_{z=0}((f+g)\circ \gamma)(z) \\
\implies Z_f - P_f = Z_{f+g} - P_{f+g}
.\]
In particular, if $f, g$ are holomorphic, they have the same number of zeros in $\Omega$.

:::

:::{.slogan}
The number of zeros/poles are determined by a dominating function.
:::

#todo prove

![[30_Complex Analysis/figures/2021-10-29_01-39-19.png]]

![[30_Complex Analysis/figures/2021-10-29_01-39-19.png]]

![[30_Complex Analysis/figures/2021-10-29_01-39-19.png]]

![[30_Complex Analysis/figures/2021-10-29_01-39-43.png]]

![[30_Complex Analysis/figures/2021-10-29_01-39-43.png]]

:::{.exercise title="?"}
Show that $h(z) =z^5 + 3z + 1$ has 5 zeros in $\abs z \leq 2$.
:::


:::{.exercise title="?"}
Show that $h(z) = z + 3 + 2e^z$ has one root in $\ts{ \Re(z) \leq 0}$.
:::


:::{.solution}
Use the following contour:


![[2021-07-29_20-39-31.png]]

Take $g(z) \da 2e^z < f(z) \da f(z) \da z+3$.
:::



:::{.corollary title="Open Mapping"}
Any holomorphic non-constant map is an open map.
:::

\todo[inline]{Prove}

:::{.corollary title="Maximum Modulus" ref="MaximumModulus"}
If $f$ is holomorphic and nonconstant on an open connected region $\Omega$, then $\abs{f}$ can not attain a maximum on $\Omega$.
If $\Omega$ is bounded and $f$ is continuous on $\bar \Omega$, then $\max_{\bar \Omega} \abs{f}$ occurs on $\bd \Omega$.
Conversely, if $f$ attains a local supremum at $z_0 \in \Omega$, then $f$ is constant on $\Omega$.
:::

\todo[inline]{Prove}

:::{.corollary title="?"}
If $f$ is nonzero on $\Omega$, then $f$ attains a minimum on $\bd \Omega$.
This follows from applying the MMP to $1/f$.
:::