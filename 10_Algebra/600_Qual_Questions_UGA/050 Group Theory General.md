# Group Theory: General

## Permutations


### Fall 2021 #1 #algebra/qual/work 

Let $G$ be a group. An automorphism $\phi: G \rightarrow G$ is called *inner* if the automorphism is given by conjugation by a fixed group element $g$, i.e.,
\[
\phi=\phi_{g}: h \mapsto g h g^{-1} .
\]

a.
Prove that the set of inner automorphisms forms a normal subgroup of the group of all automorphisms of $G$.

b.
Give an example of a finite group with an automorphism which is not inner.

c.
Denote by $S_{n}$ the group of permutations of the set $\{1, \ldots, n\}$. Suppose that $g \in S_{n}$ sends $i$ to $g_{i}$ for $i=1, \ldots, n .$ Let $(a, b)$ denote as usual the cycle notation for the transposition which permutes $a$ and $b$. For $i \in\{1, \ldots, n-1\}$, compute $\phi_{g}((i, i+1))$.

d.
Suppose that an automorphism $\phi \in \operatorname{Aut}\left(S_{n}\right)$ preserves cycle type, i.e., that for every element $s$ of $S_{n}, s$ and $\phi(s)$ have the same cycle type. Show that $\phi$ is inner. 

> Hint: Consider the images of generators $\phi((1,2)), \phi((2,3)), \cdots, \phi((n-1, n))$.


## Cosets

### Spring 2020 #2 #algebra/qual/completed
Let $H$ be a normal subgroup of a finite group $G$ where the order of $H$ and the index of $H$ in $G$ are relatively prime.
Prove that no other subgroup of $G$ has the same order as $H$.

:::{.concept}
\envlist

- Division algorithm: $(a,b)= d\implies as+bt =1$ for some $s, t$.
- Coset containment trick: $X\subseteq N \iff xN = N$ for all $x$.
:::

:::{.strategy}
Recognize that it suffices to show $hN = N$.
Context cue: coprimality hints at division algorithm.
Descend to quotient so you can leverage both the order of $h$ *and* the order of cosets simultaneously.
:::

:::{.solution}
\envlist

- For ease of notation, replace $H$ in the problem with $N$ so we remember which one is normal.
- Write $n\da \size N$ and $m \da [G:N] = \size G/N$, where the quotient makes sense since $N$ is normal.
- Let $H \leq G$ with $\size H = n$, we'll show $H=N$.
  - Since $\size H = \size N$ it suffices to show $H \subseteq N$.
  - It further suffices to show $hN = N$ for all $h\in H$.
- Noting $\gcd(m, n)=1$, use the division algorithm to write $1 = ns + mt$ for some $s,t\in \ZZ$.
- The result follows from a computation:
\[
hN 
&= h^1 N \\
&= h^{ns + mt}N \\
&= h^{ns} N \cdot h^{mt}N \\
&= \qty{h^n N}^s \cdot \qty{h^t N}^m \\
&= (eN)^s \cdot N \\
&= N
,\]
  - We've used that $h\in H \implies o(h) \divides \size H = n$ by Lagrange, so $h^n = e$.
  - We've also used that $\size G/N = m$, so $(xH)^m = H$ for any $xH\in G/H$.

:::

### Fall 2014 #6 #algebra/qual/completed
Let $G$ be a group and $H, K < G$ be subgroups of finite index.
Show that
\[
[G: H\intersect K] \leq [G: H] ~ [G:K]
.\]


:::{.concept}
\envlist

- For $H, K\leq G$, intersection is again a subgroup of everything: $H\intersect K \leq H, K, G$ by the one-step subgroup test.
- Counting in towers: $A\leq B \leq C \implies [C:A] = [C:B][B:A]$.
- Fundamental theorem of cosets: $xH = yH \iff xy\inv \in H$.
- Common trick: just list out all of the darn cosets!

:::

:::{.strategy}
Count in towers, show that distinct coset reps stay distinct.

:::

:::{.solution}
\envlist

- $H \intersect K \leq H \leq G \implies [G: H \intersect K] = [G: H] [H : H \intersect K]$
- So it suffices to show $[H: H \intersect K] \leq [G: K]$
- Write $H/H \intersect K = \ts{ h_1 J, \cdots, h_m J }$ as distinct cosets where $J \da H \intersect J$.
- Then $h_i J\neq h_j J \iff h_i h_j\inv \not\in J = H \intersect K$.
- $H$ is a subgroup, so $h_i h_j\inv \in H$ forces this not to be in $K$.
- But then $h_i K \neq h_j K$, so these are distinct cosets in $G/K$.
- So $\size G/K \geq m$.
:::

### Spring 2013 #3 #algebra/qual/completed
Let $P$ be a finite $p\dash$group.
Prove that every nontrivial normal subgroup of $P$ intersects the center of $P$ nontrivially.

