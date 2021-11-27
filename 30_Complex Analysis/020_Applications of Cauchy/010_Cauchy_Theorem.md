# Cauchy's Theorem

:::{.definition title="Complex Integral"}
\[
\int_{\gamma} f d z:=\int_{I} f(\gamma(t)) \gamma^{\prime}(t) \dt
= \int_\gamma (u+iv)\dx + (-v+iu)\dy
.\]
:::

:::{.theorem title="Cauchy-Goursat Theorem" ref="CauchyTheorem"}
If $f$ is holomorphic on a region $\Omega$ with $\pi_1 \Omega = 1$, then for any closed path $\gamma \subseteq \Omega$,
\[ 
\int_{\gamma} f(z) \dz = 0
.\]
:::

:::{.slogan}
Closed path integrals of holomorphic functions vanish.
:::
