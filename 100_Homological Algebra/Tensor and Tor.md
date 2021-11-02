## Tensor and Tor


:::{.proposition title="Basic Properties of the Tensor Product"}
\envlist

- $A\tensor_R \wait$ is:
  - Covariant
  - Right-exact
  - Left-exact
  - Has left-derived functors $\Ext^i_R(A, B) \da L_i \Hom_R(\wait, B)(A)$ computed using *projective* resolutions.


- $\wait\tensor_R B$ is:
  - Covariant
  - Right-exact
  - Has left-derived functors $\Ext^i_R(A, B) \da L_i \Hom_R(\wait, B)(A)$ computed using *projective* resolutions.

- Tensor commutes with colimits: $(\colim A_i)\tensor_R M = \colim (A_i \tensor_R M)$.

:::


:::{.proposition title="Basic Properties of Tor"}
\envlist 

- $\Tor_n^R(A, B) = 0$ for either $A$ or $B$ flat.
:::


:::{.fact}
The most useful SES for proofs here:
\[
0 \to \ZZ \mapsvia{n} \ZZ \mapsvia{\pi} \ZZ/n \to 0
.\]

:::

:::{.proposition title="Common Tensor Products"}
\envlist

- $\ZZ/n \tensor_\ZZ G \cong G/nG$
- $\ZZ/n \tensor_\ZZ \ZZ/m \cong \ZZ/d$.
- $\QQ\tensor_\ZZ \ZZ/n \cong 0$.


:::

:::{.proposition title="Common Tor Groups"}

- $\Tor^\ZZ_1(\ZZ/n, G) \cong \ts{ h\in H \st nh = e }$
- $\Tor^\ZZ_1(\ZZ/n, \QQ) \cong 0$.
- $\Tor^\ZZ_1(\ZZ/n, \ZZ/m) \cong \ZZ/d$.

:::