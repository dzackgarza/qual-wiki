---
order: 50
---

# Laurent and Power Series

:::{.definition title="Analytic"}
A function $f:\Omega \to \CC$ is *analytic* at $z_0\in \Omega$ iff there exists a power series $g(z) = \sum a_n (z-z_0)^n$ with radius of convergence $R>0$ and a neighborhood $U\ni z_0$ such that $f(z) = g(z)$ on $U$.
:::

:::{.fact title="Generalized Binomial Theorem"}
Define $(n)_k$ to be the falling factorial 
\[
\prod_{j=0}^{k-1} (n-k) = n(n-1)\cdots(n-k+1)
\]
and set ${n\choose k} \da (n)_k/k!$, then
\[
(x+y)^n = \sum_{k\geq 0} {n\choose k} x^{k}y^{n-k}
.\]
:::

:::{.fact title="Some useful series"}
\[
\sum_{k=1}^{n} k 
  &=\frac{n(n+1)}{2} \\
\sum_{k=1}^{n} k^{2} 
  &=\frac{n(n+1)(2 n+1)}{6} \\
\sum_{k=1}^{n} k^{3} 
  &=\frac{n^{2}(n+1)^{2}}{4}  \\
\sum_{0\leq k \leq N} z^k 
  &= {1 - z^{N+1} \over 1-z} \\
{1\over 1-z} &= \sum_{k\geq 0} z^k \\
e^z &= \sum_{k\geq 0} {z^k \over k!} \\
\sin(z) 
  &= \sum_{\substack{ k \geq 1 \\ \text{odd} }} (-1)^{k+1 \over 2} {z^k \over k!} \\
  &= z - {1\over 3!}z^3 + {1\over 5!}z^5 + \cdots \\ \\
\cos(z) 
  &= \sum_{\substack{ k \geq 0 \\ \text{even}} } (-1)^{k\over 2} {z^k \over k!} \\
  &= 1 - {1\over 2!}z^2 + {1\over 4!}z^4 + \cdots \\ \\
\cosh(z) &= \sum_{k\geq 0} { z^{2k} \over (2k)! } \\
&= 1 + {1\over 2!}z^2 + {1\over 4!}z^4 + \cdots \\ \\
\sinh(z) &= \sum_{k\geq 0} { z^{2k+1} \over (2k+1)! } \\
&= z + {1\over 3!}z^3 + {1\over 5!}z^5 + \cdots \\ \\
\log(1-z) 
  &= \sum_{k \geq 0} {z^k\over k} \quad \abs{z} < 1 \\ \\
\dd{}{z} \sum_{k=0}^\infty a_k z^k 
  &= \sum_{k=0}^\infty a_{k+1}z^k \\
(1+x)^{1/2} 
  &= 1 + (1/2)x + {(1/2)(-1/2) \over 2!}x^2 + {(1/2)(-1/2)(-3/2) \over 3!}x^3 + \cdots \\
  &= 1 + {1\over 2} x - {1\over 8}x^2 + {1\over 16}x^3 - \cdots
\]
:::

:::{.fact}
Useful trick for expanding square roots:
\[
\sqrt{z} = \sqrt{z_0 + z - z_0} = \sqrt{z_0 \qty{ 1 + {z-z_0 \over z} }} = \sqrt{z_0} \sqrt{1+u},\quad u\da {z-z_0 \over z} \\
\implies \sqrt{z} = \sqrt{z_0} \sum_{k\geq 0} {1/2 \choose k} \qty{z- z_0 \over z}^k
.\]

:::

:::{.fact}
The product of two sequences is given by the Cauchy product
\[
\sum a_kz^k \cdot \sum b_k z^k = \sum c_k z^k,\quad c_k \da \sum_{j\leq k} a_k b_{k-j}
.\]
:::

\todo[inline]{Add series tricks.}

:::{.fact title="Multiplicatively inverting a series"}
Using the general ring theory fact that $A(z) \da \sum_{k\geq 0} a_k z^k \in R[[z]]$ is invertible iff $a_0$ is invertible in $R$, power series over fields can always be inverted.
There is a formula: writing $B(z) \da \sum_{k\geq 0 } b_k z^k \da 1/A(z) \in \CC[[z]]$, the coefficients can be inductively computed as
\[
b_0 &= a_0\inv \\
b_n &= -a_0\inv \sum_{1\leq i \leq n} a_i b_{n-i} \\
&= -a_0\inv \sum_{0\leq i \leq n-1} a_{n-i}b_i \\
&= -{1\over a_0}\qty{a_nb_0 + a_{n-1}b_1 + \cdots + a_1 b_{n-1} }
.\]
:::

