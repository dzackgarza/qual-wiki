---
order: 5
---

# Calculus Preliminaries

## Derivatives and Integrals

:::{.proposition title="Contraction principle"}
If $(X, \abs{\wait})$ is a metric space and $f: X\to X$ with
\[
\abs{f(x) - f(y)} \leq c \abs{x-y} \text{ for some }c < 1, \forall x, y\in X
,\]
then $f$ is a **contraction**.
If $X$ is complete, then $f$ has a unique fixed point $x_0$ such that $f(x_0) = x_0$.
:::

:::{.proof title="?"}
Uniqueness: if $x, y$ are two fixed points, then 
\[
0 \leq \abs{x-y} = \abs{f(x) - f(y)}\leq c \abs{x-y}\leq \abs{x-y}
,\]
forcing $\abs{x-y} = 0$

Existence:
Define a sequence by picking $x_0$ arbitrarily and setting $x_k \da f(x_{k-1})$.
Then 
\[
\abs{x_{k+1}-x_k} = \abs{f(x_k) - f(x_{k-1}) } \leq c\abs{x_k - x_{k-1}}
,\]
so inductively
\[
\abs{x_{k+1}- x_k}\leq c^k \abs{x_1 - x_0}
.\]
The claim is that this makes $\ts{x_k}$ a Cauchy sequence, this follows from the fact that if $n < m$ then
\[
\abs{x_n - x_m} \leq \sum_{n+1\leq k \leq m} \abs{x_k - x_{k-1}} \leq \sum_{n \leq k \leq m-1} c^k \abs{x_1 - x_0} \leq c^n \abs{x_1 - x_0 \over 1-c} \to 0
.\]
:::

:::{.exercise title="?"}
Show that if $f$ is a differentiable contraction, $f$ is uniformly continuous.

#work

:::

:::{.theorem title="Implicit Function Theorem"}
Suppose $f\in C^1(\RR^n, \RR^n)$, $f'(a)$ is an invertible linear map, and $b\da f(a)$.
Then there exist neighborhoods $U\ni a, V\ni f(a)$ such that $f:U\to V$ is a bijection with an inverse $g:V\to U$ satisfying $g(f(x)) = x$ for all $x\in U$.
Moreover, $g \in C^1(V)$.
:::

:::{.slogan}
A $C^1$ function is invertible in any neighborhood in which its derivative $f'$ is invertible.

:::

:::{.theorem title="Inverse Function Theorem"}
For $f \in C^1(\RR; \RR)$ with $f'(a) \neq 0$, then $f$ is invertible in a neighborhood $U \ni a$, $g\da f\inv \in C^1(U; \RR)$, and at $b\da f(a)$ the derivative of $g$ is given by
\[
g'(b) = {1 \over f'(a)}
.\]
For $F \in C^1(\RR^n, \RR^n)$ with $D_f$ invertible in a neighborhood of $a$, so $\det(J_f)\neq 0$, then setting $b\da F(a)$,
\[
J_{F\inv}(q) = \qty{J_F(p)}\inv
.\]

The version for holomorphic functions: if $f\in \Hol(\CC; \CC)$ with $f'(p)\neq 0$ then there is a neighborhood $V\ni p$ with that $f\in \BiHol(V, f(V))$.

:::

:::{.theorem title="Green's Theorem"}
If $\Omega \subseteq \CC$ is bounded with $\bd \Omega$ piecewise smooth and $f, g\in C^1(\bar \Omega)$, then 
$$\int_{\bd \Omega} f\, dx + g\, dy = \iint_{\Omega} \qty{ \dd{g}{x} - \dd{f}{y} } \, \dA.$$
In vector form,
\[
\int_\gamma F\cdot \dr = \iint_R \curl F \dA
.\]
:::

## Function Convergence

:::{.definition title="Locally uniform convergence"}
A sequence of functions $f_n$ is said to converge **locally uniformly** on $\Omega \subseteq \CC$ iff $f_n\to f$ uniformly on every compact subset $K \subseteq \Omega$.
:::

