---
order: 51
---

# Polynomials


## Spring 2019.4 #work

^047423

Let $f$ be a meromorphic function on the complex plane with the property that $|f(z)| \leq$ $M$ for all $|z|>R$, for some constants $M>0, R>0$.

Prove that $f(z)$ is a rational function, i.e., there exist polynomials $p, q$ so that $f=\frac{p}{q}$.

## Fall 2019.4 #work

^398dec

Let $f: \mathbb{C} \rightarrow \mathbb{C}$ be an injective analytic (also called univalent) function. Show that there exist complex numbers $a \neq 0$ and $b$ such that $f(z)=a z+b$.

## Tie's Extra Questions: Fall 2011

Let $f(z)$ be entire and assume that $f(z) \leq M |z|^2$ outside some
disk for some constant $M$. Show that $f(z)$ is a polynomial in $z$ of degree $\leq 2$.

## Tie's Extra Questions: Spring 2014


Suppose $f$ is entire and there exist $A, R >0$ and natural number $N$ such that $$|f(z)| \geq A |z|^N\ \text{for}\ |z| \geq R.$$ Show
that 

(i) 
$f$ is a polynomial and 

(ii) 
the degree of $f$ is at least $N$.


## Tie's Extra Questions: Fall 2015


Let $f$ be entire and suppose that
$\lim_{z \rightarrow \infty} f(z) = \infty$. Show that $f$ is a polynomial.

## Spring 2020 HW 3 #  5 #work

Show that if $f$ is entire and $\lim_{z\to\infty}f(z) = \infty$, then
$f$ is a polynomial.

## Tie's Extra Questions: Fall 2009 #work
Suppose $f$ is entire and there exist $A, R >0$ and natural number
$N$ such that $$|f(z)| \geq A |z|^N\ \text{for}\ |z| \geq R.$$ Show
that

1. $f$ is a polynomial and
2. the degree of $f$ is at least $N$.

## Tie's Extra Questions: Fall 2009 #work

Let $f(z)$ be entire and assume that $f(z) \leq M |z|^2$ outside some disk for some constant $M$. Show that $f(z)$ is a polynomial in $z$ of
degree $\leq 2$.

## 8 #work

Suppose $f$ is entire and suppose that for some integer $n\geq 1$,
\[
\lim_{z\to \infty} {f(z) \over z^n} = 0
.\]

Prove that $f$ is a polynomial of degree at most $n-1$.

## Spring 2020 HW 3 #  3 #work

Let $P, Q$ be polynomials with no common zeros. Assume $a$ is a root of
$Q$.
Find the principal part of $P/Q$ at $z=a$ in terms of $P$ and $Q$ if $a$ is 

(1) a simple root, and 
(2) a double root.


## Tie's Extra Questions: Spring 2015


Suppose $f$ is entire and there exist $A, R >0$ and natural number $N$ such that $|f(z)| \leq A |z|^N$ for $|z| \geq R$. 
Show that 

(i) $f$ is a polynomial and 
(ii) the degree of $f$ is at most $N$.

## Tie's Extra Questions: Fall 2016


(a) 
Let Let $f:{\mathbb C}\rightarrow {\mathbb C}$ be an entire function. Assume the existence of a non-negative integer $m$, and of positive constants $L$ and $R$, such that for all $z$ with $|z|>R$ the inequality $$|f(z)| \leq L |z|^m$$ holds. 
Prove that $f$ is a polynomial of degree $\leq m$.

(b) 
Let $f:{\mathbb C}\rightarrow {\mathbb C}$ be an entire function. Suppose that there exists a real number $M$ such that for all $z\in {\mathbb C}, \mbox{\textrm Re} (f) \leq M$.
Prove that $f$ must be a constant.


## Tie's Extra Questions: Spring 2015

Suppose $f$ is entire and there exist $A, R >0$ and natural number
$N$ such that $|f(z)| \geq A |z|^N$ for $|z| \geq R$. Show that (i)
$f$ is a polynomial and (ii) the degree of $f$ is at least $N$.

