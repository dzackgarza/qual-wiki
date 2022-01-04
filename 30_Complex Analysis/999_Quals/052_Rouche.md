---
order: 52
---

# Rouché's Theorem

## Exponential

### Zeros of $e^z$ #complex/exercise/completed

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


### More $e^z$ #complex/exercise/completed

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


### Zeros of partial sums of exponential #complex/exercise/completed

:::{.problem title="?"}
For each $n\in \ZZ^{\geq 1}$, let
\[
P_n(z) = 1 + z + {1\over 2!} z^2 + \cdots + {1\over n!}z^n
.\]
Show that for sufficiently large $n$, the polynomial $P_n$ has no zeros in $\abs{z} < 10$, while the polynomial $P_n(z) - 1$ has precisely 3 zeros there.
:::

:::{.solution}
More is true: this will hold for any disc of arbitrary radius $R$, with $n$ depending on $R$.
Fix $R$, then use that $P_n(z) \convergesto{n\to\infty} e^z$ uniformly on the compact disc $\abs{z} \leq R$.
Consequently, setting $g_n(z) \da {P_n(z)\over e^z}$, we have $g_n(z) \to 1$ uniformly on this disc, for any $\eps> 0$ this can be used to produce an $n\gg 1$ such that $\abs{ g_n(z) - 1 } < \eps$ for all $\abs{z} \leq R$.

So take $\eps \da 1$ and define $h(z) \da 1$, then for $\abs{z} = R$
\[
\abs{g_n(z) - 1} < 1 = \abs{h(z)}
,\]
so by Rouché,
\[
0 = \size Z_{h} = \size Z_{h + (g_n - 1)} = \size Z_{g_n}
,\]
since $h$ has no zeros at all.
Take $R=10$ to get the stated result.

For $P_n(z) - 1$, note that $e^z-1=0$ has three solutions in $\abs{z} < 10$, namely $z=0, \pm 2\pi i$.
We similarly have $P_n(z)-1\to e^z-1$ uniformly, so on a disc of radius $R$ choose $n$ large enough so that
\[
\abs{{P_n(z) -1 \over e^z - 1} - 1} &< 1 \\
\implies \abs{ (P_n(z) - 1) - (e^z-1) \over e^z-1} &< 1 \\
\implies \abs{ (P_n(z) - 1) - (e^z-1)} &< \abs{e^z-1} \\
\da \abs{m(z)} &< \abs{M(z)}
,\]
so 
\[
3 = \size Z_M = \size Z_{M+m} = \size Z_{P_n - 1}
.\]
:::

## Other Stuff

### Standard Rouché #complex/exercise/completed

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

### Fixed points #complex/exercise/completed

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

### Standard Rouché #complex/exercise/completed

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

### $n$-to-one functions #complex/exercise/completed

:::{.problem title="?"}
Let $f$ be analytic in a domain $D$ and fix $z_0 \in D$ with $w_0 \definedas f(z_0)$.
Suppose $z_0$ is a zero of $f(z) - w_0$ with finite multiplicity $m$.
Show that there exists $\delta >0$ and $\eps > 0$ such that for each $w$ such that $0 < \abs{w-w_0} < \eps$, the equation $f(z) - w = 0$ has exactly $m$ *distinct* solutions inside the disc $\abs{z-z_0} < \delta$.
:::

