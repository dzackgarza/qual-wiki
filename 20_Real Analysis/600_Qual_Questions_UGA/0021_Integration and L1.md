# Integrals: Approximation

## Fall 2021.2 #completed

:::{.problem title="?"}
a.
Let $F \subset \mathbb{R}$ be closed, and define
\[
\delta_{F}(y):=\inf _{x \in F}|x-y| .
\]
For $y \notin F$, show that
\[
\int_{F}|x-y|^{-2} d x \leq \frac{2}{\delta_F(y)},
\]
b.
Let $F \subset \mathbb{R}$ be a closed set whose complement has finite measure, i.e. $m(\RR \sm F)< \infty$. 
Define the function
\[
I(x):=\int_{\mathbb{R}} \frac{\delta_{F}(y)}{|x-y|^{2}} d y
\]
Prove that $I(x)=\infty$ if $x \not\in F$, however $I(x)<\infty$ for almost every $x \in F$. 

  > Hint: investigate $\int_{F} I(x) d x$.

:::

:::{.solution title="Part a"}
Let $y\in F^c$ which is open, then one can find an epsilon ball about $y$ avoiding $F$.
We can take $\eps \da \delta_F(y)$ to define $A \da B_{\eps}(y)$, and we still have $A \subseteq F^c$ and $F \subseteq A^c$.
Note that $\abs{x-y}^2 = (x-y)^2$ since this is always positive, then
\[
\int_F \abs{x-y}^{-2} \dx 
&\leq \int_{A^c} \abs{x-y}^{-2} \dx \\
&= \int_{-\infty}^{-\eps} \qty{x-y}^{-2} \dx + \int_{\eps}^{\infty} \qty{x-y}^{-2}\dx \\
&= \int_{-\infty}^{-\eps} u^{-2} \dx + \int_{\eps}^{\infty} u^{-2} \dx \\
&= -u\inv \evalfrom_{u=-\eps}^{u=-\infty}- u\inv\evalfrom_{u=\infty}^{u=\eps} \\
&= {2\over \eps} \\
&\da {2\over \delta_F(y)}
.\]
:::


:::{.solution title="Part b"}
Estimate:
\[
\int_F I(x) \dx 
&\da \int_F \int_\RR {\delta_F(y) \over (x-y)^2 } \dy \dx \\
&= \int_\RR \delta_F(y) \int_F {1\over (x-y)^2} \dx \dy \\
&= \int_F \delta_F(y) \int_F {1\over (x-y)^2} \dx \dy 
+ \int_{F^c} \delta_F(y) \int_F {1\over (x-y)^2} \dx \dy \\
&= 0
+ \int_{F^c} \delta_F(y) \int_F {1\over (x-y)^2} \dx \dy \\
&\leq
\int_{F^c} 2 \dy \\
&= 2\mu(F^c) \\
&<\infty
,\]
where we've used that $y\in F\implies \delta_F(y) = 0$.
This forces $I(x) < \infty$ for almost every $x\in F$, since if $I(x)$ is unbounded on any positive measure set then this integral would diverge.
We've also implicitly used Fubini-Tonelli to change the order of integration, justified by positivity of the integrand and the finite iterated integral.
:::




## Spring 2018.3 #completed
Let $f$ be a non-negative measurable function on $[0, 1]$. 

Show that
\[
\lim _{p \rightarrow \infty}\left(\int_{[0,1]} f(x)^{p} d x\right)^{\frac{1}{p}}=\|f\|_{\infty}.
\]

:::{.concept}
\envlist
- $\norm{f}_\infty \definedas \inf_t {\theset{ t\suchthat m\qty{\theset{x\in \RR^n \suchthat f(x) > t}} = 0 } }$, i.e. this is the lowest upper bound that holds almost everywhere.
:::

:::{.solution}
\envlist

