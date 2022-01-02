---
sort: 999
title: "Exercises: Singularities"
---

# Exercises: Singularities

## General

:::{.exercise title="True/false"}
Prove that the following statements or true, or find a counterexample:

- If $f,g$ have a pole at $a$, then $f+g$ has a pole at $a$.
- If $f,g$ have a pole at $a$, then $fg$ has a pole at $a$.
- If $f$ has an essential singularity at $z_0$ at $g$ is has a pole at $z_0$, then $z_0$ is an essential singularity for $f+g$.
- If $f$ has a pole of order $N$ at $z_0$ then $f^2$ has a pole of order $2N$ at $z_0$.

#complex/exercise/completed 

:::

:::{.solution}
\envlist

- False: $f(z) \da 1/z, g(z) \da -1/z \implies f+g = 0$.
- False: $f(z) = g(z) = 1/z \implies fg = 1/z^2$.
- True: write $f(z) = \sum_{k\in \ZZ} c_k (z-z_0)^k$, which has infinitely many negative coefficients, and $g(z) = \sum_{k\geq -N}d_k (z-z_0)^k$.
  Then 
  \[
  f(z) + g(z) = \sum_{k\leq -N-1}c_k(z-z_0)^k + \sum_{k\geq -N} (c_k + d_k)(z-z_0)^k
  ,\] 
  which again has infinitely many negative coefficients.
- True: check the Laurent expansion directly:
\[
  \qty{ \sum_{k\geq -N} c_k (z-z_0)_k }^2 
  &= {c_{-N}(z-z_0)^{-N} + \bigo((z-z_0)^{-N+1})}^2 \\
  &= (c_{-N})^2 (z-z_0)^{-2N} + \bigo((z-z_0)^{-2N+1})
.\]
  An easier alternative, use theorem 1.2 from S&S: write $f(z) = (z-z_0)^{-N} g(z)$ where $g$ is holomorphic and (importantly) nonvanishing in a neighborhood of $z_0$.
  Then $f(z)^2 = (z-z_0)^{-2N}(g(z))^2$, where $g^2$ is again nonvanishing in a neighborhood of $z_0$ since $\CC$ is an integral domain.
:::

:::{.exercise title="Residues and classifying singularities"}
Classify the singularities of 
\[
f(z) = {z^3+1\over z^2(z+1)}
.\]

#complex/exercise/completed

:::

:::{.concept}
Showing a pole $z_0$ of $f$ is order $n$: show that $z_0$ is a zero of order $n$ of $1/f$, i.e. $1/f = (z-z_0)^nh(z)$ with $h$ nonvanishing in a neighborhood of $z_0$.
:::

:::{.solution}
Write $f(z) = p(z)/q(z)$ and factor $p$: a principal root is $\omega = e^{i\pi 3}$, so 
\[
p(z) 
&= (z-\omega\zeta_3^0)(z-\omega\zeta_3^1)(z-\omega\zeta_3^2) \\
&= (z-e^{i\pi\over 3})(z-e^{3i\pi \over 3})(z-e^{5i\pi \over 3}) \\
&= (z+1)(z-\omega)(z-\bar\omega)
,\]
so $z=-1$ is a removable singularity of $f$.
Alternatively, note that ${z^3+1 \over z+1} = z^2-z+1$ and cancel the common term.

Note that $z=0$ is a zero of order $n=2$ of $1/f(z)$, since $1/f(z) = z^2h(z)$ where $h$ is nonvanishing in a neighborhood of $0$.
Thus $z=0$ is a pole of order $n=2$ of $f$.
The residue is computed as
\[
\Res_{z=0} f(z) 
&= {1\over (1-1)!} \lim_{z\to 0} \dd{}{z} (z-0)^2f(z) \\
&= \dd{}{z} {z^3+1\over z+1}\evalfrom_{z=0} \\
&= \qty{ {3z^2\over z+1} - {(z^3+1)\cdot 1\over (z+1)^2} }\evalfrom_{z=0} \\
&= -1
.\]

Alternatively, expand as a Laurent series about $z=0$:
\[
f(z) 
&= z^{-2}(z^3 + 1) {1\over 1+z} \\
&= (z + z^{-2})\sum_{k\geq 0}(-z)^k \\
&= (z-z^2 + z^3 - \cdots) + (z^{-2} - z\inv + 1 - z + \cdots)
,\]
and read off the coefficient of $z\inv$.

