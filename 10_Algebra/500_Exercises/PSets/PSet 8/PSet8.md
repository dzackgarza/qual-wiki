---
title: Problem Set 8
---

# Regular Problems

## Problem 1

### Part a

Define a map

$$
\phi_\mathrm{ev}: \hom_\ZZ(\ZZ_m, A) \to A \\
(f: \ZZ_m \to A) \mapsto f(1)
$$

Then $\phi_\mathrm{ev}$ is a $\ZZ\dash$module homomorphism, since

\[
\begin{align*}
\phi_\mathrm{ev}(nf + g) 
&= (nf + g)(1) \\
&= nf(1) + g(2) \\
&= n\phi_\mathrm{ev}(f) + \phi_\mathrm{ev}(g)
\end{align*}
\]

But this forces $f(\overline 0) = 0_A$ (where $\overline 0: \ZZ_m \to A$ is the zero map), we have
$$
0 = f(0) = f(m) = m f(1),
$$

we must have $mf(1) = 0$ in $A$. So 
$$
\im \phi_\mathrm{ev} = \theset{a\in A \mid ma = 0} \definedas A[m].
$$

It is also the case that
\[
\begin{align*}
\ker \phi_{\mathrm{ev}} &= \theset{f \in \hom_\ZZ(\ZZ_m, A) \mid f(1) = 0} = \theset{\overline 0},
\end{align*}
\]

which follows from the fact that $\ZZ_m = \generators{1 \mod m}$ and $A = \generators{1_A}$ as $\ZZ\dash$modules, so if $f(1 \mod m) = 0_A$ then 
$$
f(n \mod m) = nf( 1 \mod m) = 0
$$ 

and so $f$ is necessarily the zero map. So $\ker \phi = \overline 0$. 

We can then apply the first isomorphism theorem,
$$
\frac{\hom_\ZZ(\ZZ_m, A)}{\ker \phi_{\mathrm{ev}}} \cong \im \phi_{\mathrm{ev}} \implies \hom_\ZZ(\ZZ_m, A) \cong A[m].
$$

### Part 2

**Lemma:**
If $x \divides n$ and $x\divides m$ then $x\divides \gcd(m, n)$

*Proof:*
We have $x\divides km + \ell n$ for any integers $k, \ell$. So let $d = \gcd(m, n)$, then there exist integers $a, b$ such that $am + bn = d$. But we can now just take $k=a$ and $\ell = b$. $\qed$

We claim that $\ZZ_n[m] \cong \ZZ_{(m, n)}$, from which the result immediately follows by part 1.

Define a map
\[
\begin{align*}
\phi: \ZZ &\to \ZZ_n[m] \\ 
1 &\mapsto [1]_{\mod n}
,\end{align*}
\]

which we claim is an isomorphism.
$\phi$ is clearly surjective since $\ZZ\to \ZZ_n$ is a quotient map and $\ZZ_n[m]$ is a subgroup of $\ZZ_n$, and if we let $d \definedas \gcd(m, n)$, we have

\[
\begin{align*}
\ker \phi &= \theset{x\in \ZZ_n \suchthat  mx = 0} \\
&= \theset{x \in \ZZ_n \suchthat x \divides m} \\
&= \theset{x \in \ZZ \suchthat x \divides n ~\text{ and }~ x \divides m} \\
&= \theset{x \in \ZZ \suchthat x \divides d} \quad \text{by the lemma} \\
&= d\ZZ~
.\end{align*}
\]


Then by the first isomorphism theorem, we have
$$
\frac{\ZZ}{\ker \phi} \cong \im \phi \implies \frac{\ZZ}{d\ZZ} \cong \ZZ_n[m].
$$

### Part 3

> Note: let $[x]_m$ denote the equivalence class of $x \mod m$.

Let $f\in \ZZ^* = \hom_\ZZ(\ZZ_m, \ZZ)$, so $f: \ZZ_m \to \ZZ$. 
These are both $\ZZ\dash$modules generated by their identity elements, so such a map is determined by where it send $[1]_m$.

