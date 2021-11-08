# Convergence of Functions

## Exercises

- Show that a uniform limit of continuous functions is continuous. #work


## Fall 2021 #4 #work
Prove that the sequence $\left(1+\frac{z}{n}\right)^{n}$ converges uniformly to $e^{z}$ on compact subsets of $\mathbb{C}$. 

> Hint: $e^{\pi \log w_{n}}=w_{n}^{n}$ and $e^{x}$ is uniform continuous on compact subsets of $\mathbb{C}$.

## Tie's Extra Questions: Spring 2015 #work

Assume $f_n \in H(\Omega)$ is a sequence of holomorphic functions on the region $\Omega$ that are uniformly bounded on compact subsets and $f \in H(\Omega)$ is such that the set
$\displaystyle \{z \in \Omega: \lim_{n \rightarrow \infty} f_n(z) = f(z) \}$
has a limit point in $\Omega$. Show that $f_n$ converges to $f$ uniformly on compact subsets of $\Omega$.

## Tie's Extra Questions: Spring 2015 #work

Let $f_n, f$ be analytic functions on the unit disk ${\mathbb D}$.
Show that the following are equivalent.

(i) $f_n(z)$ converges to $f(z)$ uniformly on compact subsets in
$\mathbb D$.

(ii) $\int_{|z|= r} |f_n(z) - f(z)| \, |dz|$ converges to $0$ if
$0< r<1$.

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
