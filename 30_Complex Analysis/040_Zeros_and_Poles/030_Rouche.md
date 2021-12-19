# Rouché 


:::{.theorem title="Rouché's Theorem" ref="Rouche"}
Let $f, g$ be meromorphic on $\Omega$ and write $Z_f, Z_g, P_f, P_g$ for the numbers of zeros and poles of $f$ and $g$ respectively.
Suppose $\gamma \subseteq \Omega$ is a toy contour winding about each zero and pole of $f$ and $g$ precisely once.
Then
\[
\abs{g} \leq \abs{f} \text{ on } \gamma \implies \Index_{z=0}(f\circ \gamma)(z) 
&= \Index_{z=0}((f+g)\circ \gamma)(z) \\
\implies Z_f - P_f 
&= Z_{f+g} - P_{f+g}
.\]
In particular, if $f, g$ are *holomorphic* on $\Omega$, then $f$ and $f+g$ have the same number of zeros in $\Omega$, i.e. $Z_f = Z_{f+g}$.

Some alternative formulations:

- Bounding a difference: given $f$, find a big part $F$ and call the small part $g\da f-F$. 
Then
\[
\abs{g} \da \abs{f-F} \leq \abs{F}
\text{ on }\bd\Omega \implies Z_f = Z_F
.\]


:::

:::{.slogan}
You can add a small perturbation $g$ to $f$ and preserve the number of zeros, where "small" means $\abs{g} < \abs{f}$ on the boundary.
:::

:::{.slogan}
The number of zeros/poles are determined by a dominating function on the boundary.
:::

:::{.remark}
On strategy: write your function as big + small, where big $>$ small on the boundary and it's clear how many zeros big has inside. 
:::

:::{.proof title="of Rouché"}
Idea: use argument principle on $(f+g)/f$.
Alternatively, use that $N(f+tg, \Omega)$ is a continuous $\ZZ\dash$valued function for all $t\in [0, 1]$.

![](figures/2021-12-10_22-23-58.png)

:::

:::{.proof title="of Rouché, alternative"}

![](figures/2021-12-14_16-25-41.png)

![](figures/2021-12-15_02-24-10.png)

:::

# Exercises

:::{.exercise title="Explicit Rouché, $\mathbb{D}$"}
Find the number of zeros in $\abs{z} < 1$ of
\[
p(z) \da z^6 + 9z^4 + z^3 + 2z + 4
.\]

#completed

:::

:::{.solution}
Strategy: bound the difference.
Find the big and small term:

- Big: $F(z) = 9z^4$, so $\abs{F(z)} = 9$ on the boundary
- Small: $g(z) = p(z) - F(z) = z^6 + z^3 + 2z + 4$, so $\abs{g(z)}\leq 1+1+2+4=8$ on the boundary.


So $\abs{p-F} \leq \abs{F}$ on $\abs{z} = 2$, meaning $Z_{p} = Z_F = 4$.


:::

:::{.exercise title="Explicit Rouche, $2\mathbb{D}$"}
Find the number of zeros in $\abs{z} < 2$ of
\[
h(z) \da z^5 + 3z + 1
.\]


#completed
:::

:::{.solution}
Strategy: bound the difference.

- Big: $F(z) \da z^5$ so $\abs{F(z)} = 2^5 = 32$ on $\abs{z} = 2$
- Small: $g(z) \da p(z) - F(z) = 3z+1$, so $\abs{g(z)} \leq 3\abs{z}+ 1 = 7$ on $\abs{z} = 2$.

Then $\abs{g}\leq \abs{F}$ on $\abs{z} = 2$, $Z_{p} = Z_F = 5$.
:::

:::{.exercise title="Arbitrary Rouché, $R\mathbb{D}$"}
Show that if $p(z) \da z^d + a_1z^{d-1} + \cdots + a_d$ and $\abs{a_k}< {R^k \over d}$ for every $k$ (noting the strict inequality), then $p$ has $d$ zeros in $\abs{z} < R$.

#completed

:::

:::{.solution}
Strategy: bound the difference.
Find the big and small term:

- Big: $F(z) = z^d$, so $\abs{F(z)} = R^d$ on $\abs{z} = R$.
- Small: $g(z) = p(z) - F(z) = a_1 z^{d-1} + \cdots + a_d$, so
\[
\abs{g(z)} 
&\leq \abs{a_1} R^{d-1} + \abs{a_2} R^{d-2} + \cdots + \abs{a_d} \\
&< {R\over d} \cdot R^{d-1} + {R^2 \over d} \cdot R^{d-2} + \cdots + {R^{d-1} \over d} \cdot R + {R^{d} \over d} \\
&= d {R^d\over d} = R^d
,\]
so $\abs{g} < R^d = \abs{F}$, meaning $Z_{p-F} = Z_F = d$ in $R\DD$.

:::

:::{.exercise title="?"}
Show that $h(z) = z + 3 + 2e^z$ has one root in $\ts{ \Re(z) \leq 0}$.
:::

:::{.solution}
Use the following contour:


![figures/2021-07-29_20-39-31.png](figures/2021-07-29_20-39-31.png)

Take $g(z) \da 2e^z < f(z) \da f(z) \da z+3$.
:::

:::{.exercise title="?"}
Show that $P(z) \da z^4 + 6z + 3$ has 3 zeros in $\ts{1\leq \abs{z} \leq 2}$.

#completed
:::

:::{.solution}
\envlist

- Take $P(z) = z^4 + 6z + 3$.
- On $\abs{z} < 2$:
  - Set $f(z) = z^4$ and $g(z) = 6z + 3$, then $\abs{g(z)} \leq 6\abs{z} + 3 = 15 < 16= \abs{f(z)}$.
  - So $P$ has 4 zeros here.
- On $\abs{z} < 1$:
  - Set $f(z) = 6z$ and $g(z) = z^4 + 3$.
  - Check $\abs{g(z)} \leq \abs{z}^4 + 3 = 4 < 6 = \abs{f(z)}$.
  - So $P$ has 1 zero here.
:::

:::{.exercise title="?"}
Show that $\alpha z e^z = 1$ where $\abs{\alpha} > e$ has exactly one solution in $\DD$.

#completed

:::

:::{.solution}
\envlist 

- Set $f(z) = \alpha z$ and $g(z) = e^{-z}$.
- Estimate at $\abs{z} =1$ we have $\abs{g} =\abs{e^{-z}} = e^{-\Re(z)} \leq e^1 < \abs{\alpha} = \abs{f(z)}$
- $f$ has one zero at $z_0 = 0$, thus so does $f+g$.
:::
