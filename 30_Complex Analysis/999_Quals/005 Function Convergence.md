# Function Convergence 

## Fall 2021.4 #completed

:::{.problem title="?"}
Prove that the sequence $\left(1+\frac{z}{n}\right)^{n}$ converges uniformly to $e^{z}$ on compact subsets of $\mathbb{C}$. 

> Hint: $e^{n \log w_{n}}=w_{n}^{n}$ and $e^{z}$ is uniform continuous on compact subsets of $\mathbb{C}$.

:::

:::{.solution}

Let $K$ be compact, where $z\in K\implies \abs{z} \leq R$ for some constant $R$. For the remainder of the problem, we only work in $K$.

:::{.claim}
$f_n(z) \da n\log(1 + {z\over n}) \to z$ uniformly.
:::

:::{.claim}
$f_n$ are uniformly bounded on $K$.
:::


:::{.claim}
$e^z$ is uniformly continuous on $K$.
:::


:::{.claim}
If $g_n\to g$ uniformly and $F$ is uniformly continuous, then $F \circ g_n \to F\circ g$ uniformly.
:::


Why these claims imply the result:

If $f_n(z)\to z$ uniformly, both are uniformly bounded, and $e^z$ is uniformly continuous, then $e^{f(z)}\to e^z$ uniformly.


:::{.proof title="Of first claim"}
We'll first show that for $w$ in a neighborhood of zero avoiding 1, there exists a constant $C$ such that
\[
\abs{ 1 - {\log(1+w) \over w} } \leq C\abs{w}
.\]
This follows from estimating the series expansion about $w=0$:
\[
\abs{ 1 - {\log(1+w) \over w} }
&= \abs{w\inv\sum_{k\geq 1} { (-w)^k \over k} } \\
&= \abs{\sum_{k\geq 2} {(-w)^{k-1} \over k} } \\
&\leq {\sum_{k\geq 2} {\abs{w}^{k-1} \over k} } \\
&= {\sum_{k\geq 1} {\abs{w}^{k} \over k+1} } \\
&\leq {\sum_{k\geq 1} {\abs{w}^{k} \over 2} } \\
&= {1\over 2}\qty{{1\over 1 - \abs w} - 1 } \\
&= {1\over 2}\abs{2} \qty{1\over 1 - \abs w} \\
&\leq C \abs{w}
,\]
using that ${1\over 1-x}$ is bounded in compact sets avoiding $x=1$.

We can now apply the $M\dash$test:
\[
\abs{n\log\qty{ 1 + {z\over n} } - z } 
&= \abs{z}\cdot \abs{
{{ \log\qty{1 + {z\over n}} \over {z\over n}} - 1}
} \\
&\leq \abs{z} \cdot C\abs{z\over n} \\
&\leq M\cdot C\qty{M\over n} \\
&= {CM^2 \over n}\\
&\convergesto{n\to\infty}0
.\]


:::


:::


## Tie's Extra Questions: Spring 2015 #work

:::{.problem title="?"}
Assume $f_n \in H(\Omega)$ is a sequence of holomorphic functions on the region $\Omega$ that are uniformly bounded on compact subsets and $f \in H(\Omega)$ is such that the set
$\displaystyle \{z \in \Omega: \lim_{n \rightarrow \infty} f_n(z) = f(z) \}$
has a limit point in $\Omega$. Show that $f_n$ converges to $f$ uniformly on compact subsets of $\Omega$.

:::

## Spring 2021, Spring 2015, Extras.6 #completed

:::{.problem title="?"}
Let $\ts{f_n}_{n=1}^\infty$ is a sequence of holomorphic functions on $\DD$ and $f$ is also holomorphic on $\DD$. 
Show that the following are equivalent:

- $f_n\to f$ uniformly on compact subsets of $\DD$.
- For $0 < r < 1$,
\[
\int_{\abs z = r} \abs{f_n(z) - f(z)} \abs{dz} \convergesto{n\to\infty}0
.\]
:::

:::{.solution}
$\implies$: 

- Fix $r \in (0, 1)$ and let $\gamma = \ts{\abs{z} = r}$.
  This is compact, so $f_n\to f$ uniformly on $\gamma$:
