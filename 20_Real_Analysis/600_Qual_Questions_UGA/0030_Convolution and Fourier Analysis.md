# $L^2$ and Fourier Analysis


## Fall 2020.5 #real_analysis/qual/completed

^31cd83


:::{.problem title="?"}
Suppose $\varphi\in L^1(\RR)$ with 
\[  
\int \varphi(x) \, dx = \alpha
.\]
For each $\delta > 0$ and $f\in L^1(\RR)$, define
\[  
A_\delta f(x) \da \int f(x-y) \delta^{-1} \varphi\qty{\delta^{-1} y}\, dy
.\]

a.
Prove that for all $\delta > 0$,
\[  
\norm{A_\delta f}_1 \leq \norm{\varphi}_1 \norm{f}_1
.\]

b.
Prove that 
\[  
A_\delta f \to \alpha f \text{ in } L^1(\RR) \qtext{as} \delta\to 0^+
.\]

> Hint: you may use without proof the fact that for all $f\in L^1(\RR)$,
\[  
\lim_{y\to 0} \int_\RR \abs{f(x-y) - f(x)}\, dx = 0
.\]

:::

:::{.remark}
See Folland 8.14.
:::

:::{.solution title="Part 1"}
This is a direct application of Fubini-Tonelli:
\[
\norm{A_\delta f} 
&\da \int \abs{ \int f(x-y)\delta\inv \varphi(\delta\inv y)\dy} \dx\\
&\leq \int \int \abs{f(x-y)\delta\inv \varphi(\delta\inv y)} \dy \dx\\
&\equalsbecause{FT} \int \int \abs{ f(x-y) } \cdot \abs{\delta\inv \varphi(\delta\inv y)} \dx\dy\\
&= \int \abs{ \delta\inv \varphi(\delta\inv y) } \qty{ \int \abs{ f(x-y) }\dx } \dy \\
&= \int \abs{ \delta\inv \varphi(\delta\inv y)}\cdot  \norm{f} \dy \\
&= \norm{f} \cdot \int \abs{ \delta\inv \varphi(\delta\inv y) }  \dy \\
&= \norm{f} \cdot \norm{\varphi} 
.\]
Here we've used translation and dilation invariance of the Lebesgue integral.

:::

:::{.solution title="Part 2" .foldopen}
Write $\phi_\delta(y) \da \delta\inv\phi(\delta\inv y)$, then
\[
\norm{A_\delta f - \alpha f}_1
&\da \int \abs{A_\delta f(x) - \alpha f(x) } \dx \\
&= \int \abs{ \int {f(x-y) \phi_\delta(y) } \dy - \alpha f(x) }\dx \\
&= \int \abs{ \int { \tau_y f (x) \phi_\delta(y) } \dy - \int f(x) \phi_\delta(y) \dy }\dx \\
&\leq \int\int \abs{\tau_y f(x) - f(x)}\cdot \abs{\phi_\delta(y)} \dy\dx\\
&= \int\int \abs{\tau_y f(x) - f(x)}\cdot \abs{\phi_\delta(y)} \dx\dy \\
&= \int\abs{\phi_\delta(y)}\cdot \norm{\tau_yf - f}_1 \dy
,\]
where the interchange of integration order is justified by Tonelli since the integrands are positive.
The goal is to now make this small when $\delta$ is small.

One way to do this immediately: make a change of variables $y=tz$ to get
\[
\norm{A_\delta f - \alpha f}_1 \leq\int {\abs{\phi(z)}} \norm{\tau_{tz}f -f}_1 \dz
,\]
use that $\norm{\tau_{tz} f- f}_1 \leq 2\norm{f}_1 < \infty$ by the triangle inequality and apply the DCT:
\[
\lim_{t\to 0}
\int {\abs{\phi(z)}} \cdot \norm{\tau_{tz}f -f}_1 \dz =
\int {\abs{\phi(z)}} \lim_{t\to 0} \norm{\tau_{tz}f -f}_1 \dz = 0
.\]

