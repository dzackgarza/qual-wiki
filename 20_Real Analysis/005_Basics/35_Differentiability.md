---
order: 35
---

# Differentiability

:::{.theorem title="Mean Value Theorem"}
If $f: [a, b] \to \RR$ is continuous on a closed interval and differentiable on $(a, b)$, then there exists $\xi \in [a, b]$ such that 
\[
f(b) - f(a) = f'(\xi)(b-a)
.\]
:::

:::{.proposition title="Lipschitz $\iff$ differentiable with bounded derivative."}
A function $f: (a, b) \to \RR$ is Lipschitz $\iff f$ is differentiable and $f'$ is bounded.
In this case, $\abs{f'(x)} \leq C$, the Lipschitz constant.
:::

:::{.theorem title="Term by Term Differentiability Theorem"}
If $f_n$ are differentiable, $\sum f_n' \to g$ uniformly, and there exists one point[^pointwise_works_too] $x_0$ such that $\sum f_n(x)$ converges, then there exist an $f$ such that $\sum f_n \to f$ uniformly and $f' = g$.[^theorem_referfence_6.4.3_Abbott]

[^theorem_referfence_6.4.3_Abbott]: See Abbott theorem 6.4.3, pp 168.

[^pointwise_works_too]: So this implicitly holds if $f$ is the pointwise limit of $f_n$.

:::


:::{.example title="Derivatives of bounded functions need not be bounded"}
\[
f(x) \da 
\begin{cases}
x^2 \sin\qty{1\over x^2} &  x\neq 0
\\
0 & x=0.
\end{cases}
.\]

Note that
\[
f'(x) = 2x\sin\qty{1\over x^2 } - \qty{2\over x}\cos\qty{1\over x^2} \chi_{x\neq 0}
,\]
now take the sequence $x_n \da ((2n+1)\pi)^{-1\over 2}$.


:::

