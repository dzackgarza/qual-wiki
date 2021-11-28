# Riemann Mapping and Casorati-Weierstrass

### Spring 2020 HW 3 #  4

Let $f$ be non-constant, analytic in $\abs{z} > 0$, where $f(z_n) = 0$
for infinitely many points $z_n$ with $\lim_{n\to\infty} z_n = 0$.

Show that $z=0$ is an essential singularity for $f$.

> Example: $f(z) = \sin(1/z)$.


## 10. 
Let $f: {\mathbb C} \rightarrow {\mathbb C}$ be an injective analytic (also called univalent) function. 
Show that there exist complex numbers $a \neq 0$ and $b$ such that $f(z) = az + b$.

### Tie's Extra Questions: Fall 2009
Let $f: {\mathbb C} \rightarrow {\mathbb C}$ be an injective
analytic (also called *univalent*) function. Show that there exist
complex numbers $a \neq 0$ and $b$ such that $f(z) = az + b$.

### Spring 2020 HW 3 #  3.8.14
Prove that all entire functions that are injective are of the form $f(z) = az + b$ with $a,b\in \CC$ and $a\neq 0$.

> Hint: Apply the Casorati-Weierstrass theorem to $f(1/z)$.


### Tie's Extra Questions: Spring 2015


(1) Let $f$ be analytic in $\Omega: 0<|z-a|<r$ except at a
sequence of poles $a_n \in \Omega$ with
$\lim_{n \rightarrow \infty} a_n = a$. Show that for any
$w \in \mathbb C$, there exists a sequence $z_n \in \Omega$ such
that $\lim_{n \rightarrow \infty} f(z_n) = w$.

(2) Explain the similarity and difference between the above assertion and the Weierstrass-Casorati theorem.


### Tie's Extra Questions: Fall 2015

Let $f(z) = \sum_{n=0}^\infty c_n z^n$ be analytic and one-to-one in $|z| < 1$. 
For $0<r<1$, let $D_r$ be the disk $|z|<r$. 
Show that the area of $f(D_r)$ is finite and is given by
$$
S = \pi \sum_{n=1}^\infty n |c_n|^2 r^{2n}
.$$ 

> Note that in
general the area of $f(D_1)$ is infinite.


### Tie's Extra Questions: Fall 2015 (Variant)


Let $f(z) = \sum_{n= -\infty}^\infty c_n z^n$ be analytic and one-to-one in $r_0< |z| < R_0$. For $r_0<r<R<R_0$, let $D(r,R)$ be the annulus $r<|z|<R$. Show that the area of $f(D(r,R))$ is finite and is given by
$$S = \pi \sum_{n=- \infty}^\infty n |c_n|^2 (R^{2n} - r^{2n}).$$

## 4 #work
Suppose $f: \HH\union \RR\to \CC$ satisfies the following:

- $f(i) = i$
- $f$ is continuous
- $f$ is analytic on $\HH$
- $f(z) \in \RR \iff z\in \RR$.

Show that $f(\HH)$ is a dense subset of $\HH$.