- $\norm{f}_p \leq \norm{f}_\infty$:
  - Note $\abs{f(x)} \leq \norm{f}_\infty$ almost everywhere and taking $p$th powers preserves this inequality.
  - Thus
  \[
  \abs{f(x)} &\leq \norm{f}_\infty \quad\text{a.e. by definition} \\
  \implies 
  \abs{f(x)}^p &\leq \norm{f}_\infty^p \quad\text{for } p\geq 0 \\  
  \implies
  \norm{f}_p^p 
  &= \int_X \abs{f(x)}^p ~dx \\
  &\leq \int_X \norm{f}_\infty^p ~dx  \\
  &= \norm{f}_\infty^p \int_X 1\,dx \\ 
  &= \norm{f}_\infty^p \cdot m(X) \quad\text{since the norm doesn't depend on }x \\
  &= \norm{f}_\infty^p \qquad \text{since } m(X) = 1
  .\]

    - Thus $\norm{f}_p \leq \norm{f}_\infty$ for all $p$ and taking $\lim_{p\to\infty}$ preserves this inequality.

- $\norm{f}_p \geq \norm{f}_\infty$:
  - Fix $\varepsilon > 0$.

  - Define 
  \[
  S_\varepsilon \definedas \theset{x\in \RR^n \suchthat \abs{f(x)} \geq \norm{f}_\infty - \varepsilon}
  .\]

    - Note that $m(S_\eps) > 0$; otherwise if $m(S_\eps) = 0$, then $t\definedas \norm{f}_\infty - \eps < \norm{f}_\eps$.
    But this produces a *smaller* upper bound almost everywhere than $\norm{f}_\eps$, contradicting the definition of $\norm{f}_\eps$ as an infimum over such bounds.
    


  - Then
  \[
  \norm{f}_p^p 
  &= \int_X \abs{f(x)}^p ~dx \\
  &\geq \int_{S_\varepsilon} \abs{f(x)}^p ~dx \quad\text{since } S_\eps \subseteq X \\
  &\geq \int_{S_\varepsilon} \abs{\norm{f}_\infty - \varepsilon}^p ~dx \quad\text{since on } S_\eps, \abs{f} \geq \norm{f}_\infty - \eps \\
  &= \abs{\norm{f}_\infty - \varepsilon}^p \cdot m(S_\varepsilon) \quad\text{since the integrand is independent of }x \\
  & \geq 0 \quad\text{since } m(S_\eps) > 0
  \]
  
  - Taking $p$th roots for $p\geq 1$ preserves the inequality, so
  \[
  \implies \norm{f}_p &\geq \abs{\norm{f}_\infty - \varepsilon} \cdot m(S_\varepsilon)^{\frac 1 p} 
  \converges{p\to\infty}\too \abs{\norm{f}_\infty - \varepsilon} 
  \converges{\varepsilon \to 0}\too \norm{f}_\infty
  \]
  where we've used the fact that above arguments work 

  - Thus $\norm{f}_p \geq \norm{f}_\infty$.


:::


## Spring 2018.4 #completed
Let $f\in L^2([0, 1])$ and suppose
$$
\int _{[0,1]} f(x) x^{n} d x=0 \text { for all integers } n \geq 0.
$$
Show that $f = 0$ almost everywhere.

:::{.concept}
\envlist
- Weierstrass Approximation: A continuous function on a compact set can be uniformly approximated by polynomials.
- $C^1([0, 1])$ is dense in $L^2([0, 1])$
- Polynomials are dense in $L^p(X, \mathcal{M}, \mu)$ for any $X\subseteq \RR^n$ compact and $\mu$ a finite measure, for all $1\leq p < \infty$.
  - Use Weierstrass Approximation, then uniform convergence implies $L^p(\mu)$ convergence by DCT.
:::

:::{.solution}
\envlist

:::{.proof title="using Fourier transforms"}
\envlist

- Fix $k \in \ZZ$.
- Since $e^{2\pi i k x}$ is continuous on the compact interval $[0, 1]$, it is uniformly continuous.
- Thus there is a sequence of polynomials $P_\ell$ such that 
$$
P_{\ell, k} \converges{\ell\to\infty}\too e^{2\pi i k x} \text{ uniformly on } [0,1]
.$$

- Note applying linearity to the assumption $\int f(x) \, x^n$, we have
$$
\int f(x) x^n \,dx = 0 ~\forall n \implies \int f(x) p(x) \,dx = 0 
$$
  for any polynomial $p(x)$, and in particular for $P_{\ell, k}(x)$ for every $\ell$ and every $k$.

- But then  
\[
\inner{f}{e_k} 
&= \int_0^1 f(x) e^{-2\pi i k x} ~dx \\
&= \int_0^1 f(x) \lim_{\ell \to \infty} P_\ell(x) \\
&= \lim_{\ell \to \infty}  \int_0^1 f(x) P_\ell(x) \quad\quad \text{by uniform convergence on a compact interval} \\
&= \lim_{\ell \to \infty} 0 \quad\text{by assumption}\\
&= 0 \quad \forall k\in \ZZ
,\]
 so $f$ is orthogonal to every $e_k$. 

- Thus $f\in S^\perp \definedas \spanof_\CC\theset{e_k}_{k\in \ZZ}^\perp \subseteq L^2([0, 1])$, but since this is a basis, $S$ is dense and thus $S^\perp = \theset{0}$ in $L^2([0, 1])$.

- Thus $f\equiv 0$ in $L^2([0, 1])$, which implies that $f$ is zero almost everywhere.

:::

:::{.proof title="Alternative"}
\envlist

- By density of polynomials, for $f\in L^2([0, 1])$ choose $p_\eps(x)$ such that $\norm{f - p_\eps} < \eps$ by Weierstrass approximation.
- Then on one hand,
\[
\norm{f(f-p_\eps)}_1 
&= \norm{f^2}_1 - \norm{f\cdot p_\eps}_1 \\
&= \norm{f^2}_1 - 0 \quad\text{by assumption} \\
&= \norm{f}_2^2
.\]

  - Where we've used that $\norm{f^2}_1 = \int \abs{f^2} = \int \abs{f}^2 = \norm{f}_2^2$.

- On the other hand
\[
\norm{f(f-p_\eps)} 
&\leq \norm{f}_1 \norm{f-p_\eps}_\infty \quad\text{by Holder} \\
&\leq \eps \norm{f}_1  \\
&\leq \eps \norm{f}_2 \sqrt{m(X)} \\ 
&= \eps \norm{f}_2 \quad\text{since } m(X)= 1
.\]
  - Where we've used that $\norm{fg}_1 = \int \abs{fg} = \int \abs{f}\abs{g} \leq \int \norm{f}_\infty \abs{g} = \norm{f}_\infty \norm{g}_1$.

- Combining these,
\[
\norm{f}_2^2 \leq \norm{f}_2 \eps \implies \norm{f}_2 < \eps \to 0,
.\]
  so $\norm{f}_2 = 0$, which implies $f=0$ almost everywhere.


:::

:::

## Spring 2015.2 #work
Let $f: \RR \to \CC$ be continuous with period 1. 
Prove that
\[
\lim _{N \rightarrow \infty} \frac{1}{N} \sum_{n=1}^{N} f(n \alpha)=\int_{0}^{1} f(t) d t \quad \forall \alpha \in \RR\setminus\QQ.
\]

> Hint: show this first for the functions $f(t) = e^{2\pi i k t}$ for $k\in \ZZ$.


## Fall 2014.4 #work
Let $g\in L^\infty([0, 1])$
Prove that
\[
\int _{[0,1]} f(x) g(x)\, dx = 0 
\quad\text{for all continuous } f:[0, 1] \to \RR 
\implies g(x) = 0 \text{ almost everywhere. }
\]


# $L^1$

## Spring 2021.4 #completed

Let $f, g$ be Lebesgue integrable on $\RR$ and let $g_n(x) \da g(x- n)$.
Prove that
\[
\lim_{n\to \infty } \norm{f + g_n}_1 = \norm{f}_1 + \norm{g}_1
.\]

:::{.concept}
\envlist

- For $f\in L^1(X)$, $\norm{f}_1 \da \int_X \abs{f(x)} \dx < \infty$.

- Small tails in $L_1$: if $f\in L^1(\RR^n)$, then for every $\eps>0$ exists some radius $R$ such that
\[
\norm{f}_{L^1(B_R^c)} < \eps
.\]

- Shift $g$ to the right far enough so that the two densities are mostly disjoint:

![Shifting density](figures/densities.png)

- Any integral $\int_a^b f$ can be written as $\norm{f}_1 - O(\text{err})$.

- Bounding technique: 
\[
a-\eps \leq b \leq a+\eps \implies b=a
.\]

:::

:::{.solution}
\envlist

- Fix $\eps$.
- Using small tails for $f, g \in L^1$, choose $R_1, R_2 \gg 0$ so that
\[
\int_{B_{R_1}(0)^c} \abs{f} &< \eps \\
\int_{B_{R_2}(0)^c} \abs{g} &< \eps
.\]

  - Note that this implies
  \[
  \int_{-R_1}^{R_1} \abs{f} &= \norm{f}_1 - 2\eps \\
  \int_{-R_2}^{R_2} \abs{g_N} &= \norm{g_N} - 2\eps 
  .\]

  - Also note that by translation invariance of the Lebesgue integral, $\norm{g}_1 = \norm{g_N}_1$.


- Now use $N$ to make the densities almost disjoint: choose $N\gg 1$ so that $N-R_2 > R_1$:

![Shifting density](figures/densities.png)

- Consider the change of variables $x\mapsto x-N$:
\[
\int_{-R_2}^{R_2} \abs{g(x)}\dx 
= \int_{N-R_2} ^{N+R_2} \abs{g(x-N)} \dx
\da \int_{N-R_2} ^{N+R_2} \abs{g_N(x)} \dx
.\]
  - Use this to conclude that
  \[
  \int_{N-R_2}^{N+R_2} \abs{g_N} = \norm{g_N} - 2\eps
  .\]

- Now split the integral in the problem statement at $R_1$:

\[
\norm{f + g_N}_1 
= \int_\RR \abs{f+g_N} 
= \int_{-\infty}^{R_1} \abs{f+ g_N}
+ \int_{R_1}^{\infty} \abs{f+ g_N}
\da I_1 + I_2
.\]

- **Idea**: from the picture, 

  - On $I_1$, $f$ is big and $g_N$ is small
  - On $I_2$, $f$ is small and $g_N$ is big

- Casework: estimate $I_1, I_2$ separately, bounding from above and below.

- $I_1$ upper bound:
  \[
  I_1 
  &\da \int_{-\infty}^{R_1} \abs{f + g_N} \\
  &\leq \int_{-\infty}^{R_1} \abs{f} + \abs{g_N} \\
  &= \int_{-\infty}^{R_1} \abs{f} + \int_{-\infty}^{R_1} \abs{g_N} \\
  &\leq \int_{-\infty}^{R_1} \abs{f} + \int_{-\infty}^{\color{green} N - R_2} \abs{g_N} && R_1 < N-R_2 \\
  &= \norm{f}_1 - \int_{R_1}^{\infty} \abs{f} + \int_{-\infty}^{N - R_2} \abs{g_N} \\
  &\leq \norm{f}_1 - \int_{R_1}^{\infty} \abs{f} + \eps \\
  &\leq \norm{f}_1 + \eps
  .\]
  
  - In the last step we've used that we're subtracting off a positive number, so forgetting it only makes things larger.
  
  - We've also used monotonicity of the Lebesgue integral: if $A\leq B$, then $(c, A) \subseteq (c, B)$ and $\int_{c}^A \abs f \leq \int_c^B \abs{f}$ since $\abs f$ is positive.

- $I_1$ lower bound:
\[
I_1 
&\da \int_{-\infty}^{R_1} \abs{f + g_N} \\
&\geq \int_{-\infty}^{R_1} \abs{f} - \abs{g_N} \\
&= \int_{-\infty}^{R_1} \abs{f} - \int_{-\infty}^{R_1} \abs{g_N} \\
&\geq \int_{-\infty}^{R_1} \abs{f} - \int_{-\infty}^{\color{green} N-R_2} \abs{g_N} && R_1 < N-R_2 \\
&= \norm{f}_1 - \int_{R_1}^{ \infty } \abs f - \int_{- \infty }^{N-R_2} \abs {g_N} \\
&\geq \norm{f}_1 - \eps - \eps \\
&= \norm{f}_1 - 2\eps
.\]

  - Now we've used that the integral with $g_N$ comes in with a negative sign, so extending the range of integration only makes things *smaller*.
  We've also used the $\eps$ bound on both $f$ and $g_N$ here, and both are tail estimates.

- Taken together we conclude
\[
\norm{f}_1 - 2\eps
\leq I_1
\leq \norm{f}_1 && \eps\to 0 \implies  I_1 = \norm{f}_1
.\]


- $I_2$ lower bound:
\[
I_2 
&\da \int_{R_1}^{\infty} \abs{f + g_N} \\
&\leq \int_{R_1}^{\infty} \abs{f} + \int_{R_1}^{\infty} {g_N} \\
&\leq \int_{R_1}^{\infty} \abs{f} + \norm{g_N}_1 - \int_{-\infty}^{R_1} \abs{g_N} \\
&\leq \eps + \norm{g_N}_1 - \int_{-\infty}^{R_1} \abs{g_N} \\
&\leq \eps + \norm{g_N}_1 \\
&= \eps + \norm{g}_1 
.\]

  - Here we've again thrown away negative terms, only increasing the bound, and used the tail estimate on $f$.

- $I_2$ upper bound:

\[
I_2 
&\da \int_{R_1}^{\infty} \abs{f + g_N} \\
&= \int_{R_1}^{\infty} \abs{g_N + f} \\
&\geq \int_{R_1}^{\infty} \abs{g_N} - \int_{R_1}^{\infty} \abs{f} \\
&=  \norm{g_N} - \int_{-\infty}^{R_1} \abs{g_N} - \int_{R_1}^{\infty} \abs{f} \\
&\geq  \norm{g_N} - 2\eps
.\]

  - Here we've swapped the order under the absolute value, and used the tail estimates on both $g$ and $f$.

- Taken together:
\[
\norm{g}_1 - \eps \leq I_2 \leq \norm{g}_1 + 2\eps 
.\]

- Note that we have two inequalities:
\[
\norm{f}_1 - 2\eps &\leq \int_{-\infty}^{R_1} \abs{f -g_N} \leq \norm{f}_1 + \eps \\
\norm{g}_1 - 2\eps &\leq \int^{\infty}_{R_1} \abs{f -g_N} \leq \norm{g}_1 + \eps 
.\]

- Add these to obtain
\[
\norm{f}_1 + \norm{g}_1 - 4\eps \leq I_1 + I_2 \da \norm{f - g_N}_1 \leq \norm{f} + \norm{g}_1 + 2\eps
.\]

- Check that as $N\to \infty$ as $\eps\to 0$ to yield the result.

:::

## Fall 2020.4 #completed

:::{.problem title="?"}
Prove that if $xf(x) \in L^1(\RR)$, then
\[  
F(y) \da \int f(x) \cos(yx)\,  dx
\]
defines a $C^1$ function.
:::

:::{.solution }

- Fix $y_0$, we'll show $F'$ exists and is continuous at $y_0$.
- Fix a sequence $y_n\decreasesto y_0$ and define
\[
h_n(x) \da 
{ h(x, y_n) - h(x, y_0) \over y_n - y_0} && h(x, y) \da f(x) \cos(yx)
.\]

- We can then write 
\[
\dd{h}{y}(x, y_0) 
= \lim_{n\to \infty} h_n(x)
.\]
- Apply the MVT:
\[
h_n(x) \da { h(x, y_n) - h(x, y_0) \over y_n - y_0}
&= \dd{h}{y}(x, \tilde y) && \text{ for some } \tilde y \in [y_0, y_n]
.\]

- Use this to get a bound for DCT:
\[
\abs{h_n(x)}
&\da \abs{ h(x, y_n) - h(x, y_0) \over y_n - y_0} \\
&= \abs{ \dd{h}{y}(x, \tilde y) } \\
&\leq \sup_{y\in [y_0, y_n]} \abs{ \dd{h}{y}(x, y) } \\
&\leq \sup_{y\in [y_0, y_n]} \abs{ xf(x) \sin(yx) } \\
&\leq \abs{ xf(x) }
,\]
  and by assumption $xf(x) \in L^1$.

- So this justifies commuting an integral and a limit:
\[
F'(y_0) 
&\da \lim_{y_n\to y_0} { F(y_n) - F(y_0) \over y_n - y_0} \\
&= \lim_{n\to 0} \int {h_n(x)  } \dx \\
&\equalsbecause{\text{DCT}} \int \lim_{n\to\infty} h_n(x) \dx \\
&\da \int \dd{h}{y}(x, y_0) \dx \\
&\da - \int xf(x) \sin(yx) \dx 
,\]
and since this limit exists and is finite, $F$ is differentiable at $y_0$.

- That $F$ is continuous:
\[
\lim_{y_n \to y_0} F'(y_n)
&= \lim_{y_n \to y_0} \int \dd{h}{y}(x, y_n) \dx \\
&\equalsbecause{\text{DCT}} \int \lim_{y_n \to y_0} \dd{h}{y}(x, y_n) \dx \\
&= - \int \lim_{y_n \to y_0} xf(x) \sin(y_n x) \dx \\
&= - \int xf(x) \sin(y_0x) \dx 
,\]
where we've used that $y\mapsto \sin(yx)$ is clearly continuous.




:::

## Spring 2020.3 #completed

a. Prove that if $g\in L^1(\RR)$ then
\[
\lim_{N\to \infty} \int _{\abs{x} \geq N} \abs{f(x)} \, dx = 0
,\]
and demonstrate that it is not necessarily the case that $f(x) \to 0$ as $\abs{x}\to \infty$.

b. Prove that if $f\in L^1([1, \infty])$ and is decreasing, then $\lim_{x\to\infty}f(x) =0$ and in fact $\lim_{x\to \infty} xf(x) = 0$.

c. If $f: [1, \infty) \to [0, \infty)$ is decreasing with $\lim_{x\to \infty} xf(x) = 0$, does this ensure that $f\in L^1([1, \infty))$?

:::{.concept}
\envlist
- Limits
- Cauchy Criterion for Integrals: $\int_a^\infty f(x) \,dx$ converges iff for every $\eps>0$ there exists an $M_0$ such that $A,B\geq M_0$ implies $\abs{\int_A^B f} < \eps$, i.e. $\abs{\int_A^B f} \converges{A\to\infty}\to 0$.
- Integrals of $L^1$ functions have vanishing tails: $\int_{N}^\infty \abs{f} \converges{N\to\infty}\too 0$.
- Mean Value Theorem for Integrals: $\int_a^b f(t)\, dt = (b-a) f(c)$ for some $c\in [a, b]$.
:::

:::{.solution title="of a"}
Stated integral equality: 

- Let $\eps > 0$
- $C_c(\RR^n) \injects L^1(\RR^n)$ is dense so choose $\theset{f_n} \to f$ with $\norm{f_n - f}_1 \to 0$.
- Since $\theset{f_n}$ are compactly supported, choose $N_0\gg 1$ such that $f_n$ is zero outside of $B_{N_0}(\vector 0)$.
- Then
\[
N\geq N_0 \implies \int_{\abs x > N} \abs{f} &= \int_{\abs x > N} \abs{f - f_n + f_n} \\
&\leq \int_{\abs x > N} \abs{f-f_n} + \int_{\abs x > N} \abs{f_n} \\
&= \int_{\abs x > N} \abs{f-f_n} \\ 
&\leq \int_{\abs x > N} \norm{f-f_n}_1 \\
&= \norm{f_n-f}_1 \qty{\int_{\abs x > N} 1} \\
&\converges{n\to\infty}\too 0 \qty{\int_{\abs x > N} 1} \\
&= 0\\
&\converges{N\to\infty}\too 0
.\]


To see that this doesn't force $f(x)\to 0$ as $\abs{x} \to \infty$:

- Take $f(x)$ to be a train of rectangles of height 1 and area $1/2^j$ centered on even integers.
- Then $$\int_{\abs x > N} \abs{f} = \sum_{j=N}^\infty 1/2^j \converges{N\to\infty}\too 0$$ as the tail of a convergent sum. 
- However $f(x) = 1$ for infinitely many even integers $x > N$, so $f(x) \not\to 0$ as $\abs{x}\to\infty$.
:::

:::{.solution title="of b"}
\envlist

:::{.proof title="Solution 1, a slight trick"}
\envlist

- Since $f$ is decreasing on $[1, \infty)$, for any $t\in [x-n, x]$ we have
\[
x-n \leq t \leq x \implies f(x) \leq f(t) \leq f(x-n)
.\]

- Integrate over $[x, 2x]$, using monotonicity of the integral:
\[
\int_x^{2x} f(x) \,dt \leq 
\int_x^{2x} f(t) \,dt \leq 
\int_x^{2x} f(x-n) \,dt \\ 
\implies 
f(x) \int_x^{2x} \,dt \leq 
\int_x^{2x} f(t) \,dt \leq 
f(x-n) \int_x^{2x} \,dt  \\
\implies xf(x) \leq \int_x^{2x} f(t) \, dt \leq xf(x-n)
.\]

- By the Cauchy Criterion for integrals, $\lim_{x\to \infty} \int_x^{2x} f(t)~dt = 0$.
- So the LHS term $xf(x) \converges{x\to\infty}\too 0$.
- Since $x>1$, $\abs{f(x)} \leq \abs{xf(x)}$ 
- Thus $f(x) \converges{x\to\infty}\too 0$ as well.

:::

:::{.proof title="Solution 2: Variation on the trick"}
\envlist

- Use mean value theorem for integrals:
\[
\int_x^{2x} f(t)\, dt = xf(c_x) \quad\text{for some $c_x \in [x, 2x]$ depending on $x$}
.\]

- Since $f$ is decreasing, 
\[
x\leq c_x \leq 2x 
&\implies f(2x)\leq f(c_x) \leq f(x) \\
&\implies 2xf(2x)\leq 2xf(c_x) \leq 2xf(x) \\
&\implies 2xf(2x)\leq 2x\int_x^{2x} f(t)\, dt \leq 2xf(x) \\
.\]

- By Cauchy Criterion, $\int_x^{2x} f \to 0$.
- So $2x f(2x) \to 0$, which by a change of variables gives $uf(u) \to 0$.
- Since $u\geq 1$, $f(u) \leq uf(u)$ so $f(u) \to 0$ as well.

:::

:::{.proof title="Solution 3: Contradiction"}
Just showing $f(x) \converges{x\to \infty}\too 0$:

- Toward a contradiction, suppose not.
- Since $f$ is decreasing, it can not diverge to $+\infty$
- If $f(x) \to -\infty$, then $f\not\in L^1(\RR)$: choose $x_0 \gg 1$ so that $t\geq x_0 \implies f(t) < -1$, then 
- Then $t\geq x_0 \implies \abs{f(t)} \geq 1$, so
 \[
\int_1^\infty \abs{f} \geq \int_{x_0}^\infty \abs{f(t) } \, dt \geq \int_{x_0}^\infty 1 =\infty
 .\]

- Otherwise $f(x) \to L\neq 0$, some finite limit.
- If $L>0$:
  - Fix $\eps>0$, choose $x_0\gg 1$ such that $t\geq x_0 \implies L-\eps \leq f(t) \leq L$
  - Then $$\int_1^\infty f \geq \int_{x_0}^\infty f \geq \int_{x_0}^\infty \qty{L-\eps}\,dt = \infty$$
- If $L<0$:
  - Fix $\eps > 0$, choose $x_0\gg 1$ such that $t\geq x_0 \implies L \leq f(t) \leq L + \eps$.
  - Then $$\int_1^\infty f \geq \int_{x_0}^\infty f \geq \int_{x_0}^\infty \qty{L}\,dt = \infty$$

Showing $xf(x) \converges{x\to \infty}\too 0$.

- Toward a contradiction, suppose not.
- (How to show that $xf(x) \not\to + \infty$?)
- If $xf(x)\to -\infty$
  - Choose a sequence $\Gamma = \theset{\hat x_i}$ such that $x_i \to \infty$ and $x_i f(x_i) \to -\infty$.
  - Choose a subsequence $\Gamma' = \theset{x_i}$ such that $x_if(x_i) \leq -1$ for all $i$ and $x_i \leq x_{i+1}$.
  - Choose a further subsequence $S = \theset{x_i \in \Gamma' \suchthat 2x_i  < x_{i+1}}$.
  - Then since $f$ is always decreasing, for $t\geq x_0$, $\abs f$ is increasing, and $\abs{f(x_i)} \leq \abs{f(2x_i)}$, so
  \[
  \int_1^{\infty} \abs{f} \geq \int_{x_0}^\infty \abs{f} \geq \sum_{x_i \in S} \int_{x_i}^{2x_i} \abs{f(t)} \, dt \geq 
  \sum_{x_i \in S} \int_{x_i}^{2x_i} \abs{f(x_i)} &= \sum_{x_i \in S} x_i f(x_i) \to \infty
  .\]

- If $xf(x) \to L \neq 0$ for $0 < L< \infty$:
  - Fix $\eps> 0$, choose an infinite sequence $\theset{x_i}$ such that $L-\eps \leq x_i f(x_i) \leq L$ for all $i$.
\[
\int_1^\infty \abs{f} \geq \sum_S \int_{x_i}^{2x_i} \abs{f(t)}\,dt \geq \sum_S \int_{x_i}^{2x_i} f(x_i) \,dt = \sum_S x_i f(x_i) \geq \sum_S \qty{L-\eps} \to \infty
.\]
- If $xf(x) \to L \neq 0$ for $-\infty < L < 0$:
  - Fix $\eps> 0$, choose an infinite sequence $\theset{x_i}$ such that $L \leq x_i f(x_i) \leq L + \eps$ for all $i$.
\[
\int_1^\infty \abs{f} \geq \sum_S \int_{x_i}^{2x_i} \abs{f(t)}\,dt \geq \sum_S \int_{x_i}^{2x_i} f(x_i) \,dt = \sum_S x_i f(x_i) \geq \sum_S \qty{L} \to \infty
.\]

:::

:::{.proof title="Solution 4: Akos' suggestion"}
For $x\geq 1$, 
\[
\abs{xf(x)} = \abs{ \int_x^{2x} f(x) \, dt } \leq \int_x^{2x} \abs{f(x)} \, dt \leq \int_x^{2x} \abs{f(t)}\, dt \leq \int_x^{\infty} \abs{f(t)} \,dt \converges{x\to\infty}\too 0
\]
  where we've used 
  
  - Since $f$ is decreasing and $\lim_{x\to\infty}f(x) =0$ from part (a), $f$ is non-negative.
  - Since $f$ is positive and decreasing, for every $t\in[a, b]$ we have $\abs{f(a)} \leq \abs{f(t)}$.
  - By part (a), the last integral goes to zero.


:::

:::{.proof title="Solution 5: Peter's"}
\envlist

- Toward a contradiction, produce a sequence $x_i\to\infty$ with $x_i f(x_i) \to \infty$ and $x_if(x_i) > \eps > 0$, then
\[
\int f(x) \, dx 
&\geq \sum_{i=1}^\infty \int_{x_i}^{x_{i+1}} f(x) \, dx \\
&\geq \sum_{i=1}^\infty \int_{x_i}^{x_{i+1}} f(x_{i+1}) \, dx \\
&=    \sum_{i=1}^\infty f(x_{i+1}) \int_{x_i}^{x_{i+1}} \, dx \\
&\geq \sum_{i=1}^\infty (x_{i+1} - x_i) f(x_{i+1}) \\
&\geq \sum_{i=1}^\infty (x_{i+1} - x_i) {\eps \over x_{i+1}} \\
&= \eps \sum_{i=1}^\infty \qty{ 1 - {x_{i-1} \over x_i}} \to \infty
\]
  which can be ensured by passing to a subsequence where $\sum {x_{i-1} \over x_i} < \infty$.

:::


:::

:::{.solution title="of c"}
\envlist

- No: take $f(x) = {1\over x\ln x}$
- Then by a $u\dash$substitution,
  \[
  \int_0^x f = \ln\qty{\ln (x)} \converges{x\to\infty}\too \infty
  \]
  is unbounded, so $f\not\in L^1([1, \infty))$.
- But 
  \[
  xf(x) = { 1 \over \ln(x)} \converges{x\to\infty} \too 0
  .\]

:::


## Fall 2019.5 #completed

a.
Show that if $f$ is continuous with compact support on $\RR$, then 
\[
\lim _{y \rightarrow 0} \int_{\mathbb{R}}|f(x-y)-f(x)| d x=0
\]

b. 
Let $f\in L^1(\RR)$ and for each $h > 0$ let 
\[
\mathcal{A}_{h} f(x):=\frac{1}{2 h} \int_{|y| \leq h} f(x-y) d y
\]

  - Prove that $\left\|\mathcal{A}_{h} f\right\|_{1} \leq\|f\|_{1}$ for all $h > 0$.

  - Prove that $\mathcal{A}_h f \to f$ in $L^1(\RR)$ as $h \to 0^+$.

\todo[inline]{Walk through.}

:::{.concept}
\envlist
- Continuity in $L^1$ (recall that DCT won't work! Notes 19.4, prove it for a dense subset first).
- Lebesgue differentiation in 1-dimensional case. See HW 5.6.
:::

:::{.solution}
\envlist

:::{.proof title="of a"}

- Fix $\varepsilon > 0$.
  If we can find a set $A$ such that the following calculation holds for $h$ small enough, we're done:
  \[
  \int_\RR \abs{f(x-h) - f(x)} \dx 
  &= \int_A \abs{f(x-h) - f(x)} \dx \\
  &\leq \int_A \eps \\
  &= \eps \mu(A) \too 0
  ,\]
  provided $h\to 0$ as $\eps\to 0$, which we can arrange if $\abs{h} < \eps$.

- Choose $A\contains \supp f$ compact such that $\supp f \pm 1 \subseteq A$
  - Why this can be done: $\supp f$ is compact, so closed and bounded, and contained in some compact interval $[-M, M]$.
  So e.g. $A\da [-M-1, M+1]$ suffices.
- Note that $f$ is still continuous on $A$, since it is zero on $A\sm \supp f$, and thus uniformly continuous (by Heine-Cantor, for example).
- We can rephrase the usual definition of uniform continuity:
\[
\forall \eps \exists \delta = \delta(\eps) \text{ such that } \abs{x - y} < \delta \implies \abs{f(x) - f(y)} < \eps \quad \forall x, y\in A
\]
as
\[
\forall \eps \exists \delta = \delta(\eps) \text{ such that } \abs{h} < \delta \implies \abs{f(x-h) - f(x)} < \eps \quad \forall x \text{ such that }x, x\pm h \in A
\]

- So fix $\eps$ and choose such a $\delta$ for $A$, and choose $h$ such that $\abs{h} < \min(1, \delta)$.
  Then the desired computation goes through by uniform continuity of $f$ on $A$.

:::

:::{.proof title="of b"}
We have
\[
\int_\RR \abs{A_h(f)(x)} ~dx 
&= \int_\RR \abs{\frac{1}{2h} \int_{x-h}^{x+h} f(y)~dy} ~dx \\
&\leq \frac{1}{2h} \int_\RR \int_{x-h}^{x+h} \abs{f(y)} ~dy ~dx    \\
&=_{FT} \frac{1}{2h} \int_\RR \int_{y-h}^{y+h} \abs{f(y)} ~\mathbf{dx} ~\mathbf{dy}    \\
&= \int_\RR \abs{f(y)} ~{dy} \\
&= \norm{f}_1
,\]

and (rough sketch)

\[
\int_\RR \abs{A_h(f)(x) - f(x)} ~dx 
&= \int_\RR \abs{ \left(\frac{1}{2h} \int_{B(h, x)} f(y)~dy\right) - f(x)}~dx \\
&= \int_\RR \abs{ \left(\frac{1}{2h} \int_{B(h, x)} f(y)~dy\right) - \frac{1}{2h}\int_{B(h, x)} f(x) ~dy}~dx \\
&\leq_{FT} \frac{1}{2h} \int_\RR  \int_{B(h, x)}\abs{ f(y-x) - f(x)} ~\mathbf{dx} ~\mathbf{dy} \\
&\leq \frac 1 {2h} \int_\RR \norm{\tau_x f - f}_1 ~dy \\
&\to 0 \quad\text{by (a)}
.\]

:::

:::


:::{.remark}
This works for arbitrary $f\in L^1$, using approximation by continuous functions with compact support:

- Choose $g\in C_c^0$ such that $\norm{f- g}_1 \to 0$.

- By translation invariance, $\norm{\tau_h f - \tau_h g}_1 \to 0$.

- Write
\[
\norm{\tau f - f}_1 
&= \norm{\tau_h f - g + g - \tau_h g + \tau_h g - f}_1 \\
&\leq \norm{\tau_h f - \tau_h g} + \norm{g - f} + \norm{\tau_h g - g} \\
&\to \norm{\tau_h g - g}
,\]

  so it suffices to show that $\norm{\tau_h g - g} \to 0$.

:::



## Fall 2017.3 #completed
Let 
$$
S = \spanof_\CC\theset{\chi_{(a, b)} \suchthat a, b \in \RR},
$$
the complex linear span of characteristic functions of intervals of the form $(a, b)$.

Show that for every $f\in L^1(\RR)$, there exists a sequence of functions $\theset{f_n} \subset S$ such that 
\[
\lim _{n \rightarrow \infty}\left\|f_{n}-f\right\|_{1}=0
\]

:::{.concept}
\envlist
- From homework: $E$ is Lebesgue measurable iff there exists a finite union of closed cubes $A$ such that $m(E\Delta A) < \varepsilon$.
:::

:::{.solution}
\envlist

- Idea: first show this for characteristic functions, then simple functions, then for arbitrary $f$.

- For characteristic functions:
  - Consider $\chi_{A}$ for $A$ a measurable set.
  - By regularity of the Lebesgue measure, for every $\eps>0$ we can find an $I_\eps$ such that $m(A\Delta I_\eps)< \eps$ where $I_\eps$ is a finite disjoint union of intervals.
  - Then use
  \[
  \eps > m(A\Delta I\eps) = \int_X \abs{\chi_A - \chi_{I_\eps}}
  ,\]
  so the $\chi_{I_\eps}$ converge to $\chi_A$ in $L_1$.

  - Then just note that $\chi_{I_\eps} = \sum_{j\leq N} \chi_{I_j}$ where $I_\eps = \Disjoint_{j\leq N} I_j$, so $\chi_{I_\eps} \in S$.


- For simple functions:
  - Let $\psi = \sum_{k\leq N} c_k \chi_{E_k}$.
  - By the argument above, for each $k$ we can find $I_{\eps, k}$ such that $\chi_{I_{\eps, k}}$ converges to $\chi_{E_k}$ in $L^1$. 
  - So defining $\psi_\eps = \sum_{k\leq N} c_k \chi_{I_{\eps, k}}$, the claim is that this will converge to $\phi$ in $L_1$.
  - Note that 
  \[
  \psi_\eps = \sum_k c_k \chi_{I_{\eps, k}} 
  = \sum_k c_k \sum_j \chi_{I_{j, k} }
  = \sum_{k, j} c_k \chi_{ I_{j, k} } \in S
  \]
  since now the $I_{j, k}$ are indicators of intervals.
  - Moreover
  \[
  \norm{\psi_\eps - \psi} 
  = \norm{ \sum_k c_k \qty{ \chi_{E_k} - \chi_{I_{\eps, k} }}  }
  \leq \sum_k c_k \norm{ \chi_{E_k} - \chi_{I_{\eps, k}} }
  ,\]
  where the last norm can be bounded by the proof for characteristic functions.

- For arbitrary functions:

  - Now just use that every $f \in L^1$ can be approximated by simple functions $\phi_n$ so that $\norm{f-\phi_n}_1 < \eps$ for $n \gg 1$.
  - So find $\phi_n\to f$, and for each $n$, find $g_{n, k} \in S$ with $\norm{g_{n, k} - \phi_n}_1 \convergesto{k\to \infty} 0$, an approximation by functions in $S$.
  - Then
  \[
  \norm{f - g_{n, k}} \leq \norm{f - \phi_n} + \norm{\phi_n - g_{n, k}}
  ,\]
  which can be made arbitrarily small.

:::


## Spring 2015.4 #completed

:::{.problem title="?"}
Define
$$
f(x, y):=\left\{\begin{array}{ll}{\frac{x^{1 / 3}}{(1+x y)^{3 / 2}}} & {\text { if } 0 \leq x \leq y} \\ {0} & {\text { otherwise }}\end{array}\right.
$$

Carefully show that $f \in L^1(\RR^2)$.
:::

:::{.solution}
Note that

\[
\int_{\RR^2}\abs{f} \dmu 
&= \int_0^\infty \int_x^\infty x^{1\over 3}(1+xy)^{-3\over 2} \dy \dx \\
&= \int_0^\infty -2x^{-{ 2\over 3} }(1+xy)^{-{ 1\over 2} }\evalfrom_{y=x}^{y=\infty} \dx \\
&= \int_0^\infty {2\over x^{2\over 3} (1+x^2)^{1\over 2}}\\
&= \int_0^1 {2\over x^{2\over 3} (1+x^2)^{1\over 2}}
+ \int_1^\infty {2\over x^{2\over 3} (1+x^2)^{1\over 2}} \\
&=
\int_0^1 {2\over x^{2\over 3} }
+ \int_1^\infty {2\over x^{5\over 3} } \\
&<\infty
,\]
where 

- For the first term: We've entirely neglected the $1+x^2$ factor, since neglecting to divide by a positive number can only make the integrand larger,
- For the second term:
\[
1+x^2\geq 0 \implies {1\over \sqrt{1+x^2}} \leq {1\over \sqrt{x^2}} = {1\over x}
\]

- Both terms converge by the $p\dash$tests.

The use of iterated integration is justified by Tonelli's theorem on $\abs{f} = f$, since $f$ is non-negative and clearly measurable on $\RR^2$, and if any iterated integral is finite then it is equal to $\int \abs{f}$.

:::

## Fall 2014.3 #completed

:::{.problem title="?"}
Let $f\in L^1(\RR)$. Show that
\[
\forall\varepsilon > 0 \exists \delta > 0 \text{ such that } \qquad 
m(E) < \delta 
\implies 
\int _{E} |f(x)| \, dx < \varepsilon
\]

:::

:::{.solution title="by contradiction" }

- Note that if $m(E) = 0$ then $\int_E f = 0$ for any $f$.
- Toward a contradiction, suppose there exists an $\eps>0$ such that for all $\delta>0$ there exists a set $E_\delta \subseteq \RR$ with $m(E) < \delta$ but $\int_{E_\delta} \abs f > \eps$.
- Let $\delta_n \decreasesto 0$ be any sequence converging to zero and choose $E_n$ with $\int_{E_n} \abs f > \eps$ for every $n$.
- Define $E \da \limsup_n E_n \da \Intersect_{N\geq 1} \Union_{n\geq N} E_n$, then $m(E) = 0$ by Borel-Cantelli.
- Now estimate using Fatou:
\[
\int_{E} \abs{f} 
&= \int_X \chi_E \abs{f} \\
&= \int_X \limsup_n \chi_{E_n} \abs{f} \\
&\geq \limsup_n \int_X \chi_{E_n }\abs{f}  \\
&\geq \limsup_n \int_{E_n} \abs{f} \\
&\geq \limsup_n \eps \\
&= \eps
,\]
however $\displaystyle\int_E \abs{f}\dm = 0$ since $m(E) = 0$, a contradiction. $\contradiction$.
:::

:::{.solution title="direct" }
Note that this is clear for simple functions: let $\phi = \sum_{k\leq n} c_k m(A_k) < \infty$ be simple function. then $\phi$ is necessarily bounded on $\RR$, so let $M\da \sup_\RR \phi$ and estimate
\[
\int_E \phi 
&\da \sum_k c_k m(A_k \intersect E) \\
&\leq \sum_k M\cdot m(E)\\ 
&= C M m(E) 
,\]
for some constant $C$, so choosing $\delta < { \eps \over C M}$ (and its corresponding $E$ with $m(E) < \delta$) bounds this above by $\eps$.

For arbitrary $f \in L^1$, there is a sequence of simple functions $\phi_n$ with $\int \phi_n \increasesto \int f$ and $\norm{\phi_n - f}_{L_1} \convergesto{n\to\infty} 0$.
Choose $\delta$ and $E$ as above,
and use the triangle inequality to estimate
\[
\int_E \abs{f} 
&= \int_E \abs{f - \phi_n + \phi_n} \\
&\leq \int_E \abs{f - \phi_n} + \int_E \abs{\phi_n}
,\]
choose $n\gg 1$ to bound the first term by $\eps$, noting that the second term is bounded by $\eps$ by the case for simple functions.


:::

## Spring 2014.1 #completed

:::{.problem title="?"}
1. Give an example of a continuous $f\in L^1(\RR)$ such that $f(x) \not\to 0$ as$\abs x \to \infty$.

2. Show that if $f$ is *uniformly* continuous, then
\[
\lim_{\abs x \to \infty} f(x) = 0.
\]

:::

:::{.solution}
Part 1:
Take a train of triangles with base points at $k$ and $k+1$, each of area $2^{-k}$.
Then $\int \abs{f} \approx \sum_{k\geq 0} 2^{-k} <\infty$, but $f(x)\not\to 0$ since $f(x) > 0$ infinitely often.

Part 2:

- Idea: use contradiction to produce a sequence with arbitrarily large terms, and bound below an integral in a ball about each point.
- Suppose $\lim_{\abs{x}\to \infty}f(x) = L > 0$.
  - Then for any $\eps$ there exists an $M$ such that $x\geq M \implies \abs{f(x) - L} < \eps$, so $L-\eps \leq f(x) \leq L+\eps$
  - Choosing $\eps=L/2$ yields $L/2 \leq f(x) \leq 3L/2$, and so
  \[
  \int_\RR \abs f
  \geq \int_{\abs x \geq M} \abs{f} \geq \int_{\abs x\geq M} L/2 \to \infty
  ,\]
  contradicting $f\in L^1(\RR)$. $\contradiction$.

- So it must be that this limit does not exist.
  Fix $\eps>0$, then there are infinitely many $x$ such that $f(x) > \eps$, so choose a sequence $x_n\to \infty$ with $f(x_n) > \eps$ for each $n$.

- Now use uniform continuity: pick a uniform $\delta = \delta(\eps)$ such that $x\in B_\delta(x_n) \implies \abs{f(x) - f(x_n)} < \eps/4$.

- Now use that $f(x_n) - \eps/4 \leq f(x) \leq f(x_n)+\eps/4$ implies that $f(x) \geq 3\eps/4$ whenever $x\in B_\delta(x_n)$ for any $n$ to estimate
\[
\int_{B_\delta(x_n)} \abs{f(x)}\dx 
\geq  2\delta \cdot 3\eps/4 \da C = C_{\delta, \eps} > 0
,\]
where $C$ is a constant.
- But now we've contradicted $f\in L^1$:
\[
\int_\RR \abs{f} \geq \sum_{n\geq 1} \int_{B_\delta(x_n)} \abs{f} \geq \sum_{n\geq 1} C \to \infty
,\]
provided we pass to a further subsequence of $x_n$ such that the balls $B_\delta(x_n)$ are disjoint.
$\contradiction$



  
:::


