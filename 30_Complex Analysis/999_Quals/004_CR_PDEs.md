---
order: 4
---

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


## Fall 2021.1 #complete

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


