# Unsorted

## Spring 2021 # 3 #completed

:::{.problem title="?"}
Suppose $f$ is entire, let $A, R> 0$ and $N \in \NN$, and suppose
\[
\abs{f(z)} \geq A\abs{z}^N && \text{for } \abs{z} \geq R
.\]

- Show that $f$ is polynomial.
- Show that $f$ has degree at least $N$.

:::

:::{.solution}
Note that the analogue of this problem where $\abs{f(z)} \leq A \abs{z}^N$ implies $f$ is a polynomial of degree at *most* $N$ is easy by the Cauchy estimate:
\[
\abs{f(z)} =\abs{\sum_{k\geq 0} c_k z^k } \implies 
\abs{c_n} = \abs{f^{(n)}(0)} 
&= \abs{{n!\over 2\pi i }\int_\gamma {f(\xi) \over (\xi-a)^{n+1} } \dxi } \quad \text{ at } a=0\\
&\leq {n!\over 2\pi }\int_\gamma {\abs{f(\xi)} \over \abs{\xi}^{n+1} } \dxi \\
&\leq {n!\over 2\pi }\int_\gamma {A {\abs{\xi}^N } \over \abs{\xi}^{n+1} } \dxi \\
&= {A n!\over 2\pi }\int_\gamma {{R ^N } \over R^{n+1} } \dxi \\
&= {An!\over 2\pi} \cdot {2\pi R \over R^{n+1-N}} \\
&= {An! \over R^{n-N}} \\
&\convergesto{R\to\infty} 0 \quad \iff n-N>0 \quad\iff n>N
,\]
so $f(z) = \sum_{0\leq k\leq N} c_k z^k$.

For the case at hand, a solution I liked from MSE:

- Write $g(z) \da f(1/z)$, so $g$ has a singularity at $z=0$.
  The claim is that this is a pole.

- It can't be removable: 
\[
\abs{g(z)} \geq A \abs{1\over z}^n \to\infty
\quad \text{ for }
\abs{1/z} \geq R \,\, (\iff \abs{z} < 1/R)
,\]
so $g$ is unbounded near $z=0$.
- It can't be essential: if so, take the neighborhood of $z=0$ given by $U\da D_{1\over R}(0)\smz = \ts{z\st 0< \abs{z} < {1\over R} }$.
Then $g(U) \subseteq \CC$ would be dense by Casorati-Weierstrass, but note that $g(z) = w\in g(U) \implies \abs{w} \da \abs{g(z)} \geq A\abs{1/z}^n$ since $\abs{z}<1/R$, so $g(U) \subseteq (\CC\sm D_{A\over R^n}(0))$ and in particular does not intersect the interior of $D_{A\over R^n}(0)$.

- Since $z=0$ is a pole, it has some finite order $m$, so write
\[
g(z) = \qty{c_{-m}z^{-m} + \cdots + c_{-1}z\inv} + \qty{c_0 + c_1 z + \cdots} \da p(1/z) + h(z)
,\]
where $p$ is polynomial of degree exactly $m$ (since $c_{-m} \neq 0$) and $h$ is entire.
In particular, $z=0$ is not a singularity of $h$.

- Now
\[
g(z) = p(1/z) + h(z) \implies f(z) = p(z) + h(1/z)
.\]

- Then
\[
f(z) - p(z) = h(1/z) \convergesto{\abs z\to \infty} c_0 \da h(0)
,\]
since holomorphic functions are continuous.

- Then $h$ is an entire function with a finite limit $L$ at $\infty$.
$h$ is bounded by $c_0$ in a neighborhood $U_\infty$ of $\infty$ and takes on a maximum on $U_\infty^c$ by compactness and the maximum modulus principle.
So $h$ is bounded on all of $\CC$, and thus constant by Liouville, and thus $h(1/z) = L$ for all $z$.

