---
order: 10
---

# Complex Arithmetic

## Fall 2021.1

## Spring 2021.1 #completed

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

## Spring 2020 HW 1.5 #work

:::{.problem title="?"}
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


:::{.solution}

**Part 1**: 
See Spring 2021.1 above.

**Part 2**: 
This is clearly meromorphic, as it's a rational function, and has a singularity only at $z$ such that $\bar w z = 1$.
This can only happen if $z, w \in S^1$: taking the modulus yields
\[
\bar w z = 1 \implies \abs{w}^2\abs{z}^2 = 1 
,\]
and moreover since $\abs{w}^2 \leq 1$ and $\abs{z}^2\leq 1$, the only way this product can be one is when $\abs{w}^2 = \abs{z}^2 = 1$.
This also forces $z=1/\bar w$.

The claim is that the singularity $1/\bar w$ is removable.
Note that $1\over w = \bar w$ on the circle, so $1/\bar{w} = \bar{\bar w} = 2$, so
\[
\qty{ z- \bar{w}\inv } \qty{w-z \over 1-\bar w z}
&= \qty{\bar w z - 1 \over \bar w} \qty{w-z \over 1-\bar w z} \\
&= \bar{w}\inv(w-z) \\
&= w(w-z) \\
&\converges{z\to \bar w\inv=w }\to 0
.\]

:::



## Spring 2020 HW 1.2 #work 
Prove the following inequality, and explain when equality holds:
\[
\abs{z+w} \geq \abs{ \abs{z} - \abs{w} }
.\]


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



