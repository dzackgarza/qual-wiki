# Field Theory: Extensions and Towers

## Basics

:::{.remark}
Galois is defined as **normal and separable**.
:::

:::{.definition title="Simple Extensions"}
An extension $L/k$ is **simple** iff $L = K( \alpha)$ for some \( \alpha\in L \).
:::

:::{.theorem title="Primitive Element Theorem"}
Every finite separable extension is simple.
:::

:::{.corollary}
$\GF(p^n)$ is a simple extension over $\FF_p$.
:::

:::{.definition title="Algebraic Extension"}
A field extension $L/k$ is **algebraic** iff every $\alpha \in L$ is the root of some polynomial $f\in k[x]$.
:::

:::{.theorem title="Finite Extensions are Algebraic"}
Every finite extension is algebraic.
:::

:::{.proof title="that finite extensions are algebraic"}
If \( K/F \) and \( [K:F] = n \), then pick any \( \alpha \in K \) and consider \( 1, \alpha , \alpha ^2, ...  \).
This yields \( n+1 \) elements in an \( n\dash \)dimensional vector space, and thus there is a linear dependence 
\[
f(\alpha ) \da \sum_{j=1}^n c_j \alpha ^j = 0
.\]
But then \( \alpha \) is the root of the polynomial \( f \).

:::

## Normal Extensions

:::{.definition title="Normal Field Extension"}
Let $L/k$ be an extension.
Then TFAE:

- $L/k$ is **normal**.

- Every irreducible polynomial $f\in k[x]$ that has one root in $L$ has *all* of its roots in $L$, and thus splits in $L[x]$.
  - So if $\alpha\in L$ then every Galois conjugate $\alpha_k \in L$ as well..
   Thus either $f$ splits in $L$ or $f$ has no roots in $L$.

:::

:::{.example title="of normal extensions"}
\envlist

- Useful trick: if $[L: k] = 2$ then $L/k$ is automatically normal.

- Useful trick: if $L/K/k$, then $K/k$ is normal iff $\Gal(L/K) \normal \Gal(L/k)$.

- $K \da \QQ(2^{1\over 3})$ is not normal, since $K\subset \RR$ but $(x^3-2) = \prod_k x-\zeta_3^k 2^{1\over 3}$ with $\zeta_3, \zeta_3^2 \in \CC$.
  - Another reason: an embedding $\sigma: K\to \bar k$ can send $2^{1\over 3}$ to any other root of $x^3-2$.

- $\QQ(\sqrt 2, \sqrt 3)$ is normal over $\QQ$, since it it is finite and splits $f(x) \da (x^2-2)(x^2-3)$, which is a separable polynomial.

- $L \da \QQ(2^{1\over 4})$ is not normal, since it is finite but not the splitting field of any polynomial.

- $\QQ(\zeta_k)$ is normal for $\zeta_k$ any primitive $k$th root of unity.


- A normal non-separable extension: $\FF_p(x, y) \slice{\FF_p (x^p, y^p)}$.
  This has finite degree $p^2$ but infinitely many subfields?

:::

:::{.proposition title="Characterization of normal algebraic extensions"}
For $L/k$ algebraic: let $\bar{k}$ be an algebraic closure containing $L$, then $L/k$ is normal iff every $k\dash$embedding $\sigma: L\to \bar{k}$ satisfies $\im \sigma = L$, so $\sigma$ is a $k\dash$automorphism of $L$:

\begin{tikzcd}
	&& {\bar{k}} \\
	\\
	L && \textcolor{rgb,255:red,92;green,214;blue,92}{\sigma(L) = L} \\
	\\
	k && k
	\arrow[hook, from=5-1, to=3-1]
	\arrow[Rightarrow, no head, from=5-1, to=5-3]
	\arrow[hook, from=5-3, to=3-3]
	\arrow[hook, from=3-3, to=1-3]
	\arrow["\sigma", hook, from=3-1, to=1-3]
	\arrow[hook, two heads, from=3-1, to=3-3]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsNSxbMCw0LCJrIl0sWzAsMiwiTCJdLFsyLDQsImsiXSxbMiwwLCJcXGJhcntrfSJdLFsyLDIsIlxcc2lnbWEoTCkgPSBMIixbMTIwLDYwLDYwLDFdXSxbMCwxLCIiLDAseyJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6InRvcCJ9fX1dLFswLDIsIiIsMSx7ImxldmVsIjoyLCJzdHlsZSI6eyJoZWFkIjp7Im5hbWUiOiJub25lIn19fV0sWzIsNCwiIiwxLHsic3R5bGUiOnsidGFpbCI6eyJuYW1lIjoiaG9vayIsInNpZGUiOiJ0b3AifX19XSxbNCwzLCIiLDEseyJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6InRvcCJ9fX1dLFsxLDMsIlxcc2lnbWEiLDAseyJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6InRvcCJ9fX1dLFsxLDQsIiIsMSx7InN0eWxlIjp7InRhaWwiOnsibmFtZSI6Imhvb2siLCJzaWRlIjoidG9wIn0sImhlYWQiOnsibmFtZSI6ImVwaSJ9fX1dXQ==)

:::

:::{.definition title="Normal Closure"}
If $K/k$ is algebraic, then there is an extension $N_k/K$ such that $N_k/k$ is normal and $N_k/K/k$ is a tower.
$N_k$ is referred to as the **normal closure** of $K/k$.
:::

:::{.proposition title="Characterization of finite normal extensions as splitting fields"}
An extension $L/k$ is finite and normal $\iff L$ is the splitting field of some polynomial $f\in k[x]$.
:::

:::{.proof title="?"}
$\implies$:

- Write $L = k(a_1, \cdots, a_n)$ by finiteness.
- Let $m_i$ be the minimal polynomials of the $a_i$.
- By normality, the $m_i$ split in $L[x]$.
- Then $L$ is the splitting field of $f(x) \da \prod_i m_i(x)$.

$\impliedby$:

- Suppose $L/k = \SF(f)$, and pick any monic $m\in L[x]^{\irr}$ with a root $a\in L$, so that $m$ is the minimal polynomial of $a$.
- Toward showing $m$ splits in $L$: let $M = \SF(m)$, we'll show $M=L$.
- To show that for any root $b\in M$ we have $b\in L$, it suffices to show $[L(b): L] = 1$.

  The strategy: use that $[L(a):L] = 1$ since $a\in L$ by assumption, and try to relate the two degrees.

- We have $L/k$, and a number of towers to work with:
\[
[L(a):k] &= [L(a): k(a)] [k(a): k] &= [L(a) : L] [L: k] \\ \\
[L(b):k] &= [L(b): k(b)] [k(b): k] &= [L(b) : L] [L: k]
.\]

- In the first set of equalities, note that $k(a)\slice{k} \cong k(b)\slice{k}$ since $a,b$ are conjugate roots over $k$.
  Moreover $L(a)\slice{k(a)} \cong L(b) \slice{k(b)}$ since both are splitting fields for $f$.

