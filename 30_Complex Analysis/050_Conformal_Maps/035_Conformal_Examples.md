# Conformal Map Examples and Exercises 

:::{.example title="Mapping the half-disc to the half-plane"}
\[
(z: i, 1, -1) = \qty{z-1 \over z+1} \qty{i-1 \over i+1}\inv
.\]

#work

:::

:::{.example title="?"}
\envlist

- $(z; i, 1, -1): \DD\to \HH$
- $(z; 0, -1, 1): \DD \intersect \HH \to Q_1$.

A Mobius transformation of the following form:
\[
1 &\mapsto 3 \\
i &\mapsto 0 \\
2 &\mapsto -1
.\]
Write $T(z) = (z; 1, i, 2)$ and $S(w) = (w; 3, 0, -1)$.
Set $T(z) = S(w)$ and solve for $w$ to get
\[
\frac{-3 z+3 i}{(7-4 i) z+(-8+5 i)}
.\]
:::

:::{.example title="Cayley transform (important!!)"}
The fractional linear transformation given by $F(z) = {i - z \over i + z}$ maps $\DD\to \HH$ with inverse $G(w) = i {1-w \over 1 + w}$.
The following transformation is very important:
\[
F: \DD &\to \HH \\
z &\mapsto {i-z\over i+z} \\
i{1-w\over 1+w} &\mapsfrom w
.\]
:::

:::{.exercise title="Upper half-disc to upper half-plane"}
Find a conformal map from the upper half-disc to the upper half-plane.

#work

:::

:::{.solution}
![[2021-07-29_19-26-39.png]]
:::

:::{.exercise title="Half disc to full disc"}
Find a conformal map from $\ts{z\in \CC \st \abs{z} < 1, \Im(z) > 0}$ to $\DD$.

#work

:::

:::{.solution}
Note that $z\mapsto z^2$ doesn't actually work, because the image is $\DD\sm \RR_{\geq 0}$ and has a slit deleted.
Instead compose:

- $z\mapsto i{z-1\over z+1}$, which maps $\DD\to \HH$ and restricts to map $\DD \intersect \HH \to Q_1$.
- $z\mapsto z^2$, which maps $Q_1\to \HH$
- $z\mapsto {z-i\over z+i}$ which maps $\HH\to \DD$.
:::
