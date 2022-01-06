---
order: 52
---

# Rouché's Theorem

## Standard Applications

### Tie's Extra Questions: Fall 2009, Fall 2011, Spring 2014 (FTA) #complex/exercise/completed

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

:::{.solution title="Explicit bound"}
An estimate: write $f(z) = \sum_{k\leq n} c_k z^k$ with $c_n = 1$, then for $R> 1$, on $\abs{z} = R$ we have
\[
\abs{f(z) - z^n} 
&\leq \sum_{k\leq n-1} \abs{ c_k z^k} \\
&\leq \sum_{k\leq n-1} \abs{ c_k} R^k \\
&\leq \sum_{k\leq n-1} \abs{ c_k} R^{n-1} \\
&= R^{n-1} \sum_{k\leq n-1} \abs{ c_k}  \\
&\da R^{n-1} C \\
&\leq R^n \\
&= \abs{z^n}
,\]
provided we can choose $C<R$, but this is possible since $\sum_{k\leq n-1}\abs{c_k}$ is a constant.
So $n = \size Z_{z^n} = \size Z_f$.
:::

### Tie's Extra Questions: Fall 2015 (Standard polynomial) #complex/exercise/completed

:::{.problem title="?"}
Find the number of roots of $z^4 - 6z + 3 =0$ in $|z|<1$ and
$1 < |z| < 2$ respectively.
:::

:::{.solution}
On $\abs{z} \leq 1$:

- Big: $M(z) = -6z$
- Small: $m(z) = z^4 + 3$

Then on $\abs{z} = 1$,
\[
\abs{m(z)} \leq \abs{z}^4 + 3 = 4 < 6 = \abs{-6z} = \abs{M(z)}
,\]
so $1 = Z_M = Z_f$ here.

On $\abs{z} \leq 2$:

- Big: $M(z) = z^4$
- Small: $m(z) = -6z+3$.

Then on $\abs{z} = 2$,
\[
\abs{m(z)} = \abs{-6z + 3} \leq 6\abs{z} + 3 = 15 < 16 = 2^4 = \abs{z}^4 = \abs{M(z)}
,\]
so $4 = Z_M = Z_f$ here.

Thus there are $4-1 = 3$ zeros in $1 \leq \abs{z} \leq 2$.
:::

### Tie's Extra Questions: Fall 2016 (Standard polynomial) #complex/exercise/completed

:::{.problem title="?"}
Prove that all the roots of the complex polynomial
$$f(z) = z^7 - 5 z^3 +12 =0$$ lie between the circles $|z|=1$ and $|z|=2$.
:::

:::{.solution}
On $\abs{z} \leq 1$:

- Big: $M(z) = 12$
- Small: $m(z) = z^6 - 5z^3$

For $\abs{z} = 1$,
\[
\abs{m(z)} \da \abs{z^7-5z^3}\leq \abs{z}^7 + 5\abs{z}^3 = 6 < 12 \da \abs{M(z)}
,\]
so $0 = Z_M = Z_{f}$.

On $\abs{z} \leq 2$,

- Big: $M(z) = z^7$
- Small: $m(z) = -5z^3 + 12$

On $\abs{z} = 2$,
\[
\abs{m(z)} \da \abs{-5z^3 + 12} \leq 5\abs{z}^2 + 12 = 32 < 128 = 2^7 \da \abs{M(z)}
,\]
so $7 = Z_M = Z_{f}$.

So $f$ has 7 zeros in $1 \leq \abs{z} \leq 2$.
:::

### Spring 2020 HW 3.11 (Standard polynomial) #complex/exercise/completed

:::{.problem title="?"}
Find the number of roots of $p(z) = z^4 - 6z + 3$ in $\abs{z} < 1$ and
$1 < \abs{z} < 2$ respectively.

> Note: the original problem used $4z^4-6z+3$, but I don't think it's possible to use Rouché on that at all!

:::

:::{.solution}
On $\abs{z} < 1$:

- Small: $m(z) = z^4+3$
- Big: $M(z) = -6z$

On $\abs{z} = 1$,
\[
\abs{m(z)} = \abs{z^4+3} \leq \abs{z}^4 + 3 = 4 < 6 = \abs{-6z} = \abs{M(z)}
,\]
so $Z_f = Z_M = 1$.

