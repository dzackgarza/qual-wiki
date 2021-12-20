# Exercises: Integrals

## Rational Functions 

:::{.remark}
For guidelines for what techniques to use,
[see this very detailed note](https://math.mit.edu/~jorloff/18.04/notes/topic9.pdf).

Some good computations [here](https://math.mit.edu/~jorloff/18.04/notes/topic9.pdf).

Let $\deg$ denote the $z\dash$adic valuation, so $\deg(p(x)/q(x)) = \deg(p) - \deg(q)$.
A summary of techniques:

- Rational functions in $z$ with $\deg(f) \leq -2$: 
  Semicircle. Always get $\int_\RR f = \sum_{z_0\in \HH} \Res_{z=z_0}f(z)$.

- Rational function in $z$ against a single $\sin$ or $\cos$:
  - Semicircles. Realize $\int_\RR f(z)\cos(z) = \Re\qty{\int_\RR f(z)e^{iz}}$.

![](figures/2021-12-10_18-24-10.png)

- Rational functions in $z$:

  - $f(z) \sim 1/z^{1+\eps}$: semicircular contours.

    ![figures/2021-07-29_18-37-57.png](figures/2021-07-29_18-37-57.png)
    
    - The relevant theorem: $f(z) \leq {M \over \abs{z}^{1+\eps} }$ for $\abs{z} \gg 0$ implies $\int_{C_R} f \convergesto{R\to\infty} 0$.

  -  $f(z) \sim 1/z$: rectangular contours.

    ![figures/2021-07-29_18-38-24.png](figures/2021-07-29_18-38-24.png)
    
    - The relevant theorem: $f(z) \leq {M \over \abs{z} }$ for $\abs{z} \gg 0$ implies $\int_{C_R} f(z) e^{i\alpha z} \convergesto{R\to\infty} 0$ where for $\alpha>0$ take $C_R$ to be the left rectangular contour, and $\alpha>0$ take $C_R$ the right.

- Rational functions of $\cos, \sin$:
  - Set
	\[
	2\cos(z) = z + z\inv, \quad 2\sin(z) = z - z\inv, && \dtheta = {\dz\over iz}
	.\] 
	This reduces to a residue count in $\abs{z} \leq 1$.
	
- $f(z) \approx \cos(z), \sin(z), \tan(z), \cdots$: check if $\displaystyle\int f \approx \Re\displaystyle\int (g(e^{iz}))$.

- $\int_\RR f(x)\cos(x) = \Im(f(z)e^{iz})$ or $\int_\RR f(x)\sin x = \Im(f(z)e^{iz})$: use a semicircular contour, then if $f(re^{i\theta})\to 0$ uniformly as $r\to \infty$ for $0<\theta<\pi$, then just picks up the residues in $\HH$.

- $\int_{\RR_{\geq 0}} f(x)x^\alpha$ for $\alpha$ rational with $\abs{\alpha} < 1$ 
  - For $f$ rational with $\deg f\leq -2$, take a keyhole

  ![](figures/2021-12-14_17-19-31.png)

- $\int_{\RR_{\geq 0}} f(x) \log(x)$: indented semicircular contours

![](figures/2021-12-14_17-20-48.png)

:::

:::{.exercise title="$1/(1+x^2)^2$"}
\[
\int_\RR {1 \over (1+x^2)^2} = {\pi \over 2}
.\]

#completed 

:::

:::{.solution}
Use that $f(z) \sim 1/z^4$:

![figures/2021-07-29_18-40-40.png](figures/2021-07-29_18-40-40.png)

Then 
\[
\int_{C_1 + C_R} f = \int_{C_1} f + \int_{C_R} f = 2\pi i \Res_{z=i} {1\over (1+z^2)^2}
.\]

Note $f$ factors:
\[
f(z) = {1 \over \qty{(z-i)(z+i)}^2 }
,\]
so $z=i$ is a pole of order 2.


Compute the residue within the contour:
\[
\Res_{z=i} f(z) 
= \lim_{z\to i} \dd{}{z} {1\over (z+i)^2}
= - {2 \over (z+i)^3 }\evalfrom_{z=i}
= - {2\over (2i)^3 }
= {1\over 4i} = -{i\over 4}
.\]

Now solve:
\[
2\pi i \qty{- {i\over 4}} = \int_{C_1}f + \int_{C_R} f \da I_R + \int_{C_R}f \implies I_R = {\pi \over 4} - \int_{C_R} f
.\]

Note $I_R \convergesto{R\to \infty} I \da \int_\RR f$, so it suffices to show
the semicircular error term vanishes as $R\to \infty$. 
Parameterize $C_R = \ts{z=R e^{it} \st t\in [0, \pi]}$, so $\abs{z} = R$ on $C_R$.
Letting $z=e^{it}$, $\dz =iR e^{it}\dt$,
\[
\abs{\int_{C_R} f(z) \dz }
&= \abs{\int_{C_R} {1\over (1+z^2)^2} \dz } \\
&\leq \int_{C_R}\abs{ {1\over (1+z^2)^2} } \dz \\
&= \int_{C_R} {1\over \abs{1+z^2}^2 } \dz\\
&\leq \int_{C_R} {1\over \qty{1 - \abs{z}^2 }^2 } \dz \\
&= \int_{C_R} {1\over \qty{1 - R^2 }^2 } \dz \\
&= {1\over \qty{1 - R^2 }^2 } \int_{C_R} \dz\\
&= {1\over \qty{1 - R^2 }^2 } \cdot \length(C_R) \\
&= {1\over \qty{1 - R^2 }^2 } \cdot \qty{1\over 2}2\pi R \\
&= {\pi R \over R^4 + O(R^3)} \\
&= \pi\qty{ 1 \over R^3 + O(R^2)} \\
&\convergesto{R\to\infty} 0
,\]
where we've used a variant of the triangle inequality:
\[
\abs{a\pm b} \geq \abs{ \abs{a} - \abs{b} } \implies {1\over \abs{a \pm b}} \leq {1\over \abs{a} - \abs{b} }
.\]





:::

:::{.exercise title="$1/x^4+1$"}
#work

\[
\int_\RR {1 \over x^4 + 1} = {\pi \sqrt{2} \over 2}
.\]
:::

:::{.solution}

![figures/2021-07-29_18-41-05.png](figures/2021-07-29_18-41-05.png)

:::

:::{.exercise title="$\cos(x) / x^2 + b^2$"}
#work
\[
\int_{0}^{\infty} \frac{\cos (x)}{x^{2}+b^{2}} d x=\frac{\pi \mathrm{e}^{-b}}{2 b} .
.\]
:::

:::{.solution}
Extend to $\int_\RR$ using that $f$ is even.

![figures/2021-07-29_18-42-38.png](figures/2021-07-29_18-42-38.png)

:::

:::{.exercise title="Trigonometric functions"}
#work
\[
\int_{0}^{2 \pi} \frac{d \theta}{1+a^{2}-2 a \cos (\theta)}
= \begin{cases}\frac{2 \pi}{a^{2}-1} & \text { if }|a|>1 \\ \frac{2 \pi}{1-a^{2}} & \text { if }|a|<1\end{cases}
.\]
:::

:::{.solution}
Write $2\cos(z) = z + z\inv$ on $S^1$ to get
\[
=\int_{|z|=1} \frac{1}{i\left(\left(1+a^{2}\right) z-a\left(z^{2}+1\right)\right)} d z
.\]

:::

## Branch Cuts

:::{.exercise title="?"}
\[
\int_0^\infty {x^{1\over 3} \over 1 + x^2} \dx = {\pi \over \sqrt 3}
.\]
:::

:::{.solution}

![figures/2021-07-29_18-51-17.png](figures/2021-07-29_18-51-17.png)

:::

:::{.exercise title="?"}
\[
\int_{1}^{\infty} \frac{d x}{x \sqrt{x^{2}-1}} = {\pi \over 2}
.\]
:::

:::{.solution}

![figures/2021-07-29_18-53-35.png](figures/2021-07-29_18-53-35.png)

:::


# Exercises


:::{.exercise}
Show that the complex zeros of $f(z) \da \sin(\pi z)$ are exactly $\ZZ$, and each is order 1.
Calculate the residue of $1/\sin(\pi x)$ at $z=n\in \ZZ$.
:::

![figures/image_2021-05-17-13-32-46.png](figures/image_2021-05-17-13-32-46.png)

![figures/image_2021-05-17-13-32-57.png](figures/image_2021-05-17-13-32-57.png)

![figures/image_2021-05-17-13-33-12.png](figures/image_2021-05-17-13-33-12.png)

![figures/image_2021-05-17-13-33-30.png](figures/image_2021-05-17-13-33-30.png)

:::{.exercise title="?"}
\[
\int_\RR {1 \over (1+x^2)^2} \dx
.\]
:::

:::{.solution}
\envlist

- Factor $(1+z^2)^2 = ((z-i)(z+i))^2$, so $f$ has poles at $\pm i$ of order 2.
- Take a semicircular contour $\gamma \da I_R \union D_R$, then $f(z) \approx 1/z^4 \to 0$ for large $R$ and $\int_{D_R} f \to 0$.
- Note $\int_{I_R} f \to \int_\RR f$, so $\int_\gamma f \to \int_\RR f$.
- $\int_\gamma f = 2\pi i \sum_{z_0} \Res_{z=z_0} f$, and $z_0 = i$ is the only pole in this region.
- Compute
\[
\Res_{z=i} f 
&= \lim_{z\to i} {1\over (2-1)!} \dd{}{z} (z-i)^2 f(z) \\
&= \lim_{z\to i} \dd{}{z} {1\over (z+i)^2 } \\
&= \lim_{z\to i} {-2 \over (z+i)^3 } \\
&= -{2 \over (2i)^3 } \\
&= {1\over 4i} \\ \\
\implies
\int_\gamma f &= {2\pi i \over 4i} = \pi/2
,\]

:::

:::{.exercise title="?"}
Use a direct Laurent expansion to show
\[
\Res_{z=0} {1\over z-\sin(z)} = {3! \over 5\cdot 4}
.\]

> Note the necessity: one doesn't know the order of the pole at zero, so it's unclear how many derivatives to take.

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

:::{.exercise title="?"}
Compute
\[
\Res_{z=0} {1\over z^2 \sin(z)}
.\]
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

:::{.exercise title="Keyhole contour and ML estimate"}
Compute
\[
\int_{[0, \infty]} {\log(x) \over (1+x^2)^2}\dx 
.\]
:::

:::{.solution}
Factor $(1+z^2)^2 = (z+i^2(z-i)^2$.
Take a keyhole contour similar to the following:

![attachments/image_2021-06-09-02-11-59.png](attachments/image_2021-06-09-02-11-59.png)

Show that outer radius $R$ and inner radius $\rho$ circles contribute zero in the limit by the ML estimate?
Compute the residues by just applying the formula and manually computing derivatives:
\[
\Res_{z= \pm i} f(z) 
&= \lim_{z\to \pm i} \dd{}{z} {\log^2(z) \over (z\pm i)^2} \\
&= \lim_{z\to \pm i} {2\log(z) (z\pm i)^2 - 2(z\pm i)^2 \log^2(z) \over \qty{(z\pm i )^2}^2} \\
&= {
2\log(\pm i)(\pm 2i)^2 - 2(\pm 2i)^2 \log^2(\pm i)
\over {\qty{\pm 2i}}^4 } \\
&=_? {\pi \over 4}\pm {i\pi^2 \over 16}
.\]

> See p.4: <http://www.math.toronto.edu/mnica/complex1.pdf>

:::

:::{.exercise title="Sinc Function"}
Show
\[
\int_{(0, \infty)} {\sin(x) \over x }\dx = {\pi \over 2}
.\]
:::

:::{.solution}
Take an indented semicircle.
Let $I$ be the original integral, then 
\[
I = {1\over 2i} \int_\RR {e^{iz} - 1 \over z } \dz
.\]

:::

![figures/image_2021-05-17-13-33-55.png](figures/image_2021-05-17-13-33-55.png)
