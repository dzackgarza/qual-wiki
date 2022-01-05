---
order: 300
title: "Open Mapping, Riemann Mapping, Casorati-Weierstrass"
---

# Open Mapping, Riemann Mapping, Casorati-Weierstrass

## Spring 2020.6 (Prove the open mapping theorem) #complex/qual/completed

^128e58

:::{.problem title="?"}
Prove the open mapping theorem for holomorphic functions: If $f$ is a non-constant holomorphic function on an open set $U$ in $\mathbb{C}$, then $f(U)$ is also an open set.
:::

:::{.solution title="using the argument principle"}
Idea:

![](figures/2022-01-02_02-14-17.png)

Let $f: U\to \CC$.
Pick $w_0\in W$ with $f(z_0) = w_0$ for some $z_0\in U$; we want to show that $w_0$ is an interior point of $f(U)$, so we're looking for a disc containing $w_0$ and contained in $f(U)$.

Write 
\[
g_0(z) \da f(z) - w_0
,\]
so $g_0$ is holomorphic and has a zero at $z_0$.
Since zeros of holomorphic functions are isolated, there is some $U' \da \DD_r(z_0)$ where $g_0$ is nonvanishing.
The claim is that if we choose $\eps$ small enough, we can arrange so that $W_\eps \da \DD_\eps(w_0) \subseteq f(U)$.
This will follow if for every $w\in W_\eps$, the equation $f(z) = w$ has a solution in $U$, i.e. 
Define a function that counts the number of zeros:
\[
F(w)
&\da {1\over 2\pi i}\int_{\bd U' } {f(z) \over f(z) - w_1 }\dz\\
&= {1\over 2\pi i}\int_{\bd U' } {\dd{}{z}\qty{f(z) - w} \over f(z) - w }\dz\\
&= \size Z(f(z) - w, U' ) 
,\]
which is the number of zeros of $f(z) - w$ in $U'$ by the argument principle.
Now $F$ is a $\ZZ\dash$valued function, and the only obstruction to continuity is if $f(z) - w = 0$ in the integrand for some $z$.
The claim is that $\eps$ can be chosen such 
\[
z\in \bd U' \implies \abs{f(z) - w} > 0 \qquad \forall w\in W_\eps
.\]
The theorem then follows immediately: $F(w): U' \to W_\eps$ is a continuous and $\ZZ\dash$valued, thus constant.
Then noting that $F(w_0) = 1$ since $z_0\in U'$ and $w_0\in W_\eps$, we have $F\equiv 1 > 0$ for all $w$.


:::{.proof title="of claim"}
Choose
\[
\eps \da \min_{z\in \bd U'}\abs{f(z) - w_0}
.\]
Now if $\abs{w-w_0} < \eps$ and $\abs{z-z_0} = r$, we have $\abs{f(z) - w} > \eps > 0$.
:::




:::




## Fall 2019.4, Spring 2020 HW 3 SS 3.8.14, Tie's Extras Fall 2009, Problem Sheet (Entire univalent functions are linear) #complex/qual/completed

^398dec

:::{.problem title="Entire univalent functions are affine/linear"}
Let $f: \mathbb{C} \rightarrow \mathbb{C}$ be an injective analytic (also called univalent) function. Show that there exist complex numbers $a \neq 0$ and $b$ such that $f(z)=a z+b$.

> Hint: Apply the Casorati-Weierstrass theorem to $f(1/z)$.
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

:::{.solution title="older"}
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


## Tie's Extra Questions: Spring 2015 #complex/exercise/work


:::{.problem title="?"}
1.
Let $f$ be analytic in $\Omega: 0<|z-a|<r$ except at a
sequence of poles $a_n \in \Omega$ with
$\lim_{n \rightarrow \infty} a_n = a$. Show that for any
$w \in \mathbb C$, there exists a sequence $z_n \in \Omega$ such
that $\lim_{n \rightarrow \infty} f(z_n) = w$.

2.
Explain the similarity and difference between the above assertion and the Weierstrass-Casorati theorem.

> DZG: I think it's also necessary to state that $z_n \to a$.

:::


:::{.solution}
Without loss of generality, by translating $f$ we can take $a=0$ so that $a_n\to 0$.
Toward a contradiction, pick a $w$ with no such sequence.
Then there exists an $\eps$ and $R$ such that $f(\DD_\eps(a) ) \subseteq \DD_R(w)^c$, so in particular $\abs{f(z) - w} > R$ for $\abs{z-a} < \eps$.
So define
\[
G(z) \da {1\over f(z) - w} \implies \abs{G(z)} \leq R\inv < \infty \qquad \text{in } \DD_\eps(a)
,\]
If any of the $a_k$ are singularities, there is an $N \gg 1$ such that $\abs{z-z_k} < \eps$ for $k\geq N$, and since the bound holds here, the $a_k$ are all removable for $k\geq N$
So $a$ is an isolated singularity, and the bound implies it is removable.
By Riemann's removable singularity theorem, $G$ extends holomorphically over $a$.

Since the $a_k$ were poles of $f(z)$, they are poles of $f(z) - w$ since $\abs{f(z) - w} \geq \abs{\abs{f(z)} - \abs{w} } \to \infty$ as $a_k\to a$, and thus these are zeros of $G$ for $k\geq N$.
Since $G$ is holomorphic on $\DD_\eps(a)$ and $G(a_k) = 0$, choosing $N$ large enough so that $\abs{a_k - a} < \eps$, we have $\abs{G(z)} = 0 < R$ infinitely often, contradicting that

:::



## Tie's Extra Questions: Fall 2015 #complex/exercise/work

Let $f(z) = \sum_{n=0}^\infty c_n z^n$ be analytic and one-to-one in $|z| < 1$. 
For $0<r<1$, let $D_r$ be the disk $|z|<r$. 
Show that the area of $f(D_r)$ is finite and is given by
$$
S = \pi \sum_{n=1}^\infty n |c_n|^2 r^{2n}
.$$ 

> Note that in
general the area of $f(D_1)$ is infinite.


## Tie's Extra Questions: Fall 2015 (Variant) #complex/exercise/work


Let $f(z) = \sum_{n= -\infty}^\infty c_n z^n$ be analytic and one-to-one in $r_0< |z| < R_0$. For $r_0<r<R<R_0$, let $D(r,R)$ be the annulus $r<|z|<R$. Show that the area of $f(D(r,R))$ is finite and is given by
$$S = \pi \sum_{n=- \infty}^\infty n |c_n|^2 (R^{2n} - r^{2n}).$$

## 4 #complex/exercise/work
Suppose $f: \HH\union \RR\to \CC$ satisfies the following:

- $f(i) = i$
- $f$ is continuous
- $f$ is analytic on $\HH$
- $f(z) \in \RR \iff z\in \RR$.

Show that $f(\HH)$ is a dense subset of $\HH$.
