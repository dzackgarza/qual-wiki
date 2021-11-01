# Undergrad Review

:::{.fact title="Undergrad reminders"}
\[
\det M = \prod_{\sigma \in S_n} \eps(\sigma) \prod_{i=1}^n a_{i, \sigma(i)}
.\]

For example,

\[
\operatorname{det}\left(\begin{array}{ccc}
a_{11} & a_{12} & a_{13} \\
a_{21} & a_{22} & a_{23} \\
a_{31} & a_{32} & a_{33}
\end{array}\right)=\begin{gathered}
a_{11} a_{22} a_{33}+a_{12} a_{23} a_{31}+a_{13} a_{21} a_{32} \\
-a_{13} a_{22} a_{31}-a_{12} a_{21} a_{33}-a_{11} a_{23} a_{32}
\end{gathered}
.\]

Let $\minor_A(i, j)$ denote $A$ with the $i$th row, $j$th column deleted.

One can expand determinants along rows:
\[
\det(A) = \sum_{j=1}^n (-1)^{i+j} a_{ij} \det \minor_A(i, j)
.\]


Also useful, a matrix can be inverted by computing the adjugate:
\[
A\inv = {1\over \det A} \operatorname{adj}(A) && \adj(A)_{ij} \da (-1)^{i+j} \det \minor_A(j, i)
.\]

The eigenvalues of an upper-triangular matrix are exactly the diagonal entries, and the determinant is their product.
More generally, the determinant is always the product of the eigenvalues, and the trace is the sum of the eigenvalues, so $\tr(A) = \sum \lambda_i$ and $\det(A) = \prod \lambda_i$.

Matrices can be block-multiplied when all dimensions are compatible:
\[
\begin{bmatrix}
A & B \\
C & D 
\end{bmatrix}
\begin{bmatrix}
E & F \\
G & H 
\end{bmatrix}
= \matt{AE + BG}{AF + BH}{CE + DG}{ CF + DH}
.\]

> Note that if any of these matrix multiplications don't make sense, the results won't be valid!

If $A$ is upper triangular, some entries of $A^k$ can be computed easily:

\[
A\da\left(\begin{array}{ccc}
a_1 & & * \\
& \ddots & \\
0 & & a_n
\end{array}\right)
\implies
A^k = \left(\begin{array}{ccc}
a_1^k & & * \\
& \ddots & \\
0 & & a_n^k
\end{array}\right)
.\]


Traces of products can be commuted: $\trace(AB) = \trace(BA)$, so similar matrices have identical traces since $\trace(PJP\inv) = \trace{PP\inv J} = \trace{J}$.

The coefficients of the characteristic polynomial are elementary symmetric functions in the eigenvalues:
\[
\chi_A(t) = t^n - \qty{\sum_i \lambda_i }t^{n-1} + \qty{\sum_{i < j} \lambda_i \lambda_j }t^{n-2} + \cdots \pm \qty{\prod_i \lambda_i}
.\]
:::

:::{.example title="of polynomial long division"}
Consider $f(x) \da x^3-6x^2+12x-8$, then any rational root is in $\ts{\pm 8, \pm 4, \pm 2, \pm 1}$.
Testing $f(2) = 0$ works, and dividing by $x-2$ yields

![](figures/2021-07-24_18-32-38.png)

The rest can be factored by inspection:
\[
f(x) = (x-2)(x^2-4x+4) = (x-2)^3
.\]
:::


