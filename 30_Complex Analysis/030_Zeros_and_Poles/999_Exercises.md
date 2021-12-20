# Exercises

## Singularities and Zeros

:::{.exercise title="Residues and classifying singularities"}
Classify the singularities of 
\[
f(z) = {z^3+1\over z^2(z+1)}
.\]

#completed

:::

:::{.concept}
Showing a pole $z_0$ of $f$ is order $n$: show that $z_0$ is a zero of order $n$ of $1/f$, i.e. $1/f = (z-z_0)^nh(z)$ with $h$ nonvanishing in a neighborhood of $z_0$.
:::

:::{.solution}
Write $f(z) = p(z)/q(z)$ and factor $p$: a principal root is $\omega = e^{i\pi 3}$, so 
\[
p(z) 
&= (z-\omega\zeta_3^0)(z-\omega\zeta_3^1)(z-\omega\zeta_3^2) \\
&= (z-e^{i\pi\over 3})(z-e^{3i\pi \over 3})(z-e^{5i\pi \over 3}) \\
&= (z+1)(z-\omega)(z-\bar\omega)
,\]
so $z=-1$ is a removable singularity of $f$.
Alternatively, note that ${z^3+1 \over z+1} = z^2-z+1$ and cancel the common term.

Note that $z=0$ is a zero of order $n=2$ of $1/f(z)$, since $1/f(z) = z^2h(z)$ where $h$ is nonvanishing in a neighborhood of $0$.
Thus $z=0$ is a pole of order $n=2$ of $f$.
The residue is computed as
\[
\Res_{z=0} f(z) 
&= {1\over (1-1)!} \lim_{z\to 0} \dd{}{z} (z-0)^2f(z) \\
&= \dd{}{z} {z^3+1\over z+1}\evalfrom_{z=0} \\
&= \qty{ {3z^2\over z+1} - {(z^3+1)\cdot 1\over (z+1)^2} }\evalfrom_{z=0} \\
&= -1
.\]

Alternatively, expand as a Laurent series about $z=0$:
\[
f(z) 
&= z^{-2}(z^3 + 1) {1\over 1+z} \\
&= (z + z^{-2})\sum_{k\geq 0}(-z)^k \\
&= (z-z^2 + z^3 - \cdots) + (z^{-2} - z\inv + 1 - z + \cdots)
,\]
and read off the coefficient of $z\inv$.

:::

:::{.exercise title="Classifying singularities"}
Classify the singularities at $z=0$ of the following
\[
f_1(z) &= {\Log(1+z) \sin(z) \over z^2} \\
f_2(z) &= e^{\sin\qty{1\over z}} \\
f_3(z) &= {1+z \over e^z-1}
.\]

#completed
:::

:::{.solution}
$f_1$: removable, evident from Laurent expansion at $z=0$:
\[
z^{-2}\Log(1+z)\sin(z) 
&= z\inv \qty{ \sum_{k\geq 1} { (-z)^k \over k} }
\qty{z - { z^3 \over 3!} + { z^5 \over 5!} - \cdots} \\
&= z^{-2}
\qty{ -z+ { z^2 \over 2}  - { z^3 \over 3} + \cdots}
\qty{z - { z^3 \over 3!} + { z^5 \over 5!} - \cdots} \\
&= z^{-2}\qty{ z^2(-1) + z^3\qty{1\over 2} + z^2\qty{ -{ 1 \over 3!} - { 1 \over 3} } + \cdots } \\
&= 1 + {z \over 2} + \cdots
.\]

$f_2$: essential, evident from a sequence like $z_k \da \qty{k\cdot {\pi\over 2} }\inv$ which makes $\sin(z_k)$ oscillate between 0 and 1.

$f_3$: pole of order 1 with residue 1, evident after some slightly clever Laurent manipulations:
\[
{1\over e^z-1} 
&= {1 \over z + {1\over 2}z^2 + \cdots} \\
&= {1 \over z\qty{1 + {1\over 2}z + \cdots} } \\
&\da {1\over z \qty{1 + p(z)}} && p(z) \da {1\over 2} z + {1\over 3!}z^2 + \cdots \\
&= z\inv \sum_{k\geq 0}(-p(z))^k z^k \\
&= z\inv \qty{1 - zp(z) + z^2p(z)^2 - z^3p(z)^3 + \bigo(z^4)} \\
&= z\inv\qty{1- \bigo(z^2) + \bigo(z^4) - \bigo(z^6) } \\
&={1\over z} - \bigo(z) + \bigo(z^3)
.\]

:::

:::{.exercise title="Singularities of of $\sin(z)/z$"}
Show that $\sin(z)/z$ has no poles.

