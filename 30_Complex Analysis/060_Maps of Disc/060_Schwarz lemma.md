# Schwarz

## Hyperbolic Translations / Blaschke Factors

:::{.definition title="Hyperbolic translations/Blaschke factors"}
For $a\in \DD$, the maps
\[
\psi_a \da {a-z\over 1-\bar{a}z}
\]
are *hyperbolic translations* because they preserve the hyperbolic metric on the PoincarĂ© disc.
They're also commonly called **Blaschke factors**, and also sometimes taken to be
\[
\phi_a \da {z-a \over 1-\bar{a} z} = - \psi_a
.\]
A rational map of the form
\[
\Psi_{\vector a}(z) = \lambda \prod_{1\leq k\leq n} \psi_a(z) = \lambda \prod_{1\leq k \leq n} {a_i - z\over 1 - \bar{a_i} z},\qquad \vector a\da\tv{a_1,\cdots, a_n}
\]
with zeros $a_i \in \DD$ is called a **Blaschke product** and is a map $\DD\to \DD$ that preserves $S^1$.
:::

:::{.proposition title="Properties of hyperbolic translations / Blaschke factors"}
Some useful properties:

- $\psi_a \in \Aut(\DD)$
- $\psi_a(S^1) = S^1$
- $\psi_a(0) = a$ and $\psi(a) = 0$
- With this choice of sign, $\psi_{a} \inv = \psi_{a}$, so $\psi_a^2 = \id$.
- $\psi_a'(z) = {\abs{a}^2 - 1 \over \qty{1-\bar{a} z}^2 }$
- $\psi_a(\lambda z) = \lambda\psi_{\bar\lambda a}(z)$
:::

:::{.proof title="of properties"}
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

Being an involution: check $\psi_a(\psi_a(z))$ satisfies the Schwarz lemma and has two fixed points, forcing it to be the identity.
:::

:::{.theorem title="Structure theorem: automorphisms of the disc"}
Every map $g\in \Aut(\DD)$ is of the form 

\[
\Aut(\DD) = \ts{ \lambda \psi_a(z) \st a\in \DD, \lambda \in S^1 }
,\]
i.e. they are all Blaschke factors and rotations.
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

:::{.proof title="of Schwarz"}
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

## Blaschke Factors

:::{.exercise title="Bounded above by Blaschke product"}
Let $f: \DD\to \DD$ with $\ts{a_k}_{k\leq n}$ the zeros of $f$ in $\DD$.
Show that
\[
\abs{f(z)}\leq \prod_{k\leq n} \abs{ \psi_{a_k}(z) }
.\]

#complex/exercise/completed

:::

:::{.solution}
Define $\Psi(z) \da \prod_{k\leq n} \psi_{a_k}(z)$ and $g(z) \da f(z)/\Psi(z)$.
The claim is that $\abs{g(z)} \leq 1$, which implies the result directly.
Note that $\abs{\Psi(z)} = 1$ for $\abs{z} = 1$, so $\lim_{r\to 1^-} \abs{\Psi(re^{it})} = 1$ along any ray.
Now for $z_r \da re^{it}$ for $r< 1$,
\[
\abs{g(z_r)} = { \abs{f(z_r)} \over \abs{\Psi(z_r)} } \leq {1\over \abs{\Psi(z_r)} } \leq {1\over \displaystyle\sup_{t\in [0, 2\pi]} \abs{\Psi(z_r) } } \convergesto{r\to 1^-} 1
.\]
:::



## Schwarz-Fu

:::{.exercise title="Schwarz with domain/codomain scaled"}
If $f: \DD_R(a)\to\DD_M(0)$ with $f(a) = 0$, then 
\[
\abs{f(z)}\leq {M\over R}\abs{z-a}
.\]

#complex/exercise/completed

:::

:::{.solution}
Set $g(z) \da {f(Rz + a) \over M}$, then $g: \DD\to \DD$ with $g(0) = f(a)/M = 0$, so unwinding Schwarz yields
\[
\abs{g(z)} \leq \abs{z} 
\implies \abs{f(Rz+a)\over M}
&\leq \abs{z} \\
\implies \abs{f(Rz+a)} &\leq M\abs{z} \\
\implies \abs{f(w)} &\leq M\abs{w-a\over R} \qquad w = Rz+a\implies z={w-a\over R}
.\]
:::

