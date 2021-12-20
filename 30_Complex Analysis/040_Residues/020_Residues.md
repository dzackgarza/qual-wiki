# Residues

See:

- <https://www.damtp.cam.ac.uk/user/reh10/lectures/nst-mmii-chapter5.pdf>

:::{.remark}
Pedantic warning: $\Res_{z=p}(f)$ should really be $\Res_{z=p}(df)$ for $df = f(z) \dz$, since it's only an invariant of the 1-form $df$ and not necessarily $f$ itself.
We freely abuse notation!
:::

## Basics

:::{.remark}
Check: do you need residues at all??
You may be able to just compute an integral!

- Check to see if the integrand is holomorphic in the interior first, in which case the integral just vanishes.
  - If you have an integral of the form $\int {f(z) \over (z-a)^n}\dz$, apply Cauchy.

- Directly by parameterization:
\[
\int_\gamma f \dz = \int_a^b f(z(t))\, z'(t) \dt && \text{for } z(t) \text{ a parameterization of } \gamma
,\]

- Finding a primitive $F$, then 
\[
\int_\gamma f = F(b) - F(a)
.\]

  - Note: you can parameterize a circle around $z_0$ using
  \[
  z= z_0 + re^{i \theta }
  .\]

:::

:::{.fact title="Integrating $z^k$ around $S^1$ is the source of residue theory"}
The major fact that reduces integrals to residues:

\[
\int_\gamma z^k \dz = \int_0^{2\pi} e^{ik\theta} ie^{i\theta } \dtheta = i\int_0^{2\pi} e^{i(k+1)\theta \dtheta }
= \begin{cases}
2\pi i & k=-1 
\\
0 & \text{else}.
\end{cases}
\]

Thus
\[
\int \sum_{k\geq -M} c_k z^k = \sum_{k\geq -M} \int c_k z^k = 2\pi i c_{-1}
,\]
i.e. the integral picks out the $c_{-1}$ coefficient in a Laurent series expansion.

:::

:::{.exercise title="?"}
Compute $\int_\gamma {1\over z^2 - 1} \dz$ for $\gamma$ a circle of radius 1 about $z=1$.
Also compute this integral for $\gamma$ a circle of radius 2 about $z=0$.

#completed

:::

:::{.solution}
For the first integral:
\[
\int_\gamma{1\over z^2-1}\dz = {1\over 2}\int_\gamma {1\over z-1} + {1\over z+1}\dz = {1\over 2}\int_\gamma {1\over z-1} = {1\over 2}\cdot 2\pi i \Res_{z=1}f(z) = \pi i
\]
using that $f(z) = {1\over z-1}$ is already an expansion of $f$ about $z=1$ since it is a Laurent series in $(z-1)^k$, so the residue is $1$.

For the second integral:
attempt to define a primitive
\[
F(z) \da {1\over 2}\log\qty{z-1\over z+1} \implies F'(z) = {1\over z^2-1}
.\]
If this primitive is well-defined on $\gamma$, the integral will vanish because this is a closed curve.
Choose the branch cut $\CC\sm(-\infty, 0]$ and define $g(z) = {z-1\over z+1}$, so that $F(z) = {1\over 2}\log(g(z))$.
Then then $g(z)\in (-\infty, 0] \iff z\in [-1, 1]$ and $[-1, 1] \intersect \gamma = \emptyset$.
:::

:::{.exercise title="?"}
Compute
\[
\int_{S^1} {2 \sinh(z) \over z^n}\dz
.\]


#completed

:::

:::{.solution}
Write $f(z) = 2\sinh(z) = e^{z} - e^{-z}$ and apply the generalized Cauchy formula:
\[
f^{(n-1)}(0) = {(n-1)! \over 2\pi i} \int_{S^1} {f(z) \over z^n}\dz \\
\implies \int_{S^1}{f(z)\over z^n}\dz 
= {2\pi i f^{(n-1)(0)} \over (n-1)!}
= {2\pi i \qty{e^{z} + (-1)^n e^{-z}} \over (n-1)!}
.\]

:::

:::{.exercise title="?"}
Compute
\[
\int_\gamma {z^2+1 \over z(z^2 + 4)}\dz
\]
for 

- A circle of radius $1$,
- A circle of radius $2+\eps$,

#completed

:::