:::{.remark}
How to prove this:
\[
\qty{\sum a_k z^k}\qty{\sum b_k z^k} = 1
\implies 
a_0b_0 &=1 \\
a_0b_1 + a_1b_0 &= 1 \\
a_0b_2 + a_1b_1 + a_2b_0 &= 1 \\
\vdots \quad&\quad \vdots
\]

:::

:::{.example title="?"}
For example, for $A(z) = 1-z$, this recovers $(1-z)\inv = \sum_{k\geq 0} z_k$.
Noting $a_0 = 1, a_1 = -1$, we have

- $b_0 = 1/a_0 = 1$
- $b_1 = -{1\over a_0}(a_1 b_0) = -1(-1\cdot 1) = 1$
- $b_2 = -{1\over a_0}(a_2 b_0 + a_1 b_1) = -1(0\cdot 1 + -1\cdot 1) = 1$, 

and so on, so
\[
{1\over A(z)} = 1 + 1\cdot z + 1\cdot z^2 + \cdots
.\]

:::

:::{.example title="?"}
To compute the inverse of $A(z) \da (2z-1)$, note $a_0 = -1, a_1 = 2$, so

- $b_0 = 1/a_0 = -1$
- $b_1 = -{1\over a_0}(a_1b_0) = 1(2\cdot -1) = -2$
- $b_2 = -{1\over a_0}(a_2 b_0 + a_1 b_1) = 1(0\cdot 1 + 2\cdot -2) = -4$
- $b_3 = -{1\over a_0}(a_3b_0 + a_2 b_1 + a_1 b_2) = 1(0 + 0 + 2\cdot -4) = -8$

so
\[
{1\over 1-2z} = -1 - 2z - 4z^2 - 8z^3 \cdots 
= - \sum_{k\geq 0} (2z)^k
.\]
:::


:::{.fact title="Using geometric series to invert power series"}
There is an alternative that sometimes (?) works: writing $A(z) = \sum_{k\geq 0} a_k z_k$, invert by formal manipulations:
\[
{1\over A(z)} = {1 \over 1- (1-A(z))} = \sum_{k\geq 0} A(z)^k z^k
.\]
:::


:::{.example title="Inverting using geometric series"}

:::



# Analyticity

:::{.proposition title="Power Series are Smooth"}
Any power series is smooth (and thus holomorphic) on its disc of convergence, and its derivatives can be obtained using term-by-term differentiation:
\[
\dd{}{z} f(z) = \dd{}{z} \sum_{k\geq 0} c_k (z-z_0)^k = \sum_{k\geq 1} kc_k (z-z_0)^k
.\]
Moreover, the coefficients are given by 
\[
c_k = {f^{(n)}(z_0) \over n! }
.\]
:::

:::{.theorem title="Function value as a convolution"}
For any $p\in U$,
\[
f(p) = {1\over 2\pi i }\int_{\bd U} {f(z) \over z-p} \dz
.\]
:::

:::{.corollary title="Formula for Laurent coefficients"}
Differentiating under the integral above yields
\[
c_k = \frac{f^{(k)}(p)}{k !}=\frac{1}{2 \pi i} \int_{\partial U} \frac{f(z) }{(z-p)^{k+1}} \dz
= {1 \over 2\pi R^n}\int_0^{2\pi} f(z_0 + Re^{i\theta})e^{-in\theta} \dtheta
.\]
For $R \da d(p, \bd U)$,
this yields a bound
\[
f(z) = \sum c_kz_k \implies \abs{c_k} \leq {\sup_{z\in \bd U}f(z) \cdot \length(\bd U) \over 2\pi R^{k+1}}
,\]
so $\limsup \abs{c_k}^{1\over k} < R\inv$, showing that $\sum c_k (z-p)^k$ has radius of convergence at least $R$ and is represented by its power series in $D_R(p)$.
This implies that $f$ is smooth at $p\in U$, and thus can only have poles on $\bd U$.
:::

:::{.theorem title="Holomorphic implies analytic"}
If $f$ is analytic on $D_R(p)$, then $f(z) = \sum c_k(z-p)^k$ on this disc.
:::

:::{.proof title="?"}
Reduce to $z\in \DD$, then for a fixed $z$ and any $w\in S^1$,
\[
{1\over w-z} = {1\over w} \qty{ 1 + \qty{z\over w} + \qty{z\over w}^2 + \cdots}
,\]
which converges uniformly on $S^1$.
Then
\[
f(z)=\frac{1}{2 \pi i} \int_{S^{1}} \frac{f(w) }{w-z} \dw 
= \sum z^{k} \frac{1}{2 \pi i} \int_{S^{1}} \frac{f(w)}{w^{k+1}} \dw 
=\sum c_{k} z^{k}
.\]

:::

:::{.proposition title="Exponential is uniformly convergent in discs"}
$f(z) = e^z$ is uniformly convergent in any disc in $\CC$.
:::

