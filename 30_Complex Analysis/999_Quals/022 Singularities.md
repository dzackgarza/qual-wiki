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

## Entire functions with poles at $\infty$ #complex/exercise/completed

:::{.problem title="?"}
Find all entire functions with have poles at $\infty$.
:::

:::{.solution}
If $f$ is entire, write $f(z) = \sum_{k\geq 0}c_k z^k$ and $g(z) \da f(1/z) = \sum_{k\geq 0}c_k z^{-k}$.
If $z=\infty$ is a pole of order $m$ of $f$, $z=0$ is a pole of order $m$ of $g$, so 
\[
g(z) = \sum_{0\leq k \leq m}c_k z^{-k} \implies f(z) = \sum_{0\leq k \leq m}c_k z^k
,\]
making $f$ a polynomial of degree at most $m$.
:::

## 6 #complex/exercise/completed

:::{.problem title="?"}
Find all functions on the Riemann sphere that have a simple pole at $z=2$ and a double pole at $z=\infty$, but are analytic elsewhere.
:::

:::{.solution}
Write $f(z) = P_2(z) + g(z)$ where $P_2$ is the principal part of $f$ at $z=2$ and $g$ is holomorphic at $z=2$.
Then $g$ is an entire function with a double pole at $\infty$, and is thus a polynomial of degree at most $2$, so $g(z) = c_2z^2 + c_1 z + c_0$.
Since the pole of $f$ at $z=2$ is simple, $P_2(z) = \sum_{k\geq -1} d_k (z-2)^k$.
Combining these, we can write
\[
f(z) = d_{-1}(z-2)\inv + \sum_{0\leq k\leq 3} (d_k + c_k)(z-2)^k + \sum_{k\geq 3}d_k (z-2)^k 
.\]
However, if $d_k\neq 0$ for any $k\geq 3$, this results in a higher order pole at $\infty$, so $f$ must be of the form
\[
f(z) = d_{-1}(z-2)\inv + \sum_{0\leq k\leq 3} (d_k + c_k)(z-2)^k 
.\]
:::



## Entire functions with singularities at $\infty$ #complex/exercise/completed

:::{.problem title="?"}
Let $f$ be entire, and discuss (with proofs and examples) the types of singularities $f$ might have (removable, pole, or essential) at $z=\infty$ in the following cases:

1. $f$ has at most finitely many zeros in $\CC$.
2. $f$ has infinitely many zeros in $\CC$.

:::

:::{.solution}
Write $f(z) = \sum_{k\geq 0} c_k z^k$ since it is entire.

- If $f$ has finitely many zeros, $f$ is nonconstant and entire, and thus unbounded by Liouville.
  If $f$ is nonconstant, $z=\infty$ can not be removable, since this would force $f$ to be constant.
  So $z=\infty$ can be a pole or an essential singularity.
  Both possibilities can occur: if $f$ is a polynomial, it is entire with finitely many zeros and a pole at $z=\infty$.
  Taking $f(z)= e^z$ has no zeros and an essential singularity at $z=\infty$.

- If $f$ has infinitely many zeros, if $f$ is nonconstant then infinitely many $c_k$ are nonzero -- otherwise $f$ is a polynomial and can only have finitely many zeros.
  Then $g(z) \da f(1/z) = \sum_{k\geq 0}{c_k\over z^k}$ has infinitely many nonzero terms, making $z=0$ an essential singularity for $g$ and $z=\infty$ essential for $f$.
:::


## Sum formula for $\sin^2$ #complex/exercise/work

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


