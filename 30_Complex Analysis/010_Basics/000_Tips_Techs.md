---
order: 0
---

# Info / Tips / Techniques

> A great deal of content borrowed from the following: <https://web.stanford.edu/~chriseur/notes_pdf/Eur_ComplexAnalysis_Notes.pdf>

## Greatest Hits

Things to know well:

- Estimates for derivatives
- [[30_Complex Analysis/020_Applications of Cauchy/010_Cauchy_Theorem|Cauchy's theorem]]
- [[30_Complex Analysis/020_Applications of Cauchy/015 Mean Value Theorem|MVT for harmonic/holomorphic functions]]
- [[30_Complex Analysis/020_Applications of Cauchy/012 Cauchy Integral Formula|Cauchy's integral formula]]
- [[30_Complex Analysis/020_Applications of Cauchy/012_Cauchy Inequality|Cauch'y inequality]]
- [[30_Complex Analysis/020_Applications of Cauchy/050_Morera_Theorem|Morera's theorem]]
	- [[30_Complex Analysis/999_Quals/070_Morera|Morera qual questions]]
- [[30_Complex Analysis/020_Applications of Cauchy/020 Liouville|Liouville's theorem]]
	- [[30_Complex Analysis/999_Quals/050 Liouville|Liouville qual questions]]
- [[30_Complex Analysis/999_Quals/040_Maximum_Modulus|The Maximum Modulus principle]]
- [[30_Complex Analysis/040_Zeros_and_Poles/030_Rouche|Rouche's theorem]]
- [[30_Complex Analysis/020_Applications of Cauchy/030_Schwarz reflection principle|The Schwarz reflection principle]]
- [[30_Complex Analysis/060_Maps of Disc/060_Schwarz lemma|The Schwarz lemma]]
- [[30_Complex Analysis/045_Casorati/Casorati-Weierstrass|Casorati-Weierstrass]]
	- [[30_Complex Analysis/999_Quals/300_Riemann Mapping, Casorati|Casorati-Weierstrass Qual questions]]
- [[30_Complex Analysis/050_Conformal_Maps/031_Conformal_Standard|Conformal maps]]
- [[30_Complex Analysis/900 Unsorted/Maps of the disc|Automorphisms of the disc]]
	- The Cayley transformation
	- Other Mobius transformations
- [[30_Complex Analysis/020_Applications of Cauchy/030 Identity Principle|The identity principle]]
- [[30_Complex Analysis/070_Omitted Values/070_Picard|Picard theorems]]
- [[30_Complex Analysis/040_Zeros_and_Poles/040_Open Mapping|The open mapping theorem]]
- [[30_Complex Analysis/030_Residues/020_Residues|Computing residues]]
- Jordan's lemma
- [[30_Complex Analysis/010_Basics/130_The Cauchy-Riemann equations|The Cauchy-Riemann equations]]
- [[30_Complex Analysis/040_Zeros_and_Poles/020_Argument Principle|The argument principle]]
- [[30_Complex Analysis/060_Maps of Disc/090_Riemann Mapping|The Riemann mapping theorem]]

For just the statements of most of these theorems: [[attachments/ComplexAnalysisNotes.pdf|see this doc]].


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
- Showing something is constant or zero on a region: show it's zero on the boundary and apply the MMP.
- Show that $f$ omits at least 2 values and apply little Picard.

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

## Arithmetic

:::{.remark title="Arithmetic tricks"}
Some silly arithmetic tricks:

- $z$ is purely imaginary $\iff \bar{z} = -z$.
- $z\in \RR \iff \bar z = z$.
- $\log\qty{\abs{z}} = {1\over 2}\log\qty{\abs{z}^2} = {1\over 2}\log\qty{x^2 + y^2}$, which is easier to differentiate.
- To prove $a=b$, try $a/b = 1$ or $a-b=0$.
:::

## Constant or Zero

- $\abs{f}$ constant implies $f$ constant by the open mapping theorem.

## Singularities and zeross

- Let $z_0$ be a singularity of $f$. To show $z_0$ is...
	- **Removable**: show that $\lim_{z\to z_0} f(z)$ is bounded.
	- **A pole of some order:** show $\lim_{z\to z_o}f(z) = \infty$.
	- **A pole of order $m$**: write $f(z) = (z-z_0)^mg(z)$ where $g(z_0)\neq 0$ (or check the Laurent expansion directly).
	- **Essential**: show that $\lim_{z\to z_0} f(z)$ doesn't exist (e.g. if it's oscillatory).
  - It can be useful to take a specific sequence $\ts{z_k}\to z_0$.
- To show that a zero $z_0$ is order $n$, show that $f^{(<n)}(z_0) = 0$ but $f^{(n)}(z_0) \neq 0$.


## Estimating
- To show that a sequence of harmonic functions converge on e.g. a disc or rectangle, find good estimates on the boundary and apply the MMP.
- To prove $a\leq b$, try showing ${a\over b} \leq 1$.
- To bound a rational function, use the reverse triangle inequality:
\[
\abs{a\pm b} \geq \abs{ \abs{a} - \abs{b}} \implies {1\over \abs{a\pm b}} \leq {1\over \abs{\abs{a} - \abs{b} } }
.\]

- To show $a\leq b$, try ${a\over b}\leq 1$ instead and reason about $\DD$.
  - Alternatively, try $b-a\geq 0$ (obvious, but useful!)
- If $\abs{f} = M$ on $\bd \Omega$, then if (importantly) $f\neq 0$ in $\Omega$ then $\abs{f} = M$ on all of $\bar \Omega$ by apply the MMP to $f$ and $1/f$.
	- Why $f\neq 0$ is necessary: take $f(z) = z$.
	
## Polynomials

- $f$ is polynomial when:
	- $f^{(n)} =0$ for every $n$ large enough.
	- $f$ is entire and only has poles at $\infty$.

## General advice

- Given $f$, define $g\da e^f$, then $\abs{g} = e^{\Re(f)}$.
- If $f$ is holomorphic in a neighborhood of $\DD$ and $\abs{f} = 1$ on $\bd \DD$, then $f$ is a finite Blaschke product.

- A holomorphic function with a non-isolated zero is identically zero.
- If $f$ has no zeros, put it in the denominator! No one can stop you!
  - Getting rid of zeros: divide by a Blaschke product.

- $f$ and $f'$ have the same poles.