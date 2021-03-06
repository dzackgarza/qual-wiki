---
order: 35
---

# Cauchy's Theorem

## Entire and $O$ of polynomial implies polynomial #complex/exercise/completed

:::{.problem title="?"}
Let $f(z)$ be entire and assume that $\abs{f(z)} \leq M |z|^2$ outside of some disk for some constant $M$. 
Show that $f(z)$ is a polynomial in $z$ of degree $\leq 2$.
:::

:::{.solution}
\envlist

- Prove a more general statement: if $\abs{f(z)} \leq M\abs{z}^n$, then $f$ is a polynomial of degree at most $n$.
- Since $f$ is entire, it is analytic everywhere, so $f(z) = \sum_{k\geq 0}c_k z^k$ where $c_k = f^{(k)}(0)/n!$ is given by the coefficient of its Taylor expansion about $z=0$.
- Applying Cauchy's estimate, on a circle of radius $R$, 
\[
\abs{f^{(k)}(0)} \leq { \sup_{\gamma}\abs{f(z)} n! \over R^k} \leq {M\abs{z}^n n! \over R^k} = {M R^n n! \over R^k} 
.\]

- So for $k \geq n+1$, this goes to zero as $R\to \infty$, so $\abs{f^{k}(0)} = 0$ for all such $k$.
- But then $f$ is a power series annihilated by taking $n+1$ derivatives, so it is a polynomial of degree at most $n$.
:::

## Uniform sequence implies uniform derivatives #complex/exercise/work

:::{.problem title="?"}
Let $a_n(z)$ be an analytic sequence in a domain $D$ such that
$\displaystyle \sum_{n=0}^\infty |a_n(z)|$ converges uniformly on
bounded and closed sub-regions of $D$. 
Show that $\displaystyle \sum_{n=0}^\infty |a'_n(z)|$ converges uniformly on bounded and closed sub-regions of $D$.
:::

## Tie's Extra Questions: Spring 2014 #complex/exercise/completed

:::{.problem title="?"}
The question provides some insight into Cauchy's theorem. Solve the
problem without using the Cauchy theorem.

1.  Evaluate the integral $\displaystyle{\int_{\gamma} z^n dz}$ for
    all integers $n$. Here $\gamma$ is any circle centered at the
    origin with the positive (counterclockwise) orientation.

2.  Same question as (a), but with $\gamma$ any circle not
    containing the origin.

3.  Show that if $|a|<r<|b|$, then
    $\displaystyle{\int_{\gamma}\frac{dz}{(z-a)(z-b)} dz=\frac{2\pi i}{a-b}}$.
    Here $\gamma$ denotes the circle centered at the origin, of
    radius $r$, with the positive orientation.
:::

:::{.solution}
\[
\int_\gamma z^n\dz = \int_0^{2\pi} R^n e^{itn} \cdot iRe^{it} \dt
= R^{n+1} \int_0^{2\pi} e^{i(t+1)n}\dt 
= { i R^{n+1} \over i(n+1) } \delta_{n+1 = 0}
.\]

About a point $a$ and $R<\abs{a}$,
\[
\int_{\abs{z-a} = R} z^n\dz 
&= \int_0^{2\pi} (a + re^{it})^n \cdot ire^{it}\dt \\
&= \int_0^{2\pi} \sum_{1\leq k\leq n} {n \choose k} a_k R^{n-k+1} e^{it(n-k)} \cdot ire^{it}\dt \\
&= i \int_0^{2\pi} \sum_{1\leq k\leq n} {n \choose k} a_k R^{n-k+1} e^{it(n-k+1)} \dt \\
&= i \sum_{1\leq k\leq n} {n \choose k} a_k R^{n-k+1} \int_0^{2\pi} e^{it(n-k+1)} \dt \\
&= i \sum_{1\leq k\leq n} {n \choose k} a_k R^{n-k+1} \cdot 0 \\
&= 0
,\]
provided $n\neq 0$, in which case $\int_\gamma \dz = 2\pi$.

For the third computation, this follows from partial fraction decomposition.
:::

## Fall 2019.3, Spring 2020 HW 2.9 (Cauchy's Formula for Exterior Regions) #complex/qual/completed

^f2a684

