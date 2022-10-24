---
order: 2
---

# Continuity

## 1 #complex/qual/work
Is the following function continuous, differentiable, continuously differentiable?
\[  
f: \RR^2 &\to \RR  \\
f(x, y) &= 
\begin{cases}
{xy \over \sqrt{x^2 + y^2}} & (x, y) \neq (0, 0) \\
0 & \text{else}.
\end{cases}
\]

## ? #complex/qual/work

Show that $f(z) = z^2$ is uniformly continuous in any open disk $|z| < R$, where $R>0$ is fixed, but it is not uniformly continuous on $\mathbb C$.

## 6 #complex/qual/work
Let $F:\RR^2\to \RR$ be continuously differentiable with $F(0, 0) = 0$ and $\norm{\nabla F(0, 0)} < 1$.

Prove that there is some real number $r> 0$ such that $\abs{F(x, y)} < r$ whenever $\norm{(x, y)} < r$.

## 2 Multivariable derivatives #complex/qual/work

a.  
Complete this definition: "$f: \RR^n\to \RR^m$ is real-differentiable a point $p\in \RR^n$ iff there exists a linear transformation..."

b. #complex/qual/work
Give an example of a function $f:\RR^2\to \RR$ whose first-order partial derivatives exist everywhere but $f$ is not differentiable at $(0, 0)$.

c. #complex/qual/work
Give an example of a function $f: \RR^2 \to \RR$ which is real-differentiable everywhere but nowhere complex-differentiable.

# Implicit/Inverse Function Theorems

## 3 #complex/qual/work
Let $f:\RR^2\to \RR$.

a. #complex/qual/work
Define in terms of linear transformations what it means for $f$ to be differentiable at a point $(a, b) \in \RR^2$.

b. #complex/qual/work
State a version of the inverse function theorem in this setting.

c. #complex/qual/work
Identify $\RR^2$ with $\CC$ and give a necessary and sufficient condition for a real-differentiable function at $(a, b)$ to be complex differentiable at the point $a+ib$.

## 5 #complex/qual/work
Let $P = (1, 3) \in \RR^2$ and define
\[  
f(s, t) \definedas ps^3 -6st + t^2
.\]

a. 
State the conclusion of the implicit function theorem concerning $f(s, t) = 0$ when $f$ is considered a function $\RR^2\to\RR$.

b. 
State the above conclusion when $f$ is considered a function $\CC^2\to \CC$.

c. 
Use the implicit function theorem for a function $\RR\cross \RR^2 \to \RR^2$ to prove (b).

> There are various approaches: using the definition of the complex derivative, the Cauchy-Riemann equations, considering total derivatives, etc.



## 7 #complex/qual/work
State the most general version of the implicit function theorem for real functions and outline how it can be proved using the inverse function theorem.


	
# Complex Differentiability

## 4 #complex/qual/work
Let $f = u+iv$ be complex-differentiable with continuous partial derivatives at a point $z = re^{i\theta}$ with $r\neq 0$.
Show that
\[  
\dd{u}{r} = {1\over r}\dd{v}{\theta} \qquad \dd{v}{r} = -{1\over r}\dd{u}{\theta}
.\]

## Tie's Extra Questions: Fall 2016

Let $u(x,y)$ be harmonic and have continuous partial derivatives of order three in an open disc of radius $R>0$.

a.
Let two points $(a,b), (x,y)$ in this disk be given. Show that the following integral is independent of the path in this disk joining these points:
$$
v(x,y) = \int_{a,b}^{x,y} ( -\frac{\partial u}{\partial y}dx +  \frac{\partial u}{\partial x}dy)
.$$

b. 
In parts:

- Prove that $u(x,y)+i v(x,y)$ is an analytic function in this disc.
- Prove that $v(x,y)$ is harmonic in this disc.
	
## Tie's Questions, Spring 2014: Polar Cauchy-Riemann #complex/qual/work 

Let $f=u+iv$ be differentiable (i.e. $f'(z)$ exists) with continuous partial derivatives at a point $z=re^{i\theta}$, $r\not= 0$. 
Show that
$$
\frac{\partial u}{\partial r}=\frac{1}{r}\frac{\partial v}{\partial \theta},\quad
\frac{\partial v}{\partial r}=-\frac{1}{r}\frac{\partial u}{\partial \theta}
.$$

## ? #complex/qual/work

1.
Show that the function $u=u(x,y)$ given by
$$
u(x,y)=\frac{e^{ny}-e^{-ny}}{2n^2}\sin nx\quad \text{for}\ n\in {\mathbf N}
$$
is the solution on $D=\{(x,y)\ | x^2+y^2<1\}$ of the Cauchy problem for the Laplace equation
$$\frac{\partial ^2u}{\partial x^2}+\frac{\partial ^2u}{\partial y^2}=0,\quad
u(x,0)=0,\quad \frac{\partial u}{\partial y}(x,0)=\frac{\sin nx}{n}.$$

2.
Show that there exist points $(x,y)\in D$ such that $\displaystyle{\limsup_{n\to\infty} |u(x,y)|=\infty}$.