So let $f([1]_m) = n \in \ZZ$.
Since $f$ is a module homomorphism, we have $f([0]_m) = 0$, and in particular we have
\[
\begin{align*}
0 &= f([0]_m) \\
&= f([m]_m) \\
&= f([1 m]_m) \\
&= m f([1]_m),
\end{align*}
\]

which forces $f([1]) \in \ZZ[m] = \theset{0}$, so $f$ must be the zero map and $\ZZ^* = 0$.

> Note: $\ZZ[m] = 0$ because $\ZZ$ is an integral domain, so $mx = 0$ forces $m=0$ or $x=0$.

### Part 4

To see that $\ZZ_m$ is a $\ZZ_{mk}$ module, we define an action

\[
\begin{align*}
\ZZ_{mk} &\actson \ZZ_{m} \\
[x]_{mk} \actson [y]_m &\definedas [xy]_m
\end{align*}
\]

**This is a well-defined action**:

If $[x_1]_{mk} = [x_2]_{mk}$ are two representatives of the same equivalence class, then 
$$
[x_1]_{mk} - [x_2]_{mk} = [x_1-x_2]_{mk} = [0]_{mk} \implies m \divides x_1 - x_2.
$$ 

But then
\[
\begin{align*}
([x_1]_{mk}\actson [y]_m) - ([x_2]_{mk} \actson [y]_m) 
&= [x_1 y]_m - [x_2 y]_m \\
&= [(x_1 - x_2)y]_m \\
&= [0]_m,
\end{align*}
\]

which shows that their resulting actions on $\ZZ_m$ are equal.



**This action yields a module structure:**

- $r.(x+y) = r.x + r.y$:
$$
[r]_{mk} \actson ([x]_m + [y]_m)  = [r]_{mk} \actson [x+y]_m = [r(x+y)]_m = [rx]_m + [ry]_m.
$$

- $(r+s).x = r.x + s.x$: 
$$
[r]_{mk} + [s]_{mk} \actson [x]_m = [r + s]_{mk} \actson [x]_m = [(r+s)x]_m = [rx]_m + [sx]_m.
$$

- $(rs).x = r.s.x$:
\[
\begin{align*}
[r]_{mk} \cdot [s]_{mk} \actson [x]_m 
&= [rs]_{mk} \actson [x]_m \\
&= [(rs)x]_m  \\
&= [r]_{mk} \actson [sx]_m \\
&= [r]_{mk} \actson ( [s]_{mk} \actson [x]_m).
\end{align*}
\]

- $1.x = x$:
$$
[1]_{mk} \actson [x]_m = [1x]_m = [x]_m.
$$

$\ZZ_m^* \definedas \hom_{\ZZ_{mk}}(\ZZ_m, \ZZ_{mk}) \cong \ZZ_m$:

Define a map
\[
\begin{align*}
\phi: \hom_{\ZZ_{mk}}(\ZZ_m, \ZZ_{mk}) &\to \ZZ_m \\
f \mapsto [f([1]_m)]_m
\end{align*}
\]

**$\phi$ is a homomorphism**, as

\[
\begin{align*}
\phi(f + g) &= [(f+g)([1]_m)]_m \\
&= [f([1]_m) + g([1]_m)]_m  \\
&= [f([1]_m)]_m + [g([1]_m)]_m \\ \\
\phi([r]_{mk} \actson f) &= [[r]_{mk} f([1]_m)]_m \\
&= [r]_m \cdot [f([1]_m)]_m \\
&= [r]_{mk}\actson \phi(f).
\end{align*}
\]

**$\phi$ is injective**, as $[f([1]_m)]_m = [0]_m$, then for any $1 \leq \ell \leq m$, we have
\[
\begin{align*}
[f([\ell]_m)]_m &= [\ell f([1]_m)]_m \\
&= \ell [f([1]_m)]_m \\
&= \ell[0]_m \\
&= [0]_m
,\end{align*}
\]

so $f$ must be the zero map.

**$\phi$ is surjective**, since if $[\ell]_m \in \ZZ_m$, we can define
\[
\begin{align*}
f_\ell: \ZZ_m &\to \ZZ_{mk} \\
[1]_m &\mapsto [\ell]_{mk}
\end{align*}
\]

which makes sense and is well-defined because $\ZZ_m \injects \ZZ_{mk}$, and the map is defined on the generator.