More directly, use continuity in $L^1$ (as per the hint) to pick a $h>0$ such that \[
\norm{\tau_y f - f}< \eps \quad \text{ for } y\in A \da \ts{y\st \abs{y} \leq h}
.\]
Now choose $\delta_0 \gg 1$ large enough so that 
\[
\int_{A^c}\abs{\phi_\delta(y)}\dy < \eps \quad \text{ for all }\delta > \delta_0
.\]
Now
\[
\int_\RR \abs{\phi_\delta(y)}\cdot \norm{\tau_yf - f}_1 \dy
&=
\int_A \abs{\phi_\delta(y)}\cdot \norm{\tau_yf - f}_1 \dy + \int_{A^c} \abs{\phi_\delta(y)}\cdot \norm{\tau_yf - f}_1 \dy \\
&\leq 
\int_A \abs{\phi_\delta(y)}\cdot \eps \dy + \int_{A^c} \abs{\phi_\delta(y)} \cdot 2\norm{f}_1 \dy \\
&\leq \eps\norm{\phi_\delta}_1 + 2\eps\norm{f}_1 \\
&\too 0
.\]
:::

## Spring 2020.6 #real_analysis/qual/completed

:::{.problem title="?"}
\envlist

a.
Show that
\[
L^2([0, 1]) \subseteq L^1([0, 1]) \qtext{and} \ell^1(\ZZ) \subseteq \ell^2(\ZZ)
.\]

b.
For $f\in L^1([0, 1])$ define
\[
\hat{f}(n) \definedas \int _0^1 f(x) e^{-2\pi i n x} \, dx
.\]
Prove that if $f\in L^1([0, 1])$ and $\theset{\hat f(n)} \in \ell^1(\ZZ)$ then
\[
S_N f(x) \definedas \sum_{\abs n \leq N} \hat f (n) e^{2 \pi i n x}
.\]
converges uniformly on $[0, 1]$ to a continuous function $g$ such that $g = f$ almost everywhere.

> Hint: One approach is to argue that if $f\in L^1([0, 1])$ with $\theset{\hat f (n)} \in \ell^1(\ZZ)$ then $f\in L^2([0, 1])$.

:::

:::{.concept}
From Neil:

1. $\hat{f}$ in $\ell^1$ ensures that $S_N$ converges uniformly to something, call it $g$. 
2. $\hat{f} \in\ell^1$ Implies $\hat{f}\in \ell^2$ which (by characterization of an o.n.b.) implies $f$ is in $L^2$ (Parseval) and (again by characterization of an o.n.b.) that $S_N$ converges to $f$ in $L^2$ (and hence a subsequence converges to f a.e.)
3. By uniqueness of limits $f=g$.

Other stuff:

- For $e_n(x) \definedas e^{2\pi i n x}$, the set $\theset{e_n}$ is an orthonormal basis for $L^2([0, 1])$.
- For any orthonormal sequence in a Hilbert space, we have Bessel's inequality:
  \[
  \sum_{k=1}^{\infty}\left|\left\langle x, e_{k}\right\rangle\right|^{2} \leq\|x\|^{2}
  .\]
- When $\theset{e_n}$ is a basis, the above is an *equality* (Parseval)
- Arguing uniform convergence: since $\theset{\hat f(n)} \in \ell^1(\ZZ)$, we should be able to apply the $M$ test.

:::

:::{.solution title="From Neil"}
Claim: if $f\in L^1[0, 1]$ and $\hat f\in \ell^1(\ZZ)$, then $S_Nf \to f$ uniformly.

- Since $\hat f\in \ell^1(\ZZ)$, we have $S_Nf\to g$ uniformly for some continuous $g$ by the $M\dash$test.
- Now consider $\hat g$.
  We have
  \[
  \hat g(n) = \int_0^1 \sum_m \qty{\hat f(m)e_m(x)}e_{-n}(x) \dx = \hat{f}(n)
  ,\]
  using that $\int_0^1 e_n(x)\dx = \chi_{n=0}$.

- We'll now show $f-g= 0$ a.e. by mollifying against an approximate identity $\varphi\in L^1$, setting 
\[
\varphi_\eps(x) \da \eps\inv\varphi(\eps\inv x) \in L^1[0, 1]
.\]

- A computation:
\[
\hat{f\convolve \varphi_\eps}(n) 
&= \hat{f}\cdot \hat{\varphi_\eps}(n) \\
&= \hat{g}\cdot \hat{\varphi_\eps}(n) \\
&= \hat{g\convolve \varphi_\eps}(n) 
,\]
so 
\[
\hat{(f-g)\convolve \varphi_\eps} = 0 \quad \forall n \implies (f-g)\convolve \varphi_\eps \equiv 0
,\]
using that $(f-g)\convolve \varphi_\eps\in L^2$ and $\ts{e_n}$ for a complete orthonormal basis of $L^2$.

