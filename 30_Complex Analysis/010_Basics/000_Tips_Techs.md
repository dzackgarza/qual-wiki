> A great deal of content borrowed from the following: <https://web.stanford.edu/~chriseur/notes_pdf/Eur_ComplexAnalysis_Notes.pdf>

# General Info / Tips / Techniques

## Greatest Hits

Things to know well:

- Estimates for derivatives, [[mean value theorem]]
- [[Cauchy's theorem]]
- [[Cauchy's integral formula]]
- [[Cauchy's inequality]]
- [[Morera's theorem]]
- [[Liouville's theorem]]
- [[Maximum modulus principle]]
- [[Rouche's theorem]]
- [[The Schwarz reflection principle]]
- [[The Schwarz lemma]]
- [[Casorati-Weierstrass]]
- Properties of [[linear fractional transformations]] and [[conformal maps]]
- Automorphisms of $\DD, \CC, \CP^1$.

## Common Tricks

- Virtually any time: consider $1/f(z)$ and $f(1/z)$.
- Setting $w=e^z$ is useful.

:::{.remark title="Showing a function is constant"}
If you want to show that a function $f$ is constant, try one of the following:

- Write $f = u + iv$ and use Cauchy-Riemann to show $u_x, u_y = 0$, etc.
- Show that $f$ is entire and bounded.
  - If you additionally want to show $f$ is zero, show $\lim_{z\to\infty} f(z) = 0$.
:::

:::{.fact}
To show a function is holomorphic,

- Use Morera's theorem
- Find a primitive (sufficient but not necessary)

:::

:::{.fact}
To count zeros:

- Rouche's theorem
- The argument principle

:::