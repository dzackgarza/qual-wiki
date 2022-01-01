---
order: 5
title: "Montel and Function Convergence"
---

# Montel

## Tie's Extra Questions: Spring 2015 #complex/qual/work

:::{.problem title="?"}
Assume $f_n \in H(\Omega)$ is a sequence of holomorphic functions on the region $\Omega$ that are uniformly bounded on compact subsets and $f \in H(\Omega)$ is such that the set
$\displaystyle \{z \in \Omega: \lim_{n \rightarrow \infty} f_n(z) = f(z) \}$
has a limit point in $\Omega$. Show that $f_n$ converges to $f$ uniformly on compact subsets of $\Omega$.
:::

## Spring 2019.7 #complex/qual/completed

^d94130

:::{.problem title="?"}
Let $\Omega \subset \CC$ be a connected open subset. Let $\left\{f_{n}: \Omega \rightarrow \CC\right\}_{n=1}^{\infty}$ be a sequence of holomorphic functions uniformly bounded on compact subsets of $\Omega$. Let $f: \Omega \rightarrow \CC$ be a holomorphic function such that the set 
\[
\left\{z \in \Omega \mid \lim _{n \rightarrow \infty} f_{n}(z)=f(z)\right\}
\]
has a limit point in $\Omega$. Show that $f_{n}$ converges to $f$ uniformly on compact subsets of $\Omega$.

:::

:::{.solution}
Write $g(z) \da \lim_{n\to\infty}f_n(z)$ for the pointwise limit, then $g(z) = f(z)$ on a set with a limit point.
By the identity principle, $g\equiv f$ on $\Omega$, making $f$ the pointwise limit of the $f_n$.

By Montel, locally uniformly bounded implies normal and locally equicontinuous.
So $\ts{f_n}$ is normal, and thus has a locally uniformly convergent subsequence $\ts{f_{n_k}}$.
Since singletons $\ts{z}$ are compact, $f_{n_k}(z) \to g(z)$ pointwise, and by uniqueness of limits, $\lim_{k\to\infty } f_{n_k} = g = f$ on any compact $K \subseteq \Omega$.