:::{.proof}
Apply the estimate
\[  
\abs{e^z} \leq \sum {\abs {z}^n \over n!} = e^{\abs{z}}
.\]
Now by the $M\dash$test, 
\[  
\abs{z} \leq R < \infty \implies \abs{\sum {z^n \over n!}} \leq e^R < \infty
.\]
:::

# Analytic Number Theory's Faves

:::{.lemma title="Dirichlet's Test"}
Given two sequences of real numbers \( \ts{ a_k } , \ts{ b_k } \) which satisfy

1. The sequence of partial sums \( \ts{ A_n } \) is bounded,
2. $b_k \searrow 0$.

then 
\[
\sum_{k\geq 1} a_k b_k < \infty
.\]
:::

:::{.proof title="?"}

> See <http://www.math.uwaterloo.ca/~krdavids/Comp/Abel.pdf>

Use summation by parts.
For a fixed $\sum a_k b_k$, write 
\[
\sum_{n=1}^m x_n Y_n + \sum_{n=1}^m X_n y_{n+1} = X_m Y_{m+1}
.\]
Set $x_n \da a_n, y_N \da b_n - b_{n-1}$, so $X_n = A_n$ and $Y_n = b_n$ as a telescoping sum.
Importantly, all $y_n$ are negative, so $\abs{y_n} = \abs{b_n - b_{n-1}} = b_{n-1} - b_n$, and moreover $a_n b_n = x_n Y_n$ for all $n$.
We have
\[
\sum_{n\geq 1} a_n b_n 
&= \lim_{N\to\infty} \sum_{n\leq N} x_n Y_n \\
&= \lim_{N\to\infty} \sum_{n\leq N} X_N Y_N - \sum_{n\leq N} X_n y_{n+1} \\
&= - \sum_{n\geq 1} X_n y_{n+1},
\]
where in the last step we've used that 
\[
\abs{X_N} = \abs{A_N}\leq M \implies \abs{X_N Y_{N} } = \abs{X_N} \abs{b_{n+1}} \leq M b_{n+1} \to 0
.\]
So it suffices to bound the latter sum:
\[
\sum_{k\geq n}\abs{ X_k y_{k+1} } 
&\leq M \sum_{k\geq 1} \abs{y_{k+1}}\\
&\leq M \sum_{k\geq 1} b_{k} - b_{k+1} \\
&\leq 2M(b_1 - b_{n+1})\\
&\leq 2M b_1
.\]

:::

:::{.theorem title="Abel's Theorem"}
If $\sum_{k=1}^\infty c_k z^j$ converges on $\abs{z} < 1$ then 
\[
\lim_{z\to 1^-} \sum_{k\in \NN} c_k z^k = \sum_{k\in \NN} c_k
.\]
:::

:::{.lemma title="Abel's Test"}
If $f(z) \da \sum c_k z^k$ is a power series with $c_k \in \RR^{\geq 0}$ and $c_k\decreasesto 0$, then $f$ converges on $S^1$ except possibly at $z=1$.
:::

:::{.example title="application of Abel's theorem"}
What is the value of the alternating harmonic series?
Integrate a geometric series to obtain
\[
\sum {(-1)^k z^k \over n} = \log(z+1) && \abs{z} < 1
.\]
Since $c_k \da (-1)^k/k \decreasesto 0$, this converges at $z=1$, and by Abel's theorem $f(1) = \log(2)$.

:::

:::{.remark}
The converse to Abel's theorem is false: take $f(z) = \sum  (-z)^n = 1/(1+z)$.
Then $f(1) = 1-1+1-\cdots$ diverges at 1, but $1/1+1 = 1/2$.
So the limit $s\da \lim_{x\to 1^-} f(x) 1/2$, but $\sum a_n$ doesn't converge to $s$.
:::

:::{.proposition title="Summation by Parts"}
Setting $A_n \da \sum_{k=1}^n b_k$ and $B_0 \da 0$,
\[
\sum_{k=m}^n a_k b_k 
&= A_nb_n - A_{m-1} b_m - \sum_{k=m}^{n-1} A_k(b_{k+1} - b_{k})
.\]
Compare this to integrating by parts:
\[
\int_a^b f g = F(b)g(b) - F(a)g(a) - \int_a^b Fg'
.\]

Note there is a useful form for taking the product of sums:
\[
A_{n} B_{n}=\sum_{k=1}^{n} A_{k} b_{k}+\sum_{k=1}^{n} a_{k} B_{k-1}
.\]

:::

:::{.proof title="?"}
An inelegant proof: define $A_n \da \sum_{k\leq n} a_k$, use that $a_k = A_k - A_{k-1}$, reindex, and peel a top/bottom term off of each sum to pattern-match.
\

