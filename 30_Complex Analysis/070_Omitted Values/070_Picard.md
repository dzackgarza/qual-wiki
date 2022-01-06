# Picard

:::{.theorem title="Picard's big theorem"}
If $f$ is meromorphic on a punctured neighborhood $\ts{0 \leq \abs{z-z_0} < \delta}$ and $f$ omits 3 values at $z_0$, then $f$ extends meromorphically over $z_0$.
:::

:::{.theorem title="Picard's little theorem"}
If $f$ is nonconstant and entire, it takes on every value in $\CC$ with at most one exception.
Equivalently, if $f$ omits 2 finite values, $f$ is constant.
:::

:::{.proof title="Liouville and uniformization"}
Wlog, suppose the three omitted points are $1,0\infty$ and suppose $f: \CC\to X\da \CP^1\sm\ts{1,0\infty}$ is holomorphic.
The universal cover of $X$ is $\HH$, so $f$ lifts to a holomorphic map to $\HH$.
Under the Cayley map, we can obtain a holomorphic map $f:\CC\to \DD$.
This makes $f$ a bounded entire function, and thus constant by Liouville.
:::


## Exercise

:::{.exercise title="?"}
Show that $\sin(z) = z$ has infinitely many solutions in $\CC$.

#complex/exercise/completed

:::

:::{.solution}
Let $f(z) = \sin(z)-z$ and apply Big Picard: $f$ takes on every value in $\CC$, except possibly for some single $z_0$, infinitely many times.
So there is at most one $z_0$ such that there are *finitely* many solutions to $\sin(z) - z = z_0$.
If $z_0\neq 0$, we're done, so suppose such an exception $z_0$ does exist whose fiber has finitely many points.
Since $z_0+2\pi \neq z_0$, there must then be infinitely many solutions to $f(z) = z_0 + 2\pi$.
But then
\[
f(z+2\pi) = \sin(z+2\pi) - z - 2\pi = \sin(z) - z - 2\pi = (z_0 + 2\pi)-2\pi = z_0
,\]
so we can produce infinitely many points in the fiber over $w_0$, contradicting finiteness. 
So no exception $z_0$ exists, and in particular, $z_0=0$ is not an exception so $f(z) = 0$ has infinitely many solutions.
:::

:::{.exercise title="?"}
Suppose that $g$ is entire and satisfies the functional equation $g(1-z) = 1-g(z)$.
Show that $g(\CC) = \CC$.

#complex/exercise/completed

:::

:::{.solution}
By Picard, $g$ omits at most one value $a$.
Note that $a\neq 1/2$, since $g(a) = g(1/2) = g(1-1/2) = 1-g(1/2) = 1-g(a)$, so $2g(a) = 1$ and $g(a) = 1/2$.
Noting that $1-a\neq a$ for any $a$ other than $1/2$, we have that $w\da 1-a\in g(\CC)$.
Then $g(w) \da g(1-a) = 1-g(a) = 1 - w = 1-(1-a) = a$, so $a\in g(\CC)$ and $g$ omits no values.
:::


