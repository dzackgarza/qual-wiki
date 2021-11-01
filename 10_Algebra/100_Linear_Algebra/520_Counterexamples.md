# Matrix Counterexamples

:::{.example title="?"}
A matrix that:

- Is not diagonalizable over $\RR$ but diagonalizable over $\CC$

- Has *no* eigenvalues over $\RR$ but has *distinct* eigenvalues over $\CC$

- $\min_M(x) = \chi_M(x) = x^2 + 1$

\[
M = \left(\begin{array}{rr}
0  & 1 \\
-1 & 0
\end{array}\right) \sim
\left(\begin{array}{r|r}
-1 \sqrt{-1} & 0 \\
\hline
0 & 1 \sqrt{-1}
\end{array}
\right)
.\]

:::

:::{.example title="?"}
A matrix that:

- Is not diagonalizable over $\CC$,

- Has eigenvalues $[1, 1]$ (repeated, multiplicity 2)

- $\min_M(x) = \chi_M(x) = x^2-2x+1$

\[
M = \left(\begin{array}{rr}
1 & 1 \\
0 & 1
\end{array}\right) 
\sim
\left(
\begin{array}{rr}
1 & 1 \\
0 & 1
\end{array}
\right)
.\]

:::

:::{.example title="?"}
Non-similar matrices with the same characteristic polynomial
\[
\left(\begin{array}{ll}
{0}  & {0} \\
{0} & {0}
\end{array}\right)
\text { and }
\left(\begin{array}{ll}
{0} & {0} \\
{0} & {0}
\end{array}\right)
\]
Here $\chi_A(x) = \chi_B(x) = x^2$, but they are not conjugate since their JCFs differ (note that they're already in JCF!)
:::

:::{.example title="?"}
A full-rank matrix that is not diagonalizable:
\[
\left(
\begin{array}{ccc}
1 & 1 & 0 \\
0 & 1 & 1 \\
0 & 0 & 1 \\
\end{array}
\right)
.\]

:::

:::{.example title="?"}
Matrix roots of unity, i.e. representations of $i$:
\[
M_1 
\da
\matt 0 {-1} 1 0 \quad
M_2
\da 
\matt 0 1 {-1} 0
.\]
:::