- So 
\[
f(z) &= p(z) + h(1/z) = p(z) + c_0 \\
\implies f(z) &= (c_{-1}z + \cdots + c_{-m}z^m) + c_0
,\]
which is a polynomial of degree exactly $m\da \deg p$.
- Why $m \geq N$: if not, $m<N$ so $N-m > 0$.
Then for large $z$,
\[
A \leq \abs{f(z) \over z^N} 
&= \abs{c_0 + c_{-1}z + \cdots + c_{-m}z^m \over z^N}\\
&= \abs{ {c_0 \over z^N} + {c_{-1} \over z^{N-1}} + \cdots + {c_{-m} \over z^{N-m}} } \\
&\convergesto{\abs{z}\to\infty} 0
,\]
since every term has a factor of $z$ in the denominator.
This contradicts $A>0$. $\contradiction$
:::



## Spring 2021 # 4 #completed

:::{.problem title="?"}
Let $f = u + iv$ be an entire function such that $\Re(f(x+iy))$ is polynomial in $x$ and $y$.
Show that $f(z)$ is polynomial in $z$.
:::

:::{.solution}
To clear up notation: write $f(z) = u(x, y) + iv(x, y)$, here we're assuming that $u$ is polynomial in $x$ and $y$.

:::{.claim}
If $u$ is polynomial in $x,y$, then so is $v$.
:::

:::{.proof title="?"}
This follows from the fact that $u$ is a harmonic conjugate of $v$, and the explicit process computing the conjugate will result in a polynomial.
Gamelin describes this process in detail, see Ch.2 Section 5 on Harmonic functions where he proves the formula
\[
v(x, y)
= \int_{y_{0}}^{y} \frac{\partial u}{\partial x}(x, t) \dt 
-\int_{x_{0}}^{x} \frac{\partial u}{\partial y}\left(s, y_{0}\right) \ds + C 
.\]

:::

:::{.claim}
Since $f(x, y)$ is a polynomial in $x, y$, $f(z)$ must be a polynomial in $z$.
:::

:::{.proof title="?"}
Since $f$ is entire, it's equal to its Laurent series everywhere, so
\[
f(z) = \sum_{k\geq 0} c_k z^k, \qquad c_k = {f^{(k) }(0) \over k!} = {1\over 2\pi i} \int_{S^1} {f(\xi) \over \xi^{k+1} } \dxi
.\]
Thus $f$ will be a polynomial if $c_{N} = 0$ for all $N$ large enough, which will be true if $f^{(N)}(z) = 0$ for large enough $N$.
But we can write
\[
\dd{}{z} f(z) = \dd{}{x} f(x, y)
\implies
0 = \qty{\dd{^N}{x^N}} f(x, y) = \qty{\dd{^N}{z^N}} f(z) \da f^{(N)}(z)
,\]
:::

:::


## Spring 2021 # 6 #work

:::{.problem title="?"}
Let $\ts{f_n}_{n=1}^\infty$ is a sequence of holomorphic functions on $\DD$ and $f$ is also holomorphic on $\DD$. 
Show that the following are equivalent:

- $f_n\to f$ uniformly on compact subsets of $\DD$.
- For $0 < r < 1$,
\[
\int_{\abs z = r} \abs{f_n(z) - f(z)} \abs{dz} \convergesto{n\to\infty}0
.\]

:::

## Spring 2021 # 7 #work

:::{.problem title="?"}
Let $R$ be the intersection of the right half-plane and the outside of the circle $\abs{z - {1\over 2}} = {1\over 2}$ with the line segment $[1, 2]$ removed, i.e. 
\[
R = \ts{z\in \CC\st \Re(z) > 0,\,\, \abs{z-{1\over 2} > {1\over 2} }} \sm \ts{z \da x+iy \st 1\leq x\leq 2,\,\, y=0}
.\]
Find a conformal map from $R$ to $\HH$ the upper half-plane.
:::

## Fall 2021 # 1 #complete

