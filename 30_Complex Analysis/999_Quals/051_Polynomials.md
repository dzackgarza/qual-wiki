---
order: 51
---

# Polynomials

## Big O Estimates


## Tie's Extra Questions: Fall 2011 #complex/exercise/work

:::{.problem title="?"}
Let $f(z)$ be entire and assume that $f(z) \leq M |z|^2$ outside some
disk for some constant $M$. Show that $f(z)$ is a polynomial in $z$ of degree $\leq 2$.
:::


:::{.solution}
Take a Laurent expansion at zero:
\[
f(z) = \sum_{k\geq 0} c_k z^k,\qquad c_k = {1\over k!} f^{(k)}(0) = {1\over 2\pi i}\oint_{\abs{\xi} = R} {f(\xi) \over \xi^{k+1}}\dxi
.\]
The usual estimate:
\[
2\pi i\abs{c_k} \leq \oint_{\abs{\xi} = R} R^{-(k+1)}\abs{f(\xi)} \dxi
\leq \oint_{\abs{\xi} = R}R^{-(k+1)} M R^2 \dxi
.\]


:::


## The reverse polynomial bound #complex/exercise/completed

:::{.problem title="?"}
Suppose $f$ is entire and there exist $A, R >0$ and natural number $N$ such that 
\[
|f(z)| \geq A |z|^N\ \text{for}\ |z| \geq R
.\]

Show that 

- $f$ is a polynomial and 
- the degree of $f$ is at least $N$.
:::

:::{.solution}
The easier version of this question: when $\abs{f} \leq A\abs{z}^N$, $f$ is a polynomial of degree *at most* $N$ by Cauchy's integral formula:
\[
\abs{f^{(n)}(z)} 
&= \abs{ {1\over 2\pi i} \oint_\gamma {f(\xi) \over (\xi - z)^{n+1}} \dxi } \\
&\leq  {1\over 2\pi i} \oint_\gamma { \abs{ f(\xi) } \over \abs{\xi - z}^{n+1}} \dxi \\
&\leq {1\over 2\pi i } \oint_\gamma {AR^N \over R^{n+1} } \dxi \\
&= {A\over 2\pi i} R^{N-(n+1)} \cdot 2\pi R \\
&= AR^{N-n} \\
&\convergesto{R\to\infty} 0 \qquad \iff N-n<0 \iff n>N
.\]

Now rearrange the given equality 
\[
\abs{f(z) \over z^N} \geq A \qquad \abs{z} \implies \abs{z^N\over f(z)} \leq A\inv
.\]
A priori, $f$ is equal to its power series at $z=0$, so $f(z) = \sum_{k\geq 0} c_k z^k$.
Since $\DD_R$ is compact, $f$ has finitely many zeros in this region, say $\ts{z_k}_{k\leq m}$.
This set must be finite, since an infinite subset of a compact set has a limit point, and being zero on a set with a limit point implies being identically zero by the identity principle.

Define 
\[
p(z) \da \prod_{1\leq k\leq m} (z-z_k) = z^m + \bigo(z^{m-1})
,\]
the product of these roots.
Increase $R$ if necessary to ensure that
\[
\abs{p(z)\over z^m} < 1 \implies
\abs{p(z)} < \abs{z}^m
.\]
Now define
\[
G(z) \da {p(z) z^N \over f(z)} \implies \abs{G(z)} = \abs{p(z) z^N\over f(z)} 
= \abs{z^N\over f(z)}\cdot \abs{p(z)} \leq A\inv \abs{z}^m 
.\]

> Issue: this might not be entire? There could be poles at the zeros of $f$ outside of $\DD_R$...

