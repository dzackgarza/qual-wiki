---
order: 1
title: Precalculus Preliminaries 
---

# Precalculus Preliminaries 

## Geometry

:::{.fact}
The sum of the interior angles of an $n\dash$gon is $(n-2)\pi$, where each angle is $\frac{n-2}{n}\pi$.
:::

:::{.fact title="Standard forms of conic sections"}
\envlist

- Circle: $x^2 + y^2 = r^2$, or equivalently $\abs{z-a}=c$ or $\abs{z-a} = c\abs{z-b}$, the locus of points whose distances to two fixed points $A, B$ is a constant ratio not equal to 1, so $d_1/d_2 = c$:

![](figures/2021-12-04_00-49-30.png)

- Ellipse: $\qty{\frac x a}^2  + \qty{\frac y b}^2 = 1$, or equivalently $\abs{z-a} + \abs{z-b} = c$
  Equivalently, the locus of points whose *sums* of distances to two fixed points points $A, B$ is a constant, so $d_1 + d_2 = c$:

![](figures/2021-12-04_00-53-36.png)

- Hyperbola: $\qty{\frac x a}^2  - \qty{\frac y b}^2 = 1$ or equivalently $\abs{z-a} - \abs{z-b} = c$:

![](figures/2021-12-04_00-57-40.png)

  - Rectangular Hyperbola: $xy = \frac{c^2}{2}$.
- Parabola: $-4ax + y^2 = 0$.

:::

:::{.remark}
Another way to distinguish: write $f(x, y) = Ax^2 + Bxy + Cy^2 + \cdots$, then consider the discriminant $\Delta = B^2 - 4AC$:

- $\Delta < 0 \iff$ ellipse
  - $\Delta < 0$ and $A=C, B=0 \iff$ circle
- $\Delta = 0 \iff$ parabola
- $\Delta > 0 \iff$ hyperbola

:::

## Algebra

:::{.fact title="Completing the square"}
\[
x^2 + bx + c = 0 
\iff x^2 + bx {\color{red} + \qty{b\over 2}^2 - \qty{b\over 2}^2 } + c = 0 \\
\iff \qty{x+ \qty{b\over 2}^2}^2 + \qty{c - \qty{b\over 2}^2} = 0
.\]
More generally:
\[
ax^2 + bx + c = 0
\iff x^2 + {b\over a}x + {c\over a} = 0 \\
\iff x^2 + {b\over a}x + {\color{red} \qty{b/a \over 2}^2 - \qty{b/a \over 2}^2} + c = 0 \\
\iff (x + {b\over 2a})^2 + \qty{c - \qty{b\over 2a}^2} = 0
.\]
So given $ax^2+bx+c=0$, you can always write it as $a(x+d)^2 + e$ where $d\da b/2a$ and $e\da c - (b/2a)^2$.

:::