:::{.solution}
Notice this can be written as $f(z)/z$ where $f(z) = {z^2+1\over z^2+4}$ is holomorphic on $\DD$, so this yields $2\pi i f(0) = {i\pi \over 2}$.

For the larger circle, use PFD:
\[
\int_\gamma f(z) \dz = \int_\gamma {1/4\over z} + {3/8\over z+2i} + {3/8 \over z-2i}\dz = 2\pi i\qty{ {1\over 4} + {3\over 8} + {3\over 8}}
.\]

:::

## Residue Formulas

:::{.theorem title="The Residue Theorem"}
Let $f$ be meromorphic on a region $\Omega$ with poles \( \ts{ \elts{z}{N} } \).
Then for any $\gamma \in \Omega\sm \ts{ \elts{z}{N} }$, 
\[
{1 \over 2\pi i } \int_\gamma f(z) \dz = \sum_{j=1}^N n_\gamma(z_j) \Res_{z=z_j} f
.\]
If $\gamma$ is a toy contour, then  
\[
{1\over 2\pi i}\int_\gamma f\dz = \sum_{j=1}^N \Res_{z=z_j}f
.\]

:::

:::{.proposition title="Residues from partial fraction decomposition"}
Every rational function $f(z) \da p(z)/q(z)$ can be expressed as 
\[
f(z) = P_{\infty}(z) + \sum_{1\leq j \leq m} P_j(z)
,\]
where $P_\infty(z)$ is a polynomial in $z$ and the $P_j$ are the principal parts of $f$ at its poles $\ts{z_1, \cdots, z_j}$.
For example:

![](figures/2021-12-10_18-44-20.png)

:::

:::{.proposition title="Residue formula for higher order poles"}
If $f$ has a pole $z_0$ of order $n$, then
\[  
\Res_{z=z_0} f = \lim_{z\to z_0} {1 \over (n-1)!} \qty{\dd{}{z}}^{n-1} (z-z_0)^n f(z)
.\]
:::

:::{.proposition title="Residue formula for simple poles"}
As a special case, if $z_0$ is a simple pole of $f$, then
\[  
\Res_{z=z_0}f = \lim_{z\to z_0} (z-z_0) f(z)
.\]
:::

:::{.corollary title="Better derivative formula that sometimes works for simple poles"}