So we have the desired bijection. $\qed$

## Problem 2

We have the map

\[
\begin{align*}
\pi: \ZZ &\to \ZZ_2 \\
x &\mapsto [x]_2
\end{align*}
\]

which is a surjection and thus an epimorphism in the category ${\ZZ}\dash\mathrm{Mod}$, and if we apply the functor $\hom_\ZZ(\ZZ_2, \wait)$ to $\pi$ we obtain an induced map

\[
\begin{align*}
\overline{\pi}: \hom_{\ZZ}(\ZZ_2, \ZZ) &\to \hom_{\ZZ}(\ZZ_2, \ZZ_2) \\
f &\mapsto \pi \circ f 
.\end{align*}
\]

The claim is that $\overline{\pi}$ is *not* a surjection, and thus not an epimorphism (in the same category).

To see that this is the case, we can simply note that $\hom_\ZZ(\ZZ_2, \ZZ) = 0$ by part 3 of Problem 1, whereas $\hom_\ZZ(\ZZ_2, \ZZ_2) \neq 0$. 

For example, one can define 
\[
\begin{align*}
\id_{\ZZ_2}: \ZZ_2 &\to \ZZ_2\\
[x]_2 &\mapsto [x]_2 
,\end{align*}
\]
which is a nontrivial module homomorphisms. 

So any such $f$ appearing must be the zero map, and thus $\overline{\pi}$ is also the zero map. $\qed$

## Problem 3

Let $f: R \to R$ be an endomorphism of $R$ in the category of rings. 
We can then check that for any $r\in R$, we have $f(r) = f(r 1_R) = rf(1_R)$, which says that $f$ is given by right-multiplication by some fixed element $x_f \definedas f(1_R)$, i.e.
\[
\begin{align*}
f: R &\to R \\
r &\mapsto r \cdot x_f
\end{align*}
\]

and so we can attempt to define 
\[
\begin{align*}
\phi_1: \hom_R(R, R) &\to R \\
f &\mapsto x_f \definedas f(1_R)
\end{align*}
\]

We can check that 
$$
(g\circ f(r)) = g(f(r)) = g(r\cdot x_f) = r \cdot x_f \cdot x_g,
$$

which shows that in fact 
$$
\phi(g \circ f) = x_f \cdot x_g,
$$
which reverses the multiplication. So the correct codomain is $R^{op}$, and we amend the definition:
\[
\begin{align*}
\phi_2: \hom_R(R, R) &\to R^{op} \\
f &\mapsto x_f \definedas f(1_R)
\end{align*}
\]

By construction, **$\phi_s$ is a ring homomorphism**. If $R$ is commutative, then $x_f \cdot x_g = x_g \cdot x_f$, which makes $\phi_1$ a ring homomorphism as well. It remains to check that it is an isomorphism/

**$\phi_1$ is in injective**: We can check that $\ker \phi_1 = 0$ as a ring. To that end, suppose $\phi_1(f) = x_f = 0$. Then $f(r) = r \cdot 0 = 0$, so $f$ can only be the zero map.

**$\phi_1$ is surjective**: Let $x\in R$ be arbitrary, then we can define $f: R \to R$ by $f(1_R) = x$, so $f(r) = r\cdot x$. This is an endomorphism of $R$, and thus an element of $\hom_R(R, R)$.

By the first isomorphism theorem for rings, we thus have $\hom_R(R, R) \cong R$.
$\qed$

## Problem 4

> Note: Let $X\dual \definedas \hom_R(X, R)$ denote the dual.

We have maps

\[
\begin{align*}
\theta_A: A &\to (A\dual)\dual \\
a &\mapsto (\mathrm{ev}_a: f \mapsto f(a) )
\end{align*}
\]

\[
\begin{align*}
\theta_B: B &\to (B\dual)\dual \\
b &\mapsto (\mathrm{ev}_b: g \mapsto g(b) )
\end{align*}
\]

\[
\begin{align*}
f: A &\to B \\
a &\mapsto f(a)
\end{align*}
\]

\[
\begin{align*}
f\dual: B\dual &\to A\dual \\
g &\mapsto g \circ f
\end{align*}
\]

