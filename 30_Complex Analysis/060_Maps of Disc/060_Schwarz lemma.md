# Schwarz

## Hyperbolic Translations

:::{.proposition title="Properties of hyperbolic translations"}
The maps 
\[
\psi_a \da {a-z\over 1-\bar{a}z}
\]
are sometimes called *hyperbolic translations* because they preserve the hyperbolic metric on the Poincaré disc.
Some useful properties:

- $\psi_a(0) = a$ and $\psi(a) = 0$
- $\psi_{a} \inv = \psi_{a}$, so $\psi_a^2 = \id$.
- $\psi_a'(z) = {\abs{a}^2 - 1 \over \qty{1-\bar{a} z}^2 }$
- $\psi_a(\lambda z) = \lambda\psi_{\bar\lambda a}(z)$


:::

:::{.proof title="of proposition"}
Inverting: set $f(z) = w$ and solve for $z$:
\[
{a-z \over 1 - \bar{a}z} &= w \\
\implies a-z - w(1-\bar{a} z) &= 0 \\
\implies z&= {w-a \over \bar a w - 1} = {a-w\over 1-\bar a w}
.\]

Differentiating: the quotient rule
\[
\psi'_a(z) 
= {-(1-\bar a z) + \bar a(a-z) \over \qty{1-\bar a z}^2}
= {-1 + \abs{a}^2 \over \qty{1-\bar a z}^2}
.\]

Scaling: use a fun trick, insert $1=\bar\lambda \lambda$ like so
\[
\psi_a(\lambda z)
&=
{a - \lambda z \over 1 - \bar a \lambda z}\\
&=
{\lambda\bar\lambda a - \lambda z \over 1 - \bar a \lambda z} \\
&= \lambda {\bar\lambda a - z \over 1 - \bar{\bar\lambda a} z} \\
&= \lambda \psi_{\bar \lambda a}(z)
.\]




:::

:::{.remark}
There are such maps that are *not* rotations, e.g. the Blaschke factors:

![figures/2021-10-29_02-33-08.png](figures/2021-10-29_02-33-08.png)

Setting $B_w(z) \da {z-w\over 1-\bar{w} z}$, this is not a rotation when $w\neq 0$ and is an involution.
:::

:::{.theorem title="Characterization of conformal maps"}
Every map $g\in \BiHol(\DD)$ is of the form 
\[
g(z) = \lambda {a-z \over 1 - \bar a z}, \quad a\in \Delta, \lambda \in S^1
,\]
i.e a Blaschke product.
:::

:::{.proof title="of theorem, sketch"}

- That these maps are biholomorphisms: they're compositions of $z\mapsto \lambda z$ and $z\mapsto {z-a\over 1-\bar a z}$, which are biholomorphisms.
- Let $f \in \BiHol(\Delta)$ be arbitrary, fix $a\in \Delta$ with $f(a) = 0$
- Write $M(z) = {z-a\over 1-\bar a z}$, then note that $M(a) = 0$ and this is a biholomorphism.
- $g\da f\circ M\inv \in \BiHol(\Delta)$ sends $0\to0$ and is thus a rotation, so $g(z) = \lambda z$.
- Write $g\circ M = f \circ M \circ M\inv = f$, which exhibits $f$ in the desired form.

- Claim: this representation is unique.
  Consider $f'(z)$, this determines $\Arg(\lambda)$.
:::


## The Schwarz Lemma

:::{.theorem title="Schwarz Lemma" ref="SchwarzzLemma"}
If $f: \DD \to \DD$ is holomorphic with $f(0) = 0$, then