:::{.problem title="?"}
Let $f(z)$ be an analytic function on $|z|<1$.
Prove that $f(z)$ is necessarily a constant if $f(\bar{z})$ is also analytic.
:::

:::{.solution}
Let $\tilde f(z) \da f(\bar z)$.
Using that $f$ is analytic iff its components solve Cauchy-Riemann, using that $f, \tilde f$ are analytic,
\[
u_x = v_y && u_y = -v_x \\
u_x = -v_y && u_y = v_x \\ \\
\implies 2u_x = v_y - v_y = 0 \implies u_x = 0 \\
\implies 2u_y = v_x - v_x = 0 \implies u_y = 0 \\
\implies 0 = u_y - u_y = v_x - (-v_x) = 2v_x  \implies v_x = 0 \\
\implies 0 = u_x - u_x = v_y - (-v_y) = 2v_y  \implies v_y = 0
,\]
so $\grad u = [u_x, u_y] \equiv \vector 0$ making $u$ constant.
Similarly $\grad v = [v_x, v_y] = \vector 0$, so $f: \RR^2\to \RR$ is constant.
:::


## Fall 2021 # 2  #work

Let $\gamma(t)$ be a piecewise smooth curve in $\mathbb{C}, t \in[0,1]$. Let $F(w)$ be a continuous function on $\gamma$. Show that $f(z)$ defined by
\[
f(z):=\int_{\gamma} \frac{F(w)}{w-z} d w
\]
is analytic on the complement of the curve $\gamma$.

## Fall 2021 # 5  #work

Assume $f$ is an entire function such that $|f(z)|=1$ on $|z|=1$. Prove that $f(z)=e^{i \theta} z^{n}$, where $\theta$ is a real number and $n$ a non-negative integer. 

> Suggestion: First use the maximum and minimum modulus theorem to show 
$$
f(z)=e^{i \theta} \prod_{k=1}^{n} \frac{z-z_{k}}{1-\bar{z_{k}} z}
$$ 
if $f$ has zeros.

## Fall 2021 # 6 #work

Show that if $f: D(0, R) \rightarrow \mathbb{C}$ is holomorphic, with $|f(z)| \leq M$ for some $M>0$, then
\[
\left|\frac{f(z)-f(0)}{M^{2}-\overline{f(0)} f(z)}\right| \leq \frac{|z|}{M R} .
\]


## Tie's Extra Questions: Fall 2015 #work



(1) 
Let $f(z) \in H({\mathbb D})$, $\text{Re}(f(z)) >0$ and $f(0)= a>0$. 
Show that 
$$
|\frac{f(z)-a}{f(z)+a}| \leq |z|, \; \; \; |f'(0)| \leq 2a
.$$

(2) 
Show that the above is still true if $\text{Re}(f(z)) >0$ is replaced with $\text{Re}(f(z)) \geq 0$.



## Tie's Extra Questions: Spring 2015 #work


(1) Let $p(z)$ be a polynomial, $R>0$ any positive number, and
$m \geq 1$ an integer. Let
$M_R = \sup \{ |z^{m} p(z) - 1|: |z| = R  \}$. Show that $M_R>1$.

(2) Let $m \geq 1$ be an integer and
$K = \{z \in {\mathbb C}: r \leq |z| \leq R \}$ where $r<R$.
Show (i) using (1) as well as, (ii) without using (1) that there exists a positive number $\varepsilon_0>0$ such that for each polynomial $p(z)$,
$$\sup \{|p(z) - z^{-m}|: z \in K  \} \geq \varepsilon_0 \, .$$



## Tie's Extra Questions: Spring 2015 #work



(1) Explicitly write down an example of a non-zero analytic function in $|z|<1$ which has infinitely zeros in $|z|<1$.

(2) Why does not the phenomenon in (1) contradict the uniqueness theorem?



## Tie's Extra Questions: Spring 2015 #work



