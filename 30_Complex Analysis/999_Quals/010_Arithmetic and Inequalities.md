---
order: 10
---

# Complex Arithmetic

## Spring 2019.3 #complex/qual/work

^c8872d


:::{.problem title="?"}
Let $R>0$. Suppose $f$ is holomorphic on $\ts{z\st \abs{z} < 3R}$. Let
$$
M_{R}:=\sup _{|z| \leq R}|f(z)|, \quad N_{R}:=\sup _{|z| \leq R}\left|f^{\prime}(z)\right|
$$

a.
Estimate $M_{R}$ in terms of $N_{R}$ from above.

b.
Estimate $N_{R}$ in terms of $M_{2 R}$ from above.

:::


:::{.solution}
First note that by the maximum modulus principal, it suffices to consider sups on the boundary, i.e.
\[
M_R = \sup_{\abs{z} = R}\abs{f(z)}, \qquad N_R = \sup_{\abs{z} = R} \abs{f'(z)}
.\]


The second estimate: note that $M_R \leq M_{R'}$ whenever $R'>R$, since $\ts{\abs{z} \leq R} \subseteq \ts{\abs{z} \leq R'}$.
So apply Cauchy's formula to $\gamma\da \ts{ \abs{z}=R}$ for the first derivative.
Suppose 
Suppose $z_0 \in \DD_R(0)$, then any $D_R(z_0)$ is contained in $D_{2R}(0)$.
So for any such $z_0$, apply Cauchy's integral formula centered at $z_0$:
\[
f^{(1)}(z_0) &= {1\over 2\pi i }\oint_{\bd\DD_{R}(z_0)} {f(\xi)\over (\xi-z_0)^2 }\dxi \\
\implies 
\abs{ f^{(1)}(z_0)} 
&\leq {1\over 2\pi} \oint_{\bd\DD_{R}(z_0)} \abs{f(\xi)\over (\xi-z_0)^2 }\dxi \\
&= {1\over 2\pi} \oint_{\bd\DD_R(z_0)} { \abs{f(\xi)} \over \abs{\xi-z_0}^2 } \dxi \\
&= {1\over 2\pi} \oint_{\bd\DD_R(z_0)} { \abs{f(\xi)} \over R^2 } \dxi \\
&\leq {1\over 2\pi} \oint_{\bd\DD_R(z_0)} { \sup_{z\in \bd\DD_{R}(z_0) } \abs{f(z)} \over R^2 } \dxi \\
&= {1\over 2\pi} R^{-2} \sup_{} \abs{f(z)} \cdot 2\pi R
.\]

:::



## Spring 2021.1 #complex/qual/completed

^7d0c77

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

## Spring 2020 HW 1.5 #complex/qual/completed

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

## Spring 2020 HW 1.2 #complex/qual/completed

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

## Fall 2020.1, Spring 2020 HW 1.6 #complex/qual/completed

^b9b6b4

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

:::{.concept}
\envlist

- $\zeta_n \da e^{2\pi i \over n}$
- $\Phi_n(z) \da \prod_{1\leq j \leq n-1}(z-\zeta_n^j)$
- $\Phi_n(1) = n$, since $\Phi_n(z) = {z^n-1\over z-1} = \sum_{0\leq j\leq n-1} z^j$.
- $\sin(z) = \qty{e^{iz} - e^{-iz} \over 2i}$.
- $\prod_k \exp(c_k) = \exp\qty{\sum_k c_k}$.
:::

:::{.solution title="Newer"}
\[
\prod_{1\leq k \leq n-1} \sin\qty{k\pi\over n}
&= \prod_{1\leq k \leq n-1} {\omega_n^k - \omega_n^{-k} \over 2i} \\
&= \qty{1\over 2i}^{n-1} \prod_{1\leq k \leq n-1} \omega_n^{k} \qty{1 - \zeta_n^{-k}} \\
&= \qty{1\over 2i}^{n-1} \prod_{1\leq k \leq n-1} \exp\qty{i\pi k\over n} \prod_{1\leq k \leq n-1} \qty{1 - \zeta_n^{-k}} \\
&= \qty{1\over 2i}^{n-1} \exp\qty{ {i\pi\over n} \displaystyle\sum_{1\leq k \leq n-1} k } \prod_{1\leq k \leq n-1} \qty{1 - \zeta_n^{-k}} \\
&= \qty{1\over 2i}^{n-1} e^{i\pi n(n-1)\over 2n} \prod_{1\leq k \leq n-1} \qty{1 - \zeta_n^{-k}} \\
&= \qty{1\over 2}^{n-1}\qty{1\over i}^{n-1} \qty{ e^{i\pi \over 2} }^{n-1} \prod_{1\leq k \leq n-1} \qty{1 - \zeta_n^{-k}} \\
&= 2^{1-n} \prod_{1\leq k \leq n-1} \qty{1 - \zeta_n^{-k}} \\
&= 2^{1-n} \prod_{1\leq k \leq n-1} \qty{1 - \zeta_n^{k}} \\
&= 2^{1-n}  { \Phi_n(z) \over z-1}\evalfrom_{z=1} \\
&= 2^{1-n} \qty{ \sum_{0\leq k \leq n-1} z^k}\evalfrom_{z=1} \\
&= n2^{1-n}
.\]


:::

:::{.solution title="Older"}
\[
\prod_{1\leq j\leq n-1} 
\sin \left(\frac{j \pi}{n}\right)
&=\prod_{1\leq j\leq n-1} \frac{1}{2 i}
\qty{\zeta_n^{j\over 2} - \zeta_n^{- {j \over 2} }} \\
&=\left(\frac{1}{2 i}\right)^{n-1} \prod_{1\leq j\leq n-1} 
\zeta_n^{j\over 2} \prod_{1\leq j \leq n-1} \qty{1 - \zeta_n^{-j}} \\
&=\left(\frac{1}{2 i}\right)^{n-1} \prod_{1\leq j\leq n-1} 
\exp\qty{ij\pi \over n} \prod_{1\leq j \leq n-1} \qty{1 - \zeta_n^{-j}} \\
&=\left(\frac{1}{2 i}\right)^{n-1} \exp \left(\sum_{1\leq j\leq n-1} \frac{i j \pi}{n}\right) \Phi_{n}(1)\\
&=\left(\frac{1}{2 i}\right)^{n-1} \exp \left(\frac{(n-1) i \pi}{2}\right) \Phi_{n}(1)\\
&=\left(\frac{1}{2 i}\right)^{n-1}\left(e^{i \pi / 2}\right)^{n-1} \Phi_{n}(1)\\
&=\left(\frac{1}{2 i}\right)^{n-1} i^{n-1} \Phi_{n}(1)\\
&=\left(\frac{1}{2}\right)^{n-1} \Phi_{n}(1)\\
&=\frac{n}{2^{n-1}}
.\]

:::
