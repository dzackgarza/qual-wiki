# Standard Conformal Maps


:::{.theorem title="Classification of Conformal Maps"}
There are 8 major types of conformal maps:

| Type/Domains                                            | Formula                                   |
| ------------                                            | -------                                   |
| Translation                                             | $z\mapsto z + h$            |
| Dilation                                                | $z\mapsto cz$            |
| Rotation                                                | $z\mapsto e^{i\theta}$            |
| Sectors to sectors                                      | $z\mapsto z^n$                            |
| $\DD_{1\over 2} \to \HH_{1\over 2}$, the first quadrant | $z\mapsto {1+z \over 1-z}$                |
| $\HH\to S$                                              | $z\mapsto \log(z)$                        |
| $\DD_{1\over 2} \to L_{1\over 2}$                       | $z\mapsto \log(z)$                        |
| $S_{1\over 2} \to \DD_{1\over 2}$                       | $z\mapsto e^{iz}$                         |
| $\DD_{1\over 2} \to \HH$                                | $z\mapsto {1\over 2}\qty{z + {1\over z}}$ |
| $L_{1\over 2} \to \HH$                                  | $z\mapsto \sin(z)$                        |

:::

\todo[inline]{Pictures!}

:::{.proposition title="Half-plane to Disc"}
\[
F: \HH^\circ &\mapstofrom \DD^\circ \\
\ts{z\st \Im(z) > 0 } &\mapstofrom \ts{w\st \abs{w} < 1 } \\
z &\mapsto {i-z \over i+z} \\
i \qty{1-w \over 1+w} &\mapsfrom w
.\]

**Boundary behavior:**

- This maps $\RR\to \bd \DD$, where $F(\infty) = -1$, and as $x\in \RR$ ranges from $-\infty\to\infty$, $F(x)$ travels from $z=-1$ counter-clockwise through $S^1$ (starting at $z=-1$ and moving through the lower half first).

![[2021-07-29_19-02-54.png]]

So this extends to a map $\HH\to \DD$.

> Mnemonic: every $z\in \HH$ is closer to $i$ than $-i$.

:::

:::{.remark}
Some write a similar map:
\[
\HH^\circ &\to \DD^\circ \\
z &\mapsto {z-i \over z+i}
.\]
This is just a composition of the above map with the flip $z\mapsto -z$:
\[
- {i-z \over i + z} = {z-i \over i+z} = {z-i \over z+i}
.\]


:::

:::{.proposition title="Right half-plane to Disc"}
\[
\HH_{R} &\mapstofrom \DD \\
\ts{ z \st \Re(z) > 0 } &\mapstofrom \ts{ w \st \abs{w} < 1 } \\
z &\mapsto {1-z \over 1+z} \\
{1-w\over 1+w} &\mapsfrom w
.\]

Just map the *right* half-plane $\HH_R$ to the disc $\DD$ by precomposing with a rotation $e^{i\pi/2} = i$:
\[
\HH_{R} \to \HH &\to \DD \\
z \mapsto iz &\mapsto {i- (iz) \over i + (iz)} = {i(1-z) \over i(1+z) } = {1-z \over 1+z}
.\]

This can easily be inverted:
\[
&\quad w = {1+z \over 1+z} \\
&\implies -(1-w) + z(w+1) = 0 \\
&\implies z = {1-w \over 1+w}
.\]

**Boundary behavior**:
Just a rotated version of $\HH\to \DD$!

> Mnemonic: every $z\in \HH_R$ is closed to 1 than $-1$.

:::

:::{.proposition title="Sector to sector"}
For $0 < \alpha < 2$:
\[
F_\alpha: S_{\pi \over \alpha }^\circ &\mapstofrom S_{\pi}^\circ = \HH^\circ \\
\ts{z\st 0 < \Arg(z) < {\pi\over \alpha} } &\mapstofrom \ts{w\st 0 < \Arg(w) < \pi } \\
z &\mapsto z^\alpha \\
w^{1\over \alpha} &\mapsfrom w
.\]
Note that if you look at the image of $\HH$ under $z\mapsto z^{\alpha}$, you get
\[
\ts{z \st 0 < \Arg(z) < \pi } &\mapstofrom \ts{0 < \Arg(w) < \alpha \pi } 
.\]
For the inverse, choose a branch cut of $\log$ deleting the negative real axis, so $w\mapsto e^{1\over n \log w}$ here.

**Boundary behavior:**

- As $x$ travels from $-\infty\to 0$, $F_\alpha(x)$ travels *away* from infinity along the ray $\theta = \alpha \pi$, so $L = \ts{ e^{t \alpha \pi } \st t\in (0, \infty) }$, from $\infty\to 0$.
- As $x$ travels from $0\to \infty$, $F_\alpha(x)$ travels from $0\to \infty$ along $\RR$.

:::

:::{.proposition title="Sector to Disc"}
The unmotivated formula first:
\[
F: S_{\alpha} &\to \DD \\ \\
\ts{ z \st 0 < \Arg(z) < \alpha } &\mapstofrom \ts{ w \st \abs{w} < 1 } \\
z &\mapstofrom {z^{\pi\over \alpha} - i \over z^{\pi\over\alpha} + i}
.\]

Idea: compose some known functions.

![[image_2020-07-22-13-22-46.png]]

\[
S_{\alpha} &\to S_{\pi} = \HH \to \DD \\
z &\mapsto z^{\pi \over \alpha} \mapsto {z-i\over z+i}\evalfrom_{z= z^{\pi\over \alpha}}
.\]
:::

