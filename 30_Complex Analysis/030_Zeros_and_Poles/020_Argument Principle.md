# Argument Principle

:::{.definition title="The logarithmic derivative"}
The **logarithmic derivative** is defined as 
\[
\logd f \da {f' \over f}
.\]
:::

:::{.fact}
It converts all poles and zeros of meromorphic $f$ into simple poles of $\logd f$.
If $z_0$ is a root of $f$ of multiplicity $m$, write $f(z) = (z-z_0)^m g(z)$ with $g$ holomorphic and nonzero near $z_0$.
Then take log derivatives:
\[
\logd f(z) 
&= \logd (z-z_0)^m g(z) \\
&= \logd (z-z_0)^m + \logd g(z) \\
&= {m\over (z-z_0)} + {g'(z) \over g(z)}
.\]

Then if $g$ is holomorphic and nonzero away from $z_0$, so is $g'/g$.
So the only contribution to $\Res_{z=z_0} \logd f$ is $m$.
:::

:::{.remark}
Note that the logarithmic derivative picks up the $p\dash$adic valuation for $\gens{x-p} \in \CC[x]$ a point:
\[
d \qty{ \log(f) } = {f'\over f}\dz  \implies \Res_{z=p}(d \log(f) ) = v_p(f)
.\]

:::

:::{.definition title="Winding Number"}
For $\gamma \subseteq \Omega$ a closed curve not passing through a point $z_0$, the **winding number of $\gamma$ about $z_0$** (or the **index**) is defined as
\[
\Index_{z=z_0}(\gamma) \da {1\over 2\pi i} \int_\gamma {1\over \xi -z_0}\dxi
.\]

:::

:::{.theorem title="Argument Principle, Zeros/Poles Version"}
For $f$ meromorphic in $\Omega$ with multisets of zeros \( Z_f \da \ts{ z_j } \) and poles \( P_f\da \ts{ p_k } \) (so repeated with multiplicity) 
for $\gamma \da \bd \Omega$ not intersecting any of the zeros/poles,

\[  
{1\over 2\pi i} \int_\gamma \logd f(z) \dz
\da {1\over 2\pi i} \int_\gamma {f'(z) \over f(z)} \dz =
&= \size Z_f - \size P_f
,\]
where $\size Z_f$ and $\size P_f$ are the number of zeros and poles respectively, counted with multiplicity.
If $f$ is holomorphic, then
\[
{1\over 2\pi i} \oint_{\bd \Omega} {f'(z) \over f(z)}\dz 
&= \sum_{z_k\in f\inv(0) \intersect \Omega} \mathrm{mult}(f, z_k) \\
{1\over 2\pi i} \oint_{\bd \Omega} {zf'(z) \over f(z)}\dz 
&= \sum_{z_k\in f\inv(0) \intersect \Omega} f(z_k) \mathrm{mult}(f, z_k) \\
.\]

:::

:::{.proof title="?"}
\envlist

- If $z_0$ is a zero of $f$ of order $m$, write $f(z) = (z-z_0)^m g(z)$ with $g(z)$ holomorphic and nonzero on some neighborhood of $z_0$.
- Compute
\[
\logd f(z)
&=
\frac{m\left(z-z_{0}\right)^{m-1} g(z)+\left(z-z_{0}\right)^{m} g^{\prime}(z)}{\left(z-z_{0}\right)^{m} g(z)} \\
&= {m \over z-z_0} + \logd g(z)
,\]
so $z_0$ is a simple pole of $\logd f$ and $\res_{z=z_0} \logd f = m$.

- If $z_0$ is a pole of $f$ of order $m$, write $f(z) = (z-z_0)^{-m} g(z)$, then
\[
\logd f = {-m \over z-z_0} + \logd g
,\]
  so $z_0$ is a simple pole and $\Res_{z=z_0} \del_{\log f} = -m$.

- Now apply the residue theorem, and group residues according to sign:
\[
{1\over 2\pi i } \int_{\gamma} \del_{\log }f(z) \dz 
&= \sum_{z_i \in P_{\logd f}} \Res_{z=z_i} \logd f(z)\\
&= \sum_{z_k \in Z_f} \Res_{z=z_k} f(z) - \sum_{z_j \in P_f} \Res_{z=z_j} f(z)
.\]
:::

:::{.theorem title="Argument Principle, Index Version"}
With the same setup as above, 
\[
{1\over 2\pi i} \int_\gamma \logd f(z) \dz
&= \Index_{w=0}(f\circ \gamma)(w)
.\]


:::

:::{.proof title="?"}
Make the change of variables $w = f(z)$, then $z=\gamma(t) \mapsto w = (f\circ \gamma)(t)$ and $\dw = f'(z) \dz$, so
\[
{1\over 2\pi i }\int_{\gamma} \logd f(z) \dz 
= {1\over 2\pi i} \int_{f\circ \gamma} {1\over w} \dw \da \Index_{w=0} (f\circ \gamma)(w)
.\]


:::

:::{.example title="Using the index version of the argument principle"}
Let $f(z) = z^2 + z = z(z+1)$.

- $\gamma_1 \da \ts{\abs z = 2}$ contains 2 zeros and 0 poles, so $f\circ \gamma$ winds twice around zero counterclockwise.
- $\gamma_2 \da \ts{\abs z = {1\over 2}}$ contains 1 zero and 0 poles, so $f\circ \gamma$ winds once.

:::

:::{.remark}
You can track the change in argument by just breaking a curve up into sub-curves and evaluating a branch of the $\arg$ function at the endpoints.
For example, in this picture, the change in argument is $\pi$ no matter what the curve does in $\HH$:

![](figures/2021-12-10_18-06-04.png)

:::

:::{.remark}
The integral function
\[
F(w) \da {1\over 2\pi i} \oint_{\bd \Omega} {f'(z) \over f(z) - w} \dw
\]
counts the number of solutions to $f(z) = w$ in $\Omega$, since it's of the form $\int_\gamma \logd g_w(z)\dz$ for $g_w(z) \da f(z) - w$.
This is continuous provided $f(z) \neq w$ on $\bd \Omega$ and is $\ZZ\dash$valued, thus constant on connected components.

> Also useful: zeros of $f$ with multiplicity $m\geq 2$ are zeros of $f'$.
  This also holds for $f(z) -a$.

:::

## Exercises

:::{.exercise title="?"}
Show that $\logd(fg) = \logd f + \logd g$, i.e. 
\[
{ (fg)' \over fg} = {f'\over f} + {g' \over g}
.\]

#complex/exercise/completed

:::

:::{.solution}
\[
{(fg)' \over fg} = { f'g + fg' \over fg} = {f'g \over fg} + {fg' \over fg} = {f'\over f} + {g' \over g}
.\]

:::

:::{.exercise title="Detecting injectivity using derivatives"}
Show that if $z_0$ is a zero of $f'$ of order $n-1$, then $f$ is $n$-to-one in a neighborhood of $z_0$.

#complex/exercise/completed

:::

:::{.solution}
Wlog, assume $z_0 = 0$.
We want to show that there exists discs $U = \DD_r(0)$ and $W = \DD_R(0)$ such that the fiber of $f:U\to W$ has exactly $n$ distinct points.
Since $0$ is a zero of order $n$, expand $f$ as $\sum_{k\geq n} c_k z^k = z^n\sum_{k\geq 0} c_{k+n}z^k$.
By dividing coefficients through, we may assume $c_n = 1$, so 
\[
f(z) = z^n + \qty{ c_{n+1} z^{n+1} + c_{n+2}z^{n+2} + \cdots} = z^n + z^{n+1} \sum_{k\geq 0} c_{k+n+1}z^k \da z^n + g(z)
.\]

:::{.claim}
By Rouché, $f(z)$ and $z^n$ have the same number of zeros in a small disc $\DD_\rho(0)$.
:::

:::{.proof title="of claim"}
Write $m(z) = \sum_{k\geq 0}c_{k+n}z^k$ and $M(z) = z^n$; then if $\abs{m(z)} < \abs{M(z)}$ for any circle $\abs{z} = \rho$ with $\rho< 1$ then $M$ and $m+M = f$ will have the same number of zeros ($n$ with multiplicity).

Bounding $m$, the tail of the Laurent series of $f$: by Cauchy's integral formula, on a disc of radius $R$,
\[
c_k = {f^{(n)}(z_0) \over n!} = {1\over 2\pi i} \oint_{\abs{\xi} = R} { f(\xi) \over (\xi - z_0)^{n+1} } \dxi
,\]
so
\[
\abs{c_k} \leq \max_{\abs{\xi} = R}\abs{f(\xi)} R^{-k} \da {M_R \over R^{k}}
.\]

We can now estimate $g$:
\[
\abs{g(z)} 
&= \abs{z^n \sum_{k\geq 0} c_{k+n+1} z^k} \\
&\leq \abs{z}^n \sum_{k\geq 0} \abs{ c_{k+n+1}} \abs{z}^k \\
&\leq \sum_{k\geq 0} {M_R \over R^{k+n+1}} \rho^k \\
&= \abs{z}^n {M_R \over R^{n+1}} \sum_{k\geq 0} \qty{\rho\over R}^k \\
&= \abs{z}^n {M_R \over R^{n+1}} \qty{1\over 1- {\rho \over R}} \\
&= \abs{z}^n {M_R \over R^{n+1}} {R\over R-\rho} \\
&= \abs{z}^n \qty{ {M_R\over R^n( R-\rho)} } \\
&\da \abs{z}^n C_{R, \rho}
,\]
and $R, \rho$ can be chosen such that $C_{R, \rho} < 1$.

Thus on $\abs{z} = \rho$,
\[
\abs{m(z)} = \abs{g(z) } \leq C_{R, \rho} \abs{z} < \abs{z} = \abs{M(z)}
.\]

:::

So the fiber above $z=0$ is of size $n$, the claim is that this is also true in a neighborhood of zero.
The above estimate also shows that for $0 < \abs{z}\leq \rho$, $\abs{g(z)} \leq \abs{z^n}$, and so
\[
\abs{g(z)} = \abs{g(z) - z^n + z^n} \geq \abs{ \abs{g(z) - z^n} - \abs{z^n} } > 0
,\]
so $g$ is nonzero on $\DD_\rho(0)\smz$.
For the zero-counting function
\[
F(w) \da {1\over 2\pi i} \oint_{\abs{\xi} = \rho'} {f'(\xi) \over f(\xi) - w }\dxi
.\]
Taking $\rho ' < \min_{\abs{\xi} = \rho} \abs{f(z)}$ makes this a holomorphic function of $w$ on $\DD_{\rho'}(0)$, and as a continuous $\ZZ\dash$valued function it is constant.
Since $F(0) = n$, this forces $F(w) = n$ for all $\abs{w} < \rho'$, so there are $n$ solutions to $f(z) = w$ in these discs.
After shrinking these discs if necessary, $f'\neq 0$ is nonvanishing on a punctured disc, so $f$ is injective there and these solutions are distinct.
:::