\[
\int_\gamma \abs{f_n(z) - f(z) } \dz 
&\leq\int_\gamma \sup_{w\in \gamma } \abs{f_n(w) - f(w) } \dz \\
&\leq\int_\gamma \norm{f_n(w) - f(w) }_{\infty} \dz \\
&= \norm{f_n(w) - f(w) }_{\infty} \int_\gamma \dz \\
&= \norm{f_n(w) - f(w) }_{\infty} \length(\gamma) \\
&\convergesto{n\to\infty} 0
.\]

$\impliedby$:

- Let $K$ be compact, then choose $\gamma$ enclosing but not intersecting $K$.
- Since $\gamma, K$ are disjoint compact sets, define $M \da \inf \ts{\abs{z-\xi} \st z\in K, \xi\in \gamma}$, the $0<M<\infty$.

- Apply Cauchy's formula to the function $F_n(z) \da f_n(z) - f(z)$:
\[
F(z) 
&= {1\over 2\pi i} \int_\gamma { F(\xi) \over z-\xi} \dxi \\
\implies \abs{f_n(z) - f(z) } 
&\leq {1\over 2\pi }\int_\gamma \abs{f_n(\xi) - f(\xi) \over z-\xi} \dxi \\
&\leq {1\over 2\pi} \int_\gamma {\abs{ f_n(\xi) - f(\xi) } \over 
M} \dxi \\
&\leq {1\over 2\pi M} \int_\gamma {\abs{ f_n(\xi) - f(\xi) } }\dxi \\
&\leq {1\over 2\pi M}\cdot \eps \\
&\convergesto{\eps\to 0}0
.\]
So given $\eps$, choose $n$ large enough to bound the integral as above. 
Then $\norm{f_n - f}_{\infty, K} \leq {\eps\over 2\pi M}$, so $f_n\to f$ uniformly on $K$.
:::

## Spring 2020 HW 2, Stein 2.6.10 #completed

:::{.problem title="?"}
Can every continuous function on $\bar \DD$ be uniformly approximated by polynomials in the variable $z$?

> Hint: compare to Weierstrass for the real interval.

> Note: $\abs{\dz} = \abs{\gamma'(t)}\dt$ for $\gamma$ a parameterization of the curve.

:::

:::{.solution}
No: polynomials are holomorphic and the uniform limit of holomorphic functions is holomorphic.
However, $f(z) \da \bar{z}$ is continuous on $\bar\DD$ but not holomorphic.
:::

## Spring 2020 HW 2.5 #completed

:::{.problem title="?"}
Assume $f$ is continuous in the region $\theset{x+iy \suchthat x\geq x_0, ~ 0\leq y \leq b}$, and the following limit exists independent of $y$:
\[
\lim_{x\to +\infty}f(x+iy) = A
.\]

Show that if $\gamma_x \definedas \theset{z = x+it \suchthat 0 \leq t \leq b}$, then
\[
\lim_{x\to +\infty} \int_{\gamma_x} f(z) \,dz = iAb
.\]
:::


:::{.solution}
The key insight:
\[
\int_\gamma A \dz 
&= \int_0^b A \cdot i \dt && z=x+it,\, \dz = i\dt \\
&=iA \int_0^b \dt \\
&= iAb
.\]

So now estimate the difference:
\[
\abs{
\int_{\gamma} f(z) \dz - iAB 
}
&= \abs{ \int_\gamma f(z) \dz - \int_\gamma A \dz} \\
&= \abs{ \int_\gamma \qty{ f(z) - A } \dz} \\
&\leq\int_\gamma \abs{ f(z) - A } \dz \\
&= \abs{f(z) - A} \cdot \length(\gamma_x \\
&\convergesto{x\to \infty}0
,\]
using that $x\to \infty$ forces $z\to \infty$ and $\length(\gamma_x) = b$ is constant.


:::

## Limiting curve variant #work


:::{.problem title="?"}
Let $0\leq \alpha \leq 2\pi$ be a fixed angle.
Suppose $f$ is continuous on the region $\Omega = \ts{\abs{z} \geq R, \Arg(z) \in [0, \alpha]}$ and $\lim_{z\to \infty} zf(z) = A$.
Show that
\[
\lim_{z\to \infty} \int_{\gamma_R} f(z) \dz = iA\alpha
,\]
where $\gamma_R \da \ts{ \abs{z} = R, \Arg(z) \in [0, \alpha]}$ is an arc.
:::


:::{.solution}
Key observation:
\[
iA\alpha = \int_\gamma {A\over z}\dz
.\]

:::


