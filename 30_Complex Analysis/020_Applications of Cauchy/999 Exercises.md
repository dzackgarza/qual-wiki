# Exercises

:::{.exercise title="Primitives imply vanishing integral"}
Show that if $f$ has a primitive $F$ on $\Omega$ then $\displaystyle\int_\gamma f = 0$ for every closed curve $\gamma \subseteq \Omega$.

#completed/exercise

:::

:::{.solution}
Let $F$ be a primitive of $f$, so $\dd{}{z}F = f$.
Then
\[
\int_\gamma f(z) \dz = F(\gamma(1)) - F(\gamma(0)) = F(p) - F(p) = 0
.\]
More explicitly, let $z(t): [a, b]\to \CC$ be any parameterization of $\gamma$, then
\[
\int_\gamma f(z) \dz 
&= \int_a^b f(z(t)) z'(t)\dt \\
&= \int_a^b F'(z(t))z'(t) \dt \\
&= \int_a^b \tilde F'(t)\dt && \text{ where } \tilde F(t) \da F(z(t)) \text{ by the chain rule} \\
&= F(z(b)) - F(z(a)) && \text{ by FTC} \\
&= 0
,\]
since $z(b) = z(a)$ for a closed curve.


:::

:::{.exercise title="Uniform limit theorem for holomorphic functions"}
Show that if $f_n\to f$ locally uniformly and each $f_n$ is holomorphic then $f$ is holomorphic.

#work/exercise

:::

:::{.solution}
This is S&S Theorem 5.2.
Statement: if $f_n\to f$ uniformly locally uniformly on $\Omega$ then $f$ is holomorphic on $\Omega$.

\envlist

- Let $D \subset \Omega$ with $\bar\DD \subset \Omega$ and $\Delta \subset D$ be a triangle.
- Apply Cauchy-Goursat: 
\[
\int_\Delta f_n = 0
.\]
- $f_n\to f$ uniformly on $\Delta$ since it is closed and bounded and thus compact by Heine-Borel, so $f$ is continuous and
\[
\lim_n 0 = \lim_n \int_\Delta f_n = \int_\Delta \lim_n f_n \da \int_\Delta f
.\]
- Apply Morera's theorem: $\displaystyle\int_\Delta f$ vanishes on every triangle in $\Omega$, so $f$ is holomorphic on $\Omega$.

:::

:::{.exercise title="Locally uniform limit theorem for holomorphic functions"}
Prove that if $f_n\to f$ locally uniformly with $f_n$ holomorphic, then $f_n'\to f'$ locally uniformly and $f'$ is holomorphic.

#work/exercise

:::

:::{.solution}
\envlist