:::{.theorem title="Uniform limit theorem"}
A continuous function on a compact set is uniformly continuous.

#work

:::

:::{.remark}
Recall that absolutely convergent implies convergent, but not conversely: $\sum k\inv = \infty$ but $\sum (-1)^k k\inv < \infty$.
This converges because the even (odd) partial sums are monotone increasing/decreasing respectively and in $(0, 1)$, so they converge to a finite number.
Their difference converges to 0, and their common limit is the limit of the sum.
:::

:::{.proposition title="Uniform Convergence of Series"}
A series of functions $\sum_{n=1}^\infty f_n(x)$ converges uniformly iff 
\[  
\lim_{n\to \infty} \norm{ \sum_{k\geq n} f_k }_\infty = 0
.\]
:::

:::{.theorem title="Weierstrass $M\dash$Test"}
If $\theset{f_n}$ with $f_n: \Omega \to \CC$ and there exists a sequence $\theset{M_n}$ with $\norm{f_n}_\infty \leq M_n$ and $\sum_{n\in \NN} M_n < \infty$, then $f(x) \definedas \sum_{n\in \NN} f_n(x)$ converges absolutely and uniformly on $\Omega$. 
Moreover, if the $f_n$ are continuous, by the uniform limit theorem, $f$ is again continuous.
:::

## Integrals

:::{.remark}
Some basic facts needed for line integrals in the plane:

- $\grad f = \tv{ \dd{f}{x}, \dd{f}{y} }$.
  - If $F = \grad f$ for some $f$, $F$ is a vector field.
