::: {.remark .proofenv title="Reminder of notation"}
For a group $G$ acting on a set $X$,

<table>
<colgroup>
<col style="width: 81%" />
<col style="width: 18%" />
</colgroup>
<thead>
<tr class="header">
<th>Notation</th>
<th>Definition</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span class="math inline">$\OO(x) = Gx = \theset{g\cdot x \suchthat g\in G} \subseteq X$</span></td>
<td>Orbit</td>
</tr>
<tr class="even">
<td><span class="math inline">$\Stab(x) = G_x = \ts{ g \in G \st g\cdot x=x } \leq G$</span></td>
<td>Stabilizer</td>
</tr>
<tr class="odd">
<td><span class="math inline"><em>X</em>/<em>G</em> ⊆ 2<sup><em>X</em></sup></span></td>
<td>Set of Orbits</td>
</tr>
<tr class="even">
<td><span class="math inline">$\Fix = X^G = \theset{x\in X \suchthat g\cdot x = x\, \forall g\in G} \subseteq X$</span></td>
<td>Set of Fixed Points</td>
</tr>
</tbody>
</table>

Note that being in the same orbit is an equivalence relation which
partitions $X$, and $G$ acts transitively if restricted to any single
orbit. Also, $x\in \Fix$ iff $\Orb(x) = \ts{x}$ and $\Stab_G(x) = G$.
:::

::: {.fact .proofenv}
For any group action, the kernel is the intersection of all stabilizers:
$$
\ker \psi = \Intersect_{x\in X} G_x
.$$
:::
