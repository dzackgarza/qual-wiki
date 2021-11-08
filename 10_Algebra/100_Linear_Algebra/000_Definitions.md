# Definitions

:::{.remark}
The main powerhouse: for $T:V\to V$ a linear transformation for $V\in\Vect_k$, map to $V\in \modsleft{k[x]}$ by letting polynomials act via $p(x)\cdot \vector v \da p(T)(\vector v)$.
Using that $k[x]$ is a PID iff $k$ is a field, and we can apply the FTFGMPID to get two decompositions:
\[
V &\cong \bigoplus_{i=1}^n k[x]/ \gens{ q_i(x) } && q_{i}(x) \divides q_{i+1}(x) \divides \cdots  \\
V &\cong \bigoplus _{j=1}^m k[x] / \gens{ p_i(x)^{e_i} } && \text{ with } p_i \text{ not necessarily distinct.} 
\]

- The $q_i$ are the **invariant factors** of $T$
  - $q_i$ is the minimal polynomial of $T$ restricted to $V_i \da k[x] / \gens{ q_i(x) }$. 
  - The largest invariant factor $q_n$ is the **minimal polynomial** of $T$.
  - The product $\prod_{i=1}^n q_i(x)$ is the **characteristic polynomial** of $T$.
- The $p_i$ are the **elementary divisors** of $T$.
  - Todo: what can you read off of this...?

:::

:::{.definition title="Nondegenerate Bilinear Form"}
#todo
:::

:::{.definition title="Quadratic Form"}
#todo

:::

:::{.definition title="Gram Matrix"}
#todo

:::

:::{.definition title="Normal Matrix"}
A matrix $A\in \Mat(n\times n; \CC)$ is **normal** iff $A^{\dagger} A = AA^{\dagger}$ where $A^{\dagger}$ is the conjugate transpose.
:::

:::{.definition title="Semisimple"}
A matrix $A$ over $k$ is **semisimple** iff $A$ is diagonalizable over $k^\alg$, the algebraic closure.
:::

:::{.definition title="Nilpotent"}
A matrix $A$ over $k$ is **nilpotent** iff $A^k = 0$ for some $k\geq 1$.

> Idea: upper triangular matrices.

:::

:::{.definition title="Unipotent"}
A element $A$ in a ring $R$ is **unipotent** iff $A-1$ is nilpotent.

> Idea: an upper-triangular matrix with ones on the diagonal.

:::

:::{.proposition title="Triangular Decomposition"}
Any linear map $T:V\to V$ over a perfect field decomposes as $T = S + N$ with $S$ semisimple (diagonal), $N$ nilpotent, and $[DN] = 0$.
If $T$ is invertible, then $T$ decomposes as $T = SU$ where $S$ is semisimple, $U$ is unipotent, and $[UN] = 0$.
:::

:::{.proposition title="Perp of sum is intersection of perps"}
\[
\qty{ \sum  W_i}^\perp = \Intersect \qty{W_i^\perp}
.\]
:::

:::{.definition title="Similar Matrices"}
Two matrices $A,B$ are **similar** (i.e. $A = PBP\inv$) $\iff A,B$ have the same Jordan Canonical Form (JCF).
:::

:::{.definition title="Equivalent Matrices"}
Two matrices $A, B$ are **equivalent** (i.e. $A = PBQ$) $\iff$

- They have the same rank,

- They have the same invariant factors, *and*

- They have the same (JCF)

:::

## Notation

:::{.remark}
Some definitions:

- $A^t$ is the usual transpose.
- $A^{\dagger}$ is the conjugate transpose.
- A matrix is $A^{\dagger}$ is **adjoint** to $A$ iff $\inner{A\vector x}{\vector y} = \inner{\vector x}{A^{\dagger} \vector y}$.
  - $A$ is **self-adjoint** iff $A$ is an adjoint for itself, so $\inner{A\vector x}{\vector y} = \inner{\vector x}{A \vector y}$.
- $A$ is **symmetric** iff $A = A^t$.
  - $A$ is **orthogonal** iff $A^tA = AA^t = I$
- $A$ is **Hermitian** iff $A^{\dagger} = A$.
  - $A$ is **normal** iff $AA^{\dagger} = A^{\dagger} A$.
  - $A$ is **unitary** iff $A^{\dagger}A = AA^{\dagger} = I$.
:::

