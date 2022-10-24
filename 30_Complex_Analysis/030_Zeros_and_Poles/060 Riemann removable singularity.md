# Removable Singularities 

:::{.theorem title="Riemann's removable singularity theorem"}
If $z_0$ is an isolated singularity of $f(z)$ and $\abs{f(z)}$ is bounded near $z_0$, then $z_0$ is removable.

More generally, TFAE:

- $f$ extends holomorphically over $z_0$, i.e. there is a function $F$ such that $\ro{F}{\Omega\sm\ts{z_0}} = f$
- $f$ extends continuously over $z_0$.
- There exists *some* neighborhood of $z_0$ on which $f$ is bounded.
- $\lim_{z\to z_0}(z-z_0)f(z) = 0$.

:::

:::{.remark}
Showing a singularity $z_0$ of $f$ is removable: it suffices to show 

- Expand $f(z) = \sum_{k\in \ZZ} c_k z^k$ and show $z_k=0$ for $k<0$.
- Show $\lim_{z\to z_0}f(z) \neq \infty$
:::

## Exercises

:::{.exercise title="?"}
Show that there is an entire function $h$ such that
\[
{\pi^2\over \sin^2(\pi z)} = \sum_{k\in \ZZ} {1\over (z-k)^2} + h(z)
.\]

#complex/exercise/completed

:::

:::{.concept}
\envlist

- The principal part of $f$ at $z=z_0$ is gotten by expanding $f(z) = \sum_{k\in \ZZ} c_k z^k$ and taking $\sum_{k\leq 1} c_k z^k$.
- Common trick: to control a singularity, subtract off a function with the same principal part at that point.
:::

:::{.solution}
Write 

- $f(z) = {\pi^2 \over \sin^2(\pi z)}$
- $g(z) = \sum_{k\in \ZZ} {1\over (z-k)^2}$

Write the above equation as $f(z) = g(z) - h(z)$ and consider $h(z) \da f(z) - g(z)$.
Then $h$ is meromorphic with singularities precisely on the set $\ZZ$, and are thus isolated.
By the classification of isolated singularities, these can be removable, poles, or essential.
If they are removable, then $h$ is entire.

Consider the singularity at $z_0 = 0$.
This is a pole of $f$, and a computation shows it is order 2:
\[
f(z) 
&= \qty{\pi \over \sin(\pi z)}^2 \\
&= \qty{\pi \over \pi z - {1\over 3!}(\pi z)^3 + \bigo(z^5) }^2 \\
&= \qty{\pi \over \pi z (1 - {1\over 3!}(\pi z)^2 + \bigo(z^4))}^2 \\
&= {1\over z^2} \qty{1 \over 1 - {1\over 3!}(\pi z)^2 + \bigo(z^4)}^2 \\
&= {1\over z^2}\qty{1 + \bigo(z^2)}^2 \\
&= {1\over z^2} + \bigo(z^2)
,\]
so $z=0$ is a zero of order 2 of $1/f$.
This expansion also shows that the principal part of $f$ at $z=0$ is ${1\over z^2}$, which is precisely that of $g$ at $z=0$, i.e. ${1\over (z-0)^2} = 1/z^2$, 
Since $f-g$ subtracts off this part, $z=0$ becomes a removable singularity for $h$ since $\lim_{z\to 0} \qty{ f(z) - {1\over z^2}} = 1<\infty$.

Now note that $f$ is periodic, and since the period is 1, a similar argument shows that the remaining singularities on $\ZZ\smz$ are all removable for $f-g$.
By Riemann's removable singularity theorem, $f-g$ extends over these singularities, yielding an entire function $h$ that restricts to $f-g$ on $\CC\sm\ZZ$.
:::

