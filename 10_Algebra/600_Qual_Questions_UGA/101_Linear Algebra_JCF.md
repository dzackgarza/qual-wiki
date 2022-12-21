# Linear Algebra: Canonical Forms

## Fall 2021 #3 #algebra/qual/completed 

What is the Jordan normal form over $\mathbb{C}$ of a $7 \times 7$ matrix $A$ which satisfies all of the following conditions:

a.
$A$ has real coefficients,

b.
$\mathrm{rk} A=5$,

c.
$\mathrm{rk} A^{2}=4$,

d.
$\mathrm{rk} A-I=6$,

e.
$\mathrm{rk} A^{3}-I=4$,

f.
$\operatorname{tr} A=1 ?$


:::{.solution}
\envlist

- We'll use rank-nullity throughout: $\rank M + \dim \ker M = 7$.
- Also note that 
\[
Av = \lambda v
\implies
A^nv = A^{n-1}Av = A^{n-1}\lambda v = \cdots = \lambda^n v
,\]
  so if $\lambda \in \spec(A)$ then $\lambda^n\in \spec(A^n)$.
  Conversely, $\lambda\in \spec(A^n) \implies \lambda^{1\over n}\in \spec(A)$, which we'll use several times.
- Since $5 = \rank A = \rank(A - 0\cdot I)$,  we have $\dim \ker(A-0\cdot I) = 2$ contributing an eigenvalue of $\lambda = 0$ with multiplicity $2$.

- Since $4 = \rank A^2 = \rank(A^2 - 0\cdot \lambda) = \rank(A-0\cdot \lambda)^2$, we have that $\dim \ker(A-0\cdot I)^2 = 3$.
  Since $\dim \ker (A-0\cdot I)^1 = 2 < 3$, this means there is 1 generalized eigenvector associated to $\lambda = 0$.

- Since $6 = \rank(A-1\cdot I)$, $\dim \ker (A- 1\cdot I) = 1$, contributing $\lambda = 1$ with multiplicity 1.
- Since $\rank(A^3-1\cdot I) = 4$, we have $\dim \ker (A^3-1\cdot I) = 3$, contributing $\lambda = 1$ *now to $\spec(A^3)$* instead of $\spec(A)$.
  Thus some unknown cube roots of 1 are contributed to $\spec(A)$, so any of $1=\zeta_3^0, \zeta_3, \zeta_3^2$ are possibilities at this point.
  Call these three contributions $z_1, z_2, z_3$, which may not be distinct.

- Now use that $\tr(A) = \sum_{i=1}^n \lambda_i$ is the sum of the diagonal on $\JCF(A)$, using that trace is a similarity invariant, to write
\[
1 = \tr(A) = (0 + 0) + (0) + (1) + (z_1 + z_2 + z_3) \implies z_1 + z_2 + z_3 = 0 
,\]
which is actually enough to force $z_1 = 1, z_2 = \zeta_3, z_3 = \zeta_3^2$, since no other combination sums to zero.
That $1 + \zeta_3 + \zeta_3^2 = 0$ is a general fact.

- Since $\lambda=1$ occurs twice as an eigenvalue but $\dim \ker(A-1\cdot I) = 1$, the two copies of $\lambda = 1$ must occur in a nontrivial Jordan block.
- So we get a Jordan form
\[
\JCF(A) = 
\begin{bmatrix}
0 & & & & & & 
\\
& 0 & 1 & & & & 
\\
& & 0 & & & & 
\\
& & & 1 & 1 & & 
\\
& & & & 1 & & 
\\
& & & & & \zeta_3 & 
\\
& & & & & & \zeta_3^2
\\
\end{bmatrix}
.\]

:::

## $\star$ Spring 2012 #8 #algebra/qual/work
Let $V$ be a finite-dimensional vector space over a field $k$ and $T:V\to V$ a linear transformation.

a.
Provide a definition for the *minimal polynomial* in $k[x]$ for $T$.

b. 
Define the *characteristic polynomial* for $T$.