:::{.exercise title="Forcing a map to be the identity"}
Let $\psi_a$ be a Blaschke factor and use the Schwarz lemma to prove that $\psi_a \circ \psi_a = \id_\DD$.

#complex/exercise/completed

:::

:::{.solution}
First, $\psi_a$ maps $\DD\to \DD$.
Fix $z\in S^1$, then
\[
\abs{\psi_a(z)} \da 
\abs{a-z\over 1-\bar{a} z}
&= \abs{a-z\over 1-\bar{a} z} \cdot \abs{\bar z}\inv \\
&= \abs{a-z\over \bar{a} - \bar{z}} \\
&= \abs{a-z \over \bar{a-z} } \\
&\da \abs{w \over \bar w } \\
&= \abs{w \over \abs{w}^2/w }\\
&= \abs{w^2 \over \abs{w}^2} \\
&= 1
.\]
$\psi_a$ is holomorphic on $\DD$ since it has a simple pole at $z=1/\bar{a}$, but $\abs{a}<1$ implies $\abs{1/\bar{a}} > 1$.
Let $g\da \psi_a\circ \psi_a$, then $g(0) = 0$ so Schwarz applies.
Since $g(a) = a$ with $a\neq 0$, the 2nd part of Schwarz also applies since $\abs{g(a)} = \abs{a}$ and $g(z) = \lambda z$ is a rotation.
Since $a = g(a) = \lambda a$, this forces $\lambda = 1$, so $g$ is the identity.
:::

:::{.exercise title="Schwarz-Pick Lemma"}
Prove the following:
suppose $\abs{f(z)}\leq 1$, then for all $z, w\in \DD$,
\[
\left|\frac{f(z)-f(w)}{1-\overline{f(w)} f(z)}\right| \leq\left|\frac{z-w}{1-\bar{w} z}\right|
\quad\text{ and }
\left|f^{\prime}(z)\right| \leq \frac{1-|f(z)|^{2}}{1-|z|^{2}}
.\]
If equality holds for some $z\neq w$ in either expression, then $f= \lambda F$ where $F$ is a linear fractional transformation and $\abs{\lambda} = 1$, so $f\in \Aut(\DD)$.

> Note that this does not require $f(0) = 0$.

#complex/exercise/completed

:::

:::{.proof title="of Schwarz-Pick"}

![](figures/2021-11-27_00-55-19.png)

![](figures/2021-12-14_01-48-57.png)

:::

:::{.exercise title="Special case of bijections"}
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

