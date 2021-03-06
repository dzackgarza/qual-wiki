---
title: "Theory and Background: Conformal Maps"
sort: 0
---

# Theory and Background: Conformal Maps

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
R(z) \da (z, a,b,c) &\da {z - b\over z-c}{a - c\over a - c} \\
.\]

Given any three points, $R(z)$ sends
\[
a &\to 1 \\
b &\to 0 \\
c &\to \infty
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

:::{.remark}
An LFT that fixes three points is the identity.

:::


## Blaschke Factors

:::{.remark}
A very useful variant that shows up in applications of the Schwarz' lemma:
\[
\psi_a \da {a-z \over 1-\bar{a} z}
.\]
Some nice properties:

- $\psi_a(a) = 0$ and $\psi_a(0) = a$
- $\psi_a$ has a simple pole at $1/\bar{a}$ and a simple zero at $z=a$.
- $\psi_a(\bd \DD) = \bd \DD$, i.e. $\abs{\psi_a(z)} = \abs{z}$ when $\abs{z} = 1$.
- $\Aut(\DD) = \ts{ e^{i\theta} \psi_{a_k} \st a_k\in \DD}$, i.e. these form the factors of automorphisms of the disc after including rotations.
- $\psi_a'(z) = {\abs{a}^2 - 1\over (1-\bar{a} z)^2}$

:::

## Exercise

:::{.exercise title="Mobius transformations as cross-ratios"}
Write a Mobius transformation $f(z) = {az+b\over cz + d}$ as a cross-ratio.

#complex/exercise/completed

:::

:::{.solution}
\[
T(z) = \qty{ z; {d-b\over a-c}, -{b\over a}, -{d\over c}}
.\]
:::

:::{.exercise title="Cancelling poles"}
Let $f$ be meromorphic on $\DD$ with no poles on $\bd\DD$.
Show that there exists a meromorphic $g$ with *no* poles in $\DD$ such that $\abs{f(z)} = \abs{g(z)}$ when $\abs{z} = 1$.

#complex/exercise/completed

:::

:::{.solution}
Write $\ts{a_1,\cdots, a_n}$ for all of the poles of $f$, indexed with multiplicity, and define
\[
g(z) \da \prod_{1\leq k\leq n} \psi_{a_k}(z) f(z) 
\da \qty{ \prod_{1\leq k \leq n}{z-a_k\over 1 -\bar{a_k} z}} f(z)
.\]
Then $g$ has no poles, and since $\abs{ \psi_{a_k} } = 1$ on $\bd \DD$, this works.
:::

:::{.exercise title="?"}
Show that if $f$ is injective, then $f'$ is nowhere vanishing and thus $f$ is conformal.

#complex/exercise/completed

:::

:::{.solution}
Contrapositive: if $f'(z_0)=0$ at some point, then $f$ fails injectivity in a neighborhood of $z_0$.
Without loss of generality, we can assume $f(0) = 0$ after changes of coordinates in the domain/codomain, since this won't affect injectivity or vanishing of derivatives.
If $z_0$ is a zero of $f$ of some order $n$, we can write $f(z) = z^n g(z)$ with $g(0) \neq 0$ and $g$ nonvanishing in some neighborhood of zero.
Choosing a branch of $z\mapsto z^{1\over n}$, write $g(z) = (h(z))^n$ for some $h$, then
\[
f(z) = z^n h(z)^n = (zh(z))^n
.\]
Write $H(z) \da zh(z)$, then $H'(z) = h(z) + zh'(z)$, so $H'(0)\neq 0$.
By the inverse function theorem, $H$ is invertible on a small neighborhood of $0$, making $f$ $n$-to-one for some $n$.
Writing $f(z) = \sum_{k\geq 0} c_k z^k$, we have $c_0 = 0$ since $f(0) = 0$ and $c_1 = 0$ if $f'(0) = 0$, making $n\geq 2$, so $f$ fails injectivity in this neighborhood.
:::