\todo[inline]{Clean up, sketchy argument.}

:::{.solution}
\envlist

- Let $N\normal P$, then for each conjugacy class $[n_i]$ in $N$, $H \intersect [g_i] = [g_i]$ or is empty.
- $G = \disjoint_{i\leq M} [g_i]$ is a disjoint union of conjugacy classes, and the conjugacy classes of $H$ are of the form $[g_i] \intersect H$.
- Then pull out the center
\[
H = \Disjoint_{i\leq M} [g_i] \intersect H = \qty{ Z(G) \intersect H } \disjoint \Disjoint_{i\leq M'} [g_i]
.\]
- Taking cardinalities, 
\[
\size H = \size \qty{ Z(G) \intersect H} + \sum_{i\leq M'} \size [g_i]
.\]
- $p$ divides $H$ since $H\leq P$ and $P$ is a $p\dash$group.
- Each $\size [g_i] \geq 2$ since the trivial conjugacy classes appear in the center, forcing $\size [g_i] \geq p$.
- $p$ divides $\size [g_i]$ since $\size [g_i]$ must divide $\size P = p^k$
- So $p$ must divide the remaining term $Z(G) \intersect H$, which makes it nontrivial.

:::


## Burnside / Class Equation

### Spring 2019 #4 #algebra/qual/completed
For a finite group $G$, let $c(G)$ denote the number of conjugacy classes of $G$.

a.
Prove that if two elements of $G$ are chosen uniformly at random,then the probability they commute is precisely
$$
\frac{c(G)}{\abs G}
.$$

b.
State the class equation for a finite group.

c.
Using the class equation (or otherwise) show that the probability in part (a) is at most $$
\frac 1 2 + \frac 1 {2[G : Z(G)]}
.$$

> Here, as usual, $Z(G)$ denotes the center of $G$.

:::{.warnings}
(DZG) This is a slightly anomalous problem!
It's fun and worth doing, because it uses the major counting formulas.
Just note that the techniques used in this problem perhaps don't show up in other group theory problems.
:::

:::{.concept}
\envlist

- Notation: $X/G$ is the set of $G\dash$orbits
- Notation: $X^g = \theset{x\in X\suchthat g\cdot x = x}$
- Burnside's formula: $\size{X/G} = {1 \over \size G} \sum \size {X^g}$.
- Definition of conjugacy class: $C(g) = \ts{ hgh\inv \st h\in G }$.
:::

:::{.strategy}
Fixed points of the conjugation action are precisely commuting elements.
Apply Burnside.
Context clue: $1/[G:Z(G)]$ is weird, right? 
Use that $[G:Z(G)] = \size G/\size Z(G)$, so try to look for $\size Z(G)/\size(G)$ somewhere.
Count sizes of centralizers.
:::

:::{.solution}
\envlist

:::{.proof title="Part a"}
\envlist

- Define a sample space $\Omega = G \cross G$, so $\size {\Omega} = (\size {G})^2$.

- Identify the event we want to analyze: 
\[
A \definedas \theset{(g,h) \in G\cross G \suchthat [g,h] = 1} \subseteq \Omega
.\]
- Note that the slices are centralizers:
\[
A_g \definedas \theset{(g, h) \in \ts{ g } \cross G \suchthat [g, h] = 1} = Z(g) \implies A = \Disjoint_{g\in G} Z(g)
.\]

- Set $n$ be the number of conjugacy classes, note we want to show $P(A) = n / \abs{G}$.
 
- Let $G$ act on itself by conjugation, which partitions $G$ into conjugacy classes.

  - What are the orbits? 
  $$
  \mathcal{O}_g = \theset{hgh\inv \suchthat h\in G}
  ,$$ 
  which is the **conjugacy class** of $g$.
  In particular, the number of orbits is the number of conjugacy classes.

  - What are the fixed points? 
  $$X^g = \theset{h\in G \suchthat hgh\inv = g},$$ 
  which are the elements of $G$ that commute with $g$, which is isomorphic to $A_g$.


- Identifying centralizers with fixed points, 
  $$
  \size{A} = \size{\Disjoint_{g\in G} Z(g) } = \sum_{g\in G} \size{Z(g)} = \sum_{g\in G}\size {X^g}
  .$$


- Apply Burnside
$$
\size {X / G} = \frac { 1 } { \size G  } \sum _ { g \in G } \size X ^ { g } ,
$$
- Note $\size{X/G} = n$, i.e. the number of conjugacy classes is the number of orbits.
- Rearrange and use definition:
$$
n \cdot \size{G}
= \qty{\size{X/G} }\cdot \size{G}
= \sum _ { g \in G } \size X ^ { g } 
$$
- Compute probability:
\[
P(A)
= {\size A \over \size \Omega} 
= \Sum_{ g \in G } \frac{\size X ^ { g }}{ ( \size {G} )^2} 
= \frac{\qty{ \size {X/G}} \cdot \size{G}}{ (\size{G})^2} 
= \frac{n \cdot \size{G}}{( \size{G} )^2} 
= \frac n {\size G}
.\]

:::

:::{.proof title="Part b"}
Statement of the class equation:
\[
\abs G = Z(G) + \sum_{\substack{\text{One $x$ from each} \\ \text{conjugacy class}}}[G: Z(x)]
\]
where $Z(x) = \theset{g\in G \suchthat [g, x] = 1}$ is the centralizer of $x$ in $G$.
:::

:::{.proof title="Part c"}
\envlist

> (DZG): I couldn't convince myself that a previous proof using the class equation actually works.
> Instead, I'll borrow the proof from [this note](https://math.berkeley.edu/~tb65536/Commuting_Probability.pdf)

- Write the event as $A = \Disjoint_{g\in G} \ts{g} \cross Z(g)$, then
\[
P(A) 
= {\size A\over (\size G)^2} 
= {1\over (\size G)^2} \sum_{g\in G} \size Z(g)
.\]
- Attempt to estimate the sum: pull out central elements $g\in Z(G)$.
  - Note $Z(g) = G$ for central $g$, so $\size Z(g) = \size G$
  - Note 
  \[
  g\not\in Z(G)\implies \size Z(g) \leq {1\over 2} \size G
  ,\]
  since $Z(g) \leq G$ is a subgroup, and 
  \[
  [G:Z(g)] \neq 1 \implies [G: Z(g)] \geq 2
  .\]
- Use these facts to calculate:
\[
P(A) 
&= {1\over (\size G)^2 } \qty{ \sum_{g\in Z(g)} \size Z(g) + \sum_{g\not\in Z(g)} \size Z(g) } \\
&= {1\over (\size G)^2 } \qty{ \sum_{g\in Z(g)} \size G + \sum_{g\not\in Z(g)} \size Z(g) } \\
&= {1\over (\size G)^2 } \qty{ \size Z(G) \cdot \size G + \sum_{g\not\in Z(g)} \size Z(g) } \\
&\leq {1\over (\size G)^2 } \qty{ \size Z(G) \cdot \size G + \sum_{g\not\in Z(g)} {1\over 2} \size G } \\
&= {1\over (\size G)^2 } \qty{ \size Z(G) \cdot \size G + \qty{ \sum_{g\not\in Z(g)} {1\over 2} } \cdot \size G } \\
&= {1\over (\size G) } \qty{ \size Z(G) + \sum_{g\not\in Z(g)} {1\over 2} } \\
&= {1\over (\size G) } \qty{ \size Z(G) + {1\over 2} \sum_{g\not\in Z(g)} 1 } \\
&= {1\over (\size G) } \qty{ \size Z(G) + {1\over 2} \size (G \sm Z(G) ) } \\
&= {1\over (\size G) } \qty{ \size Z(G) + {1\over 2} \size G - {1\over 2} \size Z(G) } \\
&= {1\over (\size G) } \qty{ {1\over 2} \size Z(G) + {1\over 2} \size G  } \\
&= {1\over 2} \qty{1 + { \size Z(G) \over \size G }} \\
&= {1\over 2} \qty{1 + { 1 \over [G : Z(G)]  }}
.\]



:::

\todo[inline]{Redo part c}

:::

## Group Actions / Representations

### Spring 2017 #1 #algebra/qual/completed
Let $G$ be a finite group and $\pi: G\to \sym(G)$ the Cayley representation.

> (Recall that this means that for an element $x\in G$, $\pi(x)$ acts by left translation on $G$.)

Prove that $\pi(x)$ is an odd permutation $\iff$ the order $\abs{\pi(x)}$ of $\pi(x)$ is even and $\abs{G} / \abs{\pi(x)}$ is odd.

:::{.warnings}
(DZG): This seems like an unusually hard group theory problem.
My guess is this year's qual class spent more time than usual on the proof of Cayley's theorem.
:::

:::{.concept}
\envlist

- $\Sym(G) \da \Aut_\Set(G, G)$ is the group of set morphisms from $G$ to itself, i.e. permutations of elements of $G$.
- More standard terminology: this is related to the **left regular representation** where $g\mapsto \phi_g$ where $\phi_g(x) = gx$, regarded instead as a permutation representation.
  - This action is transitive!
- Cayley's theorem: every $G$ is isomorphic to a subgroup of a permutation group.
  In particular, take \( \ts{ \phi_g \st G\in G } \) with function composition as a subgroup of $\Aut_\Set(G)$.
:::

:::{.solution}
\envlist

> (DZG): Warning!! I haven't checked this solution very carefully, and this is kind of a delicate parity argument.
  Most of the key ideas are borrowed [from here](https://math.stackexchange.com/questions/3028603/show-that-phig-is-an-even-permutation).

- Write $k \da o(\pi_g)$, then since $\pi$ is injective, $k = o(g)$ in $G$.
- Since $\pi_g$ as a cycle is obtained from the action of $g$, we can pick an element $x_0$ in $G$, take the orbit under the action, and obtain a cycle of length $k$ since the order of $g$ is $k$.
  Then continue by taking any $x_1$ not in the first orbit and taking *its* orbit.
  Continuing this way exhausts all group elements and yields a decomposition into disjoint cycles:
\[
\pi_g = 
(x_0, gx_0, g^2 x_0, \cdots, g^{k-1} x_0)
(x_1, gx_1, g^2 x_1, \cdots, g^{k-1} x_1)
\cdots
(x_m, gx_m, g^2 x_m, \cdots, g^{k-1} x_m)
.\]
- So there are $m$ orbits all of length exactly $k$.
  Proceed by casework.
- If $k$ is even:
  - This yields $m$ odd cycles, and thus $\pi$ has zero (an even number) of even cycles.
  - Thus $\pi \in \ker \sgn$ and is an even permutation.
- If $k$ is odd
  - This yields $m$ even cycles, thus an even number of even cycles iff $m$ is even 
- The claim is that the number of orbit representatives $m$ is equal to $[G:H] = \size G/H$ for $H = \gens{ g }$. 
  - Proof: define a map
  \[
  \ts{ \text{Orbit representatives } x_i } &\to G/H \\
  x &\mapsto xH
  .\]
  - This is injective and surjective because
  \[
  xH = yH &\iff xy\inv \in H = \gens{ g } \\
  &\iff xy\inv = g^\ell \\
  &\iff x=g^\ell y \\
  &\iff y\in \OO_x
  ,\]
  so $y$ and $x$ are in the same orbit and have the same orbit representative.

- We now have
\[
\pi_g \text{ is an even permutation } \iff 
\begin{cases}
k \text{ is odd and } m \text{ is even} &  
\\
\text{ or } & \\
k \text{ is even}
 & .
\end{cases}
\]
- Everything was an iff, so flip the evens to odds:
\[
\pi_g \text{ is an odd permutation } \iff 
\begin{cases}
k \text{ is even and } m \text{ is odd} &  
\\
\text{ or } & \\
k \text{ is odd}
 & .
\end{cases}
.\]
- Then just recall that $k\da o(\pi_g)$ and 
\[
m= [G: \gens{ g }] = \size G / \size \gens{ g }= \size G / o(g) = \size G/ o(\pi_g)
.\]




:::


### Fall 2015 #1 #algebra/qual/completed
Let $G$ be a group containing a subgroup $H$ not equal to $G$ of finite index.
Prove that $G$ has a normal subgroup which is contained in every conjugate of $H$ which is of finite index.

> (DZG) A remark: it's not the conjugates that should be finite index here, but rather the normal subgroup.

:::{.solution}
\envlist

- Let $H\leq G$ and define $n\da [G:H]$.
- Write $G/H = \ts{ x_1 H, \cdots, x_n H }$ for the finitely many cosets.
- Let $G$ act on $G/H$ by left translation, so $g\cdot xH \da gxH$..
  Call the action $\psi: G\to \Sym(G/H)$.
- Then $\Stab(xH) = xHx\inv$ is a subgroup conjugate to $H$, and $K\da \ker \psi = \Intersect_{i=1}^n xHx\inv$ is the intersection of all conjugates of $H$.
- Kernels are normal, so $K\normal G$, and $K\subseteq xHx\inv$ for all $x$, meaning $K$ is contained in every conjugate of $H$.
- The index $[G:K]$ is finite since $G/K \cong \im \psi$ by the first isomorphism theorem, and $\size \im \psi \leq \size \Sym(G/H) = \size S_n = n! < \infty$.

:::


## Conjugacy Classes

### Spring 2021 #2 #algebra/qual/completed

Let $H \normal G$ be a normal subgroup of a finite group $G$, where the order of $H$ is the smallest prime $p$ dividing $\abs{G}$.
Prove that $H$ is contained in the center of $G$.

> Solution due to Swaroop Hegde, typed up + modifications added by DZG.

:::{.concept}
\envlist

- $x\in Z(G)$ iff $\size C_x = 1$, i.e. the size of its conjugacy class is one.
- Normal subgroups are disjoint unions of (some) conjugacy classes in $G$.
  - In fact, this is a characterization of normal subgroups (i.e. $H$ is normal iff $H$ is a union of conjugacy classes in $G$).
  - Why: if $H\normal G$ then $ghg\inv \in H$ for all $g$, so $C_h \subseteq H$ and $\Union_h C_h = H$.
  Conversely, if $H = \Union_{h\in H} C_h$, then $ghg\inv \in C_h \subseteq H$ and thus $gHg\inv = H$.
- Orbit stabilizer theorem: $\size C_g = \size G/ \size K_g$ where $C_g$ is the centralizer and $K_g$ is the conjugacy class of $g$.
  - In particular, $\size C_g$ divides $\size G$.
:::


:::{.strategy}
Show an element $x$ is central by showing $\size C_x = 1$.
:::


:::{.proof title="?"}
\envlist

- Let $p \da \size H$.
- Let \( \ts{ C_i }_{i\leq n} \) be the conjugacy classes in $G$, then $G = \disjoint_{i\leq n} C_i$
- By the first fact, there is a sub-collection \( \ts{ C_{i_j}}_{j\leq k } \)  such that 
\[
H = \disjoint_{j\leq k} C_{i_j}
.\]
- The identity is always in a single conjugacy class, so $C_e = \ts{ e }$.
- Since $e\in H$, without loss of generality, label $C_{i_1} = \ts{ e }$.
- So
\[
H 
= \Disjoint_{j\leq k} C_{i_j} 
= C_{i_1}{\textstyle  \coprod} \displaystyle\Disjoint_{\substack{ j\leq k \\ j\neq 1} } C_{i_j} 
.\]

- Take cardinality in the above equation 
\[
p = 1 + \sum_{\substack{ j\leq k \\ j\neq 1 }} \size C_{i_j}
.\]
- So $\size C_{i_j} \leq p-1$ for all $j\neq 1$.

- Every $\size C_{i_j}$ divides $\size G$, but $p$ was the *minimal* prime dividing $\size G$, forcing $\size C_{i_j} = 1$ for all $j \neq 1$.
  - This rules out $\size C_{i_j}$ being a prime less than $p$, but also rules out composites: if a prime $q\divides \size C_{i_j}$, then $q<p$ and $q\divides \size G$, a contradiction.

- By fact 3, each $x\in C_{i_j}$ satisfies $x\in Z(G)$.

- $\union C_{i_j} = H$, so $H \subseteq Z(G)$.

:::


### Spring 2015 #1 #algebra/qual/completed
For a prime $p$, let $G$ be a finite $p\dash$group and let $N$ be a normal subgroup of $G$ of order $p$.
Prove that $N$ is contained in the center of $G$.

:::{.concept}
\envlist

- Definition of conjugacy class: $[x] = \ts{gxg\inv \st g\in G}$.
- A conjugacy class $[x]$ is trivial iff $[x] = \ts{ x }$ iff $x\in Z(G)$.
- Sizes of conjugacy classes divide the order of the group they live in.
  - This is orbit-stabilizer: $G\actson G$ by $g\cdot x \da gxg\inv$, so $\OO(x) = [x]$.
    Then $\size \OO(x) = \size G / \size \Stab(x)$, so $\size \OO(x)$ divides $\size G$.
:::

:::{.solution}
\envlist

- Use that $N\normal G \iff N = \disjoint' [n_i]$ is a *disjoint* union of (full) conjugacy classes.
- Take cardinalities:
\[
p = \size N = \sum_{i=1}^m \size [n_i] = 1 + \sum_{i=2}^m [n_i]
.\]
- The size of each conjugacy class divides the size of $H$ by orbit-stabilizer, so $\size [n_i] \divides p$ for each $i$.
- But the entire second term must sum to $p-1$ for this equality to hold, which forces $\size[n_i] = 1$ (and incidentally $m=p-1$)
- Then $[n_i] = \ts{ n_i } \iff n_i \in Z(G)$, and this holds for all $i$, so $N \subseteq Z(G)$.
:::

## Unsorted / Counting Arguments


### Fall 2021 #2 #algebra/qual/completed 

Give generators and relations for the non-commutative group $G$ of order 63 containing an element of order $9 .$


:::{.solution}
\envlist

- Idea: take a semidirect product involving $C_9$ and $C_7$.
  We'll need some facts: $\Hom(C_m, C_n) \cong C_d$ where $d = \gcd(m, n)$, and $\Aut(C_m)\cong C_m\units$ which has order $\phi(m)$ (since one needs to send generators to generators), which can be explicitly calculated based on the prime factorization of $m$.

- Some calculations we'll need:
  - $\Aut(C_9) \cong C_9\units \cong C_{\phi(9)} \cong C_6$, using that $\phi(p^k) = p^{k-1}(p-1)$.
  - $\Aut(C_7) \cong C_7\units \cong C_{\phi(7)}\cong C_6$ using that $\phi(p) = p-1$.
- To get a nonabelian group, we need a nontrivial semidirect product, so look at $\Hom(G, \Aut(H))$ in the two possible combinations.
  - $\Hom(C_7, \Aut(C_9)) \cong \Hom(C_7, C_6) \cong C_1 \da \ts{e}$ using that $\Hom(C_m, C_n) \cong C_{d}$ for $d = \gcd(m, n)$.
    So there are no nontrivial homs here, so only the direct product is possible.
  - $\Hom(C_9, \Aut(C_7)) \cong \Hom(C_9, C_6) \cong C_3$, so use this!
  - Note that we don't have to consider possibilities for $C_3\cross C_3$, since including this as a factor would yield no elements of order 9.

- So take $G\da C_7 \semidirect_\psi C_9$ for some $\psi: C_9 \to \Aut(C_7)$, and we can take the presentation
\[
G = \gens{x, y\st x^7, y^9, yxy\inv = \psi(x)}
.\]

- It now suffices to find a nontrivial $\psi: C_7\to C_7$.
  Writing it multiplicatively as $C_7 = \gens{x\st x^7}$, any map that sends $x$ to a generator will do.
  It suffices to choose any $k$ coprime to $7$, and then take $\psi(x) \da x^k$, which will be another generator.

- So take 

\[
G = \gens{x, y\st x^7, y^9, yxy\inv = x^2}
.\]
:::



### Fall 2019 Midterm #5 #algebra/qual/completed
Let $G$ be a nonabelian group of order $p^3$ for $p$ prime. Show that $Z(G) = [G, G]$.

> Note: this is a good problem, it tests several common theorems at once.
> Proof due to Paco Adajar.

:::{.concept}
\envlist

Important notations and definitions:

-   The **center** of $G$, denoted by $Z(G)$, is the subset of elements
    of $G$ which commute with all elements of $G$. That is, if
    $x \in Z(G)$, then for all $g \in G$, $gx = xg$:
    $$Z(G) = \{ x \in G : gx = xg \, \text{for all } g \in G \}.$$

    In fact, $Z(G)$ is not just a subset of $G$, but a normal subgroup
    of $G$.

-   The **commutator subgroup** of $G$, denoted by $[G, G]$, is the
    subgroup of $G$ generated by the commutators of $G$, i.e., the
    elements of the form $ghg^{-1}h^{-1}$:
    $$[G, G] = \langle ghg^{-1}h^{-1} : g, h \in G \rangle.$$

    The commutator subgroup $[G,G]$ is the smallest normal subgroup of
    $G$ whose quotient is abelian. That is, if $H$ is a normal subgroup
    of $G$ for which $G/H$ is abelian, then $[G, G] \le H$.

    Moreover, $G$ is abelian if and only if $[G,G]$ is trivial.

Theorems to remember and know how to prove:

-   **$G/Z(G)$ Theorem**: If $G/Z(G)$ is cyclic, then $G$ is abelian,
    i.e., $G/Z(G)$ is in fact trivial.

-   **Lagrange's Theorem**: If $G$ is a group of finite order and $H$ is
    a subgroup of $G$, then the order of $H$ divides that of $G$.

    - One consequence of this is that every group of prime order is
    cyclic.

-   A $p$-group (a group of order $p^n$ for some prime $p$ and
    some positive integer $n$) has nontrivial center.

-   A consequence of the theorems above: every group of order $p^2$
    (where $p$ is prime) is abelian.

:::

:::{.solution}
Since $Z(G)$ is a subgroup of $G$ and $|G| = p^3$, by Lagrange's
theorem, $|Z(G)| \in \{1, p, p^2, p^3\}$.

Since we stipulated that $G$ is nonabelian, $|Z(G)| \ne p^3$. Also,
since $G$ is a $p$-group, it has nontrivial center, so $|Z(G)| \ne 1$.
Finally, by the $G/Z(G)$ theorem, $|Z(G)| \ne p^2$: if $|Z(G)| = p^2$,
then $|G/Z(G)| = p$ and so $G/Z(G)$ would be cyclic, meaning that $G$ is
abelian. Hence, $|Z(G)| = p$.

Then, since $|Z(G)| = p$, we have that $|G/Z(G)| = p^2$, and so $G/Z(G)$
is abelian. Thus, $[G, G] \in Z(G)$. Since $|Z(G)| = p$, then
$|[G,G]| \in \{ 1, p\}$ again by Lagrange's theorem. If $|[G,G]| = p$
then $[G,G] = Z(G)$ and we are done. And, indeed, we must have
$|[G,G]| = p$, because $G$ is nonabelian and so $|[G,G]| \ne 1$.
:::

### Spring 2012 #2 #algebra/qual/completed
Let $G$ be a finite group and $p$ a prime number such that there is a normal subgroup $H\normal G$ with $\abs{H} = p^i > 1$.

a.
Show that $H$ is a subgroup of any Sylow $p\dash$subgroup of $G$.

b.
Show that $G$ contains a nonzero abelian normal subgroup of order divisible by $p$.

:::{.concept}
\envlist

- $p$ groups have nontrivial centers.
- Definition of maximality and $p\dash$groups
- Sylows are conjugate
- $Z(G) \ch G$ always.
- Transitivity of characteristic: $A \ch B$ and $B\normal C$ implies $A \normal C$.
:::

:::{.strategy}
Just use maximality for (a).
For (b), centers are always abelian, so $Z(H)$ is good to consider, just need to ensure it's normal in $G$.
Use transitivity of characteristic.
:::

:::{.solution}
\envlist

:::{.proof title="of a"}
\envlist

- By definition, $S\in \Syl_p(G) \iff S$ is a *maximal* $p\dash$subgroup: $S<G$ is a $p\dash$group, so $\size S = p^k$ for some $k$, $S$ is a proper subgroup, and $S$ is maximal in the sense that there are no proper $p\dash$subgroups $S'$ with $S \subseteq S' \subseteq G$.
- Since $\size H = p^i$, $H$ is a $p\dash$subgroup of $G$.
- If $H$ is maximal, then by definition $H\in \Syl_p(G)$
- Otherwise, if $H$ is not maximal, there exists an $H' \supseteq H$ with $H'\leq G$ a $p\dash$subgroup properly containing $H$.
  - In this apply the same argument to $H'$: this yields a proper superset containment at every stage, and since $G$ is finite, there is no infinite ascending chain of proper supersets.
  - So this terminates in some maximal $p\dash$subgroup $S$, i.e. a Sylow $p\dash$subgroup.
- So $H \subseteq S$ for some $S\in \Syl_p(G)$.
- All Sylows are conjugate, so for any $S' \in \Syl_p(G)$ we can write $S' = gSg\inv$ for some $g$.
- Then using that $H$ is normal, $H \subseteq S \implies H = gHg\inv \subseteq gSg\inv \da S'$.
  So $H$ is contained in every Sylow $p\dash$subgroup.

:::

:::{.proof title="of b"}
\envlist

- Claim: $Z(H) \leq H$ works.
  - It is nontrivial since $H$ is a $p\dash$group and $p\dash$groups have nontrivial centers
  - It is abelian since $Z(Z(H)) = Z(H)$.
  - $\size Z(H) = p^\ell$ for some $\ell \leq i$ by Lagrange
- It thus remains to show that $Z(H) \normal G$.
- Use that $Z(H) \ch H$ and use transitivity of characteristic to conclude $Z(H) \normal H$.
- That $Z(H) \ch H$: let $\psi \in \Aut(H)$ and $x=\psi(y)\in \psi(Z(H))$ so $y\in Z(H)$, then for arbitrary $h\in H$,
 \[
 \psi(y)h 
 &= \psi(y) (\psi \circ \psi\inv)(h) \\
 &= \psi( y \cdot \psi\inv(h) ) \\
 &= \psi( \psi\inv(h) \cdot y ) && \text{since } \psi\inv(h)\in H, \, y\in Z(H) \\
 &= h\psi(y)
 .\]
- That $A \ch B \normal C \implies A\normal C$:
  - $A\ch B$ iff $A$ is fixed by every $\psi\in \Aut(B)$., WTS $cAc\inv = A$ for all $c\in C$.
  - Since $B\normal C$, the automorphism $\psi(\wait) \da c(\wait)c\inv$ descends to an element of $\Aut(B)$.
  - Then $\psi(A) = A$ since $A\ch B$, so $cAc\inv = A$ and $A\normal C$.
:::

:::

### Fall 2016 #1 #algebra/qual/completed
Let $G$ be a finite group and $s, t\in G$ be two distinct elements of order 2.
Show that subgroup of $G$ generated by $s$ and $t$ is a dihedral group.

> Recall that the dihedral groups of order $2m$ for $m\geq 2$ are of the form
\[
D_{2m} = \gens{\sigma, \tau \suchthat \sigma^m = 1 = \tau^2, \tau \sigma = \sigma\inv \tau}
.\]

:::{.solution}
\envlist

- Suppose $G = \gens{ a, b}$ with $a^2 = b^2 = e$, satisfying some unknown relations.
- Consider $ab$. Since $G$ is finite, this has finite order, so $(ab)^n = e$ for some $n\geq 2$.
- Note $\gens{ab, b} \subseteq \gens{a, b}$, since any finite word in $ab, b$ is also a finite word in $a, b$.
- Since $(ab)b = ab^2 = a$, we have $\gens{ab, b} \subseteq \gens{a, b}$, so $\gens{ab, b} = \gens{a, b}$.
- Write $D_{2n} = F(r, s) / \ker \pi$ for $\pi: F(r, s)\to D_{2n}$ the canonical presentation map.
- Define 
\[
\psi: F(r, s) &\to G \\
r &\mapsto ab \\
t &\mapsto b
.\]
- This is clearly surjective since it hits all generators.
- We'll show that $ab, a$ satisfy all of the relations defining $D_{2n}$, which factors $\psi$ through $\ker \pi$, yielding a surjection $\tilde \psi: D_{2n} \surjects G$.
  - $(ab)^n = e$ by construction, $b^2 = e$ by assumption, and 
  \[
  b (ab) b\inv = babb\inv = ba = b\inv a\inv = (ab)\inv
  ,\]
  corresponding to the relation $srs\inv = r\inv$.
  Here we've used that $o(a) = o(b) = 2$ implies $a=a\inv, b=b\inv$.

- Surjectivity of $\tilde \psi$ yields $2n = \size D_{2n} \geq \size G$.
- The claim is that $\size G \geq 2n$, which forces $\size G = 2n$. 
  Then $\tilde \psi$ will be a surjective group morphism between groups of the same order, and thus an isomorphism.

  - We have \( \gens{ ab }\leq G  \), so $n\divides \size G$.
  - Since $b\not\in \gens{ ab }$, this forces $\size G > n$, so $\size G \geq 2n$. 

> Remark: see a more direct proof in [Theorem 2.1 and Theorem 1.1 here](https://kconrad.math.uconn.edu/blurbs/grouptheory/dihedral2.pdf)

:::


### Fall 2019 Midterm #1  #algebra/qual/completed
Let $G$ be a group of order $p^2q$ for $p, q$ prime. Show that $G$ has a nontrivial normal subgroup.
:::

:::{.solution}
\envlist

- Write $\size G = p^2 q$
- Cases: first assume $p>q$, then do $q<p$.
- In any case, we have
\[
n_p \divides q &\implies n_p \in \ts{ 1,q } \\ \\
n_q \divides p^2 &\implies n_q \in \ts{ 1, p, p^2} 
.\]

- If $n_p=1$ or $n_q=1$, we're done, so suppose otherwise.

- **Case 1:** $:p>q$.
  - Using that $[n_p]_p \equiv 1$, consider reducing elements in $\ts{1, q} \mod p$.
  - Since $q<p$, we just have $q\mod p = q$, and as long as $q\neq 1$ we have $q\not\equiv 1\mod p$.
    But since $n_p\neq 1$ and $n_p\neq q$, this is a contradiction. $\contradiction$

- **Case 2:** $p< q$:
  - Using that $[n_q]_q \equiv 1$, consider reducing $\ts{1, p, p^2}\mod q$.
  - Since now $p<q$, we have $p\mod q = p$ itself, so $p\mod q \neq 1$ and we can rule it out.
  - The remaining possibility is $n_q = p^2$.
  - Supposing that $n_p \neq 1$, we have $n_p=q$, so we can count 
  \[
  \text{Elements from Sylow } q: n_q( \size S_q - 1) &= p^2(q-1) + 1
  ,\]
  where we've used that distinct Sylow $q$s can only intersect at the identity, and although Sylow $p$s *can* intersect trivially, they can also intersect in a subgroup of size $p$.
  - Suppose all Sylow $p$s intersect trivially, we get at least
  \[
  \text{Elements from Sylow } p: n_p( \size S_p - 1) &= q(p^2-1) 
  .\]
  Then we get a count of how many elements the Sylow $p$s and $q$s contribute:
  \[
  q(p^2-1) + p^2(q-1) + 1
  = p^2q - q + p^2q - p^2 + 1 
  = p^2q + (p^2-1)(q-1)
  > p^2q = \size G
  ,\]
  provided $(p^2-1)(q-1) \neq 0$, which is fine for $p\geq 2$ since this is at least $(2^2-1)(3-2) = 3$ (since $p<q$ and $q=3$ is the next smallest prime). $\contradiction$

  - Otherwise, we get two Sylow $p$s intersecting nontrivially, which must be in a subgroup of order at least $p$ since the intersection is a subgroup of both.
  In this case, just considering these two subgroups, we get
  \[
  \text{Elements from Sylow } p: n_p( \size S_p - 1) &> p^2 + p^2 - p = 2p^2-p -1
  .\]
  Then a count:
  \[
  p^2(q-1) + (2p^2-p - 1) + 1
  &= p^2 q- p^2 + 2p^2 -p \\
  &= p^2 q + p^2 -p \\
  &= p^2q + p(p-1) \\
  &> p^2q = \size G
  ,\]
  a contradiction since this inequality is strict provided $p\geq 2$. $\contradiction$

:::

### Fall 2019 Midterm #4 #algebra/qual/work
Let $p$ be a prime. Show that $S_p = \gens{\tau, \sigma}$ where $\tau$ is a transposition and $\sigma$ is a $p\dash$cycle.

