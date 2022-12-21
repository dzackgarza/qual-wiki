# Groups: Simple and Solvable

## $\star$ Fall 2016 #7 #algebra/qual/work

a.
Define what it means for a group $G$ to be *solvable*.

a.
Show that every group $G$ of order 36 is solvable.

> Hint: you can use that $S_4$ is solvable.

## Spring 2015 #4 #algebra/qual/completed

:::{.problem title="?"}
Let $N$ be a positive integer, and let $G$ be a finite group of order $N$.

a.
Let $\sym G$ be the set of all bijections from $G\to G$ viewed as a group under composition.
Note that $\sym G \cong S_N$.
Prove that the Cayley map 
\[
C: G&\to \sym G\\
g &\mapsto (x\mapsto gx)
\]
is an injective homomorphism.

b.
Let $\Phi: \sym G\to S_N$ be an isomorphism.
For $a\in G$ define $\eps(a) \in \theset{\pm 1}$ to be the sign of the permutation $\Phi(C(a))$.
Suppose that $a$ has order $d$.
Prove that $\eps(a) = -1 \iff d$ is even and $N/d$ is odd.

c.
Suppose $N> 2$ and $N\equiv 2 \mod 4$.
Prove that $G$ is not simple.

> Hint: use part (b).

:::

:::{.warnings}
We haven't *really* covered the Cayley representation ("left-regular representation") in the qual class in recent years, and this question uses some slightly nontrivial properties of it.
:::

:::{.concept}
\envlist

- A cycle $\sigma\in S_N$ is odd $\iff \eps(\sigma) = -1 \iff \sigma$ has an odd number of even cycles $\iff \sigma$ can be written as an even number of transpositions.
- A single cycle of even length is odd, and of odd length is even, by writing $(123\cdots, d) = (12)(13)\cdots(1d)$, reading right-to-left.
- $A_n \da \ker (S_n\to \ZZ/2\ZZ)$ is the kernel of the sign morphism, so only even permutations.

:::

:::{.solution}
**Part a**:
Check that $\ker C = \ts{e} \subseteq G$, or prove injectivity directly via $C(g) = C(h) \implies g=h$.
For the former, introduce some new notation: write
\[
C: G &\to \Sym(G) \\
g &\mapsto \tau_g
.\]
where
\[
\tau_g: G &\to G \\
x &\mapsto gx
\]
is left-translation by $g$.
Now note that the identity in $\Sym(G)$ is the group morphism $\id_G$, so
\[
\ker(C) 
&\da \ts{g\in G \st C(g) = \id_G } \\
&= \ts{g\in G \st \tau_g(x) = x \,\,\forall x\in G} \\
&= \ts{g\in G \st gx = x \,\, \forall x\in G} \\
&= \Intersect_{x\in G}\Stab_G(x)
,\]
i.e. anything in the kernel is (by definition) in the stabilizer of every point $x\in G$.
Now check that
\[
g\in \Stab_G(x) \iff gx=x \iff gxx\inv = xx\inv \iff ge= e \iff g=e
\]
where $e$ is the identity in $G$,
so $\Stab_G(x) = \ts{e}$ for every $x\in G$ and thus $\ker(C) = \ts{e}$.

> Note: one should also prove that $C$ is actually a group morphism, but this is mostly a routine check.

**Part b**:
Let $\Psi: G\to S_N$ be the composition $\Psi = \Phi \circ C$; this is a group morphism and $\ker \Psi \normal G$ is always a normal subgroup (which is used in part c).

Fix $a\in G$ with $d$ defined as the order of $a$.

$\impliedby$:
Suppose $d$ is even and $N/d$ is odd. 
Let $A \da \gens{a}$, then $[G: H] = N/d$, so there are an odd number of (left) $A\dash$cosets.
Consider the permutation $\Psi(a) \in S_N$; the claim is that $\tau_a$ is a product of $N/d$ cycles, all of length $d$.
Given this claim, under our assumptions $\Psi(a)$ has an **odd number of even cycles**, is thus an odd permutation, and thus $\eps(a) = -1$.

$\implies$: 
Suppose $\eps(a) = -1$, then $\Psi(a)$ is an odd permutation. Since $\Psi(a)$ is in the image of $\Psi$, it can be written as a product (not necessarily unique) of $N/d$ cycles of length $d$.
Since this cycle must be odd, there must be an odd number of even cycles in any such decomposition.
One can show that all cycles in the image of the left-regular representation are the same length, so every cycle is of even length $d$, and there are an odd number $N/d$ of them.

**Part c**:
. Since a sufficient condition for $G$ not to be simple is existence of a nontrivial normal subgroup, it suffices to cook up a nontrivial $a\in \ker \Psi$.

Note that
\[
N\equiv 2\mod 4\implies 2\divides N\, \text{ and } 2^2\notdivides N \implies N/2 \text{ is odd}
,\]
so with the hint in mind, consider $d\da 2$.

Suppose 
\[
\ker(\Psi) \da \ts{a\in G \st \eps(a) = 1} = \ts{e}
,\]
then this forces $\eps(a) = -1$ for every nontrivial $a\in G$.
Letting $d(a)$ be the order of $a$, we know that $d(a)$ must be even and $N/d(a)$ must be odd for every $a$.
Since $d(a)$ is even, $2\divides d(a)$, but since $2^2 \not\divides N$, we must have $2^2\not\divides d(a)$.
So $d(a)$ is an even number (so no odd prime factors) with exactly one copy of $2$ in its prime factorization, forcing $d(a) = 2$ for all $a\in G$.

But now every element in $G$ is order 2, and a one can show the general result that if every $g\in G$ satisfies $g^2=e$ then the size of $G$ is a power of $2$.
However, since $N/2$ is necessarily odd, this is a contradiction. $\contradiction$

So there must be some $a\in G$ with $\eps(a)=1$, making $\ker(\Psi) \normal G$ nontrivial and exhibiting a normal subgroup that makes $G$ non-simple.

> For the power of 2 result, one can use Cauchy's theorem: if any odd prime $p\geq 3$ divides the size of $G$, then there exists an element of order $p$, contradiction.

:::


## Spring 2014 #1 #algebra/qual/work
Let $p, n$ be integers such that $p$ is prime and $p$ does not divide $n$.
Find a real number $k = k (p, n)$ such that for every integer $m\geq k$, every group of order $p^m n$ is not simple.

## Fall 2013 #1 #algebra/qual/work
Let $p, q$ be distinct primes.

a.
Let $\bar q \in \ZZ_p$ be the class of $q\mod p$ and let $k$ denote the order of $\bar q$ as an element of $\ZZ_p\units$.
Prove that no group of order $pq^k$ is simple.

b.
Let $G$ be a group of order $pq$, and prove that $G$ is not simple.

## Spring 2013 #4  #algebra/qual/work
Define a *simple group*.
Prove that a group of order 56 can not be simple.

## Fall 2019 Midterm #3 #algebra/qual/work
Show that there exist no simple groups of order 148.

