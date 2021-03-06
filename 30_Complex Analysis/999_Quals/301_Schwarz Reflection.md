---
order: 301
---

# Schwarz Reflection

## Tie's Extra Questions: Spring 2015 (Reflection for harmonic functions) #complex/exercise/completed

:::{.problem title="?"}
(1) Assume $u$ is harmonic on open set $O$ and $z_n$ is a sequence
in $O$ such that $u(z_n) = 0$ and $\lim z_n \in O$. Prove or
disprove that $u$ is identically zero. What if $O$ is a region?

(2) Assume $u$ is harmonic on open set $O$ and $u(z) = 0$ on a
disc in $O$. Prove or disprove that $u$ is identically zero. What if
$O$ is a region?

(3) Formulate and prove a Schwarz reflection principle for
harmonic functions

> cf. Theorem 5.6 on p.60 of Stein et al.

> Hint: Verify the mean value property for your new function obtained by
Schwarz reflection principle.

:::

:::{.solution}
**Part 1**:
This is not true: take the holomorphic function $f(z) = z$, then $u(z) \da \Re(f(z)) = \Re(z)$ is harmonic on nonzero on $\RR$ but zero on $i\RR$.

**Part 2**:
Set $f \da u_x + i u_y$, then $f$ is holomorphic on $O$.
Since $h\equiv 0$ on $\DD_\eps \subseteq O$, $g\equiv 0$ on this disc.
By the identity principle for holomorphic functions, $g\equiv 0$ on $O$.
So $h_x, h_y \equiv 0$, making $h$ constant, and since $h\equiv 0$ on $U$ this forces $h\equiv 0$ on $O$.

**Part 3**:
Let $u$ be harmonic on $S^+$, a region symmetric about $\RR$, and that $u\equiv 0$ on $\RR \intersect S^+$.
Define $S^- = \ts{\bar{z} \st z\in S^+}$, and
\[
U(z) \da 
\begin{cases}
 U(z) &  z\in S^+
\\
 -U(\bar z) & z\in S^-.
\end{cases}
.\]
Then $U$ is a harmonic extension of $u$ to $S \da S^+ \union (S^+ \intersect \RR) \union S^-$.
To see that $U$ is harmonic on $S$, it suffices to check that $U$ satisfies the mean value property on $S$.
Clearly this holds in $S^+$, so for $z_0\in S^+$ we have
\[
U(z_0) 
&= u(z_0) \\
&= {1\over 2\pi} \int_{-\pi}^\pi u(z_0 + re^{it} )\dt \\
&= {1\over 2\pi} \int_{-\pi}^\pi U(z_0 + re^{it} )\dt \\
.\]
So for $w_0\in S^-$, write it as $w_0 = \bar{z_0}$, then
\[
U(z_0)
&\da -u(\bar{z_0}) \\
&= {1\over 2\pi }\int_{-\pi}^\pi - u\qty{\bar{z_0 + re^{it} }} \dt \\
&= {1\over 2\pi }\int_{-\pi}^\pi - u\qty{\bar{z_0} + re^{-it} } \dt \\
&= {1\over 2\pi }\int_{-\pi}^\pi - u\qty{\bar{z_0 + re^{-it} }} \dt \\
&= {1\over 2\pi }\int_{-\pi}^\pi U(z_0 + re^{it} ) \dt
.\]

:::

## Reflection for the disc #complex/exercise/completed

:::{.problem title="?"}
a. 
State the standard Schwarz reflection principle involving reflection across the real axis.

b. 
Give a linear fractional transformation $T$ mapping $\DD$ to $\HH$.
Let $g(z) = \bar z$, and show
\[  
(T^{-1} \circ g \circ T)(z) = 1/\bar z
.\]

c.
Suppose that $f$ is holomorphic on $\DD$, continuous on $\bar \DD$, and real on $S^1$.
Show that $f$ must be constant.

:::

