---
order: 90
---

# Counterexamples

Let all of the following integrals to be over a compact interval $[a, b]$ with $0 \leq a < b$.

Questions to ask:

- Is $f$ bounded?
- What is the discontinuity set $D_f$? 
- What is the non-differentiability locus $D'_f$?
- Is $f$ Riemann integrable?
- If $f$ Lebesgue integrable? 
  If so, what is $\int_\RR f$?

## Thomae function
\[
f ( x ) = \begin{cases}
\frac 1 q, & x = \frac p q \in \QQ,~(p,q) = 1 \\
0, & \text{else}
\end{cases}
\]

- Bounded 
- $D_f = \QQ$
- $D'_f = \RR$
- Riemann integrable with $\int_a^b f = 0$ by the Lebesgue criterion


## Weierstrass Function



Note that this series converges uniformly since it's bounded above by $\sum \abs{a^n}$, which is geometric.

- Bounded: ?
- $D_f = \emptyset$
- $D'_f = \RR$
- Riemann integrable: ?
- Lebesgue integrable: ?



| Function                                                                   | Bounded?             | $D_f$       | $D'_f$    | $\mathcal{R}$?              | $\mathcal{L}$? |
| -------------------------------------------------------------------------- | -------------------- | ----------- | --------- | --------------------------- | -------------- |
| Dirichlet $\chi_\QQ(x)$                                                    | ✅, $\abs{f} \leq 1$ | $\RR$       | $\RR$     | ❌                          | ✅, $\int f=0$ |
| Dirichlet 2 $x\chi_\QQ(x)$                                                 | ❌                   | $\RR\smz$   | $\RR$     | ❌, $U(f) > 1/4 > 0 = L(f)$ | ?              |
| Dirichlet 3 $x^2\chi_\QQ(x)$                                               | ❌                   | $\RR\smz$   | $\RR\smz$ | ❌                          | ?              |
| Dirichlet 4 $f(x) = x\qty{ \chi_\QQ(x) - \chi_{\QQ^c}(x)}$                 | ❌                   | $\RR\smz$   | $\RR$     | ❌                          | ?              |
| Thomae $(x={p\over q} \mapsto {1\over q})\chi_{\QQ}(x)$                    | ✅                   | $\QQ$       | $\RR$     | ✅, $\int f = 0$[^1]        | ✅             |
| Weierstrass $f(x)=\sum_{n=0}^{\infty} a^{n} \cos \left(b^{n} \pi x\right)$ |                      | $\emptyset$ | $\RR$     | ?                           | ?              |
|                                                                            |                      |             |           |                             |                |

Full definition of the 


[^1]: Riemann integrable by the Lebesgue criterion.

:::{.proof title="of non-integrability of Dirichlet 4"}
Restrict attention to $\tv{\frac 1 2, 1}$
\[
\overline{\int_0^1} f 
&= \inf \theset{ \sum \sup f(x) (x_i - x_{i-1}) } \\
\sup f(x) = x_i \implies 
\sum \sup f(x) (x_i - x_{i-1}) &= \sum x_i (x_i - x_{i-1}) \\
&> \sum \frac 1 2 (x_i - x_{i-1}) \\
&= \frac 1 2 \left(\frac 1 2\right) = \frac 1 4 \\
\implies \overline{\int_0^1} f &\geq \frac 1 4
\]
and 
\[
\underline{\int_0^1} f 
&= \sup \theset{ \sum \inf f(x) (x_i - x_{i-1})} \\
\inf f(x)= -x_i \implies 
\sum \inf f(x) (x_i - x_{i-1}) 
&= \sum -x_i (x_i - x_{i-1}) \\
&< -\sum \frac 1 2 (x_i - x_{i-1}) \\
&= -\frac 1 2 \left( \frac 1 2 \right) = -\frac 1 4 \\
\implies \underline{\int_0^1} f &\leq -\frac 1 4
\]
So we have $\underline{\int_0^1} f \lneq 0 \lneq \overline{\int_0^1} f$.
:::
