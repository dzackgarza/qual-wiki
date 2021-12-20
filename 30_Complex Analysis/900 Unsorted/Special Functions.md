# Special Functions

## The Gamma Function

:::{.definition title="Gamma function"}
\[
\Gamma(z) = \int_0^\infty t^{z-1}e^{-t} \dt
.\]
:::

:::{.remark}
Some interesting properties of $\Gamma$:
$\Gamma(z+1) = z\Gamma(z)$ and has simple poles at $z=0,-1,-2,\cdots$ with residues $\Res_{z=-m} \Gamma(z) = (-1)^m/m!$.
There is also a factorization
\[
\Gamma(z) = {1 \over ze^{\gamma z} \prod_{n=1}^\infty \qty{1 + {z\over n}}e^{-z\over n} }
\]
where $\gamma \da \lim_{N\to\infty } \sum_{n=1^N} {1\over n} - \log(N)$

\[
\Gamma(z) \Gamma(1-z) = {\pi \over \sin(\pi z)}
,\]
which yields a product factorization for $\sin(\pi z)$.

$\mcl(t^{z-1}, s=1) = \Gamma(z)$ and $\mcl(t^n, s=1) = \Gamma(n+1)$.

The residues:

![](figures/2021-12-19_19-59-45.png)

:::

:::{.proposition title="$\Gamma$ is holomorphic on the right half-plane"}

![](figures/2021-12-19_19-58-16.png)

:::


:::{.proposition title="Functional equation for $\Gamma$"}

![](figures/2021-12-19_19-58-44.png)

:::


:::{.proposition title="Meromorphic continuation of $\Gamma$"}

![](figures/2021-12-19_19-59-05.png)
:::



