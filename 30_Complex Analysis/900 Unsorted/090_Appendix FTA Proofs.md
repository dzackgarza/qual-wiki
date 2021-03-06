# Proofs of the Fundamental Theorem of Algebra

## Argument Principle 

:::{.proof title="using the argument principle"}
\envlist

- Let $P(z) = a_nz^n + \cdots + a_0$ and $g(z) = P'(z)/P(z)$, note $P$ is holomorphic
- Since $\lim_{\abs z \to \infty} P(z) = \infty$, there exist an $R>0$ such that $P$ has no roots in $\theset{\abs{z} \geq R}$.
- Apply the argument principle:
\begin{align*}
N(0) = {1\over 2\pi i} \oint_{\abs{\xi} = R} g(\xi) \,d\xi
.\end{align*}
- Check that $\lim_{\abs{z\to \infty}}zg(z) = n$, so $g$ has a simple pole at $\infty$
- Then $g$ has a Laurent series ${n\over z} + {c_2 \over z^2} + \cdots$
- Integrate term-by-term to get $N(0) = n$.
:::

## Rouche's Theorem

:::{.proof title="From Gamelin"}

![](figures/2021-12-10_18-02-14.png)

:::

:::{.proof title="using Rouche's theorem"}

![](2021-07-29_20-41-18.png)
![](2021-07-29_20-41-29.png)

- Let $P(z) = a_nz^n + \cdots + a_0$
- Set $f(z) = a_n z^n$ and $g(z) = P(z) - f(z) = a_{n-1}z^{n-1} + \cdots + a_0$, so $f+g = P$.
- Choose $R > \max\qty{ { \abs{a_{n-1}} + \cdots + \abs{a_0} \over \abs{a_n} }, 1}$, then

\begin{align*}
|g(z)| 
&\definedas |a_{n-1}z^{n-1} + \cdots + a_1 z + a_0 | \\
&\leq |a_{n-1}z^{n-1}| + \cdots + |a_1 z| + |a_0 | \quad\text{by the triangle inequality} \\
&= |a_{n-1}|\cdot |z^{n-1}| + \cdots + |a_1|\cdot| z| + |a_0 | \\
&=  |a_{n-1}|\cdot R^{n-1} + \cdots + |a_1| R + |a_0 | \\
&\leq |a_{n-1}|\cdot R^{n-1}+|a_{n-2}|\cdot R^{n-1} + \cdots + |a_1| \cdot R^{n-1} + |a_0 |\cdot R^{n-1} \quad\text{since } R>1 \implies R^{a+b} \geq R^a \\
&= R^{n-1} \left( |a_{n-1}| + |a_{n-2}| + \cdots + |a_1| + |a_0| \right) \\
&\leq R^{n-1} \left( |a_n|\cdot R \right) \quad\text{by choice of } R   \\
&= R^{n} |a_n| \\
&= |a_n z^n| \\
&\definedas  |f(z)|
\end{align*}

- Then $a_n z^n$ has $n$ zeros in $\abs{z} < R$, so $f+g$ also has $n$ zeros.

:::

## Liouville's Theorem

:::{.proof title="?"}

![](figures/2021-12-14_16-58-33.png)

:::

:::{.proof title="from Gamelin"}

![](figures/2021-12-10_19-52-51.png)

![](figures/2021-12-10_19-52-58.png)

:::

:::{.proof title="using Liouville's theorem"}
\envlist

- Suppose $p$ is nonconstant and has no roots, then ${1\over p}$ is entire.
  We will show it is also bounded and thus constant, a contradiction.
- Write $p(z) = z^n \left(a_n + \frac{a_{n-1}}{z}+\dots+\frac{a_{0}}{z^{n}}\right)$
- Outside a disc:
  - Note that $p(z) \converges{z\to \infty }\to \infty$. so there exists an $R$ large enough such that $\abs{p(z)} \geq {1\over A}$ for any fixed chosen constant $A$.
  - Then $\abs{ 1/p(z)} \leq A$ outside of $\abs{z} >R$, i.e. $1/p(z)$ is bounded there.
- Inside a disc:
  - $p$ is continuous with no roots and thus must be bounded below on $\abs{z} < R$.
  - $p$ is entire and thus continuous, and since $\bar{D}_r(0)$ is a compact set, $p$ achieves a min $A$ there
  - Set $C \da \min(A, B)$, then $\abs{p(z)} \geq C$ on all of $\CC$ and thus $\abs{1/p(z)} \leq C$ everywhere. 
  - So $1/p(z)$ is bounded an entire and thus constant by Liouville's theorem -- but this forces $p$ to be constant. $\contradiction$


:::

## Open Mapping Theorem

:::{.proof title="using the Open Mapping theorem"}
\envlist

- $p$ induces a continuous map $\CP^1 \to \CP^1$
- The continuous image of compact space is compact; 
- Since the codomain is Hausdorff space, the image is closed.
- $p$ is holomorphic and non-constant, so by the Open Mapping Theorem, the image is open.
- Thus the image is clopen in $\CP^1$.
- The image is nonempty, since $p(1) = \sum a_i \in \CC$
- $\CP^1$ is connected
- But the only nonempty clopen subset of a connected space is the entire space.
- So $p$ is surjective, and $p\inv(0)$ is nonempty.
- So $p$ has a root.

:::

## Generalized Liouville

:::{.theorem title="Generalized Liouville"}
If $X$ is a compact complex manifold,
any holomorphic $f:X\to \CC$ is constant.
:::

:::{.lemma title="?"}
If $f:X\to Y$ is a nonconstant holomorphic map between Riemann surfaces with $X$ compact, then

- $f$ must be surjective,
- $Y$ must be compact,
- $f\inv(q)$ is finite for all $q\in Y$,
- The branch and ramification loci consist of finitely many points.
:::

:::{.proof title="of FTA, using Generalized Liouville"}
Given a nonconstant $p\in \CC[x]$, regard it as a function $p: \PP^1(\CC) \to \PP^1(\CC)$ by extending so that $p(\infty) = \infty$.
Since $p$ is nonconstant, by the lemma $p$ is surjective, so there exists some $x\neq \infty$ in $\PP^1(\CC)$ with $p(x) = 0$.
:::
