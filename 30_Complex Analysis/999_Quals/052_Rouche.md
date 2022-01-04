---
order: 52
---

# Rouché's Theorem

## Zeros of $e^z$ #complex/exercise/completed

:::{.problem title="?"}
Prove that for every $n\in \ZZ^{\geq 0}$ the following polynomial has no roots in the open unit disc:
\[
f_n(z) \definedas \sum_{k=0}^n {z^k \over k!}
.\]

> Hint: check $n=1,2$ directly.

:::

:::{.solution title="Using Rouché"}
For the $n=1$ case, $f_1(z) = 0 \iff 1+z = 0 \iff z=-1$, so this has no roots in $\DD$.
For $n=2$, factor
\[
f_2(z) = 1 + z + z^2 = (z-\zeta_3^2)(z-\zeta_3^{-2})
,\]
using that
\[
\zeta_3^2\cdot \zeta_3^{-2} = 1,\qquad 
-(\zeta_3^2 + \zeta_3^{-2}) = -2\Re(\zeta_3^2) = -2\cos\qty{2\pi \over 3} = 1
.\]
Now use that $\abs{\zeta_3^{k}} = 1$, which is not in $\DD$.

For $n\geq 3$: toward applying Rouche's theorem, let $M(z) = 1 + z$ and $m(z) = {1\over 2}z^2 + \cdots + {1\over n!}z^n$.
Note that on $\abs{z} = 1$, $\abs{m(z)} = 2$, and 
\[
\abs{m(z)} 
&= \abs{\sum_{k\geq n+1} {z^k\over k!} } \\
&\leq \sum_{k\geq n+1} { \abs{z}^k \over k!} \\
&\leq \sum_{k\geq n+1} { 1 \over k!} \\
&= e^1 - \sum_{k\leq n} {1\over k!}
.\]
Suppose $n\geq 3$, 
\[
\abs{m(z)} < e - (1 + 1 + \cdots) \approx 0.718 < 2
,\]
then Rouché applies directly and 
\[
0 = \size Z_M(\DD) =\size Z_{M+m}(\DD) \da \size Z_f(\DD)
,\]
noting that $M(z) = 0 \iff z= -1$, which isn't contained in the open disc $\DD$.
:::

## Standard Rouché #complex/exercise/completed

:::{.problem title="?"}
Assume that $\abs b < 1$ and show that the following polynomial has exactly two roots (counting multiplicity) in $\abs{z} < 1$:
\[
f(z) \definedas z^3 + 3z^2 + bz + b^2
.\]

:::

:::{.solution}
Big: $M(z) = 3z^2$.
Small: $m(z) = z^3+bz + b^2$.
Then on $\abs{z} = 1$:
\[
\abs{m(z)} \leq \abs{z}^3 + b\abs{z} + b^2 = 1 + b + b^2 < 3 = \abs{M(z)}
,\]
and $M(z)$ has exact two roots in $\DD$.
:::

## Fixed points #complex/exercise/completed

:::{.problem title="?"}
Let $c\in \CC$ with $\abs{c} < {1\over 3}$.
Show that on the open set $\theset{z\in \CC \suchthat \Re(z) < 1}$, the function $f(z) \definedas ce^z$ has exactly one fixed point.
:::

:::{.solution}
The boundary region is $\ts{1+it\st t\in \RR}$, write $g(z) = ce^z-z$ so that fixed points of $f$ are zeros of $g$.

Big: $M(z) = z$.
Small: $m(z) = ce^z$.
Then for $z=1+it$,
\[
\abs{m(z)} = \abs{c}e^{\Re(z)} < ce < 1 \leq \sqrt{1^2+t^2} = \abs{1+it} = \abs{z}
,\]
so $M$ and $g$ have the same number of zeros, and $M$ has a unique zero. 
:::

## Standard Rouché #complex/exercise/completed

:::{.problem title="?"}
How many roots does the following polynomial have in the open disc $\abs{z} < 1$?
\[
f(z) = z^7 - 4z^3 - 1
.\]