:::{.proposition title="Upper half-disc to first quadrant"}
\[
\ts{ z \st \abs{z} < 1,\, \Im(z) > 0 } &\mapstofrom \ts{ w \st \Re(w)>0,\, \Im(w) > 0}  \\
z &\mapsto {1+z \over 1-z} \\
{w-1\over w+1} &\mapsfrom w
.\]

- Why this lands in the first quadrant: 
  - Use that squares are non-negative and $z=x+iy\in \DD \implies x^2 + y^2 < 1$:
\[
f(z)=\frac{1-\left(x^{2}+y^{2}\right)}{(1-x)^{2}+y^{2}}+i \frac{2 y}{(1-x)^{2}+y^{2}}
.\]
- Why the inverse lands in the unit disc:
  - For $w$ in Q1, the distance from $w$ to 1 is smaller than from $w$ to $-1$.
  - Check that if $w=u+iv$ where $u, v>0$, the imaginary part of the image is positive:

\[
{w-1 \over w+1} 
&= { (w-1) \bar{(w+1)} \over \abs{w+1}^2}\\
&={ \qty{u-1 + iv} \qty{u+1-iv} \over (u+1)^2 + v^2 } \\
&= {u^2 + v^2 + 1 \over (u+1)^2 + v^2}
+ i\qty{ 2v \over (u+1)^2 + v^2}
.\]


**Boundary behavior**:

- On the upper half circle \( \ts{ e^{it } \st t\in (0, \pi)  } \), write 
\[
f(z)=\frac{1+e^{i \theta}}{1-e^{i \theta}}=\frac{e^{-i \theta / 2}+e^{i \theta / 2}}{e^{-i \theta / 2}-e^{i \theta / 2}}=\frac{i}{\tan (\theta / 2)}
,\]
  so as $t$ ranges $0\to \pi$ we have $f(z)$ ranging from $0\to i\infty$ along the imaginary axis.

- As $x$ ranges from $-1\to 1$ in $\RR$, $f(z)$ ranges from $0\to \infty$ with $f(0) = 1$.
:::

:::{.proposition title="Log: Upper half-plane to horizontal strip"}
\[
\HH &\mapstofrom \RR \cross (0, \pi) \\
\ts{ z \st \Im(z) > 0 } &\mapstofrom \ts{ w \st \Im(z) \in (0, \pi ) } \\
z &\mapsto \log(z) \\
e^w &\mapsfrom w
.\]

- Why this lands in a strip: use that $\arg(z) \in (0, \pi)$ and $\log(z) = \abs{z} + i\arg(z)$.

**Boundary behavior**:

- As $x$ travels from $-\infty \to 0$, $F(x)$ travels horizontally from $\infty + i\pi$ to $-\infty + i\pi$.
- As $x$ travels from $o\to \infty$, $F(x)$ travels from $-\infty\to\infty$ in $\RR$.

:::

:::{.remark}
This extends to a function $\CC\sm\RR^{\leq 0} \to \RR \cross (-\pi, \pi)$.
Circles of radius $R$ are mapped to vertical line segments connecting $\ln(R) + i\pi$ to $\ln(R) - i\pi$, and rays are mapped to horizontal lines.
:::

:::{.remark}
One can find other specific images of the logarithm:
\[
\ts{ z \st \abs{z} < 1,\, \Im(z) > 0 } &\mapstofrom \RR^{<0} \cross (0, \pi ) \\
\ts{ z \st \abs{z} > 1,\, \Im(z) > 0 } &\mapstofrom \RR^{>0} \cross (0, \pi ) \\
.\]

For the upper half-disc to the negative horizontal half-strip:
  - As $x$ travels $0\to 1$ in $\RR$, $\log(x)$ travels from $-\infty\to 0$.
  - As $x$ travels from $-1$ to $1$ along $S^1\intersect \HH$, $\log(x)$ travels from $0\to i\pi$ vertically.
  - As $x$ travels from $-1\to 0$, $\log(x)$ travels from $0+i\pi\to i-\infty+i\pi$ along the top of the strip.

:::

## Logs and Exponentials

:::{.proposition title="Upper half-plane to horizontal strip"}
\[
F: \HH \to \RR \times i(0, i\pi) \\
z &\mapsto \Log(z) \\
e^w &\mapsfrom w
.\]


![](figures/2021-11-28_18-09-31.png)

:::

:::{.proposition title="Half-discs to half strips"}
\[
F: \DD \intersect \HH &\to \RR_{<0} \times i (0, i\pi) \\
z &\mapsto \Log(z) \\
e^w &\mapsfrom w
.\]


![](figures/2021-11-28_17-56-47.png)

:::

:::{.proposition title="Vertical half-strip to right half-disc"}
\[
F: \qty{{-\pi \over 2}, {\pi \over 2}} \cross i\RR &\to \ts{\abs{z} < 1,\, \Re(z) > 0} \\
z &\mapsto e^{iz} \\
-i\Log(w) &\mapsfrom w
.\]

![](figures/2021-11-28_18-22-45.png)

This is essentially polar coordinates: write $e^z = e^{-y} e^{ix}$, then $x\in (-\pi/2, \pi/2)$ and $y\in (0, \infty)$ so this fills out a half-disc as $x,y$ vary.
:::


:::{.proposition title="Half-disc to upper half-plane"}
\[
F: ? &\mapstofrom ? \\
z & \mapsto -{1\over 2}\qty{z + z\inv} \\
.\]

:::

