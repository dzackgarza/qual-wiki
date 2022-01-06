---
order: 70
title: "Morera's Theorem"
status: completed
---

# Morera 

## Uniform limit theorem #complex/exercise/completed

:::{.problem title="?"}
Suppose $\theset{f_n}_{n\in \NN}$ is a sequence of analytic functions on $\DD \definedas \theset{z\in \CC \suchthat \abs{z} < 1}$.

Show that if $f_n\to g$ for some $g: \DD \to \CC$ uniformly on every compact $K\subset \DD$, then $g$ is analytic on $\DD$.


:::

:::{.solution}
By Morera's theorem, it suffices to show $\int_T f = 0$ for all triangles $T \subseteq \DD$.
Noting that $T$ is closed and bounded and thus compact, $f_n\to g$ uniformly on $T$.
Since the $f_n$ are holomorphic, $\int_T f_n = 0$ for all $n$, and thus
\[
\int_T g = \int_T \lim f_n = \lim_n \int_T f_n = \lim_n 0 = 0
,\]
where moving the limit through the integral is justified by uniform convergence.
:::

## Fourier transforms are entire #complex/exercise/completed

:::{.problem title="?"}
Suppose that $f: \RR\to\RR$ is a continuous function that vanishes outside of some finite interval.
For each $z\in \CC$, define
\[
g(z) = \int_{-\infty}^\infty f(t) e^{-izt} \,dt
.\]

Show that $g$ is entire.

:::

:::{.solution}
By Fubini:
\[
\oint_T g(z)\dz 
&\da \oint_T \int_\RR f(t)e^{-izt} \dt\dz \\
&\da \int_\RR \oint_T f(t)e^{-izt} \dz\dt \\
&\da \int_\RR f(t) \qty{ \oint_T e^{-izt} \dz } \dt \\
&\da \int_\RR f(t) \cdot 0 \dt \\
&= 0
,\]
where the inner integral vanishes because $z\mapsto e^{-izt}$ is entire by Goursat's theorem.
So $g$ is entire by Morera.
:::






## Tie's Extra Questions: Fall 2009, Fall 2011 #complex/exercise/completed

:::{.problem title="?"}
Let $f(z)$ be analytic in an open set $\Omega$ except possibly at a
point $z_0$ inside $\Omega$. Show that if $f(z)$ is bounded in near
$z_0$, then $\displaystyle \int_\Delta f(z) dz = 0$ for all triangles
$\Delta$ in $\Omega$.
:::

:::{.solution}
Write $\DD_\eps(z_0)$ for a disc in which $f$ is bounded, say by $\abs{f}\leq M$ here.
Note that if $z_0$ is not in the region enclosed by $\Delta$, then $\int_\Delta f = 0$ since $f$ is holomorphic throughout $\Delta$, so suppose $z_0$ is in this region.

Since $f$ is holomorphic in $\Omega\smts{z_0}$, $\Delta$ can be deformed to $\bd \DD_\eps(z_0)$ without changing the integral. 
So
\[
\abs{ \oint_\Delta f } 
&= \abs{\oint_{\bd\DD_\eps(z_0)} f } \\
&\leq \oint_{\bd \DD_\eps(z_0)} \abs{f} \\
&\leq \oint_{\bd \DD_\eps(z_0)} M \\
&= M\cdot 2\pi \eps \\
&\convergesto{\eps\to 0} 0
,\]
noting that the bound $M$ is constant and remains an upper bound on smaller discs by the maximum modulus principle.
:::

## Fall 2021.2  #complex/qual/completed

^a550c1

:::{.problem title="?"}
Let $\gamma(t)$ be a piecewise smooth curve in $\mathbb{C}, t \in[0,1]$. Let $F(w)$ be a continuous function on $\gamma$. Show that $f(z)$ defined by
\[
f(z):=\int_{\gamma} \frac{F(w)}{w-z} d w
\]
is analytic on the complement of the curve $\gamma$.

:::

:::{.solution title="Using Morera"}
By Morera's theorem, it suffices to show $\int_\Delta f(z) \dz = 0$ for all triangles $\Delta \subseteq \gamma^c$.
Claim:
\[
\int_\Delta f(z) \dz 
&= \int_\Delta \int_\gamma {F(w) \over w-z} \dw \dz \\
&= \int_\gamma \int_\Delta {F(w) \over w-z} \dz \dw \\
&= \int_\gamma F(w) \qty{ \int_\Delta {1 \over w-z} \dz} \dw \\
&= \int_\gamma F(w) \cdot 0 \dw \\
&= 0
.\]

That the inner integral is zero follows from the fact that the function $z\mapsto {1\over w-z}$ is holomorphic on $\gamma^c$, since it has only a simple pole at $w$ where $w\in \gamma$ is fixed.

That the interchange of integrals is justified follows from Fubini's theorem: these are continuous functions on compact sets, which are uniformly bounded and thus Lebesgue measurable and integrable.

:::


:::{.solution title="Using limit definition"}
The claim is that $f$ is complex differentiable, thus smooth, thus holomorphic and equal to its Taylor series expansion.
The quick justification:
\[
\dd{}{z} f(z)
&= \dd{}{z} \int_\gamma {F(w) \over w-z}\dw \\
&= \int_\gamma \dd{}{z} {F(w) \over w-z} \dw \\
&= \int_\gamma {F(w) \over (w-z)^2} \dw
,\]
where differentiating through the integral is justified since the integrand is a continuous function of $z$ on $\gamma$ since $w\neq z$ on $\gamma$, and $\gamma$ is a compact set.

Slightly more rigorously, one can equivalently pass a limit through the integral to show that the defining limit exists:
\[
f(z+h) - f(z)
&= \int_\gamma {F(w) \over w+h-z} \dw - \int_\gamma {F(w) \over w-z}\dw \\
&= \int_\gamma {(w-z)F(w) - (w+h-z)F(w) \over (w+h-z)(w-z) } \dw \\
&= \int_\gamma F(w) {h \over (w+h-z)(w-z)} \dw \\
&\convergesto{h\to 0} \int_\gamma {F(w) \over (w-z)^2}\dw
,\]
since the term involving $h$ goes to 1.


:::



## Spring 2020 HW 2, SS 2.6.6 #complex/exercise/completed

:::{.problem title="?"}
Suppose that $f$ is holomorphic on a punctured open set $\Omega\setminus\theset{w_0}$ and let $T\subset \Omega$ be a triangle containing $w_0$.
Prove that if $f$ is bounded near $w_0$, then $\int_T f(z) ~dz = 0$.
:::

:::{.solution}
Without loss of generality assume $w_0 = 0$.
If $\abs{f(z)} \leq M$ for $\abs{z} < \eps$, pick $T$ contained in $\DD_\eps$, then
\[
\abs{\oint_T f(z)\dz } \leq \oint_T \abs{f(z)}\dz \leq \oint_T M \dz = M \mu(T)
,\]
and by homotopy invariance, this integral doesn't change as $T$ is perturbed.
Shrinking $T$, we can make $\mu(T)\to 0$.
:::