c. 
Prove the Cayley-Hamilton theorem: the linear transformation $T$ satisfies its characteristic polynomial.

## $\star$ Spring 2020 #8 #algebra/qual/work
Let $T:V\to V$ be a linear transformation where $V$ is a finite-dimensional vector space over $\CC$.
Prove the Cayley-Hamilton theorem: if $p(x)$ is the characteristic polynomial of $T$, then $p(T) = 0$.
You may use canonical forms.

## $\star$ Spring 2012 #7 #algebra/qual/work
Consider the following matrix as a linear transformation from $V\definedas \CC^5$ to itself:
\[
A=\left(\begin{array}{ccccc}
-1 & 1 & 0 & 0 & 0 \\
-4 & 3 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 & 1 \\
0 & 0 & 0 & 1 & 0 \\
0 & 0 & 0 & 0 & 2
\end{array}\right)
.\]

a. 
Find the invariant factors of $A$.

b. 
Express $V$ in terms of a direct sum of indecomposable $\CC[x]\dash$modules.

c.
Find the Jordan canonical form of $A$.


## Fall 2019 Final #8 #algebra/qual/work
Exhibit the rational canonical form for

  - $A\in M_6(\QQ)$ with minimal polynomial $(x-1)(x^2 + 1)^2$.
  - $A\in M_{10}(\QQ)$ with minimal polynomial $(x^2+1)^2(x^3 + 1)$.

## Fall 2019 Final #9 #algebra/qual/work
Exhibit the rational and Jordan canonical forms for the following matrix $A\in M_4(\CC)$:
  \[
  A=\left(\begin{array}{cccc}
  2 & 0 & 0 & 0 \\
  1 & 1 & 0 & 0 \\
  -2 & -2 & 0 & 1 \\
  -2 & 0 & -1 & -2
  \end{array}\right)
  .\]

## Spring 2016 #7 #algebra/qual/work
Let $D = \QQ[x]$ and let $M$ be a $\QQ[x]\dash$module such that
\[
M \cong \frac{\mathbb{Q}[x]}{(x-1)^{3}} \oplus \frac{\mathbb{Q}[x]}{\left(x^{2}+1\right)^{3}} \oplus \frac{\mathbb{Q}[x]}{(x-1)\left(x^{2}+1\right)^{5}} \oplus \frac{\mathbb{Q}[x]}{(x+2)\left(x^{2}+1\right)^{2}}
.\]

Determine the elementary divisors and invariant factors of $M$.

## Spring 2020 #7 #algebra/qual/work
Let
\[
A=\left[\begin{array}{ccc}
2 & 0 & 0 \\
4 & 6 & 1 \\
-16 & -16 & -2
\end{array}\right] \in M_{3}(\mathrm{C})
.\]

a.
Find the Jordan canonical form $J$ of $A$.

b.
Find an invertible matrix $P$ such that $P\inv A P = J$. 

c.
Write down the minimal polynomial of $A$.

> You should not need to compute $P\inv$.

## Spring 2019 #7 #algebra/qual/completed 
Let $p$ be a prime number.
Let $A$ be a $p \times p$ matrix over a field $F$ with 1 in all
entries except 0 on the main diagonal.

Determine the Jordan canonical form (JCF) of $A$

a. 
When $F = \QQ$,

b.
When $F = \FF_p$.

> Hint: In both cases, all eigenvalues lie in the ground field. In each case find a
matrix $P$ such that $P\inv AP$ is in JCF.


:::{.strategy}
\envlist

- Work with matrix of all ones instead.
- Eyeball eigenvectors.
- Coefficients in minimal polynomial: size of largest Jordan block
- Dimension of eigenspace: number of Jordan blocks
- We can always read off the *characteristic* polynomial from the spectrum.
:::

:::{.concept}
\envlist

- Todo
:::

:::{.solution}
**Proof of (a)**:
Let $A$ be the matrix in the question, and $B$ be the matrix containing 1's in every entry.