- Now use that $(f-g)\convolve \varphi_\eps \to (f-g)$ in $L^1$ and $(f-g)\convolve \varphi_\eps \equiv 0$ to conclude $f-g = 0$ a.e.


:::

:::{.solution title="Part 1"}
\envlist

:::{.claim}
$\ell^1(\ZZ) \subseteq \ell^2(\ZZ)$.
:::

:::{.proof title="?"}
\envlist

- Set $\vector c = \theset{c_k \suchthat k\in \ZZ} \in \ell^1(\ZZ)$.
- It suffices to show that if $\sum_{k\in \ZZ} \abs{c_k} < \infty$ then $\sum_{k\in \ZZ} \abs {c_k}^2 < \infty$.
- Let $S = \theset{c_k \suchthat \abs{c_k} \leq 1}$, then $c_k \in S \implies \abs{c_k}^2 \leq \abs{c_k}$
- Claim: $S^c$ can only contain finitely many elements, all of which are finite.
  - If not, either $S^c \definedas \theset{c_j}_{j=1}^\infty$ is infinite with every $\abs{c_j} > 1$, which forces $$\sum_{c_k\in S^c} \abs{c_k} = \sum_{j=1}^\infty \abs{c_j} > \sum_{j=1}^\infty 1 = \infty.$$
  - If any $c_j = \infty$, then $\sum_{k\in \ZZ} \abs{c_k} \geq c_j = \infty$.
- So $S^c$ is a finite set of finite integers, let $N = \max \theset{\abs{c_j}^2 \suchthat c_j \in S^c} < \infty$.
- Rewrite the sum
\[
\sum_{k\in \ZZ} \abs{c_k}^2 
&= \sum_{c_k\in S} \abs{c_k}^2 + \sum_{c_k \in S^c} \abs{c_k}^2 \\
&\leq \sum_{c_k\in S} \abs{c_k} + \sum_{c_k \in S^c} \abs{c_k}^2 \\
&\leq \sum_{k\in \ZZ} \abs{c_k} + \sum_{c_k \in S^c} \abs{c_k}^2 \quad\text{since the $\abs{c_k}$ are all positive} \\
&= \norm{\vector c}_{\ell^1} + \sum_{c_k \in S^c} \abs{c_k}^2 \\
&\leq \norm{\vector c}_{\ell^1} + \abs{S^c}\cdot N \\
&< \infty
.\]

:::

:::{.claim}
$L^2([0, 1]) \subseteq L^1([0, 1])$.
:::

:::{.proof title="?"}
\envlist

- It suffices to show that $\int \abs{f}^2 < \infty \implies \int \abs{f} < \infty$.
- Define $S = \theset{x\in [0, 1] \suchthat \abs{f(x)} \leq 1}$, then $x\in S^c \implies \abs{f(x)}^2 \geq \abs{f(x)}$.

- Break up the integral:
\[
\int_\RR \abs f 
&= \int_S \abs f + \int_{S^c} \abs f \\
&\leq \int_S \abs{f} + \int_{S^c} \abs{f}^2 \\
&\leq \int_S \abs{f} + \norm{f}_2 \\
&\leq \sup_{x\in S}\theset{\abs{f(x)}} \cdot \mu(S) + \norm{f}_2 \\
&= 1 \cdot \mu(S) + \norm{f}_2 \quad\text{by definition of } S\\
&\leq 1 \cdot \mu([0, 1]) + \norm{f}_2 \quad\text{since } S\subseteq [0, 1] \\
&= 1 + \norm{f}_2 \\
&< \infty
.\]


:::

> Note: this proof shows $L^2(X) \subseteq L^1(X)$ whenever $\mu(X) < \infty$.
:::

:::{.solution title="Part 2"}
\envlist

- First, $S_Nf$ converges in $\mch$ to something, say $g \da \lim_{n\to\infty} S_n f$, since
\[
\norm{g - S_Nf} = \norm{\sum_{\abs n \geq N} \hat f (n) e_n(x) } \leq \sum_{\abs n \geq N } \abs{\hat f(n)} \convergesto{N\to\infty}0
,\]
where the last term is the tail of a convergent sum since $\ts{\hat f(n)} \in \ell^1$.
- This also shows that $S_N\to g$ uniformly.
- $g$ is continuous, as the uniform limit of continuous functions.
- Showing that $g = f$ a.e.: it suffices to show that $S_N$ converges to $f$ in $L^p$ for some $p$, since this will provide a subsequence that converges to $f$ a.e..