:::{.solution title="Shorter version"}
By Schwarz, $\abs{f'(0)} \leq 1$ -- the claim is that we have equality, so that by Schwarz $f(z) = \lambda z$ for some $\abs{\lambda} = 1$.
Use that $f'(0) \neq 0$ since $f$ is a bijection near zero and if $g\da f\inv$ then $g'(0) = 1/f'(0)$.
Moreover Schwarz applies to $g$, so $1 \geq \abs{g'(0)} \geq {1\over \abs{f'(0)} }$, forcing $\abs{ f'(0) } = 1$.
By the equality clause in the Schwarz lemma for $f$, $f$ is rotation.
:::

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

:::{.exercise title="More juggling"}
Suppose $f:\DD\to \DD$ with $f(0) = 0$ and that there exists an $r\in (0, 1)$ with $f(r) = f(-r) = 0$.
Show that 
\[
\abs{f(z)} \leq \abs{z^2-r^2 \over 1-r^2 z^2}
.\]

#complex/exercise/completed

:::

:::{.solution}
The key observation is that this factors:
\[
{z^2 - r^2 \over 1-r^2 z^2} = {r-z\over 1+rz}{-r-z\over 1-rz} = \psi_{r}(z) \psi_{-r}(z)
,\]
so this inequality will follow from Schwarz on $g(z) \da f(z)/\psi_a(z)\psi_{-a}(z)$.
Schwarz does apply since $\abs{f}\leq 1$ in $\DD$ and $\abs{\psi_a(z)} = 1$ on $S^1$, so $\abs{g(z)} \leq 1$ on $S^1$ and by the MMP this inequality holds in all of $\DD$.
So $\abs{g(z)}\leq \abs{z}$ and unwinding gives the desired inequality.
:::

:::{.exercise title="Liouville"}
Use a version of the Schwarz lemma to prove Liouville's theorem.

#complex/exercise/completed

:::

:::{.solution}
Suppose $f$ is entire and bounded, we'll show $f$ is constant.
If $f$ is bounded by $M$, then $f(\CC) \subseteq \DD_M(0)$.
Without loss of generality, replace $f$ with $g(z) \da f(z) - f(0)$, so $g(0) = 0$ and is still bounded by $M' \da M + \abs{f(0)}$ by the triangle inequality.
This is still finite since $0$ is not a singularity since $f$ is entire.

By the radius $R$ variant of the Schwarz lemma, for every $\DD_R(0)$,
\[
\abs{g(z)} \leq {M\over R}\abs{z} \qquad \text{for } z\in \DD_R(0)
.\]
Using that $g(0) = 0$,
\[
\abs{g(z) - g(0) \over z} \leq {M\over R}\convergesto{R\to\infty}0
,\]
where dividing by $z$ is not an issue since $z=0$ is a zero of $g$ of at least order one.
This forces $g(z) = g(0) = 0$ for all $z$, so $f(z) = f(z_0)$ is constant.
:::

:::{.exercise title="Using derivatives"}
Let $f:\DD\to \DD$ with $f(0) = f'(0) = 0$.
Show that $\abs{f''(0)} \leq 2$ and describe all $f$ for which this is an equality.

#complex/exercise/completed

:::

:::{.solution}
By Schwarz, $\abs{f(z)}\leq z$.
Write $g(z) \da f(z)/z$, then $\abs{g(z)}\leq 1$ and $g:\DD\to \DD$ is holomorphic since $f$ has a zero of order at least one at $0$.
Note that $f(z) = c_2z^2 + \bigo(z^3)$, where $c_0 = 0$ since $f(0) = 0$ and $c_1 = 0$ since $f'(0) = 0$.
Thus $g(z) = c_2z + \bigo(z^2)$, and $g(0) = 0$, so Schwarz applies and

- $\abs{g(z)}\leq \abs{z}$
- $\abs{g'(0)} \leq 1$

We have $g'(z) = c_2 + \bigo(z)$ so $g'(0) = c_2 = {f^{(2)}(0) \over 2!}$.
\[
1 \geq \abs{g'(0)} = \abs{c_2} = \abs{f^{(2)}(0) \over 2} \implies \abs{ f^{(2)}(0) } \leq 2!
.\]

Suppose this is an equality -- then Schwarz on $g$ shows $g$ is a rotation, so
\[
{f(z)\over z} = g(z) = \lambda z \implies f(z) = \lambda z^2 \qquad \lambda \in S^1
.\]

> Note: if $\abs{z}\leq 1$, we have $g(\DD) \subseteq \bar{\DD}$, but the open mapping theorem always guarantees $g(\DD) = \DD$.

:::

:::{.exercise title="Fixed point convergence"}
Suppose $f:\DD\to \DD$ with $f(a) = a$ a fixed point where $\abs{f'(a)} < 1$.
Show that for any initial point $z_0$, the sequence $z_k \da f(z_{k-1})$ converges to $a$.

#complex/exercise/completed

:::

:::{.solution}
First suppose $a=0$ -- then Schwarz applies, and since $\abs{f'(a)} < 1$ is strict, $f$ is *not* a rotation.

:::{.claim}
For any choice of $z_0\in \DD$, there is an $r$ with $0< \abs{z_0} < r < 1$ and a constant $C<1$ such that $\abs{f(z)} \leq C\abs{z}$ for $\abs{z} < r$.
:::

With such an $r$ and $C<1$ in hand,

\[
\abs{z_k} = \abs{f(z_{k-1})} \leq C\abs{z_{k-1}} = C\abs{f(z_{k-2})} \leq C^2 \abs{z_{k-2}} \cdots \implies \abs{z_k} \leq C^k\abs{z_0} \convergesto{k\to\infty}0
,\]
which proves the $a=0$ case.

:::{.proof title="That $f$ is a contraction"}
The claim is that for any given $r$, the constant $C\da M/r$ works, where $M\da \max_{\abs{z} = r} \abs{f(z)}>0$.
The scaled Schwarz lemma gives $\abs{f(z)}\leq {M\over r}\abs{z} = C\abs{z}$, and $\abs{C} \leq 1$ since $\abs{M} \leq r$, which follows because $\abs{f(z)}\leq \abs{z}$ on $\DD$ itself.
:::

For $a\neq 0$, take a Blaschke factor $\psi_a(z)$ and consider $F \da \psi_a\inv \circ f\circ \psi_a$.
The claim is that this reduces to the case $a=0$.

Note $F(0) = 0$, so $0$ is a fixed point of $F$.
Moreover, a clever calculation shows
\[
F'(0) 
&= (\psi_a\inv)'(f(\psi_a(0))) \cdot f'(\psi_a(0)) \cdot \psi_a'(0) \\ \\
&= (\psi_a\inv)'(f( a )) \cdot f'(a ) \cdot \psi_a'(0) \\ \\
&= (\psi_a\inv)'(a) \cdot f'(a ) \cdot \psi_a'(0) \qquad \text{since } f(a) = a \\ \\
&= (\psi_a)'(a) \cdot \psi_a'(0) \cdot f'(a) \qquad \text{since } \psi_a\inv = \psi_a \\ \\
&= (\psi_a)'( \psi_a(0) ) \cdot \psi_a'(0) \cdot f'(a) \\ \\
&= (\psi_a \circ \psi_a)'(0) \cdot f'(a) \\
&= 1 \cdot f'(a)
,\]
so $\abs{F'(0)} = \abs{f'(a)} < 1$.
Now setting $w_k \da \psi_a(z_n)$ and writing $f = \psi_a \circ F \circ \psi_a\inv$, by continuity we have 
\[
f(z_k) = \psi_a(F(w_k)) \convergesto{k\to\infty} \psi_a(0) = a
.\]
:::

:::{.exercise title="Fixed points: multiple"}
Show that the only holomorphic map $f:\DD\to \DD$ two distinct fixed points $a\neq b$ is the identity.

#complex/exercise/completed

:::

:::{.solution}
Note that without loss of generality we can assume $a=0$ so $f(0) = 0$ and $b\neq 0$.
If not, if $a,b\neq 0$ then let $F\da \psi_a \circ f \circ \psi_a$, then $F(0) = 0$ and $F(b') = b'$ for $b\da \psi_a(b)$.

Since $f(0) = 0$, Schwarz applies, so $\abs{f(z)} = \abs{z}$ with equality attained because $\abs{f(b)} = \abs{b}$, and $f(z) = \lambda z$ must be a rotation.
Since $b = f(b) = \lambda b$, we have $\lambda = 1$.
:::

## Estimating

:::{.exercise title="Using the estimates"}
Let $f\in \Hol(\DD)$.
Show that if $f$ has a fixed point $a$ then $\abs{f'(a)} \leq 1$, and that 
\[
\abs{f(0)}^2 + \abs{f'(0)}^2 \leq 1
.\]

#complex/exercise/completed

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
:::

:::{.exercise title="Using the estimates"}
Does there exist a map $f: \DD\to \DD$ with

- $f\qty{1\over 2} = {3\over 4}$
- $f'\qty{1\over 2} = {2\over 3}$

#complex/exercise/completed

:::

:::{.solution}
Apply Schwarz-Pick:
\[
\abs{f'\qty{1\over 2} } \leq {1 - \abs{f\qty{1\over 2}}^2 \over 1 - \abs{1\over 2}^2 } = {7\over 2}< {2\over 3}
,\]
so this is not possible.
:::

:::{.exercise title="Using the estimates"}
Suppose $f: \DD\to \DD$ with $f(0) = 0$ and $\abs{f(z)} \leq \abs{e^z}$ when $\abs{z} = 1$.
Find an upper bound for $f\qty{1+i\over 2}$.

#complex/exercise/completed

:::

:::{.solution}
Consider $g(z) \da f(z)/e^z$ -- since $g(0) = 0$ and $g: \DD\to \DD$, Schwarz applies and 
\[
\abs{g(z)}\leq \abs{z} \implies \abs{f(z)} \leq \abs{ze^z} \leq e\abs{z}
.\]
So
\[
\abs{f\qty{1+i\over 2}} \leq e\abs{1+i\over 2}= {e\sqrt{2} \over 2}
.\]
:::

:::{.exercise title="Estimating and conformal maps"}
Suppose $f:\HH\to \CC$ with $\abs{f(z)}< 1$ and $f(i) = 0$.
Find an upper bound for $f(2i)$.

#complex/exercise/completed

:::

:::{.solution}
Compose with the inverse Cayley map $g(z) \da i{1+z\over 1-z}$ so $g: \DD\to \HH$ to get $F\da f\circ g:\DD\to \DD$, where $F(0) =f(g(0))=f(i) = 0$.
So Schwarz applies and $\abs{F(z)}\leq \abs{z}$.
Now a small trick:
\[
\abs{f(2i)} = \abs{(f\circ g\circ g\inv)(2i)} = \abs{ F \qty{z+i\over z-i}\evalfrom_{z=2i} } = \abs{F \qty{1\over 3} } \leq {1\over 3}
.\]
:::

:::{.exercise title="Combining with Rouche"}
Use RouchĂ©'s theorem and the Schwarz lemma to prove the following: if $f:\DD\to \bar{ \DD}$ is holomorphic with $f(0) = 0$, then there are exactly $m$ solutions (counted with multiplicity) to $f(z) = (2z)^m$ in the disc $\abs{z} < 1/2$.

#complex/exercise/completed

:::

:::{.solution}
First note that the image of $f$ is in fact $\DD$ rather than $\bar{\DD}$, using the open mapping theorem and that the domain $\DD$ is open.
So Schwarz applies to $f$.
Write $g(z) \da f(z) - (2z)^m$, the claim is that $g$ has $m$ zeros.
Toward applying RouchĂ©, identify 

- The big part of $g$: $M(z) \da -(2z)^m$ 
- The small part of $g$: $m(z) \da g(z) - M(z) = f(z)$.

Now
\[
\abs{m(z)} \da \abs{f(z)} \leq \abs{z} = {1\over 2} < \abs{m(z)} = \abs{2z}^m = 1 \qquad \text{on } \abs{z} = {1\over 2}
,\]
so RouchĂ© applies: $\size Z_m = \size Z_M$ on $\abs{z} < {1\over 2}$, where $m(z) = f(z)$ and $M(z) = -(2z)^m$ which has exactly $m$ zeros.

> Note that this works with $g(z) \da (cz)^m$ and $R = {1\over c}$.

:::

:::{.exercise title="Estimating and conformal maps"}
Suppose $f$ is holomorphic and $\abs{f(z)}\leq 1$ for $\Re(z) > 0$ with $f(1) = 0$.
Find an upper bound for $f(2)$.

#complex/exercise/completed

:::

:::{.solution}
Use the conformal map $g: z\mapsto -1{z+1\over z-1}$ to map $\Re(z)>0$ to $\DD$.
Composing $F: \DD \mapsvia{g} -i\HH \mapsvia{f} \DD$ yields a map $F = f\circ g:\DD\to \DD$.
Since $F(0) = f(g(0)) = f(1) = 0$, Schwarz applies and $\abs{F(z)} \leq \abs{z}$.
Using the standard trick,
\[
\abs{f(2)} = \abs{(f\circ \circ g\inv )(2)} = \abs{F(g\inv(2))} = \abs{F\qty{z-1\over z+1}\evalfrom_{z=2}} = \abs{F\qty{1\over 3}} \leq \abs{1\over 3}
.\]
:::

:::{.exercise title="The equality case"}
Suppose $f:\DD\to \DD$ and $f(0) = 0$.
Show that
\[
\abs{f(z) + f(-z)} \leq 2\abs{z}^2
,\]
with equality only if $f(z) = \lambda z^2$ for some $\abs{\lambda} = 1$.

#complex/exercise/completed

:::

:::{.solution}
Define $F(z) \da { f(z) + f(-z) \over 2 z^2}$, then $F(0) = 0$ and thus Schwarz applies and yields the desired inequality.
If $\abs{F(z)} = \abs{z}$ for any $z$, then $F(z) = \lambda z^2$ is a rotation and $f(z) + f(-z) = \lambda z$.
Noting that $F$ is an even function, $f(z) = \lambda z^2 + f_o(z)$ for $f_o$ some odd function.

:::{.claim}
$f_0$ is identically zero.
:::

Given this, the result follows immediately since $f(z) = \lambda z^2$.

:::{.proof title="of claim"}
Note that on the LHS, $\abs{ f(re^{it})} \to 1$ as $r\to 1$ for any $t$.
So this must be true on the RHS, and the first term $\lambda \abs{ re^{it}}^2 \to 1$, forcing $\abs{h(re^{it})} \to 0$.
So $h\equiv 0$ on $\abs{z} = 1$, and by the MMP, $\abs{h} = 0$ in $\DD$, making $h\equiv 0$ on $\DD$.
:::

:::