On $\abs{z} < 2$:

- Small: $-6z+3$
- Big: $z^4$

On $\abs{z} = 2$,
\[
\abs{m(z)} = \leq 6 + 3 = 9 < 2^4 = \abs{M(z)}
,\]
so $Z_f = Z_M = 4$.

Thus there are $4-1=3$ zeros in $1 \leq \abs{z} \leq 2$.
:::

### Standard polynomial #complex/exercise/completed

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

### Spring 2020 HW 1.3 (Standard polynomial) #complex/exercise/completed

:::{.problem title="?"}
Prove that the following polynomial has its roots outside of the unit circle:
\[
p(z) = z^3 + 2z + 4
.\]

> Hint: What is the maximum value of the modulus of the first two terms if $\abs{z} \leq 1$?

:::

:::{.solution}
Big: $M(z) = 4$
Small: $m(z) = z^3 + 2z$.
On $\abs{z} = 1$,
\[
\abs{m(z)} \leq \abs{z}^3 + 2\abs{z} = 1+2=3 < 4 = \abs{M(z)}
,\]
so $0 = Z_M = Z_{M+m} = Z_f$ in $\DD$.
:::

### Polynomials with parameters #complex/exercise/completed

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

### Tie's Extra Questions: Spring 2015 (Power series) #complex/exercise/completed

:::{.problem title="?"}
Let $0<r<1$. Show that polynomials
$P_n(z)  = 1 + 2z + 3 z^2 + \cdots + n z^{n-1}$ have no zeros in $|z|<r$
for all sufficiently large $n$'s.
:::

:::{.solution}
Key observation:
\[
P_n(z) = \sum_{1\leq k\leq n-1} kz^{k-1} = \dd{}{z}Q_n(z) 
\qquad Q(z) \da \sum_{0\leq k \leq n} z^k
.\]
Note that $Q(z) \to \sum_{k\geq 0} z^k = {1\over 1-z}$ uniformly on $\abs{z} \leq R < 1$ since this power series has radius of convergence 1.
Similarly $P_n(z)$ converges uniformly to $\dd{}{z}{1\over 1-z} = {1\over (1-z)^2}$, so let $P(z) \da {1\over (1-z)^2}$.
Note that $P$ is nonvanishing in $\DD$.

Strategy:

- Small: $m(z) = P(z) - P_n(z)$, look for an upper bound $\abs{m(z)} < U$
- Big: $P(z)$, look for a lower bound $L$ with $\abs{P(z)} > L > U$.

Just by considering the geometry of circles of radius $R < 1$ and $1$ and measuring distances to the point $1$, we can estimate
\[
0 < 1-R \leq \abs{1-z} < 1+R < 2 \implies \abs{P(z)} = {1\over \abs{1-z}^2} \geq {1\over 2^2} = {1\over 4}
.\]

Now fix $\eps < {1\over 4}$ and use uniform convergence of $P_n\to P$ to produce an $N$ such that $n\geq N$ implies $\norm{P-P_n}_\infty < \eps$ in $\abs{z} \leq R$.
Then on $\abs{z} = R$, for $n\geq N$,
\[
\abs{m(z)} \da \abs{P(z) - P_n(z)} \leq \norm{P - P_n}_\infty < \eps < {1\over 4} \leq \abs{P(z)} = \abs{M(z)}
,\]
so $0 = Z_P = Z_{P_n}$ by Rouché.
:::

## Exponentials

### UMN Fall 2009 (Solutions as zeros) #complex/exercise/completed

:::{.problem title="?"}
Find the number of solutions to the following equation on $\abs{z} < 1$:
\[
6z^3 + 1 = -e^z
.\]
:::

:::{.solution}
Write $f(z) \da 6z^3 + 1 + e^z$.

- Small: $m(z) = e^z + 1$
- Large: $M(z) = 6z^3$
- The estimate:
\[
\abs{m(z)} = \abs{e^z + 1} \leq e^{\Re(z)} + 1 \leq e^{\abs{z}} + 1 = e+1 < 6 = \abs{6z^3}
,\]
so $3 = Z_M = Z_f$.
:::

### UMN Spring 2009 (Checking the equality case) #complex/exercise/completed

