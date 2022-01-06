---
order: 0
---

# Info / Tips / Techniques

> A great deal of content borrowed from <https://web.stanford.edu/~chriseur/notes_pdf/Eur_ComplexAnalysis_Notes.pdf>

Some useful notation:

- $\DD_r(a) \da \ts{z\in \CC \st 0\leq \abs{z-a}< a}$ an open disc about $a$
- $\bar{\DD}_r(a) \da \ts{z\in \CC \st 0\leq \abs{z-a} \leq a}$ a closed disc about $a$.
- $\DD^*(a) \da \ts{z\in \CC \st 0 < \abs{z-a} < r}$ a punctured disc about $a$.
- $\Delta \da \DD_1(0)$ the standard unit disc
- $\bar\Delta \da \bar{\DD}_1(0)$ the closed unit disc
- $\Delta^* \da \DD_1^*(0)$ the punctured unit disc.
- $\Omega$ an open simply-connected subset of $\CC$.
- $\OO(\Omega), \Hol(\Omega), \Hol(\Omega, \CC)$ the holomorphic functions $f:\Omega \to \CC$ equipped with the structure of a $\CC\dash$algebra..

## Greatest Hits

Things to know well:

- Estimates for derivatives
- [[30_Complex Analysis/020_Applications of Cauchy/010_Cauchy_Theorem|Cauchy's theorem]]
- [[30_Complex Analysis/020_Applications of Cauchy/015 Mean Value Theorem|MVT for harmonic/holomorphic functions]]
- [[30_Complex Analysis/020_Applications of Cauchy/012 Cauchy Integral Formula|Cauchy's integral formula]]
- [[30_Complex Analysis/020_Applications of Cauchy/012_Cauchy Inequality|Cauchy's inequality]]
- [[30_Complex Analysis/020_Applications of Cauchy/050_Morera_Theorem|Morera's theorem]]
	- [[30_Complex Analysis/999_Quals/070_Morera|Morera qual questions]]
- [[30_Complex Analysis/020_Applications of Cauchy/020 Liouville|Liouville's theorem]]
	- [[30_Complex Analysis/999_Quals/050 Liouville|Liouville qual questions]]
- [[30_Complex Analysis/030_Zeros_and_Poles/030_Rouche|Rouche's theorem]]
	- [[30_Complex Analysis/999_Quals/052_Rouche|Rouche qual questions]]
- [[30_Complex Analysis/020_Applications of Cauchy/030_Schwarz reflection principle|The Schwarz reflection principle]]
- [[30_Complex Analysis/060_Maps of Disc/060_Schwarz lemma|The Schwarz lemma]]
	- [[30_Complex Analysis/999_Quals/200_Schwarz_Lemma|Schwarz lemma qual questions]]
- [[30_Complex Analysis/070_Omitted Values/020_Casorati-Weierstrass|Casorati-Weierstrass]]
	- [[30_Complex Analysis/999_Quals/300_Riemann Mapping, Casorati|Casorati-Weierstrass Qual questions]]
- [[30_Complex Analysis/050_Conformal_Maps/031_Conformal_Standard|Conformal maps]]
- [[30_Complex Analysis/060_Maps of Disc/000 Automorphisms of the disc and plane|Automorphisms of the disc and plane]]
	- The Cayley transformation and other Mobius transformations
	- [[30_Complex Analysis/999_Quals/105_Conformal Maps|Conformal map questions]]
- [[30_Complex Analysis/020_Applications of Cauchy/030 Identity Principle|The identity principle]]
- [[30_Complex Analysis/070_Omitted Values/070_Picard|Picard theorems]]
- [[30_Complex Analysis/030_Zeros_and_Poles/040_Open Mapping|The open mapping theorem]]
- [[30_Complex Analysis/040_Residues/020_Residues|Computing residues]]
	- [[30_Complex Analysis/999_Quals/030_Computing Integrals|Qual integrals]]
- Jordan's lemma
- [[30_Complex Analysis/010_Basics/130_The Cauchy-Riemann equations|The Cauchy-Riemann equations]]
- [[30_Complex Analysis/030_Zeros_and_Poles/020_Argument Principle|The argument principle]]
- [[30_Complex Analysis/060_Maps of Disc/090_Riemann Mapping|The Riemann mapping theorem]]
- [[30_Complex Analysis/030_Zeros_and_Poles/060 Riemann removable singularity|Riemann's removable singularity theorem]]

For just the statements of most of these theorems: [[attachments/ComplexAnalysisNotes.pdf|see this doc]].


## Common tricks

- Virtually any time: consider $1/f(z)$ and $f(1/z)$.
- Set $w=e^z$.
- If $f$ has no zeros, put it in the denominator! No one can stop you!
- If $f$ is holomorphic in a neighborhood of $\DD$ and $\abs{f} = 1$ on $\bd \DD$, then $f$ is a finite Blaschke product.
- If $\Omega$ is connected, $f$ admits a log and exponential, so try setting $f^{1\over n} = \exp\qty{{1\over n}\log(f)}$.

## Holomorphic

-To show a function is holomorphic,
	- Use Morera's theorem
	- Find a primitive (sufficient but not necessary)
	- Express $f$ as a convergent power series
- Holomorphic functions have isolated zeros.


## Arithmetic

Some silly arithmetic tricks:

- Absolutely essential: $\abs{f}^2 = f\bar{f}$.
- $z$ is purely imaginary $\iff \bar{z} = -z$.
- $z\in \RR \iff \bar z = z$.
- $\log\qty{\abs{z}} = {1\over 2}\log\qty{\abs{z}^2} = {1\over 2}\log\qty{x^2 + y^2}$, which is easier to differentiate.
- To prove $a=b$, try $a/b = 1$ or $a-b=0$.
- $\int_0^{2\pi} e^{i(m-n)\theta}\dtheta = \chi_{m=n}\cdot 2\pi$.

## Showing a function is constant (or zero)

- Show $f' = 0$.
	- Can write $f=u+iv$ and show $u_x, u_y = 0$ and apply CR.
- Show $\abs{f}=0$ on the boundary and apply the MMP.
- Show that $f$ attains a minimum or maximum on the interior of a domain where it is nonzero.
- Show that $f$ is entire and bounded.
  - If you additionally want to show $f$ is zero, show $\lim_{z\to\infty} f(z) = 0$.
  - Useful trick: show that *either* $\abs{f} \geq M$ or $\abs{f} \leq M$, then by Liouville on $f$ or $1/f$ respectively, $f$ must be constant.
  - Similar trick: show either $e^f$ or $e^{-f}$ is bounded.
  - If the function is periodic, just bound it on a fundamental domain.
- Show that $f(\CC)$ is not an open set (e.g. $\RR$ or $\bd \DD_r(0)$, and apply the open mapping theorem.
	- More generally, the image can be dimension 0 or 2, but never 1. 
	- E.g. if $\im(f) \subseteq \RR$ or $\abs{f} = R$ is constant.
- A holomorphic function with a non-isolated zero is identically zero.
	- How to use: show $f-g$ has uncountably many zeros
- Show that $f$ omits at least 2 values and apply little Picard.
	- E.g. if $f$ misses an open set, or $\abs{f} \geq M$ or $\abs{f} \leq M$.
- Define $g\da e^f$, then $\abs{g} = e^{\Re(f)}$ and if $g$ is constant then $f$ is constant.
- Show any of the following are constant:
	- $u = \Re(f)$
	- $v = \Im(f)$
	- $\abs{f}$
	- $\Arg(f)$
- Show that $f$ preserves $\bd \DD$, so $\abs{f(z)} = 1$ when $\abs{z} = 1$, and has no zeros in $\DD$.
- To show $f(z) = g(z)$ infinitely often, show $f(z)/g(z)$ (or $f(1/z)/g(1/z)$) has an essential singularity and apply Picard or Casorati.

## Singularities 

- Let $z_0$ be a singularity of $f$. To show $z_0$ is...
	- **Removable**: show that $\lim_{z\to z_0} f(z)$ is bounded.
	- **A pole of some order:** show $\lim_{z\to z_o}f(z) = \infty$.
	- **A pole of order $m$**: write $f(z) = (z-z_0)^mg(z)$ where $g(z_0)\neq 0$ (or check the Laurent expansion directly).
    - Can also check that $\del_z^k f(z_0) \neq 0$ for $k<m$ but $\del_z^m f(z_0) = 0$.
	- **Essential**: show that $\lim_{z\to z_0} f(z)$ doesn't exist (e.g. if it's oscillatory).
    - Alternatively, show $z_0$ is neither removable nor a pole, or that $f$ has a Laurent expansion about $z_0$ with infinitely many negative terms.
  - It can be useful to take a specific sequence $\ts{z_k}\to z_0$.

- $f$ and $f'$ have the same poles.

## Zeros

- To show that a zero $z_0$ is order $n$, show that $f^{(<n)}(z_0) = 0$ but $f^{(n)}(z_0) \neq 0$.
- Getting rid of zeros: divide by a Blaschke product.
- To count zeros:
	- Rouche's theorem
	- The argument principle
- If $f(z_0)\neq 0$, by continuity there is some neighborhood where $f$ is nonzero.
	- Conversely, if $f$ is holomorphic at $z_0$ *is* a zero, there is punctured neighborhood of $z_0$ where $f$ is nonzero.

## Estimating

- To prove $a\leq b$, try showing ${a\over b} \leq 1$ and reason about $\DD$, or show $b-a\geq 0$, 
- To bound a rational function, use the reverse triangle inequality:
\[
\abs{a\pm b} \geq \abs{ \abs{a} - \abs{b}} \implies {1\over \abs{a\pm b}} \leq {1\over \abs{\abs{a} - \abs{b} } }
.\]
- Bounding a derivative using the original function: Cauchy's formula.
  - Also works to bound a function in terms of its integral, e.g. over a compact set like a curve.
- If $\abs{f} = M$ on $\bd \Omega$, then if (importantly) $f\neq 0$ in $\Omega$ then $\abs{f} = M$ on all of $\bar \Omega$ by apply the MMP to $f$ and $1/f$.
	- Why $f\neq 0$ is necessary: take $f(z) = z$.
- To show that a sequence of harmonic functions converge on e.g. a disc or rectangle, find good estimates on the boundary and apply the MMP.
- For real analysis: if $f' < M$, apply the mean value theorem to show $f$ is Lipschitz: $\abs{f(x) - f(y)} = \abs{f'(\xi)} \abs{x-y} < M\abs{x-y}$.
- To show $\abs{f} \leq \abs{g}$: if you have a factor of $z$ to play with, try to apply Schwarz to $f/g$ to get $\abs{f/g}\leq \abs{z}$.

  
## Polynomials

- $f$ is polynomial when:
	- $f^{(n)} =0$ for every $n$ large enough (e.g. using Cauchy's inequality)
	- $f$ is entire and only has poles at $\infty$.


## Series

- A common trick:
$$
\frac{1}{z-w}=\frac{1}{(z-a)\left(1-\frac{w-a}{z-a}\right)}=\sum_{n=0}^{n} \frac{(w-a)^{n}}{(z-a)^{n+1}} .
$$
