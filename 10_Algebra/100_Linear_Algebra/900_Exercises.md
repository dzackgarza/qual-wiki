# Exercises

:::{.exercise title="?"}
Show that normal matrices are diagonalizable.
:::

:::{.exercise title="?"}
Consider the Vandermonde matrix:
\[
A \da 
\left(\begin{array}{ccc}
1 & \cdots & 1 \\
\lambda_{1} & \cdots & \lambda_{k} \\
\vdots & & \vdots \\
\lambda_{1}^{k-1} & \cdots & \lambda_{k}^{k-1}
\end{array}\right)
.\]

Show that
\[
\det A = \prod_{i < j} (\lambda_i - \lambda_j)
.\]
:::

:::{.exercise title="?"}
Show that a nonzero nilpotent matrix $A$ is not diagonalizable over any field.
Some useful facts:

- $\spec A = \ts{0}$, since $Ax=\lambda x \implies A^n=\lambda^nx$, so $A^n=0$ forces $\lambda =0$.
  This forces $\JCF(A)$ to be strictly upper-triangular.
- $\min_A(x) = x^n$.
- If $A$ were diagonalizable, $\JCF(A) = 0$.

:::

:::{.exercise title="?"}
Prove Cayley-Hamilton in the following way.
Let $V = \spanof\ts{\vector v_1, \cdots, \vector v_n}$ and define the $i$th flag as $\Fil_i V \da \spanof\ts{\vector v_1, \cdots, \vector v_i}$ for all $1\leq i \leq n$, and set $\Fil_0 V \da \ts{0}$.
Show that if if $A$ is upper triangular, then $A(\Fil_i V) \subseteq \Fil_i V$.
Now supposing $\vector v_i$ are eigenvectors for $\lambda_i$, show that
\[
(A-\lambda_n I) \Fil_n V &\subseteq \Fil_{n-1} V \\
(A-\lambda_{n-1} I) (A-\lambda_n I ) \Fil_n V &\subseteq \Fil_{n-2} V \\
&\vdots \\
\prod_i (A-\lambda_{n-i} I) \Fil_n V &\subseteq \Fil_0 V = \ts{0}
.\]
Conclude that $\chi_A(A) = 0$.
:::

