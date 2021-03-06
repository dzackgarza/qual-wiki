---
order: 50
---

# Liouville's Theorem

## Spring 2020.3, Extras Fall 2009 #complex/qual/completed

^c6e205

:::{.problem title="?"}
\envlist

- Assume $f(z)=\sum_{n=0}^{\infty} c_{n} z^{n}$ converges in $|z|<R$. Show that for $r<R$,

$$
\frac{1}{2 \pi} \int_{0}^{2 \pi}\left|f\left(r e^{i \theta}\right)\right|^{2} d \theta=\sum_{n=0}^{\infty}\left|c_{n}\right|^{2} r^{2 n}
$$

- Deduce Liouville's theorem from (a).

:::

:::{.solution}
Computing the LHS:
\[
\int_{[0, 2\pi]} \abs{f(re^{i\theta})}^2 \dtheta
&= \int_{[0, 2\pi]} f(re^{i\theta}) \bar{f(re^{i\theta}) } \dtheta \\
&= \int_{[0, 2\pi]} \sum_{k\geq 0} c_k r^k e^{ik\theta} \sum_{j\geq 0} \bar{c_j} r^j e^{-ij\theta} \dtheta \\
&= \int_{[0, 2\pi]} \sum_{k,j\geq 0} c_k\bar{c_j} r^{k+j} e^{i(k-j)\theta} \dtheta \\
&= \sum_{k,j\geq 0} c_k\bar{c_j} r^{k+j} \int_{[0, 2\pi]} e^{i(k-j)\theta} \dtheta \\
&= \sum_{k,j\geq 0} c_k\bar{c_j} r^{k+j} \chi_{i=j}\cdot 2\pi \\
&= \sum_{k\geq 0} c_k\bar{c_k} r^{2k} \cdot 2\pi \\
&= 2\pi \sum_{k\geq 0}\abs{c_k}^2 r^{2k}
,\]
where we've used that the series converges uniformly in its radius of convergence to commute sums and integrals.

Now supposing $\abs{f(z)}\leq M$ for all $z\in \CC$, if $f$ is entire then $\sum_{k\geq 0} c_k z^k$ converges for all $r$, so
\[
\sum_{k\geq 0} \abs{c_k}^2 r^{2k} = {1\over 2\pi }\int_{[0, 2\pi]} \abs{f(re^{i\theta})}^2 \dtheta \leq {1\over 2\pi}\int_{[0, 2\pi]} M^2 \dtheta = M^2
.\]
Thus for all $r$,
\[
\abs{c_0}^2 + \abs{c_1}^2 r^2 + \abs{c_2}^2 r^{4} + \cdots \leq M^2
,\]
and taking $r\to\infty$ forces $\abs{c_1}^2 = \abs{c_2}^2 = \cdots = 0$.
So $f(z) = c_0$ is constant.



:::

## FTA via Liouville #complex/exercise/completed

:::{.problem title="?"}
Prove the Fundamental Theorem of Algebra (using complex analysis).
:::

:::{.solution}
\envlist

- Strategy: By contradiction with Liouville's Theorem
- Suppose $p$ is non-constant and has no roots.
- Claim: $1/p(z)$ is a bounded holomorphic function on $\CC$.
  - Holomorphic: clear? Since $p$ has no roots.
  - Bounded: for $z\neq 0$, write
    \begin{align*}
    \frac{P(z)}{z^{n}}=a_{n}+\left(\frac{a_{n-1}}{z}+\cdots+\frac{a_{0}}{z^{n}}\right)
    .\end{align*}

  - The term in parentheses goes to 0 as $\abs{z}\to \infty$
  - Thus there exists an $R>0$ such that
    \begin{align*}
    \abs{z} > R \implies \abs{P(z) \over z^n} \geq c \definedas {\abs{a_n} \over 2}
    .\end{align*}

  - So $p$ is bounded below when $\abs{z} > R$
  - Since $p$ is continuous and has no roots in $\abs{z} \leq R$, it is bounded below when $\abs{z} \leq R$.
  - Thus $p$ is bounded below on $\CC$ and thus $1/p$ is bounded above on $\CC$.
- By Liouville's theorem, $1/p$ is constant and thus $p$ is constant, a contradiction.
:::

## Entire functions satisfying an inequality #complex/exercise/completed

:::{.problem title="?"}
Find all entire functions that satisfy
\[
\abs{f(z)} \geq \abs{z} \quad \forall z\in \CC
.\]
Prove this list is complete.

:::


:::{.concept}
\envlist
- If $f$ is bounded in a neighborhood of a singularity $z_0$, then $z_0$ is removable.

:::


:::{.solution}
\envlist

- Suppose $f$ is entire and define $g(z) \definedas {z \over f(z)}$.
- By the inequality, $\abs{g(z)} \leq 1$, so $g$ is bounded.
- $g$ potentially has singularities at the zeros $Z_f \definedas f\inv(0)$, but since $f$ is entire, $g$ is holomorphic on $\CC\setminus Z_f$.
- Claim: $Z_f = \theset{0}$.
  - If $f(z) = 0$, then $\abs{z} \leq \abs{f(z)} = 0$ which forces $z=0$.
