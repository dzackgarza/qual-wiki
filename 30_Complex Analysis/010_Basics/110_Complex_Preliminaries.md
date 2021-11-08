---
order: 110
---

# Complex Preliminaries

- Since $\CC$ is a field, $\CC[x]$ is a UFD.

:::{.definition title="Toy contour"}
A closed Jordan curve that separates $\CC$ into an exterior and interior region is referred to as a **toy contour**.
:::

:::{.fact title="Complex roots of a number"}
The complex $n$th roots of $z \da r e^{i\theta}$ are given by
\[
\ts{ \omega_k \da r^{1/n} e^{i \qty{ \theta + 2k\pi \over n} } \st 0 \leq k \leq n-1 }
.\]
Note that one root is $r^{1/n}\in \RR$, and the rest are separated by angles of $2\pi/n$.
Mnemonic: 
\[
z = re^{i\theta} = re^{i\qty{\theta + 2k\pi}} \implies z^{1/n} = \cdots
.\]
:::


:::{.fact title="Factoring common polynomials"}
Note $\zeta_n \da e^{2\pi i n}$ so $\zeta_n^k = e^{2\pi i k \over n}$ and $\zeta_n^n = e^{2\pi i} = 1$.
Similarly $\zeta_{2n} = e^{2\pi i \over 2n} = e^{\pi i \over n}$ so $\zeta_{2n}^n = e^{\pi i} = -1$.

\[
z^n-1 &= \prod_{k=1}^n (z-\zeta_n^k) 
= (z-\zeta_n)(z-\zeta_n^2)\cdots(z-\zeta_n^{n-1}) (z-1)\\
z^n+1 &= \prod_{k=1}^n (z - \zeta_{2n}^k)
= (z-\zeta_{2n})(z-\zeta_{2n}^2)\cdots(z-\zeta_{2n}^{n-1}) (z- (-1) )\\
.\]

:::


[[30_Complex Analysis/010_Basics/115_Complex Log]]

[[30_Complex Analysis/010_Basics/130_The Cauchy-Riemann equations]]

[[30_Complex Analysis/010_Basics/125_Harmonic Functions]]




