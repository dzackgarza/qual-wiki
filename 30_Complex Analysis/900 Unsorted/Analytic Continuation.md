# Analytic Continuation


:::{.theorem title="Identity principle"}
If $f(z)$ and $g(z)$ are analytic on a domain $\Omega$, and if $f(z)=g(z)$ for $z$ belonging to a set that has a nonisolated point, then $f(z)=g(z)$ for all $z \in \Omega$.

More generally, if $\Omega$ is a domain with a nonisolated point, $F(z, w): \Omega\cartpower{2}\to \CC$ is holomorphic in both variables, and $F(z, w) \equiv 0$ on $\Omega$, then $F(z, w) \equiv 0$ on any domain $\Omega' \contains \Omega$. 
:::


:::{.example title="?"}
Since $\sin^2(z)+\cos^2(z) = 1$ for $z\in \RR$, which has a limit point, this holds for $z\in \CC$ as well.
For the generalization, consider $F(z, w) \da e^{z+w}-e^z e^w$; then $F\equiv 0$ on $\RR$ and thus this holds on $\CC$.
:::


