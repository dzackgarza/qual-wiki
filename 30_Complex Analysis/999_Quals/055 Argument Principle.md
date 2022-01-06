---
order: 55
title: "Argument Principle"
status: completed
---

# Argument Principle

## Spring 2020 HW 3.12 (Root counting with argument principle) #complex/exercise/completed

:::{.problem title="?"}
Prove that $f(z) = z^4 + 2z^3 -2z + 10$ has exactly one root in each open
quadrant.
:::

:::{.solution}
It suffices to show there's only one root in the open quadrant $Q_1$, since they come in conjugate pairs.
Assume that there are no roots on $\RR$ or $i\RR$.
Since polynomials are entire, the argument principle can be used to count zeros:
\[
Z_f = {1\over 2\pi i}\int_\gamma \logd f(z)\dz = \Delta_\gamma \Arg(f)
.\]
To take the curve $\gamma$ comprised of

- $\gamma_1 = [0, R]$,
- $\gamma_2 = Re^{it}$ for $t\in [0, \pi/2]$
- $\gamma_3 = i[0, R]$.

Then

- $\Delta_{\gamma_1}\Arg(f) = 0$, since $f(\RR_{\geq 0}) \subseteq \RR_{\geq 0}$.
- $\Delta_{\gamma_2}\Arg(f) = 4\cdot {\pi\over 2} = 2\pi$ since $f\sim z^4$ for large $R$.
- $\Delta_{\gamma_3}\Arg(f)$: consider
\[
f(it) = t^4 - it^3 -2it + 10 = t^4\qty{1 - it\inv -2it^{-2} +10t^{-4}} \\
\implies \Arg(f(it)) \sim \Arg(t^4) =0
.\]

So $\Delta_\gamma \Arg(f) = 1$, meaning there is one zero enclosed by $\gamma$ for $R$ large enough.
As $R\to \infty$, this covers $Q_1$.
:::

## Tie's Extra Questions: Fall 2015 #complex/exercise/work

:::{.problem title="?"}
Prove that $z^4 + 2 z^3 - 2z + 10 =0$ has exactly one root in each open quadrant.
:::


### $n$-to-one functions #complex/exercise/completed

:::{.problem title="?"}
Let $f$ be analytic in a domain $D$ and fix $z_0 \in D$ with $w_0 \definedas f(z_0)$.
Suppose $z_0$ is a zero of $f(z) - w_0$ with finite multiplicity $m$.
Show that there exists $\delta >0$ and $\eps > 0$ such that for each $w$ such that $0 < \abs{w-w_0} < \eps$, the equation $f(z) - w = 0$ has exactly $m$ *distinct* solutions inside the disc $\abs{z-z_0} < \delta$.
:::

:::{.solution}
Write $g(z) \da f(z) - w_0$, then $g$ is holomorphic on $D$ and thus $w_0$ is an isolated zero.
Choose $\delta$ small enough so that $g$ is nonvanishing on $\DD_\delta(z_0)\smts{z_0}$.
Let 
\[
\gamma \da \ts{\abs{\xi - z_0} = \delta }= \bd\DD_{\delta}(z_0)
.\]
Choose $\eps < \inf\ts{w\in f(\delta)}$ so that $\abs{f(z) - w_0} > \eps$ in $\DD_\eps(w_0)\smts{w_0}$ for every $z\in \gamma$.
Let 
\[
\gamma' \da \bd \DD_{\eps}(w_0) = \ts{\abs{z-w_0} = \eps}
,\]
and
define the solution counting function:
\[
F(w) 
\da {1\over 2\pi i} \oint_{\gamma'} \logd(g(z)) \dz 
= {1\over 2\pi i } \oint_{\gamma'} {g'(z)\over g(z) }\dz
= {1\over 2\pi i} \oint_{\gamma'} {f'(z)\over f(z) - w} \dz
,\]
which counts the zeros of $g$ (since it has no poles) and consequently the number of solutions to $f(z) = w$ in $\DD_\eps(w_0)$.
This is now a continuous integer valued function on $\DD_\eps(w_0)$, and is thus constant.
Since $f(z_0) = w_0$ with $z_0$ enclosed by $\gamma$ and $w_0$ enclosed by $\gamma'$, the constant is exactly the multiplicity of the zero of $f(z) - w_0$ at $z_0$, which is $m$.
:::



### Blaschke products are $n$ to one #complex/exercise/completed

:::{.problem title="?"}
For $k=1,2,\cdots, n$, suppose $\abs{a_k} < 1$ and
\[
f(z) \da \qty{z - a_1 \over 1 - \bar a_1 z} \qty{z-a_2 \over 1 - \bar a_2 z} \cdots \qty{z - a_n \over 1 - \bar a_n z}
.\]
Show that $f(z) = b$ has $n$ solutions in $\abs{z} < 1$.
:::

:::{.solution}
Note that $f$ is holomorphic on $\DD$ and $S^1$, since the poles are at $1/\bar{a_k}$ and if $\abs{a_l} < 1$ then $\abs{\bar{a_k}} > 1$.
Fix $b$, then define $g_w(z) \da f(z) - w$ and form the solution counting function
\[
F(w) \da {1\over 2\pi i}\oint_{S^1} \logd g_w(z) \dz
= {1\over 2\pi i} \oint_{S^1} {f'(z) \over f(z)-w}\dz
.\]
Start by computing $F(0)$.
\[
F(0) 
&= {1\over 2\pi i }\oint_{S^1} \logd \prod_{1\leq k\leq n} \psi_{a_k}(z) \dz \\
&= {1\over 2\pi i }\oint_{S^1} \sum_{1\leq k\leq n} \logd \psi_{a_k}(z) \dz \\
&= {1\over 2\pi i }\oint_{S^1} \sum_{1\leq k\leq n} \qty{1-\abs{a_k}^2 \over (1-\bar{a_k} z)^2} \qty{z-a_k \over 1-\bar{a_k} z}\inv \dz \\
&= {1\over 2\pi i }\oint_{S^1} \sum_{1\leq k\leq n} {1-\abs{a_k}^2 \over (z-a_k)( 1-\bar{a_k}z) } \dz \\
&= {1\over 2\pi i } \sum_{1\leq k\leq n} \oint_{S^1} {1-\abs{a_k}^2 \over (z-a_k)( 1-\bar{a_k}z) } \dz \\
&= {1\over 2\pi i } \sum_{1\leq k\leq n} 2\pi i \\
&= n
,\]
where we've used that the integrand has a simple pole at $a_k$ since $1/\bar{a_k}\in \DD^c$.
So the equation $f(z) = 0$ has $n$ solutions.
Now use that $F$ is a continuous function of $w$ on $\DD$ and integer valued, thus constant.
So $F(w) = n$ for any $w$, meaning $f(z) = w$ has $n$ solutions in $\DD$ for every $w$.

> Alternative: $F$ continuously depends on the $a_k$, so send them all to zero to get $f(z) = z^n$ which trivially has $n$ zeros.

:::

