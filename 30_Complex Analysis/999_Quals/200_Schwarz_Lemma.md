---
order: 200
title: "Schwarz Lemma"
---

# Schwarz Lemma

## Fall 2020.7 #complex/qual/completed

^4c605e

:::{.problem title="?"}
Suppose that $f: \mathbb{D} \rightarrow \mathbb{D}$ is holomorphic and $f(0)=0$. Let $n \geq 1$, and define the function $f_{n}(z)$ to be the $n$-th composition of $f$ with itself; more precisely, let

$$
f_{1}(z):=f(z), f_{2}(z):=f(f(z)), \text { in general } f_{n}(z):=f\left(f_{n-1}(z)\right) .
$$

Suppose that for each $z \in \mathbb{D}, \lim _{n \rightarrow \infty} f_{n}(z)$ exists and equals to $g(z)$. Prove that either $g(z) \equiv 0$ or $g(z)=z$ for all $z \in D$.

:::

:::{.solution}
Note that there is a unique fixed point.
We have $f(0) = 0$, so there is at least one, so suppose $a$ is another fixed point with $f(a) = a$.
By Schwarz, $\abs{f(z)}\leq \abs{z}$ with equality at any nonzero point implying $f$ is a rotation, and $f(a) = a\implies \abs{f(a)} = \abs{a}$, so write $f(z) = e^{i\theta}z$.
Now $f(a) = a = e^{i\theta }a$ forces $\theta = 0$, so $f(z) = z$ is the identity.


Since $f(0) = 0$, the Schwarz lemma applies and either

