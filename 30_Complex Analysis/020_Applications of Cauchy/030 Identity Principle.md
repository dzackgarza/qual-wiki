# The Identity/Continuation Principle

:::{.theorem title="Continuation Principle / Identity Theorem"}
If $f$ is holomorphic on a bounded connected domain $\Omega$ and there exists a sequence $\theset{z_i}$ with a **limit point** in $\Omega$ such that $f(z_i) = 0$, then $f\equiv 0$ on $\Omega$.
:::

Recall that a point $x$ is a limit point of a set $S$ if every punctured neighborhood of $x$ contains a point of $S$, and any infinite subset of a compact set contains a limit point.

:::{.slogan}
Two functions agreeing on a set with a limit point are equal on a domain.
:::

:::{.proof title="?"}
![[attachments/Pasted image 20211215021255.png]]
:::

:::{.exercise title="?"}

![figures/image_2021-05-17-11-53-33.png](figures/image_2021-05-17-11-53-33.png)

:::

:::{.exercise title="Rudin 10.2"}
Let $f$ be entire and for every $a\in \CC$, and write the Laurent expansion about $a$ as $f(z) = \sum_{k\geq 0} c_{k, a} (z-a)^k$.
Suppose that for every $a$, there exists some $k$ such that $c_{k, a} = 0$.
Show that $f$ is a polynomial.

#completed

:::

:::{.solution}
\envlist

- Claim: $f^{(n)} = 0$ for some $n$.
- Collect all of these bad points up into $Z_n \da \ts{a\in \CC \st c_{n, a} = 0}$ and write $Z = \Union_n Z_n$.
  Note that $f^{(n)}(z) = 0$ on $Z_n$.
- By hypothesis, $Z = \CC$, so not every $Z_n$ can be countable.
  Pick any $Z_n$ which is uncountable.

- Write $Z_n = \Union_{m} Z_{m, n}$ where $Z_{m, n} \da \DD_m(0) \intersect Z_n$ as a union of increasing discs, then not every $Z_{m, n}$ can be finite, so pick an infinite one.
- Now $Z_{m, n}$ has a limit point since $\DD_m(0)$ forms a complete totally bounded metric space, and $f^{(n)}(z) = 0$ on $Z_{m, n}$, so by the identity principle $f^{(n)}(z) = 0$ on $\CC$.
:::