By the previous result, $G$ is a polynomial of degree at most $m$.
Now consider leading terms: on one hand,
\[
f(z) G(z) = p(z) z^N \sim \qty{z^m + \cdots }\cdot z^N = z^{N+m} + \cdots
.\]
On the other hand,
\[
f(z) G(z) 
&= f(z) \qty{z^m + \cdots} \\
&\sim \sum_{k\geq 0} c_k z^{k+m} + z^{m-1}f(z) + \cdots \\
&= (z^m + \cdots + c_{N}z^{N+m} + \cdots) + z^{m-1}f(z) + \cdots
,\]
and by the previous expression, this must be a polynomial of degree at most $N+m$.
This forces $c_k = 0$ for all $k> N$, otherwise these would contribute higher order terms.

> Note: maybe not quite right! 

Alternatively, note that the inequality can be rewritten as
\[
\abs{G(z)} \leq A\inv \abs{z}^m \implies \abs{p(z)\over f(z)} \leq A\inv \abs{z}^{m-N}
.\]

- If $m-N = 0$, then $p/f$ is an entire bounded function and thus constant, making $p(z) = \lambda f(z)$ and $f$ is a polynomial of degree exactly $N$.
-If $m-N>0$, then $p/f$ is a polynomial of degree at most $m-N$ by the previous result.
  But $p/f$ is a polynomial with no zeros, since $Z_p = Z_f$, and the only nonvanishing polynomial is a constant, so again $p = \lambda f$.
- If $m-N<0$, then use the inequality
\[
\abs{z^{N-m}p(z) \over f(z)} \leq A\inv
,\]
so the LHS is an entire bounded function and thus constant, so $z^{N-m}p(z) = \lambda f(z)$.
But the LHS is evidently a polynomial of degree $(N-m)+m = m$.
:::


# Misc

## Spring 2019.4 #complex/qual/completed

^047423

:::{.problem title="?"}
Let $f$ be a meromorphic function on the complex plane with the property that $|f(z)| \leq$ $M$ for all $|z|>R$, for some constants $M>0, R>0$.

Prove that $f(z)$ is a rational function, i.e., there exist polynomials $p, q$ so that $f=\frac{p}{q}$.
:::

:::{.solution}
Note that $f$ must have finitely many poles -- either $z=\infty$ is a pole or a removable singularity, and since poles are isolated, there is some $R\gg 0$ such that all other poles of $f$ are in $\abs{z} \leq R$.
The set $P_f$ of poles is a closed set and $\bar{\DD_R}$ is compact, so if $P_f$ is infinite it has an accumulation point, contradicting that poles are isolated.

So enumerate $P_f$ as $\ts{p_k}_{k\leq N}$, define $g(z) \da \prod_{k\leq N}(z-p_k)$, and set $F(z) \da g(z) f(z)$.
Then $F$ is an entire function, and the claim is that $F$ is bounded and thus constant by Liouville.
Proving the bound: take $\abs{z} > R$, then
\[
\abs{G(z)} 
&= \abs{f(z)} \abs{g(z)} \\
&\leq M C \abs{z}^N 
,\]
using that $g$ is a polynomial of degree $N$, so $\abs{g(z)\over z^N}\to 1$ as $\abs{z}\to \infty$ since $g$ is monic.
So after possibly increasing $R$, we can choose $\abs{z}$ large enough so that $\abs{g(z)\over z^N} < C$ for, say, some constant $C<2$.
In any case, by a common qual question, if $\abs{G} \in \bigo(\abs{z}^N)$ for $\abs{z}$ large enough then $G$ is a polynomial of degree at most $N$.
Then $f(z) \da G(z)/g(z)$ is a rational function.
:::



## Fall 2019.4 (Entire univalent functions are linear) #complex/qual/completed

^398dec

:::{.problem title="Entire univalent functions are affine/linear"}
Let $f: \mathbb{C} \rightarrow \mathbb{C}$ be an injective analytic (also called univalent) function. Show that there exist complex numbers $a \neq 0$ and $b$ such that $f(z)=a z+b$.
:::


:::{.solution}
Note that $f$ is non-constant, since a constant function is extremely non-injective.
Consider the singularity at $\infty$:

- If it is removable, then $f$ is bounded outside of a large disc, and bounded inside of it as a continuous function on a compact set, making $f$ entire and bounded and thus constant by Liouville.