- Given $f(x, y)$ and $\gamma(t)$, the chain rule yields $\dd{}{t} (f\circ \gamma)(t) = \inner{ \grad f\circ \gamma)(t)} {\gamma'(t)}$.
- For $F(x, y) = \tv{M(x, y), N(x, y)}$, $\curl F = \dd{N}{x} - \dd{M}{y}$ and $\div F = \dd{M}{x} + \dd{N}{y}$.
- $\int_\gamma F\cdot \dr = \int_a^b F(\gamma(t))\cdot \gamma'(t) \dt$.

:::

## Series and Sequences

:::{.remark}
Note that if a power series converges uniformly, then summing commutes with integrating or differentiating.
:::

:::{.proposition title="Ratio Test"}
Consider $\sum c_k z^k$, set $R = \lim \abs{c_{k+1} \over c_k}$, and recall the **ratio test**:

- $R\in (0, 1) \implies$ convergence.
- $R\in (1, \infty] \implies$ divergence.
- $R=1$ yields no information.
:::

:::{.proposition title="Root Test"}
![figures/image_2021-05-27-15-40-58.png](figures/image_2021-05-27-15-40-58.png)
:::

:::{.proposition title="Radius of Convergence by the Root Test"}
For $f(z) = \sum_{k\in \NN} c_k z^k$, defining
\[
{1\over R} \da \limsup_{k} \abs{a_k}^{1\over k}
,\]
then $f$ converges absolutely and uniformly for $D_R \da\abs{z} < R$ and diverges for $\abs{z} > R$.
So the radius of convergence is given by
\[
R = {1\over \limsup_n \abs{a_n}^{1\over n}}
.\]

Moreover $f$ is holomorphic in $D_R$, can be differentiated term-by-term, and $f' = \sum_{k\in \NN} n c_k z^k$.
:::

:::{.fact}
Recall the **$p\dash$test**:
\[
\sum n^{-p} < \infty \iff p \in (1, \infty)
.\]
:::

:::{.fact}
Recall how to carry out polynomial long division:

\todo[inline]{Polynomial long division}

:::

:::{.fact title="Partial Fraction Decomposition"}
\envlist

- For every root $r_i$ of multiplicity 1, include a term $A/(x-r_i)$.
- For any factors $g(x)$ of multiplicity $k$, include terms $A_1/g(x), A_2/g(x)^2, \cdots, A_k / g(x)^k$.
- For irreducible quadratic factors $h_i(x)$, include terms of the form ${Ax+B \over h_i(x)}$.
:::

## Exercises


:::{.exercise title="?"}
Show that a uniform limit of continuous functions is continuous, and a uniform limit of uniformly continuous functions is uniformly continuous.
Show that this is not true if uniform convergence is weakened to pointwise convergence.

#completed

:::

:::{.solution}
Suppose $\norm{f_n - f}_\infty\to 0$, fix $\eps$, we then need to produce a $\delta$ so that
\[
\abs{z-w}\leq \delta \implies \abs{f(z) - f(w) } < \eps
.\]

Write
\[
\abs{f(z) - f(w)} \leq \abs{f(z) - f_n(z)} + \abs{f_n(z) - f_n(w)} + \abs{f_n(w) - f(w)}
.\]

- Bound the first term by $\eps/3$ using that $f_n\to f$
- Bound the second term by $\eps/3$ using that $f_n$ is continuous 
- Bound the third term by $\eps/3$ using that $f_n\to f$
- Pick $\delta$ to be the minimum $\delta$ supplied by these three bounds.

Why uniform convergence is necessary: need these bounds to holds for all $z, w$ where $\abs{z-w} < \delta$.
Why pointwise convergence doesn't work: $f_n(z) \da z^n \convergesto{n\to\infty}\chi_{z=1}$

For uniform continuity: take $\sup_{z, w}$ on both sides:
\[
\sup_{z, w} \abs{f(z) - f(w)} 
&\leq \sup_{z} \abs{f(z) - f_n(z)} + \sup_{z, w} \abs{f_n(z) - f_n(w)} + \sup_{w} \abs{f_n(w) - f(w)} \\
&\leq \norm{f - f_n}_\infty + \sup_{z, w} \abs{f_n(z) - f_n(w)} + \norm{f-f_n}_\infty 
,\]
where now the middle term is bounded by uniform continuity of $f_n$.

:::

:::{.exercise title="?"}
Determine where the following real-valued function is or is not uniformly convergent:
\[
f_n(x) \da {\sin(nx)\over 1+nx}
.\]

#completed
:::

:::{.solution}
This converges uniformly on $[a, \infty)$ for $a$ any constant:
\[
\abs{\sin(nx) \over 1+nx} \leq {1\over 1 + na} < \eps = \eps(n, a)
.\]

This does not converge uniformly on $(0, \infty)$: 
\[
x_n \da {1\over n} \implies \abs{f_n(x_n)} = \abs{\sin(1) \over 2} > \eps
.\]
:::

:::{.exercise title="?"}
Show that $\sum_{k\geq 0}z^k/k!$ converges locally uniformly to $e^z$.

#completed

:::

:::{.solution}
Apply the $M\dash$test on a compact set $K$ with $z\in K \implies \abs{z} \leq M$:
\[
\norm{e^z - \sum_{0\leq k \leq n} z^k/k!}_\infty 
&= \norm{\sum_{k\geq n+1}z^k/k! }_{\infty} \\
&\leq \sum_{k\geq n+1} \norm{z}_\infty^k /k! \\
&\leq \sum_{k\geq 0} \norm{z}_\infty^k /k! \\
&= e^{\norm{z}_\infty} \\
&\leq e^{\abs{M}} \\
&< \infty
.\]


:::

:::{.exercise title="?"}
Show that if $f_n\to f$ uniformly then $\int_\gamma f_n\to \int_\gamma f$.

#completed

:::

:::{.solution}
\[
\abs{
\int_\gamma f_n(z) \dz - \int_\gamma f(z) \dz
}
&=
\abs{\int_\gamma f_n(z) - f(z) \dz}  \\
&\leq \int_\gamma \abs{f_n - f} \abs{\dz} \\
&\leq \int_\gamma \norm{f_n - f}_{\infty, \gamma} \cdot \abs{\dz} \\
&= \eps \cdot \length(\gamma) \\
&\convergesto{n\to\infty} 0
.\]

:::