\[
\begin{align*}
f^{\vee\vee}: A^{\vee\vee} &\to B^{\vee\vee} \\
h &\mapsto h \circ f\dual
\end{align*}
\]

We can now check that $f^{\vee\vee} \circ \theta_A = \theta_B \circ f$ as maps from $A$ to $B^{\vee\vee}$. Letting $a\in A$, and $h\in B^{\vee\vee}$ (so $h: B\dual \to R$), we will show that both maps act on $h$ in the same way.

For notational convenience, write $\phi \actson h \definedas h\circ \phi$. We then have

\[
\begin{align*}
(f^{\vee\vee} \circ \theta_A)(a) \actson h 
&\definedas f^{\vee\vee}(\theta_A(a)) \actson h \\
&\definedas f^{\vee\vee}(\mathrm{ev}_a)\actson h \\
&=(\mathrm{ev}_a \circ f\dual)\actson h \\
&\definedas h \circ (\mathrm{ev}_a  \circ f) \\
&\definedas h(f(a)) \\
&= \mathrm{ev}_{f(a)}\actson h \\
&\definedas \theta_B(f(a))\actson h \\
&\definedas (\theta_B \circ f)(a)\actson h,
\end{align*}
\]

which shows that these actions agree, and thus the diagram commutes.

## Problem 5

Let $E$ be a free module over $R$ an integral domain. 
Then $E$ has a basis $\theset{\vector e_i} \subseteq F$, so if $x \neq 0 \in E$, we have
$$
x = \sum_i r_i \vector e_i
$$

where each $r_i \in R$. Moreover, since $x\neq 0$, at least one $r_i \neq 0$, so let $r_j$ denote one of the nonzero coefficients.

Now suppose $x$ is a torsion element, so $mx = 0$ for some $m\neq 0 \in E$. We can then write
$$
mx = m\sum_i r_i \vector e_i = \sum_i mr_i \vector e_i = 0
$$

But by linear independence, this forces $mr_i = 0$ for all $i$. 
In particular, $mr_j = 0$ where $r_j \neq 0$.
But this exhibits either $m$ or $r_j$ as a zero divisor, and since the only zero divisor in an integral domain is zero, we must have $m=0$ or $r_j = 0$, a contradiction.

So $x$ can not be a torsion element. But since $x \in E$ was arbitrary, $E$ must be torsion-free.

For an example of a torsion-free module over an integral domain that is *not* free, consider $\QQ$ as a $\ZZ\dash$module. Then $\QQ$ is clearly torsion-free, since it is an integral domain and the same argument as above applies. 

But $\QQ$ is not free as $\ZZ\dash$module. Supposing that $\mathcal B =\theset{\vector b_1, \vector b_2, \cdots} \subset \QQ$ was a $\ZZ\dash$basis, consider $\vector b_1 = \frac {p_1} {q_1}$ and $\vector b_2 = \frac {p_2} {q_2}$. 
Then $\vector b_1, \vector b_2$ can not be linearly independent over $\ZZ$, which follows from the fact that
$$
q_1 p_2 \vector b_1 + q_2 p_1 \vector b_2 = p_2 p_1 - p_1 p_2 = 0, 
$$

while $q_1 p_2, ~q_2 p_1 \neq 0 \in \ZZ$. 
$\qed$

## Problem 6

If $A$ is a cyclic module over a commutative ring $R$, so we have $A = Ra$ for some $a\in A$. By Hungerford's definition, the submodule $A$ has order $r$ $\iff$ the element $a$ has order $r$ $\iff$ the order ideal $\mathcal{O}_a \definedas \theset{x\in R \mid xa = 0} = (r)$. 

In particular, $ra = 0$.

### Part 1

Since $(r, s) = (1)$, we can find $t_1, t_2 \in R$ such that
\[
\begin{align*}
t_1r + t_2 s = 1 &\implies t_1ra + t_2 sa = 1a  &\\
&\implies t_1(ra) + t_2 sa = a &\\
&\implies t_2 sa = a &\text{since $ra=0$}\\
&\implies s(t_2 a) = a &\text{since $R$ is commutative}
,\end{align*}
\]

