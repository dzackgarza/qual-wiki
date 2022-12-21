---
order: 6
---

# Series Convergence 

## Fall 2020.2 #complex/qual/completed

^c47851

:::{.problem title="?"}
Expand $\frac{1}{1-z^{2}}+\frac{1}{z-3}$ in a series of the form $\sum_{-\infty}^{\infty} a_{n} z^{n}$ so it converges for

- $|z|<1$,

- $1<|z|<3$,

- $|z|>3$.

:::

:::{.solution}
General strategy: each has two expansions, so just compute them all and pick appropriate ones for regions afterwards.

For $1\over z-3$:
\[
{1\over z-3} &= -{1\over 3}{1\over 1- {z\over 3}} = -{1\over 3}\sum_{k\geq 0}3^{-k}z^k 
&& \abs{z} < 3 \\
&= {1\over z} {1\over 1 - {3\over z}} = z\inv \sum_{k\geq 0} 3^k z^{-k}
&& \abs{z} > 3
.\]

For $1\over 1-z^2$:
\[
{1\over 1-z^2}
&= \sum_{k\geq 0} z^{2k} && \abs{z} < 1 \\
&= {1\over z^2} {-1\over 1- z^{-2}} = -z^{-2}\sum_{k\geq 0}z^{-2k} && \abs{z} > 1
.\]

So take
\[
0 < \abs{z} < 1 
&& f(z) &= \sum_{k\geq 0}z^{2k} - {1\over 3}\sum_{k\geq 0} 3^{-k}z^k \\
1 < \abs{z} < 3 
&& f(z) &= -z^{-2} \sum_{k\geq 0}z^{-2k} - {1\over 3}\sum_{k\geq 0} 3^{-k}z^k \\
3 < \abs{z} < \infty 
&& f(z) &= -z^{-2} \sum_{k\geq 0}z^{-2k} + z\inv \sum_{k\geq 0}3^k z^{-k} 
.\]

:::


## Spring 2020 HW 2.2 #complex/qual/completed

:::{.problem title="?"}
Let $f$ be a power series centered at the origin.
Prove that $f$ has a power series expansion about any point in its disc of convergence.
:::

:::{.concept}
\envlist

- Cauchy's integral formula:
\[
f(z) = \int {f(\xi) \over \xi - z}\dxi
.\]

:::

:::{.solution}
Idea: use Cauchy's integral formula to get a series in $(z-z_0)$.
\[
f(z) 
&= \int {f(\xi) \over \xi -z} \dxi\\
&= \int f(\xi) \qty{ 1\over \xi - (z - z_0) - z_0 } \dxi\\
&= \int { f(\xi) \over\xi - z_0}  \qty{ 1\over 1-w  } \dxi && w\da {z-z_0 \over \xi - z_0} \\
&= \int { f(\xi) \over\xi - z_0}  \sum_{k\geq 0} w^k \dxi \\
&= \sum_{k\geq 0} \qty{\int {f(\xi) \over \xi - z_0} \dxi } w^k\\
&= \sum_{k\geq 0} \qty{\int {f(\xi) \over \xi - z_0} \dxi } w^k\\
&= \sum_{k\geq 0} \qty{\int {f(\xi) \over (\xi - z_0)^{k+1} } \dxi } (z-z_0)^k
,\]
where we've integrated over a curve contained in $D$ the disc of convergence, and that the power series for $f$ converges uniformly on $D$ to commute the sum and integral.

:::

## Fall 2015, Spring 2020 HW 2, Ratio Test #complex/qual/work 

:::{.problem title="?"}
Let $a_n\neq 0$ and show that
\[
\lim_{n\to \infty} {\abs{a_{n+1}} \over \abs{a_n}} = L \implies \lim_{n\to\infty} \abs{a_n}^{1\over n} = L
.\]

In particular, this shows that when applicable, the ratio test can be used to calculate the radius of convergence of a power series.
:::

## Analytic on circles #complex/qual/completed

:::{.problem title="?"}
Suppose $f$ is analytic on a region $\Omega$ such that $\DD \subseteq \Omega \subseteq \CC$ and $f(z) = \sum_{n=0}^\infty a_n z^n$ is a power series with radius of convergence exactly 1.

a. 
Give an example of such an $f$ that converges at every point of $S^1$.

b.  
Give an example of such an $f$ which is analytic at $1$ but $\sum_{n=0}^\infty a_n$ diverges.

c.  
Prove that $f$ can not be analytic at *every* point of $S^1$.

:::

:::{.solution}
\envlist

**Part a**:
Take $f(z) \da \displaystyle\sum n^{-2}z^n$, which converges absolutely for $\abs{z}=1$ by the comparison test.