#completed
:::

:::{.solution}
Heuristic: $\sin(z)$ has a zero of order 1, so the $z$ in the denominator exactly cancels it.
Explicitly, this is evident from the Laurent expansion about zero:
\[
z\inv \sin(z) = z\inv\qty{ z - {z^3 \over 3!} + {z^5\over 5!} - \cdots} = 1 - {z^2\over 3!} + {z^4 \over 5!} - \cdots
,\]
which has no factors of $z^{-k}$.
So $z=0$ is a removable singularity.
:::

:::{.exercise title="Singularities of $1\over e^z - 1$"}
Classify the singularities and compute the residues at any poles of the following function:
\[
f(z) \da {1\over e^z - 1}
.\]
:::

:::{.solution}
Note $e^z = 1$ when $z=z_k\da 2\pi k$ for $k\in \ZZ$, and the claim is that these are all poles of order 1 of $f(z)$.
These are clearly poles of some order, since they are zeros of $1/f$, and the order will be the smallest $n$ for which $\lim_{z\to z_k}(z-z_k)^n f(z)$ exists.
Start by computing the first:
\[
\lim_{z\to z_k}(z-z_k)f(z) = \lim_{z\to z_k} {z-z_k\over e^z - 1} \equalsbecause{\text{LH}} \lim_{z\to z_k} {1\over e^z} = e^{-z_k} = 1
.\]
:::


:::{.exercise title="Entire functions with poles at infinity"}
Characterize all entire functions with a pole of order $m$ at $\infty$.

#completed
:::

:::{.solution}
Since $f$ is entire, $f(z) = \sum_{k\geq 0 } c_k z^k$.
Expanding about $z_0=\infty$, we have $f(1/z) = \sum_{k\geq 0} c_k z^{-k} = c_0 + {c_1\over z} + \cdots$.
If $z_0=\infty$ is a pole of order $m$, then $c_m\neq 0$ but $c_{>m} = 0$, which forces $f(z) = \sum_{0\leq k \leq m} c_k z^k$ to be a polynomial of degree $m$.
:::

## Orders of poles/zeros

:::{.exercise title="?"}
Determine the order of the pole of 

- ${1\over z\sin(z)}$ at $z_0 = 0$.
- ${e^{z^2}-1\over z^4}$ at $z_0=0$

#completed
:::

:::{.solution}
- Order 2:
\[
\lim_{z\to 0}z^0 f(z) &= \infty\\
\lim_{z\to 0}z^1 f(z) &= \infty\\
\lim_{z\to 0}z^2 f(z) &= 1 \neq 0 
,\]
using that $z/\sin(z) \convergesto{z\to 0} 1$.

- Order 2: apply L'Hopital as necessary
\[
\lim_{z\to 0}z^0 f(z) &= \infty\\
\lim_{z\to 0}z^1 f(z) &= \infty\\
\lim_{z\to 0}z^2 f(z) &= 1 \neq 0 
.\]
  Alternatively, take the Laurent expansion:
  \[
  f(z) 
  &= z^{-4}(1 + z^2 + {1\over 2!} (z^2)^2 + {1\over 3!} (z^2)^3 + \bigo(z^4) - 1) \\
  &= z^{-2} + {1\over 2!} + {1\over 3!} z^2 + \bigo(z^4)
  .\]

:::

:::{.exercise title="?"}
Find the orders of zeros of the following functions:

- $(e^z-1)^3$

#completed
:::

:::{.solution}
\envlist

- $z=0$ of order 3: if $z_0$ is order $n$ for $f$, then it's order $kn$ for $f^k$.
  So check that $e^z-1$ has a root $z=0$ and $\dd{}{z}e^z-1\mid_{z=0} = e^z\mid_{z=0}\neq 0$, making it order 1.
:::

## Misc

:::{.exercise title="Essential singularities"}
Fix $a\in \CC\union\ts{\infty}$ and let $f(z) \da e^{1\over z^2}$.
Find a sequence $z_k\to 0$ such that $f(z_k) \convergesto{k\to\infty} a$

#completed
:::

:::{.solution}
\envlist

- For $a\in \RR_{< 0}$: take $z_k\da {1\over \Log(a) + 2\pi i k - {\pi i \over 2}}$  
  Then $f(z_k) = a$ for all $k$ but $z_k\to 0$.
- For $a=0$: take $z_k = -1/k$.
- For $a=\infty$, take $z_k = 1/k$.
- For anything else, take $z_k \da {1\over \Log(a) + 2\pi i n}$ if $a \in \RR_{\geq 0}$.
  Again $f(z_k) = a$ for all $k$ but $z_k\to 0$.
:::