- Simplifying step: for some reason, it suffices to assume $f_n\to f$ uniformly on all of $\Omega$?
- Take $\Omega_R$ to be $\Omega$ with a buffer of $R$, so $d(z, \bd \Omega) > R$ for every $z \in \bar{\Omega_R}$.
- It suffices to show the following bound for $F$ any holomorphic function on $\Omega$:
\[
\sup_{z\in \Omega_R} \abs{F'(z)} \leq {1\over R} \sup_{\zeta \in \Omega} \abs{F(\zeta)} && \forall R
,\]
where on the right we take the sup over all $\Omega$.
  - Then take $F \da f_n-f$ and $R\to 0$ to conclude, since the right-hand side is a constant not depending on $\Omega_R$.
- For any $z\in \Omega_R$, we have $\bar{D_R(z)} \subseteq \Omega_R$, so Cauchy's integral formula can be applied:
-
\[
\abs{F'(z)} 
&= \abs{ {1\over 2\pi i} \int_{\bd D_R(z)} {F(\xi) \over (\xi-z)^2 } \dxi  } \\
&\leq {1\over 2\pi} \int_{\bd D_R(z)} { { \abs{F(\xi)} \over \abs{\xi-z}^2 }} \dxi   \\
&\leq {1\over 2\pi} \int_{\bd D_R(z)} { { \sup_{\zeta\in \Omega} \abs{F(\zeta)} \over \abs{\xi-z}^2 }} \dxi   \\
&= {1\over 2\pi} \sup_{\zeta\in \Omega} \abs{F(\zeta)}  \int_{\bd D_R(z)} { { 1 \over R^2 }} \dxi   \\
&= {1\over 2\pi} \sup_{\zeta\in \Omega} \abs{F(\zeta)}  {1\over R^2} \int_{\bd D_R(z)} \dxi   \\
&= {1\over 2\pi} \sup_{\zeta\in \Omega} \abs{F(\zeta)}  {1\over R^2} 2\pi R   \\
&\leq {1\over 2\pi} \sup_{\zeta\in \Omega} \abs{F(\zeta)}  {1\over R^2}\qty{ 2\pi R}   \\
&= {1\over R} \sup_{\zeta \in \Omega}\abs{F(\zeta)}
.\]

- Now
\[
\norm{f_n' - f'}_{\infty, \Omega_R} \leq {1\over R} \norm{f_n - f}_{\infty, \Omega}
,\]
where if $R$ is fixed then by uniform convergence of $f_n\to f$, for $n$ large enough $\norm{f_n - f} < \eps/R$.
:::

:::{.exercise title="Sublinear growth"}
Suppose that $f$ is entire and $f$ has sublinear growth in the following sense:
\[
\abs{f(z)\over z}\to 0
\text{ as } \abs{z}\to \infty
.\]
Show that $f$ must be constant.

#completed/exercise

:::

:::{.solution title="Direct bound"}
Claim: $f'(z_0) = 0$ for every $z_0\in \CC$, so $f'\equiv 0$, making $f$ constant.
Fix $z_0$, then define
\[
g(z) \da 
\begin{cases}
{f(z) - f(0) \over z-0} & z\neq 0 
\\
f'(0) & z=0.
\end{cases}
.\]
Note that for $z\neq 0$,
\[
\abs{g(z)} \da \abs{f(z) - f(0)\over z} \leq \abs{f(z) \over z} + \abs{f(0)\over z} \convergesto{\abs{z} \to \infty }0
,\]
where we've used the assumption in the last step.
So for $\abs{z}\geq R_\eps$ large enough, $\abs{g(z)} < \eps$.
In particular, $\abs{g(z)}<\eps$ on the circle $\abs{z} = R_\eps$, and by the MMP $\abs{g(z)} < \eps$ in the disc $\abs{z}\leq R_\eps$.
Taking $\eps\to 0$ yields $g(z) = 0$ for all $z\in \CC$, so $f(z) = f(0)$ is a constant for all $z$.
:::

:::{.solution title="Cauchy bound"}
Claim: $f'(z) \equiv 0$.
Choose $R = R(\eps) \gg 1$ so that $\abs{f(z)} \leq \eps \abs{z}$ for $\abs{z} \geq R$, and apply Cauchy's formula:
\[
\abs{f'(z)} 
&= \abs{{1\over 2\pi i } \int_{\abs \xi = R} { f(\xi) \over (\xi - z)^2 }\dxi  } \\
&\leq {1\over 2\pi} \int_{\abs \xi = R} { \abs{ f(\xi) } \over \abs{\xi - z}^2 } \dxi  \\
&\leq {1\over 2\pi} \int_{\abs \xi = R} { \eps \abs{\xi} \over \qty{R - \abs{z}^2 } } \dxi  \\
&= {1\over 2\pi} \qty{\eps R\over \qty{R-\abs{z}}^2 } \cdot 2\pi R \\
&= \bigo\qty{\eps R^2\over R^2} = \bigo(\eps) \\
&\convergesto{\eps\to 0} 0
.\]

:::

:::{.exercise title="Polynomial growth"}
Suppose that $f$ is entire and has polynomial growth in the following sense:
\[
\abs{f(z)\over z^n} \leq M \text{ for }\abs{z} \geq R
,\]
for some constants $k$ and $R$.
Show that $f$ is a polynomial of degree at most $n$.

#completed/exercise

:::

:::{.solution}
Since $f$ is entire, it equals its Laurent expansion about $z_0 = 0$, so
\[
f(z) = \sum_{k\geq 0} c_k z^k, && c_k = {f^{(k)}(0)\over k! } = {1\over 2\pi i}\int_{\abs{\xi} = R} {f(\xi) \over \xi^{k+1}}\dxi
.\]
A direct estimate yields
\[
\abs{c_k} 
&\leq {1\over 2\pi} \int_{\abs{\xi} = R} {\abs{f(\xi)} \over \abs{\xi}^{k+1} }\dxi\\
&\leq {1\over 2\pi} \int_{\abs{\xi} = R} {M \abs{\xi}^n \over \abs{\xi}^{k+1} }\dxi \\
&\leq {M\over 2\pi} \int_{\abs{\xi} = R} \abs{\xi}^{n-(k+1)} \dxi \\
&\leq {M\over 2\pi} \int_{\abs{\xi} = R} R^{n-(k+1)} \dxi \\
&= {M\over 2\pi} R^{n-k-1} \cdot 2\pi R \\
&= MR^{n-k}
,\]
which converges to $0$ as $R\to \infty$ provided $n-k<0$, i.e. $k>n$.
:::