:::{.solution}
Write $g(z) \da f(z) - w_0$, then $g$ is holomorphic on $D$ and thus $w_0$ is an isolated zero.
Choose $\delta$ small enough so that $g$ is nonvanishing on $\DD_\delta(z_0)\smts{z_0}$.
Let 
\[
\gamma \da \ts{\abs{\xi - z_0} = \delta }= \bd\DD_{\delta}(z_0)
.\]
Choose $\eps < \inf\ts{w\in f(\delta)}$ so that $\abs{f(z) - w_0} > \eps$ in $\DD_\eps(w_0)\smts{w_0}$ for every $z\in \gamma$.
Let 
\[
\gamma' \da \bd \DD_{\eps}(w_0) = \ts{\abs{z-w_0} = \eps}
,\]
and
define the solution counting function:
\[
F(w) 
\da {1\over 2\pi i} \oint_{\gamma'} \logd(g(z)) \dz 
= {1\over 2\pi i } \oint_{\gamma'} {g'(z)\over g(z) }\dz
= {1\over 2\pi i} \oint_{\gamma'} {f'(z)\over f(z) - w} \dz
,\]
which counts the zeros of $g$ (since it has no poles) and consequently the number of solutions to $f(z) = w$ in $\DD_\eps(w_0)$.
This is now a continuous integer valued function on $\DD_\eps(w_0)$, and is thus constant.
Since $f(z_0) = w_0$ with $z_0$ enclosed by $\gamma$ and $w_0$ enclosed by $\gamma'$, the constant is exactly the multiplicity of the zero of $f(z) - w_0$ at $z_0$, which is $m$.
:::


### Blaschke products are $n$ to one #complex/exercise/completed

:::{.problem title="?"}
For $k=1,2,\cdots, n$, suppose $\abs{a_k} < 1$ and
\[
f(z) \da \qty{z - a_1 \over 1 - \bar a_1 z} \qty{z-a_2 \over 1 - \bar a_2 z} \cdots \qty{z - a_n \over 1 - \bar a_n z}
.\]
Show that $f(z) = b$ has $n$ solutions in $\abs{z} < 1$.
:::

:::{.solution}
Note that $f$ is holomorphic on $\DD$ and $S^1$, since the poles are at $1/\bar{a_k}$ and if $\abs{a_l} < 1$ then $\abs{\bar{a_k}} > 1$.
Fix $b$, then define $g_w(z) \da f(z) - w$ and form the solution counting function
\[
F(w) \da {1\over 2\pi i}\oint_{S^1} \logd g_w(z) \dz
= {1\over 2\pi i} \oint_{S^1} {f'(z) \over f(z)-w}\dz
.\]
Start by computing $F(0)$.
\[
F(0) 
&= {1\over 2\pi i }\oint_{S^1} \logd \prod_{1\leq k\leq n} \psi_{a_k}(z) \dz \\
&= {1\over 2\pi i }\oint_{S^1} \sum_{1\leq k\leq n} \logd \psi_{a_k}(z) \dz \\
&= {1\over 2\pi i }\oint_{S^1} \sum_{1\leq k\leq n} \qty{1-\abs{a_k}^2 \over (1-\bar{a_k} z)^2} \qty{z-a_k \over 1-\bar{a_k} z}\inv \dz \\
&= {1\over 2\pi i }\oint_{S^1} \sum_{1\leq k\leq n} {1-\abs{a_k}^2 \over (z-a_k)( 1-\bar{a_k}z) } \dz \\
&= {1\over 2\pi i } \sum_{1\leq k\leq n} \oint_{S^1} {1-\abs{a_k}^2 \over (z-a_k)( 1-\bar{a_k}z) } \dz \\
&= {1\over 2\pi i } \sum_{1\leq k\leq n} 2\pi i \\
&= n
,\]
where we've used that the integrand has a simple pole at $a_k$ since $1/\bar{a_k}\in \DD^c$.
So the equation $f(z) = 0$ has $n$ solutions.
Now use that $F$ is a continuous function of $w$ on $\DD$ and integer valued, thus constant.
So $F(w) = n$ for any $w$, meaning $f(z) = w$ has $n$ solutions in $\DD$ for every $w$.

> Alternative: $F$ continuously depends on the $a_k$, so send them all to zero to get $f(z) = z^n$ which trivially has $n$ zeros.

:::

### Max of a polynomial on $S^1$ #complex/exercise/completed

:::{.problem}
Prove that
\[
\max_{\abs z = 1} \abs{a_0 + a_1 z + \cdots + a_{n-1}z^{n-1} + z^n} \geq 1
.\]

> Hint: the first part of the problem asks for a statement of Rouche's theorem.

:::

:::{.solution}
Write $p(z) \da a_0 + \cdots + z^n$.
Toward a contradiction, suppose not so that $\abs{p(z)} < 1$ on $\abs{z} = 1$.
Then
\[
\abs{f(z)} < 1 = \abs{z}^n \qquad \text{ on } \abs{z} = 1
.\]
Taking $m(z) \da f(z)$ and $M(z) \da -z^n$, we have 
\[
n = \size Z_M = \size Z_{M+m} = \size Z_{f(z) - z^n} \leq n-1
,\]
since $f(z) - z^n$ is degree at most $n-1$, a contradiction.

:::


### Tie's Extra Questions: Fall 2009 (FTA) #complex/exercise/completed

:::{.problem title="?"}
Use Rouche's theorem to prove the Fundamental Theorem of Algebra.
:::

:::{.solution}
Write $f(z) = \sum_{k\leq n} c_k z^k$.
Big: $M(z) = c_nz^n$.
Small: $m(z) = f(z) - M(z) = \sum_{k\leq n-1} c_k z^k$.

Now use that
\[
\abs{m(z) \over M(z)} 
&\da \abs{c_n\inv \sum_{k\leq n-1} c_k z^{k-n}} \\
&= \abs{c_n\inv\qty{ {c_1\over z^n} + {c_2\over z^{n-1} } + \cdots + {c_{n-1}\over z}  }} \\
&\convergesto{\abs{z}\to\infty}0
,\]
so choose $R$ large enough such that for $\abs{z} \geq R$, $\abs{M(z)\over m(z)} < 1$.
Then on $\abs{z} = R$,
\[
\abs{m(z) \over M(z)} < 1 \implies \abs{m(z)} < \abs{M(z)}
\implies \size n = \size Z_{M} = \size Z_{M+m} = \size Z_{f}
,\]
since $c_n z^n$ has $z=0$ as a root with multiplicity $n$.
:::

### Spring 2020 HW 3.11 #complex/exercise/work


:::{.problem title="?"}
Find the number of roots of $p(z) = 4z^4 - 6z + 3$ in $\abs{z} < 1$ and
$1 < \abs{z} < 2$ respectively.
:::


:::{.solution}

:::



### Spring 2020 HW 3.12 #complex/exercise/work

Prove that $z^4 + 2z^3 -2z + 10$ has exactly one root in each open
quadrant.

### Spring 2020 HW 3.13 #complex/exercise/work

Prove that for $a> 0$, $z\tan z - a$ has only real roots.


### Tie's Extra Questions: Fall 2011 #complex/exercise/work

Apply Rouché's Theorem to prove the Fundamental Theorem of Algebra: If
$$
P_n(z) = a_0 + a_1z + \cdots + a_{n-1}z^{n-1} + a_nz^n\quad  (a_n \neq 0)
$$
is a polynomial of degree n, then it has n zeros in $\mathbb C$.

### Tie's Extra Questions: Fall 2016 #complex/exercise/work

Prove that all the roots of the complex polynomial
$$z^7 - 5 z^3 +12 =0$$ lie between the circles $|z|=1$ and $|z|=2$.

### Tie's Extra Questions: Spring 2014 #complex/exercise/work


Apply Rouché's Theorem to prove the Fundamental Theorem of Algebra: If
$$P_n(z) = a_0 + a_1z + \cdots + a_{n-1}z^{n-1} + a_nz^n\quad  (a_n \neq 0)$$
is a polynomial of degree n, then it has n zeros in $\mathbf C$.

### Tie's Extra Questions: Spring 2015 #complex/exercise/work

Let $0<r<1$. Show that polynomials
$P_n(z)  = 1 + 2z + 3 z^2 + \cdots + n z^{n-1}$ have no zeros in $|z|<r$
for all sufficiently large $n$'s.

### Tie's Extra Questions: Spring 2015 #complex/exercise/work


Let $0<r<1$. Show that polynomials
$P_n(z)  = 1 + 2z + 3 z^2 + \cdots + n z^{n-1}$ have no zeros in
$|z|<r$ for all sufficiently large $n$'s.

### Tie's Extra Questions: Fall 2015 #complex/exercise/work

Find the number of roots of $z^4 - 6z + 3 =0$ in $|z|<1$ and
$1 < |z| < 2$ respectively.

### Tie's Extra Questions: Fall 2015 #complex/exercise/work


Prove that $z^4 + 2 z^3 - 2z + 10 =0$ has exactly one root in each
open quadrant.
