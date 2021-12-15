---
order: 22
---

# Singularities

## Spring 2020.4 #work

^4bd9ee

Suppose that $f$ is holomorphic in an open set containing the closed unit disc, except for a simple pole at $z=1$. Let $f(z)=\sum_{n=1}^{\infty} c_{n} z^{n}$ denote the power series in the open unit disc. Show that 
\[
\lim _{n \rightarrow \infty} c_{n}=-\lim _{z \rightarrow 1}(z-1) f(z)
.\]

## 5 #work

Find all entire functions with have poles at $\infty$.

## 6 #work

Find all functions on the Riemann sphere that have a simple pole at $z=2$ and a double pole at $z=\infty$, but are analytic elsewhere.


## 7 #work
Let $f$ be entire, and discuss (with proofs and examples) the types of singularities $f$ might have (removable, pole, or essential) at $z=\infty$ in the following cases:

1. $f$ has at most finitely many zeros in $\CC$.
2. $f$ has infinitely many zeros in $\CC$.

## 8 #work
Define
\[
f(z) &= {\pi^2 \over \sin^2 \qty{\pi z} } \\
g(z) &= \sum_{n\in \ZZ} {1\over (z-n)^2}
.\]

a. Show that $f$ and $g$ have the same singularities in $\CC$.
b. Show that $f$ and $g$ have the same singular parts at each of their singularities.
c. Show that $f, g$ each have period one and approach zero uniformly on $0\leq x \leq 1$ as $\abs{y}\to \infty$.
d. Conclude that $f = g$.

\todo[inline]{Not finished.}

:::{.solution}
\hfill
:::{.concept}
\hfill
Idea: show their $f-g$ is analytic by taking away all of the negative powers, and bounded by (c).
:::

:::

## Tie's Extra Questions: Fall 2015

Let $f(z)$ be a non-constant analytic function in $|z|>0$ such that $f(z_n) = 0$ for infinite many points $z_n$ with $\lim_{n \rightarrow \infty} z_n =0$. 

Show that $z=0$ is an essential singularity for $f(z)$.

> Hint: an example of such a function is $f(z) = \sin (1/z)$.
