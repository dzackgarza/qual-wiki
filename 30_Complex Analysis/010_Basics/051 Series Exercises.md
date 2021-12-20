---
order: 51
---

# Series Exercises

## Analytic Properties of Series

:::{.exercise title="Power series converge uniformly on their radius of convergence"}
Show that any power series converges uniformly within its radius of convergence.

#completed

:::

:::{.solution}
Write $S_N(z) \da \sum_{0\leq k\leq N} c_k (z-z_0)^k$ and $S \da \lim_{N\to\infty} S_N$.
Suppose $R\da \qty{\limsup_k \abs{c_k}^{1\over k} }\inv$ is the radius of convergence and let $r\leq R$, we'll show $S_N\to S$ uniformly on any disc $\abs{z-z_0}< r$.

Use the $M\dash$test: $\sum f_k$ converges if $\norm{f_k}_\infty\leq M_k$ where $\ts{M_k}\in \ell^1(\NN)$.
Define $f_k \da c_k (z-z_0)^k$, then 
\[
\norm{f_k}_\infty =\sup_{\abs{z-z_0}\leq r} \abs{c_k(z-z_0)^k} \leq \abs{c_k} r^k \da M_k
.\]
Then
\[
\sum_{k\geq 0} M_k = \sum_{k\geq 0} \abs{c_k} r^k
,\]
and the claim is that this converges.

Note that since $r\leq R$, we have convergence of 
\[
\sum_{k\geq 0} c_k r^k
.\]
Recall that root test:
\[
\sum_k a_k \text{ converges absolutely if } \limsup_k \abs{a_k}^{1\over k} < 1
.\]
Here we take $a_k \da c_k r^k$, then
\[
\limsup_k \abs{a_k}^{1\over k} 
&\da \limsup_k \abs{c_k r^k}^{1\over k} \\
&= \limsup_k \abs{c_k}^{1\over k} r \\
&< \limsup_k \abs{c_k}^{1\over k} R\\
&\da \limsup_k \abs{c_k}^{1\over k} \qty{\limsup_{k} \abs{c_k}^{1\over k} }\inv \\
&= 1
,\]
so $\sum_k \abs{c_k r^k} < \infty$.
Thus $\ts{M_k}\in \ell^1(\NN)$, and so $\sum_k f_k$ converges uniformly and absolutely on $\abs{z-z_0} = r < R$.
:::

:::{.exercise title="Power series are continuous"}
Show that any power series is continuous on its domain of convergence. 

#completed

:::

:::{.solution}
Let $f(z) = \lim_{N\to\infty} \sum_{k\leq N} c_k (z-z_0)^k$.
Use that power series converge uniformly and absolutely within their disc of convergence, each term is a continuous function, and finite sums of continuous functions are again continuous.
So the partial sums $S_N$ are continuous, and since $S_N\to f$ uniformly, $f$ is continuous by the uniform limit theorem.

:::


:::{.exercise title="Uniform limits of derivatives"}
Suppose $f_k: \Omega\to \CC$ is a sequence of differentiable functions converging locally uniformly to $f:\Omega\to \CC$.
Show that

