# Cauchy's Integral Formula

> See [reference](http://home.iitk.ac.in/~psraj/mth102/lecture_notes/comp8.pdf)

:::{.theorem title="Cauchy Integral Formula" ref="CauchyIntegral"}
Suppose $f$ is holomorphic on $\Omega$, then for any $z_0 \in \Omega$ and any open disc $\closure{D_R(z_0)}$ such that $\gamma \da \bd \closure{D_R(z_0)} \subseteq \Omega$,
\[
f(z_0) = {1 \over 2\pi i} \int_{\gamma} {f(\xi) \over \xi-z_0}\ \dxi
\]
and
\[
f^{(n)}(z_0) = {n! \over 2\pi i} \int_{\gamma} {f(\xi) \over (\xi - z_0)^{n+1}} \dxi
.\]
As a consequence, if $f(z) \sum_{k\geq 0} c_k (z-z_0)^k$,
\[
c_k = {f^{(n)}(z_0) \over n!} = {1\over 2\pi i} \int_\gamma { f(\xi) \over (\xi - z_0)^{n+1} } \dxi
.\]
:::

:::{.proof title="?"}

![figures/image_2021-05-27-16-54-06.png](figures/image_2021-05-27-16-54-06.png)

:::

:::{.proof title="?"}

![figures/image_2021-05-27-16-56-39.png](figures/image_2021-05-27-16-56-39.png)

![figures/image_2021-05-27-16-56-52.png](figures/image_2021-05-27-16-56-52.png)

:::

:::{.proof title="Alternative"}

![](figures/2021-12-14_16-49-17.png)

![](figures/2021-12-14_16-49-36.png)

:::

## Exercises

:::{.exercise title="Integral computation"}
Compute
\[
\int_{\bd\DD} {e^z\over z^2}\dz
.\]

#complex/exercise/completed

:::

:::{.solution}
By Cauchy's formula,
\[
\int {f(z) \over (z-0)^2}\dz = 2\pi i f^{(1)}(0) = 2\pi i
.\]
:::

:::{.exercise title="Integral computation"}
Without using the residue formula, compute
\[
\int_\RR f(x) \dx && f(x) \da {1\over x^4 + 16}
.\]

#complex/exercise/completed

:::

:::{.solution}
Use a semicircular contour, noting the poles are at $\pm \sqrt 2 \pm i\sqrt 2$. 
Write

- $f_1(z) \da (\sqrt 2 + i\sqrt 2)f(z)$
- $f_2(z) \da (-\sqrt 2 + i\sqrt 2) f(z)$.

Break the curve up into two integrals $I_1, I_2$ enclosing the poles, by Cauchy one gets

- For the loop around the right pole: $I_1 = 2\pi i f_1(\sqrt 2 + i\sqrt 2) = {\pi \sqrt{2}(1-i) \over 32}$
- For the loop around the left pole: $I_2 = 2\pi i f_2(\sqrt 2 - i\sqrt 2) = {\pi \sqrt 2(1+i) \over 32}$.

Now show that $\int_{C_R}$ vanishes: parameterize as $\gamma(t) = Re^{it}$ and use the reverse triangle inequality:
\[
\abs{ \int_{C_R} f} \leq  \int_0^\pi {1\over R^4 - 16} = {\pi R \over R^4-16}\to 0
.\]

:::

:::{.exercise title="Equality of different integrals"}
Suppose $f$ is holomorphic on $\Omega$, a simply connected region, and suppose $\gamma \subseteq \Omega$.
Using the Cauchy integral formula, show that
\[
\int_\gamma {f'(z) \over z-a}\dz = \int_\gamma {f(z) \over (z-a)^2 }\dz
.\]
Also prove this when $\Omega$ is *not* simply connected.

#complex/exercise/completed

:::

:::{.solution}
Use the integral formula directly:
\[
\int_\gamma {f'(z) \over z-a}\dz = 2\pi i f'(a)
.\]

On the other hand, use Cauchy's formula for derivatives:
\[
\int_\gamma {f(z) \over (z-a)^2}\dz = 2\pi i f^{(1)}(a)
,\]
and these values are equal.

If $\Omega$ is not simply connected, note that by the quotient rule
\[
\dd{}{z} {f(z) \over z-a} = {f'(z)\over z-a} - {f(z) \over (z-a)^2}
.\]

Thus
\[
\int_\gamma {f'(z) \over z-a} - \int_\gamma {f(z) \over (z-a)^2}\dz 
&= \int_\gamma \qty{ {f'(z) \over z-a} - {f(z) \over (z-a)^2} }\dz \\
&= \int_\gamma \dd{}{z} {f(z) \over z-a} \dz \\
&= G(\gamma(1)) - G(\gamma(0)) \\
&= G(p) - G(p) \\
&= 0
,\]
where $G(z) \da {f(z) \over z-a}$ is a primitive for the integrand by definition.



:::

:::{.exercise title="Evaluating integrals"}
Evaluate the following integrals using Cauchy's integral formula:

\[
\int_{S^1} {\cos(z) \over z} \dz&\\
\int_{S^1} {\sin(z) \over z}\dz&\\
\int_{\abs z = 2} {z^2\over z-1} \dz &\\
\int_{S^1} {e^z \over z^2} \dz &\\
\int_{\abs z = 2} {z^2 - 1 \over z^2 + 1}\dz &\\
\int_{\abs z = 2} {1\over z^2 + z + 1}\dz &
.\]


#complex/exercise/completed

:::

:::{.solution}
\[
\int_{S^1} {\cos(z) \over z} \dz
&= 2\pi i \cos(0) \\
&= 2\pi i \\ \\
\int_{S^1} {\sin(z) \over z}\dz
&= 2\pi i \sin(0) \\
&= 0 \\ \\
\int_{\abs z = 2} {z^2\over z-1} \dz 
&= 2\pi i z^2\evalfrom_{z=1} \\
&= 2\pi i \\ \\
\int_{S^1} {e^z \over z^2} \dz 
&= 2\pi i \dd{}{z} e^z\evalfrom_{z=0} \\
&= 2\pi i \\ \\
\int_{\abs z = 2} {z^2 - 1 \over z^2 + 1}\dz 
&= \int_{\DD + i} {(z^2 -1)/(z+i) \over z-i}\dz + \int_{\DD - i} {(z^2-1)/(z-i) \over z+i} \dz \\
&= 2\pi i \qty{z^2-1\over z+i}\evalfrom_{z=i} + 2\pi i \qty{z^2-1 \over z-i}\evalfrom_{z=-i} \\
&= 2\pi i \qty{-2\over 2i} + 2\pi i \qty{-2\over -2i} \\
&= 0 \\ \\
\int_{\abs z = 2} {1\over z^2 + z + 1}\dz 
&= \int {1\over (z-\zeta_3) (z- \bar{\zeta_3} )} \dz \\
&= \int_{\DD + \bar{ \zeta_3} } {1/(z-\zeta_3) \over (z- \bar{\zeta_3} )} \dz + \int_{\DD + {\zeta_3} } {1/(z- \bar{ \zeta_3} ) \over (z- {\zeta_3} )} \dz \\
&= 2\pi i \qty{1\over z-\zeta_3}\evalfrom_{z=\bar{\zeta_3}} + 2\pi i \qty{1\over z-\bar{\zeta_3}}\evalfrom_{z=\zeta_3} \\
&= 2\pi i \qty{ {1\over \bar{\zeta_3} - \zeta_3 } + {1\over \zeta_3 - \bar{\zeta_3}} }\\
&= 2\pi i \qty{ {1\over \bar{\zeta_3} - \zeta_3 } - {1\over \bar{\zeta_3} - {\zeta_3}} } \\
&= 0
,\]
where for the last we note that $\zeta_3 = e^{2\pi i \over 3} = -1 + i\sqrt 3$ and $\zeta_3 \bar{\zeta_3} = 2\Re(\zeta_3) = 2\cdot {1\over 2} = 1$, yielding the factorization of the denominator.

:::