**Part b**:
Take $f(z) \da {1\over 1+z} = \sum_{k\geq 0} (-1)^k z^k$, then $f(1) = 2$ by analytic continuation of the series at $z=1$.
Then $a_k = (-1)^k$,

**Part c**:
??? Not clear if this is true, take $f(z) = \sum z^n/n^2$.

:::

## Spring 2020 HW 2.3: series on the circle #complex/qual/completed

:::{.problem title="?"}
Prove the following:

a. $\sum_{n} nz^n$ does not converge at any point of $S^1$

b. $\sum_n {z^n \over n^2}$ converges at every point of $S^1$.

c. $\sum_n {z^n \over n}$ converges at every point of $S^1$ except $z=1$.

:::

:::{.concept}
\envlist

- Summation by parts:
  Set $B_0 \da 0, B_n \da \sum_{k\leq n} b_k$, then
\[
\sum_{n=M}^{N} a_{n} b_{n}=a_{N} B_{N}-a_{M} B_{M-1}-\sum_{n=M}^{N-1}\left(a_{n+1}-a_{n}\right) B_{n}
.\]

- Summing a geometric series:
\[
\sum_{1\leq k \leq N} z^k = {1 - z^{N+1}\over 1-z}
.\]

:::

:::{.solution}
**Part 1**:
This series does not have small tails: writing $c_n \da n z^n$ we have $\abs{c_n} = \abs{nz^n} = \abs{n}\to \infty$ when $\abs{z} = 1$.

**Part 2**:
This converges absolutely and absolute convergence implies convergence:
\[
\abs{\sum n^{-2} z^n} \leq \sum \abs{n^{-2}z^n} = \sum n^{-2} < \infty
.\]


**Part 3**:
Write $f(z) = \sum_{k\geq 1} k\inv z^k$.
The value $f(1)$ is the harmonic series, which we know diverges from undergraduate Calculus.
For $z\neq 1$, apply summation by parts with $a_k \da k\inv$ and $b_k \da z^k$, so 

- $a_N = N\inv$
- $a_M = M\inv$
- $B_N = \sum_{k\leq N} z^k = {1-z^{N+1} \over 1-z}$
- $B_M = \sum_{k\leq M} z^k$
- $a_{n+1} - a_n = (n+1)\inv + n\inv = - (n(n+1))\inv$

Note that $\abs{B_N} \leq C_z \da {2\over \abs{1-z} }$ for any $N$, since $\abs{z} = 1$ is on $S^1$ and the maximum distance between two points on $S^1$ is 2.
Moreover $C_z < \infty$ when $z\neq 1$.

Applying the formula:

\[
\abs{\sum_{n=M}^N n\inv z^n }
&\leq
\abs{
N\inv B_N 
- M\inv B_{M-1} 
- \sum_{n=M}^{N-1} \left[
-(n(n+1))\inv B_n 
\right]
}\\
&\leq N\inv C_z + M\inv C_z + \sum_{M\leq n \leq N-1} C_z \qty{1\over n^2 + n}\\
&\leq C_z\qty{N\inv + M\inv + \sum_{M\leq n \leq N-1} n^{-2}} \\
&\convergesto{M, N\to\infty} 0
\]

where we've used the triangle inequality and convergence of $\sum n^{-2}$.
By the Cauchy criterion for sums, $f(z)$ converges pointwise for $z\neq 1$.

:::

## Uniform convergence of series #complex/qual/work

:::{.problem title="?"}
Suppose $\sum_{n=0}^\infty a_n z^n$ converges for some $z_0 \neq 0$.

a.  
Prove that the series converges absolutely for each $z$ with $\abs z < \abs z_0$.

b.  
Suppose $0 < r < \abs{z_0}$ and show that the series converges uniformly on $\abs{z} \leq r$.

:::


## Sine series? #complex/qual/work

:::{.problem title="?"}
Prove that the following series converges uniformly on the set $\theset{z \suchthat \Im(z) < \ln 2}$:
\[
\sum_{n=1}^\infty {\sin(nz) \over 2^n}
.\]
Suppose $0 < r < \abs{z_0}$ and show that the series converges uniformly on $\abs{z} \leq r$.


:::

## Fall 2015 Extras #complex/qual/work

Assume $f(z)$ is analytic in ${\mathbb D}$ and $f(0)=0$ and is not a rotation (i.e. $f(z) \neq e^{i \theta} z$). 
Show that $\displaystyle \sum_{n=1}^\infty f^{n}(z)$ converges uniformly to an analytic function on compact subsets of ${\mathbb D}$, where $f^{n+1}(z) = f(f^{n}(z))$.