- $f$ is continuous,
- $f$ is differentiable,
- $\ts{f_k'}\to f'$ locally uniformly.

#complete

:::


:::{.solution}
That $f$ is continuous is a local question: fixing a point $z_0$, take a closed disc $\DD+z_0$ about $z_0$.
By local uniform convergence $f_k\to f$ uniformly on $\DD+z_0$, and differentiable $\implies$ continuous.
So each $f_k$ is continuous, making $f$ continuous on $\DD+z_0$ by the uniform limit theorem.

That $f$ is differentiable is again a local question: fix $z$ and write $\gamma \da \bar{\DD + z}$ as the boundary of the disc about $z$.
Define $g_k(\xi) \da {f_k\over \xi-z}$, so $g_k \to {f \over \xi-a}$ locally uniformly.
Now apply Cauchy's integral formula at $z$:
\[
f(z) 
&= \lim_k f_k(z) \\
&= \lim_k {1\over 2\pi i}\int_\gamma {f_k(\xi) \over \xi - z}\dxi \\
&= \lim_k {1\over 2\pi i}\int_\gamma g_k(\xi)\dxi\\
&= {1\over 2\pi i}\int_\gamma \lim_k g_k(\xi)\dxi \\
&= {1\over 2\pi i}\int_\gamma g(\xi)\dxi\\
&= {1\over 2\pi i}\int_\gamma {f(\xi) \over \xi - z} \dxi\\
.\]
So $f$ has an integral representation, making it differentiable.

:::



## Radius of Convergence 

:::{.exercise title="Radius of convergence"}
Find the radius of convergence of 

- $\sum a^k z^k$ for $a$ a constant.
- $\sum a^{k^2}z^k$

#completed

:::

:::{.solution}
\envlist

- $R = 1/\limsup \abs{a^k}^{1\over k} = 1\over \abs{a}$
- $R = 1/\limsup \abs{a^{k^2}}^{1\over k} = 1/\limsup \abs{a}^k$, so $R=\infty$ if $\abs{a}< 1$, $R=0$ if $\abs{a}<1$, and $R=1$ if $\abs{a} = 1$.
:::

:::{.exercise title="Radius of convergence"}
Find the radius of convergences for the power series expansion of $\sqrt{z}$ about $z_0 = 4 +3i$.
Repeat with $z_1=-4+3i$.

#completed

:::

:::{.solution}
Choose the principal branch of $\log$, so take a branch cut at $\RR_{\leq 0}$, to define $z^{1\over 2} = e^{{1\over 2}\log(z)}$.
The radius of convergence is the distance to the nearest singularity or branch cut, so note that $f(z) = z^{1\over 2}$ is singular at $z=0$, so we compute $\abs{z_0 - 0} = \abs{4+3i} = 5$.
The distance to the branch is also 5, so $R=5$.

For $z_1$, the distance to zero is $\abs{4+3i - 0} = 5$ but the distance to the branch is 4, so $R=4$.

> Note the subtle distinction: the series converges to $f$ in a disc $\abs{z-z_0}<1$, but the series itself converges in larger discs.

:::

## Finding Laurent Expansions

:::{.exercise title="Expanding Laurent series in different regions"}
Expand $f(z) = {1\over z(z-1)}$ in both

- $\abs{z} < 1$
- $\abs{z} > 1$

#completed

:::

:::{.solution}
\[
{1\over z(z-1)} = -{1\over z}{1 \over 1-z} = -{1\over z}\sum z^k
.\]
and
\[
{1\over z(z-1)} = {1\over z^2(1 - {1\over z})} = {1\over z^2} \sum \qty{1\over z}^k
.\]
:::

:::{.exercise title="Laurent expansions about different points"}
Find the Laurent expansion about $z=0$ and $z=1$ respectively of the following function:
\[
f(z) \da {z+1 \over z(z-1)}
.\]

#completed
:::

:::{.solution}
Note: once you see that everything is in terms of powers of $(z-z_0)$, you're essentially done.
For $z=0$:
\[
{z+1 \over z(z-1)}
&= {1\over z} {z+1 \over z-1} \\
&= -{z+1\over z} {1\over 1-z} \\
&= -\qty{1 + {1\over z}}\sum_{k\geq 0} z^k
.\]

For $z=1$:
\[
{z+1 \over z(z-1)}
&= {1\over z-1}\qty{1 + {1\over z} } \\
&= {1\over z-1}\qty{1 + {1\over 1 - (1-z)} } \\
&= {1\over z-1} \qty{1 + \sum_{k\geq 0} (1-z)^k } \\
&= {1\over z-1} \qty{1 + \sum_{k\geq 0} (-1)^k (z-1)^k }
.\]

:::

## New Things in $\CC$

:::{.exercise title="Cauchy integral formula for coefficients"}
Show that if $f(z) \sum_{k\in \ZZ} c_k (z-z_0)^k$, then 
\[
c_k = {1\over 2\pi i}\int_\gamma {f(z) \over (z-z_0)^{n+1}}\dz
,\]
and that this converges in an annulus $D_R(z_0)\sm \bar{D_r(z_0)}$ where
\[
r=\limsup _{n \rightarrow \infty} \sqrt[n]{\left|a_{-n}\right|} \text { and } R=\frac{1}{\limsup _{n \rightarrow \infty} \sqrt[n]{\left|a_{n}\right|}} \text {. }
.\]


Hint: start with
\[
f(z)=\frac{1}{2 \pi i} \oint_{\left|w-z_{0}\right|=s_{2}} \frac{f(w)}{w-z} d w-\frac{1}{2 \pi i} \oint_{\left|w-z_{0}\right|=s_{1}} \frac{f(w)}{w-z} d w
,\]
and try to obtain a geometric series to obtain
\[
f(z)=\sum_{j=-\infty}^{\infty}\left(\frac{1}{2 \pi i} \oint_{\left|w-z_{0}\right|=r} \frac{f(w)}{\left(w-z_{0}\right)^{j+1}} d w\right)\left(z-z_{0}\right)^{j}
.\]

#work

:::

