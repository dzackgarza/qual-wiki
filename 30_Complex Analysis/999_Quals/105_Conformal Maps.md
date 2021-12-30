
---
order: 105
---

# Conformal Maps 

## Spring 2019.6 #complex/qual/work

^5c3979

Find a conformal map from 
\[
\ts{ z\st  \abs{z -1 / 2} >1 / 2, \Re(z)>0 }
\]
to $\mathbb{H}$.

## Fall 2019.5 #complex/qual/work

^043381

:::{.problem title="?"}
Find a conformal map from $D=\{z:|z|<1,|z-1 / 2|>1 / 2\}$ to the unit disk $\Delta=\{z:|z|<1\} .$.
:::


## Spring 2020.5 #complex/qual/work

^0df993

:::{.problem title="?"}
Find a conformal map that maps the region 
\[
\ts{z \st \Re(z) > 0,\, \abs{z - {1\over 2} }> {1\over 2} }
\]
to the upper half plane.
:::


## Spring 2021.7 #complex/qual/work

^644ace

:::{.problem title="?"}
Let $R$ be the intersection of the right half-plane and the outside of the circle $\abs{z - {1\over 2}} = {1\over 2}$ with the line segment $[1, 2]$ removed, i.e. 
\[
R = \ts{z\in \CC\st \Re(z) > 0,\,\, \abs{z-{1\over 2}} > {1\over 2} } \sm \ts{z \da x+iy \st 1\leq x\leq 2,\,\, y=0}
.\]
Find a conformal map from $R$ to $\HH$ the upper half-plane.
:::

:::{.concept}
\envlist

- Blow up the point of tangency: inverting through a circle sends inner circles to lines, fixes the real line, and preserves regions between curves. 
E.g. the image of $\abs{z-i/2} =2$ is $\ts{ \Im(z) = 2}$

![[attachments/Circle Inversion.gif]]

- So $z\to 1/z$ maps the region into a half-strip.

:::

## Fall 2020.5 #complex/qual/work

^931c0a

Consider the function $f(z)=\frac{1}{2}\left(z+\frac{1}{z}\right)$ for $z \in \mathbb{C} \backslash\{0\}$. Let $\mathbb{D}$ denote the open unit disc.

- Show that $f$ is one-to-one on the punctured disc $\mathbb{D} \backslash\{0\}$. What is the image of the circle $|z|=r$ under this map when $0<r<1$ ?

- Show that $f$ is one-to-one on the domain $\mathbb{C} \backslash \mathbb{D}$. What is the image of this domain under this map?

- Show that there exists a map $g: \mathbb{C} \backslash[-1,1] \rightarrow \mathbb{D} \backslash\{0\}$ such that $(g \circ f)(z)=z$ for all $z \in \mathbb{D} \backslash\{0\}$. Describe the map $g$ by an explicit formula.

## Fall 2021.7 #complex/qual/work

^efdbde

:::{.problem title="?"}
Find a conformal map from the intersection of $|z-1|<2$ and $|z+1|<2$ to the upper half plane.
:::

## Lune #complex/exercise/completed

:::{.problem title="?"}
Let $\lambda = {1\over 2}\qty{1 + i \sqrt{3}}$ and find a map 
\[
R \da \ts{\abs{z - \lambda} < 1} \intersect \ts{\abs{z-\bar{\lambda}} < 1 } \too \DD
.\]
:::

:::{.solution}
The region looks like the following:

![](figures/2021-12-29_19-19-01.png)

Following the general strategy for lunar regions, send the intersection points to $0$ and $\infty$ to get triangular sector.
So choose to send $0\to 0$ and $1\to \infty$ by taking
\[
f(z) \da {z\over z-1}
.\]

> Note: mistake here, really we need to compose with $z\mapsto -z$ to get the picture, so take $f(z) \da {z\over 1-z}$ instead!!

:::{.claim}
\[
f(R) = \ts{z\st -\theta_0 < \Arg(z) < \theta_0 },\qquad \theta_0 \da {\pi \over 6}
.\]

![](figures/2021-12-29_19-35-44.png)

:::

From here it is easy to map to the disc:

- $z\mapsto {z\over z-1}$ sends $R$ to $\abs{\Arg(z)} < \theta_0$
- $z\mapsto z^{\pi \over 2\theta_0}$ maps $\abs{\Arg(z)}<\theta_0 \to \abs{\Arg(z)} < {\pi \over 2}$, the right half-plane.
- $z\mapsto iz$ rotates the right half-plane into $\HH$.
- $z\mapsto {z-i\over z+i}$ maps $\HH\to \DD$.