- Thus $[L(a):k] = [L(b): k]$, which forces $[L(a): L] = [L(b): L]$ after dividing by $[L:k]$.
  But $[L(a): L] = 1$.

:::


:::{.proposition}
$\abs{\aut(L/k)} \leq [L: k]$ with equality precisely when $L/k$ is normal.
:::

## Separable Extensions

:::{.definition title="Separable polynomials"}
A polynomial $f \in k[x]$ is **separable** iff $f$ has no repeated roots.
:::

:::{.example title="of separable and inseparable polynomials"}
\envlist

- $x^2-1$ is separable over $\QQ$, but inseparable over $\FF_2$ since it factors as $(x-1)^2$.
- $(x^2-2)^2$ is inseparable over $\QQ$
- $x^2-t$ is inseparable over $\FF_2(t)$.
- $f(x) \da x^n-1$ is inseparable over $\FF_p$ when $p\divides n$.
  - Otherwise, $f' = nx^{n-1}$ has only $x=0$ as roots, whereas $0$ is not a root of $f$, so $f$ is separable.
- $f(x) \da x^p-t$ is not separable over $\FF_p(t)$: it is irreducible by Eisenstein, but has only the single root $t^{1\over p}$.
- $f(x) \da x^{p^n}-x$ is separable over $\FF_p$, since $f'(x) = -1$ has no roots at all.

:::

:::{.definition title="Separable Field Extension"}
Let $L/k$ be a field extension, $\alpha \in L$ be algebraic over $k$, and $f(x) \definedas\min(\alpha, k)$.
The following are equivalent 

- $L/k$ is a **separable** extension.
- Every element ${\alpha} \in L$ is separable over $k$, so $\alpha$ has separable minimal polynomial $m(x)$ in some splitting field of $m$.
- Every finite subextension $L'/k$ is separable.
:::

:::{.fact}
If $\alpha \in K/k$ is separable, then $\alpha$ is separable in any larger field $L/K/k$ since the minimal polynomial over the larger field will divide the minimal polynomial over the smaller field. 
:::