:::{.solution}
**Part 1**:
Let $\Omega = \Omega^+ \union I \union \Omega^-$ be a region symmetric about $\RR$.
If $f$ is holomorphic on $\Omega^+$ extending continuously to $I$ and real valued on $I$, then $f$ extends to a holomorphic function $F$ on all of $\Omega$ defined on $\Omega^-$ by $F(z) = \bar{f(\bar{z})}$.

**Part 2**:
The map is $T(z) = -i\qty{z+1\over z-1}$ with $T\inv(z) = {z-i\over z+i}$, so
\[
(T\inv \circ g \circ T)(z)
&= T\inv\bar{\qty{-i {z+1\over z-1} }} \\
&= T\inv\qty{i{\bar z + 1 \over \bar z - 1}} \\
&= {i\qty{\bar z + 1 \over \bar z - 1} - i \over i\qty{\bar z + 1 \over \bar z - 1} + i } \\
&= {(\bar z + 1) - (\bar z - 1) \over (\bar z + 1) + (\bar z - 1)} \\
&= {1\over \bar{z}}
.\]


**Part 3**:
Define $h: \HH\to \bar{\HH}$ by $h(z) = (T\circ f\circ T\inv)(z)$.
Under $T\inv: \DD\to \HH$, we have $T(S^1) = \RR$, so $h$ is a holomorphic function on $\HH$ that is continuous and real-valued on $\RR$.
By the reflection principle, defining $H(z) \da \bar{h(\bar z)}$ for $\Im(z) < 0$ yields an entire function $H: \CC\to \CC$
Noting that for $g(z) \da \bar{z}$, $g=g\inv$, we can write
\[
H \da g\inv \circ h \circ = h\inv \circ (T\inv \circ f \circ T)\circ g
.\]
We can then conjugate $H$ by $T$ to get a direct formula in terms of $f$, and unwinding this yields the extension $F:\CC\to \CC$ defined by
\[
F(z) = 
\begin{cases}
f(z) & z\in \DD 
\\
f_-(z) \da {1\over \bar{f\bar{z}}} & z\in \DD^c \\
f(z) = f_i(z) & z\in S^1
\end{cases}
.\]
In particular, $H$ is an entire bounded function and thus constant, making $F$ constant as well and consequently $f$ is constant.
:::

## Spring 2020 HW 2, SS 2.6.15 (Constant on boundary and nonvanishing implies constant, using Schwarz) #complex/exercise/completed

:::{.problem title="?"}
Suppose $f$ is continuous and nonvanishing on $\bar \DD$, and holomorphic in $\DD$.
Prove that if $\abs{z} = 1 \implies \abs{f(z)} = 1$, then $f$ is constant.

> Hint: Extend $f$ to all of $\CC$ by $f(z) = 1/ \bar{f(1/\bar z)}$ for any $\abs{z} > 1$, and argue as in the Schwarz reflection principle.
:::

:::{.solution}
First, note that the Schwarz reflection principle can be applied here: let $T: \DD\to \HH$ be the Cayley map, and consider $\tilde f \da T\circ f \circ T\inv: \HH\to \HH$.
Now $T(S^1) = \RR$, and since $f(z)\in S^1$ when $z\in S^1$, we have $\tilde f(\RR) = \RR$, i.e. this is a real-valued function on $\RR$.
So $\tilde f$ extends holomorphically to $\tilde F:\CC\to CC$, and we can pull this back to a holomorphic extension of $f$.

Extend $f$ to $F:\CC\to \CC$ by $f(z) = 1/\bar{f(1/\bar{z})}$ for $z\in \DD^c$, which generally has poles at the points $1/\bar{z_k}$ for $z_k\in \DD$ zeros of $f$.
Since $f$ is nonvanishing, $F$ has no poles and thus defines an entire function.
By definition of $F$, we have $F(\CC) \subseteq f\qty{\ts{\abs{z} \leq 1}} \union \bar{ f\qty{\ts{\abs{z} \geq 1}}}$, which are both the continuous images of compact sets and thus compact and bounded.
So $F$ is a bounded entire function and thus constant.
:::