## Tie's Extra Questions: Spring 2015


Let $0<r<1$. Show that polynomials
$P_n(z)  = 1 + 2z + 3 z^2 + \cdots + n z^{n-1}$ have no zeros in
$|z|<r$ for all sufficiently large $n$'s.

## Spring 2020 HW 1 # 3
Prove that the following polynomial has its roots outside of the unit circle:
\[
p(z) = z^3 + 2z + 4
.\]

> Hint: What is the maximum value of the modulus of the first two terms if $\abs{z} \leq 1$?

## Spring 2020 HW 2 #  2.6.13 #work

Suppose $f$ is analytic, defined on all of $\CC$, and for each $z_0 \in \CC$ there is at least one coefficient in the expansion $f(z) = \sum_{n=0}^\infty c_n(z-z_0)^n$ is zero.
Prove that $f$ is a polynomial.

> Hint: use the fact that $c_n n! = f^{(n)}(z_0)$ and use a countability argument.


:::{.solution}
The claim is that there is some $N$ such that $\dd{^N f}{z^N} \equiv 0$, making $f$ a polynomial.
If no derivative is identically zero, the following set is countable:
\[
\Union_{n\in \NN} \dd{^n f}{z^n}\inv(0)
.\]
This is because each derivative is analytic and the zeros of an analytic function are countable.
But by hypothesis this set is uncountable.
:::

## Spring 2021.3 #completed

^409461

:::{.problem title="?"}
Suppose $f$ is entire, let $A, R> 0$ and $N \in \NN$, and suppose
\[
\abs{f(z)} \geq A\abs{z}^N && \text{for } \abs{z} \geq R
.\]

- Show that $f$ is polynomial.
- Show that $f$ has degree at least $N$.

:::

:::{.solution}
Note that the analogue of this problem where $\abs{f(z)} \leq A \abs{z}^N$ implies $f$ is a polynomial of degree at *most* $N$ is easy by the Cauchy estimate:
\[
\abs{f(z)} =\abs{\sum_{k\geq 0} c_k z^k } \implies 
\abs{c_n} = \abs{f^{(n)}(0)} 
&= \abs{{n!\over 2\pi i }\int_\gamma {f(\xi) \over (\xi-a)^{n+1} } \dxi } \quad \text{ at } a=0\\
&\leq {n!\over 2\pi }\int_\gamma {\abs{f(\xi)} \over \abs{\xi}^{n+1} } \dxi \\
&\leq {n!\over 2\pi }\int_\gamma {A {\abs{\xi}^N } \over \abs{\xi}^{n+1} } \dxi \\
&= {A n!\over 2\pi }\int_\gamma {{R ^N } \over R^{n+1} } \dxi \\
&= {An!\over 2\pi} \cdot {2\pi R \over R^{n+1-N}} \\
&= {An! \over R^{n-N}} \\
&\convergesto{R\to\infty} 0 \quad \iff n-N>0 \quad\iff n>N
,\]
so $f(z) = \sum_{0\leq k\leq N} c_k z^k$.

For the case at hand, a solution I liked from MSE:

- Write $g(z) \da f(1/z)$, so $g$ has a singularity at $z=0$.
  The claim is that this is a pole.

- It can't be removable: 
\[
\abs{g(z)} \geq A \abs{1\over z}^n \to\infty
\quad \text{ for }
\abs{1/z} \geq R \,\, (\iff \abs{z} < 1/R)
,\]
so $g$ is unbounded near $z=0$.
- It can't be essential: if so, take the neighborhood of $z=0$ given by $U\da D_{1\over R}(0)\smz = \ts{z\st 0< \abs{z} < {1\over R} }$.
Then $g(U) \subseteq \CC$ would be dense by Casorati-Weierstrass, but note that $g(z) = w\in g(U) \implies \abs{w} \da \abs{g(z)} \geq A\abs{1/z}^n$ since $\abs{z}<1/R$, so $g(U) \subseteq (\CC\sm D_{A\over R^n}(0))$ and in particular does not intersect the interior of $D_{A\over R^n}(0)$.