- $f(z) = e^{i\theta} z$ is a rotation, or
- $\abs{f'(0)} < 1$ and $\abs{f(z)} < z$ for all $z\in \DD$.

Supposing the latter, $f$ is a contraction, and $\abs{f_{n+1}(z)} < \abs{f_{n}(z)}$ for all $n$ and all $z$, so $\abs{f_n(z)} \convergesto{n\to\infty} 0$ for all $z$.
Since $f_n\to g$ pointwise, this means $g(z) = 0$ for all $z$, making $g\equiv 0$.

Otherwise, suppose $f$ is a rotation.
Then if $f(z) = e^{i\theta}z$, $f_n(z) = e^{in\theta}z$.
The pointwise limit $\lim_{n\to\infty}e^{in\theta}z$ can only exist if $\theta = 0$, otherwise this is periodic when $\theta$ is rational or the points $e^{i\theta}z, e^{2i\theta }z,\cdots$ form form a countably infinite set of distinct points.
So $f(z) = z$, making $\lim_{n\to \infty}f_n(z) = z$ as well.
:::


## Fall 2020.4 #complex/qual/stuck

^0f90ac


:::{.problem title="?"}
Let $\mathbb{D}:=\{z:|z|<1\}$ denote the open unit disk. Suppose that $f(z): \mathbb{D} \rightarrow \mathbb{D}$ is holomorphic, and that there exists $a \in \mathbb{D} \backslash\{0\}$ such that $f(a)=f(-a)=0$.

- Prove that $|f(0)| \leq|a|^{2}$.

- What can you conclude when $|f(0)|=|a|^{2} ?$

:::

:::{.solution}
**Part 1**:

Write $B_{z_0}(z) \da {z-z_0\over 1-\bar{z_0}z}$ for the Blaschke factor associated to $z_0$, which swaps $z_0$ and $0$.
Define
\[
g(z) \da {f(z) \over B_a(z) B_{-a}(z)}
.\]
Then $\abs{g(z)}\leq 1$ on $\DD$, and in particular, $\abs{g(0)} \leq 1$. 
Rewriting this yields
\[
1\geq \abs{g(0)} = {\abs{f(0)} \over \abs{B_a(0)} \cdot \abs{B_{-a}(0)}}
= {\abs{f(0)} \over \abs{a}^2} \implies \abs{a}^2 \geq \abs{f(0)}
.\]

**Part 2**:
Applying Schwarz-Pick:
\[
\abs{f'(0)} \leq {1 - \abs{f(0)}^2 \over 1 - \abs{0}^2 } = 1-\abs{a}^2 < 1
,\]
using that $a\neq 0$, so $f$ is a contraction.

#todo Is there more..?


:::


## Spring 2020.7 #complex/qual/work

^aff739

Let $f$ be analytic on a bounded domain $D$, and assume also that $f$ that is continuous and nowhere zero on the closure $\bar{D}$. 

Show that if $|f(z)|=M$ (a constant) for $z$ on the boundary of $D$, then $f(z)=e^{i \theta} M$ for $z$ in $D$, where $\theta$ is a real constant.

## Spring 2019.5 #complex/qual/work

^5d5430

Suppose that $f(z)$ is holomorphic on $\mathbb{D}$ and that $|f(z)|<1$. Show that

$$
\left|\frac{f(z)-f\left(z_{0}\right)}
{1-{ \bar{ f\left(z_{0}\right) } f(z)}}\right| \leq\left|\frac{z-z_{0}}{1-\bar{z}_{0} z}\right|
$$

> Hint: Schwarz lemma.

## Spring 2021.5 #complex/qual/completed

^14ad86

:::{.problem title="?"}
Let $f$ be a holomorphic map of the open unit disc $\DD$ to itself.
Show that for any $z, w\in \DD$,
\[
\left|\frac{f(w)-f(z)}{1-\overline{f(w)} f(z)}\right| \leq\left|\frac{w-z}{1-\bar{w} z}\right|
.\]
Show that this inequality is strict for $z\neq w$ except when $f$ is a linear fractional transformation from $\DD$ to itself.
:::

:::{.concept}

![](figures/2021-11-27_01-09-06.png)

:::


:::{.solution .foldopen}
This is the **Schwarz–Pick theorem**.

- Fix $z_1$ and let $w_1 = f(z_1)$.
  Define
  \[
  \psi_{a}(z) \da {a-z \over 1-\bar{a}z} \in \Aut(\DD)
  .\]

  - Note that inequality now reads
  \[
  \abs{\psi_{f(w)}(f(z)) } \leq \abs{\psi_w(z)}
  .\]
  Moreover $\psi_a$ is an involution that swaps $a$ and $0$.

- Now set up a situation where Schwarz's lemma will apply: 
\[
0 \mapsvia{\psi_{z_1}} z_1 \mapsvia{f} f(z) \mapsvia{\psi_{f(z_1)}} 0 
,\]
  so $F\da \psi_{f(z_1)} \circ f \circ \psi_{z_1} \in \Aut(\DD)$ and $F(0) = 0$.

- Apply Schwarz we get $\abs{F(z)} \leq \abs{z}$ for all $z$, so
\[
\abs{F(z)} &\leq \abs{z} \\
\implies \abs{
f(z_1) - (f\circ \psi_{z_1})(z) 
\over 
1 - \bar{f(z_1)} \cdot (f\circ \psi_{z_1}) (z)
} &\leq \abs{ z} \\
\implies \abs{f(z_1) - f(w) \over 1 - \bar{f(z_1)}\cdot f(w) }
&\leq \abs{\psi_{z_1}(z)}
&& w\da \psi_{z_1}(z) \\
\implies \abs{f(z_1) - f(w) \over 1 - \bar{f(z_1)}\cdot f(w) }
&\leq \abs{z_1 - z \over 1 - \bar{z_1} z }
.\]

- Since $z_1$ was arbitrary and fixed and $w$ was a free variable, this holds for all $z,w\in \DD$.

- Strictness: suppose equality holds, we'll show that $f(z) = {az+b\over cz+d}$
- By Schwarz, $F(z) = \lambda z$ for $\lambda \in S^1$.
  Thus
  \[
  (\psi_{f(z_1)} \circ f \circ \psi_{z_1}) (z) &= \lambda z \\
  \implies
  (f \circ \psi_{z_1}) (z) &= \psi_{f(z_1)}\inv(\lambda z ) \\
  \implies
  f(w) &= \psi_{f(z_1)}\inv(\lambda \psi_{z_1}\inv(w) ) 
  && w\da \psi_{z_1}(z) \\
  &= \psi_{f(z_1)} \qty{\lambda \psi_{z_1}(w)} \\
  &= \lambda \psi_{\bar \lambda f(z_1)} \qty{\psi_{z_1}(w)} \\
  &\da \lambda \psi_a(\psi_b(w)) \\
  &=\lambda\qty{ a- \psi_b(w) \over 1 - \bar a \psi_b(w) } \\
  &= \quad \vdots \\
  &= -\lambda \qty{ \frac{{\left(a \overline{b} - 1\right)} z - a + b}{{\left(\overline{a} - \overline{b}\right)}z - b \overline{a} + 1} } \\
  &= \qty{ \frac{-\lambda {\left(a \overline{b} - 1\right)} z + \lambda( a - b)}{{\left(\overline{a} - \overline{b}\right)}z + (- b \overline{a} + 1)} }
  ,\]
  which is evidently a linear fractional transformation.

:::

:::{.remark}
Note that Schwarz also provides an actual bound for $F'$ here -- applying the chain rule yields
\[
F' = \qty{ \psi_{f(z_1)} \circ f \circ \psi_{z_1}}'
= \qty{\psi'_{f(z_1)} \circ f \circ \psi_{z_1}} \cdot (f' \circ \psi_{z_1}) \cdot \psi'_{z_1}
.\]

Now use that (up to absolute values)

- $\psi_{z_1}(0) = z_1$
- $\psi'_{z_1}(0) = 1-\abs{z_1}^2$
- $\psi_a' = {1-\abs{a}^2 \over (1-\bar{a}z)^2 }$

and evaluate:
\[
F'(0) 
&= \psi'_{f(z_1)}(f(z_1)) \cdot f'(z_1) \cdot \qty{1 - \abs{z_1}^2} \\
&= \qty{ 1 - \abs{ f(z_1)}^2 \over \qty{1 - \bar{f(z_1)} f(z_1) }^2 } \cdot f'(z_1) \cdot \qty{1 - \abs{z_1}^2} \\
&= \qty{ 1 - \abs{ f(z_1)}^2 \over \qty{1 - \abs{f(z_1)}^2}^2 } \cdot f'(z_1) \cdot \qty{1 - \abs{z_1}^2} \\
&= f'(z_1) \qty{ 1 - \abs{z_1}^2 \over 1 - \abs{f(z_1)}^2 } \\
&\leq 1 &&\text{by Schwarz}
,\]
so
\[
f'(z_1) \leq {1- \abs{f(z_1)}^2 \over 1 - \abs{z_1}^2}
.\]

> Note: I've sloppily left absolute values off of everything and freely swapped orders of terms!

:::


## Fall 2021.5  #complex/qual/completed

^ee1748

:::{.problem title="?"}
Assume $f$ is an entire function such that $|f(z)|=1$ on $|z|=1$. Prove that $f(z)=e^{i \theta} z^{n}$, where $\theta$ is a real number and $n$ a non-negative integer. 

> Suggestion: First use the maximum and minimum modulus theorem to show 
$$
f(z)=e^{i \theta} \prod_{k=1}^{n} \frac{z-z_{k}}{1-\bar{z_{k}} z}
$$ 
if $f$ has zeros.

:::

:::{.solution}
First show the hint: assume $f$ has nonzero zeros.
Write $Z(f) \da f\inv(0)$ for the set of zeros in $\bar{\DD}$.

:::{.claim}
If we assume $f$ is continuous on $\DD$, then $\size Z(f) < \infty$
:::

:::{.proof title="?"}
Suppose $\size Z(f) = \infty$, then by compactness of $\bar{\DD}$ there is a limit point $z_0$.
If $z_0 \in \DD$, then there is a sequence $\ts{z_k}\to z_0$ with $f(z_k) = 0$ for every $k$, so $f$ is zero on a set $S\da \ts{z_k}_{k\geq 1} \union \ts{z_0}$ with an accumulation point and this forces $f\equiv 0$ on $\bar{\DD}$ by the identity principle, contradicting $\abs{f} = 1$ on $\bd \DD$>

Otherwise, if $z_0\in \bd \DD$, using continuity of $f$ we have $f(z_k) = 0$ for all $k$ and $z_k\to z_0$ so $f(z_0) = 0$, again contradiicting $\abs{f} = 1$ on $\bd \DD$.
:::

So write $Z(f) = \ts{z_1,\cdots, z_m}$ and define 
\[
g(z) \da \prod_{1\leq k \leq m} {z-z_k \over 1 - \bar{z_k} z},
\quad
h(z) \da {f(z) \over g(z)}
.\]

:::{.claim}
$h(z) \equiv 1$ is constant on $\bar{\DD}$, so that $f = \lambda g$ for some $\lambda \in S^1$, i.e. $\lambda = e^{i\theta}$ for some $\theta$.
:::

:::{.proof title="?"}
Note that $h$ cancels all zeros of $f$, so $h$ is nonzero and holomorphic on $\bar{\DD}$.
Moreover $\abs{g(z)} \leq 1$ on $\bar{\DD}$ since these are well-known to be in $\Aut(\DD)$.
It's also well-known that $\abs{g(z)} = 1$ on $\bd \DD$.
Thus $\abs{h(z)} = 1$ and $\abs{1\over h(z)} =1$ on $\bd \DD$, and by the maximum modulus principle, 
\[
\abs{h(z)} \leq 1 \quad\text{ and }\quad \abs{1\over h(z)}\leq 1 \quad \text{ on } \DD
,\]
forcing $\abs{h(z)}\equiv 1$ and thus $h(z) = e^{i\theta}$ for some $\theta$.



:::

So we now have
\[
f(z) = e^{i\theta} \prod_{1\leq k\leq m} {z-z_k \over 1 -\bar{z_k} z}
,\]
which has poles at points $z$ for which $\bar{z_k}z=1$ for some $z_k\in Z(f)$.
However, since we assumed $f$ was entire, it can have no such poles, which forces $z_k = 0$ for all $k$.
But then
\[
f(z) = e^{i\theta}\prod_{1\leq k \leq m}{z- 0 \over 1 - 0\cdot z} = e^{i\theta}z^m
.\]


:::

## Fall 2021.6 #complex/qual/completed

^33ab95

:::{.problem title="?"}
Show that if $f: D(0, R) \rightarrow \mathbb{C}$ is holomorphic, with $|f(z)| \leq M$ for some $M>0$, then
\[
\left|\frac{f(z)-f(0)}{M^{2}-\overline{f(0)} f(z)}\right| \leq \frac{|z|}{M R} .
\]
:::

:::{.solution}

> Proof due to Swaroop Hegde!

Fix $R, M$ and make a clever choice: define
\[
F: \DD &\to \CC \\
z &\mapsto {f(Rz) \over M}
.\]
Write $a\da F(0)$ and consider the Blaschke factor
\[
\psi_a(z) \da {a-z \over 1-\bar{a} z} \in \Aut(\DD)
,\]
and define
\[
g: \DD &\to \DD \\
z &\mapsto (\psi_a \circ F)(z)
.\]
Then $g(0) = 0$ and $\abs{g(z)} \leq 1$ for all $z\in \DD$, so by Schwarz we have $\abs{g(z)} \leq \abs{z}$ for all $z\in \DD$.
Thus for all $z\in \DD$,
\[
&\abs{g(z)} \leq z \\ \\
\iff & \abs{\psi_a(F(z)) } \leq \abs{z} \\ \\
\iff & \abs{ {f(Rz) \over M} - a \over 1 - {\bar a f(Rz) \over M}  } \leq \abs{z} \\ \\
\iff & \abs{f(Rz) - f(0) \over 1 - {\bar{f(0)} f(Rz) \over M^2 } } \leq \abs{z} \\ \\
\iff & \abs{f(Rz) - f(0) \over M^2 - \bar{f(0)} f(Rz) } \leq {\abs{z} \over M} \\ \\
\iff & \abs{f(w) - f(0) \over M^2 - \bar{f(0)} f(w) } \leq {\abs{w} \over MR}
,\]
which holds for all $w\in \DD$ by replacing $Rz$ with $w$ (i.e. to show this equality for arbitrary $w\in \DD$, write $w = Rz$ for some $z\in \DD$ and run this chain of inequalities backward).




:::

## 1 #complex/exercise/work
Suppose $f:\DD\to\DD$ is analytic and admits a continuous extension $\tilde f: \bar \DD \to \bar \DD$ such that $\abs{z} = 1 \implies \abs{f(z)} = 1$.

a.
Prove that $f$ is a rational function.

b.
Suppose that $z=0$ is the unique zero of $f$.
Show that
\[  
\exists n\in \NN, \lambda \in S^1 \qtext{ such that }f(z) = \lambda z^n
.\]

c
Suppose that $a_1, \cdots, a_n \in \DD$ are the zeros of $f$ and prove that
\[  
\exists \lambda \in S^1 \qtext{such that} f(z) = \lambda \prod_{j=1}^n {z - a_j \over 1 - \bar{a_j} z}
.\]

## 2 #complex/exercise/work
Let $\bar B(a, r)$ denote the closed disc of radius $r$ about $a\in \CC$.
Let $f$ be holomorphic on an open set containing $\bar B(a, r)$ and let 
\[  
M \definedas \sup_{z\in \bar B(a, r)} \abs{f(z)}
.\]

Prove that 
\[  
z\in \bar B\qty{a, {r\over 2}},\,z\neq a, \qquad {\abs{ f(z) - f(a)} \over \abs{z-a}} \leq {2M \over r}
.\]

## 3 #complex/exercise/work
Define
\[  
G \definedas \theset{z\in \CC\suchthat \Re(z) > 0, \, \abs{z-1} > 1}
.\]

Find all of the injective conformal maps $G\to \DD$.
These may be expressed as compositions of maps, but explain why this list is complete.



## 5 #complex/exercise/work
Suppose $f: \DD\to \HH$ is analytic and satisfies $f(0) = 2$.
Find a sharp upper bound for $\abs{f'(0)}$, and prove it is sharp by example.

## 6 #complex/exercise/work
Suppose $f:\DD\to\DD$ is analytic, has a single zero of order $k$ at $z=0$, and satisfies $\lim_{\abs z \to 1} \abs{f(z)} = 1$.
Give with proof a formula for $f(z)$.



## 8 #complex/exercise/work
Suppose $f, g: \DD\to \Omega$ are holomorphic with $f$ injective and $f(0) = g(0)$.

Show that 
\[  
\Forall 0 < r < 1,\qquad g\qty{\theset{\abs{z} < r}} \subseteq f\qty{\theset{\abs{z} < r}}
.\]

> The first part of this problem asks for a statement of the Schwarz lemma.

## 9 #complex/exercise/work
Let $S\definedas \theset{z\in \DD\suchthat \Im(z) \geq 0}$.
Suppose $f:S\to \CC$ is continuous on $S$, real on $S\intersect \RR$, and holomorphic on $S^\circ$.

Prove that $f$ is the restriction of a holomorphic function on $\DD$.

## 10 #complex/exercise/work
Suppose $f:\DD\to \DD$ is analytic.
Prove that 
\[  
\forall a\in \DD, \qquad {\abs{f'(a)} \over 1 - \abs{f(a)}^2 } \leq {1 \over 1 - \abs{a}^2}
.\]

### Tie's Extra Questions: Fall 2009
Let $g$ be analytic for $|z|\leq 1$ and $|g(z)| < 1$ for $|z| = 1$.

1.  Show that $g$ has a unique fixed point in $|z| < 1$.

2.  What happens if we replace $|g(z)| < 1$ with $|g(z)|\leq 1$ for
    $|z|=1$? Give an example if (a) is not true or give an proof
    if (a) is still true.

3.  What happens if we simply assume that $f$ is analytic for
    $|z| < 1$ and $|f(z)| < 1$ for $|z| < 1$? Suppose that $f(z)
    \not\equiv  z$. Can f have more than one fixed point in
    $|z| < 1$?

> Hint: The map $\displaystyle{\psi_{\alpha}(z)=\frac{\alpha-z}{1-\bar{\alpha}z}}$ may be useful.

### Tie's Extra Questions: Fall 2015

(a) Let $z, w$ be complex numbers, such that $\bar{z} w \neq 1$.
Prove that
$$\abs{\frac{w - z}{1 - \bar{w} z}} < 1 \; \; \; \mbox{if} \; |z| < 1 \; \mbox{and}\; |w| < 1,$$
and also that
$$\abs{\frac{w - z}{1 - \bar{w} z}} = 1 \; \; \; \mbox{if} \; |z| = 1 \; \mbox{or}\; |w| = 1.$$

(b) Prove that for fixed $w$ in the unit disk $\mathbb D$, the
mapping $$F: z \mapsto \frac{w - z}{1 - \bar{w} z}$$ satisfies the following conditions:

(i) $F$ maps $\mathbb D$ to itself and is holomorphic. 

(ii) $F$ interchanges $0$ and $w$, namely, $F(0) = w$ and
$F(w) = 0$.

(iii) $|F(z)| = 1$ if $|z| = 1$.

(iv) $F: {\mathbb D} \mapsto {\mathbb D}$ is bijective.

> Hint: Calculate $F \circ F$.

### Tie's Extra Questions: Spring 2015


Suppose $f$ is analytic in an open set containing the unit disc $\mathbb D$ and $|f(z)| =1$ when $|z|$=1. Show that either $f(z) = e^{i \theta}$ for some $\theta \in \mathbb R$ or there are
finite number of $z_k \in \mathbb D$, $k \leq n$ and
$\theta \in \mathbb R$ such that
$\displaystyle f(z) = e^{i\theta} \prod_{k=1}^n \frac{z-z_k}{1 - \bar{z}_k z } \, .$

> Also cf. Stein et al, 1.4.7, 3.8.17



### Tie's Extra Questions: Spring 2015


Let $f$ and $g$ be non-zero analytic functions on a region $\Omega$.
Assume $|f(z)| = |g(z)|$ for all $z$ in $\Omega$. Show that
$f(z) = e^{i \theta} g(z)$ in $\Omega$ for some
$0 \leq \theta < 2 \pi$.

