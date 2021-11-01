# Polynomials in Linear Algebra

## Using Canonical Forms

:::{.lemma title="?"}
The characteristic polynomial is the *product of the invariant factors*, i.e.
$$
\chi_A(x) = \prod_{j=1}^n f_j(x)
.$$
:::

:::{.lemma title="?"}
The minimal polynomial of $A$ is the *invariant factor of highest degree*, i.e.
$$
\min_A(x) = f_n(x)
.$$
:::

:::{.proposition title="?"}
For a linear operator on a vector space of nonzero finite dimension, TFAE:

- The minimal polynomial is equal to the characteristic polynomial.

- The list of invariant factors has length one.

- The Rational Canonical Form has a single block.

- The operator has a matrix similar to a companion matrix.

- There exists a *cyclic vector* $\vector v$ such that $\spanof_k\theset{T^j \vector v \suchthat j = 1, 2, \cdots} = V.$

- $T$ has $\dim V$ distinct eigenvalues

:::


## Minimal / Characteristic Polynomials

:::{.proposition title="Useful computational trick"}
A trick for finding characteristic polynomials:
\[
\chi_A(t) &= \sum_{k=0}^n (-1)^k \trace\qty{\Extpower^k A} t^{n-k} \\
&= t^n - \trace\qty{A} t^{n-1} + \trace\qty{\Extpower^2 A}t^{n-2} - \cdots \pm \trace\qty{\Extpower^{n-1} A} t \mp \det(A)
,\]
using that 

\[
{\Extpower^0 A} \da 1 \\
{\Extpower^1 A} \da A \\
\trace\qty{\Extpower^n A} = \det(A)
.\]

Moreover, the intermediate traces are easy to compute by hand:
\[
\trace\qty{\Extpower^\ell A} = \sum \det\qty{M^{\ell}}
,\]
where the sum is taken over all $\ell\times\ell$ **principal minors**: determinants of the $n \choose \ell$ principal matrices which are obtained by choosing $\ell$ diagonal entries to keep and and deleting the rows and columns for every entry not chosen.
Equivalently, one can select $n-\ell$ diagonal entries and delete the corresponding row/column for each. 


:::{.example title="?"}

![](figures/2021-07-24_19-48-11.png)

:::


To factor this polynomial, the **rational roots test** can be useful: for $f(t) = a_nt^n + \cdots + a_1 t + a_0$, rational roots are of the form $p/q$ where $p \divides a_n$ and $q\divides a_0$.
Note that this simplifies greatly for $f$ monic!
Once you have a root, apply **polynomial long division** to get a smaller problem, and hopefully this continues to work until it's factored.
:::

:::{.remark}
Fix some notation:
\[
\min_A(x): \quad & \text{The minimal polynomial of } A \\
\chi_A(x): \quad & \text{The characteristic polynomial of } A
.\]

:::

:::{.definition title="Minimal polynomial"}
The **minimal polynomial** of a linear map $T$ is the unique monic polynomial $\min_T(x)$ of minimal degree such that $\min_T(T) = 0$.
:::

:::{.definition title="Characteristic polynomial"}
The **characteristic polynomial** of $A$ is given by
$$
\chi_A(x) = \det(A - xI))= \det(SNF(A - xI))
.$$

:::

:::{.fact}
If $A$ is upper triangular, then $\det(A) = \prod_{i} a_{ii}$
:::

:::{.theorem title="Cayley-Hamilton"}
The minimal polynomial divides the characteristic polynomial, and in particular $\chi_A(A) = 0$.
:::

:::{.proof title="?"}
By minimality, $\min_A$ divides $\chi_A$. 
Every $\lambda_i$ is a root of $\min_A(x)$: 
Let $(\vector v_i, \lambda_i)$ be a nontrivial eigenpair. 
Then by linearity,
$$
\min_A(\lambda_i)\vector v_i = \min_A(A)\vector v_i = \vector 0
,$$ 
which forces $\min_A(\lambda_i) = 0$.
:::

## Finding Minimal Polynomials

:::{.proposition title="How to find the minimal polynomial"}
Let $m(x)$ denote the minimal polynomial $A$.

1. Find the characteristic polynomial $\chi(x)$; this annihilates $A$ by Cayley-Hamilton. Then $m(x) \divides \chi(x)$, so just test the finitely many products of irreducible factors.

2. Pick any $\vector v$ and compute $T\vector v, T^2\vector v, \cdots T^k\vector v$ until a linear dependence is introduced. Write this as $p(T) = 0$; then $\min_A(x) \divides p(x)$.

:::



