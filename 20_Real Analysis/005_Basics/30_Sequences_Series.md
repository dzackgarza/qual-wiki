---
order: 35
---

# Sequences and Series

## Sequences of functions

:::{.definition title="limsup of functions"}
For $f:A\to \RR$,
\[
\limsup_{x\to y} f(x) \da \lim_{\eps\to 0} \sup f\qty{A \intersect B_\eps(y) \smts{y}}
.\]

:::

## Sequences of number

:::{.slogan}
$\limsup$ is largest limit of a convergent subsequence, $\liminf$ is the smallest.
:::

:::{.proposition title="The Cauchy condensation test"}
For $\ts{a_k}$ is a non-increasing sequence in $\RR$ then
\[
\sum_{k\geq 1} a_k < \infty \iff \sum_{k\geq 1} 2^k a_{2^k}<\infty
.\]
:::

:::{.proof title="showing a useful trick"}
Show that
\[
\sum a_k \leq \sum 2^k a_{2^k} \leq 2 \sum a_k
\]
using 
\[
\sum a_k = a_0 + a_1 + a_2 + a_3 + \cdots
\leq \qty{a_1} + \qty{a_2 + a_2} + \qty {a_3 + a_3 + a_3 + a_3} + \cdots \\
\]
where each group with $a_k$ has $2^k$ terms.

:::

## Series

:::{.proposition title="Comparison Test"}
If $0\leq a_n \leq b_n$, then 

- $\sum b_n < \infty \implies \sum a_n < \infty$, and 
- $\sum a_n = \infty \implies \sum b_n = \infty$.

:::

:::{.proposition title="Sufficient condition for Taylor convergence"}
Given a point $c$ and some $\varepsilon>0$, if $f \in C^\infty(I)$ and there exists an $M$ such that 
$$
x \in N_\varepsilon(c) \implies \abs{f^{(n)}(x)} \leq M^n
$$
then the Taylor expansion about $c$ converges on $N_\varepsilon(c)$.
:::

:::{.proposition title="p-tests"}
Let $n$ be a fixed dimension and set $B = \theset{x\in \RR^n \suchthat \norm{x} \leq 1}$. 
\[
\sum \frac 1 {n^p} < \infty &\iff p>1 \\
\int_\varepsilon^\infty \frac 1 {x^p} < \infty 
&\iff p>1 \\
\int_0^1 \frac 1 {x^p} < \infty 
&\iff p<1 \\
\int_B \frac{1}{\abs{x}^p} < \infty &\iff p < n \\
\int_{B^c} \frac{1}{\abs{x}^p} < \infty &\iff p > n \\
.\]
:::

:::{.proposition title="Small Tails for Series of Functions"}
\[
\sum f_n < \infty \implies \norm{f_n}_\infty \convergesto{n\to\infty}0
.\]

:::

:::{.corollary title="Term by Term Continuity Theorem"}
\[
f_n \text{ cts},\, \norm{\sum_{k\leq N} f_n \to F}_\infty \convergesto{N\to\infty} 0 \implies F \text{ cts}
.\]
:::

:::{.proposition title="Cauchy criterion for sums"}
Uniformly Cauchy iff uniformly convergent, i.e.
\[
\norm{f_n - f_m} \convergesto{m, n\to \infty} 0 \iff \exists f,\, \norm{f_n - f} \convergesto{n\to\infty} 0
.\]

:::

:::{.theorem title="Lagrange and Cauchy Remainders"}
If $f$ is $n$ times differentiable on a neighborhood of a point $p$, say $N_\delta(p)$, then for all points $x$ in the deleted neighborhood $N_\delta(p) - \theset{p}$ , there exists a point $\xi$ strictly between $x$ and $p$ such that
\[
x \in N_\delta(p)-\theset{p} \implies f(x) 
&= \sum_{k=0}^{n-1} \frac{f^{(k)}(p)}{k!}(x-p)^k + \frac{f^{(n)}(\xi)}{n!}(x-p)^n \\ \\
&= \sum_{k=0}^{n-1} \frac{f^{(k)}(p)}{k!}(x-p)^k + \int_c^x \frac{1}{n!} \dd{^n f}{x^n}(t) (x-t)^n ~dt
\]
:::

## Uniform Convergence

:::{.proposition title="Testing Uniform Convergence: The Sup Norm Test"}
$f_n \to f$ uniformly iff there exists an $M_n$ such that $\norm{f_n - f}_\infty \leq M_n \to 0$.
:::

:::{.remark title="Negating the Sup Norm test"}
**Negating**: find an $x$ which depends on $n$ for which $\norm{f_n}_\infty > \eps$ (negating small tails) or $\norm{f_n - f_m} > \eps$ (negating the Cauchy criterion).
:::

:::{.proposition title="$C(I)$ is complete"}
The space $X = C([0, 1])$, continuous functions $f: [0, 1] \to \RR$, equipped with the norm 
\[
\norm{f}_\infty \da \sup_{x\in [0, 1]} \abs{f(x)}
\]
is a **complete** metric space.
:::

:::{.proof}
\envlist

1.  Let $\theset{f_k}$ be Cauchy in $X$.

2.  Define a candidate limit using pointwise convergence:

    Fix an $x$; since
  \[
  \abs{f_k(x) - f_j(x)}  \leq \norm{f_k - f_k} \to 0
  \] 
    the sequence $\theset{f_k(x)}$ is Cauchy in $\RR$.
    So define $f(x) \definedas \lim_k f_k(x)$.


3.  Show that $\norm{f_k - f} \to 0$:
  \[
  \abs{f_k(x) - f_j(x)} < \varepsilon ~\forall x \implies \lim_{j} \abs{f_k(x) - f_j(x)} <\varepsilon ~\forall x
  \]
    Alternatively, $\norm{f_k-f} \leq \norm{f_k - f_N} + \norm{f_N - f_j}$, where $N, j$ can be chosen large enough to bound each term by $\varepsilon/2$.

4.  Show that $f\in X$:

    The uniform limit of continuous functions is continuous.

:::

:::{.remark}
In other cases, you may need to show the limit is bounded, or has bounded derivative, or whatever other conditions define $X$.
:::

:::{.theorem title="Weierstrass Approximation"}
If $[a, b] \subset \RR$ is a closed interval and $f$ is continuous, then for every $\eps> 0$ there exists a polynomial $p_\eps$ such that $\norm{f- p_\eps}_{L^\infty([a, b])} \converges{\eps \to 0}\to 0$.

Equivalently, polynomials are dense in the Banach space $C([0, 1], \norm{\wait}_\infty)$.
:::