which implies that $a \in sA$ and thus $A \subseteq sA$. However, we always have $sA \subseteq A$ for modules, so this shows that $A = sA$.

To see that $A[s] = \theset{x\in A \mid sx = 0} = 0$, let $x\in A[s]$; we will show $x=0$. Since $x\in A = Ra$, we have $x = r_1 a$, and in particular 
$$
ra = 0 \implies rx = r r_1 a = r_1 (ra) = 0.
$$

So we now have $rx = 0$ and $sx=0$, and we can write
\[
\begin{align*}
x &= (t_1 r + t_2 s)x \\
&= t_1 (rx) + t_2 (sx) \\
&= t_1 0 + t_2 0 \\
&= 0
.\end{align*}
\]

So $x = 0$ and thus $A[s] = 0$.
$\qed$

### Part 2

Suppose $r = sk$. 
Toward an application of the first isomorphism theorem, define a map
\[
\begin{align*}
\phi: R &\to sA = sRa \\
x &\mapsto sxa
.\end{align*}
\]

**$\phi$ is well-defined**: 

This follows from that fact that $a\in A \implies xA \in A$ for any $x\in R$, so the codomain is in fact $sA$. 

**$\phi$ is an $R\dash$module homomorphism:** 

We have 
\[
\begin{align*}
t\in R \implies \phi(tx) &= s(tx)a = t(sxa) = t\phi(x) \\
x,y \in R \implies \phi(x + y) &= s(x+y)a = sxa + sya + \phi(x) + \phi(y)
\end{align*}
\]


**$\ker \phi = (k)$**: 

Suppose $x\in \ker\phi$ so $sxa = 0_A$; we'd like to show $x \in (k)$.

By definition $sx \in \mathcal O_a$, and by assumption $\mathcal O_a = (r)$, so $sx = t_1 r$ for some $t_1 \in R$. 
\[
\begin{align*}
& sxa = 0_A \\
\implies sx &= t_1 r &\text{since $sx \in \mathcal O_a$} \\
\implies sx &= t_1 (sk)  &\text{since $r=sk$ by assumption}\\
\implies sx &= s (t_1 k) &\text{since elements in $R$ and $A$ commute}\\
\implies x &= t_1 k &\text{since $R$ is a domain, so $sm = sn, s\neq 0 \implies m=n$}
,\end{align*}
\]

which exhibits $x = t_1 k \implies x\in (k)$ as desired.

**$\phi$ is surjective:**

Since $A=Ra$, we have $sA =sRA$ and thus $x\in sA \implies x = sra$ for some $r\in R$; but then $\phi(r) = sra = x$.

We thus have
\[
\begin{align*}
R/\ker \phi \cong \im \phi \implies R/(k) \cong sA.
\end{align*}
\]


Similarly, define a map
\[
\begin{align*}
\psi: R &\to A[s] \\
x &\mapsto kxa
\end{align*}
\]

**$\psi$ is well-defined**:

It suffices to check that $\im \psi \subseteq A[s]$ (since we will show surjectivity shortly), i.e. that $s$ annihilates anything in the image. This follows from
$$
s (kxa) = (sk)xa = rxa = x(ra) = 0,
$$
since $ra = 0$ by assumption.


**$\psi$ is an $R\dash$module homomorphism:**

We can check
$$
\psi(tr_1 + r_2) = k(tr_1 + r_2)s = tkr_1s + kr_2 s = t\psi(r_1) + \psi(r_2)
$$

which follows because elements of $R$ commute with those from $A$ under multiplication.

**$\ker \psi = (s)$**:

Suppose $x\in \ker\psi$, so $kxa = 0$. Then $kx \in \mathcal O_a = (r)$, so $kx = r t_1$. Then

\[
\begin{align*}
& kxa = 0_A  \\
&\implies kx = r t_1 & \text{since } kx \in \mathcal O_a\\
&\implies kx = (sk)t_1  &\text{since } r = sk\\
&\implies kx = k(st_1) &\text{since $R$ is commutative} \\
&\implies x = s t_1 &\text{since $R$ is a domain},
\end{align*}
\]
and so $x\in (s)$ as desired.

**$\psi$ is surjective:**

