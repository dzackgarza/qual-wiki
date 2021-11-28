
---
order: 115
---

# Complex Log

:::{.fact title="Complex Log"}
For $z= r e^{i\theta}\neq 0$, $\theta$ is of the form $\Theta + 2k\pi$ where $\Theta = \Arg z$
We define
\[
\log(z) = \ln\qty{\abs{z}} + i\Arg(z)
\]
and $z^c \da e^{c\log(z)}$.
Thus
\[
\log(re^{i\theta}) = \ln \abs{r} + i\theta
.\]
:::

![[Pasted image 20211127210218.png]]

:::{.fact}
Common trick:
\[
f^{1/n} = e^{{1\over n} \log(f)}
,\]
taking (say) a principal branch of $\log$ given by $\CC \sm (-\infty, 0] \cross 0$.
:::

:::{.proposition title="Existence of complex log"}
Suppose $\Omega$ is a simply-connected region such that $1\in \Omega, 0\not\in\Omega$.
Then there exists a branch of $F(z) \da \Log(z)$ such that

- $F$ is holomorphic on $\Omega$,
- $e^{F(z)} = z$ for all $z\in \Omega$
- $F(x) = \log(x)$ for $x\in \RR$ in a neighborhood of $1$.

:::

:::{.definition title="Principal branch and exponential"}
Take $\CC$ and delete $\RR^{\leq 0}$ to obtain the **principal branch** of the logarithm. 
Equivalently, this is define for all $z=re^{i\theta}$ where $\theta \in (-\pi, \pi)$.

Here the log is defined as 
\[
\Log(z) \da \log(r) + i\theta && \abs{\theta} < \pi
.\]
Similarly define
\[
z^{\alpha} \da e^{\alpha \Log(z)}
.\]

The principal branch of $\Log$ is defined so that $\Log(1) = 0$, and can be written as $\Log(z) = \int_\gamma {1\over \xi} \dxi$ where $\gamma$ is any piecewise smooth path connecting 1 to $z$.
This yields the usual $\Log(re^{i\theta}) = \log(\abs{r}) + i\theta$.

:::

:::{.warnings}
It's tempting to define
\[
z^{1\over n} \da (re^{i\theta})^{1\over n} = r^{1\over n} e^{i\theta \over n}
,\]
but this requires a branch cut to ensure continuity.

:::

:::{.warnings}
\[
\Log(zw) &\neq \Log(z) + \Log(w) \\
\Log(e^z) &\neq z
.\]

For counterexamples, take $z=\zeta_4^3=\exp(3\pi i / 4$ and $w=\zeta_4^2 = \eexp(\pi i/2)$.
Then $zw= \exp(-3 \pi i /4)$, using that the domain of $\Arg$ is $(-\pi, \pi]$.
:::

:::{.remark}
Note the problem: for $z\da x+i0 \in \RR^{\leq 0}$, just above the axis consider $z_+ \da x + i\eps$ and $z_- \da x-i\eps$.
Then

- $\log(z_+) = \log\abs{x} + i\pi$, and
- $\log(z_-) = \log\abs{x} - i\pi$.

So $\log$ can't even be made continuous if one crosses the branch.
The issue is the **branch point** or **branch singularity** at $z=0$.
:::

:::{.theorem title="Existence of log of a function"}
If $f$ is holomorphic and nonvanishing on a simply-connected region $\Omega$, then there exists a holomorphic $G$ on $\Omega$ such that

\[
f(z) = e^{G(z)}
.\]

:::

:::{.fact}
The complex exponential is $2\pi i$ periodic, and invertible on any horizontal strip of the form
\[
S_\alpha \da \ts{z\in \CC \st \Im(z) \in [\alpha, \alpha+2\pi] }
.\]
:::


:::{.example title="of branch cuts"}
Generally choose branch cuts that are slits between branch points to prevent monodromy around those points.
One can find branch points for $\log(f(z))$ by noting that $\log$ should be a primitive of $\dd{}{z}\log(f(z))$.

- $\log(z^2-1)$ has branch points at $z=\pm 1,\ infty$.
  To see $\infty$ is a branch point: by differentiating, the log should be a primitive of ${2z\over z^2-1}$.
  Taking a large curve, each term contributes $2\pi i$ with the same sign, so the value jumps.

  So a cut like $(-\infty, +1]$ works, and an explicit formula may be obtained by taking:

  - $\log(z+1) + \log(z-1) = (r_1 + i\theta_1) + (r_2 + i\theta_2)$.

- $\log\qty{z+1\over z-1}$: needs to be a primitive for ${1\over z+1} + {1\over z-1}$, so $\pm 1$ are branch points.
  $z=\infty$ is **not** a branch point, because integrating over a large curve yields $+2\pi i - 2\pi i = 0$, so no monodromy.

  - So a cut like $[-1, 1]$ works, with a formula $\log(z+1) - \log(z-1) = (r_1 + i\theta_1) - (r_2 + i\theta_2)$.

:::

