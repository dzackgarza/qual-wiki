---
sort: 020
title: Residues
---

# Residues

:::{.remark}
On strategy: see <https://www.damtp.cam.ac.uk/user/reh10/lectures/nst-mmii-chapter5.pdf>

A quick shortcut (?) for the quotient rule:
\[
\dd{}{z} {p(z) \over q(z)} = {p'(z)\over q(z)} - {p(z)q'(z) \over q^2(z)}
.\]
Useful when taking $z\to z_0$ with $z_0$ a root of $p, p', q'$.

:::

:::{.remark}
Pedantic warning: $\Res_{z=p}(f)$ should really be $\Res_{z=p}(df)$ for $df = f(z) \dz$, since it's only an invariant of the 1-form $df$ and not necessarily $f$ itself.
We freely abuse notation!
:::

:::{.remark}
Check: do you need residues at all??
You may be able to just compute an integral!

- If the integrand is holomorphic throughout the region enclosed by $\gamma$, $\int_\gamma f = 0$
- If $f$ has a well-defined primitive $F$ on $\gamma$, then 
\[
\int_\gamma f = \int_\gamma F' = F(\gamma(1)) - F(\gamma(0)) = 0
.\]
- Use Cauchy's theorem when applicable:
\[
\int_\gamma {f(z) \over (z-a)^n} = 2\pi i f^{(n-1)}(a)
.\]

- Compute directly by parameterization:
\[
\int_\gamma f \dz = \int_a^b f(z(t))\, z'(t) \dt && \text{for } z(t) \text{ a parameterization of } \gamma
,\]

  - Note: you can parameterize a circle around $z_0$ using
  \[
  z= z_0 + re^{i \theta }
  .\]

:::

## Residue Formulas

:::{.theorem title="The residue theorem"}
Let $f$ be meromorphic on a region $\Omega$ with poles \( \ts{ \elts{z}{N} } \).
Then for any $\gamma \in \Omega\sm \ts{ \elts{z}{N} }$, 
\[
{1 \over 2\pi i } \int_\gamma f(z) \dz = \sum_{j=1}^N n_\gamma(z_j) \Res_{z=z_j} f
.\]
If $\gamma$ is a toy contour with winding number 1 about each pole, then
\[
{1\over 2\pi i}\int_\gamma f\dz = \sum_{j=1}^N \Res_{z=z_j}f
.\]

:::

:::{.theorem title="The residue formula"}
If $f$ has a pole $z_0$ of order $n$, then
\[  
\Res_{z=z_0} f = \lim_{z\to z_0} {1 \over (n-1)!} \qty{\dd{}{z}}^{n-1} (z-z_0)^n f(z)
.\]

As a special case, if $z_0$ is a simple pole of $f$, then
\[  
\Res_{z=z_0}f = \lim_{z\to z_0} (z-z_0) f(z)
.\]
:::