If additionally $f=g/h$ where $h(z_0) = 0$ and $h'(z_0)\neq 0$, 
\[
\Res_{z=z_0} {g(z) \over h(z)} = {g(z_0) \over h'(z_0)}
.\]

Note that if $f(z) = 1/h(z)$ and $z_0$ is a simple pole, this reduces to
\[
\Res_{z=z_0}{1\over h(z)} = {1\over h'(z_0)}
.\]

:::

:::{.proof title="Of derivative formula for simple poles"}
Apply L'Hopital:
\[
(z-z_0) {g(z) \over h(z)} = {(z-z_0) g(z) \over h(z) } \equalsbecause{LH}
{g(z) + (z-z_0) g'(z) \over h'(z)} \converges{z\to z_0}\too {g(z_0) \over h'(z_0)}
.\]
:::

:::{.example title="?"}
Let $f(z) \da {1\over x^n + 1}$, then factor $z^n+1 = \prod_{k=1}^n (z-\zeta_m^k)$ where $m\da 2n$, and apply the formula:
\[
\Res_{z=\zeta_{m}} {1\over z^n + 1} = {1 \over nz^{n-1}}\evalfrom_{z=\zeta_m} = {1\over n\zeta_m^{n-1}}
= {\zeta_m^{1-n}\over n}
= -{\zeta_m \over n}
,\]
which follows from expanding $\zeta_m^{1-n} = e^{2\pi i (1-n) \over m}$.

:::

:::{.example title="Residue of a simple pole (order 1)"}
Let $f(z) = \frac{1}{1+z^2}$, then $g(z) = 1, h(z) = 1+z^2$, and $h'(z) = 2z$ so that $h'(i) = 2i \neq 0$. Thus
\[
\Res_{z=i}{1\over 1+z^2} = \frac{1}{2i}
.\]
:::

:::{.proposition title="Residue at infinity"}

\[
\Res_{z=\infty}f(z) = \Res_{z=0} g(z) && g(z) \da -{1 \over z^2}f\qty{1\over z} 
.\]

:::

:::{.proposition title="Fractional Residue Formula"}

![](figures/2021-12-10_18-27-31.png)

:::

## Estimates

:::{.remark}
Note that
\[
a\geq b \implies e^{-a} \leq e^{-b}
.\]

:::

:::{.proposition title="Length bound / ML Estimate"}
\[
\abs{ \int_\gamma f} \leq ML \da \sup_{z\in \gamma} \abs{f} \cdot \mathrm{length}(\gamma)
.\]
:::

:::{.proof title="?"}
\[
\left|\int_{\gamma} f(z) d z\right| \leq \sup _{t \in[a, b]}|f(z(t))| \int_{a}^{b}\left|z^{\prime}(t)\right| d t \leq \sup _{z \in \gamma}|f(z)| \cdot \operatorname{length}(\gamma)
.\]

:::

:::{.example title="of estimating a sup"}
Consider
\[
f(z) \da {e^{iz} \over 1 + z^2}
\]

where $z\neq \pm i$, and attempt to integrate
\[
\int_\RR f(z) \dz
.\]

Use a semicircular contour $\gamma_R$ where $z = Re^{it}$
and check
\[
\sup_{z\in \gamma_R} \abs{f(z)} 
&= \max_{t\in [0, \pi]} {1 \over 1 + (Re^{it})^2 } \\
&= \max_{t\in [0, \pi]} {1 \over 1 + R^2e^{2it} } \\
&= {1\over R^2 - 1}
.\]

:::

:::{.proposition title="Jordan's Lemma"}
Suppose that $f(z) = e^{iaz}g(z)$ for some $g$, and let $C_R \da \ts{ z=Re^{it} \st t\in [0, \pi] }$. Then
\[
\abs{\int_{C_R} f(z) \dz} \leq {\pi M_R \over a}
\]
where $M_R \da \sup_{t\in [0, \pi]} \abs{g(Re^{it})}$.
:::

:::{.example title="of how to apply Jordan's lemma"}
Show that
\[
\int_\RR {\sin(x) \over x} \dx = \pi
.\]
For a contour, take the indented half-disc, and set $f(z) = e^{iz}/z$:

- For the innermost disc, use the fractional residue formula to get $-\pi i$ since $\Res_{z=0}f(z) = 1$
- For the arc $\Gamma_R$, apply Jordan:
\[
\abs{\int_{\Gamma_R} f(z) \dz } \leq {1\over R} \int_{\Gamma_R} \abs{e^{iz}} \dz < {\pi \over R} \convergesto{R\to\infty} 0
.\]



:::

:::{.proof title="?"}
\[
\abs{ \int_{C_R} f(z)\dz }
&= \abs{ \int_{C_R} e^{iaz}g(z) \dz} \\
&= \abs{ \int_{[0, \pi]} e^{ia\qty{Re^{it}}}g(Re^{it}) iRe^{it} \dt} \\
&\leq \int_{[0, \pi]} \abs{ e^{ia\qty{Re^{it}}}g(Re^{it}) iRe^{it}} \dt \\
&=R \int_{[0, \pi]} \abs{ e^{ia\qty{Re^{it}}}g(Re^{it})} \dt \\
&\leq R M_R \int_{[0, \pi]} \abs{ e^{ia\qty{Re^{it}}}} \dt \\
&= R M_R \int_{[0, \pi]} e^{\Re\qty{iaRe^{it}}}   \dt \\
&= R M_R \int_{[0, \pi]} e^{\Re\qty{iaR\qty{\cos(t) + i\sin(t) } }}   \dt \\
&= R M_R \int_{[0, \pi]} e^{-aR\sin(t) }   \dt \\
&= 2 R M_R \int_{[0, \pi/2]} e^{-aR\sin(t) }   \dt \\
&\leq 2R M_R \int_{[0, \pi/2]} e^{-aR\qty{2t\over \pi} }   \dt \\
&= 2RM_R \qty{\pi \over 2aR}\qty{1-e^{-aR}} \\
&= {\pi M_R \over a}
.\]

where we've used that on $[0, \pi/2]$, there is an inequality $2t/\pi \leq \sin(t)$.
This is obvious from a picture, since $\sin(t)$ is a height on $S^1$ and $2t/\pi$ is a height on a diagonal line:

![figures/image_2021-06-09-01-29-22.png](figures/image_2021-06-09-01-29-22.png)

:::