:::

:::{.exercise title="Classifying singularities"}
Classify the singularities at $z=0$ of the following
\[
f_1(z) &= {\Log(1+z) \sin(z) \over z^2} \\
f_2(z) &= e^{\sin\qty{1\over z}} \\
f_3(z) &= {1+z \over e^z-1}
.\]

#complex/exercise/completed

:::

:::{.solution}
$f_1$: removable, evident from Laurent expansion at $z=0$:
\[
z^{-2}\Log(1+z)\sin(z) 
&= z\inv \qty{ \sum_{k\geq 1} { (-z)^k \over k} }
\qty{z - { z^3 \over 3!} + { z^5 \over 5!} - \cdots} \\
&= z^{-2}
\qty{ -z+ { z^2 \over 2}  - { z^3 \over 3} + \cdots}
\qty{z - { z^3 \over 3!} + { z^5 \over 5!} - \cdots} \\
&= z^{-2}\qty{ z^2(-1) + z^3\qty{1\over 2} + z^2\qty{ -{ 1 \over 3!} - { 1 \over 3} } + \cdots } \\
&= 1 + {z \over 2} + \cdots
.\]

$f_2$: essential, evident from a sequence like $z_k \da \qty{k\cdot {\pi\over 2} }\inv$ which makes $\sin(z_k)$ oscillate between 0 and 1.

$f_3$: pole of order 1 with residue 1, evident after some slightly clever Laurent manipulations:
\[
{1\over e^z-1} 
&= {1 \over z + {1\over 2}z^2 + \cdots} \\
&= {1 \over z\qty{1 + {1\over 2}z + \cdots} } \\
&\da {1\over z \qty{1 + p(z)}} && p(z) \da {1\over 2} z + {1\over 3!}z^2 + \cdots \\
&= z\inv \sum_{k\geq 0}(-p(z))^k z^k \\
&= z\inv \qty{1 - zp(z) + z^2p(z)^2 - z^3p(z)^3 + \bigo(z^4)} \\
&= z\inv\qty{1- \bigo(z^2) + \bigo(z^4) - \bigo(z^6) } \\
&={1\over z} - \bigo(z) + \bigo(z^3)
.\]

:::

## Zeros

:::{.exercise title="Zeros of $\sin(\pi z)$"}
Show that the complex zeros of $f(z) \da \sin(\pi z)$ are exactly $\ZZ$, and each is order 1.
Calculate the residue of $1/\sin(\pi x)$ at $z=n\in \ZZ$.

#complex/exercise/work 

:::

## Orders of poles/zeros

:::{.exercise title="Orders of zeros"}
Find the orders of zeros of the following functions:

- $(e^z-1)^3$

#complex/exercise/completed

:::

:::{.solution}
\envlist

- $z=0$ of order 3: if $z_0$ is order $n$ for $f$, then it's order $kn$ for $f^k$.
  So check that $e^z-1$ has a root $z=0$ and $\dd{}{z}e^z-1\mid_{z=0} = e^z\mid_{z=0}\neq 0$, making it order 1.
:::

:::{.exercise title="Orders of poles"}
Determine the order of the pole of 

- ${1\over z\sin(z)}$ at $z_0 = 0$.
- ${e^{z^2}-1\over z^4}$ at $z_0=0$

#complex/exercise/completed

:::

:::{.solution}
- Order 2:
\[
\lim_{z\to 0}z^0 f(z) &= \infty\\
\lim_{z\to 0}z^1 f(z) &= \infty\\
\lim_{z\to 0}z^2 f(z) &= 1 \neq 0 
,\]
using that $z/\sin(z) \convergesto{z\to 0} 1$.

- Order 2: apply L'Hopital as necessary
\[
\lim_{z\to 0}z^0 f(z) &= \infty\\
\lim_{z\to 0}z^1 f(z) &= \infty\\
\lim_{z\to 0}z^2 f(z) &= 1 \neq 0 
.\]
  Alternatively, take the Laurent expansion:
  \[
  f(z) 
  &= z^{-4}(1 + z^2 + {1\over 2!} (z^2)^2 + {1\over 3!} (z^2)^3 + \bigo(z^4) - 1) \\
  &= z^{-2} + {1\over 2!} + {1\over 3!} z^2 + \bigo(z^4)
  .\]

:::

:::{.exercise title="Poles of $1/\sin$"}
Show that all singularities of $1/\sin(z)$ are poles of order 1.

