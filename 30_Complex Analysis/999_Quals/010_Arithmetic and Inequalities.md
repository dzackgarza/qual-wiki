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

## Spring 2020 HW 1.5 #completed

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
- $F$ is a bijection.

:::

:::{.solution}

**Part 1**: 
See Spring 2021.1 above.

**Part 2, holomorphicity**: 
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

**Part 2, being a bijection**: 
This follows from finding an explicit inverse, using that $F^2 = \id$:
\[
F(F(z))
&= \frac{w- \qty{ \frac{w-z}{1-\bar{w} z} } }{1-\bar{w} 
\qty{ \frac{w-z}{1-\bar{w} z} } } \\
&= \frac{w(1-\bar{w} z)-(w-z)}{q-\bar{w} z-\bar{w}(w-z)} \\
&= \frac{w-|w|^{2} z-w+z}{1-\bar{w} z-|w|^{2}+\bar{w} z} \\
&= \frac{z\left(1-|w|^{2}\right)}{1-|w|^{2}} \\
&= z
.\]


**Part 2, being an involution**: 
A direct check shows that $F(w) = 0$, since the numerator vanishes, and $F(0) = {w - 0 \over 1 - 0} = w$.

**Part 3, preserving the circle**: 
Follows from the estimate in part 1.

:::

## Spring 2020 HW 1.2 #completed

:::{.problem title="?"}
Prove the following inequality, and explain when equality holds:
\[
\abs{z-w} \geq \abs{ \abs{z} - \abs{w} }
.\]

:::

:::{.solution}
\[
\abs{z-w}^2 
&= (z-w)(\bar z - \bar w) \\
&= \abs{z}^2 + \abs{w}^2 - z\bar{w} - \bar{z} w \\
&= \abs{z}^2 + \abs{w}^2 - 2\Re(\bar w z) \\
&\geq \abs{z}^2 + \abs{w}^2 - 2\abs{\bar w }\abs{z} \\
&\geq \qty{ \abs{z} - \abs{w} }^2
,\]
and taking square roots introduces an absolute value on the final term.
Here we've used the basic estimate 
\[
\Re(z) \leq \abs{z} \implies -\Re(z) \geq -\abs{z}
.\]



:::

## Spring 2020 HW 1.6 #work


:::{.problem title="?"}
Use $n$th roots of unity to show that
\[
2^{n-1} \sin\qty{\pi \over n} \sin\qty{2\pi \over n} \cdots \sin\qty{(n-1)\pi \over n} = n
.\]

> Hint:
\[
1 - \cos(2\theta) &= 2\sin^2(\theta) \\
2 \sin(2\theta) &= 2\sin(\theta) \cos(\theta)
.\]
:::


:::{.solution}
Write $\zeta_n\da e^{2\pi i /n}$ and $\Phi_n = {x^n-1\over x-1}$, note that $\Phi_n(1) = n$.
We can then write $\sin\qty{j\pi\over n} = \zeta_n^j$, so using that $\sin(z) = (2i)\inv(z + z\inv)$,
\[
\prod_{j=1}^{n-1} \sin \left(\frac{j \pi}{n}\right)
&=\prod_{j=1}^{n-1} \frac{1}{2 i}
\qty{\zeta_n^j - \zeta_n^{-j}}
&=\left(\frac{1}{2 i}\right)^{n-1} \prod_{j=1}^{n-1} e^{i j \pi / n} \prod_{j=1}^{n-1}\left(1-e^{-2 i j \pi / n}\right)\\
&=\left(\frac{1}{2 i}\right)^{n-1} \prod_{j=1}^{n-1} e^{i j \pi / n} \prod_{j=1}^{n-1}\left(1-\zeta_{n}^{j}\right)\\
&=\left(\frac{1}{2 i}\right)^{n-1} \exp \left(\sum_{j=1}^{n-1} \frac{i j \pi}{n}\right) \Phi_{n}(1)\\
&=\left(\frac{1}{2 i}\right)^{n-1} \exp \left(\frac{i \pi}{n} \sum_{j=1}^{n-1} j\right) \Phi_{n}(1)\\
&=\left(\frac{1}{2 i}\right)^{n-1} \exp \left(\frac{(n-1) i \pi}{2}\right) \Phi_{n}(1)\\
&=\left(\frac{1}{2 i}\right)^{n-1}\left(e^{i \pi / 2}\right)^{n-1} \Phi_{n}(1)\\
&=\left(\frac{1}{2 i}\right)^{n-1} i^{n-1} \Phi_{n}(1)\\
&=\left(\frac{1}{2}\right)^{n-1} \Phi_{n}(1)\\
&=\frac{n}{2^{n-1}}
.\]
:::




