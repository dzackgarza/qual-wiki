# The Fundamental Group

## 1 (Spring '15) #topology/qual/completed

:::{.problem title="?"}
Let $S^1$ denote the unit circle in $C$, $X$ be any topological space, $x_0 \in X$, and $$\gamma_0, \gamma_1 : S^1 \to X$$ be two continuous maps such that $\gamma_0 (1) = \gamma_1 (1) = x_0$.

Prove that $\gamma_0$ is homotopic to $\gamma_1$ if and only if the elements represented by $\gamma_0$ and $\gamma_1$ in $\pi_1 (X, x_0 )$ are conjugate.
:::

:::{.concept}
\envlist

- Any two maps $f_i: Y\to X$ are **homotopic** iff there exists a homotopy $H: I\cross Y \to X$ with $H_0 = f_0$ and $H_1 = f_1$.
- $\pi_1(X; x_0)$ is the set of maps $f:S^1\to X$ such that $f(0) = f(1) = x_0$, modulo being homotopic maps.
- Loops can be homotopic (i.e. *freely* homotopic) without being homotopic rel a base point, so not equal in $\pi_1(X; x_0)$.
  - Counterexample where homotopic loops are not equal in $\pi_1$, but just conjugate.
    Need nonabelian $\pi_1$ for conjugates to possibly not be equal, so take a torus:

  ![figures/2020-02-04-20:00.png](figures/2020-02-04-20:00.png)

:::

:::{.solution}
\hfill
$\implies$:

- Suppose $\gamma_1 \homotopic \gamma_2$, then there exists a free homotopy $H: I\cross S^1 \to X$ with $H_0 = \gamma_0, H_1 = \gamma_1$.
- Since $H(0, 1) \gamma_0(1) = x_0$ and $H(1, 1) = \gamma_1(1) =  x_0$, the map
\[
T: [0, 1] &\to X \\
t &\mapsto H(t, 1)
\]
  descends to a loop $T:S^1\to X$.
- Claim: $\gamma_1$ and $T\ast \gamma_2 \ast T\inv$ are homotopic rel $x_0$, making $\gamma_1, \gamma_2$ conjugate in $\pi_1$.
  - Idea: for each fixed $s$, follow $T$ for the first third, $\gamma_2$ for the middle third, $T\inv$ for the last third.

  ![figures/2020-02-04-20:23.png](figures/2020-02-04-20:23.png)


$\impliedby$:

- Suppose $[\gamma_1] = [h] [\gamma_2] [h]\inv$ in $\pi_1(X; x_0)$.
  The claim is that $\gamma_1 \homotopic h\gamma_2 h\inv$ are freely homotopic.
- Since these are equal in $\pi_1$, we get a square interpolating $\gamma_1$ and $h\gamma_2 h\inv$ with constant sides $\id_{x_0}$.
- For free homotopies, the sides don't have to be constant, to merge $h$ and $h\inv$ into the sides to get a free homotopy from $f$ to $g$:

![image_2021-06-04-00-44-45.png](image_2021-06-04-00-44-45.png)

:::

## 2 (Spring '09/Spring '07/Fall '07/Fall '06) #topology/qual/work

a. 
State van Kampen's theorem.

b. 
Calculate the fundamental group of the space obtained by taking two copies of the torus $T = S^1 \times S^1$ and gluing them along a circle $S^1 \times {p}$ where $p$ is a point in $S^1$.

c. 
Calculate the fundamental group of the Klein bottle.

d. 
Calculate the fundamental group of the one-point union of $S^1 \times S^1$ and $S^1$.

e.
Calculate the fundamental group of the one-point union of $S^1 \times S^1$ and $\RP^2$.

> **Note: multiple appearances!!**