- Noting that $B = A+I$, we have
  \[
  &B\vector x = \lambda \vector x \\
  &\iff (A+I) \vector x = \lambda \vector x \\
  &\iff A \vector x = (\lambda - 1) \vector x
  ,\]
    so we will find the eigenvalues of $B$ and subtract one from each.

- Note that $B\vector v = \thevector{\sum v_i, \sum v_i, \cdots, \sum v_i}$, i.e. it has the effect of summing all of the entries of $\vector v$ and placing that sum in each component.

- We proceed by finding $p$ eigenvectors and eigenvalues, since the JCF and minimal polynomials will involve eigenvalues and the transformation matrix will involve (generalized) eigenvectors.

:::{.claim title="1"}
Each vector of the form $\vector p_i \definedas \vector e_1 - \vector e_{i+1} = \thevector{1, 0, 0,\cdots, 0 -1, 0, \cdots, 0 }$ where $i\neq j$ is also an eigenvector with eigenvalues $\lambda_0 = 0$, and this gives $p-1$ linearly independent vectors spanning the eigenspace $E_{\lambda_0}$
:::

:::{.claim title="2"}
$\vector v_1 = \thevector{1, 1, \cdots, 1}$ is an eigenvector with eigenvalue $\lambda_1 = p$.
:::

- Using that the eigenvalues of $A$ are $1+\lambda_i$ for $\lambda_i$ the above eigenvalues for $B$,
\[
\spec(B) \definedas \theset{(\lambda_i, m_i)} &=  \theset{(p, 1), (0, p-1)}  \implies \chi_{B}(x) = (x-p)x^{p-1} \\ 
\implies \spec(A) &= \theset{(p-1,1), (-1, p-1) }  \implies \chi_{A}(x) = (x- p+1)(x+1)^{p-1} \\
\]

- The dimensions of eigenspaces are preserved, thus
\[
JCF_\QQ(A)
=  J_{p-1}^{1} \oplus (p-1)J_{-1}^1
=
\left[\begin{array}{r|r|r|r|r|r}
p-1 & 0 & 0 & \cdots & 0 & 0 \\
\hline
0& -1 & 0 & 0 & 0 & 0 \\ \hline
0& 0 & -1 & 0 & 0 & 0 \\ \hline
0& 0 & 0 & \ddots & \ddots & 0 \\ \hline
0& 0 & 0 & \cdots & -1 & 0 \\ \hline
0& 0 & 0 & \cdots & 0 & -1 \\
\end{array}\right]
.\]

- The matrix $P$ such that $A = PJP\inv$ will have columns the bases of the generalized eigenspaces.
- In this case, the generalized eigenspaces are the usual eigenspaces, so
\[
P = [\vector v_1, \vector p_1, \cdots, \vector p_{p-1}] =
\left[\begin{array}{rrrrrr}
1 & 1 & 1 & 1 & 1 & 1  \\
1 & -1 & 0 & 0 & 0 & 0 \\
1 & 0 & -1 & 0 & 0 & 0 \\
1 & 0 & 0 & -1 & 0 & 0 \\
1 & \vdots & \vdots & \vdots & \ddots & \vdots\\
1 & 0 & 0 & 0 & 0 & -1 \\
\end{array}\right]
.\]

:::{.proof title="of claim 1"}
\envlist

- Compute $$B \vector p_i = \thevector{ 1 + 0 + \cdots + 0 + (-1) + 0 + \cdots + 0} = \thevector{0, 0, \cdots, 0}$$
- So every $\vector p_i \in \ker(B)$, so they are eigenvectors with eigenvalue 0.
- Since the first component is fixed and we have $p-1$ choices for where to place a $-1$, this yields $p-1$ possibilities for $\vector p_i$
- These are linearly independent since the $(p-1)\times (p-1)$ matrix $\thevector{ \vector p_1^t, \cdots, \vector p_{p-1}^t}$ satisfies
\[
\det 
\begin{bmatrix}
1 & 1 & 1 & \cdots & 1\\
-1 & 0  & 0 & \cdots & 0\\
0 & -1  & 0 & \cdots & 0\\
0 & 0 & -1 & \cdots & 0\\
\vdots & \vdots  & \vdots & \ddots & \vdots \\
0 & 0  & 0 & \cdots & -1\\
\end{bmatrix}
&= (1) \cdot \det 
\begin{bmatrix}
-1 & 0  & 0 & \cdots & 0\\
0 & -1  & 0 & \cdots & 0\\
0 & 0 & -1 & \cdots & 0\\
\vdots & \vdots  & \vdots & \ddots & \vdots \\
0 & 0  & 0 & \cdots & -1\\
\end{bmatrix}
\\
&= (-1)^{p-2} \neq 0
.\]

