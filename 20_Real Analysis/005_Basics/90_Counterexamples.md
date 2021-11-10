---
order: 90
---

# Counterexamples

:::{.example title="?"}
A series of continuous functions that does *not* converge uniformly but is still continuous:
\[  
g(x) \da \sum {1 \over 1 + n^2 x}
.\]

Take $x = 1/n^2$.
:::

Let all of the following integrals to be over a compact interval $[a, b]$ with $0 \leq a < b$.

Questions to ask:

- Is $f$ bounded?
- Where is $f$ discontinuous? 
- Where is $f$ non-differentiable? 
- Is $f$ Riemann integrable?
- If $f$ Lebesgue integrable? 
  If so, what is $\int_\RR f$?

## Dirichlet function
\[
f(x )\da \chi_{\QQ}(x)
\]

- Bounded: $\abs{f} \leq 1$.
- Discontinuous on $\RR$
- Non-differentiable on $\RR$
- Not Riemann integrable
- Lebesgue integrable with $\int_\RR f = 0$.

## Dirichlet with a Continuous Point
$$
f ( x ) = x~\chi(\QQ) = 
\begin{cases}
x, & x\in \QQ \\
0, & \text{else}
\end{cases}
$$

- Continuous at 0
- Discontinuous at $\RR-\theset{0}$
- Not integrable
  - $U(f) > \frac 1 4$ but $L(f) = 0$.
- Differentiable nowhere

## Dirichlet with a Differentiable Point
$$
f ( x ) = x^2~\chi(\QQ) = \begin{cases}
x^2, & x\in \QQ \\
0, & \text{else}
\end{cases}
$$

- Continuous at 0
- Discontinuous at $\RR-\theset{0}$
- Not integrable
- Differentiable at 0 

## Dirichlet with Two Functions
$$
f ( x ) = x~\chi{\QQ} + (-x)\chi(\RR-\QQ) = \begin{cases}
x, & x\in \QQ \\
-x, & \text{else}
\end{cases}
$$

- Continuous at 0
- Discontinuous at $\RR-\theset{0}$
- Differentiable nowhere.
- Not integrable


:::{.proof title="of non-integrability"}
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


## The Thomae function
$$
f ( x ) = \begin{cases}
\frac 1 q, & x = \frac p q \in \QQ,~(p,q) = 1 \\
0, & \text{else}
\end{cases}
$$

- Continuous on $\RR-\QQ$
- Discontinuous on $\QQ$
- Integrable with $\int_a^b f = 0$
- Differentiable nowhere


## Weierstrass Function

\[
f(x)=\sum_{n=0}^{\infty} a^{n} \cos \left(b^{n} \pi x\right)
&&
a \in (0, 1), b \in \ZZ_{\geq 0}, ab > 1 + {3\pi \over 2}
.\]

Note that this series converges uniformly since it's bounded above by $\sum \abs{a^n}$, which is geometric.

- Bounded: ?
- Continuous on $\RR$.
- Non-differentiable on $\RR$
- Riemann integrable: ?
- Lebesgue integrable: ?


