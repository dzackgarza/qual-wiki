---
order: 50
---

# Liouville's Theorem

## Spring 2020.3 #work

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
.\]

:::


## 3 #work

Suppose $D$ is a domain and $f, g$ are analytic on $D$.

Prove that if $fg = 0$ on $D$, then either $f \equiv 0$ or $g\equiv 0$ on $D$.


## 4 #work

Suppose $f$ is analytic on $\DD^\circ$.
Determine with proof which of the following are possible:

a. $f\qty{1\over n} = (-1)^n$ for each $n>1$.

b. $f\qty{1\over n} = e^{-n}$ for each even integer $n>1$ while $f\qty{1\over n} = 0$ for each odd integer $n>1$.

c. $f\qty{1\over n^2} = {1\over n}$ for each integer $n>1$.

d. $f\qty{1\over n} = {n-2 \over n-1}$ for each integer $n>1$.


## 5 #completed

Prove the Fundamental Theorem of Algebra (using complex analysis).

:::{.solution}
\hfill
:::{.concept}
\hfill

:::
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



## 6 #completed
Find all entire functions that satisfy
\[
\abs{f(z)} \geq \abs{z} \quad \forall z\in \CC
.\]
Prove this list is complete.

:::{.solution}
\hfill
:::{.concept}
\hfill

:::
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


## 9 #work

Find all entire functions satisfying
\[
\abs{f(z)} \leq \abs{z}^{1\over 2} \quad\text{ for } \abs{z} > 10
.\]


## Tie's Extra Questions: Fall 2009 #work

1. 
Assume $\displaystyle f(z) = \sum_{n=0}^\infty c_n z^n$ converges in $|z| < R$. 

Show that for $r <R$,
$$
\frac{1}{2 \pi} \int_0^{2 \pi} |f(r e^{i \theta})|^2 d \theta = \sum_{n=0}^\infty |c_n|^2 r^{2n}
.$$

2.
Deduce Liouville's theorem from (1).


## Tie's Extra Questions: Fall 2009 #work

Let $f(z)$ be entire and assume values of $f(z)$ lie outside a *bounded* open set $\Omega$. Show without using Picard's theorems that $f(z)$ is a constant.


## Tie's Extra Questions: Fall 2015

Let $f(z)$ be bounded and analytic in $\mathbb C$. Let $a \neq b$ be any fixed complex numbers. Show that the following limit exists:
$$
\lim_{R \rightarrow \infty} \int_{|z|=R} \frac{f(z)}{(z-a)(z-b)} dz
.$$

Use this to show that $f(z)$ must be a constant (Liouville's theorem).