Letting $y \in A[s]$ be arbitrary. We have
\[
\begin{align*}
y \in A[s] &\implies x = t_1 a,\quad sx = 0 \\
&\implies s(t_1 a) = 0 \\
&\implies st_1 \in \mathcal O_a \implies \exists x\in R \suchthat st_1 = xr = x (sk) \\
&\implies st_1 = sxk \\
&\implies t_1 = xk \qquad\qquad\text{since $R$ is a domain} \\
&\implies y = t_1 a = (x k)a = kxa, 
\end{align*}
\]

so $\psi(x) = y$.

We can then apply the first isomorphism theorem
$$
R/\ker \psi \cong \im \psi \implies R/(s) \cong A[s].
$$

$\qed$

## Problem 7

**Lemma:**
If $M$ is a cyclic module over a PID, then $M$ has exactly 1 invariant factor.

**Lemma:**
Let $A$ be a cyclic module, so $A = Ra$. If the order of $A$ is $r$, so $\mathcal O_a = (r)$, then $A \cong R/(r)$.

This means that we can write $A = R/(a)$ and $B = R/(b)$, and $a, b$ are the invariant factors of $A, B$ respectively, and $M\definedas A \oplus B \cong R/(ab)$.

Since $R$ is a PID, there is unique factorization, so we can write
\[
\begin{align*}
r &= \prod_{i=1}^n p_i^{k_i} \\
s &= \prod_{i=1}^n p_i^{\ell_i} \\
\implies rs &= \prod_{i=1}^n p_i^{k_i + \ell_i},
\end{align*}
\]

where we allow some $k_i, \ell_i = 0$ so that we can take the product over the same set of primes.

However, means that the elementary divisors of $M$ are given by the multiset $L \definedas \theset{p_i^{k_i}} \union \theset{p_i^{\ell_i}}$.

The largest invariant factor $d_1$ of $M$ is obtained from the elementary divisors
by 

a. Forming the multiset $L$ of elementary divisors,
b. Selecting the highest power of each prime occurring, say $s_i \definedas p_i^{\max(k_i, \ell_i)}$,
c. Removing $s_i$ from $L$,
d. Then letting $d_1 = \prod s_i$.

However, this process yields $d_1 = \mathrm{lcm}(r, s)$ by construction, since 
$$
d_1 = \prod_{i=1}^n s_i = \prod_{i=1}^n p_i^{\max(k_i, \ell_i)} \definedas \mathrm{lcm}(r_s).
$$

The next largest invariant factor is obtained by performing the same process on the remaining prime powers in $L$.
However, we can note that after obtaining $d_1$, we have $L = \theset{p_i^{\min(k_i, \ell_i)}}$, since **there were only two choices** for each $p_i$ occurring and we chose the copy with the maximal exponent.

But this means when we perform step (b) to obtain $d_2$, **there is now only one choice**, and thus each $s_i = p_i^{\min(k_i, \ell_i)}$ and we have
$$
d_2 = \prod_{i=1}^n s_i = \prod_i p_i^{\min(k_i, \ell_i)} \definedas \gcd(r, s).
$$

> Note: by construction, $d_2 \divides d_1$, since we are choosing from the same prime powers but with smaller exponents.

Since there were only at most two copies of each prime occurring in $L$, where one of them was chosen for $d_1$ and the other was chosen for $d_2$, this exhausts all of the elements in $L$. But this means $M$ has only two invariant divisors,
\[
\begin{align*}
d_1 &= \lcm(r, s) \\
d_2 &= \gcd(r, s)
,\end{align*}
\]

which is what we wanted to show.
$\qed$

> Note: the indexing convention for $d_i$ is opposite the usual one here, since we are choosing the largest invariant factor first, and so we have $d_n \divides d_{n-1} \divides \cdots \divides d_1$.

# Qual Problems

## Problem 8

### Part 1

The claim is that every element in $M \definedas R^n/\im A$ is torsion $\iff$ the matrix rank of $A$ is exactly $n \iff$ the Smith normal form of $A$ has exactly $n$ nonzero invariant factors.

To see that this is the case, we can apply the structure theorem for finitely-generated modules over a PID. This gives us
$$
M \cong F \oplus \bigoplus R/(r_i)
$$

