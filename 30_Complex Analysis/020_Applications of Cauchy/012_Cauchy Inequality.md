# Cauchy's Inequality

:::{.theorem title="Cauchy's Inequality / Cauchy's Estimate" ref="CauchyInequality"}
For $z_0 \in D_R(z_0) \subset \Omega$, setting $M \da \sup_{z\in \gamma}\abs{f(z)}$ so $\abs{f(z)}\leq M$ on $\gamma$
\[
\abs{ f^{(n)} (z_0) } 
\leq \frac{n !}{2 \pi} \int_{0}^{2 \pi} \frac{ M } {R^{n+1}} R \dtheta
= \frac{M n ! }{R^n} 
.\]
:::

:::{.slogan}
The $n$th Taylor coefficient of an analytic function is at most $\sup_{\abs z = R} \abs{f}/R^n$.
:::

:::{.proof title="of Cauchy's inequality"}
\envlist
- Given $z_0\in \Omega$, pick the largest disc $D_R(z_0) \subset \Omega$ and let $C = \bd D_R$.
- Then apply the integral formula.

\[
\left|f^{(n)}(z_0)\right|
&= \abs{ \frac{n !}{2 \pi i} \int_{C} \frac{f(\zeta) }{(\zeta-z_0)^{n+1}} \dzeta } \\
&=\left|\frac{n !}{2 \pi i} \int_{0}^{2 \pi} \frac{f\left(z_0 + r e^{i \theta}\right) r i e^{i \theta} }{\left(r e^{i \theta}\right)^{n+1}} \dtheta \right| \\
&\leq \frac{n !}{2 \pi} \int_{0}^{2 \pi}\left|\frac{f\left( z_0 +r e^{i \theta}\right) r i e^{i \theta}}{\left(r e^{i \theta}\right)^{n+1}}\right| \dtheta \\ 
&=\frac{n !}{2 \pi} \int_{0}^{2 \pi} \frac{\left|f\left(z_0 +r e^{i \theta}\right)\right|}{r^{n}} \dtheta \\
&\leq \frac{n !}{2 \pi} \int_{0}^{2 \pi} \frac{M}{r^{n}} \dtheta \\
&=\frac{M n !}{r^{n}} 
.\]

:::



:::{.exercise title="?"}
Show that if $f$ is entire and $\abs{f(z)} \in \bigo(\abs{z}^p)$ for $\abs{z}$ sufficiently large, then $f$ is a polynomial of degree at most $\floor{p}$.

#completed

:::

:::{.solution}
The basic idea:
\[
\abs{c_k} 
&\leq {k!\over 2\pi}\int_{\abs{z} = R} \abs{f(\xi) \over (\xi - 0)^{k+1}}\dxi\\
&\leq {k! \over 2\pi}\int_{\abs z = R}{ \abs{\xi}^{p} \over \abs{\xi}^{k+1} }\dxi \\
&= {k! \over 2\pi}\int_{\abs z = R} {1\over \abs{R}^{k+1-p}} \dxi\\
&= {k! \over 2\pi} {1\over \abs{R}^{k+1-p}} \cdot 2\pi R \\
&= \bigo(1/R^{k-p})
,\]
which converges to $0$ as $R\to \infty$ provided that $k-p>0$, so $k>p$.
So any coefficient $c_k$ for $k\geq \floor{p}$ vanishes.
:::