:::

:::{.solution}
Big: $M(z) = -4z^3$.
Small: $m(z) = z^7 - 1$.
Then on $\abs{z} = 1$,
\[
\abs{m(z)} = \abs{z^7-1} \leq \abs{z}^7 + 1 = 2 < 4 = \abs{-4z^4}
,\]
so $f$ and $M$ have the same number of zeros: three.
:::

## More $e^z$ #complex/exercise/completed

:::{.problem title="?"}
Let $n\in \ZZ^{\geq 0}$ and show that the equation
\[
e^z = az^n
\]
has $n$ solutions in the open unit disc if $\abs{a} > e$, and no solutions if $\abs{a} < {1\over e}$.

:::

:::{.solution}
Note that $\abs{e^z} = e^{\Re(z)}$, which is maximizes on $S^1$ at $z=1 \in \RR$ and minimized at $z=-1$.
Write $f(z) = e^z-az^n$, so solution correspond to zeros of $f$.

Case 1: suppose $\abs{a} > e$.
Big: $M(z) = az^n$.
Small: $m(z) = e^z$.
On $\abs{z} = 1$,
\[
\abs{m(z)} = \abs{e^z} = e^\Re(z) \leq e^1 < \abs{a} = \abs{az^n} = \abs{M(z)}
,\]
so $f$ has $\size Z_M = n$ zeros.

Case 2: suppose $\abs{a} < 1/e$.
Big: $M(z) = e^z$.
Small: $m(z) = az^n$.
On $\abs{z} = 1$,
\[
\abs{m(z)} = \abs{az^n} = \abs{a} < e\inv \leq e^{\Re(z)} = \abs{e^z} = \abs{M(z)}
,\]
and $M$ has no zeros in $\DD$ (and in fact none in $\CC$), so neither does $f$.
:::

## 6 #complex/exercise/work

:::{.problem title="?"}
Let $f$ be analytic in a domain $D$ and fix $z_0 \in D$ with $w_0 \definedas f(z_0)$.
Suppose $z_0$ is a zero of $f(z) - w_0$ with finite multiplicity $m$.
Show that there exists $\delta >0$ and $\eps > 0$ such that for each $w$ such that $0 < \abs{w-w_0} < \eps$, the equation $f(z) - w = 0$ has exactly $m$ *distinct* solutions inside the disc $\abs{z-z_0} < \delta$.
:::


:::{.solution}
Write $g(z) \da f(z) - w_0$, then $g$ is holomorphic on $D$ and thus $w_0$ is an isolated zero.
Choose $\delta$ small enough so that $g$ is nonvanishing on $\DD_\delta(z_0)\smts{z_0}$.
Choose $\eps < \inf_{\abs{\xi} = \delta}\abs{f(\xi)}$, i.e. a disc about $w_0$
:::



## 7 #complex/exercise/work
For $k=1,2,\cdots, n$, suppose $\abs{a_k} < 1$ and
\[
f(z) \definedas \qty{z - a_1 \over 1 - \bar a_q z} \qty{z-a_2 \over 1 - \bar a_2 z} \cdots \qty{z - a_n \over 1 - \bar a_n z}
.\]
Show that $f(z) = b$ has $n$ solutions in $\abs{z} < 1$.


## 8 #complex/exercise/work
For each $n\in \ZZ^{\geq 1}$, let
\[
P_n(z) = 1 + z + {1\over 2!} z^2 + \cdots + {1\over n!}z^n
.\]
Show that for sufficiently large $n$, the polynomial $P_n$ has no zeros in $\abs{z} < 10$, while the polynomial $P_n(z) - 1$ has precisely 3 zeros there.

## 9 #complex/exercise/work
Prove that
\[
\max_{\abs z = 1} \abs{a_0 + a_1 z + \cdots + a_{n-1}z^{n-1} + z^n} \geq 1
.\]

