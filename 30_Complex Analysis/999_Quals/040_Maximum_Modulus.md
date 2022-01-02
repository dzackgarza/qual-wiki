---
order: 40
---

# Maximum Modulus

## Spring 2020.7 #complex/qual/completed

^aff739

:::{.problem title="?"}
Let $f$ be analytic on a bounded domain $D$, and assume also that $f$ that is continuous and nowhere zero on the closure $\bar{D}$. 

Show that if $|f(z)|=M$ (a constant) for $z$ on the boundary of $D$, then $f(z)=e^{i \theta} M$ for $z$ in $D$, where $\theta$ is a real constant.
:::

:::{.solution}
By the maximum modulus principle, $\abs{f} \leq M$ in $\bar{D}$.
Since $f$ has no zeros in $\bar{D}$, $g\da 1/f$ is holomorphic on $D$ and continuous on $\bar{D}$.
So the maximum modulus principle applies to $g$, and $M\inv \geq \abs{g} = 1/\abs{f}$, so $\abs{f} \leq M$.
Combining these, $\abs{f(z)} = M$, so $f(z) = \lambda M$ where $\lambda$ is some constant with $\abs{\lambda}=1$.
This is on the unit circle, so $\lambda = e^{i\theta}$ for some fixed angle $\theta$.
:::


## Fall 2020.6 #complex/qual/completed

^189826

:::{.problem title="?"}
Suppose that $U$ is a bounded, open and simply connected domain in $\mathbb{C}$ and that $f(z)$ is a complex-valued non-constant continuous function on $\bar{U}$ whose restriction to $U$ is holomorphic.

- Prove the maximum modulus principle by showing that if $z_{0} \in U$, then

$$
\left|f\left(z_{0}\right)\right|<\sup \{|f(z)|: z \in \partial U\} .
$$

- Show furthermore that if $|f(z)|$ is constant on $\partial U$, then $f(z)$ has a zero in $U$ (i.e., there exists $z_{0} \in U$ for which $f\left(z_{0}\right)=0$ ).

:::

:::{.solution}
Let $M\da \sup_{z\in \bd U}\abs{f(z)}$.
If $M=0$, then $f$ must be the constant zero function, so assume $M>0$.

Suppose toward a contradiction that there exists a $z_0 \in U$ with $\abs{f(z_0)} = M$.
Note that the map $z\mapsto \abs{z}$ is an open in discs that don't intersect $z=0$.
Since $f$ is holomorphic, by the open mapping theorem $f$ is an open map, so consider $D_\eps(z_0)$ a small disk not containing $0$.
Then $f(D_\eps(z_0))$ is open, and the composition $z\mapsto f(z) \mapsto \abs{f(z)}$ is an open map $D_\eps(z_0)\to \RR$.
Now if $f$ is nonconstant, $\abs{f(D_\eps(z_0))} \contains (M-\eps, M+\eps)$ contains some open interval about $M$, which contradicts maximality of $f$ at $z_0$.

> See notes for a proof using the mean value theorem.

Suppose toward a contradiction that $f$ has no zeros in $U$.
Then $g(z) \da 1/f(z)$ is holomorphic in $U$.
Now if $\abs{f(z)} = C$ on $\bd U$, we have $\abs{g(z)} = \abs{1\over f(z)} = {1\over C}$ on $\bd U$, so $\max_{z\in U} \abs{f(z)} = C$ and $\min_{\abs{f(z)}} = {1\over C}$.
Since $\abs{f(z)}$ is constant on the boundary, we must have $\max \abs{f(z)} = \min \abs{f(z)} = C$, so $f$ is constant on $\bd U$.
By the identity principle, $f$ is constant on $U$, a contradiction.
:::

## Spring 2020 HW 3, SS 3.8.15 #complex/exercise/completed

:::{.problem title="?"}
Use the Cauchy inequalities or the maximum modulus principle to solve the following problems:

a. 
Prove that if $f$ is an entire function that satisfies
\[
\sup _{|z|=R}|f(z)| \leq A R^{k}+B
\]
for all $R>0$, some integer $k\geq 0$, and some constants $A, B > 0$, then $f$ is a polynomial of degree $\leq k$.

b. 
Show that if $f$ is holomorphic in the unit disc, is bounded, and converges uniformly to zero in the sector $\theta < \arg(z) < \phi$ as $\abs{z} \to 1$, then $f \equiv 0$.