1. $\abs{f(z)} \leq \abs z$ for all $z\in \DD$
2. $\abs{f'(0)} \leq 1$.

Moreover, if 

- $\abs{f(z_0)} = \abs{z_0}$ for any $z_0\in \DD\smz$, or 
- $\abs{f'(0)} = 1$, 

then $f$ is a rotation, i.e. $f(z) = \lambda z$ for some $\abs{\lambda} = 1$.
:::

:::{.theorem title="Schwarz lemma, a useful alternative statement"}
Let $f:\DD\to \DD$ be holomorphic with $f(0) = 0$. 
Then either

- $f(z) = e^{i\theta}z$ is a rotation, or
- $\abs{f'(0)} < 1$ and $\abs{f(z)} < \abs{z}$ for all $z\in \DD$, noting the strict inequalities.

:::

:::{.proof title="of Schwarz lemma"}
\envlist

- Idea: apply the maximum modulus principle to $g(z) \da f(z)/z$.
- $\abs{g(z)} \leq 1$:
  - Expand $f$ at $z=0$ as $\sum_{k\geq 0} c_k z^k$.
    Since $f(0) = c_0$, we have $c_0 = 0$.
  - So $g(z) \da f(z)/z$ is holomorphic on $\DD$, since the singularity at $z=0$ is removable.
  - Set $\abs{z} = r < 1$, then $\abs{g(z)} = \abs{f(z)}/r \leq 1/r$ since $\abs{f(z)} \leq 1$.
  - By MMP, $\abs{g(z)} \leq 1/r$ holds in the entire disc $\abs{z} \leq r$, so take $r\to 1$ to get $\abs{g(z)} \leq 1$
- $\abs{f'(0)} \leq 1$ with equality iff $f$ is a rotation:
  - Note that $f(0) = 0$, so we can write $g(0) = \lim_{z\to 0} {f(z) - f(0) \over z-0} \da f'(0)$.
  - So $1 = \abs{f'(0)} = \abs{g(0)}$.
  - But $\abs{g(z)} \leq 1$ on $\DD$ and $g(z) = 1$ in the interior, so by MMP this makes $g$ constant.
  - So again $f(z) = cz$ with $\abs{c} = 1$.
- $\abs{f(z_0)} = \abs{z_0}\implies f$ is a rotation:
  - Again $\abs{g(z)} \leq 1$, but $\abs{f(z_0)} = \abs{z_0} \implies \abs{g(z_0)} = 1$, so $g$ attains a maximum on $\abs{z}\leq 1$, making it constant, so $f(z) = cz$.
  - Then $\abs{z_0} = \abs{f(z_0)} = \abs{cz_0}$ since $f(z_0) = z_0$, so $\abs{c} = 1$ and $c = e^{i\theta}$ for some $\theta$.
:::

:::{.proof title="of Schwarz, alternative"}


![](figures/2021-12-14_16-30-35.png)

![](figures/2021-12-14_16-30-46.png)

:::

# Exercises

:::{.exercise title="Schwarz-Pick Lemma"}
Prove the following:
suppose $\abs{f(z)}\leq 1$, then for all $z, w\in \DD$,
\[
\left|\frac{f(z)-f(w)}{1-\overline{f(w)} f(z)}\right| \leq\left|\frac{z-w}{1-\bar{w} z}\right|
\quad\text{ and }
\left|f^{\prime}(z)\right| \leq \frac{1-|f(z)|^{2}}{1-|z|^{2}}
.\]
If equality holds for some $z\neq w$ in either expression, then $f= \lambda F$ where $F$ is a linear fractional transformation and $\abs{\lambda} = 1$, so $f\in \Aut(\DD)$.

#complex/exercise/work

:::

:::{.proof title="of Schwarz-Pick"}

![](figures/2021-11-27_00-55-19.png)

![](figures/2021-12-14_01-48-57.png)

:::

:::{.exercise title="?"}
Show that if $f: \Delta\to\Delta$ is a biholomorphism with $f(0) = 0$ then $f$ is a rotation.


#complex/exercise/completed

:::

:::{.solution}
By Schwarz, $\abs{f(z)} \leq \abs{z}$, and if we write $h \da f\inv$ then $h(0) = 0$ and $\abs{h(z)} \leq \abs{z}$ as well.
Schwarz says $f$ will be a rotation if there is any $z_0$ such that $\abs{f(z_0)} = \abs{z_0}$.
Write $f(z) = w$, we'll then show that in fact $\abs{f(z)} = \abs{z}$ for all $z\in \DD$.
\[
\abs{z} = \abs{(h\circ f)(z)} = \abs{h(w)} \leq \abs{w} = \abs{f(z)}\leq \abs{z}
.\]
:::

:::{.exercise title="?"}
Let $f\in \Hol(\DD)$.
Show that if $f$ has a fixed point $a$ then $\abs{f'(a)} \leq 1$, and that 
\[
\abs{f(0)}^2 + \abs{f'(0)}^2 \leq 1
.\]
:::

:::{.solution}
Set $f(a) = a$ in Schwarz-Pick:
\[
\left|f^{\prime}(a)\right| \leq \frac{1-|f(a)|^{2}}{1-|a|^{2}} \implies 
\abs{f'(a)} \leq {1 - \abs{a}^2 \over 1 - \abs{a}^2} \leq 1
.\]
Set $a=0$:
\[
\left|f^{\prime}(0)\right| \leq \frac{1-|f(0)|^{2}}{1-|0|^{2}} \implies \abs{f'(0)}^2 \leq 1 - \abs{f(0)}^2
.\]

#complex/exercise/work

:::

![[attachments/Pasted image 20211215022943.png]]


:::{.exercise title="The standard function juggling trick"}
Show that if $f:\HH\to \DD$ is holomorphic and $f(i) = 0$ then $\abs{f(z)} \leq \abs{z-i\over z+i}$.

#complex/exercises/completed

:::

:::{.solution}
Note that
\[
\abs{f(z)} \leq \abs{g(z)} \impliedby \abs{(f\circ g\inv)(z)} \leq \abs{z}
,\]
so one can use the Schwarz lemma on $F \da f\circ g\inv$.
Noting that $g(z) \da {z-i\over z+i}: \HH\to \DD$ is the Cayley map, the inverse is $g\inv(z) = i{1-z\over 1+z}: \DD\to \HH$. 
Then $F(0) = f(g\inv(0)) = f(i) = 0$ by assumption, so Schwarz yield $\abs{F(z)} \leq \abs{z}$.
:::


