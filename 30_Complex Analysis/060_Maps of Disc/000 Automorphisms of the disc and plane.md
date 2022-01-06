# Maps of the Disc

:::{.theorem title="Automorphisms of the disc"}
What are the automorphisms of $\DD, \CC, \CP^1$?
For the disc, it's known:
\[
\Aut_\CC(\DD) = \ts{ z\mapsto e^{i\theta} \qty{\alpha - z \over 1 - \bar{\alpha} z} }
.\]
:::

:::{.proof title="?"}
Schwarz lemma.
:::

:::{.theorem title="Automorphisms of the half-plane"}
\[
\Aut_\CC(\HH) = \ts{ z \mapsto {az+b \over cz+d} \st a,b,c,d\in \CC, ad-bc=1 } \cong\PSL_2(\RR)
.\]
:::

## Exercises

:::{.exercise title="Automorphisms of $\CC$"}
Show that $\Aut(\CC) = \ts{ z \mapsto az+b\st a\in \CC\units, b\in \CC }$.

#complex/exercise/completed

:::

:::{.solution}
$\supseteq$:
Clear, every affine function is bijective with inverse $g(z) \da a\inv(z-b)$, and holomorphic since
\[
g(f(z)) = z \implies g'(f(z)) f'(z) = 1 \implies g'(w) = {1\over f'(f\inv(w))}
.\]

$\subseteq$:
Suppose $f$ is entire and bijective.
If $f$ is bounded, then $f(z) = b$ is constant by Liouville and we're done, so suppose not.
Then $\abs{f(z)}\to \infty$ as $\abs{z}\to \infty$, making $z=\infty$ either an essential singularity or a pole, since it is isolated and not removable since $f$ is unbounded in every small enough neighborhood of $\infty$.
If $f(b) = 0$ without loss of generality we can translate to assume $f(0) = 0$ by replacing $f(z)$ with $f(z) - b$.
By bijectivity, $z=0$ must be a zero of order 1, so ${1\over f(z)}$ has a pole of order 1 at $z=0$.
So define $G(z) \da {z\over f(z)}$, which is now an entire function.

On a large enough disc, $\abs{f(z)} > 1$ for all $\abs{z} > R$, so $\abs{G(z)} < 1R\inv$ on $\abs{z} > R$.
Since $G$ is holomorphic and thus continuous on $\abs{z}\leq R$, which is compact, $G$ is bounded here too.
Thus $G$ is constant by Liouville, and $G(z) = c \implies f(z) = c\inv z \da az$.
Unwinding the initial translation that ensured $f(0)=0$, we get $f(z) = az + b$.
:::

:::{.exercise title="Automorphisms of $\CP^1$"}
Show that $\Aut(\CP^1) = \ts{{az+b\over cz+d} \st ad-bc\neq 0}$.

#complex/exercise/completed

:::

:::{.solution}
Write $I(z) \da {1\over z}$ and note that
\[
{az+b\over cz+d} = {a \over c} + {bc-ad\over c}{1\over cz+d} = (z\mapsto cz+d)\circ\qty{ z \mapsto {1\over z} }\circ\qty{{ a\over c} + {bc-ad\over c} z}
,\]
which is $I$ composed with affine transformations.
Note that the last map satisfies
\[
\dd{}{z} {bc-ad \over c} z + {a\over c} = {bc-ad\over c}
,\]
which is nonzero (making the map conformal) precisely when $bd-ad\neq 0$.

$\supseteq$:
All LFTs are bijective, since if $f$ is an LFT then $f = A_1 \circ I \circ A_2$ with the $A_i$ affine and invertible, and $I(z)$ is invertible on $\CP^1$, so $f\inv = A_2\inv \circ I\inv \circ A_1\inv$.
Noting that the $A_i$ are conformal, if $I$ is conformal then by the chain rule $f'\neq 0$.
That $I$ is conformal on $\CP^1$: this clearly holds away from $z=0$ and $z=\infty$.
Now use that $I\qty{1\over w} = w$ is conformal at zero, and ${1\over I(z)}$ is conformal at $\infty$.

$\subseteq$:
Suppose $f\in \Aut(\CP^1)$.
If $f(\infty) = \infty$, then the claim is that $f$ must be affine.
Define $F(z) \da {1\over f(1/z)}$ satisfies $F(0) = 0$, and $F$ is conformal at zero since it is a composition of $f$ and $I$.
So $F(0) = 0$ but $F'(0) \neq 0$, making zero a pole of $F$ of order one.
So $f$ has a pole of order 1 at $\infty$, and by injectivity, $f\inv(\infty) = \ts{\infty}$ has a single element.
Now $G(z) \da {f(z) - f(0) \over z}$ is bounded on $\CC$ and thus constant, so $f(z) - f(0) = cz \implies f(z) = cz + f(0)$.

If $f(\infty) = w < \infty$, consider $F(z) \da {1\over z-w}$.
By inspection, $F$ is an LFT, and $G(z) \da {1\over f(z) - w} = (F\circ f)(z)$ is an automorphisms of $\CP^1$ satisfying $G(\infty) = \infty$.
By the previous case, $G$ is affine, so 
\[
G(z) = az + b \implies {1\over f(z) - w} = az + b \implies f(z) = {1\over az + b } + w = {waz + wb\over az+b }
,\]
which is visibly an LFT.
:::