:::{.proof title="of claim"}
Since both $C_1, C_2$ pass through $0, 1$, their images become circles passing through $f(0)=0, f(1) = \infty$, so lines through the origin.
Since $f$ fixes $\RR$ and the original region is symmetric about $\RR$, the resulting region will also be symmetric about $\RR$.
As shown in the picture, since the interior of the region is to the left of each circle, the image will be to the left of each line.
So it suffices to find the orientation of the two lines, as well as the angle that one of them makes with the $x\dash$axis.

Consider $f(C_1)$ -- it suffices to find $\Arg(f(z_0))$ for any $z_0\in C_1$, so look for a point (other than $0, 1$) where $\Arg(f(z_0))$ is easy to compute.
Noting that $C_1$ intersects $i\RR$, we can find this point:
\[
C_1: \qty{ x-{1\over 2}}^2 + \qty{y - {\sqrt 3 \over 2}}^2 &= 1 \\
x=0 \implies y = \pm{1\over 2} \sqrt{3} + {1\over 2} \sqrt{3} = 0, \sqrt{3}
,\]
so choose $z_0 = i\sqrt{3}$:
\[
f(z_0) 
= {i\sqrt 3 \over i\sqrt 3 - 1} = {1\over 4}\qty{3-i\sqrt 3}
\implies \Arg(f(z_0)) = {-\pi \over 6}
.\]
So $C_1$ does get mapped to the line in the image running from $Q_2\to Q_4$.

To get the orientation of $C_1$, use that $i\sqrt{3}, 0, 1$ map to $f(z_0), 0, \infty$, which gives a $Q_4\to Q_2$ orientation -- oops.

> Mistake here: should have chosen $z\mapsto {z\over 1-z}$ to make the picture accurate!

Similarly for $C_2$, setting $z_1 \da -i\sqrt 3$ yields $f(z_1) = {1\over 4}\qty{3+i\sqrt{3}}$, so $\Arg(f(z_1)) = {\pi \over 6}$.
The orientation is found from $1,0,z_0 \mapsto \infty, 0, f(z_0)$, which is $Q_3\to Q_1$.

> Again, mistake in the picture!

Intersecting the regions that are to the left of each image curve yields $5\pi/6 < \Arg(z) < 7\pi/6$, and composing with $z\mapsto -z$ yields $-\pi/6 < \Arg(z) < \pi/6$.
:::

:::

## 1 #complex/exercise/work
Find a conformal map from $\DD$ to $\HH$.

## 2 #complex/exercise/work
Find a conformal map from the strip $\theset{z\in \CC \suchthat 0 < \Im(z) < 1}$ to $\HH$.

## 3 #complex/exercise/work
Find a fractional linear transformation $T$ which maps $\HH$ to $\DD$, and explicitly describe the image of the first quadrant under $T$.

## 4 #complex/exercise/work
Find a conformal map from $\theset{z\in \CC\suchthat \abs{z-i} > 1,\, \Re(z) > 0}$ to $\HH$.

## 5 #complex/exercise/work
Find a conformal map from $\theset{z\in \CC \suchthat \abs{z} < 1,\, \abs{z - {1\over 2}} > {1\over 2} }$ to $\DD$.

## 6 #complex/exercise/work
Find a conformal  map from $\theset{\abs{z-1} < 2} \intersect \theset{\abs{z+1} < 2}$ to $\HH$.

## 7 #complex/exercise/work
Let $\Omega$ be the region inside the unit circle $\abs{z} = 1$ and outside the circle $\abs{z-{1\over 4}} = {1\over 4}$.

Find an injective conformal map from $\Omega$ onto some annulus $\theset{r < \abs{z} < 1}$ for constant $r$.

## 8 #complex/exercise/work
Let $D$ be the region obtained by deleting the real interval $[0, 1)$ from $\DD$; find a conformal map from $D$ to $\DD$.

## 9 #complex/exercise/work
Find a conformal map from $\CC\setminus\theset{x\in \RR\suchthat x\leq 0}$ to $\DD$.

## 10 #complex/exercise/work
Find a conformal map from $\CC\setminus\theset{x\in \RR\suchthat x\geq 1}$ to $\DD$.

## 11 #complex/exercise/work
Find a bijective conformal map from $G$ to $\HH$, where
\[  
G \definedas \theset{z\in \CC \suchthat \abs{z-1} < \sqrt 2,\, \abs{z+1} < \sqrt 2} \setminus [0, i)
.\]

## 12 #complex/exercise/work
Prove that TFAE for a Möbius transformation $T$ given by $T(z) = {az + b \over cz + d}$:

a. $T$ maps $\RR\union \theset{\infty}$ to itself.
b. It is possible to choose $a,b,c,d$ to be real numbers.
c. $\bar{T(z)} = T(\bar z)$ for every $z\in \CP^1$.
d. There exist $\alpha\in \RR, \beta \in \CC\setminus \RR$ such that $T(\alpha) = \alpha$ and $T(\bar \beta) = \bar{T(\beta)}$.

## 13 #complex/exercise/work
Find a conformal map from $D = \{z :\  |z| < 1,\ |z - 1/2| > 1/2\}$ to the unit disk $\Delta=\{z: \ |z|<1\}$.

## Tie's Extra Questions: Fall 2009 #complex/exercise/work

Find a conformal map from $D = \{z :\  |z| < 1,\ |z - 1/2| > 1/2\}$
to the unit disk $\Delta=\{z: \ |z|<1\}$.

## Tie's Extra Questions: Fall 2011 #complex/exercise/work


Find a conformal map from $D = \{z :\  |z| < 1,\ |z - 1/2| > 1/2\}$
to the unit disk $\Delta=\{z: \ |z|<1\}$.

## Tie's Extra Questions: Spring 2014 #complex/exercise/work


Find a conformal map from $D = \{z :\  |z| < 1,\ |z - 1/2| > 1/2\}$
to the unit disk $\Delta=\{z: \ |z|<1\}$.

## Tie's Extra Questions: Spring 2015 #complex/exercise/work

Find a conformal map

1.  from $\{ z: |z - 1/2| > 1/2, \text{Re}(z)>0 \}$ to $\mathbb H$

2.  from $\{ z: |z - 1/2| > 1/2, |z| <1  \}$ to $\mathbb D$

3.  from the intersection of the disk $|z + i| < \sqrt{2}$ with
    ${\mathbb H}$ to ${\mathbb D}$.

4.  from ${\mathbb D}  \backslash [a, 1)$ to
    ${\mathbb D} \backslash [0, 1)$ ($0<a<1)$. 

    > Short solution possible using Blaschke factor.

5.  from $\{ z: |z| < 1, \text{Re}(z) > 0 \} \backslash (0, 1/2]$ to
    $\mathbb H$.
		
		
		## Tie's Extra Questions: Spring 2015

Prove that
$\displaystyle{f(z)=-\frac{1}{2}\left(z+\frac{1}{z}\right)}$ is a
conformal map from half disc $\{z=x+iy:\ |z|<1,\ y>0\}$ to upper
half plane ${\mathbb H}=\{z=x+iy:\ y>0\}$.

## Tie's Extra Questions: Spring 2015 #complex/exercise/work


Let $\displaystyle{\psi_{\alpha}(z)=\frac{\alpha-z}{1-\bar{\alpha}z}}$
with $|\alpha|<1$ and ${\mathbb D}=\{z:\ |z|<1\}$. 
Prove that

- $\displaystyle{\frac{1}{\pi}\iint_{{\mathbb D}} |\psi'_{\alpha}|^2 dx dy =1}$.
- $\displaystyle{\frac{1}{\pi}\iint_{{\mathbb D}} |\psi'_{\alpha}| dx dy =\frac{1-|\alpha|^2}{|\alpha|^2} \log \frac{1}{1-|\alpha|^2}}$.

Prove that $\displaystyle{f(z)=-\frac{1}{2}\left(z+\frac{1}{z}\right)}$
is a conformal map from half disc $\{z=x+iy:\ |z|<1,\ y>0\}$ to upper
half plane $\mathbb H=\{z=x+iy:\ y>0\}$.

## Tie's Extra Questions: Fall 2016 #complex/exercise/work

Find the conformal map that takes the upper half-plane conformally onto the half-strip $\{w=x+iy:\ -\pi/2<x<\pi/2\ y>0\}$.


# Linear Fractional Transformations

## Tie's Extra Questions: Spring 2015 #complex/exercise/work

Let $C$ and $C'$ be two circles and let $z_1 \in C$, $z_2 \notin C$, $z'_1 \in C'$, $z'_2 \notin C'$. Show that there is a unique fractional linear transformation $f$ with $f(C) = C'$ and
$f(z_1) = z'_1$, $f(z_2) = z'_2$.

## Tie's Extra Questions: Spring 2015 #complex/exercise/work


Let $f(z)$ be an analytic function on
${\mathbb C} \backslash \{ z_0 \}$, where $z_0$ is a fixed point.
Assume that $f(z)$ is bijective from
${\mathbb C} \backslash \{ z_0 \}$ onto its image, and that $f(z)$
is bounded outside $D_r(z_0)$, where $r$ is some fixed positive
number. Show that there exist $a, b, c, d \in \mathbb C$ with
$ad-bc \neq 0$, $c \neq 0$ such that
$\displaystyle f(z) = \frac{az + b}{cz + d}$.