- Claim: $\hat{f}\in \ell^1 \subseteq \ell^2$ implies that $f \in L^2$.
  This follows from Parseval:
\[
\infty > \norm{\hat f}_{\ell^2}^2
= \sum_{n\in \ZZ} \abs{\hat f(n)}^2
= \int_0^1 \abs{f(z)}^2 \dz 
= \norm{f}_{L^2}^2
.\]
- Claim: $S_N\to f$ in $L^2$.
  - This follows from the fact that $\ts{e_n}_{n\in \ZZ}$ is a complete orthonormal basis, so $f = \sum \inner{f}{e_n}e_n$ uniquely, recognizing $\hat{f}(n) = \inner{f}{e_n}$, and writing
  \[
  f = \sum_{n} \inner{f}{e_n}e_n = \sum_n \hat{f}(n) e_n \da \lim_{N\to\infty }S_N f
  .\]
- So a subsequence $\ts{S_{N_k}}_{k\geq 0}$ converges to $f$ a.e..
  Since $S_N\to g$ a.e., $f=g$ a.e. by uniqueness of limits.
:::

## Fall 2017.5 #real_analysis/qual/completed

^2ef915

Let $\varphi$ be a compactly supported smooth function that vanishes outside of an interval $[-N, N]$ such that $\int _{\RR} \varphi(x) \, dx = 1$.

For $f\in L^1(\RR)$, define
\[
K_{j}(x) \definedas j \varphi(j x), 
\qquad 
f \ast K_{j}(x) \definedas \int_{\RR} f(x-y) K_{j}(y) \, dy
\]
and prove the following:

1. Each $f\ast K_j$ is smooth and compactly supported.

2. 
\[
\lim _{j \to \infty} \norm{f * K_{j}-f}_{1} = 0
\]

> Hint:
\[
\lim _{y \to 0} \int _{\RR} |f(x-y)-f(x)| dy = 0
\]

\todo[inline]{Add concepts.}

:::{.solution}
\hfill
:::{.concept}
\hfill
- ?
:::


**Part a**

**Lemma:** If $\varphi \in C_c^1$, then
$(f \ast \varphi)' = f \ast \varphi'$ almost everywhere.

*Silly Proof:*