#complex/exercise/work

:::

:::{.exercise title="Poles of derivatives"}
Show that if $z_0$ is a pole of order $n$ of $f$, then it is a pole of order $n+k$ for $f^{(k)}$.

#complex/exercise/work

:::

:::{.exercise title="Poles of elliptic functions"}
Let $f$ be an elliptic function and $P$ be its fundamental parallelogram.
Supposing that $f$ is nonconstant, show that $f$ has at least two poles in $P$ (counted with multiplicity).

#complex/exercise/completed

:::

:::{.solution}
Write the period lattice of $f$ as $\Lambda = \omega_1\ZZ + \omega_2 \ZZ$, and without loss of generality (by translating $P$ if necessary), assume that $f$ has no poles on $\bd P$.
Since $P$ is bounded and $f$ is periodic, if $f$ has no poles then its only singularities will be removable.
In this case $f$, extends to a holomorphic function on $P$, and thus an entire function, making $f$ constant by Liouville.
So $f$ has at least one pole.
Toward a contradiction, suppose $f$ has exactly one pole $z_0\in P$, in which case $\int_{\bd P} f \neq 0$ since the residue at $z_0$ will be nonzero.
We'll show that $\int_{\bd P} f$ is forced to be zero to derive the contradiction.

Write $\bd P = \sum_{1\leq k \leq 4} \gamma_k$ where the $\gamma_k$ are the edges traversed counterclockwise.
By periodicity, 

- $I_1 \da \int_{\gamma_1} f = - \int_{\gamma_3}f$
- $I_2 \da \int_{\gamma_2} f = - \int_{\gamma_4}f$

Thus
\[
\int_{\bd P} f = \sum_{1\leq k \leq 4} \int_{\gamma_k} f = I_1 + I_2 - I_1 - I_2 = 0
.\]
$\contradiction$


> Note that if there are at least two poles, the residues may cancel and $\int_{\bd P} f$ may be zero or nonzero.
This argument in fact shows that the residues *can not* cancel, i.e. $\sum_{k} \Res_{z=z_k} f(z)\neq 0$.

:::


## Poles 

:::{.exercise title="Singularities of of $\sin(z)/z$"}
Show that $\sin(z)/z$ has no poles.

#complex/exercise/completed

:::

:::{.solution}
Heuristic: $\sin(z)$ has a zero of order 1, so the $z$ in the denominator exactly cancels it.
Explicitly, this is evident from the Laurent expansion about zero:
\[
z\inv \sin(z) = z\inv\qty{ z - {z^3 \over 3!} + {z^5\over 5!} - \cdots} = 1 - {z^2\over 3!} + {z^4 \over 5!} - \cdots
,\]
which has no factors of $z^{-k}$.
So $z=0$ is a removable singularity.
:::

:::{.exercise title="Singularities of $1\over e^z - 1$"}
Classify the singularities and compute the residues at any poles of the following function:
\[
f(z) \da {1\over e^z - 1}
.\]

#complex/exercise/completed

:::

:::{.solution}
Note $e^z = 1$ when $z=z_k\da 2\pi k$ for $k\in \ZZ$, and the claim is that these are all poles of order 1 of $f(z)$.
These are clearly poles of some order, since they are zeros of $1/f$, and the order will be the smallest $n$ for which $\lim_{z\to z_k}(z-z_k)^n f(z)$ exists.
Start by computing the first:
\[
\lim_{z\to z_k}(z-z_k)f(z) = \lim_{z\to z_k} {z-z_k\over e^z - 1} \equalsbecause{\text{LH}} \lim_{z\to z_k} {1\over e^z} = e^{-z_k} = 1
.\]
:::

## Singularities at Infinity 

:::{.exercise title="Removable singularity at infinity iff constant"}
Let $f$ be entire. 
Show that $f$ has a removable singularity at $z_0 = \infty$ iff $f$ is constant.


#complex/exercise/completed

:::

:::{.solution}
Suppose $f$ is not constant.
If $z=\infty$ is removable, $f$ is bounded in a neighborhood of $\infty$, say by $M_1$ on $\abs{z} > R$.
Now $\abs{z} \leq R$ is a closed and bounded set, thus compact, and since $f$ is continuous here it is bounded by the extreme value theorem, say by $M_2$.
Then $\abs{f(z)} \leq \max(M_1, M_2)$ on $\CC$ is entire and bounded, thus constant by Liouville, a contradiction. $\contradiction$

