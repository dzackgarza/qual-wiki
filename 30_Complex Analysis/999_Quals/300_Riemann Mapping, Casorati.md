---
order: 300
---

# Riemann Mapping and Casorati-Weierstrass

## Spring 2020.6 #complex/qual/work

^128e58


:::{.problem title="?"}
Prove the open mapping theorem for holomorphic functions: If $f$ is a non-constant holomorphic function on an open set $U$ in $\mathbb{C}$, then $f(U)$ is also an open set.
:::


:::{.solution title="using the argument principle"}
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


## Spring 2020 HW 3.4 #complex/exercise/work

Let $f$ be non-constant, analytic in $\abs{z} > 0$, where $f(z_n) = 0$
for infinitely many points $z_n$ with $\lim_{n\to\infty} z_n = 0$.

Show that $z=0$ is an essential singularity for $f$.

> Example: $f(z) = \sin(1/z)$.


## 10 #complex/exercise/work
Let $f: {\mathbb C} \rightarrow {\mathbb C}$ be an injective analytic (also called univalent) function. 
Show that there exist complex numbers $a \neq 0$ and $b$ such that $f(z) = az + b$.

## Tie's Extra Questions: Fall 2009 #complex/exercise/work
Let $f: {\mathbb C} \rightarrow {\mathbb C}$ be an injective
analytic (also called *univalent*) function. Show that there exist
complex numbers $a \neq 0$ and $b$ such that $f(z) = az + b$.

## Spring 2020 HW 3, SS 3.8.14 #complex/exercise/work
Prove that all entire functions that are injective are of the form $f(z) = az + b$ with $a,b\in \CC$ and $a\neq 0$.

> Hint: Apply the Casorati-Weierstrass theorem to $f(1/z)$.


## Tie's Extra Questions: Spring 2015 #complex/exercise/work


(1) Let $f$ be analytic in $\Omega: 0<|z-a|<r$ except at a
sequence of poles $a_n \in \Omega$ with
$\lim_{n \rightarrow \infty} a_n = a$. Show that for any
$w \in \mathbb C$, there exists a sequence $z_n \in \Omega$ such
that $\lim_{n \rightarrow \infty} f(z_n) = w$.

(2) Explain the similarity and difference between the above assertion and the Weierstrass-Casorati theorem.


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
