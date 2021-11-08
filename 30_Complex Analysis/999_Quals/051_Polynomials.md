# Polynomials

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

## Spring 20202 HW 2 #  2.6.13 #work

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
