# Linear Fractional Transformations

:::{.remark title="Notation"}

| Notation                                                     | Definition                                             |
|--------------------------------------------------------------|--------------------------------------------------------|
| $\DD \da \ts{z \st \abs{z} \leq 1}$                          | The unit disc                                          |
| $\HH \da \ts{x+iy \st y > 0}$                                | The upper half-plane                                   |
| $X_{1\over 2}$                                               | A "half version of $X$", see examples                  |
| $\HH_{1\over 2}$                                             | The first quadrant                                     |
| $\DD_{1\over 2}$                                             | The portion of the first quadrant inside the unit disc |
| $L \definedas \theset{x + iy \suchthat x\in \RR,\, 0<y<\pi}$ | The horizontal strip                                   |

:::

:::{.fact}
Checking if $f$ is conformal: $f'(z_0) \neq 0$.

- Conformal Mapping Dictionary:

  Parts [I](http://mathfaculty.fullerton.edu/mathews/c2003/ConformalMapDictionary.1.html),[II](http://mathfaculty.fullerton.edu/mathews/c2003/ConformalMapDictionary.2.html) ,[III](http://mathfaculty.fullerton.edu/mathews/c2003/ConformalMapDictionary.3.html) ,[IV](http://mathfaculty.fullerton.edu/mathews/c2003/ConformalMapDictionary.4.html), and [V](http://mathfaculty.fullerton.edu/mathews/c2003/ConformalMapDictionary.5.html)
:::

:::{.definition title="Conformal Map / Biholomorphism"}
A map $f$ is **conformal** on $\Omega$ iff $f$ is complex-differentiable, $f'(z)\neq 0$ for $z\in \Omega$, and $f$ preserves signed angles (so $f$ is orientation-preserving).

A bijective conformal map $f:U\to V$ **biholomorphism**, and we say $U$ and $V$ are **biholomorphic**.
:::

:::{.remark}
Conformal implies holomorphic, and a bijective conformal map has conformal inverse automatically.
Importantly, bijective holomorphic maps always have holomorphic inverses.
Self-biholomorphisms of a domain $\Omega$ form a group $\Aut_\CC(\Omega)$.
:::

:::{.remark}
The bijectivity condition can be weakened: an *injective* holomorphic map satisfies $f'(z) \neq 0$ and $f ^{-1}$ is well-defined on its range and holomorphic.
:::

:::{.definition title="Linear fractional transformation / Mobius transformation"}
A map of the following form is a *linear fractional transformation*:
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
.\]
:::

:::{.remark}
Using that $\Aut(\CP^1) \cong \PGL_2(\CC)$, there is a nice matrix representation if you let the act on the right:
\[
\tv{z: 1} \cdot \matt a b c d = \tv{f(z): 1}
.\]
This yields a quick way of finding $f\inv$: invert the matrix and ignore the determinant that shows up since it just scales every entry:
\[
{az + b\over cz+ d} \leadsto \matt a b c d \inv = \matt d {-b} {-c} a 
\leadsto 
{dw-b \over -cw + a}
.\]

:::

:::{.proposition title="Constructing Mobius transformations"}
Given any three points $z_1, z_2, z_3$, the following Möbius transformation sends them to $1, 0, \infty$ respectively:
\[
T(z) 
&\da \qty{z-z_2\over z-z_3} \qty{z_1 - z_2 \over z_1 - z_3} \inv
\\
z_1 & \mapsto 1 \\
z_2 & \mapsto 0 \\
z_3 & \mapsto \infty
.\]
Such a map is sometimes denoted $(z; z_1, z_2, z_3)$.
One can use this to produce a map sending any three points to any other three points:
\[
T(z) \da 
(w; w_1, w_2, w_3)\inv
\circ
(z; z_1,z_2, z_3)
.\]
:::

:::{.remark}
A very useful variant that shows up in applications of the Schwarz' lemma:
\[
M_{z_1} \da {z_1 - z \over 1 - \bar{z_1} z}
.\]
This swaps $z_1$ and $0$.
:::


