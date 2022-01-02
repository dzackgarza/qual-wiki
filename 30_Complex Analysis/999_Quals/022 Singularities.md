---
order: 22
---

# Singularities

## Spring 2020.4 #complex/qual/completed

^4bd9ee


:::{.problem title="?"}
Suppose that $f$ is holomorphic in an open set containing the closed unit disc, except for a simple pole at $z=1$. Let $f(z)=\sum_{n=1}^{\infty} c_{n} z^{n}$ denote the power series in the open unit disc. Show that 
\[
\lim _{n \rightarrow \infty} c_{n}=-\lim _{z \rightarrow 1}(z-1) f(z)
.\]
:::

:::{.solution}
Compute the series expansion of the RHS:
\[
(z-1) f(z) 
&= (z-1) \sum_{n\geq 1} c_n z^k \\
&= -c_1z + \sum_{n\geq 2} (c_{n-1} - c_n) z^n \\
&\convergesto{z\to 1} -c_1 + \sum_{n\geq 2} c_{n-1} - c_n \\
&\da \lim_{N\to\infty} -c_1 z + \sum_{n=2}^N c_{n-1} - c_n \\
&= \lim_{N\to\infty} -c_N
,\]
where we've used that the sum is telescoping.
:::

## 5 #complex/qual/work

Find all entire functions with have poles at $\infty$.

## 6 #complex/qual/work

Find all functions on the Riemann sphere that have a simple pole at $z=2$ and a double pole at $z=\infty$, but are analytic elsewhere.


## Entire functions with singularities at $\infty$ #complex/qual/work

:::{.problem title="?"}
Let $f$ be entire, and discuss (with proofs and examples) the types of singularities $f$ might have (removable, pole, or essential) at $z=\infty$ in the following cases:

1. $f$ has at most finitely many zeros in $\CC$.
2. $f$ has infinitely many zeros in $\CC$.

:::


:::{.solution}

**Part 2**:
Write $f(z) = \sum_{k\geq 0} c_k z^k$ since it is entire.

- If $f$ has finitely many zeros, $f$ is nonconstant and entire, and thus unbounded by Liouville.
  If $f$ is nonconstant, $z=\infty$ can not be removable, since this would force $f$ to be constant.
  So $z=\infty$ can be a pole or an essential singularity.
  Both possibilities can occur: if $f$ is a polynomial, it is entire with finitely many zeros and a pole at $z=\infty$.

- If $f$ has infinitely many zeros, if $f$ is nonconstant then infinitely many $c_k$ are nonzero -- otherwise $f$ is a polynomial and can only have finitely many zeros.
  Then $g(z) \da f(1/z) = \sum_{k\geq 0}{c_k\over z^k}$ has infinitely many nonzero terms, making $z=0$ an essential singularity for $g$ and $z=\infty$ essential for $f$.
:::



## Sum formula for $\sin^2$ #complex/qual/work

:::{.problem title="?"}
Define
\[
f(z) &= {\pi^2 \over \sin^2 \qty{\pi z} } \\
g(z) &= \sum_{n\in \ZZ} {1\over (z-n)^2}
.\]

a. Show that $f$ and $g$ have the same singularities in $\CC$.
b. Show that $f$ and $g$ have the same singular parts at each of their singularities.
c. Show that $f, g$ each have period one and approach zero uniformly on $0\leq x \leq 1$ as $\abs{y}\to \infty$.
d. Conclude that $f = g$.


:::

## Tie's Extra Questions: Fall 2015 #complex/qual/completed

:::{.problem title="?"}
Let $f(z)$ be a non-constant analytic function in $|z|>0$ such that $f(z_n) = 0$ for infinite many points $z_n$ with $\lim_{n \rightarrow \infty} z_n =0$. 

Show that $z=0$ is an essential singularity for $f(z)$.

> Hint: an example of such a function is $f(z) = \sin (1/z)$.

:::

:::{.solution}
Note that $z=0$ can not be a removable singularity, since then $f$ would extend to a holomorphic function over $z=0$, and by continuity $0 = \lim f(z_n) = f(\lim z_n) = f(0)$.
By the identity principle, this would force $f\equiv 0$, contradicting that $f$ is nonconstant.

It can not be a pole, because then $f(z_n)\to \infty$, but $\abs{f(z_n)} = 0 < \eps$ for any $\eps$ infinitely many times.
:::