:::{.corollary title="Residue formula: rational function formula for simple poles"}
If additionally $f=g/h$ where $h(z_0) = 0$ and $h'(z_0)\neq 0$, 
\[
\Res_{z=z_0} {g(z) \over h(z)} = {g(z_0) \over h'(z_0)}
.\]

Note that if $f(z) = 1/h(z)$ and $z_0$ is a simple pole, this reduces to
\[
\Res_{z=z_0}{1\over h(z)} = {1\over h'(z_0)}
.\]

:::

:::{.warnings}
Note that only the denominator gets differentiated, not the numerator!
To remember this, just rederive the equation from L'Hopital's rule and use the product rule on $(z-z_0)g(z)$.
:::

:::{.proof title="Of derivative formula for simple poles"}
Apply L'Hopital:
\[
(z-z_0) {g(z) \over h(z)} = {(z-z_0) g(z) \over h(z) } \equalsbecause{LH}
{g(z) + (z-z_0) g'(z) \over h'(z)} \converges{z\to z_0}\too {g(z_0) \over h'(z_0)}
.\]
:::

:::{.theorem title="Residue formula: poles at infinity"}
\[
\Res_{z=\infty}f(z) = \Res_{z=0} g(z) && g(z) \da -{1 \over z^2}f\qty{1\over z} 
.\]

Note on where this weird formula comes from: residues are associated not to function $f$ but to *differential forms* $f(z)\dz$, and inversion sends $f(z) \dz\to f(1/z)d(1/z) = f(1/z)\cdot -{1\over z^2}\dz$.
This residue can alternatively be calculated for $f$ by taking $\gamma$ a contour enclosing all singularities of $f$ and computing
\[
\Res_{z=\infty}f(z) = -{1\over 2\pi}\int_\gamma f(z) \dz
.\]

:::

:::{.theorem title="Residue formula: fractional residues"}
If $z_0$ is an order 1 pole of $f$ and $\gamma_{\eps, \theta}$ is an arc of the circle $C_\eps \da \ts{ \abs{z-z_0} = \eps}$ subtending an angle of $\theta$, then
\[
\lim_{\eps\to 0} \int_{\gamma_{\eps, \theta}} f(z) \dz  = i\theta \Res_{z = z_0}f(z)
.\]

![](figures/2021-12-22_05-13-02.png)

:::

:::{.proof title="?"}

![](figures/2021-12-22_05-13-27.png)

:::

## Exercises

### Avoiding Residue Formulas

:::{.exercise title="Integrating $z^k$ around $S^1$ is the source of residue theory"}
Show that
\[
\int_{S^1}z^k \dz = 
\begin{cases}
2\pi i & k=-1 
\\
0 & \text{else}.
\end{cases}
,\]
and thus
\[
\int \sum_{k\geq -M} c_k z^k = \sum_{k\geq -M} \int c_k z^k = 2\pi i c_{-1}
,\]
i.e. the integral picks out the $c_{-1}$ coefficient in a Laurent series expansion.

#complex/exercise/completed

:::

:::{.solution}
\[
\int_\gamma z^k \dz = \int_0^{2\pi} e^{ik\theta} ie^{i\theta } \dtheta = i\int_0^{2\pi} e^{i(k+1)\theta \dtheta }
= \begin{cases}
2\pi i & k=-1 
\\
0 & \text{else}.
\end{cases}
\]
:::

:::{.exercise title="Primitive in the complement of a branch cut"}
Compute the following integrals:
\[
\int_{\abs{z-1} = 1} {1\over z^2-1} \dz \\
\int_{\abs{z-0} = 2} {1\over z^2-1} \dz \\
.\]
Compute the 2nd integral by finding a primitive.

#complex/exercise/completed

:::

:::{.solution}
For the first integral:
\[
\int_\gamma{1\over z^2-1}\dz 
&= {1\over 2}\int_\gamma {1\over z-1} + {1\over z+1}\dz \\
&= {1\over 2}\int_\gamma {1\over z-1} \\
&= {1\over 2}\cdot 2\pi i \Res_{z=1}f(z) \\
&= {1\over 2}\cdot 2\pi i \cdot 1 \\
&= \pi i
,\]
using that $f(z) = {1\over z-1}$ is already an expansion of $f$ about $z=1$ since it is a Laurent series in $(z-1)^k$, so the residue is $1$.

For the second integral:
attempt to define a primitive
\[
F(z) \da {1\over 2}\log\qty{z-1\over z+1} \implies F'(z) = {1\over z^2-1}
.\]
If this primitive is well-defined on $\gamma$, the integral will vanish because this is a closed curve.
Choose the branch cut $\CC\sm(-\infty, 0]$ and define $g(z) = {z-1\over z+1}$, so that $F(z) = {1\over 2}\log(g(z))$.
Then then $g(z)\in (-\infty, 0] \iff z\in [-1, 1]$, and this is well-defined on $\gamma$ since $[-1, 1]$ does not intersect $\gamma$.

Thus for $\gamma$ any parameterization of $\abs{z} = 2$,
\[
\int_{\abs{z} = 2} f(z) \dz
= \int_{\abs{z} = 2} F'(z)\dz
= F(\gamma(0)) - F(\gamma(1))
= 0
.\]

:::

:::{.exercise title="Cauchy formula and $\sinh$"}
Compute
\[
\int_{S^1} {2 \sinh(z) \over z^n}\dz
.\]

#complex/exercise/completed

:::

:::{.solution}
Write $f(z) = 2\sinh(z) = e^{z} - e^{-z}$ and apply the generalized Cauchy formula:
\[
f^{(n-1)}(0) 
&= {(n-1)! \over 2\pi i} \int_{S^1} {f(z) \over (z-0)^n}\dz \\ \\
\implies \int_{S^1}{f(z)\over z^n}\dz 
&= {2\pi i \over (n-1)!} f^{(n-1)}(0) \\
&= {2\pi i\over (n-1)!} 2\cdot \qty{e^z - (-1)^{n-1} e^z \over 2}\evalfrom_{z=0} \\
&= {2\pi i\over (n-1)!} 2\cdot \qty{1 + (-1)^{n} \over 2} \\
&=
\begin{cases}
{2\pi i \over (n-1)!} & n \text{ even } 
\\
0 & n \text{ odd }.
\end{cases}
.\]
:::

:::{.exercise title="Cauchy formula and principal parts"}
Compute
\[
\int_\gamma {z^2+1 \over z(z^2 + 4)}\dz
\]
for 

- A circle of radius $1$,
- A circle of radius $2+\eps$,

#complex/exercise/completed

:::

:::{.solution}
For the smaller circle, use Cauchy's formula
\[
\int_{\abs{z} = 1} f(z) \dz 
&= \int_{\abs{z} = 1} { {z^2 + 1 \over z^2 + 4} \over z} \dz \\
&=  2\pi i \qty{z^2 + 1 \over z^2 + 4} \evalfrom_{z=0} \\
&= {i\pi \over 2}
.\].

For the larger circle, break into principal parts.
Write
\[
{z^2 + 1 \over z(z^2+4)} = {a\over z} + {b\over z+2i} + {c\over z-2i}
,\]
and use PFD/cover-up method/finding residues:

- $a = \qty{z^2+1\over z^2+4}\evalfrom_{z=0} = {1\over 4}$
- $b= \qty{z^2 + 1 \over z(z-2i)}\evalfrom_{z=-2i} = {-4+1\over -2i(-4i)} = {3\over 8}$
- $c = \qty{z^2 + 1 \over z(z+2i)}\evalfrom_{z=2i} = {-4+1 \over 2i(4i)} = {3\over 8}$

Thus
\[
\int_\gamma f(z) \dz 
&= \int_\gamma \qty{ {1/4\over z} + {3/8\over z+2i} + {3/8 \over z-2i} } \dz \\
&= 2\pi i\qty{ {1\over 4} + {3\over 8} + {3\over 8}}
.\]

:::

:::{.exercise title="Residues using partial fractions/principal parts"}
Find all residues of the following function by writing it as a sum of principal parts at its poles:
\[
f(z) = {z^3 \over z^2 + 1}
.\]

#complex/exercise/completed

:::

:::{.solution}
Use polynomial long division to write
\[
z^3 = z(z^2+1) - z \implies {z^3 \over z^2 + 1} = z - {z\over z^2 + 1}
.\]
Factor the latter part:
\[
{z\over z^2 + 1} = {a\over z+i} + {b\over z-i} \implies a(z-i) + b(z+i) = z
,\]
evaluate at $z=i$ to get $b=1/2$, and at $z=-i$ to get $a=1/2$.
Thus
\[
f(z) = z - {1/2 \over z+i} - {1/2 \over z-i} = P_\infty + P_{-i} + P_{i}
,\]
yielding poles at $\pm i$ with residues
\[
\Res_{z=\infty} f(z) &= -1 \\
\Res_{z = i} f(z) &= -1/2 \\
\Res_{z = -i} f(z) &= -1/2 \\
.\]




:::

:::{.exercise title="Residue from Laurent expansion: $1/(z - \sin(z))$"}
Use a direct Laurent expansion to show
\[
\Res_{z=0} {1\over z-\sin(z)} = {3! \over 5\cdot 4}
.\]

> Note the necessity: one doesn't know the order of the pole at zero, so it's unclear how many derivatives to take.

#complex/exercise/completed

:::

:::{.solution}
Expand:
\[
{1\over z - \sin(z)}
&= z\inv \qty{1 - z\inv \sin(z) }\inv \\
&= z\inv \qty{1 - z\inv\qty{ z - {1\over 3!}z^3 + {1\over 5!} z^5 - \cdots}}\inv\\
&= z\inv \qty{1 - \qty{ 1 - {1\over 3!}z^2 + {1\over 5!} z^4 - \cdots}}\inv \\
&= z\inv \qty{{1\over 3!}z^2 - {1\over 5!}z^4 + \cdots}\inv \\
&= z\inv \cdot 3! z^{-2} \qty{1 - {1\over 5!/3!}z^2 + \cdots}\inv \\
&= {3!\over z^3} \qty{1 \over 1 - \qty{ {1\over 5\cdot 4}z^2 + \cdots}} \\
&= {3!\over z^3}\qty{1 + \qty{{1\over 5\cdot 4}z^2} + \qty{{1\over 5\cdot 4}z^2}^2 + \cdots} \\
&= 3! z^{-3} + {3!\over 5\cdot 4}z\inv + O(z) \\
.\]

:::

:::{.exercise title="Computing residues: $1/z^2\sin(z)$"}
Compute
\[
\Res_{z=0} {1\over z^2 \sin(z)}
.\]

#complex/exercise/completed

:::

:::{.solution}
First expand $(\sin(z))\inv$:
\[
{1\over \sin(z)}
&= \qty{z - {1\over 3!}z^3 + {1\over 5!}z^5 -\cdots }\inv \\
&= z\inv \qty{1 - {1\over 3!}z^2 + {1\over 5!}z^4 - \cdots }\inv \\
&= z\inv \qty{1 + 
\qty{{1\over 3!}z^2 - {1\over 5!} z^4 + \cdots} 
+
\qty{{1\over 3!}z^2 - \cdots}^2 + \cdots
} \\
&= z\inv\qty{1 + {1\over 3!}z^2 \pm O(z^4) }
,\]
using that $(1-x)\inv = 1 + x + x^2 + \cdots$.

Thus
\[
z^{-2}\qty{\sin(z)}\inv 
&= z^{-2} \cdot
z\inv\qty{1 + {1\over 3!}z^2 \pm O(z^4) } \\
&= z^{-3} + {1\over 3!}z\inv + O(z)
.\]
:::

### Applying the formulas

:::{.exercise title="Residue of $1/z^2 + 1$"}
Use the rational function formula to compute the residues at $z=\pm i$ of
\[
f(z) \da {1\over z^2 + 1}
.\]

#complex/exercise/completed

:::

:::{.solution}
Applying the rational function formula:
\[
\Res_{z=z_0}{1\over 1+z^2} &= {1\over 2z}\evalfrom_{z= z_0} \implies\\
\Res_{z=i}f(z) &= {1\over 2i} = -{i\over 2} \\
\Res_{z=-i}f(z) &= -{1\over 2i} = {i\over 2}
.\]

:::

:::{.exercise title="Residue of $1/z^n+1$"}
Find the residue at $\omega_n \da e^{\pi i \over n}$ of
\[
f(z) = {1\over z^n + 1}
.\]

#complex/exercise/completed

:::

:::{.solution title="?"}
Check that $\dd{}{z} z^n+1 = nz^{n-1}\neq 0$ for $z\neq 0$, so this has no repeated roots since $z=0$ is not a root.
Thus all of the poles are simple, so apply the rational function formula:
\[
\Res_{z=\zeta_{m}} {1\over z^n + 1} 
&= {1 \over nz^{n-1}}\evalfrom_{z=\omega_n} \\
&= {1\over n\omega_n^{n-1}} \\
&= {\omega_n^{1-n}\over n} \\
&= -{\omega_n \over n}
,\]
which follows from expanding 
\[
\omega_n^{1-n} = e^{i\pi (1-n) \over n} =  e^{i\pi\over n}e^{-i\pi n \over n} = e^{i\pi \over n}\cdot (-1) = -\omega_n
.\].
:::

:::{.exercise title="Residues at $\infty$"}
Compute
\[
&\Res_{z=\infty}e^z\\
&\Res_{z=\infty}{z-1\over z+1}
.\]

#complex/exercise/completed

:::

:::{.solution}
In parts:

- For $e^z$:
  - Integral formula: $\Res_{z=\infty}f(z) = -{1\over 2\pi }\int_\gamma f(z)\dz$ where $\gamma$ encloses all singularities of $f$, but $e^z$ is entire, so this integral is zero and thus the residue is zero.
  - Inversion formula: expand $z^{-2}f(1/z)$ about $z=0$ to obtain
  \[
  {1\over z^2}e^{1\over z} = z^{-2}\sum_{k\geq 0}z^{-k}/k! = \sum_{k\geq 0}z^{-k-2}/k! = z^{-2} + z^{-3} + {1\over 2!}z^{-4} + \bigo(z^{-5}) 
  ,\]
  so the residue is zero.

- For ${z+1\over z-1}$:
  - Integral formula:
  \[
  \Res_{z=\infty} &= -{1\over 2\pi}\int_{\abs{z} = 2} {z-1\over z+1}\dz \\
  &= - \Res_{z=-1} {z-1\over z+1} \\
  &= - (-2) \\
  &= 2
  .\]
  - Inversion formula:
  \[
  {1\over z^2}{ z\inv - 1 \over z\inv + 1} 
  &= z^{-2}{1 - z \over 1 + z} \\
  &= z^{-2}(z-1)\sum_{k\geq 0} (-z)^k \\
  &= z^{-2} + 2z\inv -2 + 2z - \bigo(z^2)
  ,\]
  which has residue 2.


:::

