---
order: 40
---

# Maximum Modulus

## Fall 2020.6 #complex/qual/work

^189826

Suppose that $U$ is a bounded, open and simply connected domain in $\mathbb{C}$ and that $f(z)$ is a complex-valued non-constant continuous function on $\bar{U}$ whose restriction to $U$ is holomorphic.

- Prove the maximum modulus principle by showing that if $z_{0} \in U$, then

$$
\left|f\left(z_{0}\right)\right|<\sup \{|f(z)|: z \in \partial U\} .
$$

- Show furthermore that if $|f(z)|$ is constant on $\partial U$, then $f(z)$ has a zero in $U$ (i.e., there exists $z_{0} \in U$ for which $f\left(z_{0}\right)=0$ ).

## Spring 2020 HW 3, SS 3.8.15 #complex/exercise/work
Use the Cauchy inequalities or the maximum modulus principle to solve the following problems:

a. 
Prove that if $f$ is an entire function that satisfies
\[
\sup _{|z|=R}|f(z)| \leq A R^{k}+B
\]
for all $R>0$, some integer $k\geq 0$, and some constants $A, B > 0$, then $f$ is a polynomial of degree $\leq k$.

b. 
Show that if $f$ is holomorphic in the unit disc, is bounded, and converges uniformly to zero in the sector $\theta < \arg(z) < \phi$ as $\abs{z} \to 0$, then $f \equiv 0$.

c. 
Let $w_1, \cdots w_n$ be points on $S^1 \subset \CC$.
Prove that there exists a point $z\in S^1$ such that the product of the distances from $z$ to the points $w_j$ is at least 1.

Conclude that there exists a point $w\in S^1$ such that the product of the above distances is *exactly* 1.

d. 
Show that if the real part of an entire function is bounded, then $f$ is constant.

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