where the first equality follows from expanding along the first row and noting this is the first minor, and every other minor contains a row of zeros.

:::

:::{.proof title="of claim 2"}
\envlist

- Compute $$B\vector v = \thevector{\sum_{i=1}^p 1, \sum_{i=1}^p 1, \cdots, \sum_{i=1}^p 1} = \thevector{p, p, \cdots, p} = p \thevector{1, 1, \cdots, 1} = p\vector{v}_1,$$ thus $\lambda_1 = p$
- $\dim E_{\lambda_1} = 1$ since the eigenspaces are orthogonal and $E_{\lambda_0} \oplus E_{\lambda_1} \leq F^p$ is a subspace, so $p > \dim(E_{\lambda_0}) + \dim E_{\lambda_1} = p-1 + \dim E_{\lambda_1}$ and it isn't zero dimensional.

:::

**Proof of (b)**:

For $F = \FF_p$, all eigenvalues/vectors still lie in $\FF_p$, but now $-1 = p-1$, making $(x-(p-1))(x+1)^{p-1} = (x+1)(x+1)^{p-1}$, so $\chi_{A, \FF_p}(x) = (x+1)^p$, and the Jordan blocks may merge.

- A computation shows that $(A+I)^2 = pA = 0 \in M_p(\FF_p)$ and $(A+I) \neq 0$, so $\min_{A, \FF_p}(x) = (x+1)^2$.
  - Thus the largest Jordan block corresponding to $\lambda = -1$ is of size 2
- Can check that $\det(A) = \pm 1 \in \FF_p\units$, so the vectors $\vector e_1 - \vector e_i$ are still linearly independent and thus $\dim E_{-1} = p-1$
  - So there are $p-1$ Jordan blocks for $\lambda = 0$.

Summary:
\[
\min_{A, \FF_p}(x) &= (x+1)^2 \\
\chi_{A, \FF_p}(x) &\equiv (x+1)^p \\
\dim E_{-1} &= p-1
.\]

Thus
\[
JCF_{\FF_p}(A)
=  J_{-1}^{2} \oplus (p-2)J_{-1}^1
= \left[\begin{array}{rr|r|r|r|r}
-1 & 1 & 0 & \cdots & 0 & 0 \\
0& -1 & 0 & 0 & 0 & 0 \\
\hline
0& 0 & -1 & 0 & 0 & 0 \\ \hline
0& 0 & 0 & \ddots & \ddots & 0 \\ \hline
0& 0 & 0 & \cdots & -1 & 0 \\ \hline
0& 0 & 0 & \cdots & 0 & -1 \\
\end{array}\right]
.\]

To obtain a basis for $E_{\lambda = 0}$, first note that the matrix $P = [\vector v_1, \vector p_1, \cdots , \vector p_{p-1}]$ from part (a) is singular over $\FF_p$, since
\[
\vector v_1 + \vector p_1 + \vector p_2 + \cdots + \vector p_{p-2}
&= [p-1, 0, 0, \cdots, 0, 1] \\
&= [-1, 0,0,\cdots, 0, 1] \\
&= - \vector p_{p-1}
.\]

We still have a linearly independent set given by the first $p-1$ columns of $P$, so we can extend this to a basis by finding one linearly independent generalized eigenvector.