where $F$ is free of finite rank, $R/(r_i)$ is cyclic torsion, and $r_i \divides r_{i+1} \divides \cdots$ are the invariant factors of $M$. 

We thus have
$$
M \cong R^n/\im A \cong F \oplus \bigoplus R/(r_i),
$$

which will be pure torsion if and only if $F = 0$.

But if we compute the smith normal for of $A$, we obtain
$$
SNF(A) = 
\left[ \begin{array}{rrrrrr}
 d_1 & 0 & \cdots & 0 & \cdots & 0 \\
0 & d_2 & \cdot & 0 & \cdots & 0\\
\vdots & \vdots & \ddots & \vdots & \cdots & 0\\
0 & 0 & \cdots & d_n & \cdots & 0
\end{array}\right]
$$

where $d_1 \divides d_2 \divides \cdots \divides d_n$, and thus
\[
\begin{align*}
\im A \cong \im SNF(A) &\cong d_1 R \oplus d_2 R \oplus \cdots \oplus d_n R \\  \\
\implies M = R^n/\im A &\cong \frac{R^n}{d_1 R \oplus d_2 R \oplus \cdots d_n R} \\ \\
&\cong R/(d_1) \oplus R/(d_2) \cdots \oplus R/(d_n)
\end{align*}
\]

where $R/(d_i)$ is a cyclic torsion module precisely when $d_i \neq 0$. If instead some $d_i = 0$, we then have $R/(d_i) \cong R$, which is a free $R\dash$module, yielding non-torsion elements in $M$.

But $\det(A) = \det(SNF(A)) = \prod_{i=1}^n d_i$, and so if $d_i=0$ for some $i$ iff $\det A = 0$ iff $\rank A < n$.


### Part 2

Identifying 
$$
R \cross F = F[x] \oplus F \cong F[x] \oplus \frac{F[x]}{(f)}
$$
where $f$ is any degree 1 polynomial in $F[x]$, by the structure theorem we can pick a matrix $A \in M_2(F[x])$ with invariant factors $d_1 = 0, d_2 = f$. 
Then by the same argument given in part 1, we would have 
$$
(F[x])^2/\im A \cong \frac{ F[x] }{(d_1)} \oplus \frac{F[x]}{(d_2)} = F[x] \oplus \frac{F[x]}{(f)}
$$

So we can choose $n=2$, and say $f(x) = x+1$, and then just pick a matrix that is already in Smith normal form:
\[
\begin{align*}
A = 
\left[ \begin{array}{cc}
x+1 & 0 \\
0 & 0
\end{array}\right].
\end{align*}
\]


## Problem 9


### Part 1

Let $M$ be a finitely generated module over $R$ a PID. 

Then
$$
M \cong F \oplus \bigoplus_{i=1}^n R/(d_i)
$$

where $F$ is free of finite rank and $R/(d_i)$ are cyclic torsion modules (the *invariant factors*) satisfying $d_1 \divides d_2 \divides \cdots \divides d_n$.

Equivalently,

$$
M \cong F \oplus \bigoplus_{i=1}^n R/(p_i^{s_i})
$$

where $F$ is free of finite rank, $p^i \in R$ are (not necessarily distinct) prime elements (the *elementary divisors*), and $s_i \in \ZZ^{\geq 1}$. 

### Part 2

Since $\ZZ^4$ is a finitely generated module over the PID $\ZZ$, the structure theorem applies, and we can write $M \cong \ZZ^k \oplus \bigoplus \ZZ/(r_i)$ for some $k\leq 4$ and some collection $r_i$ of invariant factors.

If we write $M \cong \ZZ^4/N$ where $N$ is the submodule generated by the prescribed relations, then we can construct a homomorphism of $\ZZ\dash$modules $L: \ZZ^4 \to N$ which is given by the matrix
$$ 
A_L =
\left(\begin{array}{rrrr}
3 & 12 & 3 & 6 \\
0 & 6 & 0 & 0 \\
-3 & 6 & -3 & 0 \\
0 & 0 & 0 & 0
\end{array}\right)
$$

