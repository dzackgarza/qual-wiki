# Convergence of Functions

## Fall 2021 #4 #work
Prove that the sequence $\left(1+\frac{z}{n}\right)^{n}$ converges uniformly to $e^{z}$ on compact subsets of $\mathbb{C}$. 

> Hint: $e^{\pi \log w_{n}}=w_{n}^{n}$ and $e^{x}$ is uniform continuous on compact subsets of $\mathbb{C}$.

## Tie's Extra Questions: Spring 2015 #work

Assume $f_n \in H(\Omega)$ is a sequence of holomorphic functions on the region $\Omega$ that are uniformly bounded on compact subsets and $f \in H(\Omega)$ is such that the set
$\displaystyle \{z \in \Omega: \lim_{n \rightarrow \infty} f_n(z) = f(z) \}$
has a limit point in $\Omega$. Show that $f_n$ converges to $f$ uniformly on compact subsets of $\Omega$.

## Spring 2021, Spring 2015 Extras # 6 #work

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

- Let $K$ be compact, then choose $\gamma$ enclosing $K$.
  Let $R$ be the radius of the disc enclosed by $\gamma$.

- Apply Cauchy's formula to the function $F_n(z) \da f_n(z) - f(z)$:
\[
F(z) 
&= {1\over 2\pi i} \int_\gamma { F(\xi) \over z-\xi} \dxi
\implies \abs{f_n(z) - f(z) } \\
&\leq {1\over 2\pi }\int_\gamma \abs{f_n(\xi) - f(\xi) \over z-\xi} \dxi \\
&\leq {1\over 2\pi} \int_\gamma {\abs{ f_n(\xi) - f(\xi) } \over 
2R} \dxi \\
&\leq {1\over 2\pi\cdot 2R} \int_\gamma {\abs{ f_n(\xi) - f(\xi) } }\dxi \\
&\leq {1\over 2\pi\abs{\abs{z} - \abs \xi}} \cdot \eps \\
.\]



:::


## Spring 20202 HW 2 #  2.6.10 #work

Can every continuous function on $\bar \DD$ be uniformly approximated by polynomials in the variable $z$?

> Hint: compare to Weierstrass for the real interval.


:::{.solution}
No: polynomials are holomorphic and the uniform limit of holomorphic functions is holomorphic.
However, $f(z) \da \bar{z}$ is continuous on $\bar\DD$ but not holomorphic.
:::


## Spring 20202 HW 2 #  5 #work
Assume $f$ is continuous in the region $\theset{x+iy \suchthat x\geq x_0, ~ 0\leq y \leq b}$, and the following limit exists independent of $y$:
\[
\lim_{x\to +\infty}f(x+iy) = A
.\]

Show that if $\gamma_x \definedas \theset{z = x+it \suchthat 0 \leq t \leq b}$, then
\[
\lim_{x\to +\infty} \int_{\gamma_x} f(z) \,dz = iAb
.\]