:::{.problem title="?"}
Let $\gamma$ be a piecewise smooth simple closed curve with interior $\Omega_1$ and exterior $\Omega_2$.
Assume $f'$ exists in an open set containing $\gamma$ and $\Omega_2$ with $\lim_{z\to \infty} f(z) = A$.
Show that
$$
F(z) \da \frac{1}{2 \pi i} \int_{\gamma} \frac{f(\xi)}{\xi-z} d \xi=\left\{\begin{array}{ll}
A, & \text { if } z \in \Omega_{1} \\
-f(z)+A, & \text { if } z \in \Omega_{2}
\end{array}\right.
.$$

> NOTE (DZG): I think there is a typo in this question....probably this should equal $f(z)$ for $z\in \Omega_1$, which is Cauchy's formula...

:::

:::{.solution}
Note that $G_z(\xi) \da {f(\xi) \over \xi - z}$ has a pole of order one at $\xi = z$ and also a pole at $\xi = \infty$.
If $z\in \Omega_1$, then $\gamma$ encloses just the pole $\xi = z$, so apply the residue theorem:
\[
F(z) 
&\da {1\over 2\pi i}\oint_\gamma {f(\xi) \over \xi - z}\dxi \\
&= {1\over 2\pi i}\oint_\gamma G_z(\xi) \dxi \\
&= \Res_{\xi = z} G_z(\xi) \\
&= \lim_{\xi\to z} (\xi - z) G_z(\xi) \\ 
&= \lim_{\xi\to z} (\xi - z) {f(\xi) \over \xi-z} \\ 
&= \lim_{\xi\to z} f(\xi) \\
&= f(z)
.\]

Now if $z\in \Omega_2$, then $\gamma$ encloses both $\xi=z, \infty$, and is oriented negatively,so
\[
F(z) 
&= {1\over 2\pi i} \oint_\gamma G_z(\xi) \dxi \\
&= -\qty{\Res_{\xi = z} G_z(\xi) + \Res_{\xi = \infty} G_z(\xi)}\\
&= -\qty{f(z) + \Res_{\xi = \infty} G_z(\xi)}\\
,\]
where the last line proceeds by the same calculation as above.
It remains to compute the unknown residue.
Residues at $\xi = \infty$ are computed as residues at $\xi =0$, and the change of variables $G_z(\xi)\dxi \mapsto G_z(w) \dw$ for $w\da 1/\xi$ yields $G_z(\xi)\dxi \to G_z\qty{1\over \xi}(-1/\xi^2)\dxi$.
Thus
\[
\Res_{\xi=\infty} G_z(\xi) 
&= -\Rez_{\xi=0} G_z\qty{\xi\inv}\xi^{-2} \\
&= - \Rez_{\xi=0} {f(\xi\inv) \over \xi^2(\xi\inv - z) } \\
&= - \Rez_{\xi=0} {f(\xi\inv) \over \xi(1 - z\xi) } \\
&= -\lim_{\xi \to 0} {f(\xi\inv) \over 1-z\xi} \\
&= -\lim_{\xi \to 0}f(\xi \inv) \\
&= -\lim_{\xi\to\infty} f(\xi) \\
&= -A
.\]
So combining this yields
\[
F(z) = -\qty{f(z) - A} = -f(z) + A
.\]
:::

## Tie's Extra Questions: Fall 2009 (Proving Cauchy using Green's) #complex/exercise/completed

:::{.problem title="?"}
State and prove Green's Theorem for rectangles.
Use this to prove Cauchy's Theorem for functions that are analytic in a rectangle.
:::

:::{.problem title="Variant"}
Suppose $f\in C_\CC^1(\Omega)$ and $T\subset \Omega$ is a triangle with $T^\circ \subset \Omega$.

- Apply Green's theorem to show that $\int_T f(z) ~dz = 0$.
- Assume that $f'$ is continuous and prove Goursat's theorem.

> Hint: Green's theorem states
\[
\int_{T} F d x+G d y=\int_{T^\circ}\left(\frac{\partial G}{\partial x}-\frac{\partial F}{\partial y}\right) d x d y
.\]

:::

:::{.solution}
Green's theorem:
if $\Omega$ is a domain with positively oriented boundary with $u, v$ continuously differentiable in $\bar\Omega$, then
\[
\int_{\bd \Omega} u\dx + v\dy = \iint_{\Omega}\qty{v_x - u_y}\dx\dy
.\]
Now use that if $f = u+iv$ is analytic in a region, it satisfies Cauchy-Riemann:
\[
u_x = v_y \qquad u_y = -v_x
.\]

Now integrating $f$:
\[
\oint_{\bd\Omega} f(z) \dz 
&= \oint_{\bd\Omega} (u+iv)(\dx + i\dy )\\
&= \oint_{\bd\Omega} \qty{u\dx - v\dy} + i\oint_{\bd\Omega} \qty{v\dx + u\dy} \\
&= \iint_\Omega\qty{v_x + u_y}\dx\dy + \iint_\Omega\qty{u_x - v_y}\dx\dy \\
&= \iint_\Omega\qty{v_x -v_x }\dx\dy + \iint_\Omega\qty{u_x - u_x}\dx\dy \\
&= 0
.\]
:::

## No polynomials converging uniformly to $1/z$ #complex/exercise/completed

:::{.problem title="?"}
Prove that there is no sequence of polynomials that uniformly converge to $f(z) = {1\over z}$ on $S^1$.

:::

:::{.solution}

- By Cauchy's integral formula, $\int_{S^1} f = 2\pi i$
- If $p_j$ is any polynomial, then $p_j$ is holomorphic in $\DD$, so $\int_{S^1} p_j = 0$.
- Contradiction: compact sets in $\CC$ are bounded, so 
  \[
  \abs{\int f - \int p_j} 
  &\leq \int \abs{p_j - f} \\
  &\leq \int \norm{p_j - f}_\infty  \\
  &= \norm{p_j - f}_\infty \int_{S^1} 1 \,dz \\
  &= \norm{p_j-f}_\infty \cdot 2\pi \\
  &\to 0
  \]
  which forces $\int f = \int p_j = 0$.
:::

## Eventually sublinear implies constant #complex/exercise/completed

:::{.problem title="?"}
Suppose $f: \CC\to \CC$ is entire and
\[
\abs{f(z)} \leq \abs{z}^{1\over 2} \quad\text{ when } \abs{z} > 10
.\]

Prove that $f$ is constant.
:::

:::{.solution}
Let $R> 10$, then by Cauchy:
\[
2\pi \abs{f'(z)} 
&\leq \oint_{\abs{\xi} = R} { \abs{ f(\xi)} \over \abs{\xi}^2 } \dxi \\
&\leq \oint_{\abs{\xi} = R} R^{-2} \abs{\xi}^{1\over 2} \dxi \\
&= R^{-{3\over 2}} \cdot 2\pi R \\
&\sim R^{-{1\over 2}} \\
&\convergesto{R\to\infty} 0
.\]
:::

## The Cauchy pole function is holomorphic #complex/exercise/completed

:::{.problem title="?"}
Let $\gamma$ be a smooth curve joining two distinct points $a, b\in \CC$.

Prove that the function
\[
f(z) \definedas \int_\gamma {g(w) \over w-z} \,dw
\]
is analytic in $\CC\setminus\gamma$.
:::

:::{.solution}
Toward applying Morera, let $T \subseteq \CC\sm \gamma$ be a triangle, so that $z\in T$ and $w\in \gamma$ implies $z-w\neq 0$.
Then
\[
\oint_T f(z) \dz 
&= \oint_T \int_\gamma {g(w)\over w-z}\dw\dz \\
&= \int_\gamma \oint_T {g(w)\over w-z}\dz\dw \\
&= \int_\gamma g(w) \qty{ \oint_T {1 \over w-z}\dz} \dw \\
&= \int_\gamma g(w) \cdot 0 \dw \\
&= 0
,\]
where the exchange of integrals is justified by compactness of $\gamma, T$, and the inner integral vanishes because for a fixed $w\in \gamma$, the function $z\mapsto {1\over w-z}$ has a simple pole at $w$, and so is holomorphic in $\gamma^c$ and vanishes by Goursat.
:::

## Schwarz reflection proof #complex/exercise/completed

:::{.problem title="?"}
Suppose that $f: \CC\to\CC$ is continuous everywhere and analytic on $\CC\setminus \RR$ and prove that $f$ is entire.
:::

:::{.solution}
Just reproducing the proof of holomorphicity in the Schwarz reflection theorem.

- Note $f$ is continuous on $\CC$ since analytic implies continuous ($f$ equals its power series, where the partials sums uniformly converge to it, and uniform limit of continuous is continuous).
- Strategy: take $D$ a disc centered at a point $x\in \RR$, show $f$ is holomorphic in $D$ by Morera's theorem.
- Let $\Delta \subset D$ be a triangle in $D$.
- Case 1: If $\Delta \intersect \RR = 0$, then $f$ is holomorphic on $\Delta$ and $\int_\Delta f = 0$.
- Case 2: one side or vertex of $\Delta$ intersects $\RR$, and wlog the rest of $\Delta$ is in $\HH^+$.
  - Then let $\Delta_\eps$ be the perturbation $\Delta + i\eps = \theset{z+ i\eps \suchthat z\in \Delta}$; then $\Delta_\eps \intersect \RR = 0$ and $\int_{\Delta_\eps} f = 0$.
  - Now let $\eps\to 0$ and conclude by continuity of $f$ (???)
    - We want
    \begin{align*}
    \int_{\Delta_\eps} f = \int_a^b f(\gamma_\eps(t)) \gamma_\eps'(t)\,dt \converges{\eps\to 0}\to \int_a^b f(\gamma(t)) \gamma_\eps'(t)\,dt =\int_{\Delta}  f
    \end{align*}
    where $\gamma_\eps, \gamma$ are curves parametrizing $\Delta_\eps, \Delta$ respectively.
    - Since $\gamma, \gamma_\eps$ are closed and bounded in $\CC$, they are compact subsets. Thus it suffices to show that $f(\gamma_\eps(t)) \gamma_\eps'(t)$ converges uniformly to $f(\gamma(t))\gamma'(t)$.
    -  ??
- Case 3: $\Delta$ intersects both $\HH^+$ and $\HH^-$.
  - Break into smaller triangles, each of which falls into one of the previous two cases.

:::

## Prove Liouville #complex/exercise/completed

:::{.problem title="?"}
Prove Liouville's theorem: suppose $f:\CC\to\CC$ is entire and bounded. 
Use Cauchy's formula to prove that $f'\equiv 0$ and hence $f$ is constant.
:::

:::{.solution}
The main idea:
\[
\abs{f'(z)} 
&\leq {1\over 2\pi }\oint_R {\abs{f(\xi)} \over \abs{\xi}^2 } \dxi\\
&= {1\over 2\pi }\oint_R {\abs{f(\xi)}  } R^{-2} \dxi\\
&\leq {1\over 2\pi }\oint_R M R^{-2} \dxi\\
&= {1\over 2\pi} MR^{-2}\cdot 2\pi R \\
&= MR^{-1} \\
&\convergesto{R\to\infty}0
.\]
So $f'\equiv 0$.
:::

## Tie's Extra Questions Fall 2009 (Fractional residue formula) #complex/exercise/completed

:::{.problem title="?"}
Assume $f$ is continuous in the region:
\[
0 < \abs{z-a} \leq R,\quad 0 \leq \Arg(z-a) \leq \beta_0 \qquad \beta_0\in (0, 2\pi]
.\]

and the following limit exists:
\[
\lim_{z\to a}(z-a)f(z) = A
.\]
Show that
$$\lim_{r \rightarrow 0} \int_{\gamma_r} f(z) dz  = i A \beta_0 \; , \; \;$$
where
\[
\gamma_r : = \{ z \; | \; z = a + r e^{it}, \; 0 \leq  t \leq \beta_0 \}.
.\]
:::

:::{.problem title="Alternative version"}
Let $f$ be a continuous function in the region
$$
D=\{z \suchthat  \abs{z}>R, 0\leq \arg z\leq \theta\}\quad\text{where}\quad 1\leq \theta \leq 2\pi
.$$ 
If there exists $k$ such that
$\displaystyle{\lim_{z\to\infty} zf(z)=k}$ for $z$ in the region $D$.
Show that 
$$
\lim_{R'\to\infty} \int_{L} f(z) dz=i\theta k
,$$ 
where $L$ is the part of the circle $|z|=R'$ which lies in the region $D$.

:::

:::{.solution}
Without loss of generality take $a=0$.
Since $zf(z) \to A$ as $z\to 0$, $z=0$ is a simple pole of $f$ and we can write $f(z) = c_{-1}z\inv + c_0 + c_1z + \cdots$.
Then
\[
\int_{\gamma_r} f(z)\dz 
&= \int_{\gamma_r} \sum_{k\geq -1} c_k z^k \dz \\
&= \sum_{k\geq -1} c_k \int_{\gamma_r} z^k \dz \\
&= c_{-1}\int_{\gamma_r}{1\over z}\dz \\
&= c_{-1}\int_{0}^{\beta_0} {1\over re^{i t}} ire^{it} \dt \qquad z= re^{it}, \dz = ire^{it} \dt \\
&= i c_{-1}\int_{0}^{\beta_0} \dt \\
&= i c_{-1}\beta_0
.\]
Now use that
\[
zf(z) = c_{-1} + c_0z + \cdots \convergesto{z\to 0} c_{-1} = A
,\]
so the integral is $iA\beta_0$.
:::

## Spring 2020 HW 2, 2.6.7 #complex/exercise/work

Suppose $f: \DD \to \CC$ is holomorphic and let $d \definedas \sup_{z, w\in \DD}\abs{f(z) - f(w)}$ be the diameter of the image of $f$.
Show that $2 \abs{f'(0)} \leq d$, and that equality holds iff $f$ is linear, so $f(z) = a_1 z + a_2$.

> Hint: 
\[
2f'(0) = \frac{1}{2\pi i} \int_{\abs \xi = r} \frac{ f(\xi) - f(-\xi)  }{\xi^2} ~d\xi
\]
whenever $0<r<1$.


## Spring 2020 HW 2, 2.6.8 #complex/exercise/work

Suppose that $f$ is holomorphic on the strip $S = \theset{x+iy \suchthat x\in \RR,~ -1<y<1}$ with $\abs{f(z)} \leq A \qty{1 + \abs z}^\nu$ for $\nu$ some fixed real number.
Show that for all $z\in S$, for each integer $n\geq 0$ there exists an $A_n \geq 0$ such that $\abs{f^{(n)}(x)} \leq A_n (1 + \abs x)^\nu$ for all $x\in \RR$.

> Hint: Use the Cauchy inequalities.

## Spring 2020 HW 2, 2.6.9 #complex/exercise/work

Let $\Omega \subset \CC$ be open and bounded and $\phi: \Omega \to \Omega$ holomorphic.
Prove that if there exists a point $z_0 \in \Omega$ such that $\phi(z_0) = z_0$ and $\phi'(z_0) = 1$, then $\phi$ is linear.

> Hint: assume $z_0 = 0$ (explain why this can be done) and write $\phi(z)  = z + a_n z^n + O(z^{n+1})$ near $0$.
  Let $\phi_k = \phi \circ \phi \circ \cdots \circ \phi$ and prove that $\phi_k(z) = z + ka_nz^n  + O(z^{n+1})$.
  Apply Cauchy's inequalities and let $k\to \infty$ to conclude.

## Spring 2020 HW 2, 6 #complex/exercise/work
Show by example that there exists a function $f(z)$ that is holomorphic on $\theset{z\in \CC \suchthat 0 < \abs{z} < 1}$ and for all $r<1$,
\[
\int_{\abs z = r} f(z) \, dz = 0
,\]
but $f$ is not holomorphic at $z=0$.

## Spring 2020 HW 2, 7 #complex/exercise/work
Let $f$ be analytic on a region $R$ and suppose $f'(z_0) \neq 0$ for some $z_0 \in R$.
Show that if $C$ is a circle of sufficiently small radius centered at $z_0$, then 
\[
\frac{2 \pi i}{f^{\prime}\left(z_{0}\right)}=\int_{C} \frac{d z}{f(z)-f\left(z_{0}\right)}
.\]

> Hint: use the inverse function theorem.


## Spring 2020 HW 2, 8 #complex/exercise/work

Assume two functions $u, b: \RR^2 \to \RR$ have continuous partial derivatives at $(x_0 ,y_0)$.
Show that $f \definedas u + iv$ has derivative $f'(z_0)$ at $z_0 = x_0 + iy_0$ if and only if
\[
\lim _{r \rightarrow 0} \frac{1}{\pi r^{2}} \int_{\left|z-z_{0}\right|=r} f(z) d z=0
.\]





## Spring 2020 HW 2, 10 #complex/exercise/work
Let $f(z)$ be bounded and analytic in $\CC$.
Let $a\neq b$ be any fixed complex numbers.
Show that the following limit exists:
\[
\lim_{R\to \infty} \int_{\abs z = R} {f(z) \over (z-a)(z-b)} \,dz
.\]

Use this to show that $f(z)$ must be constant.


## Spring 2020 HW 2, 11 #complex/exercise/work
Suppose $f(z)$ is entire and 
\[
\lim_{z\to\infty} {f(z) \over z} = 0
.\]

Show that $f(z)$ is a constant.

## Spring 2020 HW 2, 12 #complex/exercise/work
Let $f$ be analytic in a domain $D$ and $\gamma$ be a closed curve in $D$.
For any $z_0\in D$ not on $\gamma$, show that
\[
\int_{\gamma} \frac{f^{\prime}(z)}{\left(z-z_{0}\right)} d z=\int_{\gamma} \frac{f(z)}{\left(z-z_{0}\right)^{2}} d z
.\]
Give a generalization of this result.


## Spring 2020 HW 2, 13 #complex/exercise/work

Compute
\[
\int_{\abs z = 1} \qty{z + {1\over z}}^{2n} {dz \over z}
\]
and use it to show that
\[
\int_0^{2\pi} \cos^{2n}(\theta) \, d\theta = 2\pi \qty{1\cdot 3 \cdot 5 \cdots (2n-1) \over 2 \cdot 4 \cdot 6 \cdots (2n)}
.\]


