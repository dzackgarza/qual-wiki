---
order: 100
---

# Complex Arithmetic

:::{.fact title="Some useful facts about basic complex algebra"}
\[
z\bar z &= \abs{z}^2 && 
\Arg(z/w) = \Arg(z) - \Arg(w) \\
\Re(z) &= { z + \bar z \over 2} && 
\Im(z) = {z - \bar{z} \over 2i}
.\]

Exponential forms of cosine and sine, where it's sometimes useful to set $w\da e^{iz}$:
\[
\cos(z) 
&= \frac 1 2 \qty{e^{iz} + e^{-iz}} = {1\over 2}(w+ w\inv)\\
\sin(z) 
&= \frac{1}{2i}\qty{e^{iz} - e^{-iz}} = {1\over 2i}(w-w\inv)
.\]

Exponential forms of *hyperbolic* cosine and sin:
\[
\cosh(z) 
&= \cos(iz) 
= {1\over 2}\qty{e^z + e^{-z}} \\
\sinh(z) 
&= -i \sin(iz) 
= {1\over 2}\qty{e^z - e^{-z}} 
.\]

Some other useful facts about the hyperbolic exponentials:

- They are periodic with period $2\pi i$.
- $\dd{}{z}\cosh(z) = \sinh(z)$ and $\dd{}{z}\sinh(z) = \cosh(z)$.
- $\sinh$ is odd and $\cosh$ is even.
- $\cosh(z + i\pi) = -\cosh(z)$ and $\sinh(z + i\pi) = -\sinh(z)$.
- $\cosh$ has zeros at $\ts{i\pi\qty{2k+1\over 2}} = \ts{i \qty{\pi/2 + k\pi}}$, i.e. $\cdots, -\pi/2, \pi/2, 3\pi/2,\cdots$, the half-integers.
- $\sinh$ has zeros at $\ts{i\pi k}$, i.e. the integers.



:::

:::{.fact}
Some computations that come up frequently:
\[
\abs{z \pm w}^2 &= \abs{z}^2 + \abs{w}^z + 2\Re(\bar{w}z) \\
(a+bi)(c+di) &= (ac - bd) + (ad + bc) \\
{1\over \abs{a+b}} &\leq {1 \over {\abs a - \abs b}} &&
\abs{e^{z}} = e^{\Re(z)}, \quad \arg(e^z) = \Im(z)
.\]
:::

# Exercises

:::{.exercise title="Modulus of $e^z$"}
Show that $\abs{e^z} = e^{\Re(z)}$.

#completed
:::

:::{.solution}
Write $z=x+iy$, so $\Re(z) = x$.
Then
\[
\abs{e^z} = \abs{e^{x+iy}} = \abs{e^x}\abs{e^{iy}} = \abs{e^x}
,\]
using that $e^x>0$ for all $x\in \RR$.
:::

:::{.exercise title="?"}
Show that ${z-1\over z+1}$ is purely imaginary $\iff z\in S^1$.

> Hint: $z$ is purely imaginary iff $\bar{z} = -z$.

:::

:::{.solution}

\[
{z-1\over z+1} = -\qty{\bar z - 1 \over \bar z + 1} \iff (z-1)(1+z) = (1-\bar z)(1+\bar z) \iff2-2\abs{z}^2 = 0 \iff \abs{z}^2 = 1
.\]

:::



:::{.exercise title="?"}
Find $\Re\qty{z+2\over z-1}$.

#completed

:::


:::{.solution}
\[
{z+2\over z-1}\cdot{\bar{z-1} \over \bar{z-1}}
&= {(z+2)\bar{z-1} \over \abs{z-1}^2} \\
&= {((z-1) + 3)\bar{z-1} \over \abs{z-1}^2} \\
&= {\abs{z-1}^2 + 3\bar{z} -3 \over \abs{z-1}^2} \\
&= {(x-1)^2 + y^2 + 3(x-iy) - 3 \over (x-1)^2 + y^2} \\
&= ?
.\]

:::


