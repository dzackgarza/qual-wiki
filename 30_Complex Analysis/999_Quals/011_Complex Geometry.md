---
order: 11
---

# Complex Geometry

## Spring 2020 HW 1.1  #completed

:::{.problem title="?"}
Geometrically describe the following subsets of $\CC$:

a. $\abs{z-1} = 1$
b. $\abs{z-1} = 2\abs{z-2}$
c. $1/z = \bar z$
d. $\Re(z) = 3$
e. $\Im(z) = a$ with $a\in \RR$.
f. $\Re(z) > a$ with $a\in \RR$.
g. $\abs{z-1} < 2\abs{z-2}$

:::

:::{.solution}
\envlist

a. A circle of radius 1 about $z=1$.
b. A circle, using that Apollonius circles are characterized as the locus of distances whose ratios to some fixed points $A, B$ are constant.
  To actually compute this:
  \[
  \abs{z-1}^2 &= 4\abs{z-2}^2 \\
  \implies (x-1)^2 + y^2 - 4\qty{(x-2)^2 + y^2 } &=0 \\
  -3x^2 + 14x - 3y^2 - 15 &= 0 && \star\\
  \implies x^2 - {14\over 3}x + y^2 + 5 &= 0 \\
  \implies (x- {14\over 2\cdot 3})^2 - {14\over 2\cdot 3}^2 + y^2 + 5 &= 0 \\
  \implies (x-{14\over 6})^2 + y^2 = \qty{2\over 3}^2
  ,\]
  which is a circle of radius $2/3$ with center $\qty{{14\over 6}, 0}$.
  To avoid the calculation, use
  \[
  Ax^2 + Bxy + Cy + \cdots = 0,\quad A=1, B=0, C=1 \implies \Delta \da B^2 - 4AC < 0
  ,\]
  which is an ellipse, and since $A=C$ it is in fact a circle.


c. $S^1$, using that ${1\over z} = {\bar{z} \over z\bar{z}} = {\bar z\over \abs{z}^2}$ and if this equals $\bar{z}$, then $\abs{z}^2=1$.
Alternatively, $1 = \bar{z}z = \abs{z}^2$.
d. Vertical line through $z=3$.
e. Horizontal line through $z=ia$.
f. Region to the right of the vertical line through $z=a$.
g. Exterior of a circle: same calculation is (2), replacing $=0$ with $<0$.
Note that the line marked $\star$ involves dividing by a negative, so this flips the sign, and we get $\cdots > \qty{2\over 3}^2$ at the end.
:::

## Spring 2020 HW 1.4 #work 

:::{.problem title="?"}
\envlist

a. Prove that if $c>0$,
\[
\abs{w_1} = c\abs{w_2} \implies \abs{w_1 - c^2 w_2} = c\abs{w_1 - w_2}
.\]

b. Prove that if $c>0$ and $c\neq 1$, with $z_1\neq z_2$, then the following equation represents a circle:
\[
\abs{z-z_1 \over z-z_2} = c
.\]
Find its center and radius.

> Hint: use part (a)

:::

## Spring 2020 HW 1.11 #work

:::{.problem title="?"}
Prove that the distinct complex numbers $z_1, z_2, z_3$ are the vertices of an equilateral triangle if and only if
\[
z_{1}^{2}+z_{2}^{2}+z_{3}^{2}=z_{1} z_{2}+z_{2} z_{3}+z_{3} z_{1}
.\]
:::

## Spring 2020 HW 1 # 5


:::{.problem title="?"}
\envlist

a. Let $z, w \in \CC$ with $\bar z w \neq 1$. 
Prove that
\[
\abs{w-z \over 1 - \bar w z} < 1 \quad\text{ if } \abs{z}<1,~ \abs{w} < 1
\]
with equality when $\abs{z} = 1$ or $\abs{w} = 1$.

b. Prove that for a fixed $w\in \DD$, the mapping $F: z\mapsto {w-z \over 1 - \bar w z}$ satisfies

- $F$ maps $\DD$ to itself and is holomorphic.
- $F(0) = w$ and $F(w) = 0$.
- $\abs{z} = 1$ implies $\abs{F(z)} = 1$.
:::


