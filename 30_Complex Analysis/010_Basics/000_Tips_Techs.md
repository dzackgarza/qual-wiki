---
order: 0
---

# Info / Tips / Techniques

> A great deal of content borrowed from the following: <https://web.stanford.edu/~chriseur/notes_pdf/Eur_ComplexAnalysis_Notes.pdf>

## Greatest Hits

Things to know well:

- Estimates for derivatives
- [[30_Complex Analysis/020_Applications of Cauchy/015 Mean Value Theorem|MVT]]
- [[30_Complex Analysis/999_Quals/035_Cauchy Theorem|Cauchy's theorem]]
- [[30_Complex Analysis/020_Applications of Cauchy/012 Cauchy Integral Formula|Cauchy's integral formula]]
- [[30_Complex Analysis/020_Applications of Cauchy/012_Cauchy Inequality|Cauch'y inequality]]
- [[30_Complex Analysis/020_Applications of Cauchy/050_Morera_Theorem|Morera's theorem]]
	- [[30_Complex Analysis/999_Quals/070_Morera|Morera qual questions]]
- [[30_Complex Analysis/020_Applications of Cauchy/020 Liouville]]
	- [[30_Complex Analysis/999_Quals/050 Liouville|Liouville qual questions]]
- [[30_Complex Analysis/999_Quals/040_Maximum_Modulus]]
- [[30_Complex Analysis/040_Zeros_and_Poles/030_Rouche]]
- [[30_Complex Analysis/020_Applications of Cauchy/030_Schwarz reflection principle]]
- [[The Schwarz lemma]]
- [[Maximum modulus principle]]
- [[Rouche's theorem]]
- [[The Schwarz reflection principle]]
- [[The Schwarz lemma]]
- [[30_Complex Analysis/045_Casorati/Casorati-Weierstrass]]
- Properties of [[100_Linear Fractional Transformations]] 
- [[conformal maps]]
- [[Maps of the disc]] and automorphisms of $\DD, \CC, \CP^1$

## Common Tricks

- Virtually any time: consider $1/f(z)$ and $f(1/z)$.
- Setting $w=e^z$ is useful.


:::{.remark title="Estimating and bounding"}
\envlist

- Bounding a derivative using the original function: Cauchy's formula.
  - Also works to bound a function in terms of its integral, e.g. over a compact set like a curve.

:::


:::{.remark title="Showing a function is constant"}
If you want to show that a function $f$ is constant, try one of the following:

- Write $f = u + iv$ and use Cauchy-Riemann to show $u_x, u_y = 0$, etc.
- Show that $f$ is entire and bounded.
  - If you additionally want to show $f$ is zero, show $\lim_{z\to\infty} f(z) = 0$.
- By the open mapping theorem, if $f \in \Hol( \Omega)$ then $\dim_\RR f(\Omega) \in {0, 2}$ but can never have dimension 1. So non-constant $f$ can not map open regions onto subsets of a curve, e.g. $I \subseteq \RR$, and if the image of $f$ is a curve or totally real, then $f$ is constant.
- Holomorphic functions have isolated zeros.
- For real analysis: if $f' < M$, apply the mean value theorem to show $f$ is Lipschit: $\abs{f(x) - f(y)} = \abs{f'(\xi)} \abs{x-y} < M\abs{x-y}$.

:::

:::{.remark title="Showing a function is holomorphic"}
To show a function is holomorphic,

- Use Morera's theorem
- Find a primitive (sufficient but not necessary)

:::

:::{.remark title="Counting zeros"}
To count zeros:

- Rouche's theorem
- The argument principle

:::

:::{.remark title="Arithmetic tricks"}
Some silly arithmetic tricks:

- $z$ is purely imaginary $\iff \bar{z} = -z$.
- $z\in \RR \iff \bar z = z$.
- To prove $a=b$, try $a/b = 1$ or $a-b=0$.
- To prove that a singularity $z_0$ of $f$ is removable, show that $\lim_{z\to z_0} f(z)$ is bounded.
- To prove that a singularity $z_0$ is a pole of $f$ of order $m$, write $f(z) = (z-z_0)^mg(z)$ where $g(z_0)\neq 0$ (or check the Laurent expansion directly).
  - To just show it is a pole, show $\lim_{z\to z_o}f(z) = \infty$.
- To show that a singularity is essential, show that $\lim_{z\to z_0} f(z)$ doesn't exist (e.g. if it's oscillatory).
  - It can be useful to take a specific sequence $\ts{z_k}\to z_0$.
- To show that a zero $z_0$ is order $n$, show that $f^{(<n)}(z_0) = 0$ but $f^{(n)}(z_0) \neq 0$.
- To prove $a\leq b$, try showing ${a\over b} \leq 1$.

:::