\[
\mathcal{F}(
	(f \ast \varphi)'
 )
&= 2\pi i \xi ~\mathcal{F}(f\ast \varphi) \\
&= 2\pi i \xi ~ \mathcal{F}(f) ~ \mathcal{F}(\varphi) \\
&= \mathcal{F}(f) \cdot \left( 2\pi i \xi ~\mathcal{F}(\varphi)\right) \\
&= \mathcal{F}(f) \cdot \mathcal{F}(\varphi') \\
&= \mathcal{F}(f\ast \varphi')
.\]

*Actual proof*:

\[
(f\ast \varphi)'(x)
&= (\varphi\ast f)'(x) \\
&= \lim_{h\to 0} \frac{(\varphi\ast f)'(x+h) - (\varphi\ast f)'(x)}{h} \\
&= \lim_{h\to 0} \int \frac{\varphi(x + h - y) - \varphi(x - y)}{h} f(y) \\
&\overset{DCT}=  \int \lim_{h\to 0} \frac{\varphi(x + h - y) - \varphi(x - y)}{h} f(y) \\
&= \int \varphi'(x-y) f(y) \\
&= (\varphi' \ast f)(x) \\
&= (f \ast \varphi')(x)
.\]
 

 To see that the DCT is justified, we can apply the MVT on the interval $[0, h]$ to $f$ to obtain

\[
\frac{\varphi(x + h - y) - \varphi(x - y)}{h}
&= \varphi'(c) \quad c\in [0, h]
,\]
 
and since $\varphi'$ is continuous and compactly supported, $\varphi'$ is bounded by some $M < \infty$ by the extreme value theorem and thus
\[
\int \abs{\frac{\varphi(x + h - y) - \varphi(x - y)}{h} f(y)} 
&= \int \abs{\varphi'(c) f(y)} \\
&\leq \int \abs{M}\abs{f} \\
&= \abs{M} \int \abs{f} < \infty
,\]

since $f\in L^1$ by assumption, so we can take $g\definedas \abs{M} \abs{f}$ as the dominating function.

Applying this theorem infinitely many times shows that $f\ast \varphi$ is smooth.

To see that $f\ast \varphi$ is compactly supported, approximate $f$ by a *continuous* compactly supported function $h$, so $\norm{h - f}_1 \converges{L^1}\to 0$. 

Now let $g_x(y) = \varphi(x-y)$, and note that $\mathrm{supp}(g) = x - \mathrm{supp}(\varphi)$ which is still compact.
 
But since $\mathrm{supp}(h)$ is bounded, there is some $N$ such that 
$$
\abs{x} > N \implies A_x\definedas \mathrm{supp}(h) \intersect \mathrm{supp}(g_x) = \emptyset
$$

and thus 
\[
(h\ast \varphi)(x) 
&= \int_\RR \varphi(x-y) h(y)~dy \\
&= \int_{A_x} g_x(y) h(y) \\
&= 0
,\]

so $\theset{x \suchthat f\ast g(x) = 0}$ is open, and its complement is closed and bounded and thus compact.

**Part b**

\[
\norm{f\ast K_j - f}_1 
&= \int \abs{\int f(x-y) K_j(y) ~dy  - f(x)}~dx \\
&= \int \abs{\int f(x-y) K_j(y) ~dy  - \int f(x) K_j(y) ~ dy}~dx \\
&= \int \abs{\int ( f(x-y) - f(x) ) K_j(y) ~dy } ~dx \\
&\leq \int \int \abs{(f(x-y) - f(x))} \cdot \abs{K_j(y)} ~ dy~dx \\
&\overset{FT}= \int \int \abs{(f(x-y) - f(x))} \cdot \abs{K_j(y)} \mathbf{~ dx~dy}\\
&= \int \abs{K_j(y)} \left( \int \abs{(f(x-y) - f(x))}  ~ dx\right) ~dy \\
&= \int \abs{K_j(y)} \cdot \norm{f - \tau_y f}_1 ~dy
.\]

We now split the integral up into pieces. 

1. Chose $\delta$ small enough such that
 $\abs{y} < \delta \implies \norm{f - \tau_y f}_1 < \varepsilon$ by continuity of translation in $L^1$, and

2. Since $\varphi$ is compactly supported, choose $J$ large enough such that
$$
j > J \implies \int_{\abs{y} \geq \delta} \abs{K_j(y)} ~dy 
= \int_{\abs{y} \geq \delta} \abs{j\varphi(jy)} = 0
$$

Then
\[
\norm{f\ast K_j - f}_1 
&\leq 
\int \abs{K_j(y)} \cdot \norm{f - \tau_y f}_1 ~dy \\
&= \int_{\abs y < \delta} \abs{K_j(y)} \cdot \norm{f - \tau_y f}_1 ~dy+ \int_{\abs y \geq  \delta} \abs{K_j(y)} \cdot \norm{f - \tau_y f}_1 ~dy \\
&= \varepsilon \int_{\abs y \geq  \delta} \abs{K_j(y)} + 0 \\
&\leq \varepsilon(1) \to 0
.\]


:::



## Spring 2017.5 #real_analysis/qual/work

^736e88

Let $f, g \in L^2(\RR)$. 
Prove that the formula
\[
h(x) \definedas \int _{-\infty}^{\infty} f(t) g(x-t) \, dt
\]
defines a uniformly continuous function $h$ on $\RR$.

## Spring 2015.6 #real_analysis/qual/work
Let $f \in L^1(\RR)$ and $g$ be a bounded measurable function on $\RR$.

1. Show that the convolution $f\ast g$ is well-defined, bounded, and uniformly continuous on $\RR$.
2. Prove that one further assumes that $g \in C^1(\RR)$ with bounded derivative, then $f\ast g \in C^1(\RR)$ and
\[
\frac{d}{d x}(f * g)=f *\left(\frac{d}{d x} g\right)
\]

## Fall 2014.5 #real_analysis/qual/work

1. Let $f \in C_c^0(\RR^n)$, and show
\[
\lim _{t \to 0} \int_{\RR^n} |f(x+t) - f(x)| \, dx = 0
.\]

2. Extend the above result to $f\in L^1(\RR^n)$ and show that
\[
f\in L^1(\RR^n), \quad g\in L^\infty(\RR^n) \quad
\implies f \ast g \text{ is bounded and uniformly continuous. }
\]