c. 
Let $w_1, \cdots w_n$ be points on $S^1 \subset \CC$.
Prove that there exists a point $z\in S^1$ such that the product of the distances from $z$ to the points $w_j$ is at least 1.
  Conclude that there exists a point $w\in S^1$ such that the product of the above distances is *exactly* 1.

d. 
Show that if the real part of an entire function is bounded, then $f$ is constant.

:::

:::{.solution title="Part 1"}
\[
\abs{ f(z_0) }
&= \abs{ {1\over 2\pi i} \oint_{\abs{z-z_0} = R } {f(z) \over (z-z_0)^{n+1} }  \dz } \\
&\leq {1\over 2\pi } \oint_{\abs{z-z_0} = R } \abs{f(z)} R^{-(n+1)}   \dz \\
&\leq {1\over 2\pi }\sup_{\abs{z-z_0} = R} \abs{f(z)} R^{-(n+1)} \cdot 2\pi R \\
&= \sup_{\abs{z-z_0} = R} \abs{f(z)} R^{-n} \\
&\leq (AR^k + B)R^{-n} \qquad \text{ if } z_0 = 0 \\
&= AR^{k-n} + BR^{-n} \\
&\to 0 
,\]
provided $k-n< 0$, so $n>k$.
Since $f$ is entire, write
\[
f(z) 
= \sum_{n\geq 0} f^{(n)}(0) {z^n\over n!}
= \sum_{0\leq n\leq k} f^{(n)}(0) {z^n\over n!}
,\]
making $f$ a polynomial of degree at most $k$.
:::

:::{.solution title="Part 2"}
Write $S_\phi \da \ts{0<\Arg(z) < \phi}$ and choose $n$ large enough so that 
\[
\DD \subseteq S \union \zeta_n S \union \zeta_n^2 S \union\cdots\union \zeta_{n}^{n-1}S
,\]
i.e. so that the rotated sectors cover the disc.
By uniform convergence of $f$ to $0$ on $S$, choose $r<1$ small enough so that $\abs{f(z)} < \eps$ for $\abs{z} < r$ in $S$.
Note that $\DD_r \subseteq \Union_{k=0}^{n-1} \zeta_n^k S_r$, where $S_r \da \ts{z\in S \st \abs{z} \leq r}$ is a subsector of radius $r$.

By the MMP, let $M$ be the maximum of $f$ on $\DD$, which is attained at some point on $S^1$.
Then $\abs{f} < M$ on every $\zeta_n^k S_r$.
Now define
\[
g(z) \da f(z) \prod_{k=1}^{n-1} f(\zeta_n^k z) \da f(z) \prod_{k=1}^{n-1}f_k(z)
.\]
Note that $\abs{f(z)}\leq \eps$ and $\abs{f_k(z)} \leq M$, so
\[
\abs{g(z)}\leq \eps \cdot M^{n-1} \convergesto{\eps\to 0} 0
.\]
since $M$ is a constant.
So $g(z) \equiv 0$ on $\DD_r$, and by the identity principle, on $\DD$.
Thus some factor $f_k(z)$ is identically zero. 
But if $f(\zeta_n^k z)\equiv 0$ on $\DD$, then $f(z) \equiv 0$ on $\DD$, since every $z\in \DD$ can be written as $\zeta_n^k w$ for some $w\in \DD$.

:::

:::{.solution title="Part 3"}
Consider
\[
f(z) \da \prod_{1\leq k \leq n} (w_k - z)
.\]
Then $f$ is holomorphic and nonconstant on $\DD$, so attains a maximum $M$ on $S^1$.
Moreover, $\abs{f(z)} = \prod \abs{w_k-z}$ is exactly the product of distances from $z$ to the $w_k$.
Moreover, since $\abs{f(0)} = \prod\abs{w_k} = 1$, we must have $M>1$.

Now note that $f(w_k) = 0$ and $f$ is continuous in $\DD$.
So $\abs{f(z)} \in [0, M] \subseteq \RR$ where $M>1$, so by the intermediate value theorem, $\abs{f(z)} = 1$ for some $z$.
:::