- Since $z=0$ is a pole, it has some finite order $m$, so write
\[
g(z) = \qty{c_{-m}z^{-m} + \cdots + c_{-1}z\inv} + \qty{c_0 + c_1 z + \cdots} \da p(1/z) + h(z)
,\]
where $p$ is polynomial of degree exactly $m$ (since $c_{-m} \neq 0$) and $h$ is entire.
In particular, $z=0$ is not a singularity of $h$.

- Now
\[
g(z) = p(1/z) + h(z) \implies f(z) = p(z) + h(1/z)
.\]

- Then
\[
f(z) - p(z) = h(1/z) \convergesto{\abs z\to \infty} c_0 \da h(0)
,\]
since holomorphic functions are continuous.

- Then $h$ is an entire function with a finite limit $L$ at $\infty$.
$h$ is bounded by $c_0$ in a neighborhood $U_\infty$ of $\infty$ and takes on a maximum on $U_\infty^c$ by compactness and the maximum modulus principle.
So $h$ is bounded on all of $\CC$, and thus constant by Liouville, and thus $h(1/z) = L$ for all $z$.

- So 
\[
f(z) &= p(z) + h(1/z) = p(z) + c_0 \\
\implies f(z) &= (c_{-1}z + \cdots + c_{-m}z^m) + c_0
,\]
which is a polynomial of degree exactly $m\da \deg p$.
- Why $m \geq N$: if not, $m<N$ so $N-m > 0$.
Then for large $z$,
\[
A \leq \abs{f(z) \over z^N} 
&= \abs{c_0 + c_{-1}z + \cdots + c_{-m}z^m \over z^N}\\
&= \abs{ {c_0 \over z^N} + {c_{-1} \over z^{N-1}} + \cdots + {c_{-m} \over z^{N-m}} } \\
&\convergesto{\abs{z}\to\infty} 0
,\]
since every term has a factor of $z$ in the denominator.
This contradicts $A>0$. $\contradiction$
:::



## Spring 2021.4 #completed

^c3336f

:::{.problem title="?"}
Let $f = u + iv$ be an entire function such that $\Re(f(x+iy))$ is polynomial in $x$ and $y$.
Show that $f(z)$ is polynomial in $z$.
:::

:::{.solution}
To clear up notation: write $f(z) = u(x, y) + iv(x, y)$, here we're assuming that $u$ is polynomial in $x$ and $y$.

:::{.claim}
If $u$ is polynomial in $x,y$, then so is $v$.
:::

:::{.proof title="?"}
This follows from the fact that $u$ is a harmonic conjugate of $v$, and the explicit process computing the conjugate will result in a polynomial.
Gamelin describes this process in detail, see Ch.2 Section 5 on Harmonic functions where he proves the formula
\[
v(x, y)
= \int_{y_{0}}^{y} \frac{\partial u}{\partial x}(x, t) \dt 
-\int_{x_{0}}^{x} \frac{\partial u}{\partial y}\left(s, y_{0}\right) \ds + C 
.\]

:::

:::{.claim}
Since $f(x, y)$ is a polynomial in $x, y$, $f(z)$ must be a polynomial in $z$.
:::

:::{.proof title="?"}
Since $f$ is entire, it's equal to its Laurent series everywhere, so
\[
f(z) = \sum_{k\geq 0} c_k z^k, \qquad c_k = {f^{(k) }(0) \over k!} = {1\over 2\pi i} \int_{S^1} {f(\xi) \over \xi^{k+1} } \dxi
.\]
Thus $f$ will be a polynomial if $c_{N} = 0$ for all $N$ large enough, which will be true if $f^{(N)}(z) = 0$ for large enough $N$.
But we can write
\[
\dd{}{z} f(z) = \dd{}{x} f(x, y)
\implies
0 = \qty{\dd{^N}{x^N}} f(x, y) = \qty{\dd{^N}{z^N}} f(z) \da f^{(N)}(z)
,\]
:::

:::