Solving $(A-I\lambda)\vector x = \vector v_1$ is our only option (the others won't yield solutions).
This amounts to solving $B\vector x = \vector v_1$, which imposes the condition $\sum x_i = 1$, so we can choose $\vector x = [1, 0, \cdots, 0]$.

Thus
\[
P = [\vector v_1, \vector x, \vector p_1, \cdots, \vector p_{p-2}] =
\left[\begin{array}{rrrrrr}
1 & 1 & 1 & 1 & 1 & 1  \\
1 & 0 & -1 & 0 & 0 & 0 \\
1 & 0 & 0 & -1 & 0 & 0 \\
1 & \vdots & \vdots & \vdots & \ddots & \vdots \\
1 & 0 & 0 & 0 & 0 & -1\\
1 & 0 & 0 & 0 & 0 & 0 \\
\end{array}\right]
.\]

:::

## Spring 2018 #4 #algebra/qual/work
Let
\[
A=\left[\begin{array}{lll}{0} & {1} & {-2} \\ {1} & {1} & {-3} \\ {1} & {2} & {-4}\end{array}\right] \in M_{3}(\mathbb{C})
\]

a. 
Find the Jordan canonical form $J$ of $A$.

b.
Find an invertible matrix $P$ such that $P\inv AP = J$. 

> You should not need to compute $P\inv$.

## Spring 2017 #6 #algebra/qual/work
Let $A$ be an $n\times n$ matrix with all entries equal to $0$ except for the $n-1$ entries just above the diagonal being equal to 2.

a.
What is the Jordan canonical form of $A$, viewed as a matrix in $M_n(\CC)$?

b.
Find a nonzero matrix $P\in M_n(\CC)$ such that $P\inv A P$ is in Jordan canonical form.

## Spring 2016 #1 #algebra/qual/work
Let
\[
A=\left(\begin{array}{ccc}
-3 & 3 & -2 \\
-7 & 6 & -3 \\
1 & -1 & 2
\end{array}\right) \in M_{3}(\mathrm{C})
.\]

a.
Find the Jordan canonical form $J$ of $A$.

b.
Find an invertible matrix $P$ such that $P\inv A P = J$.
You do not need to compute $P\inv$.

## Spring 2015 #6 #algebra/qual/completed

:::{.problem title="?"}
Let $F$ be a field and $n$ a positive integer, and consider
\[
A=\left[\begin{array}{ccc}
1 & \dots & 1 \\
& \ddots & \\
1 & \dots & 1
\end{array}\right] \in M_{n}(F)
.\]

Show that $A$ has a Jordan normal form over $F$ and find it.

> Hint: treat the cases $n\cdot  1 \neq 0$ in $F$ and $n\cdot 1 = 0$ in $F$ separately.

:::

:::{.solution}
Note that if $\vector x = \tv{x_1,\cdots, x_n}$ then $A\vector x = \tv{\sum x_i, \sum x_i, \cdots, \sum x_i}$, so $A$ acts by summing the entries in $\vector x$ and setting every coordinate to that sum.
By inspection (or clever guessing), we can find eigenvalues and eigenvectors:

- $\lambda = 0$ and:
  - $\vector v_1 = \tv{1,0,0,\cdots,0, -1}$ 
  - $\vector v_2 = \tv{0,1,0,\cdots,0, -1}$
  - $\vector v_3 = \tv{0,0,1,\cdots,0, -1}$
  - $\cdots$
  - $\vector v_{n-1} = \tv{0,0,0,\cdots,1, -1}$
- $\lambda = n$ and $\vector v_n = \tv{1,1,\cdots, 1}$

Note that for $\lambda = n$, we have $A \tv{1,1,\cdots, 1} = \tv{n\cdot 1,\cdots, n\cdot 1}$.
So for $n\cdot 1\neq 0$, there are two eigenspaces corresponding to $\lambda = 0, n$, and if $n\cdot 1 = 0$ these collapse to just a single eigenspace for $\lambda = 0$.

Assuming $n\cdot 1\neq 0$, we get a characteristic polynomial of $(x-n)x^{n-1}$.
The $x-n$ factor corresponds to a single $1\times 1$ Jordan block with diagonal $n$.
For the $x^{n-1}$ factor, we've produced $n-1$ distinct eigenvectors, so we get $n-1$ Jordan blocks of size $1\times 1$ with diagonal zero.
Thus
\[
\JCF(A) =
\left[
\begin{array}{c|c|c|c|c}
n & \cdot & \cdot & \cdot & \cdot \\ \hline
\cdot & 0 & \cdot & \cdot & \cdot \\ \hline
\cdot & \cdot & 0 & \ddots & \cdot \\ \hline
\cdot & \cdot & \cdot & \ddots & \cdot \\ \hline
\cdot & \cdot & \cdot & \cdot & 0 
\end{array}
\right]
.\]
One can verify this by checking directly that the minimal polynomial of $A$ is $p(x) = (x-n)x$, so the size of the largest Jordan block for $\lambda = n$ is 1 and for $\lambda = 0$ is $n-1$, while the characteristic polynomial is $(x-n)x^{n-1}$, so the sum of the sizes of Jordan blocks for $\lambda = n$ is 1 and for $\lambda = 0$ is $n-1$, forcing the $1\times 1$ blocks everywhere.

Now consider the case when $n\cdot 1 = 0$; then $\vector v_n$ becomes an eigenvector for $\lambda = 0$ instead of $\lambda = n$.
The minimal polynomial becomes $(x-0)x = x^2$ and the characteristic polynomial becomes $x^n$, so $\lambda = 0$ has:

- The size of the largest Jordan block is 2,
- The sum of sizes of Jordan blocks is $n-1$,

and so this forces one block of size $2\times 2$ and $n-2$ blocks of size $1\times 1$.
So we now have:
\[
\JCF(A) = 
\left[
\begin{array}{cc|c|c|c}
0 & 1 & \cdot & \cdot & \cdot \\
\cdot & 0 & 0 & \cdot & \cdot \\ \hline
\cdot & \cdot & 0 & \ddots & \cdot \\ \hline
\cdot & \cdot & \cdot & \ddots & 0 \\ \hline
\cdot & \cdot & \cdot & \cdot & 0 
\end{array}
\right]
.\]



:::

## Fall 2014 #5 #algebra/qual/work
Let $T$ be a $5\times 5$ complex matrix with characteristic polynomial $\chi(x) = (x-3)^5$ and minimal polynomial $m(x) = (x-3)^2$.
Determine all possible Jordan forms of $T$.

## Spring 2013 #5 #algebra/qual/work
Let $T: V\to V$ be a linear map from a 5-dimensional $\CC\dash$vector space to itself and suppose $f(T) = 0$ where $f(x) = x^2 + 2x + 1$.

a.
Show that there does not exist any vector $v\in V$ such that $Tv = v$, but there *does* exist a vector $w\in V$ such that $T^2 w= w$.

b.
Give all of the possible Jordan canonical forms of $T$.

## Spring 2021 #1 #algebra/qual/completed

Let m
\[
A \da 
\begin{bmatrix}
4 & 1 & -1 \\
-6 & -1 & 2 \\
2 & 1 & 1
\end{bmatrix}
\in \Mat(3\times 3, \CC)
.\]

a. 
Find the Jordan canonical form $J$ of $A$.

b. 
Find an invertible matrix $P$ such that $J = P \inv A P$.

c. 
Write down the minimal polynomial of $A$.

> You should not need to compute $P\inv$

:::{.concept}
\envlist

- $\chi_A(t) = t^n - \tr\qty{\Extpower^1 A}t^{n-1} + \tr\qty{\Extpower^2 A}t^{n-2} - \cdots \pm \det(A)$
- Finding generalized eigenvectors: let $B = A-\lambda I$, get eigenvector $v$, solve $Bw_1 = v, Bw_2 = w_1, \cdots$ to get a Jordan block. 
  Repeat with any other usual eigenvectors.
- Convention: construct Jordan blocks in decreasing order of magnitude of eigenvalues.
- Polynomial exponent data:
  - Minimal polynomial exponents: sizes of **largest** Jordan blocks.
  - Characteristic polynomial exponents: **sum of sizes** of Jordan blocks, i.e. how many times $\lambda$ is on the diagonal of $\JCF(A)$.

:::

:::{.solution}
\envlist

:::{.proof title="parts a and b"}
\envlist

- Write $\chi_A(t) = t^3 - T_1 t^2 + T_2 t - T_3$ where $T_i \da \tr\qty{\Extpower^i A}$:
  - $T_1 = \tr(A) = 4-1+1=4$.
  - $T_2 = (-1-2) + (4+2) + (-4-6) = 5$.
  - $T_3 = \det(A) = 4(-1-2) -1(-10) + (-1)(-6+2) = 2$.
- So $\chi_A(t) = t^3 - 4t^2 + 5t-2$.
- Try rational roots test: $r \in \ts{\pm 2/1}$, and check that 2 is root.
- By polynomial long division, $\chi_A(t) / (t-2) = t^2-2t+1 = (t-1)^2$.
- So the eigenvalues are $\lambda = 2, 1$.
- $\lambda = 2$:
  - Set $U\da A-\lambda I$, then find $\RREF(U)$ to compute its kernel:
  \[
  U \da
  \begin{bmatrix}
  2 & 1 & -1
  \\
  -6 & -3 & 2
  \\
  2 & 1 & -1
  \end{bmatrix}
  \leadsto
  \begin{bmatrix}
  2 & 1 & 0
  \\
  0 & 0 & 1
  \\
  0 & 0 & 0
  \end{bmatrix}
  ,\]
  which yields $v_1 = [1,-2,0]$.

- $\lambda = 2$:
  - Similarly,
  \[
  U \da 
  \begin{bmatrix}
  3 & 1 & -1 \\
  -6 & -2 & 2 \\
  2 & 1 & 0
  \end{bmatrix}
  \leadsto  
  \begin{bmatrix}
  1 & 0 & -1
  \\
  0 & 1 & 2
  \\
  0 & 0 & 0
  \end{bmatrix}
  ,\]
  which yields $v_2 = [1,-2,1]$.

  - Solve $Uw = v_3$:
  \[
  \begin{bmatrix}
  3 & 1 & -1 & 1 \\
  -6 & -2 & 2 & -2 \\
  2 & 1 & 0 & 1
  \end{bmatrix}
  \leadsto
  \begin{bmatrix}
  1 & 0 & -1 & 0 \\
  0 & 1 & 2 & 1 \\
  0 & 0 & 0 & 0
  \end{bmatrix}
  ,\]
  so take $v_3 = [0,1,0]$.

- Putting things together:
\[
A &= P\inv J P \text{ where } \\
J = J_1(\lambda = 2) \oplus J_2(\lambda = 1) 
&=
\begin{bmatrix}
2 & 0 & 0
\\
0 & 1 & 1
\\
0 & 0 & 1
\end{bmatrix} \\
P = [v_1, v_2, v_3] 
&= 
\begin{bmatrix}
1 & 1 & 0
\\
-2 & -2 & 1
\\
0 & 1 & 0
\end{bmatrix}
.\]

:::

:::{.proof title="part c"}
\envlist

- Write $\min_A(t) = (t-2)(t-1)^{\ell_1}$, then since $\min_A(t)$ divides $\chi_A(t)$ either $\ell_1 = 1, 2$.
- $\ell_1$ is the size of the **largest** block corresponding to $\lambda = 1$, which is size 2, so $\lambda_1=2$.
- Thus 
\[
\min_A(t) = (t-2)(t-1)^2
.\]

:::

:::


## Fall 2020 #5 #algebra/qual/work

Consider the following matrix:
\[
B \da 
\begin{bmatrix}
1 & 3 & 3
\\
2 & 2 & 3
\\
-1 & -2 & -2
\end{bmatrix}
.\]

a. Find the minimal polynomial of $B$.

b. Find a $3\times 3$ matrix $J$ in Jordan canonical form such that $B = JPJ\inv$ where $P$ is an invertible matrix.