Then $\im A_L \cong N$, and we can compute the Smith normal form,
$$
SNF(A_L) = 
\left(\begin{array}{rrrr}
3 & 0 & 0 & 0 \\
0 & 6 & 0 & 0 \\
0 & 0 & 6 & 0 \\
0 & 0 & 0 & 0
\end{array}\right)
$$

which shows that the invariant factors are $3, 6, 6, 0$. We can thus write $\im A_L \cong 3\ZZ \oplus 6\ZZ \oplus 6\ZZ$, and so
$$
M \cong \frac{\ZZ^4}{3\ZZ \oplus 6\ZZ \oplus 6\ZZ} \cong \ZZ \oplus \ZZ/(3) \oplus \ZZ/(6) \oplus \ZZ/(6).
$$

## Problem 10

### Part 1

An element $x\in M$ is *torsion* iff there exists some nonzero $r\in R$ such that $rm = 0$, or equivalently $\mathrm{Ann}(x) \neq 0$.

### Part 2

Let $R = \CC[x],~ M = \CC^2$, and
$$
A = 
\left[\begin{array}{ccc}
1 & 2 \\ 2 & 1
\end{array}\right]
\in M_2(\CC).
$$

Then $\CC^2$ is a module over $\CC[x]$ with action given by 
$$
p(x) \actson \vector v \definedas p(A)\vector v
$$

Then $M$ is cyclic as an $R\dash$module and generated by the basis vector $[1, 0]^2 \in \CC^2$, since 
\[
\begin{align*}
(tA + s)
\left[\begin{array}{cc}
1 \\ 0
\end{array}\right]
&= 
\left[\begin{array}{cc}
x \\ y
\end{array}\right]
\\
\implies
\left[\begin{array}{cc}
t & 2t \\ 2t & t
\end{array}\right]
\left[\begin{array}{cc}
1 \\ 0
\end{array}\right]
+
\left[\begin{array}{cc}
s \\ 0
\end{array}\right]
&=
\left[\begin{array}{cc}
x \\ y
\end{array}\right] \\
\implies 
\left[\begin{array}{cc}
t + s \\ 2t
\end{array}\right]
&=
\left[\begin{array}{cc}
x \\ y
\end{array}\right] \\
\implies 
\left[\begin{array}{cc}
1 & 1 \\ 2 & 0
\end{array}\right]
\left[\begin{array}{cc}
t \\ s
\end{array}\right] 
&=
\left[\begin{array}{cc}
x \\ y
\end{array}\right] \\
,\end{align*}
\]

which is a linear system of equations represented by an invertible matrix, which always has a solution. So every $\vector v\in \CC^2$ is the image of some polynomial in $A$.

It is then easy to see that $\CC^2$ is torsion as a module over $\CC[x]$, since by Cayley-Hamilton we have $\mathrm{Ann}(A) = (\mathrm{minpoly}(A)) = (x^2-2x-3)$, and so letting $p(x) = x^2-2x-3$, we find that 
$$
\forall~ \vector v\in \CC^2 \quad p(A) \actson \vector v = 0 \actson \vector v = 0.
$$

### Part 3

Suppose $R$ is a domain, $M$ an $R\dash$module, and let 
$$
T(M) = \theset{m \in M \suchthat rm = 0 \text{ for some $r\neq 0 \in R$}}.
$$

Then $T(R)$ is a submodule iff for all $r\in R$ and all $m,n\in T(M)$ we have $rm + n \in T(M)$.

So pick annihilators $a_m, a_n \neq 0 \in R$ where $a_m m = 0$ and $a_n n = 0$. 

Since $a_m \neq 0$ and $a_n \neq 0$, the product $a_m a_n \neq 0$ **because $R$ is a domain**.

Since $0 \in T(M)$, we can suppose $rm+n \neq 0$ (otherwise this is in $T(M)$ trivially). Then

\[
\begin{align*}
a_m a_n (rm + n) 
&= a_m a_n r m + a_m a_n n \\
&=r a_n (a_m m) + a_m (a_n n) \\
&= r a_n 0 + a_m 0 \\
&= 0
.\end{align*}
\]

where the commutativity of $r, a_n, a_m$ follows from the fact that these are all elements of $R$, which is a domain, and in particular is commutative.
$\qed$
