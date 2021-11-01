# Diagonalizability

:::{.remark}
*Notation:*
$A^{\dagger}$ denotes the conjugate transpose of $A$.

:::

:::{.lemma title="?"}
Let $V$ be a vector space over $k$ an algebraically closed and $A \in \mathrm{End}(V)$.
Then if $W \subseteq V$ is an invariant subspace, so $A(W) \subseteq W$, the $A$ has an eigenvector in $W$.
:::

:::{.theorem title="The Spectral Theorem"}
\envlist

1. Hermitian (self-adjoint) matrices (i.e. $A^{\dagger} = A$) are diagonalizable over $\CC$.
2. Symmetric matrices (i.e. $A^t = A$) are diagonalizable over $\RR$.

:::

:::{.remark}
In fact, $A$ is symmetric $\iff \spec A$ forms an orthonormal basis.
:::

:::{.proof title="of spectral theorem"}
\envlist

- Suppose $A$ is Hermitian.
- Since $V$ itself is an invariant subspace, $A$ has an eigenvector $\vector v_1 \in V$.
- Let $W_1 = \spanof_k\theset{\vector v_1}\perp$.
- Then for any $\vector w_1 \in W_1$, 
$$
\inner{\vector v_1}{ A \vector w_1} =
\inner{A \vector v_1}{\vector w_1} =
\lambda \inner{\vector v_1}{\vector w_1} = 0,
$$
so $A(W_1) \subseteq W_1$ is an invariant subspace, etc.

- Suppose now that $A$ is symmetric.
- Then there is an eigenvector of norm 1, $\vector v \in V$.
\[
\lambda = \lambda\inner{\vector v}{\vector v} = \inner{A\vector v}{\vector v} = \inner{\vector v}{A\vector v} = \overline{\lambda} \implies \lambda \in \RR
.\]

:::

:::{.proposition title="Simultaneous Diagonalizability"}
A set of operators $\theset{A_i}$ pairwise commute $\iff$ they are all simultaneously diagonalizable.
:::

:::{.proof title="?"}
By induction on number of operators

- $A_n$ is diagonalizable, so $V = \bigoplus E_i$ a sum of eigenspaces
- Restrict all $n-1$ operators $A$ to $E_n$.
- The commute in $V$ so they commute in $E_n$
- **(Lemma)** They were diagonalizable in $V$, so they're diagonalizable in $E_n$
- So they're simultaneously diagonalizable by I.H.
- But these eigenvectors for the $A_i$ are all in $E_n$, so they're eigenvectors for $A_n$ too.
- Can do this for each eigenspace.

> [Full details here](https://kconrad.math.uconn.edu/blurbs/linmultialg/minpolyandappns.pdf#page=9)

:::

:::{.theorem title="Characterizations of Diagonalizability"}
$M$ is diagonalizable over $\FF \iff \min_M(x, \FF)$ splits into distinct linear factors over $\FF$, or equivalently iff all of the roots of $\min_M$ lie in $\FF$.
:::

:::{.proof title="?"}
$\implies$:
If $\min_A$ factors into linear factors, so does each invariant factor, so every elementary divisor is linear and $JCF(A)$ is diagonal.

$\impliedby$:
If $A$ is diagonalizable, every elementary divisor is linear, so every invariant factor factors into linear pieces. 
But the minimal polynomial is just the largest invariant factor.
:::