:::{.problem title="?"}
Find the number of roots on $\abs{z} \leq 1$ of
\[
f(z)=z^{6}+4 z^{2} e^{z+1}-3
.\]
:::

:::{.solution}

- Small: $m(z) = z^6-3$
- Big: $M(z) = 4z^2 e^{z+1}$, which has two such zeros

Now estimate $m$ from above:
\[
\abs{m(z)} = \abs{z^6 - 3} \leq \abs{z}^6 + 3 = 4
.\]
and $M$ from below:
\[
\abs{M(z)} = \abs{4z^2 e^{z+1}} 
= 4e\abs{z}^4 e^{\Re(z)} 
= 4e e^{\Re(z)} 
\geq 4e e^{-1} = 4
,\]
which unfortunately isn't quite enough.
But equality occurs iff $\Re(z) = -1$ on $S^1$, so $z=-1$, in which case $\abs{m(-1)} = \abs{1-3} = 2$, so the inequality is in fact strict.
So $2 = Z_M = Z_f$.
:::



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

## Working for the estimate

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

### $z\sin(z)=1$ #complex/exercise/completed

:::{.problem title="?"}
Show that $z\sin(z) = a$ has only real solutions.
:::

:::{.solution}
Consider $f(z) \da z\sin(z) - a$.

Big: $M(z) \da z\sin(z)$.
Small: $m(z) \da -a$.
Use the following estimate:
\[
\abs{z\sin(z)}^2
&= \abs{z\over 2}^2 \abs{e^{iz} - e^{-iz}}^2 \\
&\geq \abs{z\over 2}^2 \abs{ \abs e^{iz} } - \abs{ e^{-iz} } }^2 \\
&= \abs{z\over 2}^2 \abs{e^{-\Im(z)} - e^{\Im(z)} } \\
&\convergesto{\Im(z)\to\infty} \infty
,\]
and so in particular a radius $R$ can be chosen large enough so that $\abs{z\sin(z)} > a$ for any $a$.
Thus for $\abs{z} = R$,
\[
\abs{m(z)} = \abs{a} \leq \abs{z\sin(z)} < \abs{M(z)}
\implies \size Z_{M} = \size Z_{M+m} = \size Z_f
.\]
To count the number of zeros of $z\sin(z)$, note that this equals zero at $z=0$ with multiplicity two and $z= k\pi$ for $k\in \ZZ$.
Choosing $R = {\pi \over 2} + n\pi$ for $n$ large enough, there are exactly $2n+2$ such zeros (with multiplicity) to $z\sin(z)$, and thus $2n+2$ zeros to $z\sin(z) - a$.
Now using that $z\sin(z) - a$ has exactly $2n+2$ *real* roots (??), this must be all of them.


> Unsure how to find any roots of this thing, real or not!

:::

#stuck

### Spring 2020 HW 3.13 #complex/exercise/work #stuck

:::{.problem title="?"}
Prove that for $a> 0$, $z\tan z - a$ has only real roots.
:::

### UMN Spring 2011 (Constant coefficient trick) #complex/exercise/completed

:::{.problem title="?"}
Let $a\in \CC$ and $n\geq 2$.
Show that the following polynomial has one root in $\abs{z} \leq 2$:
\[
f(z) = az^n + z + 1
.\]
:::

:::{.solution}
The key step: getting the following inequality to work
\[
\abs{az^n} = \abs{a}\abs{z}^n < c \leq 1 = \abs{ \abs{z} - \abs{1} } \leq \abs{z+1} 
.\]
If this is true, then $1 = \size Z_{z+1} = \size Z_f$.
If $\abs{a} < 2^n$, this holds because $\abs{a}\abs{z}^n < {1\over 2^n} 2^n = 1$, so taking $c\da 1$ works.

Otherwise, suppose $\abs{a} \geq 2^n$.
Letting $z_k$ be the roots of $f$ and considering the constant coefficient, we have
\[
a\prod_{k\leq n} z_k = 1 \implies \abs{ \prod_{k\leq n} z_k } = \abs{1\over a} \leq 2^n
,\]
so not every $z_k$ can satisfy $\abs{z_k} > 2$ and at least one is in $\abs{z} \leq 2$.
:::



