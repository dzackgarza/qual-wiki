# Picard

:::{.theorem title="Picard's big theorem"}
If $f$ is meromorphic on a punctured neighborhood $\ts{0 \leq \abs{z-z_0} < \delta}$ and $f$ omits 3 values at $z_0$, then $f$ extends meromorphically over $z_0$.
:::

:::{.theorem title="Picard's little theorem"}
If $f$ is nonconstant and entire, it takes on every value in $\CC$ with at most one exception.
Equivalently, if $f$ omits 2 finite values, $f$ is constant.
:::



:::{.exercise title="?"}
Show that $\sin(z) = z$ has infinitely many solutions in $\CC$.

#completed

:::


:::{.solution}
Let $f(z) = \sin(z)-z$ and apply Big Picard: $f$ takes on every value in $\CC$, except possibly for some single $z_0$, infinitely many times.
So there is at most one $z_0$ such that there are *finitely* many solutions to $\sin(z) - z = z_0$.
Since $z_0+2\pi \neq z_0$, there must then be infinitely many solutions to $f(z) = z_0 + 2\pi$.
But then
\[
f(z+2\pi) = \sin(z+2\pi) - z - 2\pi = \sin(z) - z - 2\pi = (z_0 + 2\pi)-2\pi = z_0
\]
has infinitely many solutions, a contradiction.

:::