It remains to show that the original sequence $\ts{f_n}$ converges locally uniformly to $f$, not just the subsequence.
Suppose not, then there exists a compact $K \subseteq \Omega$ and $\eps>0$ so that $\norm{f_n - f}_{K, \infty} > \eps$ for infinitely many $n$.
This produces a subsequence $\ts{f_{n_j}}$ with $\norm{f_{n_j} - f} > \eps$ for all $j$.
However, since $\mcf$ was normal, *every* subsequence has a locally uniformly convergent subsequence, so this has a further subsequence $f_{n_{j'}}$ uniformly converging to $f$, a contradiction.


:::

# Function Convergence

## Fall 2021.4 #complex/qual/completed

^b0c999

:::{.problem title="?"}
Prove that the sequence $\left(1+\frac{z}{n}\right)^{n}$ converges uniformly to $e^{z}$ on compact subsets of $\mathbb{C}$. 

> Hint: $e^{n \log w_{n}}=w_{n}^{n}$ and $e^{z}$ is uniform continuous on compact subsets of $\mathbb{C}$.

:::

:::{.solution}

Let $K$ be compact, where $z\in K\implies \abs{z} \leq R$ for some constant $R$. For the remainder of the problem, we only work in $K$.

:::{.claim}
$f_n(z) \da n\log(1 + {z\over n}) \to z$ uniformly.
:::

:::{.claim}
$f_n$ are uniformly bounded on $K$.
:::


:::{.claim}
$e^z$ is uniformly continuous on $K$.
:::


:::{.claim}
If $g_n\to g$ uniformly and $F$ is uniformly continuous, then $F \circ g_n \to F\circ g$ uniformly.
:::


Why these claims imply the result:

If $f_n(z)\to z$ uniformly, both are uniformly bounded, and $e^z$ is uniformly continuous, then $e^{f(z)}\to e^z$ uniformly.


:::{.proof title="Of first claim"}
We'll first show that for $w$ in a neighborhood of zero avoiding 1, there exists a constant $C$ such that
\[
\abs{ 1 - {\log(1+w) \over w} } \leq C\abs{w}
.\]
This follows from estimating the series expansion about $w=0$:
\[
\abs{ 1 - {\log(1+w) \over w} }
&= \abs{w\inv\sum_{k\geq 1} { (-w)^k \over k} } \\
&= \abs{\sum_{k\geq 2} {(-w)^{k-1} \over k} } \\
&\leq {\sum_{k\geq 2} {\abs{w}^{k-1} \over k} } \\
&= {\sum_{k\geq 1} {\abs{w}^{k} \over k+1} } \\
&\leq {\sum_{k\geq 1} {\abs{w}^{k} \over 2} } \\
&= {1\over 2}\qty{{1\over 1 - \abs w} - 1 } \\
&= {1\over 2}\abs{2} \qty{1\over 1 - \abs w} \\
&\leq C \abs{w}
,\]
using that ${1\over 1-x}$ is bounded in compact sets avoiding $x=1$.

We can now apply the $M\dash$test:
\[
\abs{n\log\qty{ 1 + {z\over n} } - z } 
&= \abs{z}\cdot \abs{
{{ \log\qty{1 + {z\over n}} \over {z\over n}} - 1}
} \\
&\leq \abs{z} \cdot C\abs{z\over n} \\
&\leq M\cdot C\qty{M\over n} \\
&= {CM^2 \over n}\\
&\convergesto{n\to\infty}0
.\]


:::


:::

## Spring 2021.6, Spring 2015, Extras #complex/qual/completed

^c94b57

:::{.problem title="?"}
Let $\ts{f_n}_{n=1}^\infty$ is a sequence of holomorphic functions on $\DD$ and $f$ is also holomorphic on $\DD$. 
Show that the following are equivalent:

- $f_n\to f$ uniformly on compact subsets of $\DD$.
- For $0 < r < 1$,
\[
\int_{\abs z = r} \abs{f_n(z) - f(z)} \abs{dz} \convergesto{n\to\infty}0
.\]

> Note: $\abs{\dz} = \abs{\gamma'(t)}\dt$ for $\gamma$ a parameterization of the curve.

:::

:::{.solution}
$\implies$: 

- Fix $r \in (0, 1)$ and let $\gamma = \ts{\abs{z} = r}$.
  This is compact, so $f_n\to f$ uniformly on $\gamma$:
\[
\int_\gamma \abs{f_n(z) - f(z) } \dz 
&\leq\int_\gamma \sup_{w\in \gamma } \abs{f_n(w) - f(w) } \dz \\
&\leq\int_\gamma \norm{f_n(w) - f(w) }_{\infty} \dz \\
&= \norm{f_n(w) - f(w) }_{\infty} \int_\gamma \dz \\
&= \norm{f_n(w) - f(w) }_{\infty} \length(\gamma) \\
&\convergesto{n\to\infty} 0
.\]

$\impliedby$:

- Let $K$ be compact, then choose $\gamma$ enclosing but not intersecting $K$.
- Since $\gamma, K$ are disjoint compact sets, define $M \da \inf \ts{\abs{z-\xi} \st z\in K, \xi\in \gamma}$, the $0<M<\infty$.

- Apply Cauchy's formula to the function $F_n(z) \da f_n(z) - f(z)$, where we want to show $\abs{F_n(z)} < \eps$:
\[
F_n(z) 
&= {1\over 2\pi i} \int_\gamma { F_n(\xi) \over z-\xi} \dxi \\
\implies \abs{f_n(z) - f(z) } 
&\leq {1\over 2\pi }\int_\gamma \abs{f_n(\xi) - f(\xi) \over z-\xi} \dxi \\
&\leq {1\over 2\pi} \int_\gamma {\abs{ f_n(\xi) - f(\xi) } \over 
M} \dxi \\
&\leq {1\over 2\pi M} \int_\gamma {\abs{ f_n(\xi) - f(\xi) } } \abs{\dxi} \\
,\]
where by hypothesis we can bound this integral by an $\eps$.
So given $\eps$, choose $n$ large enough to bound the integral as above by some $\eps$ depending only on $n$ and not on $z$.
Taking $\sup$ of both sides yields $\norm{f_n - f}_{\infty, K} \leq {\eps\over 2\pi M}$, so $f_n\to f$ uniformly on $K$.
:::

## Spring 2020 HW 2, SS 2.6.10 #complex/qual/completed

:::{.problem title="?"}
Can every continuous function on $\bar \DD$ be uniformly approximated by polynomials in the variable $z$?

> Hint: compare to Weierstrass for the real interval.


:::

:::{.solution}
No: polynomials are holomorphic and the uniform limit of holomorphic functions is holomorphic.
However, $f(z) \da \bar{z}$ is continuous on $\bar\DD$ but not holomorphic, so can not be uniformly approximated by any sequence of polynomials.
:::

## Spring 2020 HW 2.5 #complex/qual/completed

:::{.problem title="?"}
Assume $f$ is continuous in the region $\theset{x+iy \suchthat x\geq x_0, ~ 0\leq y \leq b}$, and the following limit exists independent of $y$:
\[
\lim_{x\to +\infty}f(x+iy) = A
.\]

Show that if $\gamma_x \definedas \theset{z = x+it \suchthat 0 \leq t \leq b}$, then
\[
\lim_{x\to +\infty} \int_{\gamma_x} f(z) \,dz = iAb
.\]
:::

:::{.solution}
The key insight:
\[
\int_\gamma A \dz 
&= \int_0^b A \cdot i \dt && z=x+it,\, \dz = i\dt \\
&=iA \int_0^b \dt \\
&= iAb
.\]

So now estimate the difference:
\[
\abs{
\int_{\gamma} f(z) \dz - iAb
}
&= \abs{ \int_\gamma f(z) \dz - \int_\gamma A \dz} \\
&= \abs{ \int_\gamma \qty{ f(z) - A } \dz} \\
&\leq\int_\gamma \abs{ f(z) - A } \dz \\
&\leq \sup_{z = x+iy\in \gamma} \abs{f(x+iy) - A} \cdot \length(\gamma_x) \\
&\convergesto{x\to \infty}0
,\]
using that $\length(\gamma_x) = b$ is constant.
:::

## Limiting curve variant #complex/qual/completed

:::{.problem title="?"}
Let $0\leq \alpha \leq 2\pi$ be a fixed angle.
Suppose $f$ is continuous on the region $\Omega = \ts{\abs{z} \geq R, \Arg(z) \in [0, \alpha]}$ and $\lim_{z\to \infty} zf(z) = A$.
Show that
\[
\lim_{z\to \infty} \int_{\gamma_R} f(z) \dz = iA\alpha
,\]
where $\gamma_R \da \ts{ \abs{z} = R, \Arg(z) \in [0, \alpha]}$ is an arc.
:::

:::{.solution}
Key observation:
\[
iA\alpha = \int_\gamma {A\over z}\dz
.\]
Why this is true:
\[
\int_\gamma {A\over z}\dz = \int_0^\alpha {1\over Re^{it}} iRe^{it}dt
= \int_0^\alpha iA \dt = iA\alpha
.\]

Now estimate the difference:

\[
\abs{ \int_\gamma f(z) \dz - iA\alpha }
&= \abs{ \int_\gamma f(z) \dz - \int_\gamma {A\over z} \dz}\\
&= \abs{\int_\gamma f(z) - {A\over z} \dz} \\
&= \abs{\int_\gamma{zf(z) - A \over z} \dz} \\
&\leq \int_\gamma \abs{zf(z) - A \over z} \dz \\
&= \int_\gamma { \abs{zf(z) - A} \over R} \dz \\
&\leq {1\over R } \int_\gamma \norm{zf(z) - A}_{\infty, \gamma} \dz \\
&= {\eps\over R}\cdot \length(\gamma) \\
&= {\eps \over R} \cdot R\alpha \\
&= \eps \alpha \\
&\convergesto{R\to\infty}0
.\]



:::

