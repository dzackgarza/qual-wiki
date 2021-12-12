---
order: 7
---

# Holomorphicity 

## Spring 2020 HW 1.7 #completed

:::{.problem title="?"}
Prove that $f(z) = \abs{z}^2$ has a derivative at $z=0$ and nowhere else.
:::

:::{.solution}
The easy check: $f$ is differentiable iff $\delbar_z f = 0$, but
\[
\delbar_z \abs{z}^2 = \delbar_z z\bar{z} = z \neq 0
,\]
unless of course $z=0$.

A more explicit check: check the limits.
\[
{f(z) - f(0) \over z-0} = { \abs{z}^2 \over z } = {z\bar z \over z} = \bar{z} \converges{z\to 0}\too 0
,\]
so $f$ is differentiable at $w=0$.
Now taking $w = Re^{i\theta} \neq 0$,
\[
{f(z) -f(w) \over z-w} = {\abs{z}^2 - \abs{w}^2 \over z - w} 
= {\qty{\abs{z} + \abs{w} } \qty{\abs{z} - \abs{w}} \over z-w }
= {\abs z - \abs w \over z-w}\cdot \qty{\abs{z} + \abs{w}}
.\]
First let $z\to w$ along $\bd \DD_{R'}(0)$ where $R' \da \abs{w}$, so that the numerator vanishes and the limit is zero.
Then let $z\to w$ along the curve $\ts{tw\st t\in [0, 1]}$, then $\abs{z} = t \abs{w}$, so the ratio becomes
\[
{\abs z - \abs w \over z-w}\cdot \qty{\abs{z} + \abs{w}}
&= {t\abs{w}  - \abs w \over tw-w}\cdot \qty{t\abs{w} + \abs{w}} \\
&= {\abs{w}\qty{t-1 } \over w(t-1)} \cdot \abs{w}(t+1) \\
&= { \abs{w}^2(t+1) \over w} \\
&= \bar{w}(t+1) \\
&\converges{t\to 1}\to 2\bar{w}
,\]
which is nonzero is $w\neq 0$.
:::

## Spring 2020 HW 1.8 #completed

:::{.problem title="?"}
Let $f(z)$ be analytic in a domain, and prove that $f$ is constant if it satisfies any of the following conditions:

a. $\abs{f(z)}$ is constant.
b. $\Re(f(z))$ is constant.
c. $\arg(f(z))$ is constant.
d. $\bar{f(z)}$ is analytic.

How do you generalize (a) and (b)?

:::

:::{.solution title="1"}
\envlist

Slick proof: use that no curve $\gamma \subseteq \CC$ is open in $\CC$.

If $\abs{f} = c = r^2$ for some $r$, then the image of $f$ is contained in the curve $\bd \DD_r(0)$.
Since $f$ is holomorphic on the source domain $\Omega$, $f$ is an open map, so if $f$ is nonconstant the $f(\Omega)$ is open.
But $f(\Omega) \subseteq \bd \DD_r(0)$ can not be open, so $f$ must be constant.

The usual more direct proof: write $\abs{f(z)} = u^2 = v^2 = r^2$.
The claim is that both $u$ and $v$ are constant.
Take partial derivatives and clear the factor of 2:
\[
\del_x: \quad uu_x + vv_x &= 0\\
\del_y: \quad uu_y + vv_y &= 0
.\]
Now apply CR: $u_x= v_y, u_y=-v_x$, then
\[
uu_x - vu_y &=0 \\
uu_y + vu_x &=0
.\]
Multiply the first by $u_x$ and the second by $u_y$, then add
\[
uu_x^2 - vu_y u_x &= 0 \\
uu_y^2 + vu_x u_y &=0 \\
\implies u(u_x^2 + u_y^2) &=0
.\]
A similar calculation yields $v(v_x^2 + v_y^2) = 0$, so
If $u(x,y) = v(x, y) = 0$ at any point, then $\abs{f} = 0$ and $f\equiv 0$, so we're done.
Otherwise, $u,v$ do not simultaneously vanish, so we must have
\[
0 = u_x^2 + u_y^2 &\implies 0 = u_x = u_y \implies u \text{ constant }\\
0 = v_x^2 + v_y^2 &\implies 0 = v_x = v_y \implies v \text{ constant }
,\]
so $f=u+iv$ is constant.





:::

:::{.solution title="2"}
Write $f=u+iv$, so $u\equiv c$ is constant.
Then $u_x = u_y = 0$, and CR yields $v_y = u_x = 0$ and $v_y = -u_x = 0$, so $v$ is constant, making $f$ constant.
:::

:::{.solution title="3"}
Slick proof: apply the open mapping theorem again, since $\Arg(f) = \theta_0$ implies that $\im(f) \subseteq \gamma$ for the curve $\gamma \da \ts{t e^{i\theta_0}\st t\in \RR}$ which has no open subsets.

Note that this implies that any $\RR\dash$valued holomorphic function is constant.
:::

:::{.solution title="4"}
Write $f=u+iv$ so $\bar f = u +i\tilde v$ where $\tilde v \da -v$.
Then $u, \tilde v$ are constant, so in particular $\Re(f)$ is constant and by 2 $f$ is constant.
:::



## Spring 2020 HW 1.9 #work

:::{.problem title="?"}
Prove that if $z\mapsto f(z)$ is analytic, then $z \mapsto \bar{f(\bar z)}$ is analytic.
:::


:::{.solution title="Cauchy-Riemann"}
It suffices to show that $g(z) \da \bar{f(\bar z)}$ satisfies CR.
Write $f=u+iv$, then
\[
g(x, y) \da a(x, y) + ib(x, y) = u(x, -y) -i v(x, -y)
,\]
so we want to show $a_x = b_y$ and $a_y = -b_x$.
By the chain rule,
\[
a_x &= \del_x (x\mapsto u(x, -y)) = u_x \\ 
a_y &= \del_x (y\mapsto u(x, y))\circ(y\mapsto -y) = -u_y \\ 
b_x &= \del_x(x\mapsto -v(x, -y)) = -v_x \\
b_y &= \del_x(y \mapsto - v(x, y))\circ(y\mapsto -y) = v_y
.\]
Now use CR for $f$ to write
\[
a_x &= u_x = v_y = b_y \\
a_y &= -u_y = v_x = -b_x
.\]





:::

:::{.solution title="Direct definition"}
Set $g(z) \da (f(z^*))^* \da \bar{f(\bar z)}$, we can then show $g'$ exists:
\[
\lim_{h\to 0} {g(z+h) - g(z) \over h} 
&\da \lim_{h\to 0} {f((z+h)^*)^* - f(z^*)^* \over h^{**}} \\
&= \lim_{h\to 0} {\qty{ f(z^* + h^*) - f(z^*) }^* \over h^{**}} \\
&= \lim_{h\to 0} \qty{ f(z^* + h^* ) - f(z^*) \over h^* }^* \\
&\da \qty{f'(z^*)}^*
,\]
where we've used that $w\mapsto w^*$ is continuous to commute a limit.
So this limit exists, $g$ is differentiable with $g'(z) \da \bar{f'(\bar z)}$.


:::


:::{.solution title="Power series"}
Since $f$ is analytic, take a Laurent expansion $f(z) = \sum_{k\geq 0} c_k z^k$.
Set 
\[
g(z) \da (f(z^*))^*
= \qty{\sum_{k\geq 0} c_k \bar{z^k} }
.\] 

:::


# Cauchy-Riemann and PDEs

## Spring 2020 HW 1.10 #work

a. Show that in polar coordinates, the Cauchy-Riemann equations take the form
\[
\frac{\partial u}{\partial r}=\frac{1}{r} \frac{\partial v}{\partial \theta} \text { and } \frac{\partial v}{\partial r}=-\frac{1}{r} \frac{\partial u}{\partial \theta}
.\]

b. Use (a) to show that the logarithm function, defined as 
\[
\log z=\log r+i \theta \text { where } z=r e^{i \theta} \text { with }-\pi<\theta<\pi
.\]
is holomorphic on the region $r> 0, -\pi < \theta < \pi$.

Also show that this function is not continuous in $r>0$.

### Tie's Extra Questions: Fall 2011 #work

(1) 
Show that the function $u=u(x,y)$ given by
$$u(x,y)=\frac{e^{ny}-e^{-ny}}{2n^2}\sin nx\quad \text{for}\ n\in {\mathbf N}$$
is the solution on $D=\{(x,y)\ | x^2+y^2<1\}$ of the Cauchy problem for the Laplace equation
$$\frac{\partial ^2u}{\partial x^2}+\frac{\partial ^2u}{\partial y^2}=0,\quad
u(x,0)=0,\quad \frac{\partial u}{\partial y}(x,0)=\frac{\sin nx}{n}.$$

(2) 
Show that there exist points $(x,y)\in D$ such that
$\displaystyle{\limsup_{n\to\infty} |u(x,y)|=\infty}$.


## Fall 2021.1 #completed

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