Conversely, if $f$ is constant, $f$ is trivially bounded in every neighborhood of $\infty$, making it a removable singularity.
:::

:::{.exercise title="Entire functions with poles at infinity"}
Characterize all entire functions with a pole of order $m$ at $\infty$.

#complex/exercise/completed

:::

:::{.solution}
Since $f$ is entire, $f(z) = \sum_{k\geq 0 } c_k z^k$.
Expanding about $z_0=\infty$, we have $f(1/z) = \sum_{k\geq 0} c_k z^{-k} = c_0 + {c_1\over z} + \cdots$.
If $z_0=\infty$ is a pole of order $m$, then $c_m\neq 0$ but $c_{>m} = 0$, which forces $f(z) = \sum_{0\leq k \leq m} c_k z^k$ to be a polynomial of degree $m$.
:::

## Essential Singularities

:::{.exercise title="Images of sequences of poles converge to anything"}
Let $f$ be holomorphic in $0 < \abs{z-z_0} < r$, minus a sequence of poles $\ts{z_k} \to z_0$.
Show that for any $w\in \CC$, there is a sequence $\ts{w_k}\to z_0$ with $f(w_k)\to w$.

#complex/exercise/completed

:::

:::{.solution}
Toward a contradiction, fix $w$ and suppose no such sequence exists.
Then for every sequence $w_k\to z_0$, there is an $\eps$ such that $\abs{f(w_k) - w} \geq \eps$ for all $k$.
So the function $g(z) \da {1\over f(z) - w}$ has no poles in $D_r(z_0)\smts{z_0}$, and since each $z_k$ is a pole of $f$, each is a zero of $g$.
If $z_0$ is a singularity, since $\abs{g(z)} \leq \eps$, it is removable and thus $g$ can be extended holomorphically over $z_0$.
By continuity, since $z_k\to z_0$ with $g(z_k) = 0$, we have $g(z_0) = 0$.
By the identity principle, $g\equiv 0$, which means that every $z\in D_r(z_0)\smts{z_0}$ is a zero of $g$ and thus a pole of $f$.
But this contradicts that $f$ is holomorphic on $D_r(z_0)\smts{z_k}$. $\contradiction$
:::

:::{.exercise title="Essential singularities"}
Fix $a\in \CC\union\ts{\infty}$ and let $f(z) \da e^{1\over z^2}$.
Find a sequence $z_k\to 0$ such that $f(z_k) \convergesto{k\to\infty} a$

#complex/exercise/completed

:::

:::{.solution}
\envlist

- For $a\in \RR_{< 0}$: take $z_k\da {1\over \Log(a) + 2\pi i k - {\pi i \over 2}}$  
  Then $f(z_k) = a$ for all $k$ but $z_k\to 0$.
- For $a=0$: take $z_k = -1/k$.
- For $a=\infty$, take $z_k = 1/k$.
- For anything else, take $z_k \da {1\over \Log(a) + 2\pi i n}$ if $a \in \RR_{\geq 0}$.
  Again $f(z_k) = a$ for all $k$ but $z_k\to 0$.
:::

:::{.exercise title="Constructing functions with specified singularities"}
Determine a function with

- An essential singularity at $z=1$
- An essential singularity at $z=0$
- A pole of order 1 at $z=1-i$
- A pole of order 2 at $z=1+i$
- A removable singularity at $z=7$

#complex/exercise/completed

:::

:::{.solution}
Note that writing a single function for each singularity and taking a product *might* work, except that there may be unforeseen cancellation of zeros of one with poles of another, or some might become removable.
A surefire way is to take a sum, e.g. 
\[
f(z) = e^{1\over z-1} + e^{1\over z} + {1\over z - (1-i)} + {1\over (z - (1+i) )^2 } + { z-7 \over \sin(z-7) }
.\]

:::

:::{.exercise title="Limit point of zeros is an essential singularity"}
Suppose $f\not\equiv 0$ is holomorphic on $\Omega\smts{z_0}$ with a sequence of zeros $z_k$ limiting to $z_0$.
Show that $z_0$ is an essential singularity of $f$.

#complex/exercise/completed

:::

