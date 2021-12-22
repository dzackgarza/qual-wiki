# Linear Fractional Transformations

:::{.remark title="Resources"}
Conformal Mapping Dictionary:

  Parts [I](http://mathfaculty.fullerton.edu/mathews/c2003/ConformalMapDictionary.1.html),[II](http://mathfaculty.fullerton.edu/mathews/c2003/ConformalMapDictionary.2.html) ,[III](http://mathfaculty.fullerton.edu/mathews/c2003/ConformalMapDictionary.3.html) ,[IV](http://mathfaculty.fullerton.edu/mathews/c2003/ConformalMapDictionary.4.html), and [V](http://mathfaculty.fullerton.edu/mathews/c2003/ConformalMapDictionary.5.html)

:::

## Conformal Map Facts


:::{.remark}
It's a theorem that holomorphic and $f'\neq 0$ implies conformal.
Write $f(z+\eps) = f(z) + \eps f'(z) + \bigo(\eps^2)$, then
\[
\Arg(f(z+\eps) - f(z)) \approx \Arg(\eps f'(z)) = \Arg(\eps) + \Arg(f'(z))\to \Arg(f'(z))
,\]
so all tangent vectors near $z_0$ are rotated by approximately the same angle $f'(z_0)$, preserving their relative angles.
:::


:::{.definition title="Conformal Map / Biholomorphism"}
A map $f$ is **conformal** on $\Omega$ iff $f$ is complex-differentiable, $f'(z)\neq 0$ for $z\in \Omega$, and $f$ preserves signed angles (so $f$ is orientation-preserving).

A bijective conformal map $f:U\to V$ **biholomorphism**, and we say $U$ and $V$ are **biholomorphic**.
:::

:::{.fact title="Checking if a map is conformal"}
To check if a map is conformal at $p$, it *suffices* to check that $f'(p)\neq 0$.
:::

:::{.remark}
Conformal implies holomorphic, and a bijective conformal map has conformal inverse automatically.
Importantly, bijective holomorphic maps always have holomorphic inverses.
Self-biholomorphisms of a domain $\Omega$ form a group $\Aut_\CC(\Omega)$.
:::

:::{.remark}
The bijectivity condition can be weakened: an *injective* holomorphic map satisfies $f'(z) \neq 0$ and $f ^{-1}$ is well-defined on its range and holomorphic.
:::

## The Cross-Ratio Construction

:::{.proposition title="Cross ratio construction of conformal maps"}
Define generalized cross-ratios as
\[
(z_1, z_2, z_3, z_4) &\da {z_1 - z_3\over z_1-z_4}{z_2 - z_4 \over z_2 - z_3} \\
R(z) \da (z, z_2, z_3, z_4) &\da {z - z_3\over z-z_4}{z_2 - z_4 \over z_2 - z_3} \\
.\]

Given any three points, $R(z)$ sends
\[
z_2 &\to 1 \\
z_3 &\to 0 \\
z_4 &\to \infty
.\]


One can use this to produce a map sending any three points to any other three points:
\[
T(z) \da 
(w; w_1, w_2, w_3)\inv
\circ
(z; z_1,z_2, z_3)
.\]

If any of the $z_i$ are $\infty$, the convention is to remove the corresponding terms where they appear:
:::

## Linear Fractional/Mobius Transformations

:::{.definition title="Mobius transformation"}
A map of the following form is a **linear fractional transformation** ( or a **Mobius transformation**):
\[  
T(z) = {az + b \over cz + d}
,\]
where the denominator is assumed to not be a multiple of the numerator.
These have inverses given by
\[  
T^{-1}(w) = {dw-b \over -cw + a}
\]
and derivatives given by
\[
T'(z) = {ad-bc \over (cz+d)^2}
,\]
so this is always a conformal map when $ad-bc\neq 0$.
:::

:::{.remark title="Mobius transformations as projective linear automorphisms"}
Using that $\Aut(\CP^1) \cong \PGL_2(\CC)$, there is a nice matrix representation if you act on projective coordinates:
\[
\matt a b c d \cdot \tv{z: 1}^t = \tv{ {az+b \over cz + d }: 1} = \tv{f(z): 1}
.\]
This yields a quick way of finding $f\inv$: invert the matrix and ignore the determinant that shows up since it just scales every entry:
\[
{az + b\over cz+ d} \leadsto \matt a b c d \inv = \matt d {-b} {-c} a 
\leadsto 
{dw-b \over -cw + a}
.\]

:::

:::{.exercise title="Mobius transformations as cross-ratios"}
Write a Mobius transformation $f(z) = {az+b\over cz + d}$
as a cross-ratio.
:::

:::{.solution}
\[
T(z) = \qty{ z; {d-b\over a-c}, -{b\over a}, -{d\over c}}
.\]
:::

## Blaschke Factors

:::{.remark}
A very useful variant that shows up in applications of the Schwarz' lemma:
\[
\psi_a \da {z-a \over 1-\bar{a} z}
.\]
Some nice properties:

- $\psi_a(a) = 0$ and $\psi_a(0) = a$
- $\psi_a$ has a simple pole at $1/\bar{a}$ and a simple zero at $z=a$.
- $\psi_a(\bd \DD) = \bd \DD$, i.e. $\abs{\psi_a(z)} = \abs{z}$ when $\abs{z} = 1$.
- $\Aut(\DD) = \ts{ e^{i\theta} \prod_{k\leq N} \psi_{a_k} \st N\in \ZZ_{\geq 0}, a_k\in \DD}$, i.e. these form the factors of automorphisms of the disc after including rotations.
- Fun fact: these yield continuous dynamical systems on $\bd \DD$!
:::

:::{.exercise title="Cancelling poles"}
Let $f$ be meromorphic on $\DD$ with no poles on $\bd\DD$.
Show that there exists a meromorphic $g$ with *no* poles in $\DD$ such that $\abs{f(z)} = \abs{g(z)}$ when $\abs{z} = 1$.

#completed

:::

:::{.solution}
Write $\ts{a_1,\cdots, a_n}$ for all of the poles of $f$, indexed with multiplicity, and define
\[
g(z) \da \prod_{1\leq k\leq n} \psi_{a_k}(z) f(z) 
\da \qty{ \prod_{1\leq k \leq n}{z-a_k\over 1 -\bar{a_k} z}} f(z)
.\]
Then $g$ has no poles, and since $\abs{ \psi_{a_k} } = 1$ on $\bd \DD$, this works.
:::

