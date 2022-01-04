# Argument Principle

### Spring 2020 HW 3.12 (Root counting with argument principle) #complex/exercise/completed

:::{.problem title="?"}
Prove that $f(z) = z^4 + 2z^3 -2z + 10$ has exactly one root in each open
quadrant.
:::

:::{.solution}
It suffices to show there's only one root in the open quadrant $Q_1$, since they come in conjugate pairs.
Assume that there are no roots on $\RR$ or $i\RR$.
Since polynomials are entire, the argument principle can be used to count zeros:
\[
Z_f = {1\over 2\pi i}\int_\gamma \logd f(z)\dz = \Delta_\gamma \Arg(f)
.\]
To take the curve $\gamma$ comprised of

- $\gamma_1 = [0, R]$,
- $\gamma_2 = Re^{it}$ for $t\in [0, \pi/2]$
- $\gamma_3 = i[0, R]$.

Then

- $\Delta_{\gamma_1}\Arg(f) = 0$, since $f(\RR_{\geq 0}) \subseteq \RR_{\geq 0}$.
- $\Delta_{\gamma_2}\Arg(f) = 4\cdot {\pi\over 2} = 2\pi$ since $f\sim z^4$ for large $R$.
- $\Delta_{\gamma_3}\Arg(f)$: consider
\[
f(it) = t^4 - it^3 -2it + 10 = t^4\qty{1 - it\inv -2it^{-2} +10t^{-4}} \\
\implies \Arg(f(it)) \sim \Arg(t^4) =0
.\]

So $\Delta_\gamma \Arg(f) = 1$, meaning there is one zero enclosed by $\gamma$ for $R$ large enough.
As $R\to \infty$, this covers $Q_1$.
:::
