
# Cauchy's Inequality

:::{.theorem title="Cauchy's Inequality / Cauchy's Estimate" ref="CauchyInequality"}
For $z_0 \in D_R(z_0) \subset \Omega$, setting $M \da \sup_{z\in \gamma}\abs{f(z)}$ so $\abs{f(z)}\leq M$ on $\gamma$
\[
\abs{ f^{(n)} (z_0) } 
\leq \frac{n !}{2 \pi} \int_{0}^{2 \pi} \frac{ M } {R^{n+1}} R \dtheta
= \frac{M n ! }{R^n} 
.\]
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


:::{.slogan}
The $n$th Taylor coefficient of an analytic function is at most $\sup_{\abs z = R} \abs{f}/R^n$.
:::