:::{.solution}
It can not be a pole: otherwise $\abs{f(z)}\to \infty$ as $z\to z_0$, but $f(z) = 0$ infinitely often in every neighborhood of $z_0$ since the $z_k$ accumulate on it.
It can not be removable: otherwise $f$ extends holomorphically over $z_0$, and continuity forces $f(z_k) \to 0$ as $z_k\to z_0$.
But then $f = 0$ on a set with an accumulation point, making $f \equiv 0$ by the identity principle.
:::


## Removable Singularities

:::{.exercise title="Showing singularities are removable"}
Consider
\[
f(z) \da {1\over \sin(z)} - {1\over z} + {2z\over z^2-\pi^2}
.\]
Show that on $\abs{z} < 2\pi$, all singularities are removable, and find a Laurent expansion about $z=0$.

#complex/exercise/completed

:::

:::{.solution title="Using L'Hopital and boundedness"}
Note that the singularities are
\[
z = 0, \pi, -\pi
.\]

That $z=0$ is removable:
\[
\lim_{z\to 0} f(z) 
&= \lim_{z\to 0} {z-\sin(z) \over z\sin(z)} \\
&\equalsbecause{\text{LH}} \lim_{z\to 0} {1 - \cos(z) \over \sin(z) + z\cos(z)} \\
&\equalsbecause{\text{LH}} \lim_{z\to 0} {\sin(z) \over \cos(z) + \cos(z) -z\sin(z) } \\
&= 0 < \infty
,\]
so in particular $f$ is bounded in a neighborhood of $z=0$, making it removable.

That $z=\pi$ is removable:
\[
\lim_{z\to \pi} f(z) 
&= \lim_{z\to \pi} {1\over \sin(z)} - {1\over z} + {1\over z-\pi} + {1\over z+\pi}\\
&= c_1 + \lim_{z\to \pi} {1\over \sin(z)} + {1\over z-\pi} \\
&= c_1 + \lim_{z\to \pi} { (z-\pi) -\sin(z) \over (z-\pi) \sin(z) }\\
&= c_1 + \lim_{w\to 0} { w -\sin(w + \pi) \over w \sin(w+\pi) } \qquad w\da z-\pi \\
&= c_1 - \lim_{w\to 0} { w + \sin(w) \over w \sin(w) } \\
&\equalsbecause{\text{LH}} c_1 + 0 < \infty
,\]
using the same L'Hopital argument as above. 
So this limit is bounded.

That $z=-\pi$ is removable:
\[
\lim_{z\to \pi} f(z) 
&= \lim_{z\to -\pi} {1\over \sin(z)} - {1\over z} + {1\over z-\pi} + {1\over z+\pi}\\
&= c_2 + \lim_{z\to -\pi} {1\over \sin(z)} + {1\over z+\pi}\\
&= c_2 + \lim_{z\to -\pi} {(z+\pi) - \sin(z) \over (z+\pi) \sin(z) } \\
&= c_2 - \lim_{z\to -\pi} {w + \sin(w) \over w \sin(w) } \qquad w \da z+\pi \\
&= c_2 + 0 < \infty
,\]
again by the same argument.

For a Laurent expansion about $z=0$, note
\[
{1\over \sin(z) } 
&= {1\over z + c_3 z^3 + c_5 z^5 + \bigo(z^7)} \\
&= z\inv( 1 + c_3z^2 + (c_3^2-c_5)z^4 + \bigo(z^6)) \\
&= z\inv + {1\over 3!} z + \qty{ \qty{1\over 3!}^2 - {1\over 5!} }z^3 + \bigo(z^5) \\
&= z\inv + {1\over 6}z + {7\over 360}z^3 + \bigo(z^5)
.\]
and
\[
{2z\over z^2-\pi^2} 
&= - {2z\over \pi^2} {1\over 1 - \qty{z\over \pi}^2 } \\
&= -{2z\over \pi^2}\sum_{k\geq 0}\qty{z\over \pi}^{2k} \\
&= -{2z\over \pi^2}\qty{1 + {1\over \pi^2} z^2 + {1\over \pi^4}z^4 + \bigo(z^6) } \\
&= -{2\over \pi^2}z -{2\over \pi^4}z^3 - {2\over \pi^6} z^5 - \bigo(z^7)
,\]
so
\[
f(z) &= 
\qty{z\inv + {1\over 6}z + {7\over 360}z^3 + \bigo(z^5)}
+
\qty{-{2\over \pi^2}z -{2\over \pi^4}z^3 - {2\over \pi^6} z^5 - \bigo(z^7)}
- z\inv \\
&= \qty{ {1\over 6} - {2\over \pi^2}}z + \qty{{7\over 360} - {2\over \pi^4} }z^3 + \bigo(z^5)
.\]
:::

