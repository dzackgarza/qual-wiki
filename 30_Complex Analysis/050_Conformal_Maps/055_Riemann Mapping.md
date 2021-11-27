# Riemann Mapping

:::{.slogan}
If $\Omega \subseteq \CC$ with $\pi_1 \Omega = 1$ then $\Omega$ is biholomorphic to $\DD$.
:::

:::{.theorem title="Riemann Mapping"}
If $\Omega$ is simply connected, nonempty, and not $\CC$, then for every $z_{0}\in \Omega$ there exists a unique conformal map $F:\Omega \to \DD$ such that $F(z_{0}) = 0$ and $F'(z_{0}) > 0$.

Thus any two such sets $\Omega_{1}, \Omega_{2}$ are conformally equivalent.
:::

:::{.proof title="Sketch"}
\envlist

- Fix some $z_0\in \Omega$ and set $\mcf = \ts{f\in \Hol(\Omega, \DD) \st f(z_0) = 0, f \text{ injective }}$.
  A lemma will show $\mcf$ is nonempty.

- Define the hyperbolic translations and compute
\[
h_w(z) &\da {z-w \over 1-\bar{w} z} \in \Hol(\DD)
h'_w(0) &= 1 - \ab{w}^2 \\
h'_w(w) &= {1\over 1 - \abs{w}^2}
.\]

- Show that if $f\in \mcf$ is not surjective, one can find another member with a larger derivative of $z_0$, say $g$ with $\abs{g'(z_0)} > \abs{f'(z_0)}$.

- Show that $\mcf$ is uniformly bounded and thus normal by Montel.
- Define $m\da \sup_{f\in \mcf} \abs{f'(z_0)}$, noting that $0<m<\infty$ since the maps are conformal and the Cauchy estimate supplies an upper bound:
\[
\abs{f'(z_0)} \leq \max_{\abs{z-z_0} = R} { \abs{f(z)} \over R} \leq {1\over R}
.\]

- Produce a sequence $\tilde \mcf = \ts{f_k}$ such that $\abs{f_k'(z_0)} \convergesto{k\to\infty} m$.
- Apply Montel to $\tilde \mcf$ which are uniformly bounded by 1 to extract a subsequence that converges locally uniformly to some $h$.
- Show $h\in \mcf$ by showing $h(z_0) = 0$, is analytic, and non-constant.
  Apply Hurwitz's theorem to conclude $h$ is injective as a uniform limit of injective functions.
- Show $h$ is surjective by showing $\abs{h'(z_0)} \geq \abs{g'(z_0)}$ (contrapositive to earlier step).


:::

