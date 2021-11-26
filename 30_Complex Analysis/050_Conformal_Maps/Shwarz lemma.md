# Schwarz Lemma

#todo

\todo[inline]{Montel's theorem}

\todo[inline]{Normal families}

\todo[inline]{Equicontinuity}

:::{.theorem title="Schwarz Lemma" ref="SchwarzzLemma"}
If $f: \DD \to \DD$ is holomorphic with $f(0) = 0$, then

1. $\abs{f(z)} \leq \abs z$ for all $z\in \DD$
2. $\abs{f'(0)} \leq 1$.

Moreover, if 

- $\abs{f(z_0)} = \abs{z_0}$ for any $z_0\in \DD$, or 
- $\abs{f'(0)} = 1$, 

then $f$ is a rotation.
:::

![[figures/2021-10-29_02-32-14.png]]

:::{.proof title="?"}
\envlist

- Idea: apply the maximum modulus principle to $g(z) \da f(z)/z$.
- $\abs{g(z)} \leq 1$:
  - Expand $f$ at $z=0$ as $\sum_{k\geq 0} c_k z^k$.
    Since $f(0) = c_0$, we have $c_0 = 0$.
  - So $g(z) \da f(z)/z$ is holomorphic on $\DD$, since the singularity at $z=0$ is removable.
  - Set $\abs{z} = r < 1$, then $\abs{g(z)} = \abs{f(z)}/r \leq 1/r$ since $\abs{f(z)} \leq 1$.
  - By MMP, $\abs{g(z)} \leq 1/r$ holds in the entire disc $\abs{z} \leq r$, so take $r\to 1$ to get $\abs{g(z)} \leq 1$
- $\abs{f'(0)} \leq 1$ with equality iff $f$ is a rotation:
  - Note that $f(0) = 0$, so we can write $g(0) = \lim_{z\to 0} {f(z) - f(0) \over z-0} \da f'(0)$.
  - So $1 = \abs{f'(0)} = \abs{g(0)}$.
  - But $\abs{g(z)} \leq 1$ on $\DD$ and $g(z) = 1$ in the interior, so by MMP this makes $g$ constant.
  - So again $f(z) = cz$ with $\abs{c} = 1$.
- $\abs{f(z_0)} = \abs{z_0}\implies f$ is a rotation:
  - Again $\abs{g(z)} \leq 1$, but $\abs{f(z_0)} = \abs{z_0} \implies \abs{g(z_0)} = 1$, so $g$ attains a maximum on $\abs{z}\leq 1$, making it constant, so $f(z) = cz$.
  - Then $\abs{z_0} = \abs{f(z_0)} = \abs{cz_0}$ since $f(z_0) = z_0$, so $\abs{c} = 1$ and $c = e^{i\theta}$ for some $\theta$.

:::

# Exercises


:::{.exercise title="?"}
Show that if $f: \Delta\to\Delta$ is a biholomorphism with $f(0) = 0$ then $f$ is a rotation.
:::


:::{.solution}
Apply Schwarz, which says $\abs{f(z)} \leq \abs{z}$ with equality $\iff g$ is a rotation, so it suffices to show that this is an equality.
Write $f(z) = w$, then
\[
\abs{z} = \abs{(h\circ f)(z)} = \abs{h(w)} \leq \abs{w} = \abs{f(z)}\leq \abs{z}
.\]
:::