## 3 (Fall '18) #topology/qual/work
Prove the following portion of van Kampen's theorem. 
If $X = A\cup B$ and $A$, $B$, and $A \cap B$ are nonempty and path connected with $\pt \in A \cap B$, then there is a surjection 
$$
\pi_1 (A, \pt) \ast \pi_1 (B, \pt) \to \pi_1 (X, \pt)
.$$

## 4 (Spring '15) #topology/qual/work
Let $X$ denote the quotient space formed from the sphere $S^2$ by identifying two distinct points. 

Compute the fundamental group and the homology groups of $X$.

## 5 (Spring '06) #topology/qual/work
Start with the unit disk $\DD^2$ and identify points on the boundary if their angles, thought of in polar coordinates, differ a multiple of $\pi/2$. 

Let $X$ be the resulting space. Use van Kampen's theorem to compute $\pi_1 (X, \ast)$.

## 6 (Spring '08) #topology/qual/work
Let $L$ be the union of the $z$-axis and the unit circle in the $xy\dash$plane. 
Compute $\pi_1 (\RR^3 \backslash L, \ast)$.

## 7 (Fall '16) #topology/qual/work
Let $A$ be the union of the unit sphere in $\RR^3$ and the interval $\theset {(t, 0, 0) : -1 \leq t \leq 1} \subset \RR^3$. 

Compute $\pi_1 (A)$ and give an explicit description of the universal cover of $X$.

## 8 (Spring '13) #topology/qual/work
a. Let $S_1$ and $S_2$ be disjoint surfaces. 
    Give the definition of their connected sum $S^1 \#S^2$.

b. Compute the fundamental group of the connected sum of the projective plane and the two-torus.

## 9 (Fall '15) #topology/qual/work
Compute the fundamental group, using any technique you like, of $\RP^2 \#\RP^2 \#\RP^2$.

## 10 (Fall '11) #topology/qual/work
Let 
$$
V = \DD^2 \times S^1 = \theset{ (z, e^{it}) \suchthat \norm z \leq 1,~~ 0 \leq t < 2\pi}
$$ 
be the "solid torus" with boundary given by the torus $T = S^1 \times S^1$ . 

For $n \in \ZZ$ define 
\begin{align*}
\phi_n : T &\to T \\
(e^{is} , e^{it} ) &\mapsto (e^{is} , e^{i(ns+t)})
.\end{align*}

Find the fundamental group of the identification space
$$
V_n = {V\disjoint V \over \sim n}
$$
where the equivalence relation $\sim_n$ identifies a point $x$ on the boundary $T$ of the first copy of $V$ with the point $\phi_n (x)$ on the boundary of the second copy of $V$.

## 11 (Fall '16) #topology/qual/work
Let $S_k$ be the space obtained by removing $k$ disjoint open disks from the sphere $S^2$. 
Form $X_k$ by gluing $k$ Möbius bands onto $S_k$ , one for each circle boundary component of $S_k$ (by identifying the boundary circle of a Möbius band homeomorphically with a given boundary component circle). 

Use van Kampen's theorem to calculate $\pi_1 (X_k)$ for each $k > 0$ and identify $X_k$ in terms of the classification of surfaces.


## 12 (Spring '13) #topology/qual/work

a.
Let $A$ be a subspace of a topological space $X$. 
Define what it means for $A$ to be a **deformation retract** of $X$.

b. 
Consider $X_1$ the "planar figure eight" and $$X_2 = S^1 \cup ({0} \times [-1, 1])$$ (the "theta space"). 
Show that $X_1$ and $X_2$ have isomorphic fundamental groups.

c.
Prove that the fundamental group of $X_2$ is a free group on two generators.

## Spring 2021 #4

:::{.problem title="Spring 2021, 4"}
Suppose that $X$ is a topological space and $x_0\in X$, and suppose that every continuous map $\gamma: S^1 \to X$ is freely homotopic to the constant map to $x_0$.
Prove that $\pi_1(X, x_0) = \ts{ e }$.

> Note that "freely" means there are no conditions on basepoints.

:::