- We can now apply Riemann's removable singularity theorem:
  - Check $g$ is bounded on some open subset $D\smz$, clear since it's bounded everywhere
  - Check $g$ is holomorphic on $D\smz$, clear since the only singularity of $g$ is $z=0$.
- By Riemann's removable singularity theorem, the singularity $z = 0$ is removable and $g$ has an extension to an entire function $\tilde g$.
- By continuity, we have $\abs{\tilde g(z)} \leq 1$ on all of $\CC$
  - If not, then $\abs{\tilde g(0)} = 1+\eps > 1$, but then there would be a domain $\Omega \subseteq \CC\smz$ such that $1 < \abs{\tilde g(z)} \leq 1 +\eps$ on $\Omega$, a contradiction.
- By Liouville, $\tilde g$ is constant, so $\tilde g(z) = c_0$ with $\abs {c_0} \leq 1$
- Thus $f(z) = c_0\inv z \definedas cz$ where $\abs{c}\geq 1$

Thus all such functions are of the form $f(z) = cz$ for some $c\in \CC$ with $\abs{c}\geq 1$.
:::


## Entire functions with an asymptotic bound #complex/exercise/completed

:::{.problem title="?"}
Find all entire functions satisfying
\[
\abs{f(z)} \leq \abs{z}^{1\over 2} \quad\text{ for } \abs{z} > 10
.\]
:::

:::{.solution}
Since $f$ is entire, take a Laurent expansion at $z=0$, so $f(z) = \sum_{k\geq 0} c_k z^k$ where ${2\pi i\over k!} c_k = f^{(k)}(0)$ by Cauchy's integral formula.
Take a Cauchy estimate on a disc of radius $R>10$:
\[
\abs{c_k} 
&\leq {k!\over 2\pi}\int_{\abs{z} = R} \abs{f(\xi) \over (\xi - 0)^{k+1}}\dxi\\
&\leq {k! \over 2\pi}\int_{\abs z = R}{ \abs{\xi}^{1\over 2} \over \abs{\xi}^{k+1} }\dxi \\
&= {k! \over 2\pi} \cdot {1\over R^{k+{1\over 2}}}\cdot 2\pi R \\
&= \bigo(1/R^{k-{1\over 2}})
.\]
So in particular, if $k\geq 1$ then $k-{1\over 2}>0$ and $c_k = 0$.
This forces $f = c_0$ to be constant.

:::



## Tie's Extra Questions: Fall 2009 #complex/exercise/completed

:::{.problem title="?"}
Let $f(z)$ be entire and assume values of $f(z)$ lie outside a *bounded* open set $\Omega$. Show without using Picard's theorems that $f(z)$ is a constant.
:::

:::{.solution}
We have $\abs{f(z)}\geq M$ for some $M$, so $\abs{1/f(z)} \leq M\inv$ is bounded, and we claim it is entire as well.
This follows from the fact that $1/f$ has singularities at the zeros of $f$, but these are removable since $1/f$ is bounded in every neighborhood of each such zero.
So $1/f$ extends to a holomorphic function.
But now $1/f =c$ is constant by Liouville, which forces $f= 1/c$ to be constant.
:::

## Tie's Extra Questions: Fall 2015 #complex/exercise/completed


:::{.problem title="?"}
Let $f(z)$ be bounded and analytic in $\mathbb C$. Let $a \neq b$ be any fixed complex numbers. Show that the following limit exists:
$$
\lim_{R \rightarrow \infty} \int_{|z|=R} \frac{f(z)}{(z-a)(z-b)} dz
.$$

Use this to show that $f(z)$ must be a constant (Liouville's theorem).
:::


:::{.solution}
Apply PFD and use that $f$ is holomorphic to apply Cauchy's formula over a curve of radius $R$ enclosing $a$ and $b$:
\[
\int_\gamma {f(z) \over (z-a)(z-b)}\dz
&= \int_\gamma f(z)\qty{{a-b \over z-a} + {b-a\over z-b} } \dz\\
&= (a-b)\inv \int_\gamma {f(z) \over z-a} \dz + (b-a)\inv \int_\gamma {f(z) \over z-b}\dz \\ 
&= (a-b)\inv \cdot 2\pi i f(a) + (b-a)\cdot 2\pi i f(b)\\
&= 2\pi i\qty{f(a) - f(b) \over a-b }
.\]
Since $f$ is bounded, this number is finite and independent of $R$, so taking $R\to\infty$ preserves this equality.
On the other hand, if $\abs{f(z)}\leq M$, then we can estimate this integral directly as 
\[
I \leq 
\int_{\abs z = R} {M \over \abs{R-a} \cdot \abs{R-b} } 
= {M\cdot 2\pi R \over \abs{R-a} \cdot \abs{R-b}} \asymptotic {1\over R} \to 0
,\]
which forces $f(a) =f(b)$.
Since $a, b$ were arbitrary, $f$ must be constant.
:::



