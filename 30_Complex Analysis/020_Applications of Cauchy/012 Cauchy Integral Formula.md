# Cauchy's Integral Formula

> See [reference](http://home.iitk.ac.in/~psraj/mth102/lecture_notes/comp8.pdf)

:::{.theorem title="Cauchy Integral Formula" ref="CauchyIntegral"}
Suppose $f$ is holomorphic on $\Omega$, then for any $z_0 \in \Omega$ and any open disc $\closure{D_R(z_0)}$ such that $\gamma \da \bd \closure{D_R(z_0)} \subseteq \Omega$,
\[
f(z_0) = {1 \over 2\pi i} \int_{\gamma} {f(\xi) \over \xi-z_0}\ \dxi
\]
and
\[
\dd{^nf }{z^n}(z_0) = {n! \over 2\pi i} \int_{\gamma} {f(\xi) \over (\xi - z_0)^{n+1}} \dxi
.\]
:::

:::{.proof title="?"}
![[image_2021-05-27-16-54-06.png]]
:::

:::{.proof title="?"}
![[image_2021-05-27-16-56-39.png]]
![[image_2021-05-27-16-56-52.png]]
:::