- If it is essential, then by Casorati-Weierstrass there is a large disc of radius $R$ such that $f(\bar{\DD_R}^c) \subseteq \CC$ is dense.
  By the open mapping theorem, $f(\DD_R) \subseteq \CC$ is open, so by density it intersects $f(\bar{\DD_R}^c)$, but $\DD_R \intersect \bar{\DD_R}^c$ is empty so this contradicts injectivity.

So we can conclude $\infty$ is a pole of some order $N$, so $f\qty{1\over z} = \sum_{0\leq k\leq N} c_k z^{-k}$ and thus $f(z) = \sum_{0\leq k\leq N} c_k z^k$ is a polynomial of degree $N$.
However, a polynomial of degree $N$ is generically $N$-to-one locally, so injectivity forces $N=1$ and $f(z) = c_0 + c_1 z$, where $c_1\neq 0$ since $f$ is nonconstant.
:::



## Tie's Extra Questions: Spring 2014 #complex/exercise/work

Suppose $f$ is entire and there exist $A, R >0$ and natural number $N$ such that $$|f(z)| \geq A |z|^N\ \text{for}\ |z| \geq R.$$ Show
that 

(i) 
$f$ is a polynomial and 

(ii) 
the degree of $f$ is at least $N$.


## Tie's Extra Questions: Fall 2015 #complex/exercise/work


Let $f$ be entire and suppose that
$\lim_{z \rightarrow \infty} f(z) = \infty$. Show that $f$ is a polynomial.

## Spring 2020 HW 3.5 #complex/exercise/work

Show that if $f$ is entire and $\lim_{z\to\infty}f(z) = \infty$, then
$f$ is a polynomial.

## Tie's Extra Questions: Fall 2009 #complex/exercise/work
Suppose $f$ is entire and there exist $A, R >0$ and natural number
$N$ such that $$|f(z)| \geq A |z|^N\ \text{for}\ |z| \geq R.$$ Show
that

1. $f$ is a polynomial and
2. the degree of $f$ is at least $N$.

## Tie's Extra Questions: Fall 2009 #complex/exercise/work

Let $f(z)$ be entire and assume that $f(z) \leq M |z|^2$ outside some disk for some constant $M$. Show that $f(z)$ is a polynomial in $z$ of
degree $\leq 2$.

## #complex/exercise/work

Suppose $f$ is entire and suppose that for some integer $n\geq 1$,
\[
\lim_{z\to \infty} {f(z) \over z^n} = 0
.\]

Prove that $f$ is a polynomial of degree at most $n-1$.

## Spring 2020 HW 3.3 #complex/exercise/work

Let $P, Q$ be polynomials with no common zeros. Assume $a$ is a root of
$Q$.
Find the principal part of $P/Q$ at $z=a$ in terms of $P$ and $Q$ if $a$ is 

(1) a simple root, and 
(2) a double root.


## Tie's Extra Questions: Spring 2015 #complex/exercise/work


Suppose $f$ is entire and there exist $A, R >0$ and natural number $N$ such that $|f(z)| \leq A |z|^N$ for $|z| \geq R$. 
Show that 

(i) $f$ is a polynomial and 
(ii) the degree of $f$ is at most $N$.

## Tie's Extra Questions: Fall 2016 #complex/exercise/work


(a) 
Let Let $f:{\mathbb C}\rightarrow {\mathbb C}$ be an entire function. Assume the existence of a non-negative integer $m$, and of positive constants $L$ and $R$, such that for all $z$ with $|z|>R$ the inequality $$|f(z)| \leq L |z|^m$$ holds. 
Prove that $f$ is a polynomial of degree $\leq m$.

(b) 
Let $f:{\mathbb C}\rightarrow {\mathbb C}$ be an entire function. Suppose that there exists a real number $M$ such that for all $z\in {\mathbb C}, \mbox{\textrm Re} (f) \leq M$.
Prove that $f$ must be a constant.


## Tie's Extra Questions: Spring 2015 #complex/exercise/work

