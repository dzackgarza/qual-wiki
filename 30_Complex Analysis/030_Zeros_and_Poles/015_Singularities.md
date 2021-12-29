# Zeros and Singularities

## Definitions

:::{.remark}
On notation: for an analytic function $f$ expanded as a power series about $a$, write $v_a(f)$ as the $a\dash$adic valuation of $f$: expanding $f(z) = \sum_{k\in \ZZ} a_k (z-a)^k$ about $a$, define $v_a(f) = n$ iff $a_n\neq 0$ but $a_{\leq n} = 0$.
In other words, $v_a$ is the lowest power of $(z-a)$ occurring in a Laurent expansion of $f$ about $a$.
:::

:::{.definition title="Isolated singularities"}
A point $z_0$ is an **isolated singularity** if $f(z_0)$ is undefined but $f(z)$ is defined in a punctured neighborhood $D(z_0)\sm\ts{z_0}$ of $z_0$.

There is a classification of isolated singularities:

- Removable singularities, so $v_a(f) \in [0, \infty)$
- Poles, so $v_a(f) \in (-\infty, 0)$
- Essential singularities, so $v_a(f) = -\infty$, e.g. $\sin(z\inv )$ at $z=0$.
:::

:::{.warnings title="Branch singularities"}
Not all singularities are isolated, and thus don't fall into this classification.
One may also have **branch singularities**, e.g. $\Log(z)$ at $z=0$.
$f(z) \da z^{1\over 2}$ has a singularity at zero that does not fall under this classification -- the point $z=0$ is a **branch singularity** and $f$ admits no Laurent expansion around $z=0$.
A similar example: $\qty{z(z-1)}^{1\over 2}$ has two branch singularities at $z=0, 1$.
:::

:::{.remark title="Classification by Laurent expansion"}
Singularities can be classified by Laurent expansions $f(z) = \sum_{k\in \ZZ} c_k z^k$:

- Essential singularity: infinitely many negative terms.
- Pole of order $N$: truncated at $k = -N$, so $c_{N-\ell} = 0$ for all $\ell$.
- Removable singularity: truncated at $k=0$, so $c_{\leq -1} = 0$.
:::

:::{.remark title="Classification by limiting behavior"}
Isolated singularities can also be classified by their limiting behavior near the singularity:

- $\lim_{z\to z_0} f(z) < \infty$: removable (equivalently: bounded in a neighborhood).
- $\lim_{z\to z_0} f(z) = \infty$: pole.
- $\lim_{z\to z_0} f(z)$ does not exist: essential.

:::

:::{.definition title="Singularities at infinity"}
For any $f$ holomorphic on an unbounded region, we say $z=\infty$ is a singularity (of any of the above types) of $f$ if $g(z) \da f(1/z)$ has a corresponding singularity at $z=0$.
:::

## Removable

:::{.definition title="Removable Singularities"}
If $z_0$ is a singularity of $f$. then $z_0$ is a **removable singularity** iff
there exists a holomorphic function $g$ such that $f(z) = g(z)$ in a punctured neighborhood of $z_0$.
Equivalently,
\[
\lim_{z\to z_0}(z-z_0) f(z) = 0
.\]
Equivalently, $f$ is bounded on a neighborhood of $z_0$.
Equivalently, $v_{z_0}(f) \geq 0$


![](figures/2021-11-26_23-54-18.png)

:::

:::{.example title="Removable singularities"}
\envlist

- $f(z) \da \sin(z)/z$ has a removable singularity at $z=0$, and one can redefine $f(0) \da 1$.
- If $f(z) = p(z)/q(z)$ with $q(z_0)=0$ and $p(z_0)=0$, then $z_0$ is removable with $f(z_0)\da p'(z_0)/q'(z_0)$.
:::

:::{.theorem title="Riemann's removable singularity theorem"}
Suppose $f$ is holomorphic on $\Omega\sm\ts{z_0}$.
TFAE:

- $z_0$ is a pole of order $0$.
- $z_0$ is a removable singularity of $f$.
- There exists some neighborhood of $z_0$ on which $f$ is bounded.
- $(z-a)f(z) \convergesto{z\to z_0} 0$
- $f$ admits a holomorphic extension $F$ to all of $\Omega$
- $f$ admits a continuous extension $F$ to all of $\Omega$.
- $f$ admits a Laurent expansion about $z_0$ with vanishing principal part, i.e. $f(z) = \sum_{k\geq 0}c_k (z-z_0)^k$.

:::

:::{.proof title="?"}
Take $\gamma$ to be a circle centered at $z_0$ and use
\[
f(z) \da \int_\gamma { f(\xi) \over \xi - z} \dx
.\]
This is valid for $z\neq z_0$, but the right-hand side is analytic. (?)
:::

#complex/exercise/work 

![](figures/2021-10-29_01-30-50.png)

![[attachments/Pasted image 20211215021531.png]]
![[attachments/Pasted image 20211215021546.png]]


:::{.theorem title="Riemann Extension Theorem"}
A singularity of a holomorphic function is removable if and only if the function is bounded in some punctured neighborhood of the singular point.
:::

## Essential

:::{.definition title="Essential Singularity"}
A singularity $z_0$ is *essential* iff it is neither removable nor a pole.
Equivalently, a Laurent series expansion about $z_0$ has a principal part with infinitely many terms.
:::

:::{.example title="Essential singularities"}
$f(z) \da e^{1/z}$ has an essential singularity at $z=0$, since we can expand and pick up infinitely many negative terms:
\[
e^{1/z} = 1 + {1\over z} + {1\over 2! z^2} + \cdots
.\]
In fact there exists a neighborhood of zero such that $f(U) = \CC\smz$.
Similarly $g(z) \da \sin\qty{1\over z}$ has an essential singularity at $z=0$, and there is a neighborhood $V$ of zero such that $g(V) = \CC$.
:::

:::{.example title="?"}
The singularities of a rational function are always isolated, since there are finitely many zeros of any polynomial.
The function $F(z) \da \Log(z)$ has a singularity at $z=0$ that is **not** isolated, since every neighborhood intersects the branch cut $(-\infty, 0) \cross \ts{ 0 }$, where $F$ is not even defined.
The function $G(z) \da 1/\sin(\pi/z)$ has a non-isolated singularity at 0 and isolated singularities at $1/n$ for all $n$.
:::

## Zeros

:::{.proposition title="Zeros and their orders"}
A **zero** of an analytic function on a domain $\Omega$ is any $z_0$ such that $f(z_0)=0$, with no further conditions.
If $f$ is analytic and not identically zero on $\Omega$ with $f(z_0) = 0$, then there exists a  neighborhood $U\ni z_0$ and function $g$ that is holomorphic and nonvanishing on $U$ such that 
\[
f(z) = (z-z_0)^n g(z)
.\]
We refer to $z_0$ as a **zero of order $n$**.
Equivalently, $f^{(n-1)}(z_0)=0$ but $f^{(n)}(z) \neq 0$, so the Laurent expansion has the form $f(z) = \sum_{k\geq n} c_k (z-z_0)^k$ where $c_n\neq 0$.
:::

:::{.remark}
On terminology: if the order of $z_0$ for $f$ is $n$, we say $f$ **vanishes to order $n$**.
:::

