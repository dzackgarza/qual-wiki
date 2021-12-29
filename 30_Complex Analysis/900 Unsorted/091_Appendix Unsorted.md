# Appendix

:::{.theorem title="Uniformization"}
Every Riemann surface $S$ is the quotient of a free proper holomorphic action of a group $G$ on the universal cover $\tilde S$ of $S$, so $S\cong \tilde S/G$ is a biholomorphism.
Moreover, $\tilde S$ is biholomorphic to either 

- $\CP^1$
- $\CC$
- $\DD$

:::

:::{.exercise title="Using algebraic topology"}
Show that there is no continuous square root function defined on all of $\CC$.

#complex/completed/exercise

:::

:::{.solution}
Suppose $f(z)^2 = z$. 
Then $f$ is a section to the covering map
\[
p: \CC\units &\to \CC\units \\
z & \mapsto z^2
,\]
so $p\circ f = \id$.
Using $\pi_1(\CC\units) = \ZZ$, the induced maps are $p_*(1) = 2$ and $f_*(1) = n$ for some $n\in \ZZ$.
But then $p_* \circ f_*$ is multiplication by $2n$, contradicting $p_* \circ f_* = \id$ by functoriality.
:::