:::{.solution title="Comparing orders of vanishing"}
Write
\[
f(z) = {z-\sin(z) \over z\sin(z)} - {2z\over z^2-\pi^2}
,\]

For $z=0$, the 2nd term doesn't contribute to zero/pole order.
For the first, take an expansion:
\[
f_1(z) 
&= {z - \qty{ z + c_3z^3 + \bigo(z^5)} \over z \qty{z + c_3z^3 + \bigo(z^5)} } \\ \\
&= { -c_3z^3 + \bigo(z^5)\over z^2 + \bigo(z^4) }
,\]
so there is a zero of order 3 in the numerator and of order 2 in the denominator, making the singularity removable.
A similar argument works at $z=\pm \pi$.
:::

:::{.exercise title="Removable singularities for derivatives"}
Suppose $f$ is meromorphic. Show that if $z_0$ is a removable singularity of $f$, then it is also a removable singularity of $f'$.

#complex/exercise/work

:::

:::{.exercise title="Bounded derivatives imply removable singularities"}
Suppose $f$ is holomorphic on $\DD\smz$ and there exist $M, k$ such that
\[
\abs{f^{(k)}(z)} \leq {M\over \abs{z}^k} && \forall 0 < \abs z < 1
.\]

Show that if $f$ has a singularity at $z=0$, then it must be removable.

#complex/exercise/completed

:::

:::{.concept}
\envlist

- $\dd{}{z}$ is a left-shift on power series, $z^m$ is a right-shift.
- $f'$ has the same poles as $f$, possibly with worse order due to the left-shift.
  - In general, if $z_0$ is an order $\ell$ pole of $f$, then it is at least an order $\ell + m$ pole of $f^{(m)}$.

:::

:::{.solution}
Define $F(z) \da z^k f^{(k)}(z)$ and note that $\abs{F(z)} \leq M$ on $\DD\smz$.

If $f$ has an essential singularity at $z=0$, then so does $F$ by considering power series expansions:
\[
f(z) = \sum_{k\in \ZZ} c_k z^k 
\implies z^m f^{(m)}(z) = \sum_{k\leq 1} \tilde c_k z^{-k} + \sum_{k\geq m}\tilde c_{k}z^{k}
,\]
which will still have infinitely many terms in its principal part at $0$.
However, if $F$ had an essential singularity, the image of $F$ in a neighborhood of $0$ would be dense in $\CC$ by Casorati-Weierstrass, contradicting that its image is bounded (by $M$). 

Suppose instead $z=0$ is a pole of order $\ell$ of $f$, so $\abs{f(z)}\to \infty$ as $z\to 0$.
Then again by considering power series expansions, $z=0$ remains a pole of $F$, now of order at worst $\ell$:
\[
f(z) = \bigo(z^{\ell}) 
\implies z^m f^{(m)}(z) \approx z^m \cdot \bigo(z^{\ell - m}) = \bigo(z^\ell)
.\]
But if this is an order $\ell$ pole of $F$, then $\lim_{z\to 0} \abs{F(z)} = \infty$ and $\lim_{z\to 0} z^\ell F(z))$ is finite and nonzero.
Apply the assumed bound yields the last contradiction:
\[
z^{\ell}F(z) = z^{\ell + m}f(z) \leq z^{\ell + m} \cdot Mz^{-m} = z^{\ell} \convergesto{z\to 0} 0
.\]
$\contradiction$

:::

:::{.exercise title="When bounds imply removability"}
Suppose $f$ is holomorphic with $z_0 = 0$ an isolated singularity, and suppose there is some neighborhood of $0$ on which
\[
\abs{f(z)} \leq \abs{z}^{-{ 1\over 2}}
.\]
Show that $z_0$ is removable.

> Warning: Riemann's removable singularity theorem won't apply to $z^{1\over 2}f(z)$ since $z^{1\over 2}$ is highly singular at $z=0$.

#complex/exercise/completed

:::

:::{.solution}
Using the inequality,
\[
\abs{(z-0)f(z)} \leq \abs{z}^{1\over 2}\convergesto{\abs{z}\to 0}0
,\]
so $z=0$ is removable by Riemann's removable singularity theorem.
:::