:::{.solution title="Part 4, using MMP"}
Write $f=u+iv$ where by assumption $u$ is bounded.
Both $u$ and $v$ are harmonic, so if $\abs{u} \leq M$ on $\CC$, then there is some disc where $\abs{u} = M$ for some point in the interior.
By the MMP for harmonic functions, $u$ is constant on $\CC$.
So $u_x, u_y = 0$, and by Cauchy-Riemann, $v_x, v_y = 0$, so $v'=0$ and $v$ is constant, making $f$ constant.
:::

:::{.solution title="Part 4, using Liouville"}

Consider $g(z) \da e^{f(z)}$, then $\abs{g(z)} = e^{\Re(z)}$ is entire and bounded and thus constant by Liouville's theorem.
So $g'(z) = 0$, but on the other hand $g'(z) = f'(z) e^{f(z)} = 0$, so $f'(z) = 0$ and $f$ must be constant since $e^f$ is nonvanishing.

:::

## Spring 2020 HW 3, 3.8.17 #complex/exercise/work

Let $f$ be non-constant and holomorphic in an open set containing the closed unit disc.

a. 
Show that if $\abs{f(z)} = 1$ whenever $\abs{z} = 1$, then the image of $f$ contains the unit disc.

> Hint: Show that $f(z) = w_0$ has a root for every $w_0 \in \DD$, for which it suffices to show that $f(z) = 0$ has a root.
> Conclude using the maximum modulus principle.

b. 
If $\abs{f(z)} \geq 1$ whenever $\abs{z} = 1$ and there exists a $z_0\in \DD$ such that $\abs{f(z_0)} < 1$, then the image of $f$ contains the unit disc.

## Spring 2020 HW 3, 3.8.19 #complex/exercise/work

Prove that maximum principle for harmonic functions, i.e.

a. If $u$ is a non-constant real-valued harmonic function in a region $\Omega$, then $u$ can not attain a maximum or a minimum in $\Omega$.

b. Suppose $\Omega$ is a region with compact closure $\bar \Omega$.
    If $u$ is harmonic in $\Omega$ and continuous in $\bar \Omega$, then 
    \[
    \sup _{z \in \Omega}|u(z)| \leq \sup _{z \in \bar \Omega -\Omega}|u(z)|
    .\]

> Hint: to prove (a), assume $u$ attains a local maximum at $z_0$.
> Let $f$ be holomorphic near $z_0$ with $\Re(f) = u$, and show that $f$ is not an open map.
> Then (a) implies (b).

## Spring 2020 HW 3.9 #complex/exercise/work

Let $f$ be analytic in a region $D$ and $\gamma$ a rectifiable curve in
$D$ with interior in $D$.

Prove that if $f(z)$ is real for all $z\in \gamma$, then $f$ is constant.

## Spring 2020 HW 3.14 #complex/exercise/work

Let $f$ be nonzero, analytic on a bounded region $\Omega$ and continuous
on its closure $\overline \Omega$.

Show that if $\abs{f(z)} \equiv M$ is constant for $z\in \partial \Omega$, then $f(z) \equiv Me^{i\theta}$ for some real constant $\theta$.


## Tie's Extra Questions: Spring 2015 #complex/exercise/work

Let
$\displaystyle{\psi_{\alpha}(z)=\frac{\alpha-z}{1-\bar{\alpha}z}}$
with $|\alpha|<1$ and ${\mathbb D}=\{z:\ |z|<1\}$. Prove that

-   $\displaystyle{\frac{1}{\pi}\iint_{{\mathbb D}} |\psi'_{\alpha}|^2 dx dy =1}$.

-   $\displaystyle{\frac{1}{\pi}\iint_{{\mathbb D}} |\psi'_{\alpha}| dx dy =\frac{1-|\alpha|^2}{|\alpha|^2} \log \frac{1}{1-|\alpha|^2}}$.


## Tie's Extra Questions: Spring 2015 #complex/exercise/work

Let $\Omega$ be a simply connected open set and let $\gamma$ be a simple closed contour in $\Omega$ and enclosing a bounded region $U$ anticlockwise. Let $f: \ \Omega \to {\mathbb C}$ be a holomorphic function and $|f(z)|\leq M$ for all $z\in \gamma$. Prove that
$|f(z)|\leq M$ for all $z\in U$.

## Tie's Extra Questions: Fall 2015 #complex/exercise/work

Assume $f(z)$ is analytic in region $D$ and $\Gamma$ is a rectifiable curve in $D$ with interior in $D$. Prove that if $f(z)$ is real for all $z \in \Gamma$, then $f(z)$ is a constant.

