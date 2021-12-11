---
order: 10
---

# Complex Arithmetic

## Fall 2021.1 #completed

:::{.warnings}
The question as written on the original qual has several errors.
What is below is the correct version of the inequality.
:::

:::{.problem title="?"}
1. Let $z_{1}$ and $z_{2}$ be two complex numbers.

(a) Show that 
\[
\left|1-\bar{z}_{1} z_{2}\right|^{2}-\left|z_{1}-z_{2}\right|^{2}=\left(1-\left|z_{1}\right|^{2}\right)\left(1-\left|z_{2}\right|^2\right)
\]

(b) Show that if $\left|z_{1}\right|<1$ and $\left|z_{2}\right|<1$, then $\left|\frac{z_{1}-z_{2}}{1-\bar{z}_{1} z_{2}}\right|<1 .$

(c) Assume that $z_{1} \neq z_{2}$. Show that $\left|\frac{z_{1}-z_{2}}{1-\bar{z}_{1} z_{2}}\right|=1$ if only if $\left|z_{1}\right|=1$ or $\left|z_{2}\right|=1$.
:::

:::{.solution}
**Part 1**:
For ease of notation, let $z=z_1$ and $w=z_2$
We want to show
\[
\abs{1- z\bar{w}} - \abs{z-w}^2 
= \qty{{1 - \abs{z}^2 }} \qty{{1 - \abs{w}^2}}
.\]

So write
\[
\abs{1- z\bar{w}} - \abs{z-w}^2 
&= (1-z\bar w)(1-\bar z w) - (z-w)(\bar z - \bar w) \\
&= 1 - z\bar w - \bar z w - \abs{z}^2\abs{w}^2 - \abs{z}^2 - \abs{w}^2 + w\bar{z} + z\bar{w} \\
&= 1 - \abs{z}^2\abs{w}^2 - \abs{z}^2 - \abs{w}^2 \\
&=(1-\abs z^2)(1-\abs w^2)
.\]


**Part 2 and 3**:
\[
\abs{z-w \over 1 - \bar z w}^2 \leq 1 
&\iff 0 \leq \abs{1 - \bar z w}^2 - \abs{z-w}^2 \\
&\iff 0 \leq (1 - \abs z^2 )(1 - \abs w^2)
,\]
where we've used part 1.
But this is clearly true when $\abs{z}, \abs{w} < 1$, so the RHS is positive.
Moreover if $\abs{z} = \abs{w} = 1$, the RHS is zero, yielding equalities at every step instead.


:::

## Spring 2021.1 #completed

:::{.problem title="?"}
Let $z_1, z_2$ be two complex numbers.

- Show that 
\[
\abs{1 - \bar z_1 z_2}^2 - \abs{z_1 - z_2}^2 = \qty{1 - \abs{z_1}^2}\qty{1 - \abs{z_2}^2}
.\]


- Show that if $\abs{z_1} < 1$ and $\abs{z_2} < 1$, then
\[
\left|\frac{z_{1}-z_{2}}{1-\bar{z}_{1} z_{2}}\right|<1
.\]

- Assume $z_1\neq z_2$, and show that
\[
\abs{z_1 - z_2 \over 1 - \bar z_1 z_2} = 1 \iff \abs{z_1} = 1 \text{ or } \abs{z_2} = 1
.\]

:::

:::{.solution}
Part 1:

Note that the RHS expands to
\[
1 - \abs{z_1}^2 - \abs{z_2}^2 + \abs{z_1 z_2}^2
.\]
The LHS expands to
\[
\cdots 
&= (1 - \bar{z_1} z_2)(1 - z_1 \bar z_2) - (z_1 - z_2)(\bar z_1 - \bar z_2) \\
&= 1 - \bar z_2 z_2 - z_1\bar z_2 + \abs{z_1 z_2}^2 - \qty{ \abs{z_1}^2 - \abs{z_2}^2 - z_1 \bar z_2 - \bar{z_1}z_2} \\
&= 1 + \abs{z_1 z_2}^2 - \abs{z_1}^2 - \abs{z_2}^2
.\]

Part b:
This isn't mentioned, but note that we need $\bar{z_1}z_2 \neq 1$.
Then
\[
\qty{ \abs{z_1 - z_2}^2 \over \abs{1 - \bar z_1 z_2 } } < 1 
&\iff \abs{z_1 - z_2}^2 - \abs{1 - \bar z_1 z_2}^2 < 0 \\
&\iff \qty{1 - \abs z_2^2}\qty{1 - \abs z_2^2} > 0 \\
&\iff \abs{z_1} < 1 \text{ and } \abs{z_2} < 1
.\]


Part c:
Suppose $z_1\neq z_2$, then
\[
\qty{ \abs{z_1 - z_2}^2 \over \abs{1 - \bar z_1 z_2 } } = 1 
&\iff \abs{z_1 - z_2}^2 - \abs{1 - \bar z_1 z_2}^2 = 0 \\
&\iff \qty{1 - \abs z_2^2}\qty{1 - \abs z_2^2} = 0 \\
&\iff \abs{z_1} = 1 \text{ or } \abs{z_2} = 1
.\]
:::

## Spring 2020 HW 1.2 #work 
Prove the following inequality, and explain when equality holds:
\[
\abs{z+w} \geq \abs{ \abs{z} - \abs{w} }
.\]


## Spring 2020 HW 1.5 #work

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

## Spring 2020 HW 1.6 #work

Use $n$th roots of unity to show that
\[
2^{n-1} \sin\qty{\pi \over n} \sin\qty{2\pi \over n} \cdots \sin\qty{(n-1)\pi \over n} = n
.\]

> Hint:
\[
1 - \cos(2\theta) &= 2\sin^2(\theta) \\
2 \sin(2\theta) &= 2\sin(\theta) \cos(\theta)
.\]