:::{.proof title="of existence and uniqueness of order"}
Use that $\Omega$ is connected to find some neighborhood $U$ on which $f$ is not identically zero.
WLOG assume $z_0=0$. Expand $f$ as an honest power series at $z_0$ to write
\[
f(z) = \sum_{k\geq 0}c_k z^k = z^n\qty{c_n + c_{n+1}z + \cdots} \da z^n g(z)
,\]
where $a_n$ is the minimal nonvanishing coefficient.
Since $a_n\neq 0$, we have $\lim_{z\to z_0} g(z) = a_n \neq 0$, so $g$ is nonvanishing in some neighborhood of $z_0$.
Uniqueness follows from writing 
\[
z^n g(z) = z^m h(z) \implies g(z) = z^{m-n} h(z) 
,\]
assuming $m>n$, but then taking $z\to z_0 =0$ on the RHS yields $g(z) = 0$, a contradiction.
:::

:::{.proposition title="Zeros of holomorphic functions are isolated"}

![](figures/2021-12-15_02-12-08.png)

:::

## Poles

:::{.definition title="Poles (and associated terminology)"}
Let $f$ be a meromorphic function with an isolated singularity at $z_0$.
TFAE:

- $z_0$ is a pole of $f$ of order $n$.
- $\abs{f(z)}\convergesto{z\to z_0} \infty$
- $z_0$ is a zero of order $n$ of $g(z) \da {1\over f(z)}$, and $g$ is holomorphic in a neighborhood of $z_0$
- $f(z) = (z-z_0)^{-n}h(z)$ where $h$ is holomorphic in a punctured neighborhood of $z_0$.
- $f$ admits a Laurent expansion of the form
\[
f(z) = \sum_{k\geq -n} c_k (z-z_0)^k, && c_{-n}\neq 0
.\]

:::

:::{.proposition title="Well-definedness of pole order"}
In this case there exists a minimal $n$ and a holomorphic $h$ such that
\[  
f(z) = \qty{z-z_0}^{-n} h(z)
.\]
Such an $n$ is the *order* of the pole.
A pole of order 1 is said to be a *simple pole*.
:::

:::{.proof title="?"}
Use that $z_0$ is a zero of $1/f$ to write
\[
{1\over f(z) } = (z-z_0)^n g(z)
,\]
for $h$ holomorphic and nonvanishing in a neighborhood of $z_0$.
Taking reciprocals yields
\[
f(z) = (z-z_0)^{-n} h(z) && \quad h(z) \da {1\over g(z)}
.\]
:::

:::{.example title="Of using this characterization"}
Claim: if $f$ has a pole of order $m$ at $z_0$, then $g(z) \da f(z^2)$ has a pole of order $2m$ at $z_0$.
WLOG assume $z_0=0$.
Note that this is clear by multiplying Laurent expansions about $z_0$:
\[
f(z) = \sum_{k\geq -m} c_k z^k \implies g(z) = \sum_{k\geq -m} c_k z^{2k} 
= {c_{-m} \over z^{2m}} + \cdots
.\]
Using the other characterization, write $f(z) = z^{-m} h(z)$ with $g$ holomorphic and nonzero in a neighborhood $U$ of $z_0$, so in particular $h(0) \neq 0$.
Then $f(z^2) = z^{-2m} h(z^z)$ and $h(z^2)\mid_{z=0} = h(0) \neq 0$.
:::

:::{.definition title="Principal Part and Residue at poles"}
If $f$ has a pole of order $n$ at $z_0$, then there exist a holomorphic $G$ in a neighborhood of $z_0$ such that
\[
f(z) = {a_{-n} \over (z-z_0)^n } + \cdots + {a_{-1} \over z-z_0} + G(z) \da P(z) + G(z)
.\]

The term $P(z)$ is referred to as the *principal part of $f$ at $z_0$* consists of terms with negative degree, and the *residue* of $f$ at $z_0$ is the coefficient $a_{-1}$.
:::

## Exercises

:::{.exercise title="Poles of $1/\sin$"}
Show that all singularities of $1/\sin(z)$ are poles of order 1.

#complex/exercise/work

:::

:::{.exercise title="Removable singularities for derivatives"}
Suppose $f$ is meromorphic. Show that if $z_0$ is a removable singularity of $f$, then it is also a removable singularity of $f'$.

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

