---
order: 50
---

# Commuting Limiting Operations


:::{.example title="Limits of doubly indexed sequences need not commute"}
\[
\lim_{m\to \infty}\lim_{n\to\infty} a_{mn}
\neq \lim_{n\to \infty}\lim_{m\to\infty} a_{mn}
.\]

For example, 
\[
\lim_{m\to \infty}\lim_{n\to\infty} {n \over n + m} &= 1 \neq 0 =
\lim_{n\to \infty}\lim_{m\to\infty} {n \over n + m}
.\]
:::

:::{.example title="Limits of bounded functions need not be bounded"}
\[  
\lim_{n\to \infty}\sup_{x\in X} \abs{f_n(x) } \neq \sup_{x\in X} \abs{\lim_{n\to\infty} f_n(x) }
.\]
:::

:::{.example title="Limits of continuous functions need not be continuous"}
\[  
\lim_{k\to \infty} \lim_{n\to\infty} f_n(x_k) \neq
\lim_{n\to \infty} \lim_{k\to\infty} f_n(x_k)
.\]
For example, take $f_n(x) \da x^n$, then for $\ts{x_k}\to 1$,
\[
\lim_{k\to\infty}\lim_{n\to\infty} (x_k)^n 
&= \lim_{k\to \infty } \chi_{x=1}(x_k) 
= 0 \\
\lim_{n\to\infty } \lim_{k\to\infty } (x_k)^n
&= \lim_{n\to\infty} (1)^n 
= 1
.\]

:::

:::{.example title="Limits of differentiable functions need not be differentiable"}
\[  
\lim_{n\to \infty} \dd{}{x} f_n \neq \dd{}{n} \qty{\lim_{n\to \infty} f_n}
.\]
For example,
\[
f_n(x) \da \sqrt{x^2 + {1\over n}} \converges{n\to\infty}\too f(x) \da \abs{x}
,\]
and this convergence is even uniform.

Another example:
\[
f_n(x) \da {x\over 1 + nx^2}
.\]
Then by Calculus, $f_n(x) \leq 1/2\sqrt{n} \da M_n$ and $f_n\to 0$ uniformly, so $f' = 0$.
But 
\[
f_n'(x) = {1-nx^2 \over\qty{1 + nx^2}^2}
,\]
and $f_n'(0) \to 1$.
:::

:::{.remark}
Note that uniform convergence of $f_n$ and $f_n'$ is sufficient to guarantee that $f$ is differentiable.
Even worse: every continuous function is a uniform limit of polynomials by the Weierstrass approximation theorem.
:::


:::{.example title="?"}
\[  
\lim_{n\to \infty} \int_a^b f_n(x) \,dx \neq \int_a^b \lim_{n\to \infty} \qty{ f_n(x) } \,dx
.\]
:::

- Differentiability $\implies$ continuity but not the converse: $f(x) = \abs{x}$.

  - The Weierstrass function is continuous but nowhere differentiable.

- $f$ continuous does not imply $f'$ is continuous: $f(x) = x^2 \sin(x)$.

- Limit of derivatives may not equal derivative of limit:
  $$
  f(x) = \frac{\sin(nx)}{n^c} \text{ where } 0 < c < 1.
  $$
  
  - Also shows that a sum of differentiable functions may not be differentiable.

- Limit of integrals may not equal integral of limit:
$$
\sum \indic{x = q_n \in \QQ}
.$$

- A sequence of continuous functions converging to a discontinuous function:
$$
f(x) = x^n \text{ on } [0, 1]
.$$