Suppose $f$ is entire and there exist $A, R >0$ and natural number
$N$ such that $|f(z)| \geq A |z|^N$ for $|z| \geq R$. Show that (i)
$f$ is a polynomial and (ii) the degree of $f$ is at least $N$.

## Tie's Extra Questions: Spring 2015 #complex/exercise/work


Let $0<r<1$. Show that polynomials
$P_n(z)  = 1 + 2z + 3 z^2 + \cdots + n z^{n-1}$ have no zeros in
$|z|<r$ for all sufficiently large $n$'s.

## Spring 2020 HW 1.3 #complex/exercise/work
Prove that the following polynomial has its roots outside of the unit circle:
\[
p(z) = z^3 + 2z + 4
.\]

> Hint: What is the maximum value of the modulus of the first two terms if $\abs{z} \leq 1$?

## Spring 2020 HW 2, SS 2.6.13 #complex/exercise/work

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

## Spring 2021.3 #complex/qual/completed

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



## Spring 2021.4 #complex/qual/completed

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

## Entire injective functions are linear #complex/exercise/completed

:::{.exercise title="Entire injective functions"}
Show that if $f$ is entire and injective then $f$ is necessarily linear, i.e. $f(z) = az+b$ for some constants $a,b\in \CC$ with $a\neq 0$.
:::

:::{.solution}
Write $g(z) \da f(1/z)$, which has a singularity at $z=0$.
The claim is that this is a pole.

If $z=0$ is a removable singularity, $g$ is bounded on some closed disc $\abs{z} \leq \eps$, so $f$ is bounded on $\abs{z} > \eps$.
Moreover $f$ is continuous and $\abs{z}\leq \eps$, $f$ is bounded on this disc.
This makes $f$ an entire bounded function and thus constant by Liouville, contradicting injectivity.

If $z=0$ is essential, then by Casorati-Weierstrass pick a punctured disc $D = \ts{\abs{z} \leq \eps}$ where $g(D)$ is dense in $\CC$.
Writing $D^c \da \ts{\abs{z} > \eps}$, this means that $f(D^c)$ is dense. 
But $U\da \ts{\abs{z} < \eps}$ is open and by the open mapping theorem $f(U)$ is open, so by density there is a point $w\in f(D^c) \intersect f(U)$ while $U \intersect D^c = \emptyset$, again contradicting injectivity.

So $z=0$ is a pole of $g$, and $g$ admits a Laurent expansion
\[
g(z) = \sum_{k\geq -N} c_k z^k
.\]
Since $f$ is entire, it equals its Laurent expansion at $z=0$, so equating the two series yields
\[
f(z) = \sum_{k\geq 0} d_k z^k 
&\implies g(z) = \sum_{k\geq 0} {d_k \over z^k} = \sum_{1\leq k\leq N} {c_k\over z^k} + \sum_{k\geq 0} c_k z^k \\
&\implies \sum_{k\geq 0} c_k z^k = 0 \\
&\implies f(z) = \sum_{0\leq k \leq N} c_k z^k
,\]
making $f$ a polynomial of degree at most $N$.

Now $f$ can not be degree zero, since constant maps are not injective.
Moreover $f$ can not be degree $N\geq 2$, since any polynomial of degree $N$ has $N$ roots in $\CC$ by the fundamental theorem of algebra, and any two distinct roots will be points where injectivity fails.
Finally, ruling out the case of roots with multiplicity, if $f(z) = c(z-a)^N$, then $f$ has exactly $N$ preimages in a neighborhood of $a$.
Letting $p$ be any such point, we can find $N$ complex points mapping to it:
\[
p = c(z-a)^N &\implies {p\over c} = (z-a)^N \\
&\implies \qty{p\over c}^{1\over N}\zeta_N^k = z-a \quad k=0,1,\cdots, n-1 \\
&\implies z_k\da \qty{p\over c}^{1\over N}\zeta_N^k + a \mapsvia{f} p
.\]

So $f$ must be degree exactly 1, i.e. $f(z) = az+b$.
:::