:::{.proposition title="Separability test: $\gcd$ with derivative"}
$f$ is separable iff $\gcd(f, f')=1$, so $f, f'$ share no common roots.
Moreover, the multiple roots of $f$ are precisely the roots of $\gcd(f, f')$.
:::

:::{.proof title="of separability test"}
$\not\implies$:
Suppose $f$ has a repeated root $r_i$, so its multiplicity is at least 2.
Then 
\[
f(x) = (x-r)^2 g(x) \implies f'(x) = 2(x-r)g(x) + (x-r)^2g'(x)
,\]
so $r$ is a root of $f'$.

$\not\impliedby$:
Suppose $r$ is a root of $f, f'$.
Write $f(x) = (x-r)p(x)$ and $f'(x) = (x-r)p'(x) + p(x)$.
Rearranging, $f'(x) - (x-r)p'(x) = p(x)$, and since $r$ is a root of the LHS it's a root of the RHS.
So $p(x) = (x-r) q(x)$ and $f(x) = (x-r)^2 q(x)$, making $r$ a repeated root.
:::

:::{.proposition title="Separability test: identically zero derivative"}
$f\in k[x]^{\irr}$ is **inseparable** (so $f$ has a repeated root) iff $f'(x) \equiv 0$.
:::

:::{.proof title="of separability test"}
Assume $f$ is monic, then $f$ is inseparable iff $f, f'$ have a common root $a$.
So $(x-a)\divides q\da \gcd(f, f')$, and since $f$ is irreducible, it must be the minimal polynomial of $a$.
Since $f'(a) = 0$, this forces $f'\divides f$, and since $\deg f' = \deg f - 1 < \deg f$ this forces $f' \equiv 0$.
:::

:::{.proposition title="Derivative completely detects separability"}
\envlist

- For any field $k$, $f\in k[x]$ is separable $\iff f'\not\equiv 0 \in k[x]$.
- For $\ch k = 0$, irreducible implies separable.
- For $\ch k = p$, irreducibles $f(x)$ are inseparable iff $f(x) = g(x^p)$ for some $g\in k[x]$.


Thus for an irreducible polynomial $f$,
\[
f\text{ separable} \iff \gcd(f, f')=1 \iff f'\not\equiv 0 \iff_{\ch k = p} f(x) = g(x^p)
.\]
:::

:::{.proof title="?"}
- First part:
  - $\not A\implies \not B$: 
    - Let $f$ be irreducible, and suppose $f$ is separable.
      If $d(x) \da \gcd(f, f') \neq 1$, then $f'$ can not divide $f$ since $f$ is irreducible, so $f$ divides $f'$.
      But $\deg f' < f$ and $f\divides f'$ forces $f'\equiv 0$.
  - $\not B \implies \not A$:
    - If $f'\equiv 0$, then $d(x) \da \gcd(f, f') = \gcd(f, 0) = f \neq 1$ and $f$ is *not* separable.

- Second part:
  - If $\ch k = 0$ and $f$ is irreducible, then $\deg f \geq 2$ and $\deg f' \geq 1$ so $f' \neq 0$ and $f$ is thus separable.

- Third part:
  - $\impliedby$: If $f(x) = g(x^p)$ then $f'(x) = g'(x^p)\cdot px^{p-1}\equiv 0$.
  - $\implies$: Let $f$ be irreducible and inseparable, so $f' \equiv 0 \in k[x]$.
    Then $f(x) \da \sum_{k=0}^n a_k x^k$ implies $f'(x) \da \sum_{k=1}^{n}ka_k x^{k-1}$, which is zero iff $ka_k \equiv 0$ so $p$ divides $ka_k$.
    So $a_k\not\equiv 0$ forces $p\divides k$, so $f = a_0 + a_px^p + a_{2p}x^{2p} + \cdots$.
:::

:::{.corollary title="Inseparable iff polynomial in characteristic powers"}
If $f\in k[x]^{\irr}$ and $p\da \ch k > 0$, then $f$ inseparable $\iff f(x) = q(x^{p^n})$ for some unique $n$.
:::

:::{.proof title="of inseparable characterization"}
$\implies$:

Use that $f$ is inseparable iff $f' \equiv 0$.
The claim is that $f' \equiv 0$ in characteristic $p$ iff all exponents present in $f$ are divisible by $p$.
If $f'\equiv 0$, write
\[
f(x) &= a_nx^n + a_{n-1} x^{n-1} + \cdots + a_1 x + a_0 \\
\implies f'(x) &= na_nx^{n-1} + (n-1)a_{n-1}x^{n-2} + \cdots + a_1 \\
&\equiv 0
,\]
which forces $i a_i = 0$ for all $i$.
For any $a_i\neq 0$, this forces $i\equiv 0 \mod p$, so $a_i$ can only be nonzero when $p\divides i$, so $i=kp$ for some $k$.
So reindex to write
\[
f(x) = a_0 + a_1x^p + a_2x^{2p} + \cdots + a_n x^{np} = \qty{b_0 + b_1 x + b_2 x^{2} + \cdots + b_nx^{n}}^p \in \bar{k}[x]
,\]
using $(c+d)^p = c^p + d^p$ in characteristic $p$, and taking $b_i \da a_i^{1\over p} \in \bar{k}$
So $f' \equiv 0\implies f(x) = q(x^p)$ where $q(t) \da \sum b_i t^i$.

$\impliedby$:
If $f(x) = q(x^p)$ for some $q$, the previous calculation shows $q$ has multiple roots, thus so does $f$, so $f$ is inseparable.
:::

:::{.fact title="Irreducible implies separable in characteristic zero"}
If $\ch k = 0$ and $f\in k[x]^{\irr}$, then $f$ is automatically separable.

Why this is true: assuming $f$ is irreducible, $\gcd(f, f') = 1$ or $f$.
It can't be $f$, since $f\divides f'$ would force $\deg f = \deg f' = 0$ and make $f$ a constant.
So this $\gcd$ is 1.
:::

:::{.fact title="Irreducible implies separable for perfect fields"}
\envlist

- Use that irreducible polynomial $f$ must have distinct roots, by the argument above.
  (In fact, it is the minimal polynomial of its roots.)

- Toward a contradiction, suppose $f$ is irreducible but inseparable.
- Then $f(x) = g(x^p)$ for some $g(x) \da \sum a_k x^k$.
- Since Frobenius is bijective, write $a_k = b_k^p$ for some $b_k$, then
\[
f(x) = \sum a_k x^{pk} = \sum b_k^p x^{pk} =\qty{ \sum b_k x^k }^p
,\]
  making $f$ reducible. $\contradiction$
:::

:::{.fact title="finite extensions of perfect fields are separable"}
A finite extension of a perfect field is automatically separable, and one only needs to show normality to show it's Galois.
:::

:::{.proposition title="Simplifications of separability for finite extensions"}
If $L/k$ is a finite extension, then, TFAE:

- $L/k$ is separable.
- \( L = k( \alpha) \) for \( \alpha \)  a separable element.
- \( L = k( S ) \) for \( S \) some set of separable elements
- $[L: K] = [L:K]_s$, i.e. the separable degree equals the actual degree.
\[
[L: k] = \ts{ L: k } \da \size \Aut_{\Fieldsover k}(L)
.\] 
:::

:::{.proposition title="Separable splitting fields are Galois"}
If $L/k$ is separable, then
\[
[L: k] = \ts{ L: k } 
.\]
If $L/k$ is a splitting field, then
\[
[L:K] = \size \Aut_{\Fieldsover{k}}(L) \da \size \Gal(L/k)
.\]

:::

:::{.proposition title="Irreducible polynomials have separable splitting fields"}
Irreducible polynomials have distinct roots after passing to a splitting field.
:::

:::{.proposition title="Algebraic extensions of perfect fields are separable"}
If $\ch k = 0$ or $k$ is finite, then every *algebraic* extension $L/k$ is separable.
:::

:::{.proposition title="Irreducible implies separable for perfect fields"}
If $k$ is a perfect field, then every irreducible $f\in k[x]^{\irr}$ is automatically separable.
:::

:::{.proof title="?"}
If $\ch k = 0$ and $f$ is irreducible, then since $\deg f' < \deg f$ and $f$ is irreducible we must have $\gcd(f, f')=1$ and $f$ is separable.

If $\ch k = p>0$, then if $f$ is irreducible and inseparable then $f(x) = g(x^p)$ for some $g$.
Write $g(x) = \sum a_k x^k$, and since $k$ is perfect, write $b_k \da a_k^{1\over p}$, then
\[
f(x) = \sum a_k x^{pk} = \sum b_k^p x^{pk} = \qty{\sum b_k x^k}^p
,\]
so $f$ is reducible. $\contradiction$.

:::

:::{.definition title="Separable degree"}
The **separable degree** of an extension $L/k$ is defined by fixing an embedding $\sigma: k\embeds \bar{k}$ (the algebraic or separable closure) and letting $[L:k]_s$ be the number of embeddings $\sigma':L\to \bar{k}$:

\begin{tikzcd}
	L && {\bar{k}} \\
	\\
	k && k
	\arrow["{\sigma'}", dashed, hook, from=1-1, to=1-3]
	\arrow[hook, from=3-1, to=1-1]
	\arrow["\sigma"', hook, from=3-3, to=1-3]
	\arrow[Rightarrow, no head, from=3-1, to=3-3]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsNCxbMCwyLCJrIl0sWzIsMCwiXFxiYXJ7a30iXSxbMCwwLCJMIl0sWzIsMiwiayJdLFsyLDEsIlxcc2lnbWEnIiwwLHsic3R5bGUiOnsidGFpbCI6eyJuYW1lIjoiaG9vayIsInNpZGUiOiJ0b3AifSwiYm9keSI6eyJuYW1lIjoiZGFzaGVkIn19fV0sWzAsMiwiIiwwLHsic3R5bGUiOnsidGFpbCI6eyJuYW1lIjoiaG9vayIsInNpZGUiOiJ0b3AifX19XSxbMywxLCJcXHNpZ21hIiwyLHsic3R5bGUiOnsidGFpbCI6eyJuYW1lIjoiaG9vayIsInNpZGUiOiJ0b3AifX19XSxbMCwzLCIiLDIseyJsZXZlbCI6Miwic3R5bGUiOnsiaGVhZCI6eyJuYW1lIjoibm9uZSJ9fX1dXQ==)

:::

:::{.proposition title="Separability is transitive."}
If $L/K/k$, then $L/K$ is separable and $K/k$ is separable $\iff$ $L/k$ is separable:

\begin{tikzcd}
	L &&& L \\
	\\
	K &&& K \\
	\\
	k &&& k
	\arrow[hook, no head, from=5-1, to=3-1]
	\arrow[""{name=0, anchor=center, inner sep=0}, hook, no head, from=3-1, to=1-1]
	\arrow[hook, no head, from=5-4, to=3-4]
	\arrow[""{name=1, anchor=center, inner sep=0}, hook, no head, from=3-4, to=1-4]
	\arrow[color={rgb,255:red,214;green,92;blue,92}, curve={height=12pt}, dashed, from=1-1, to=3-1]
	\arrow[color={rgb,255:red,214;green,92;blue,92}, curve={height=12pt}, dashed, from=3-1, to=5-1]
	\arrow[color={rgb,255:red,92;green,214;blue,92}, curve={height=18pt}, dashed, tail reversed, no head, from=5-4, to=1-4]
	\arrow[shorten <=19pt, shorten >=19pt, Rightarrow, from=0, to=1]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsNixbMCwwLCJMIl0sWzAsMiwiSyJdLFswLDQsImsiXSxbMywwLCJMIl0sWzMsMiwiSyJdLFszLDQsImsiXSxbMiwxLCIiLDAseyJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6InRvcCJ9LCJoZWFkIjp7Im5hbWUiOiJub25lIn19fV0sWzEsMCwiIiwwLHsic3R5bGUiOnsidGFpbCI6eyJuYW1lIjoiaG9vayIsInNpZGUiOiJ0b3AifSwiaGVhZCI6eyJuYW1lIjoibm9uZSJ9fX1dLFs1LDQsIiIsMCx7InN0eWxlIjp7InRhaWwiOnsibmFtZSI6Imhvb2siLCJzaWRlIjoidG9wIn0sImhlYWQiOnsibmFtZSI6Im5vbmUifX19XSxbNCwzLCIiLDAseyJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6InRvcCJ9LCJoZWFkIjp7Im5hbWUiOiJub25lIn19fV0sWzAsMSwiIiwyLHsiY3VydmUiOjIsImNvbG91ciI6WzAsNjAsNjBdLCJzdHlsZSI6eyJib2R5Ijp7Im5hbWUiOiJkYXNoZWQifX19XSxbMSwyLCIiLDIseyJjdXJ2ZSI6MiwiY29sb3VyIjpbMCw2MCw2MF0sInN0eWxlIjp7ImJvZHkiOnsibmFtZSI6ImRhc2hlZCJ9fX1dLFs1LDMsIiIsMix7ImN1cnZlIjozLCJjb2xvdXIiOlsxMjAsNjAsNjBdLCJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJhcnJvd2hlYWQifSwiYm9keSI6eyJuYW1lIjoiZGFzaGVkIn0sImhlYWQiOnsibmFtZSI6Im5vbmUifX19XSxbNyw5LCIiLDAseyJzaG9ydGVuIjp7InNvdXJjZSI6MjAsInRhcmdldCI6MjB9fV1d)

:::

:::{.proof title="?"}
Use that $L/k$ is separable $\iff [L:k] = [L:k]_s$.

$\impliedby$:

- By definition, every $\alpha \in L$ is separable over $k$.
- $K/k$ is separable:
  - Since $K \subseteq L$, any $\alpha \in K$ is also separable over $k$.
- $L/K$ is separable:
  - If $\alpha \in L$, then $\min_{\alpha, k}(x)$ is a separable polynomial over some splitting field.
  - Use that $L/k$ implies $\min_{\alpha, L}(x)$ divides $\min_{\alpha, k}(x)$, so the former is separable, done.

$\implies$:

- Now use that the separable degree is multiplicative in towers.
- If all extensions in sight are **finite**, this direction is immediate:
\[
[L:k]_s = [L:K]_s [K:k]_s = [L:K][K:k] = [L:K]
.\]

- For the infinite case, want to show every $\alpha\in L$ is separable over $k$.
  It suffices to show $\alpha$ is contained in some finite separable subextension.
  The strategy:

\begin{tikzcd}
	\alpha\in & L \\
	&&& {k(\alpha, S)} & {\ni \alpha} \\
	{f\in K[x]} & K \\
	&&& {F\da k(\alpha, S) \intersect K} & {f\in F[x]} \\
	& k
	\arrow["s"', hook, from=5-2, to=4-4]
	\arrow["s"', hook, from=4-4, to=2-4]
	\arrow["s", hook', from=3-2, to=1-2]
	\arrow[hook', from=4-4, to=3-2]
	\arrow["s", hook', from=5-2, to=3-2]
	\arrow[hook', from=2-4, to=1-2]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsOSxbMSwwLCJMIl0sWzEsMiwiSyJdLFsxLDQsImsiXSxbMywzLCJGXFxkYSBrKFxcYWxwaGEsIFMpIFxcaW50ZXJzZWN0IEsiXSxbMywxLCJrKFxcYWxwaGEsIFMpIl0sWzAsMCwiXFxhbHBoYVxcaW4iXSxbMCwyLCJmXFxpbiBLW3hdIl0sWzQsMywiZlxcaW4gRlt4XSJdLFs0LDEsIlxcbmkgXFxhbHBoYSJdLFsyLDMsInMiLDIseyJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6InRvcCJ9fX1dLFszLDQsInMiLDIseyJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6InRvcCJ9fX1dLFsxLDAsInMiLDAseyJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6ImJvdHRvbSJ9fX1dLFszLDEsIiIsMSx7InN0eWxlIjp7InRhaWwiOnsibmFtZSI6Imhvb2siLCJzaWRlIjoiYm90dG9tIn19fV0sWzIsMSwicyIsMCx7InN0eWxlIjp7InRhaWwiOnsibmFtZSI6Imhvb2siLCJzaWRlIjoiYm90dG9tIn19fV0sWzQsMCwiIiwyLHsic3R5bGUiOnsidGFpbCI6eyJuYW1lIjoiaG9vayIsInNpZGUiOiJib3R0b20ifX19XV0=)


- Let $f(x) \da \min_{\alpha, K}(x)$ be the minimal polynomial of $\alpha$ *over the intermediate extension* $K$, which by assumption is separable since $L/K$ is separable.
  - So $f\in K[x]$, and letting $S$ be the finite set of coefficients of $f$, $S \subseteq K$.
  - Note that each coefficient $s\in S$ is separable over $k$ since $K/k$ is separable by assumption.
- Set $F\da k(\alpha, S) \intersect K$.
  Note $K/k$ is separable and $F \subseteq K$, so $F/k$ is separable.
- Moreover $k(\alpha, S)/F$ is separable, since the minimal polynomial of $\alpha$ over $F$ is still $f$. 
- Now $k(\alpha, S) / F /K$ is a tower of finite extensions where $k(\alpha, S)/F$ and $F/k$ are separable, so this reduces to the finite case.


:::

:::{.proposition title="Separability has the compositing property"}
$E/k$ and $F/k$ are separable $\iff$ $EF/k$ is separable.
:::

:::{.proof title="?"}
$\impliedby$:
Separability always descends to subfields, and $E \leq EF, F\leq EF$.

$\implies$:

- Write $E = k(S)$ for some finite set $S$. 
  Then $EF = F(S)$.
- Use that $k(S)/k$ is separable iff $s\in S$ is a separable element for all $s$.
  - Since $E/k$ is separable, each $s\in S$ is separable over $k$.
- Since $F/k$ is separable, each $s\in S$ is separable over $F$.
- So $F(S)/F$ is separable.
- Now use the tower $F(S)/F/k$ to obtain $F(S)/k$ separable, which is $EF/k$.

:::


## Galois Extensions

:::{.definition title="Galois Extension and Galois Group"}
Let $L/k$ be a finite field extension.
The following are equivalent:

- \( L/k \) is a **Galois extension**.
- $L$ is normal, and separable.
- The fixed field $L^H$ of $H\da \mathrm{Aut}(L/k)$ is exactly $k$.
- $L$ is the splitting field of a separable polynomial $p\in K[x]$.
- $L$ is a finite separable splitting field of an irreducible polynomial.
- There is a numerical equality:
\[
\size \Aut_{\Fieldsover{k}} (L) = [L: k] = \ts{ L: k}
,\]
  where $\ts{E:F}$ is the number of isomorphisms to any field lifting $\id_F$:

![figures/2021-08-09_22-29-40.png](figures/2021-08-09_22-29-40.png)

In this case, we define the **Galois group** as 
\[
\Gal(L/k) \definedas \Aut_{\Fieldsover{k}} (L/k)
.\]
:::

:::{.fact}
For $L/k$ algebraic and $\ch k = 0$, $L/k$ is Galois $\iff L/k$ is normal.
:::

:::{.proposition title="Galois is upper transitive, characterization of when lower transitivity holds"}
If $L/k$ is Galois, then $L/F$ is **always** Galois.
Moreover, $F/k$ is Galois if and only if \( \Gal(L/F) \normal \Gal(L/k) \)

\begin{tikzcd}
	{L} \\
	\\
	{F} \\
	\\
	{k}
	\arrow["{\text{Galois}}", from=1-1, to=5-1, curve={height=-18pt}, no head]
	\arrow["{\text{Galois}}", from=5-1, to=3-1, curve={height=-12pt}, squiggly, no head]
	\arrow["{\text{Galois}}"', from=1-1, to=3-1, curve={height=12pt}, dashed, no head]
\end{tikzcd}

> [Link to diagram](https://q.uiver.app/?q=WzAsMyxbMCwwLCJMIl0sWzAsMiwiRiJdLFswLDQsImsiXSxbMCwyLCJcXHRleHR7R2Fsb2lzfSIsMCx7ImN1cnZlIjotMywic3R5bGUiOnsiaGVhZCI6eyJuYW1lIjoibm9uZSJ9fX1dLFsyLDEsIlxcdGV4dHtHYWxvaXN9IiwwLHsiY3VydmUiOi0yLCJzdHlsZSI6eyJib2R5Ijp7Im5hbWUiOiJzcXVpZ2dseSJ9LCJoZWFkIjp7Im5hbWUiOiJub25lIn19fV0sWzAsMSwiXFx0ZXh0e0dhbG9pc30iLDIseyJjdXJ2ZSI6Miwic3R5bGUiOnsiYm9keSI6eyJuYW1lIjoiZGFzaGVkIn0sImhlYWQiOnsibmFtZSI6Im5vbmUifX19XV0=)

In this case, 
\[
\Gal(F/k) \cong \frac{\Gal(L/k)}{\Gal(L/F)}
.\]

:::

:::{.proposition title="?"}
Let $L/K/k$ with $L/k$ Galois. Then
\[
K/k \text{ is Galois } \iff \Gal(L/K)\normal \Gal(L/k)
,\]
and moreover $\Gal(K/k) = G$.
:::

:::{.proof title="?"}
\envlist

- Note separability is distinguished, so $K/k$ is separable.
- $K/k$ is Galois $\iff$ $F/k$ is normal (since we already have separability).
- $\iff \sigma(K) = K$ for all $\sigma\in G$
- $\iff \sigma H \sigma\inv = H$ for all $\sigma \in G$.

So $H$ is normal and $G/H$ is a group.
For the isomorphism, take 
\[
\rho: \Gal(L/k) &\to \Gal(K/k) \\
\rho &\mapsto \ro{\rho}{K}
.\]
This is well-defined since by normality $\sigma(K) = K$.
Any $f\in \ker \rho$ is the identity on $K$, so $f\in \Gal(L/K)$ and $\ker \phi = H$.
Since $L/K$ is Galois, every $f\in \Gal(K/k)$ lifts to $\Gal(L/k)$, making $\rho$ surjective.

:::

:::{.example title="?"}
\envlist

- $\QQ(\zeta_3, 2^{1/3})$ is normal but $\QQ(2^{1/3})$ is not since the irreducible polynomial $x^3 - 2$ has only one root in it.
- $\QQ(2^{1/3})$ is not Galois since its automorphism group is too small (only of size 1 instead of 3?).
- $\QQ(2^{1/4})$ is not Galois since its automorphism group is too small (only of size 2 instead of 4).
  However, the intermediate extensions $\QQ(2^{1/4}) / \QQ(2^{1/2})$ and $\QQ(\sqrt 2) / \QQ$ are Galois since they are quadratic.
  Slogan: "Being Galois is not transitive in towers."
- A quadratic extension that is not Galois: $\SF(x^2 + y) \in \FF_2(y)[x]$, which factors as $(x - \sqrt{y})^2$, making the extension not separable.
:::



## Fundamental Theorem of Galois Theory

:::{.theorem title="Fundamental Theorem of Galois Theory"}
Let $L/k$ be a Galois extension, then there is a correspondence:
\[
\correspond{\text{Subgroups } H \leq \Gal(L/k)}
&\mapstofrom
\correspond{\text{Fields }  F \text{ such}\\ \text{that } L/F/k} \\
H &\rightarrow \correspond{E^H \definedas ~\text{The fixed field of $H$}} \\
\correspond{\Gal(L/F) \definedas \theset{ \sigma \in \Gal(L/k) \suchthat \sigma(F) = F}} &\leftarrow F
\]

- This is contravariant with respect to subgroups/subfields.

- $[F: k] = [G: H]$, so degrees of extensions over the base field correspond to indices of subgroups.

- $[K : F] = \abs{H}$

- $L/F$ is Galois and $Gal(K/F) = H$

- $F/k$ is Galois $\iff H$ is normal, and $\Gal(F/k) = \Gal(L/k)/H$.

- The compositum $F_1 F_2$ corresponds to $H_1 \intersect H_2$.

- The subfield $F_1 \intersect F_2$ corresponds to $H_1 H_2$.

:::


:::{.remark}
A trick for remembering the degree/index correspondence:

\begin{tikzcd}
	K &&&& 1 \\
	\\
	E &&&& {H \da \Gal(K/E)\hspace{4em}} \\
	\\
	F &&&& {G \da \Gal(K/F)\hspace{4em}}
	\arrow["{[E:F]}", hook, from=5-1, to=3-1]
	\arrow["{[K:E]}", hook, from=3-1, to=1-1]
	\arrow[""{name=0, anchor=center, inner sep=0}, "{[K:F]}"', curve={height=30pt}, hook, from=5-1, to=1-1]
	\arrow["{[H:1]}"', hook, from=1-5, to=3-5]
	\arrow["{[G:H]}"', hook, from=3-5, to=5-5]
	\arrow["{[G:1]}", curve={height=-30pt}, hook, from=1-5, to=5-5]
	\arrow["{\Gal(K/\wait)}"', shift right=5, shorten <=18pt, Rightarrow, from=0, to=3-5]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsNixbMCwyLCJFIl0sWzAsMCwiSyJdLFswLDQsIkYiXSxbNCwwLCIxIl0sWzQsMiwiSCBcXGRhIFxcR2FsKEsvRSlcXGhzcGFjZXs0ZW19Il0sWzQsNCwiRyBcXGRhIFxcR2FsKEsvRilcXGhzcGFjZXs0ZW19Il0sWzIsMCwiW0U6Rl0iLDAseyJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6InRvcCJ9fX1dLFswLDEsIltLOkVdIiwwLHsic3R5bGUiOnsidGFpbCI6eyJuYW1lIjoiaG9vayIsInNpZGUiOiJ0b3AifX19XSxbMiwxLCJbSzpGXSIsMix7ImN1cnZlIjo1LCJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6InRvcCJ9fX1dLFszLDQsIltIOjFdIiwyLHsic3R5bGUiOnsidGFpbCI6eyJuYW1lIjoiaG9vayIsInNpZGUiOiJ0b3AifX19XSxbNCw1LCJbRzpIXSIsMix7InN0eWxlIjp7InRhaWwiOnsibmFtZSI6Imhvb2siLCJzaWRlIjoidG9wIn19fV0sWzMsNSwiW0c6MV0iLDAseyJjdXJ2ZSI6LTUsInN0eWxlIjp7InRhaWwiOnsibmFtZSI6Imhvb2siLCJzaWRlIjoidG9wIn19fV0sWzgsNCwiXFxHYWwoSy9cXHdhaXQpIiwyLHsib2Zmc2V0Ijo1LCJzaG9ydGVuIjp7InNvdXJjZSI6MjB9fV1d)

:::


:::{.theorem title="Splitting + Perfect implies Galois"}
\envlist

- If $\ch k = 0$ or $k$ is finite, then $k$ is perfect.

- $k = \CC,\RR, \QQ, \FF_p$ are perfect, so any finite normal extension is Galois.

- Every splitting field of a polynomial over a perfect field is Galois.
:::

:::{.proposition title="Composite Extensions"}
If $F/k$ is finite and Galois and $L/k$ is arbitrary, then $FL/L$ is Galois and
\[
\Gal(FL/L) = \Gal(F / F\intersect L) \subset \Gal(F/k)
.\]
:::

## Quadratic Extensions

:::{.proposition title="Classification of quadratic extensions"}
If $\FF$ is a field with $\ch(\FF)\neq 2$ and $E_{/\FF}$ is a degree 2 extension, then $E$ is Galois and $E = F(\sqrt{a})$ for some squarefree $a\in \FF$.
:::

:::{.corollary title="Quadratic extensions of rationals"}
If $E_{/\QQ}$ is a quadratic extension, $E = \QQ(\sqrt q)$ for some $q\in \QQ$ squarefree.
Explicitly, use the primitive element theorem to write $E = \QQ(\alpha)$, let $f$ be the minimal polynomial, then take $q=b^2-4ac$.
One can do slightly better by writing $b^2-4ac = a/b$ so that $\sqrt{b^2-4ac}=\sqrt{ab}/b$ and taking $q=ab$.
:::

:::{.proposition title="?"}
For $\FF_p$ a finite field of prime order, all quadratic extensions $E/\FF_p$ are isomorphic.
:::

# Distinguished Classes

> See <http://math.wsu.edu/students/jstreipel/notes/galoistheory.pdf>

:::{.definition title="Distinguished Classes"}
A collection of field extensions $\mathcal{S}$ is **distinguished** iff

1. (Transitive property) For any tower $L/K/k$, the extension $L/k \in \mathcal{S} \iff L/K \in \mcs$ (upper transitivity) and $K/k\in \mathcal{S}$ (lower transitivity):

\begin{tikzcd}
	L &&&& L \\
	\\
	K && \iff && K \\
	\\
	k &&&& k
	\arrow[hook, from=5-1, to=3-1]
	\arrow[hook, from=3-1, to=1-1]
	\arrow[hook, from=5-5, to=3-5]
	\arrow[hook, from=3-5, to=1-5]
	\arrow[color={rgb,255:red,214;green,92;blue,92}, curve={height=18pt}, dashed, hook, from=5-1, to=1-1]
	\arrow[color={rgb,255:red,214;green,92;blue,92}, curve={height=18pt}, dashed, hook, from=5-5, to=3-5]
	\arrow[color={rgb,255:red,214;green,92;blue,92}, curve={height=18pt}, dashed, hook, from=3-5, to=1-5]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsNyxbMCw0LCJrIl0sWzAsMiwiSyJdLFswLDAsIkwiXSxbNCw0LCJrIl0sWzQsMiwiSyJdLFs0LDAsIkwiXSxbMiwyLCJcXGlmZiJdLFswLDEsIiIsMCx7InN0eWxlIjp7InRhaWwiOnsibmFtZSI6Imhvb2siLCJzaWRlIjoidG9wIn19fV0sWzEsMiwiIiwwLHsic3R5bGUiOnsidGFpbCI6eyJuYW1lIjoiaG9vayIsInNpZGUiOiJ0b3AifX19XSxbMyw0LCIiLDAseyJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6InRvcCJ9fX1dLFs0LDUsIiIsMCx7InN0eWxlIjp7InRhaWwiOnsibmFtZSI6Imhvb2siLCJzaWRlIjoidG9wIn19fV0sWzAsMiwiIiwyLHsiY3VydmUiOjMsImNvbG91ciI6WzAsNjAsNjBdLCJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6InRvcCJ9LCJib2R5Ijp7Im5hbWUiOiJkYXNoZWQifX19XSxbMyw0LCIiLDIseyJjdXJ2ZSI6MywiY29sb3VyIjpbMCw2MCw2MF0sInN0eWxlIjp7InRhaWwiOnsibmFtZSI6Imhvb2siLCJzaWRlIjoidG9wIn0sImJvZHkiOnsibmFtZSI6ImRhc2hlZCJ9fX1dLFs0LDUsIiIsMix7ImN1cnZlIjozLCJjb2xvdXIiOlswLDYwLDYwXSwic3R5bGUiOnsidGFpbCI6eyJuYW1lIjoiaG9vayIsInNpZGUiOiJ0b3AifSwiYm9keSI6eyJuYW1lIjoiZGFzaGVkIn19fV1d)

2. (Lifting property) Lifts of distinguished extensions are distinguished: $K/k\in \mathcal{S}$ and $L/k$ any extension $\implies LK/L \in \mathcal{S}$:

\begin{tikzcd}
	& LK \\
	L && K \\
	& k
	\arrow[draw={rgb,255:red,214;green,92;blue,92}, dashed, hook, from=3-2, to=2-3]
	\arrow[hook', from=3-2, to=2-1]
	\arrow["\therefore", draw={rgb,255:red,214;green,92;blue,92}, dashed, hook, from=2-1, to=1-2]
	\arrow[hook, from=2-3, to=1-2]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsNCxbMSwyLCJrIl0sWzIsMSwiSyJdLFswLDEsIkwiXSxbMSwwLCJMSyJdLFswLDEsIiIsMCx7ImNvbG91ciI6WzAsNjAsNjBdLCJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6InRvcCJ9LCJib2R5Ijp7Im5hbWUiOiJkYXNoZWQifX19XSxbMCwyLCIiLDIseyJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6ImJvdHRvbSJ9fX1dLFsyLDMsIlxcdGhlcmVmb3JlIiwwLHsiY29sb3VyIjpbMCw2MCw2MF0sInN0eWxlIjp7InRhaWwiOnsibmFtZSI6Imhvb2siLCJzaWRlIjoidG9wIn0sImJvZHkiOnsibmFtZSI6ImRhc2hlZCJ9fX1dLFsxLDMsIiIsMCx7InN0eWxlIjp7InRhaWwiOnsibmFtZSI6Imhvb2siLCJzaWRlIjoidG9wIn19fV1d)


3. (Compositing property)
Whenever $L/k, K/k\in \mcs$, the amalgam $LK/k \in \mcs$ as well:

\begin{tikzcd}
	& LK \\
	L && K \\
	& k
	\arrow[draw={rgb,255:red,214;green,92;blue,92}, hook, from=3-2, to=2-3]
	\arrow[draw={rgb,255:red,214;green,92;blue,92}, hook', from=3-2, to=2-1]
	\arrow[draw={rgb,255:red,214;green,92;blue,92}, hook, from=2-1, to=1-2]
	\arrow[hook, from=2-3, to=1-2]
	\arrow["\therefore", color={rgb,255:red,214;green,92;blue,92}, dashed, from=3-2, to=1-2]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsNCxbMSwyLCJrIl0sWzIsMSwiSyJdLFswLDEsIkwiXSxbMSwwLCJMSyJdLFswLDEsIiIsMCx7ImNvbG91ciI6WzAsNjAsNjBdLCJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6InRvcCJ9fX1dLFswLDIsIiIsMix7ImNvbG91ciI6WzAsNjAsNjBdLCJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6ImJvdHRvbSJ9fX1dLFsyLDMsIiIsMCx7ImNvbG91ciI6WzAsNjAsNjBdLCJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6InRvcCJ9fX1dLFsxLDMsIiIsMCx7InN0eWxlIjp7InRhaWwiOnsibmFtZSI6Imhvb2siLCJzaWRlIjoidG9wIn19fV0sWzAsMywiXFx0aGVyZWZvcmUiLDAseyJjb2xvdXIiOlswLDYwLDYwXSwic3R5bGUiOnsiYm9keSI6eyJuYW1lIjoiZGFzaGVkIn19fSxbMCw2MCw2MCwxXV1d)


> One is supposed to think of $LK/L$ as a "lift" of $K/k$.

:::

:::{.example title="of distinguished classes"}
The following classes of extensions are distinguished:

- Algebraic.
- Finite.
- Separable.
- Purely inseparable.
- Finitely generated.
- Solvable.

:::

:::{.warnings}
Normal extensions are *not* distinguished, since they fail the forward implication for (lower) transitivity.
However, they do have the (forward implication) upper transitive, lifting, and compositing properties.

As a consequence, Galois extensions are also not distinguished.
:::

:::{.fact title="Normal/Algebraic/Galois extensions are upper transitive"}
For $L/F/k$: $L/k$ normal/algebraic/Galois $\implies L/F$ normal/algebraic/Galois.
:::

### Algebraic Extensions

:::{.proposition title="Transitivity of algebraic extensions, forward implication"}
If $L/K/k$ (not necessarily finite) with $L/K$ and $K/k$ both algebraic, then $L/k$ is algebraic.
:::

:::{.proof title="?"}
\envlist

- We want to show every $\alpha \in L$ is algebraic over $k$, and it suffices to show $\alpha$ is algebraic over some finite subextension $k(S)$.
- Pick $\alpha\in L$, then $\alpha$ is algebraic over $K$ by assumption, so it is a root of some $f\in K[x]$.
- Let $S$ be the finitely many coefficients of $f$, then $\alpha$ is algebraic over $k(S)$.
- Note that $k(S)/k$ is finite and thus algebraic, and $k(S,\alpha)/k(s)$ is finite and also algebraic, so we're reduced to the finite case.
- It suffices to show $k(S, \alpha)/k(s)/k$ is finite, which follows from multiplicativity of degrees.
:::


:::{.remark}
If $L/K/k$ with $\alpha$ algebraic over $L$, then $\alpha$ is algebraic over $K$ and $\min_{\alpha, L}$ divides $\min_{\alpha, K}$ (so minimal polynomials only get smaller in extensions).
:::


### Normal Extensions

:::{.corollary title="Normality satisfies the lifting property"}
$E_1/k$ normal and $E_2/k$ normal $\implies E_1E_2/k$ normal and $E_1 \intersect E_2 / k$ normal.

\begin{tikzcd}
	&& {E_1 E_2} \\
	\\
	{E_1} &&&& {E_2} \\
	&& {E_1 \cap E_2} \\
	\\
	\\
	&& {k}
	\arrow["{\text{normal}}", from=3-5, to=7-3]
	\arrow[from=4-3, to=7-3, dashed, no head, "\text{normal}", near start]
	\arrow["{\text{normal}}"', from=3-1, to=7-3]
	\arrow[from=1-3, to=3-1, no head]
	\arrow[from=1-3, to=3-5, no head]
	\arrow[from=1-3, to=4-3, no head]
	\arrow[from=1-3, to=7-3, curve={height=25pt}, dashed, no head, "\text{normal}"', near start]
	\arrow[from=3-1, to=4-3, no head]
	\arrow[from=4-3, to=3-5, no head]
\end{tikzcd}

> [Link to diagram](https://q.uiver.app/?q=WzAsNSxbMiwwLCJFXzEgRV8yIl0sWzAsMiwiRV8xIl0sWzQsMiwiRV8yIl0sWzIsMywiRV8xIFxcY2FwIEVfMiJdLFsyLDYsImsiXSxbMiw0LCJcXHRleHR7bm9ybWFsfSJdLFszLDQsIiIsMix7InN0eWxlIjp7ImJvZHkiOnsibmFtZSI6ImRhc2hlZCJ9LCJoZWFkIjp7Im5hbWUiOiJub25lIn19fV0sWzEsNCwiXFx0ZXh0e25vcm1hbH0iLDJdLFswLDEsIiIsMSx7InN0eWxlIjp7ImhlYWQiOnsibmFtZSI6Im5vbmUifX19XSxbMCwyLCIiLDEseyJzdHlsZSI6eyJoZWFkIjp7Im5hbWUiOiJub25lIn19fV0sWzAsMywiIiwxLHsic3R5bGUiOnsiaGVhZCI6eyJuYW1lIjoibm9uZSJ9fX1dLFswLDQsIiIsMSx7ImN1cnZlIjozLCJzdHlsZSI6eyJib2R5Ijp7Im5hbWUiOiJkYXNoZWQifSwiaGVhZCI6eyJuYW1lIjoibm9uZSJ9fX1dLFsxLDMsIiIsMSx7InN0eWxlIjp7ImhlYWQiOnsibmFtZSI6Im5vbmUifX19XSxbMywyLCIiLDEseyJzdHlsZSI6eyJoZWFkIjp7Im5hbWUiOiJub25lIn19fV1d)

:::

#### Issues with Normal Towers


:::{.example title="Normal extensions are not transitive: failure of lower transitivity, forward implication"}
One can similarly produce towers where the total extension is normal but the lower iterate is not normal: take
\[
L/K/k \da \QQ(2^{1\over 3}, \zeta_3) / \QQ(2^{1\over 3}) / \QQ
.\]
Now $K/k$ isn't normal, since $\Gal(L/k) = S_3$ but $\Gal(L/K) = \ZZ/2 \not\normal S_3$.

Another example: let $L/k$ be any algebraic extension that isn't normal, and take $N_k$ to be the normal closure to get $N_k/L$. 
Concretely, $N_\QQ / \QQ(2^{1\over 3})/\QQ$ works.
:::

:::{.example title="Normal extensions are not transitive: failure of reverse implication"}
One can produce towers of successively normal extensions whose total extension is not normal in a cheap way:
take 
\[
L/K/k \da \QQ(2^{1\over 4}) / \QQ(2^{1\over 2}) / \QQ
.\]
Each iterate is normal since it's quadratic, but the overall extension misses complex roots and is thus not normal.
:::

:::{.proposition title="Normal extensions are upper transitive, forward implication"}
For $L/k$ finite,

\begin{tikzcd}
	L &&&& L \\
	\\
	K && \implies && K \\
	\\
	k &&&& k
	\arrow[from=3-1, to=1-1]
	\arrow[from=5-1, to=3-1]
	\arrow["{\text{Normal}}"', color={rgb,255:red,214;green,92;blue,92}, curve={height=24pt}, dashed, from=5-1, to=1-1]
	\arrow[from=5-5, to=3-5]
	\arrow[from=3-5, to=1-5]
	\arrow["{\text{Normal}}"', color={rgb,255:red,214;green,92;blue,92}, curve={height=18pt}, dashed, from=3-5, to=1-5]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsNyxbMCwwLCJMIl0sWzAsMiwiSyJdLFswLDQsImsiXSxbMiwyLCJcXGltcGxpZXMiXSxbNCwwLCJMIl0sWzQsMiwiSyJdLFs0LDQsImsiXSxbMSwwXSxbMiwxXSxbMiwwLCJcXHRleHR7Tm9ybWFsfSIsMix7ImN1cnZlIjo0LCJjb2xvdXIiOlswLDYwLDYwXSwic3R5bGUiOnsiYm9keSI6eyJuYW1lIjoiZGFzaGVkIn19fSxbMCw2MCw2MCwxXV0sWzYsNV0sWzUsNF0sWzUsNCwiXFx0ZXh0e05vcm1hbH0iLDIseyJjdXJ2ZSI6MywiY29sb3VyIjpbMCw2MCw2MF0sInN0eWxlIjp7ImJvZHkiOnsibmFtZSI6ImRhc2hlZCJ9fX0sWzAsNjAsNjAsMV1dXQ==)

:::

:::{.proof title="Finite case"}
\envlist

- Use the fact that for finite extensions, $L/k$ is normal and separable $\iff L$ is the splitting field of a separable polynomial $f\in k[x]$.
- Now regard $f$ as a polynomial in $K[x]$; then $L$ is still the splitting field of $f$ over $K$, done.

Alternatively,

- Let $\alpha\in L$ be a root of $f\in K[x]$ with $f$ irreducible, it suffices to show all roots of $f$ are in $L$.
- Let $m\in K[x]$ be the minimal polynomial of $\alpha$ over $K$, and let $m'\in k[x]$ be the minimal polynomial of $\alpha$ over $k$.
- Since $L/k$ is normal and $\alpha\in L$, $m'$ splits in $L$.
- Minimal polynomials are divisible in towers, so $m$ divides $m'$.
  Since $m'$ splits in $L$, so must $m$.

:::

:::{.proof title="General case"}
\envlist

- Suppose $L/K/k$ with $L/k$ normal, we want to show $L/K$ is normal.
- Use the embedding characterization, it suffices to show that every embedding $\sigma: L\embeds \bar{K}$ satisfies $\im \sigma = L$:

\begin{tikzcd}
	&& {\bar{K} = \bar{k}} \\
	\\
	L && {\sigma(L)} \\
	\\
	K && K \\
	\\
	k && k
	\arrow[Rightarrow, no head, from=7-1, to=7-3]
	\arrow[hook, from=7-1, to=5-1]
	\arrow[hook, from=7-3, to=5-3]
	\arrow[hook, from=5-3, to=3-3]
	\arrow[hook, from=5-1, to=3-1]
	\arrow[hook, from=3-3, to=1-3]
	\arrow["\sigma", hook, from=3-1, to=1-3]
	\arrow["\sigma", hook, from=3-1, to=3-3]
	\arrow[Rightarrow, no head, from=5-1, to=5-3]
\end{tikzcd}

> [Link to Diagram](https://q.uiver.app/?q=WzAsNyxbMCw2LCJrIl0sWzAsNCwiSyJdLFswLDIsIkwiXSxbMiwyLCJcXHNpZ21hKEwpIl0sWzIsNCwiSyJdLFsyLDYsImsiXSxbMiwwLCJcXGJhcntLfSA9IFxcYmFye2t9Il0sWzAsNSwiIiwwLHsibGV2ZWwiOjIsInN0eWxlIjp7ImhlYWQiOnsibmFtZSI6Im5vbmUifX19XSxbMCwxLCIiLDIseyJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6InRvcCJ9fX1dLFs1LDQsIiIsMCx7InN0eWxlIjp7InRhaWwiOnsibmFtZSI6Imhvb2siLCJzaWRlIjoidG9wIn19fV0sWzQsMywiIiwwLHsic3R5bGUiOnsidGFpbCI6eyJuYW1lIjoiaG9vayIsInNpZGUiOiJ0b3AifX19XSxbMSwyLCIiLDIseyJzdHlsZSI6eyJ0YWlsIjp7Im5hbWUiOiJob29rIiwic2lkZSI6InRvcCJ9fX1dLFszLDYsIiIsMCx7InN0eWxlIjp7InRhaWwiOnsibmFtZSI6Imhvb2siLCJzaWRlIjoidG9wIn19fV0sWzIsNiwiXFxzaWdtYSIsMCx7InN0eWxlIjp7InRhaWwiOnsibmFtZSI6Imhvb2siLCJzaWRlIjoidG9wIn19fV0sWzIsMywiXFxzaWdtYSIsMCx7InN0eWxlIjp7InRhaWwiOnsibmFtZSI6Imhvb2siLCJzaWRlIjoidG9wIn19fV0sWzEsNCwiIiwxLHsibGV2ZWwiOjIsInN0eWxlIjp7ImhlYWQiOnsibmFtZSI6Im5vbmUifX19XV0=)

- Now just use the fact that $\bar{k} = \bar{K}$, and since $k\subseteq K$, any $K\dash$morphism is also a $k\dash$morphism.
- Since $L/k$ is normal, $\sigma(L) = L$ and $L/K$ is thus normal.
:::

