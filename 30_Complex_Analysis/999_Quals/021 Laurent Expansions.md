---
order: 21
---

# Laurent Expansions

## Tie, Spring 2015: #complex/qual/work 

Let $\displaystyle f(z) = \frac{1}{z} + \frac{1}{z^2 -1}$. 
Find all the Laurent series of $f$ and describe the largest annuli in which these series are valid.

## 1 #complex/qual/completed
Find the Laurent expansion of
\[
f(z) = {z + 1 \over z(z-1)}
\]
about $z=0$ and $z=1$ respectively.

:::{.solution}
\envlist

Let $f(z) = {z+1\over z(z-1)}$.

About $z=0$:

\[
f(z) 
&= (z+1) \qty{- {1 \over z} + {1\over z-1} } \\
&=  -(z+1) \qty{{1\over z} + \sum_{n=0}^\infty z^n } \\
&= -(z+1)\sum_{n=-1}^\infty z^n \\
&= {1\over z} + 2\sum_{n=0}^\infty z^n \\
&= -{1\over z} -2 - 2z - 2z^2 - \cdots
.\]

About $z=1$:

\[
f(z) 
&= \qty{(1-z) -2 \over 1-z} \qty{1 \over 1 - (1-z)} \\
&= \qty{1 - {2\over 1-z}} \sum_{n=0}^\infty (1-z)^n \\ 
&= \sum_{n=0}^\infty (1-z)^n - 2 \sum_{n=-1}^\infty (1-z)^n \\
&= -{2\over 1-z} - \sum_{n=0}^\infty (1-z)^n \\
&= {2\over z-1} + \sum_{n=0}^\infty (-1)^{n+1} (z-1)^n \\
&= {2\over z-1} - 1 + (z-1) - (z-1)^2 + \cdots
.\]

:::



## 2 #complex/qual/completed

Find the Laurent expansions about $z=0$ of the following functions:
\[
e^{1\over z} \hspace{8em} \cos \qty{1\over z}
.\]

:::{.solution}
\envlist

Let $f(z) = {z+1\over z(z-1)}$.

About $z=0$:

\[
f(z) 
&= (z+1) \qty{- {1 \over z} + {1\over z-1} } \\
&=  -(z+1) \qty{{1\over z} + \sum_{n=0}^\infty z^n } \\
&= -(z+1)\sum_{n=-1}^\infty z^n \\
&= {1\over z} + 2\sum_{n=0}^\infty z^n \\
&= -{1\over z} -2 - 2z - 2z^2 - \cdots
.\end{align*}

About $z=1$:

\[
f(z) 
&= \qty{(1-z) -2 \over 1-z} \qty{1 \over 1 - (1-z)} \\
&= \qty{1 - {2\over 1-z}} \sum_{n=0}^\infty (1-z)^n \\ 
&= \sum_{n=0}^\infty (1-z)^n - 2 \sum_{n=-1}^\infty (1-z)^n \\
&= -{2\over 1-z} - \sum_{n=0}^\infty (1-z)^n \\
&= {2\over z-1} + \sum_{n=0}^\infty (-1)^{n+1} (z-1)^n \\
&= {2\over z-1} - 1 + (z-1) - (z-1)^2 + \cdots
.\end{align*}


:::


## 3 #complex/qual/work

Find the Laurent expansion of 
\[
f(z) = {z+1 \over z(z-1)^2}
\]
about $z=0$ and $z=1$ respectively.

> Hint: recall that power series can be differentiated.

## 4 #complex/qual/work

For the following functions, find the Laurent series about $0$ and classify their singularities there:
\[
{\sin^2(z) \over z} \\
z \exp{1\over z^2} \\
{1 \over z(4-z)}
.\]

## Tie's Extra Questions: Fall 2015 #complex/qual/work

Expand the following functions into Laurent series in the indicated
regions:

(a)
$\displaystyle f(z) = \frac{z^2 - 1}{ (z+2)(z+3)}, \; \; 2 < |z| < 3$,
$3 < |z| < + \infty$.

(b)
$\displaystyle f(z) = \sin \frac{z}{1-z}, \; \; 0 < |z-1| < + \infty$

## Tie, Fall 2015: Laurent Coefficients #complex/qual/work 

Suppose that $f$ is holomorphic in an open set containing the closed unit disc, except for a pole at $z_0$ on the unit circle. Let $\displaystyle f(z) = \sum_{n = 1}^\infty c_n z^n$ denote the the power series in the open disc. Show that 

(1) 
$c_n \neq 0$ for all large enough $n$'s, and 

(2)
$\displaystyle \lim_{n \rightarrow \infty} \frac{c_n}{c_{n+1}}= z_0$.

## Spring 2020 HW 2, SS 2.6.14 #complex/qual/work

Suppose that $f$ is holomorphic in an open set containing $\DD$ except for a pole $z_0 \in \bd \DD$.
Let $\sum_{n=0}^\infty a_n z^n$ be the power series expansion of $f$ in $\DD$, and show that $\lim \frac{a_n}{a_{n+1}} = z_0$.

> [Solution](https://math.stackexchange.com/questions/1358964/show-that-lim-limits-n-fraca-na-n1-z-0?rq=1)

## 2 #complex/qual/work

Suppose $f$ is entire and has Taylor series $\sum a_n z^n$ about 0.

a.  #complex/qual/work
Express $a_n$ as a contour integral along the circle $\abs{z} = R$.

b. #complex/qual/work
Apply (a) to show that the above Taylor series converges uniformly on every bounded subset of $\CC$.

c. #complex/qual/work
Determine those functions $f$ for which the above Taylor series converges uniformly on all of $\CC$.

## Spring 2020 HW 2.4 #complex/qual/work
Without using Cauchy's integral formula, show that if $\abs{a} < r < \abs{b}$, then
\[
\int_{\gamma} \frac{d z}{(z-\alpha)(z-\beta)}
=\frac{2 \pi i}{\alpha-\beta}
\]
where $\gamma$ denotes the circle centered at the origin of radius $r$ with positive orientation.

> Hint: take a Laurent expansion.

### Spring 2020 HW 3 #  1 #complex/qual/work

Prove that if $f$ has two Laurent series expansions,
\[
f(z) = \sum c_n(z-a)^n \quad\text{and}\quad f(z) = \sum c_n'(z-a)^n
\]
then $c_n = c_n'$.

### Spring 2020 HW 3 #  2 #complex/qual/work

Find Laurent series expansions of
\[
\frac{1}{1-z^2} + \frac{1}{3-z}
\]
How many such expansions are there? In what domains are each valid?