Behold:
\[
\sum_{m\leq k \leq n} a_k b_k 
&= \sum_{m\leq k \leq n} (A_k - A_{k-1}) b_k \\
&= \sum_{m\leq k \leq n} A_kb_k - \sum_{m\leq k \leq n} A_{k-1} b_k \\
&= \sum_{m\leq k \leq n} A_kb_k - \sum_{m-1\leq k \leq n-1} A_{k} b_{k+1} \\
&= A_nb_n + \sum_{m\leq k \leq n-1} A_kb_k - \sum_{m-1\leq k \leq n-1} A_{k} b_{k+1} \\
&= A_nb_n - A_{m-1} b_{m} + \sum_{m\leq k \leq n-1} A_kb_k - \sum_{m\leq k \leq n-1} A_{k} b_{k+1} \\
&= A_nb_n - A_{m-1} b_{m} + \sum_{m\leq k \leq n-1} A_k(b_k - b_{k+1}) \\
&= A_nb_n - A_{m-1} b_{m} - \sum_{m\leq k \leq n-1} A_k(b_{k+1} - b_{k}) 
.\]

:::

:::{.proposition title="?"}
If $f$ is non-constant, then $f'$ is analytic and the zeros of $f'$ are isolated.
If $f,g$ are analytic with $f'=g'$, then $f-g$ is constant.
:::

# Exercises: Series

:::{.exercise title="Application of summation by parts"}
Use summation by parts to show that $\sin(n)/n$ converges.
:::

:::{.exercise title="1.20: Series convergence on the circle"}
Show that

1. $\sum kz^k$ diverges on $S^1$.
2. $\sum k^{-2} z^k$ converges on $S^1$.
3. $\sum k\inv z^k$ converges on $S^1\sm\ts{1}$ and diverges at $1$.
:::

:::{.solution}

1. Use that $\abs{z^k} = 1$ and $\sum c_kz^k < \infty \implies \abs{c_k} \to 0$, but $\abs{kz^k} = \abs{k} \to \infty$ here.
2. Use that absolutely convergent implies convergent, and $\sum \abs{k^{-2} z^k} = \sum \abs{k^{-2}}$ converges by the $p\dash$test.
3. If $z=1$, this is the harmonic series. 
  Otherwise take $a_k = 1/k, b_k = e^{i k \theta}$ where $\theta \in (0, 2\pi)$ is some constant, and apply Dirichlet's test.
  It suffices to bound the partial sums of the $b_k$.
  Recalling that $\sum_{k\leq N} r^k = (1-r^{N+1}) / (1-r)$,
  \[
  \norm{ \sum_{k\leq m} e^{ik\theta } } = \norm{1 - e^{i(m+1)\theta} \over 1 - e^{i\theta}} \leq {2 \over \norm{ 1- e^{i\theta}}} \da M
  ,\]
  which is a constant.
  Here we've used that two points on $S^1$ are at most distance 2 from each other.
:::

:::{.exercise title="Laurent expansions inside and outside of a disc"}
Expand $f(z) = {1\over z(z-1)}$ in both

- $\abs{z} < 1$
- $\abs{z} > 1$


:::

:::{.solution}
\[
{1\over z(z-1)} = -{1\over z}{1 \over 1-z} = -{1\over z}\sum z^k
.\]
and
\[
{1\over z(z-1)} = {1\over z^2(1 - {1\over z})} = {1\over z^2} \sum \qty{1\over z}^k
.\]


:::

:::{.exercise title="Laurent expansions about different points"}
Find the Laurent expansion about $z=0$ and $z=1$ respectively of the following function:
\[
f(z) \da {z+1 \over z(z-1)}
.\]

:::

:::{.solution}
Note: once you see that everything is in terms of powers of $(z-z_0)$, you're essentially done.
For $z=0$:
\[
{z+1 \over z(z-1)}
&= {1\over z} {z+1 \over z-1} \\
&= -{z+1\over z} {1\over 1-z} \\
&= -\qty{1 + {1\over z}}\sum_{k\geq 0} z^k
.\]

For $z=1$:
\[
{z+1 \over z(z-1)}
&= {1\over z-1}\qty{1 + {1\over z} } \\
&= {1\over z-1}\qty{1 + {1\over 1 - (1-z)} } \\
&= {1\over z-1} \qty{1 + \sum_{k\geq 0} (1-z)^k } \\
&= {1\over z-1} \qty{1 + \sum_{k\geq 0} (-1)^k (z-1)^k }
.\]
:::

:::{.exercise title="?"}
Show that a real-valued holomorphic function must be constant.
:::


:::{.exercise title="?"}
Show that $\prod_{n\in \ZZ} (1 + a_n) < \infty$ if $\ts{a_n} \in \ell_1(\ZZ)$.

:::



