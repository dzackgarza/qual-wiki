:::{.remark title="Reminder of notation"}
For a group $G$ acting on a set $X$,

| Notation                                                                                  | Definition          |
|-------------------------------------------------------------------------------------------|---------------------|
| \( \OO(x) = Gx = \theset{g\cdot x \suchthat g\in G} \subseteq X \)                        | Orbit               |
| \(\Stab(x) = G_x = \ts{ g \in G \st g\cdot x=x } \leq G \)                                | Stabilizer          |
| \( X/G \subseteq 2^X \)                                                                   | Set of Orbits       |
| \( \Fix = X^G = \theset{x\in X \suchthat g\cdot x = x\, \forall g\in G} \subseteq X \) | Set of Fixed Points |

Note that being in the same orbit is an equivalence relation which partitions $X$, and $G$ acts transitively if restricted to any single orbit.
Also, $x\in \Fix$ iff $\Orb(x) = \ts{x}$ and $\Stab_G(x) = G$.
:::

:::{.fact}
For any group action, the kernel is the intersection of all stabilizers:
\[
\ker \psi = \Intersect_{x\in X} G_x
.\]

:::


