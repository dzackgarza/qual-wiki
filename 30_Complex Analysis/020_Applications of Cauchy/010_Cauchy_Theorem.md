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

:::{.proof title="of Cauchy"}
Apply Stokes':
\[
\oint_{\partial D} f(z) d z=\int_{D} d(f(z) d z)=\int_{D}\left(\frac{\partial f}{\partial z} d z+\frac{\partial f}{\partial \bar{z}} d \bar{z}\right) \wedge d z=\int_{D} \frac{\partial f}{\partial z} d z \wedge d z+0 d \bar{z} \wedge d z=0
.\]


:::