> Hint: the first part of the problem asks for a statement of Rouche's theorem.

## 10 #complex/exercise/work
Use Rouche's theorem to prove the Fundamental Theorem of Algebra.



## #complex/exercise/work
Apply Rouché's Theorem to prove the Fundamental Theorem of Algebra: 

If
$$
P_n(z) = a_0 + a_1z + \cdots + a_{n-1}z^{n-1} + a_nz^n\quad  (a_n \neq 0)
$$
is a polynomial of degree $n$, then it has $n$ zeros in $\mathbb{C}$.


## #complex/exercise/work
Suppose $f$ is entire and there exist $A, R >0$ and natural number
$N$ such that 
$$|f(z)| \geq A |z|^N\ \text{for}\ |z| \geq R.$$ 

Show that (i) $f$ is a polynomial and (ii) the degree of $f$ is at least
$N$.

## Tie's Extra Questions: Fall 2009 #complex/exercise/work

Apply Rouché's Theorem to prove the Fundamental Theorem of Algebra: If
$$P_n(z) = a_0 + a_1z + \cdots + a_{n-1}z^{n-1} + a_nz^n\quad  (a_n \neq 0)$$
is a polynomial of degree n, then it has n zeros in $\mathbb C$.

## Spring 2020 HW 3.8 #complex/exercise/work

Prove the fundamental theorem of Algebra using

a.  
Rouche's Theorem.

b. 
The maximum modulus principle.

## Spring 2020 HW 3.11 #complex/exercise/work

Find the number of roots of $p(z) = 4z^4 - 6z + 3$ in $\abs{z} < 1$ and
$1 < \abs{z} < 2$ respectively.

## Spring 2020 HW 3.12 #complex/exercise/work

Prove that $z^4 + 2z^3 -2z + 10$ has exactly one root in each open
quadrant.

## Spring 2020 HW 3.13 #complex/exercise/work

Prove that for $a> 0$, $z\tan z - a$ has only real roots.


## Tie's Extra Questions: Fall 2011 #complex/exercise/work

Apply Rouché's Theorem to prove the Fundamental Theorem of Algebra: If
$$
P_n(z) = a_0 + a_1z + \cdots + a_{n-1}z^{n-1} + a_nz^n\quad  (a_n \neq 0)
$$
is a polynomial of degree n, then it has n zeros in $\mathbb C$.

## Tie's Extra Questions: Fall 2016 #complex/exercise/work

Prove that all the roots of the complex polynomial
$$z^7 - 5 z^3 +12 =0$$ lie between the circles $|z|=1$ and $|z|=2$.

## Tie's Extra Questions: Spring 2014 #complex/exercise/work


Apply Rouché's Theorem to prove the Fundamental Theorem of Algebra: If
$$P_n(z) = a_0 + a_1z + \cdots + a_{n-1}z^{n-1} + a_nz^n\quad  (a_n \neq 0)$$
is a polynomial of degree n, then it has n zeros in $\mathbf C$.

## Tie's Extra Questions: Spring 2015 #complex/exercise/work

Let $0<r<1$. Show that polynomials
$P_n(z)  = 1 + 2z + 3 z^2 + \cdots + n z^{n-1}$ have no zeros in $|z|<r$
for all sufficiently large $n$'s.

## Tie's Extra Questions: Spring 2015 #complex/exercise/work


Let $0<r<1$. Show that polynomials
$P_n(z)  = 1 + 2z + 3 z^2 + \cdots + n z^{n-1}$ have no zeros in
$|z|<r$ for all sufficiently large $n$'s.

## Tie's Extra Questions: Fall 2015 #complex/exercise/work

Find the number of roots of $z^4 - 6z + 3 =0$ in $|z|<1$ and
$1 < |z| < 2$ respectively.

## Tie's Extra Questions: Fall 2015 #complex/exercise/work


Prove that $z^4 + 2 z^3 - 2z + 10 =0$ has exactly one root in each
open quadrant.