Let $f$ be holomorphic in a neighborhood of $D_r(z_0)$. Show that
for any $s<r$, there exists a constant $c>0$ such that
$$||f||_{(\infty, s)} \leq c ||f||_{(1, r)},$$ where
$\displaystyle |f||_{(\infty, s)} = \text{sup}_{z \in D_s(z_0)}|f(z)|$
and $\displaystyle ||f||_{(1, r)} = \int_{D_r(z_0)} |f(z)|dx dy$.

> Note: Exercise 3.8.20 on p.107 in Stein et al is a
straightforward consequence of this stronger result using the integral form of the Cauchy-Schwarz inequality in real analysis.





## Tie's Extra Questions: Spring 2015 #work



Let $f$ be an analytic function on a region $\Omega$. Show that $f$
is a constant if there is a simple closed curve $\gamma$ in $\Omega$ such that its image $f(\gamma)$ is contained in the real axis.

## Tie's Extra Questions: Spring 2015 #work


(1) Show that $\displaystyle \frac{\pi^2}{\sin^2 \pi z}$ and
$\displaystyle g(z) = \sum_{n = - \infty}^{ \infty} \frac{1}{(z-n)^2}$
have the same principal part at each integer point.

(2) Show that
$\displaystyle h(z) = \frac{\pi^2}{\sin^2 \pi z} - g(z)$ is bounded
on $\mathbb C$ and conclude that
$\displaystyle \frac{\pi^2}{\sin^2 \pi z} = \sum_{n = - \infty}^{ \infty} \frac{1}{(z-n)^2} \, .$



## Tie's Extra Questions: Spring 2015 #work



Assume $f(z)$ is analytic in ${\mathbb D}: |z|<1$ and $f(0)=0$ and
is not a rotation (i.e. $f(z) \neq e^{i \theta} z$). Show that
$\displaystyle \sum_{n=1}^\infty f^{n}(z)$ converges uniformly to an
analytic function on compact subsets of ${\mathbb D}$, where
$f^{n+1}(z) = f(f^{n}(z))$.

## Tie's Extra Questions: Spring 2015 #work


Let $f$ be a non-constant analytic function on $\mathbb D$ with $f(\mathbb D) \subseteq \mathbb D$. Use $\psi_{a} (f(z))$ (where $a=f(0)$, $\displaystyle \psi_a(z) = \frac{a - z}{1 - \bar{a}z}$) to
prove that 
$\displaystyle \frac{|f(0)| - |z|}{1 + |f(0)||z|} \leq |f(z)| \leq \frac{|f(0)| + |z|}{1 - |f(0)||z|}$.



## Tie's Extra Questions: Spring 2015 #work



Let $f$ be holomorphic in a neighborhood of $D_r(z_0)$. Show that for any $s<r$, there exists a constant $c>0$ such that
$$
\|f\|_{(\infty, s)} \leq c \|f\|_{(1, r)}
,$$ 
where
$\displaystyle \|f\|_{(\infty, s)} = \text{sup}_{z \in D_s(z_0)}|f(z)|$
and $\displaystyle \|f\|_{(1, r)} = \int_{D_r(z_0)} |f(z)|dx dy$.


## Tie's Extra Questions: Spring 2015 #work


Let $\Omega$ be a simply connected open set and let $\gamma$ be a simple closed contour in $\Omega$ and enclosing a bounded region $U$ anticlockwise. Let $f: \ \Omega \to {\mathbb C}$ be a holomorphic function and $|f(z)|\leq M$ for all $z\in \gamma$. Prove that
$|f(z)|\leq M$ for all $z\in U$.



## Tie's Extra Questions: Spring 2015 #work


Let $f$ be holomorphic in a neighborhood of $D_r(z_0)$. Show that for any $s<r$, there exists a constant $c>0$ such that
$$\|f\|_{(\infty, s)} \leq c \|f\|_{(1, r)},$$ where
$\displaystyle \|f\|_{(\infty, s)} = \text{sup}_{z \in D_s(z_0)}|f(z)|$
and $\displaystyle \|f\|_{(1, r)} = \int_{D_r(z_0)} |f(z)|dx dy$.



