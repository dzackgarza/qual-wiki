---
order: 70
---

# Morera

## Tie's Extra Questions: Fall 2009 #work/exercise
Let $f(z)$ be analytic in an open set $\Omega$ except possibly at a
point $z_0$ inside $\Omega$. Show that if $f(z)$ is bounded in near
$z_0$, then $\displaystyle \int_\Delta f(z) dz = 0$ for all triangles
$\Delta$ in $\Omega$.

## #work/exercise
Let $f(z)$ be analytic in an open set $\Omega$ except possibly at a point $z_0$ inside $\Omega$. 

Show that if $f(z)$ is bounded in near $z_0$, then $\displaystyle \int_\Delta f(z) dz = 0$ for all triangles $\Delta$ in $\Omega$.

### Tie's Extra Questions: Fall 2011


Let $f(z)$ be analytic in an open set $\Omega$ except possibly at a
point $z_0$ inside $\Omega$. Show that if $f(z)$ is bounded in near
$z_0$, then $\displaystyle \int_\Delta f(z) dz = 0$ for all triangles
$\Delta$ in $\Omega$.

## Fall 2021.2  #complex/completed/qual

^a550c1

:::{.problem title="?"}
Let $\gamma(t)$ be a piecewise smooth curve in $\mathbb{C}, t \in[0,1]$. Let $F(w)$ be a continuous function on $\gamma$. Show that $f(z)$ defined by
\[
f(z):=\int_{\gamma} \frac{F(w)}{w-z} d w
\]
is analytic on the complement of the curve $\gamma$.

:::

:::{.solution}
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


