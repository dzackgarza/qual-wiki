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


:::{.exercise title="?"}
Show that there is an entire function $h$ such that
\[
{\pi^2\over \sin^2(\pi z)} = \sum_{k\in \ZZ} {1\over (z-k)^2} + h(z)
.\]

#completed 

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
&= \qty{\pi \over \pi z + {1\over 3!}(\pi z)^3 + \bigo(z^5) }^2 \\
&= \qty{\pi \over \pi z (1 + {1\over 3!}(\pi z)^2 + \bigo(z^4))}^2 \\
&= {1\over z^2} \qty{1 \over 1 + {1\over 3!}(\pi z)^2 + \bigo(z^4)}^2
,\]
so $z=0$ is a zero of order 2 of $1/f$.
Note that $\lim_{z\to 0} z^2f(z) = 1$.


:::