## Tie's Extra Questions: Fall 2016 #work


a.
$f(z)= u(x,y) +i v(x,y)$ be analytic in a domain
$D\subset {\mathbb C}$. Let $z_0=(x_0,y_0)$ be a point in $D$ which
is in the intersection of the curves $u(x,y)= c_1$ and $v(x,y)=c_2$,
where $c_1$ and $c_2$ are constants. Suppose that $f'(z_0)\neq 0$.
Prove that the lines tangent to these curves at $z_0$ are
perpendicular.

b.
Let $f(z)=z^2$ be defined in $\CC$.

- Describe the level curves of $\mbox{\textrm Re}{(f)}$ and of $\mbox{Im}{(f)}$.

- What are the angles of intersections between the level curves $\mbox{\textrm Re}{(f)}=0$ and $\mbox{\textrm Im}{(f)}$? 
Is your answer in agreement with part a) of this question?

## Tie's Extra Questions: Fall 2016 #work



a.
$f: D\rightarrow {\mathbb C}$ be a continuous function, where
$D\subset {\mathbb C}$ is a domain.Let $\alpha:[a,b]\rightarrow D$
be a smooth curve. Give a precise definition of the *complex line integral* $$\int_{\alpha} f.$$

b.
Assume that there exists a constant $M$ such that
$|f(\tau)|\leq M$ for all $\tau\in \mbox{\textrm Image}(\alpha$). Prove that
$$\big | \int_{\alpha} f \big |\leq M \times \mbox{\textrm length}(\alpha).$$

c.
Let $C_R$ be the circle $|z|=R$, described in the counterclockwise direction, where $R>1$. Provide an upper bound for $\big | \int_{C_R} \dfrac{\log{(z)} }{z^2} \big |,$ which depends *only* on $R$ and other constants.




## Tie's Extra Questions: Fall 2016 #work


a.
Let $F$ be an analytic function inside and on a simple closed curve $C$, except for a pole of order $m\geq 1$ at $z=a$ inside $C$.
Prove that

$$\frac{1}{2 \pi i}\oint_{C} F(\tau) d\tau =
\lim_{\tau\rightarrow a} \frac{d^{m-1}}{d\tau^{m-1}}\big((\tau-a)^m F(\tau))\big).$$

b.
Evaluate $$\oint_{C}\frac{e^{\tau}}{(\tau^2+\pi^2)^2}d\tau$$
where $C$ is the circle $|z|=4$.



## Tie's Extra Questions: Spring 2014, Fall 2009, Fall 2011  #work

For $s>0$, the **gamma function** is defined by $\displaystyle{\Gamma(s)=\int_0^{\infty} e^{-t}t^{s-1} dt}$.

-   Show that the gamma function is analytic in the half-plane $\Re (s)>0$, and is still given there by the integral formula above.

-   Apply the formula in the previous question to show that
  $$
\Gamma(s)\Gamma(1-s)=\frac{\pi}{\sin \pi s}
.$$

> Hint: You may need $\displaystyle{\Gamma(1-s)=t \int_0^{\infty}e^{-vt}(vt)^{-s} dv}$ for $t>0$.


:::{.exercise title="?"}
Show that if $f$ is entire and $f(z) \convergesto{z\to\infty} \infty$ then $f$ is a polynomial.
:::

:::{.solution}

- Set $g(z) \da f(1/z)$, so $g(z) \convergesto{z\to 0} \infty$ making $z=0$ a singularity.
- This is not an essential singularity by Casorati-Weierstrass.
- So this is a pole and $g(z) = \sum_{-N\leq k \leq 0} c_k z^k$ for $N$ the order of the pole
- Thus $f(z) = \sum_{0<k<N}c_k z^k$ is a polynomial.
:::


