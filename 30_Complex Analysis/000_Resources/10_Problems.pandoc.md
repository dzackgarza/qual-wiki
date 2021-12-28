# Problems (Complex) {#problems-complex heading="Problems (Complex)"}

## Exercises {#exercises heading="Exercises"}

[30_Complex Analysis/010_Basics/999_Basics_Exercises \>
Exercises]{.internal-embed
alt="30_Complex Analysis/010_Basics/999_Basics_Exercises > Exercises"
src="30_Complex Analysis/010_Basics/999_Basics_Exercises.html#Exercises"}

# Exercises: Integrals {#exercises-integrals heading="Exercises: Integrals"}

## Rational Functions {#rational-functions heading="Rational Functions"}

### Superlinear Decay {#superlinear-decay heading="Superlinear Decay"}

:::{.exercise title=\"[$1/x^{4} + 1$]{.math .math-inline .is-loaded},
balancing exponentials\"}\
\[\
\\int\_\\RR {1 \\over x\^4 + 1} = {\\pi \\sqrt{2} \\over 2} = {\\pi
\\over \\sqrt 2}\
.\]

\#completed

:::

:::{.solution}\
The integrand
[$f \in \mathsf{O}\text{\textbackslash qty}\frac{1}{z^{4}} \subseteq \mathsf{O}\text{\textbackslash qty}\frac{1}{z^{1 + \varepsilon}}$]{.math
.math-inline .is-loaded}, so a semicircular contour works.\
Factoring the denominator: find a principal root\
\[\
\\omega\^4 = -1 = e\^{i\\pi} \\implies \\omega = e{i\\pi\\over 4}\
,\]\
so\
\[\
z\^4 + 1 =
(z-\\omega)(z-\\omega\\zeta_4)(z-\\omega\\zeta_4\^2)(z-\\omega\\zeta_4\^3)
\\leadsto {\\pi \\over 4}, {3\\pi \\over 4}, {5\\pi \\over 4}, {7\\pi
\\over 4}\
.\]\
So there are two simple poles in [$\mathbb{H}$]{.math .math-inline
.is-loaded}:

::: {.internal-embed alt="figures/2021-07-29_18-41-05.png" src="figures/2021-07-29_18-41-05.png"}
:::

Write them as [$z_{1} = e^{\frac{i\pi}{4}}$]{.math .math-inline
.is-loaded} and [$z_{2} = e^{\frac{3i\pi}{4}}$]{.math .math-inline
.is-loaded}.\
Computing the residues:\
\[\
\\Res*{z=z_k} f(z)\
&= \\lim*{z\\to z*k} {z-z_k \\over z\^4 + 1} \\\
&\\eqLH \\lim*{z\\to z*k} {1\\over 4z\^3} \\\
&= {4z\^{-3} }\\evalfrom*{z=z*k}\
,\]\
so\
\[\
2\\pi i \\sum \\Res*{z=z_k}\
&= {2\\pi i \\over 4}\\qty{z_1\^{-3} + z_2\^{-3}} \\\
&= {\\pi i \\over 2}\\qty{e\^{-3 i \\pi \\over 4} + e\^{-9 i \\pi \\over
4}} \\\
&= {\\pi i \\over 2}\\qty{e\^{-3 i \\pi \\over 4} + e\^{-i \\pi \\over
4}} \\\
&= {\\pi i \\over 2}\\cdot e\^{-2i\\pi \\over 4}\\qty{e\^{- i \\pi
\\over 4} + e\^{i \\pi \\over 4}} \\\
&= \\pi i, {1\\over i} \\cos\\qty{\\pi \\over 4} \\\
&= {\\pi \\sqrt 2 \\over 2}\
.\]

:::

:::{.exercise title=\"[$1/x^{4} + 1$]{.math .math-inline .is-loaded},
half-line\"}\
\[\
I \\da \\int_0\^\\infty {1\\over x\^4 + 1 }\\dx = {\\pi \\over 2\\sqrt
2}\
.\]

\#completed

:::

:::{.solution title=\"Integrand symmetry\"}\
Note that the function is even, so\
\[\
\\int*{0\^\\infty} f(x) \\dx = {1\\over 2} \\int*\\RR f(x)\\dx =
{1\\over 2} {\\pi \\over \\sqrt 2} = {\\pi \\over 2 \\sqrt 2}\
,\]\
using the solution from a previous problem.\
:::

:::{.solution title=\"Sector\"}\
A sector will work, since there is a symmetry under
[$z \rightarrow \zeta_{4}z$]{.math .math-inline .is-loaded} and
[$f(z) \sim z^{- 4}$]{.math .math-inline .is-loaded}, so the
semicircular piece will vanish.\
Take the contour [$\Gamma$]{.math .math-inline .is-loaded} comprised of

-   [$\gamma_{1}:\left\{ {t + 0i{\ |\ }t \in \lbrack 0,R\rbrack} \right\}$]{.math
    .math-inline .is-loaded},
-   [$C_{R}:\left\{ {Re^{it}{\ |\ }t \in \lbrack 0,\pi/2\rbrack} \right\}$]{.math
    .math-inline .is-loaded},
-   [$\gamma_{2}:\left\{ {0 + it{\ |\ }t \in \lbrack 0,R\rbrack} \right\}$]{.math
    .math-inline .is-loaded},

oriented counter-clockwise.\
Note that
[$z^{4} + 1 = \prod\limits_{k = 0}^{3}(z - \omega\zeta_{4})$]{.math
.math-inline .is-loaded} where [$\omega = e^{\frac{i\pi}{4}}$]{.math
.math-inline .is-loaded} and
[$\zeta_{4} = e^{\frac{2\pi i}{4}} = i$]{.math .math-inline .is-loaded},
so there is only one pole at [$z_{0}{: =}e^{\frac{i\pi}{4}}$]{.math
.math-inline .is-loaded} within this contour.

Computing the symmetry:\
\[\
\\int*{\\gamma_2} f(z) \\dz\
&= \\int_R\^0 {i \\over (ti)\^4 + 1}\\dt \\qquad z=ti,, \\dz = i\\dt \\\
&= -i \\int_0\^R {1\\over t\^4 + 1}\\dt \\\
&= -i \\int*{\\gamma*1} f(z) \\dz\
,\]\
so applying the residue theorem and noting that \$\\int*{C*R}f\\to 0\$,\
\[\
2\\pi \\Res*{z=z*0} f(z) = \\int*\\Gamma f(z) \\dz =
\\qty{\\int*{\\gamma_1} + \\int*{C*R} + \\int*{\\gamma*2}}f \\too (1-i)
I\
.\]\
Computing the residue:\
\[\
\\Res*{z=z*0}f(z)\
&= {1\\over 4z\^3}\\evalfrom*{z= e\^{i\\pi \\over 4}} \\\
&= {1\\over 4}e\^{-3i\\pi \\over 4} \\\
&= {1\\over 4}e\^{5i\\pi \\over 4}\
.\]

Thus\
\[\
I\
&= (1-i)\\inv 2\\pi i \\Res\_{z=z_0} f(z) \\\
&= \\qty{\\bar{1-i} \\over \\abs{1-i}\^2} 2\\pi i \\cdot {1\\over
4}e\^{5i\\pi \\over 4} \\\
&= {1+i \\over 2} {\\pi i \\over 2}e\^{5i\\pi \\over 4} \\\
&= {e\^{i\\pi \\over 4} \\over \\sqrt{2} } {\\pi i \\over 2}e\^{5i\\pi
\\over 4} \\\
&= {\\pi i \\over 2\\sqrt{2}}e\^{6i\\pi \\over 4} \\\
&= {\\pi i \\over 2\\sqrt{2}}(-i) \\\
&= {\\pi \\over 2\\sqrt{2}}\
.\]

:::

:::{.solution title=\"The log trick\"}\
Consider the auxiliary function [$g(z){: =}\log(z)f(z)$]{.math
.math-inline .is-loaded}, and take a keyhole contour:

::: {.internal-embed src="figures/2021-12-23_00-39-57.png"}
:::

Let [$\Gamma$]{.math .math-inline .is-loaded} be the counterclockwise
contour consisting of

-   [$C_{\varepsilon} = \left\{ {\varepsilon e^{it}{\ |\ }t \in \lbrack 0 + \varepsilon,2\pi - \varepsilon\rbrack} \right\}$]{.math
    .math-inline .is-loaded}
-   [$\gamma_{+} = \left\{ {x + i\varepsilon{\ |\ }x \in \lbrack\varepsilon,R\rbrack} \right\}$]{.math
    .math-inline .is-loaded}
-   [$C_{R} = \left\{ {Re^{it}{\ |\ }t \in \lbrack 0 + \varepsilon,2\pi - \varepsilon\rbrack} \right\}$]{.math
    .math-inline .is-loaded}
-   [$\gamma_{-} = \left\{ {x - i\varepsilon{\ |\ }x \in \lbrack\varepsilon,R\rbrack} \right\}$]{.math
    .math-inline .is-loaded}

Computing the symmetry:\
\[\
\\int*{\\gamma*-}{\\log(z) \\over z\^{4} + 1} \\dz\
&= \\int*{R}\^\\eps {\\log(x-i\\eps) \\over (x-i\\eps)\^4 + 1} \\dx
\\qquad z=x-i\\eps, \\dz = \\dx \\\
&\\to - \\int*{\\eps}\^R {\\log(x) + 2\\pi i\\over x\^4 + 1}\\dz \\\
&= -\\int*{\\gamma*+} {\\log(z) \\over z\^4+1}\\dz - 2\\pi
i\\int*{\\gamma*+} {1\\over z\^4+1} \\dz\
,\]\
so\
\[\
\\int*{\\gamma*+} f + \\int*{\\gamma*-}f \\too -2\\pi i I\
.\]\
By the ML estimate, since [$\log(z)/z^{4} \rightarrow 0$]{.math
.math-inline .is-loaded} as
[$\text{\textbackslash abs}z \rightarrow \infty$]{.math .math-inline
.is-loaded}, [$\int_{C_{R}}g(z) \rightarrow 0$]{.math .math-inline
.is-loaded}.\
Similarly, since [$\log(z)/(z^{4} + 1) \rightarrow 0$]{.math
.math-inline .is-loaded} as
[$\text{\textbackslash abs}z \rightarrow 0$]{.math .math-inline
.is-loaded}, [$\int_{C_{\varepsilon}} \rightarrow 0$]{.math .math-inline
.is-loaded}.\
We\'re then left with the sum of residues at
[$e^{\frac{ki\pi}{4}}$]{.math .math-inline .is-loaded} for
[$k = 1,3,5,7$]{.math .math-inline .is-loaded}.\
We have\
\[\
\\Res*{z=z_k} f(z)\
&= {1\\over 4z\^3}\\evalfrom*{z=z*k} \\\
&= {z\\over 4z\^4}\\evalfrom*{z=z*k} \\\
&= - {z\\over 4}\\evalfrom*{z=z*k} \\qquad \\text{ since } z_k\^4 = -1
\\\
&= -{z_k \\over 4}\
,\]\
so\
\[\
\\Res*{z=z_k}g(z) = -{z_k \\over 4}\\log(z_k)\
.\]

Now use that in the limit,\
\[\
2\\pi i \\sum*k \\Res*{z=z*k}g(z)\
&= \\int*\\Gamma g(z) \\dz \\\
&= \\qty{\\int*{\\gamma*+} + \\int*{\\gamma_i}} f \\\
&= -2\\pi i I\
,\]\
so \$I = -\\sum_k \\Res*{z=z_k} g(z)\$.

Being very careful to note that we\'ve chosen a branch of [$\log$]{.math
.math-inline .is-loaded} where [${Arg}(z) \in (0,2\pi)$]{.math
.math-inline .is-loaded} in order to get the signs right,\
\[\
-\\sum_k \\Res(z=z_k) g(z)\
&= {1\\over 4}\\qty{ z_1\\log(z_1) +
z_2\\log(z_2)+z_3\\log(z_3)+z_4\\log(z_4) } \\\
&= {1\\over 4}\\qty{ z_1 {i\\pi \\over 4} + z_2 {3i\\pi \\over 4} + z_3
{5i\\pi \\over 4}+ z_4 {7i\\pi \\over 4} } \\\
&= {i\\pi \\over 16}\\qty{ z_1 + 3z_2 + 5z_3+ 7z_4 } \\\
&= {i\\pi \\over 16}\\qty{ \\omega \\zeta_4\^0 + 3\\omega\\zeta_4\^1 +
5\\omega\\zeta_4\^2+ 7\\omega \\zeta_4\^3 } \\\
&= {i\\pi \\omega \\over 16}\\qty{ 1 + 3i + -5 + -7i } \\\
&= {i\\pi \\omega \\over 16}(-4-4i) \\\
&= -{i\\pi \\omega \\over 4}(1+i) \\\
&= -{i\\pi \\omega \\over 2}{ \\omega \\over \\sqrt{2} } \\\
&= -i\\omega\^2 {\\pi \\over 2 \\sqrt 2} \\\
&= {\\pi \\over 2\\sqrt{2} }\
,\]\
using that
[$\frac{\sqrt{2}}{2}(1 + i) = e^{\frac{i\pi}{4}} = \omega$]{.math
.math-inline .is-loaded} and [$\omega^{2} = i$]{.math .math-inline
.is-loaded}.

:::

:::{.exercise title=\"[$1/(1 + x^{2})^{2}$]{.math .math-inline
.is-loaded}\"}\
\[\
\\int\_\\RR {1 \\over (1+x\^2)\^2} = {\\pi \\over 2}\
.\]

\#completed

:::

:::{.solution}\
Use that [$f(z) \sim 1/z^{4}$]{.math .math-inline .is-loaded}:

::: {.internal-embed alt="figures/2021-07-29_18-40-40.png" src="figures/2021-07-29_18-40-40.png"}
:::

Then\
\[\
\\int*{C_1 + C_R} f = \\int*{C*1} f + \\int*{C*R} f = 2\\pi i
\\Res*{z=i} {1\\over (1+z\^2)\^2}\
.\]

Note [$f$]{.math .math-inline .is-loaded} factors:\
\[\
f(z) = {1 \\over \\qty{(z-i)(z+i)}\^2 }\
,\]\
so [$z = i$]{.math .math-inline .is-loaded} is a pole of order 2.

Compute the residue within the contour:\
\[\
\\Res*{z=i} f(z)\
= \\lim*{z\\to i} \\dd{}{z} {1\\over (z+i)\^2}\
= - {2 \\over (z+i)\^3 }\\evalfrom\_{z=i}\
= - {2\\over (2i)\^3 }\
= {1\\over 4i} = -{i\\over 4}\
.\]

Now solve:\
\[\
2\\pi i \\qty{- {i\\over 4}} = \\int*{C_1}f + \\int*{C*R} f \\da I_R +
\\int*{C*R}f \\implies I_R = {\\pi \\over 4} - \\int*{C_R} f\
.\]

Note
[$I_{R}\overset{R \rightarrow \infty}{\longrightarrow}I{: =}\int_{\mathbb{R}}f$]{.math
.math-inline .is-loaded}, so it suffices to show\
the semicircular error term vanishes as [$R \rightarrow \infty$]{.math
.math-inline .is-loaded}.\
Parameterize
[$C_{R} = \left\{ {z = Re^{it}{\ |\ }t \in \lbrack 0,\pi\rbrack} \right\}$]{.math
.math-inline .is-loaded}, so [$\text{\textbackslash abs}z = R$]{.math
.math-inline .is-loaded} on [$C_{R}$]{.math .math-inline .is-loaded}.\
Letting [$z = e^{it}$]{.math .math-inline .is-loaded},
[$\, dz = iRe^{it}\, dt$]{.math .math-inline .is-loaded},\
\[\
\\abs{\\int*{C_R} f(z) \\dz }\
&= \\abs{\\int*{C*R} {1\\over (1+z\^2)\^2} \\dz } \\\
&\\leq \\int*{C*R}\\abs{ {1\\over (1+z\^2)\^2} } \\dz \\\
&= \\int*{C*R} {1\\over \\abs{1+z\^2}\^2 } \\dz\\\
&\\leq \\int*{C*R} {1\\over \\qty{1 - \\abs{z}\^2 }\^2 } \\dz \\\
&= \\int*{C*R} {1\\over \\qty{1 - R\^2 }\^2 } \\dz \\\
&= {1\\over \\qty{1 - R\^2 }\^2 } \\int*{C_R} \\dz\\\
&= {1\\over \\qty{1 - R\^2 }\^2 } \\cdot \\length(C_R) \\\
&= {1\\over \\qty{1 - R\^2 }\^2 } \\cdot \\qty{1\\over 2}2\\pi R \\\
&= {\\pi R \\over R\^4 + O(R\^3)} \\\
&= \\pi\\qty{ 1 \\over R\^3 + O(R\^2)} \\\
&\\convergesto{R\\to\\infty} 0\
,\]\
where we\'ve used a variant of the triangle inequality:\
\[\
\\abs{a\\pm b} \\geq \\abs{ \\abs{a} - \\abs{b} } \\implies {1\\over
\\abs{a \\pm b}} \\leq {1\\over \\abs{a} - \\abs{b} }\
.\]

:::

:::{.solution title=\"Older solution\"}\
\\envlist

-   Factor [$(1 + z^{2})^{2} = ((z - i)(z + i))^{2}$]{.math .math-inline
    .is-loaded}, so [$f$]{.math .math-inline .is-loaded} has poles at
    [$\pm i$]{.math .math-inline .is-loaded} of order 2.
-   Take a semicircular contour [$\gamma{: =}I_{R} \cup D_{R}$]{.math
    .math-inline .is-loaded}, then
    [$f(z) \approx 1/z^{4} \rightarrow 0$]{.math .math-inline
    .is-loaded} for large [$R$]{.math .math-inline .is-loaded} and
    [$\int_{D_{R}}f \rightarrow 0$]{.math .math-inline .is-loaded}.
-   Note [$\int_{I_{R}}f \rightarrow \int_{\mathbb{R}}f$]{.math
    .math-inline .is-loaded}, so
    [$\int_{\gamma}f \rightarrow \int_{\mathbb{R}}f$]{.math .math-inline
    .is-loaded}.
-   [$\int_{\gamma}f = 2\pi i\sum\limits_{z_{0}}{Res}_{z = z_{0}}f$]{.math
    .math-inline .is-loaded}, and [$z_{0} = i$]{.math .math-inline
    .is-loaded} is the only pole in this region.
-   Compute\
    \[\
    \\Res*{z=i} f\
    &= \\lim*{z\\to i} {1\\over (2-1)!} \\dd{}{z} (z-i)\^2 f(z) \\\
    &= \\lim*{z\\to i} \\dd{}{z} {1\\over (z+i)\^2 } \\\
    &= \\lim*{z\\to i} {-2 \\over (z+i)\^3 } \\\
    &= -{2 \\over (2i)\^3 } \\\
    &= {1\\over 4i} \\ \\\
    \\implies\
    \\int\_\\gamma f &= {2\\pi i \\over 4i} = \\pi/2\
    ,\]

:::

:::{.exercise title=\"[$1/(1 + x^{2})^{n + 1}$]{.math .math-inline
.is-loaded} \"}

\[\
I \\da \\int\_{-\\infty}\^{\\infty} \\frac{d
x}{\\left(1+x\^{2}\\right)\^{n+1}}=\\frac{(2 n) !}{4\^{n}(n !)\^{2}}
\\pi .\
\]

Note that this solution can be written many ways:\
\[\
I = {2n \\choose n} {\\pi \\over 4\^n}\
= {\\falling{2n}{n} \\over n!} {\\pi \\over 4\^n}\
= {(2n)(2n-1)\\cdots(n+1)\\over n!} {\\pi \\over 4\^n}\
.\]

\#completed

:::

:::{.solution}\
The integrand is
[$f \in \mathsf{O}\text{\textbackslash qty}\frac{1}{z^{2n + 2}} \subseteq \mathsf{O}\text{\textbackslash qty}\frac{1}{z^{1 + \varepsilon}}$]{.math
.math-inline .is-loaded}, so a semicircular contour will work:

::: {.internal-embed alt="Semicircular contour" src="figures/2021-12-23_18-05-57.png"}
:::

Thus\
\[\
I\
&= 2\\pi i \\sum*{z_k \\in \\HH} \\Res*{z=z*k} {1\\over (1+z\^2)\^{n+1}}
\\\
&= 2\\pi i \\Res*{z=i} {1\\over (z+i)\^{n+1}(z-i)\^{n+1} } \\\
&= 2\\pi i \\lim*{z\\to i}{1\\over n!}\\qty{\\dd{}{z}}\^n
(z+i)\^{-(n+1)} \\\
&= 2\\pi i \\lim*{z\\to i}{1\\over n!}\\qty{\\dd{}{z}}\^{n-1}
-(n+1)(z+i)\^{-(n+2)} \\\
&= 2\\pi i \\lim*{z\\to i}{1\\over n!}\\qty{\\dd{}{z}}\^{n-2} -(n+1)
\\cdot -(n+2) (z+i)\^{-(n+3)} \\\
&= \\qquad \\vdots \\\
&= 2\\pi i \\lim*{z\\to i}{1\\over n!}\\qty{\\dd{}{z}}\^{n-k} (-1)\^k
(n+1)(n+2)\\cdots(n+k) (z+i)\^{-(n+k-1)} \\\
&= \\qquad \\vdots \\\
&= 2\\pi i \\lim\_{z\\to i} {1 \\over n!}(-1)\^n
(n+1)(n+2)\\cdots(2n)(z+i)\^{-(2n-1)} \\\
&= { \\falling{2n}{n} \\over n!} 2\\pi i (-1)\^n (2i)\^{-(2n-1)} \\\
&= { \\falling{2n}{n} \\over n!} 2\\pi i (-1)\^n {1\\over 2\^{2n+1}
i\^{2n+1}} \\\
&= { \\falling{2n}{n} \\over n!} \\pi (-1)\^n {1\\over 4\^n i\^{2n}} \\\
&= { \\falling{2n}{n} \\over n!} \\pi (-1)\^n {1\\over 4\^n (-1)\^n }
\\\
&= { \\falling{2n}{n} \\over n!} {\\pi \\over 4\^n }\
.\]\
:::

:::{.exercise title=\"[$x/(x^{2} + 4x + 13)^{2}$]{.math .math-inline
.is-loaded}\"}

\[\
I\\da \\int\_\\RR {x\\over (x\^2 + 4x+13)\^2}\\dx\
.\]

\#completed

:::

:::{.solution}\
Write the integrand as [$f$]{.math .math-inline .is-loaded}.

:::{.claim}\
[$f \in \mathsf{O}\text{\textbackslash qty}\frac{1}{z^{3}} \subseteq \mathsf{O}\text{\textbackslash qty}\frac{1}{z^{1 + \varepsilon}}$]{.math
.math-inline .is-loaded} means that a semicircular contour will work:

::: {.internal-embed alt="Semicircular contour" src="figures/2021-12-23_18-14-14.png"}
:::

:::

:::{.proof title=\"Of integrand decay\"}\
A quick justification: for [$R > 1$]{.math .math-inline .is-loaded}, if
[$n > k$]{.math .math-inline .is-loaded} then
[$\text{\textbackslash abs}z^{n} > \text{\textbackslash abs}z^{k}$]{.math
.math-inline .is-loaded}, so using the reverse triangle inequality,\
\[\
\\abs{z\\over (z\^2 + 4z + 13)\^2}\
&= \\abs{z\\over z\^4 + 8z\^3 + 42z\^2 + 104z + 169}\\\
&\\leq \\abs{z\\over \\abs{z}\^4 - 8\\abs{z}\^3 - 42\\abs{z}\^2 -
104\\abs{z} - 169}\\\
&\\leq \\abs{z\\over \\abs{z}\^4 - 8\\abs{z}\^4 - 42\\abs{z}\^4 -
104\\abs{z}\^4 - 169\\abs{z}\^4}\\\
&= \\abs{z\\over \\abs{z}\^4( 1 - 8 - 42 - 104 - 169)}\\\
&= 322 {\\abs{z} \\over \\abs{z}\^4} \\\
&= 322 \\abs{z}\^{-3} \\\
&= 322 R\^{-3} \\to 0 \\text{ as } R\\to\\infty\
.\]

:::

Factor the denominator:\
\[\
x\^2 + 4x + 13 = 0\
&\\implies x\^2 + 4x + \\qty{4\\over 2}\^2 = -13 + \\qty{4\\over 2}\^2
\\\
&\\implies (x+2)\^2 = -9 \\\
&\\implies x = -2 \\pm 3i\
,\]\
one of which is in [$\mathbb{H}$]{.math .math-inline .is-loaded}.\
Write these as\
\[\
z_1 \\da -2+3i && z_2 \\da -2 - 3i\
.\]

So let [$\Gamma$]{.math .math-inline .is-loaded} be comprised of

-   [$C_{1} = \lbrack - R,R\rbrack$]{.math .math-inline .is-loaded},
-   [$C_{2} = \left\{ {Re^{it}{\ |\ }t \in \lbrack 0,\pi\rbrack} \right\}$]{.math
    .math-inline .is-loaded},
-   [$\Gamma = C_{1} + C_{2}$]{.math .math-inline .is-loaded}, then\
    \[\
    2\\pi i \\sum*{z_k\\in \\HH} \\Res*{z=z*k}f(z) = \\int*\\Gamma f =
    \\qty{\\int*{C_1} + \\int*{C*2}}f\
    ,\]\
    where \$\\int*{C*2} f\\to 0\$ and \$\\int*{C*1} f\\to I\$.\
    So in the limit, \$I = 2\\pi i \\Res*{z=z*1}
    f(z)[$.Computingthisresidue:note\$ z_{1}$]{.math .math-inline
    .is-loaded} is a pole of order 2, so\
    \[\
    \\Res*{z=z*1}\
    &= \\lim*{z\\to z*1} \\dd{}{z} (z-z_1)\^2f(z)\
    &= \\lim*{z\\to z*1} \\dd{}{z} {z \\over (z-z_2)\^2} \\\
    &= \\lim*{z\\to z*1} { (z-z_2)\^2 - 2z(z-z_2 ) \\over (z-z_2)\^4}
    \\\
    &= \\lim*{z\\to z*1} { (z-z_2) - 2z \\over (z-z_2)\^3} \\\
    &= \\lim*{z\\to z_1} -{ z+z_2 \\over (z-z_2)\^3} \\\
    &= - {z_1 + z_2 \\over (z_1 - z_2)\^2}\\\
    &= - {z_1 + \\bar{z_1} \\over (z_1 - \\bar{z_1} )\^2}\\\
    &= - {2\\Re(z_1) \\over (2i\\Im(z_1))\^3} \\\
    &= - {2\\cdot (-2) \\over (2i\\cdot 3) \^3} \\\
    &= {4\\over 2\^3 \\cdot 3\^3 \\cdot i\^3} \\\
    &= {-i \\over 2 \\cdot 3\^3 i\^2} \\\
    &= {i\\over 54}\
    ,\]\
    so\
    \[\
    I = 2\\pi i \\cdot {i\\over 54} = -{\\pi \\over 27}\
    .\]

:::

:::{.exercise title=\"[$\cos(x)/x^{2} + b^{2}$]{.math .math-inline
.is-loaded}\"}\
\[\
I \\da \\int\_{0}\^{\\infty} \\frac{\\cos (x)}{x\^{2}+b\^{2}} d
x=\\frac{\\pi \\mathrm{e}\^{-b}}{2 b}\
.\]

\#completed

:::

:::{.solution}\
The integrand is even, so\
\[\
I = \\Re{1\\over 2} \\tilde I \\da {1\\over 2} \\int\_\\RR {e\^{iz}
\\over (z+ib)(z-ib)}\
\]

Since [$f \sim 1/x^{2}$]{.math .math-inline .is-loaded}, the ML estimate
on a semicircular contour works:

::: {.internal-embed alt="figures/2021-07-29_18-42-38.png" src="figures/2021-07-29_18-42-38.png"}
:::

Then [$\int_{C_{R}}f \rightarrow 0$]{.math .math-inline .is-loaded} and
[$\int_{C_{1}}f \rightarrow \overset{\sim}{I}$]{.math .math-inline
.is-loaded}.\
Thus\
\[\
\\tilde I\
&= 2\\pi i \\Res*{z=ib} \\\
&= 2\\pi i \\lim*{z\\to ib}{e\^{iz}\\over (z+ib)} \\\
&= 2\\pi i {e\^{-b} \\over 2i b} \\\
&= {\\pi e\^{-b} \\over b}\
\]\
and\
\[\
I = \\Re {1\\over 2} \\tilde I = {\\pi e\^{-b} \\over 2b}\
.\]

:::

### Linear or sublinear decay {#linear-or-sublinear-decay heading="Linear or sublinear decay"}

:::{.exercise title=\"[$x\sin(x)/1 + x^{2}$]{.math .math-inline
.is-loaded}\"}\
\[\
I = \\int\_\\RR {x\\sin(x) \\over 1 + x\^2}\\dx\
.\]

\#completed

:::

:::{.solution}\
Write [$f(z) = \frac{ze^{iz}}{1 + z^{2}}$]{.math .math-inline
.is-loaded}, and note that
[$f \in \mathsf{O}\text{\textbackslash qty}\frac{1}{z}$]{.math
.math-inline .is-loaded}, so the usual semicircular contour with the ML
estimate won\'t work.\
Claim: a semicircular contour with a better estimate *will* work:

::: {.internal-embed alt="Semicircular contour" src="figures/2021-12-23_18-14-14.png"}
:::

Writing [$f(z) = e^{iz}g(z)$]{.math .math-inline .is-loaded} where
[$g(z){: =}\frac{z}{1 + z^{2}}$]{.math .math-inline .is-loaded}, we have
[$g \in \mathsf{O}\text{\textbackslash qty}\frac{1}{z} \rightarrow 0$]{.math
.math-inline .is-loaded} as
[$\text{\textbackslash abs}z \rightarrow \infty$]{.math .math-inline
.is-loaded}, so Jordan\'s lemma applies.\
Write [$C_{1} = \lbrack - R,R\rbrack$]{.math .math-inline .is-loaded}
and
[$C_{R} = \left\{ {Re^{it}{\ |\ }t \in \lbrack 0,\pi\rbrack} \right\}$]{.math
.math-inline .is-loaded}, then\
\[\
\\abs{\\int*{C_R} e\^{iz} g(z)\\dz }\\leq \\pi M_R,, \\qquad M_R \\da
\\sup*{z\\in C*R}\\abs{z\\over 1+z\^2}\
.\]\
Now use that
[$\frac{z + 1}{z^{2}} \leq M\text{\textbackslash abs}z$]{.math
.math-inline .is-loaded} for [$\text{\textbackslash abs}z$]{.math
.math-inline .is-loaded} large enough to conclude this integral goes to
zero.\
By the residue theorem,\
\[\
2\\pi i \\sum*{z*k\\in \\HH}\\Res*{z=z*k}f(z) = \\int*{C*1 + C_R} f =
\\qty{\\int*{C*1} + \\int*{C*R}}f \\converges{R\\to\\infty} \\int*{C*1}
f = I\
,\]\
so it suffices to compute the residues of [$f$]{.math .math-inline
.is-loaded}.\
Check that [$1 + z^{2} = (1 + i)(1 - i)$]{.math .math-inline
.is-loaded}, so [$z_{1} = i \in \mathbb{H}$]{.math .math-inline
.is-loaded} is a simple pole and\
\[\
2\\pi i \\Res*{z=i} f(z)\
&= 2\\pi i \\lim\_{z\\to i} {e\^{iz} \\over z+i} \\\
&= 2\\pi i {i\\over 2ei} = {\\pi \\over e}\
,\]\
so\
\[\
I = {\\pi \\over e}\
.\]\
:::

:::{.exercise title=\"[$\cos(x)/i + x$]{.math .math-inline
.is-loaded}\"}\
\[\
I \\da \\int\_\\RR {\\cos(x) \\over x+i}\\dx\
.\]

\#completed

:::

:::{.solution}\
Note that the usual thing won\'t work, since
[$\frac{\cos(z)}{z + i} \neq \Re\text{\textbackslash qty}\frac{e^{iz}}{z + i};$]{.math
.math-inline .is-loaded} the complex constant in the denominator throws
this off!\
Instead, use [$\cos(z) = \frac{1}{2}(e^{iz} + e^{- iz})$]{.math
.math-inline .is-loaded} to decompose into two integrals:\
\[\
I \\da \\int*\\RR {\\cos(z) \\over z+i}\
= {1\\over 2} \\int*\\RR {e\^{iz} \\over z+i} + {1\\over 2}\\int*\\RR
{e\^{-iz} \\over z+i} \\da \\int*\\RR f*1 + \\int*\\RR f_2\
,\]\
These both have [$\deg(f_{i}) = - 1$]{.math .math-inline .is-loaded}, so
Jordan\'s lemma on semicircular contours will work.\
For [$e^{i\alpha z}$]{.math .math-inline .is-loaded}, one needs to take
the upper half-plane for [$\alpha > 0$]{.math .math-inline .is-loaded}
(so [$f_{1}$]{.math .math-inline .is-loaded}) and the lower for
[$\alpha < 0$]{.math .math-inline .is-loaded} (for [$f_{2}$]{.math
.math-inline .is-loaded}).\
For [$f_{1}$]{.math .math-inline .is-loaded}, use the upper contour:

::: {.internal-embed alt="Semicircular contour" src="figures/2021-12-23_18-14-14.png"}
:::

Then by Jordan\'s lemma, since [$f(z) = e^{iz}g(z)$]{.math .math-inline
.is-loaded} with [$g(z) \rightarrow 0$]{.math .math-inline .is-loaded}
as [$\text{\textbackslash abs}z \rightarrow \infty$]{.math .math-inline
.is-loaded}, [$\int_{\gamma_{R}}f \rightarrow 0$]{.math .math-inline
.is-loaded} and we\'re left with the residues in [$\mathbb{H}$]{.math
.math-inline .is-loaded}.\
Here, the only residue is at [$z = - i$]{.math .math-inline .is-loaded},
so this integral is zero.\
For [$f_{2}$]{.math .math-inline .is-loaded}, use the lower contour:

::: {.internal-embed src="figures/2021-12-23_18-39-11.png"}
:::

This is parameterized counterclockwise, and so the piece along
[$\mathbb{R}$]{.math .math-inline .is-loaded} converges to [$- I$]{.math
.math-inline .is-loaded}.\
By Jordan\'s lemma\
\[\
-I\
&= 2\\pi i \\Res*{z=-i} {e\^{iz}\\over 2(z+i)} \\\
&= 2\\pi i \\lim*{z\\to -i} {e\^{iz}\\over 2} \\\
&= \\pi i e\\inv\
,\]\
so\
\[\
I = -{i\\pi \\over e}\
.\]\
:::

### No clear decay {#no-clear-decay heading="No clear decay"}

:::{.exercise title=\"[$e^{x/2}/1 + e^{x},$]{.math .math-inline
.is-loaded} replication\"}\
\[\
I \\da \\int\_\\RR {e\^{x\\over 2}\\over 1+e\^x}\\dx\
.\]

\#completed

:::

:::{.solution}\
Replication: find [$b$]{.math .math-inline .is-loaded} such that
[$f(z) = f(z + ib)$]{.math .math-inline .is-loaded} and use a
rectangle.\
\[\
f(z+ib)\
= {e\^{z\\over 2}e\^{ib\\over 2} \\over 1 + e\^{ib}e\^z}\
= e\^{ib\\over 2} {e\^{z\\over 2} \\over 1 + e\^{ib}e\^z } = f(z)
\\impliedby e\^{ib} = 1 \\impliedby b=2\\pi\
,\]\
in which case\
\[\
f(z + 2\\pi i) = e\^{ib\\over 2}f(z) = e\^{2\\pi i \\over 2}f(z) =
-f(z)\
.\]

So take the following rectangle where [$H_{-}$]{.math .math-inline
.is-loaded} is at [$2\pi i$]{.math .math-inline .is-loaded} and
[$H_{+}$]{.math .math-inline .is-loaded} is at 0, with sides at
[$\pm R$]{.math .math-inline .is-loaded}:

::: {.internal-embed src="figures/2021-12-21_21-25-04.png"}
:::

Write [$\Gamma$]{.math .math-inline .is-loaded} for the entire contour.\
Note that integrating left-to-right on [$H_{-}$]{.math .math-inline
.is-loaded} yields [$- I$]{.math .math-inline .is-loaded}, since
[$w = z + 2\pi i$]{.math .math-inline .is-loaded} for
[$w \in H_{-}$]{.math .math-inline .is-loaded} and
[$f(w) = - f(z)$]{.math .math-inline .is-loaded}.\
Then reversing the orientation, going right-to-left yields
[$\int_{H_{i}}f = I$]{.math .math-inline .is-loaded}.

Claim: the integrals over the sides [$V_{\pm}$]{.math .math-inline
.is-loaded} vanish. For the right,\
\[\
\\abs{\\int*{V*+} f(z) \\dz}\
&\\leq 2\\pi \\sup\_{t\\in \[0, 2\\pi\]} \\abs{e\^{R + it\\over 2}
\\over 1 + e\^{R + it} } \\\
&\\leq 2\\pi \\sup_t {\\abs{ e\^{R\\over 2} e\^{it \\over 2} } \\over
\\abs{e\^{R}e\^{it}} - 1} \\\
&\\leq 2\\pi \\sup_t {\\abs{ e\^{R\\over 2} } \\over \\abs{e\^{R}} - 1}
\\\
&\\in \\bigo(e\^{- {R\\over 2} }) \\to 0\
.\]

For the left:\
\[\
\\abs{\\int*{V*-} f(z) \\dz}\
&\\leq \\sup*{t\\in \[0, 2\\pi\] } \\abs{ e\^{-R-it\\over 2} \\over 1 +
e\^{-R- it}} \\\
&\\leq \\sup*{t\\in \[0, 2\\pi\]}\\abs{e\^{-R\\over 2} e\^{-it\\over 2}}
\\\
&\\leq \\sup\_{t\\in \[0, 2\\pi\]}\\abs{e\^{-R\\over 2}} \\\
&\\in \\bigo(e\^{- {R\\over 2} }) \\to 0\
,\]\
where we\'ve thrown away positive terms in the denominator, which only
makes this quantity larger.

Finding the poles within [$\Gamma$]{.math .math-inline .is-loaded}: by
inspection, there are poles when [$e^{z} = - 1$]{.math .math-inline
.is-loaded}, so at [$z = (2k + 1)\pi i$]{.math .math-inline .is-loaded}
for [$k \in \mathbb{Z}$]{.math .math-inline .is-loaded}.\
Exactly one falls into this contour, [$z_{k} = i\pi$]{.math .math-inline
.is-loaded}.\
By the residue theorem,\
\[\
2\\pi i \\Res*{z=i\\pi} f(z) = \\int*\\Gamma f(z) \\dz =
\\qty{\\int*{H*-} + \\int*{H*+}} f = 2I \\implies I = \\pi i
\\Res*{z=i\\pi } f\
.\]\
Computing this residue:\
\[\
\\pi i \\Res*{z=i\\pi }f(z)\
&= \\pi i \\lim*{z\\to i\\pi} { (z-i\\pi) e\^{z\\over 2}\\over e\^z + 1}
\\\
&\\eqLH \\pi i \\lim*{z\\to i\\pi} {e\^{z\\over 2} \\over e\^z} \\\
&= \\pi i e\^{-i\\pi \\over 2} \\\
&= \\pi\
.\]

> DZG: This is much easier than trying to find the Laurent expansion
> about [$z = i\pi$]{.math .math-inline .is-loaded} \-- trust me!

:::

:::{.exercise title=\"[$e^{ax}{sech}(z)$]{.math .math-inline .is-loaded}
\"}\
\[\
I \\da \\int\_\\RR {e\^{ax} \\over \\cosh(x) }\\dx = \\pi
\\sec\\qty{a\\pi \\over 2} && \\abs{\\Re(a)} \< 1\
.\]

\#completed

:::

:::{.solution}\
Heuristically, [$\int e^{ax}{sech}(x)$]{.math .math-inline .is-loaded}
should converge since [${sech}(x) \sim e^{- x}$]{.math .math-inline
.is-loaded}, so
[$\text{\textbackslash abs}f \sim \text{\textbackslash abs}e^{(a - 1)x} \sim e^{\Re(a - 1)x} \sim e^{- x}$]{.math
.math-inline .is-loaded} when [$\Re(a - 1)$]{.math .math-inline
.is-loaded} is negative, so [$\Re(a) < 1$]{.math .math-inline
.is-loaded}.

We\'ll need a contour along [$\mathbb{R}$]{.math .math-inline
.is-loaded}, so immediate options are a semicircular contour or a
rectangle.\
A semicircular contour is not a good idea here, since there are
infinitely many poles of this function:\
\[\
\\cosh(z) = 0 \\implies e\^z + e\^{-z} = 0 \\implies e\^{2z} = -1
\\implies z = {i\\pi \\cdot k \\over 2}\
.\]\
It turns out the residues at these poles are all 1, the residue theorem
would yield a divergent series.\
So take the rectangle contour with one side long [$\mathbb{R}$]{.math
.math-inline .is-loaded} and one along
[$\left\{ {t + ib{\ |\ }t \in \lbrack - R,R\rbrack} \right\}$]{.math
.math-inline .is-loaded} respectively, where we\'ll choose [$ib$]{.math
.math-inline .is-loaded} so that the two integrals differ by a scalar.\
Computing the symmetry by looking at [$f(z + ib)$]{.math .math-inline
.is-loaded}:\
\[\
{e\^{a(z+ib)} \\over \\cosh(z+ib)}\
= e\^{aib} {e\^{z} \\over e\^z e\^{ib} + e\^{-z} e\^{-ib} }\
,\]\
and we now need [$e^{ib} = e^{- ib}$]{.math .math-inline .is-loaded} in
order to scale it out.\
Noting that if [$z{: =}e^{ib}$]{.math .math-inline .is-loaded} then
[$\mspace{1mu}\overset{―}{\mspace{-1mu} z\mspace{-1mu}}\mspace{1mu} = e^{- ib}$]{.math
.math-inline .is-loaded}, this forces [$z \in \mathbb{R}$]{.math
.math-inline .is-loaded}, so [$z = \pm 1$]{.math .math-inline
.is-loaded}.\
Taking [$z = + 1$]{.math .math-inline .is-loaded} forces [$b = 0$]{.math
.math-inline .is-loaded}, which is the original contour, so taking
[$z = - 1$]{.math .math-inline .is-loaded} yields [$b = \pi i$]{.math
.math-inline .is-loaded}.\
So we take the following contour:

::: {.internal-embed src="figures/2021-12-22_05-16-12.png"}
:::

Computing the integral on the upper contour:\
\[\
\\int*{\\gamma_1} f(z) \\dz\
&= \\int_R\^{-R} f(t+ib) \\dt \\qquad z=t+ib, \\dz = \\dt \\\
&= - \\int*{-R}\^R f(t+ib) \\dt \\\
&= - \\int*{-R}\^R {e\^{a(t+i\\pi)} \\over \\cosh(t+i\\pi ) } \\dt \\\
&= - \\int*{-R}\^R e\^{ai\\pi} {e\^{t} \\over e\^t e\^{i\\pi} + e\^{-t}
e\^{-i\\pi} } \\dt \\\
&= - \\int*{-R}\^R e\^{ai\\pi} {e\^{t} \\over -e\^t - e\^{-t} } \\dt \\\
&= \\int*{-R}\^R e\^{ai\\pi} {e\^{t} \\over e\^t + e\^{-t} } \\dt \\\
&= e\^{ai\\pi} \\int*{-R}\^R {e\^{t} \\over e\^t + e\^{-t} } \\dt \\\
&= e\^{ai\\pi} \\int*{-R}\^R {e\^{t} \\over \\cosh(t) } \\dt \\\
&= e\^{ai\\pi} \\int*{\\gamma_0} f(z) \\dz\
,\]\
so\
\[\
\\qty{\\int*{\\gamma*0} + \\int*{\\gamma_1}} f = (1+e\^{ai\\pi}) I\
.\]

:::{.claim}\
The integrals along the sides vanish as [$R \rightarrow \infty$]{.math
.math-inline .is-loaded}.

The quick argument: [$\cos(z) \sim e^{z}$]{.math .math-inline
.is-loaded} so [${sech}(z) \sim e^{- z}$]{.math .math-inline
.is-loaded}, so\
\[\
\\abs{f(R+ it)} &= \\abs{e\^{a(R+it)}\\sech(R+it)} \\sim \\abs{
e\^{aR}e\^{-R}} = \\abs{ e\^{R(a-1)} } = e\^{R\\cdot \\Re(a-1)} \\\
\\abs{f(-R+ it)} &= \\abs{e\^{a(-R+it)}\\sech(-R+it)} \\sim \\abs{
e\^{-aR}e\^{R}} = \\abs{ e\^{-R(a+1)}} = e\^{-R \\cdot \\Re(a+1)}\
,\]\
where the first goes to zero when [$\Re(a) < 1$]{.math .math-inline
.is-loaded} and the second when [$\Re(a) > - 1$]{.math .math-inline
.is-loaded}.\
:::

:::{.proof title=\"That the side integral vanish\"}\
Parameterize the right contour as\
\[\
\\gamma\^+ = \\ts{R+it \\st t\\in \[0, \\pi\]}\
.\]\
Then\
\[\
\\abs{ \\int\_{\\gamma\^+} f(z) \\dz }\
&= \\abs{ \\int_0\^\\pi f(R+it) \\dt} \\qquad z=R+it, \\dz=\\dt \\\
&= \\abs{ \\int_0\^\\pi { e\^{a(R+it)} \\over \\cosh(R+it) } \\dt } \\\
&= \\abs{ \\int_0\^\\pi { e\^{aR}e\^{ait} \\over e\^Re\^{it} + e\^{-R}
e\^{-it} } \\dt } \\\
&\\leq \\int_0\^\\pi \\abs{{ e\^{aR}e\^{ait} \\over e\^Re\^{it} +
e\^{-R} e\^{-it} } } \\dt \\\
&= \\int_0\^\\pi {{ \\abs{ e\^{aR}e\^{ait} } \\over \\abs{ e\^Re\^{it} +
e\^{-R} e\^{-it} } } } \\dt \\\
&\\leq c\\int_0\^\\pi {{ \\abs{ e\^{aR} } \\over \\abs{ e\^{-R}
(e\^{2R}e\^{it} + e\^{-it}) } } } \\dt \\qquad c\\da e\^{ait} \\\
&= c\\int_0\^\\pi {{ \\abs{ e\^{(a-1)R} } \\over \\abs{(e\^{2R}e\^{it} +
e\^{-it}) } } } \\dt \\\
&\\leq c\\int_0\^\\pi {{ \\abs{ e\^{(a-1)R} } \\over
\\abs{e\^{2R}e\^{it} } - \\abs{e\^{-it} } } } \\dt \\\
&= c\\int_0\^\\pi {{ e\^{\\Re((a-1)R)} \\over e\^{2R} - 1 } } \\dt \\\
&= {{ c\\pi e\^{\\Re((a-1)R)} \\over e\^{2R} - 1 } } \\\
&\\leq {{ c\\pi e\^{R\\cdot \\Re((a-1))}} }\
\]\
which goes to zero provide [$\Re(a - 1) < 0$]{.math .math-inline
.is-loaded}, so [$\Re(a) < 1$]{.math .math-inline .is-loaded} (as
assumed).\
Here we\'ve thrown out positive denominators, which only makes the terms
larger.

Similarly, parameterized the left contour as\
\[\
\\gamma\^- = \\ts{-R+it \\st t\\in \[0, \\pi\]}\
,\]\
then\
\[\
\\abs{ \\int\_{\\gamma\^-} f(z) \\dz }\
&= \\abs{ \\int_0\^\\pi f(-R+it) \\dt \\qquad z=-R+it, \\dz=\\dt} \\\
&= \\abs{ \\int_0\^\\pi { e\^{a(-R+it)} \\over \\cosh(-R+it) } \\dt }
\\\
&= \\abs{ \\int_0\^\\pi { e\^{-aR}e\^{ait} \\over e\^{-R}e\^{it} +
e\^{R} e\^{-it} } \\dt } \\\
&\\leq \\int_0\^\\pi \\abs{{ e\^{-aR}e\^{ait} \\over e\^{-R}e\^{it} +
e\^{R} e\^{-it} } } \\dt \\\
&= \\int_0\^\\pi {{ \\abs{ e\^{-aR}e\^{ait} } \\over \\abs{
e\^{-R}e\^{it} + e\^{R} e\^{-it} } } } \\dt \\\
&\\leq c\\int_0\^\\pi {{ \\abs{ e\^{-aR} } \\over \\abs{ e\^{-R}
(e\^{it} + e\^{2R}e\^{-it}) } } } \\dt \\\
&= c\\int_0\^\\pi {{ \\abs{ e\^{-R(a+1)} } \\over \\abs{(e\^{it} +
e\^{2R}e\^{-it}) } } } \\dt \\\
&\\leq c\\int_0\^\\pi {{ \\abs{ e\^{-R(a+1)} } \\over
\\abs{e\^{2R}e\^{-it} } - \\abs{e\^{it} } } } \\dt \\\
&= c\\int_0\^\\pi {{ e\^{\\Re(-R(a+1))} \\over e\^{2R} - 1 } } \\dt \\\
&= {{ c\\pi e\^{\\Re(-R(a+1))} \\over e\^{2R} - 1 } } \\\
&\\leq {{ c\\pi e\^{-R \\cdot \\Re((a+1))}} }\
,\]\
which now goes to zero provided [$\Re(a + 1) > 0$]{.math .math-inline
.is-loaded}, so [$\Re(a) > - 1$]{.math .math-inline .is-loaded} (again
as assumed).

:::

Given thus, noting that only the pole [$z_{0} = \frac{i\pi}{2}$]{.math
.math-inline .is-loaded} is enclosed, the residue theorem yields\
\[\
2\\pi i \\Res*{z=z_0}f(z) = \\int*\\Gamma f = (1+e\^{ai\\pi})I \\implies
I = {2\\pi i \\Res*{z=z_0} f(z) \\over 1 + e\^{ai\\pi}}\
.\]\
Computing the residue:\
\[\
\\Res*{z=z*0}f(z)\
&= \\lim*{z\\to z*0} {(z-z_0)e\^{az} \\over \\cosh(z)}\\\
&\\eqLH \\lim*{z\\to z_0} {a(z-z_0) e\^{az} \\over \\sinh(z)} +
{e\^{az}\\over \\sinh(z)} \\\
&= {a \\cdot 0 \\cdot e\^{ai\\pi \\over 2} \\over i \\sin\\qty{\\pi
\\over 2} } + {e\^{a i \\pi \\over 2} \\over i\\sin\\qty{\\pi \\over 2}}
\\\
&= {e\^{ai\\pi\\over 2} \\over i} \\\
&= -i e\^{ai\\pi \\over 2}\
,\]\
where we\'ve used that [$\sinh(iz) = i\sin(z)$]{.math .math-inline
.is-loaded}.\
Putting it all together:\
\[\
I\
&= {2\\pi i \\cdot -i e\^{ai\\pi \\over 2} \\over 1 + e\^{a i \\pi}} \\\
&= {2\\pi e\^{ai\\pi \\over 2} \\over 1 + e\^{a i \\pi}} \\\
&= {2\\pi \\over e\^{-ai\\pi \\over 2}\\qty{ 1 + e\^{a i \\pi}} } \\\
&= {2\\pi \\over e\^{-ai\\pi \\over 2}+ e\^{a i \\pi\\over 2} } \\\
&= {\\pi \\over \\cos\\qty{a\\pi \\over 2}}\\\
&= \\pi \\csc\\qty{a\\pi \\over 2}\
.\]

:::

## Singularities along [$\mathbb{R}$]{.math .math-inline .is-loaded}, Principal Values {#singularities-along-mathbbr-principal-values heading="Singularities along $\\RR$, Principal Values"}

:::{.exercise title=\"[$\sin(x)/x$]{.math .math-inline .is-loaded} and
[$\cos(x)/x$]{.math .math-inline .is-loaded}\"}\
Compute\
\[\
I*1 \\da \\operatorname{PV}\\int*\\RR {\\sin(x) \\over x}\\dx = \\pi \\\
I*2 \\da \\operatorname{PV}\\int*\\RR {\\cos(x) \\over x}\\dx = 0\
.\]

\#completed

:::

:::{.solution}\
Take [$\Gamma$]{.math .math-inline .is-loaded} an upper-half-plane
semicircular contour indented at the origin; considering
[$f(z) = e^{iz}$]{.math .math-inline .is-loaded}, by Jordan\'s lemma
[$\int_{C_{R}}f \rightarrow 0$]{.math .math-inline .is-loaded} and the
pieces along [$\mathbb{R}$]{.math .math-inline .is-loaded} converge to
[$\text{\textbackslash PV}\int f$]{.math .math-inline .is-loaded}.\
The singularity at [$z_{0} = 0$]{.math .math-inline .is-loaded}
contributes a fractional residue:\
\[\
\\int*{C*\\eps}f(z)\\dz \\to i\\pi \\Res*{z=z_0} f(z) = i\\pi
\\lim*{z\\to 0} {(z-0) e\^{iz}\\over z} = i\\pi \\cdot 1\
.\]\
Thus\
\[\
I \\da \\PV \\int\_\\RR f(z)\\dz = 0 + i\\pi \\implies I_1 = \\Im(I) =
\\pi, \\quad I_2 = \\Re(I) = 0\
.\]\
:::

:::{.exercise title=\"[$xe^{2ix}/x^{2} - 1$]{.math .math-inline
.is-loaded} \"}\
\[\
I \\da \\int\_\\RR {xe\^{2ix} \\over x\^2-1}\\dx = i\\pi \\cos(2)\
.\]

\#completed

:::

:::{.solution}\
Factor the denominator as [$(z - 1)(z + 1)$]{.math .math-inline
.is-loaded}, then there are two poles of order 1 on [$\mathbb{R}$]{.math
.math-inline .is-loaded}.\
Define a contour

-   [$C_{1}:\lbrack - R,1 - \varepsilon_{1}\rbrack$]{.math .math-inline
    .is-loaded}
-   [$- C_{2}: - 1 + Re^{it},t \in \lbrack 0,\pi\rbrack$]{.math
    .math-inline .is-loaded}
-   [$C_{3}:\lbrack 1 - \varepsilon,1 + \varepsilon\rbrack$]{.math
    .math-inline .is-loaded}
-   [$C_{4}:1 + Re^{it},t \in \lbrack 0,\pi\rbrack$]{.math .math-inline
    .is-loaded}
-   [$C_{R}:Re^{it},t \in \lbrack 0,\pi\rbrack$]{.math .math-inline
    .is-loaded}
-   [$\Gamma = C_{1} + \cdots + C_{4} + C_{R}$]{.math .math-inline
    .is-loaded}

So this, but with a semicircular contour instead of a rectangle:

::: {.internal-embed src="figures/2021-12-21_01-47-37.png"}
:::

By Jordan\'s lemma, [$\int_{C_{R}} \rightarrow 0$]{.math .math-inline
.is-loaded}, and
[$\text{\textbackslash qty}{\int_{C_{2}} + \int_{C_{3}} + \int_{C_{4}}} \rightarrow 0$]{.math
.math-inline .is-loaded}, while [$\int_{\Gamma} = 0$]{.math .math-inline
.is-loaded} since it encloses no singularities.\
Thus\
\[\
0 = \\int*{C_2} f + \\int*{C_4} f\
,\]\
which converges to the fractional residues at [$z = \pm 1$]{.math
.math-inline .is-loaded}.

For [$z = - 1$]{.math .math-inline .is-loaded},\
\[\
\\int*{C_2}\
&\\to \\pi i \\Res*{z=-1} f(z) \\\
&= \\pi i \\lim\_{z\\to -1} {e\^{2iz} \\over z-1} \\\
&= \\pi i {e\^{-2i} \\over 2}\
.\]

For [$z = - 1$]{.math .math-inline .is-loaded}:\
\[\
\\int*{C_4}\
&\\to \\pi i \\Res*{z=1} f(z) \\\
&= \\pi i \\lim\_{z\\to 1} {e\^{2iz} \\over z+1} \\\
&= \\pi i {e\^{2i} \\over 2}\
.\]

Putting it all together:\
\[\
I\
&= \\pi i {e\^{-2i} \\over 2} + \\pi i {e\^{2i}\\over 2} \\\
&=\\pi i \\cos(2)\
.\]\
:::

## Rational functions of [$\cos,\sin$]{.math .math-inline .is-loaded} {#rational-functions-of-cossin heading="Rational functions of $\\cos, \\sin$"}

:::{.exercise title=\"[$1/1 + \sin^{2}$]{.math .math-inline
.is-loaded}\"}\
\[\
\\int\_{\[-\\pi, \\pi\]} {1\\over 1 + \\sin\^2(\\theta)} \\dtheta\
.\]

\#completed

:::

:::{.solution}\
Set [$z = e^{i\theta}$]{.math .math-inline .is-loaded}, so
[$\sin(\theta) = \frac{z + z^{- 1}}{2i}$]{.math .math-inline .is-loaded}
and [$\sin^{2}(\theta) = - \frac{1}{4}(z^{- 2} - 2 + z^{2})$]{.math
.math-inline .is-loaded}.\
Then\
\[\
I\\da \\int*{\[-\\pi, \\pi\]} {1\\over 1 + \\sin\^2(\\theta)} \\dtheta\
&= \\int*{S\^1} {1\\over 1 - {1\\over 4}(z\^{-2} -2 + z\^2) } {1\\over
iz}\\dz \\\
&= \\int*{S\^1} {-4i \\over z(4-(z\^{-2} -2 + z\^2))}\\dz \\\
&= \\int*{S\^1} {-4iz \\over z\^2(6-z\^{-2} - z\^2)}\\dz \\\
&= \\int*{S\^1} {4iz \\over z\^4-6z\^2+1}\\dz \\\
&= 2\\pi i \\sum*{z*k\\in \\DD} \\Res*{z=z_k} {4iz\\over z\^4-6z\^2+1}\
.\]

Factoring the denominator:\
\[\
w\^2 - 6w - 1 =0\
&\\implies w\^2 - 6w + \\qty{-6\\over 2}\^2 - \\qty{-6\\over 2}\^2 + 1
=0 \\\
&\\implies (w - 3)\^2 = -1 + 9 = 8 \\\
&\\implies w-3 = \\zeta_2\^k \\sqrt{8},, k=0, 1 \\\
&\\implies w = 3 \\pm \\sqrt{8} \\\
&\\implies z= \\pm\\sqrt{3\\pm \\sqrt 8}\
.\]\
Write these roots as

-   [$z_{1}{: =}\sqrt{3 - \sqrt{8}}$]{.math .math-inline .is-loaded}
-   [$z_{2}{: =} - \sqrt{3 - \sqrt{8}}$]{.math .math-inline .is-loaded}
-   [$z_{3}{: =}\sqrt{3 + \sqrt{8}}$]{.math .math-inline .is-loaded}
-   [$z_{4}{: =} - \sqrt{3 + \sqrt{8}}$]{.math .math-inline .is-loaded}

Some numerology to figure out the modulus of these roots:

-   [$3 + \sqrt{8} = 3 + 2\sqrt{2}3 + 2 \cdot (1.4) \approx 5.8$]{.math
    .math-inline .is-loaded}, so
    [$\text{\textbackslash abs}{\pm \sqrt{3 + \sqrt{8}}} > \sqrt{4} > 2 > 1$]{.math
    .math-inline .is-loaded}.
-   [$3 - \sqrt{8} \approx 3 - 2.8 \approx 0.2$]{.math .math-inline
    .is-loaded} so
    [$\text{\textbackslash abs}{\pm \sqrt{3 - \sqrt{8}}} < 1$]{.math
    .math-inline .is-loaded}.

So it suffices to compute the residues at
[$z_{1},z_{2} = \pm \sqrt{3 - \sqrt{8}}$]{.math .math-inline
.is-loaded}:\
At [$z_{1}$]{.math .math-inline .is-loaded}:\
\[\
\\Res*{z = z_1}\
&= \\lim*{z\\to z*1} {(z-z_1) 4i z \\over z\^4-6z\^2+1 } \\\
&\\equalsbecause{\\text{LH}} \\lim*{z\\to z*1} { 4iz + 4i(z-z_1) \\over
4z\^3 -12z} \\\
&= {4iz_1 \\over 4z_1\^3 - 12z_1} \\\
&= {i\\over z_1\^2 - 3} \\\
&= {i\\over (3-\\sqrt 8) - 3} \\\
&= -{i\\over \\sqrt 8}\
.\]\
At [$z_{2}$]{.math .math-inline .is-loaded}:\
\[\
\\Res*{z=z*2}\
&= \\lim*{z\\to z_2} {(z-z_2) 4i z \\over z\^4-6z\^2+1 } \\\
&= {4iz_2\\over 4z_2\^2 - 12z_2}\\\
&= {i \\over z_2\^2 - 3} \\\
&= -{i\\over \\sqrt 8}\
.\]

Thus\
\[\
I = 2\\pi i \\cdot -{2i\\over \\sqrt 8} = {4\\pi \\over \\sqrt{8}}\
.\]\
:::

:::{.exercise title=\"[$1/1 + a^{2} + 2a\cos(\theta)$]{.math
.math-inline .is-loaded}, Poisson kernels\"}\
\[\
\\int\_{0}\^{2 \\pi} \\frac{d \\theta}{1+a\^{2}-2 a \\cos (\\theta)}\
= \\begin{cases}\\frac{2 \\pi}{a\^{2}-1} & \\text { if }\|a\|\>1 \\
\\frac{2 \\pi}{1-a\^{2}} & \\text { if }\|a\|\<1\\end{cases}\
.\]

\#completed

:::

:::{.solution}\
The usual substitution: [$z = e^{i\theta},\, dz = (iz)\, d\theta$]{.math
.math-inline .is-loaded}.\
\[\
I\\da \\int\_{\[0, 2\\pi\]} \\qty{a\^2 - 2a\\cos(\\theta) + 1}\\inv
\\dtheta\
&= \\oint \\qty{a\^2-2(z+z\\inv) + 1}\\inv (iz)\\inv \\dz \\\
&= -i\\oint \\qty{za\^2 - a(z\^2+1) +z}\\inv \\dz \\\
&= -i \\oint\\qty{-az\^2 + (a\^2+1)z - a}\\inv\\dz \\\
&= {i\\over a}\\oint \\qty{z\^2 - \\qty{a\^2+a\\over a}z + 1}\\inv \\dz
\\\
&= {i\\over a}\\oint (z-a)\\inv (z-a\\inv)\\inv \\dz\
,\]\
noting that [$\frac{a^{2} + a}{a} = a + a^{- 1}$]{.math .math-inline
.is-loaded}.\
Now there are two cases:

-   [$\text{\textbackslash abs}a < 1$]{.math .math-inline .is-loaded}:
    then [$a \in \mathbb{D},a^{- 1} \in \mathbb{D}^{c}$]{.math
    .math-inline .is-loaded}, so there is a simple pole at [$a$]{.math
    .math-inline .is-loaded}.\
    Then\
    \[\
    I\
    &= {i\\over a}, 2\\pi i \\Res*{z=a} (z-a)\\inv(z-a\\inv)\\inv \\\
    &= -{2\\pi \\over a} (z-a\\inv)\\inv \\evalfrom*{z=a} \\\
    &= -{2\\pi \\over a(a-a\\inv)} \\\
    &= {2\\pi \\over 1 - a\^2}\
    .\]

-   [$\text{\textbackslash abs}a > 1$]{.math .math-inline .is-loaded}:
    then [$a^{- 1} \in \mathbb{D},a \in \mathbb{D}^{c}$]{.math
    .math-inline .is-loaded} so there is a simple pole at
    [$a^{- 1}$]{.math .math-inline .is-loaded}.\
    Then\
    \[\
    I\
    &= {i\\over a}, 2\\pi i \\Res*{z=a\\inv } (z-a)\\inv(z-a\\inv)\\inv
    \\\
    &= -{2\\pi \\over a} (z-a)\\inv \\evalfrom*{z=a\\inv} \\\
    &= -{2\\pi \\over a(a\\inv - a)} \\\
    &= {2\\pi \\over a\^2 - 1}\
    .\]

:::

:::{.exercise title=\"[$1/a + b\cos(\theta)$]{.math .math-inline
.is-loaded}\"}\
\[\
\\int\_{0}\^{2 \\pi} \\frac{d \\theta}{a+b \\cos \\theta}=\\frac{2
\\pi}{\\sqrt{a\^{2}-b\^{2}}}\
.\]

\#completed

:::

:::{.solution}\
The usual substitution:
[$z = e^{i\theta},\, d\theta = (iz)^{- 1}\, dz$]{.math .math-inline
.is-loaded}.\
\[\
\\int\_{\[0, 2\\pi\]} (a +b\\cos(\\theta))\\inv \\dtheta\
&= \\oint \\qty{ a + {b\\over 2}(z+z\\inv)}\\inv (iz)\\inv \\dz \\\
&= -i\\oint \\qty{ za + {b\\over 2}(z\^2 + 1)} \\inv \\dz \\\
&= -i \\oint \\qty{{b\\over 2}z\^2 + az + {b\\over 2} }\\inv \\dz \\\
&= -{2i\\over b} \\oint \\qty{z\^2 + {2a\\over b}z + 1}\\inv \\dz \\\
&= -{2i\\over b}\\oint (z-r_1)\\inv (z-r_2)\\inv \\dz\
,\]\
where the roots can just be found using the quadratic formula\
\[\
z_k\
&= {1\\over 2} \\qty{-{2a\\over b} \\pm \\sqrt{\\qty{2a\\over b}\^2 -
4}} \\\
&= -{a\\over b}\\pm {1\\over 2}\\sqrt{{4a\^2 \\over b\^2} - 4} \\\
&= -{a\\over b}\\pm \\sqrt{{a\^2 \\over b\^2} - 1} \\\
&= -{a\\over b}\\pm \\sqrt{{a\^2 - b\^2 \\over b\^2}} \\\
&= -{a\\over b}\\pm {1\\over b } \\sqrt{{a\^2 - b\^2}}\
.\]\
Thus\
\[\
r_1 &\\da b\\inv\\qty{-a + \\sqrt{a\^2-b\^2}} \\\
r_2 &\\da b\\inv\\qty{-a - \\sqrt{a\^2-b\^2}}\
.\]

Since [$r_{1}r_{2} = 1$]{.math .math-inline .is-loaded} and thus
[$\text{\textbackslash abs}{r_{1}r_{2}} = 1$]{.math .math-inline
.is-loaded}, only one root is in [$\mathbb{D}$]{.math .math-inline
.is-loaded} and this yields one simple pole.\
Assume [$a > b$]{.math .math-inline .is-loaded}.\
Note that for [$r_{2}$]{.math .math-inline .is-loaded},
[$\text{\textbackslash abs}{a/b} > 1$]{.math .math-inline .is-loaded}
and [$\text{\textbackslash abs}{a^{2} - b^{2}} > 0$]{.math .math-inline
.is-loaded}, so [$r_{2} \approx - 1 - \varepsilon < - 1$]{.math
.math-inline .is-loaded}, so [$r_{1} \in \mathbb{D}$]{.math .math-inline
.is-loaded}.\
Computing the residue here:\
\[\
\\Res*{z=r_1} (z-r_1)\\inv (z-r_2)\\inv\
&= (z-r_2)\\inv \\evalfrom*{z=r_1} \\\
&= (r_1 - r_2)\\inv \\\
&= \\qty{2b\\inv \\sqrt{a\^2-b\^2} }\\inv\
,\]\
so\
\[\
I &= 2\\pi i \\cdot -{2 i \\over b}{b\\over 2\\sqrt{a\^2-b\^2}} \\\
&= {2\\pi \\over \\sqrt{a\^2-b\^2} }\
.\]

:::

## Branch Cuts {#branch-cuts heading="Branch Cuts"}

### Logarithms {#logarithms heading="Logarithms"}

:::{.exercise title=\"[$\log(x)/1 + x^{2}$]{.math .math-inline
.is-loaded}\"}\
\[\
I \\da \\int_0\^\\infty {\\log(x) \\over 1+x\^2}\\dx = 0\
.\]

\#completed

:::

:::{.solution title=\"Semicircle, real reduction trick\"}\
Noting the partial [$\zeta_{2} = - 1$]{.math .math-inline .is-loaded}
symmetry, take a branch cut for [$\log$]{.math .math-inline .is-loaded}
along [$\theta = - \pi/2$]{.math .math-inline .is-loaded} and the
following semicircular contour:

::: {.internal-embed src="figures/2021-12-22_05-21-05.png"}
:::

Since [$f(z){: =}\frac{\log(z)}{z^{2} + 1}$]{.math .math-inline
.is-loaded} goes to zero as
[$\text{\textbackslash abs}R \rightarrow \infty$]{.math .math-inline
.is-loaded} and [$\varepsilon \rightarrow 0$]{.math .math-inline
.is-loaded}, only the horizontal contours will contribute.\
Parameterize, oriented counterclockwise:

-   [$\gamma_{1}{: =}\left\{ {t + 0i{\ |\ }t \in \lbrack\varepsilon,R\rbrack} \right\}$]{.math
    .math-inline .is-loaded}
-   [$\gamma_{2}{: =}\left\{ {t + 0i{\ |\ }t \in \lbrack - \varepsilon, - R\rbrack} \right\}$]{.math
    .math-inline .is-loaded}

Then [$\int_{\gamma_{1}}f(z)\, dz \rightarrow I$]{.math .math-inline
.is-loaded}.\
Computing the contribution from [$\gamma_{2}$]{.math .math-inline
.is-loaded}:\
\[\
\\int*{\\gamma_2} f(z) \\dz\
&= \\int*{-R}\^{-\\eps} f(t) \\dt \\qquad z=t+0i, \\dz=\\dt \\\
&= \\int*{-R}\^{-\\eps} {\\log(t) \\over t\^2 + 1}\\dt \\\
&= -\\int*{R}\^{\\eps} {\\log(-x) \\over (-x)\^2 + 1 }\\dx \\qquad t=-x,
\\dt = -\\dx \\\
&= \\int\_{\\eps}\^{R} {\\log(x) + i\\pi \\over x\^2 + 1 }\\dx \\\
&= I + i\\pi \\cdot {\\pi \\over 2} \\\
&= I + {i\\pi\^2\\over 2}\
,\]\
using the known antiderivative [$\arctan$]{.math .math-inline
.is-loaded}.

Note that there are two simple poles at [$\pm i$]{.math .math-inline
.is-loaded}, so only the residue at [$z_{0} = i$]{.math .math-inline
.is-loaded} contributes:\
\[\
\\Res*{z=i} = \\lim*{z\\to i} {\\log(z) \\over (z+i)} = {\\log(i) \\over
2i} = {i\\pi/2 \\over 2i} = {\\pi \\over 4}\
,\]\
so by the residue theorem,\
\[\
2\\pi i \\Res*{z=i}f(z) = \\int*{\\Gamma}f(z) \\dz = \\qty{
\\int\_{\\gamma_1} + \\int{\\gamma_2}}f = 2I + {i\\pi\^2 \\over 2} \\\
\\implies 2\\pi i \\cdot {\\pi \\over 4} = I + {i\\pi\^2\\over 2} \\\
\\implies {i\\pi\^2\\over 4} = I + {i\\pi\^2\\over 4} \\\
\\implies I = 0\
.\]

:::

:::{.exercise title=\"[$\log(x)/(1 + x^{2})^{2}$]{.math .math-inline
.is-loaded}\"}\
\[\
I\\da \\int_0\^\\infty {\\log(x) \\over (1+x\^2)\^2}\\dx = -{\\pi \\over
4}\
.\]

\#completed

:::

:::{.solution title=\"Semicircle, real reduction trick\"}\
Let [$f$]{.math .math-inline .is-loaded} be the integrand, then
[$f \sim \log(z)/(z^{4} + 1)$]{.math .math-inline .is-loaded}, so an
indented semicircular contour will work since
[$\text{\textbackslash abs}f \rightarrow 0$]{.math .math-inline
.is-loaded} as [$\text{\textbackslash abs}{z \rightarrow \infty}$]{.math
.math-inline .is-loaded}, and the inner integral will be dominated by a
term of the form
[$\varepsilon\log(\varepsilon)/\varepsilon^{4} \rightarrow 0$]{.math
.math-inline .is-loaded} as [$\varepsilon \rightarrow 0$]{.math
.math-inline .is-loaded}.\
So take such a contour, branch cutting along [$\theta = - \pi/2$]{.math
.math-inline .is-loaded}:

::: {.internal-embed src="figures/2021-12-22_05-21-05.png"}
:::

Now consider the contribution from [$\gamma_{2}$]{.math .math-inline
.is-loaded}:\
\[\
\\int*{\\gamma_2} f(z) \\dz\
&= \\int*{-R}\^{-\\eps} f(t+0i) \\dt \\\
&= \\int*{-R}\^{-\\eps} {\\log(t) \\over (t\^2 + 1)\^2 }\\dt \\\
&= -\\int*{R}\^{\\eps} {\\log(-x) \\over ((-x)\^2 + 1)\^2 }\\dx \\\
&= \\int*{\\eps}\^{R} {\\ln\\abs{x} + i\\pi \\over (x\^2 + 1)\^2 }\\dx
\\\
&\\to I + i\\pi \\int*{0}\^\\infty {1\\over (x\^2 + 1)\^2}\\dx\
.\]\
This auxiliary integral can be handled easily with a usual semicircular
contour, since the integrand is [$\mathsf{O}(x^{4})$]{.math .math-inline
.is-loaded}:\
\[\
\\int*{0}\^\\infty {1\\over (z\^2 + 1)}\\dx\
&= 2\\pi i \\sum*{z*k\\in \\HH}\\Res*{z=z*k} {1\\over (z\^2 + 1)} \\\
&= 2\\pi i \\Res*{z=i} {1\\over (z\^2 + 1)} \\\
&= 2\\pi i \\lim*{z\\to i} \\dd{}{z} {1\\over (z+i)\^2} \\\
&= 2\\pi i \\cdot {-2\\over (2i)\^3 } \\\
&= 2\\pi i \\cdot {-i\\over 4} \\\
&= {\\pi \\over 2}\
.\]\
Computing the residue of the main integral:\
\[\
2\\pi i \\Res*{z=i} f(z)\
&= 2\\pi i \\lim*{z\\to i} \\dd{}{z} { \\log(z) \\over (z+i)\^2} \\\
&= 2\\pi i \\lim*{z\\to i} { (z+i)\^2 z\\inv - 2(z+i)\\log(z) \\over
(z+i)\^4 } \\\
&= 2\\pi i { -i(2i)\^2 - 2(2i)\\qty{i\\pi \\over 2} \\over (2i)\^4 } \\\
&= \\pi i { 2i + \\pi \\over 2\^2 }\\\
&= -{\\pi \\over 2} + {i\\pi\^2 \\over 4}\
.\]\
Combining all of this:\
\[\
2\\pi i \\Res*{z=i} f(z) = \\int*\\Gamma f(z) \\dz =
\\qty{\\int*{\\gamma_1} + \\int*{ \\gamma_2} } f\
= I + \\qty{I + {i\\pi\^2\\over 4}} \\\
\\implies -{\\pi \\over 2} + {i\\pi\^2 \\over 4} = 2I + {i\\pi\^2\\over
4} \\\
\\implies -{\\pi\\over 2} = 2I \\\
implies I = -{\\pi \\over 4}\
.\]

:::

:::{.solution title=\"Log squaring trick\"}\
Factor [$(1 + z^{2})^{2} = (z + i)^{2}(z - i)^{2}$]{.math .math-inline
.is-loaded}.\
Apropos of nothing, considering the auxiliary function\
\[\
g(z) \\da \\qty{\\log(z) \\over 1+x\^2}\^2 = {\\log\^2(z) \\over
(1+x\^2)\^2}\
.\]\
Use a keyhole contour for a branch cut along [$\theta = - \pi$]{.math
.math-inline .is-loaded}, so [${Arg}(z) \in ( - \pi,\pi)$]{.math
.math-inline .is-loaded}:

-   [$\gamma_{+}:\left\{ {t + i\varepsilon{\ |\ }t \in \lbrack - \varepsilon, - R\rbrack} \right\}$]{.math
    .math-inline .is-loaded},
-   [$\gamma_{\varepsilon}:\left\{ {\varepsilon e^{it}{\ |\ }t \in \lbrack - \pi + \varepsilon,\pi - \varepsilon\rbrack} \right\}$]{.math
    .math-inline .is-loaded},
-   [$\gamma_{+}:\left\{ {t - i\varepsilon{\ |\ }t \in \lbrack - \varepsilon, - R\rbrack} \right\}$]{.math
    .math-inline .is-loaded},
-   [$\gamma_{R}:\left\{ {Re^{it}{\ |\ }t \in \lbrack - \pi + \varepsilon,\pi - \varepsilon\rbrack} \right\}$]{.math
    .math-inline .is-loaded},

and [$\Gamma$]{.math .math-inline .is-loaded} the combined contour
oriented counterclockwise.\
Note the symmetry:\
\[\
\\int*{\\gamma*+}g(z)\
&= \\int*{-R}\^{-\\eps} { \\log\^2(t) \\over (t\^2 +1)\^2 } \\dt \\\
&= - \\int*{-eps}\^{-R} { \\log\^2(t) \\over (t\^2 +1)\^2 } \\dt \\\
&= \\int*{\\eps}\^{R} { \\log\^2(e\^{i\\pi} s) \\over ( ( e\^{i\\pi}
s)\^2 +1)\^2 } \\ds && t = e\^{i\\pi}s,, \\ds = -\\dt \\\
&= \\int*{\\eps}\^{R} { \\qty{ \\log(s) + i\\pi}\^2 \\over (s\^2 +1)\^2
} \\ds \\\
,\]\
and similarly\
\[\
\\int*{\\gamma*-}g(z)\
&= \\int*{-\\eps}\^{-R} { \\log\^2(t) \\over (t\^2 +1)\^2 } \\dt \\\
&= -\\int*{\\eps}\^{R} { \\log\^2(e\^{-i\\pi} s) \\over ((e\^{-i\\pi}
s)\^2 +1)\^2 } \\ds && t=e\^{-i\\pi }s,, \\dt = -\\ds \\\
&= -\\int*{\\eps}\^{R} { \\qty{ \\log(s) - i\\pi}\^2 \\over (s\^2 +1)\^2
} \\dt \\\
.\]\
Now note that\
\[\
(\\log(s) + i\\pi)\^2 - (\\log(s) - i\\pi)\^2\
&= \\cdots \\\
&= \\qty{\\log\^2(s) + 2i\\pi \\log(s) - \\pi\^2 } - \\qty{\\log\^2(s)
-2i\\pi\\log(s) - \\pi\^2} \\\
&= 4i\\pi\\log(s)\
,\]\
and so miraculously\
\[\
\\int*{\\gamma*+}f(z)\\dz + \\int*{\\gamma*-}f(z)\\dz\
&= \\int*{\\eps}\^{R} { \\qty{ \\log(s) + i\\pi}\^2 \\over (s\^2 +1)\^2
} \\ds - \\int*{\\eps}\^{R} { \\qty{ \\log(s) - i\\pi}\^2 \\over (s\^2
+1)\^2 } \\dt \\\
&= \\int*\\eps\^R { \\qty{ \\log(s) + i\\pi}\^2 - \\qty{ \\log(s) -
i\\pi}\^2 \\over (s\^2+1)\^2 }\\ds \\\
&= 4i\\pi \\int*{\\eps}\^R {\\log(s) \\over (s\^2+1)\^2}\\ds \\\
&\\too 4i \\pi I\
.\]\
The contributions from [$\gamma_{R}$]{.math .math-inline .is-loaded}
vanish since [$\frac{\log(z)}{z^{4}} \rightarrow 0$]{.math .math-inline
.is-loaded} as [$\text{\textbackslash abs}z \rightarrow \infty$]{.math
.math-inline .is-loaded}, and the contribution from \$\\gamma*\\eps\$
vanish since
[$\frac{\varepsilon\log(\varepsilon)}{\varepsilon^{4} + c} \rightarrow 0$]{.math
.math-inline .is-loaded} as [$\varepsilon \rightarrow 0$]{.math
.math-inline .is-loaded} (and applying the ML estimate).\
Thus\
\[\
2\\pi i \\sum*{z_k\\in \\CC}\\Res*{z=z*k}g(z) = \\int*\\Gamma g(z) \\dz
= 4i\\pi I\
.\]\
Factoring the denominator as
[$(1 + z^{2})^{2} = (z - i)^{2}(z + i)^{2}$]{.math .math-inline
.is-loaded}, there are two order 2 poles at [$\pm i$]{.math .math-inline
.is-loaded}.\
At [$z = i$]{.math .math-inline .is-loaded}:\
\[\
\\Res*{z=i}g(z)\
&= \\lim*{z\\to i} \\dd{}{z} {\\log\^2(z) \\over (z+i)\^2} \\\
&= \\lim*{z\\to i} {(z+i)\^2 2\\log(z)z\\inv - \\log\^2(z) 2(z+i) \\over
(z+i)\^4} \\\
&= 2\^{-4}\\qty{(2i)\^2 \\cdot 2 \\cdot {i\\pi \\over 2} {1\\over i} -
\\qty{i\\pi \\over 2}\^2 \\cdot 2 \\cdot 2i} \\\
&= 2\^{-4}\\qty{2\^3 i\^2 {\\pi \\over 2} - 2\^{-2}i\^2 \\pi\^2 2\^2 i}
\\\
&= 2\^{-4}\\qty{-2\^2\\pi + i\\pi \^2} \\\
&= r_1 \\da - {\\pi \\over 4} + i {\\pi\^2\\over 16}\
.\]\
Similarly,\
\[\
\\Res*{z=-i}g(z)\
&= \\lim*{z\\to -i} \\dd{}{z} {\\log\^2(z) \\over (z+i)\^2} \\\
&= \\lim*{z\\to -i} {(z-i)\^2 2\\log(z) z\\inv - \\log\^2(z) 2(z-i)
\\over (z-i)\^4} \\\
&= 2\^{-4} \\qty{ (-2i)\^2 \\cdot 2 \\qty{-i\\pi \\over 2}{1\\over -i} -
\\qty{-i\\pi\\over 2}\^2 \\cdot 2(-2i) } \\\
&= 2\^{-4} \\qty{ 2\^2 i\^2 \\pi - 2\^{-2} \\pi\^2 (-4i) }\\\
&= 2\^{-4}\\qty{-2\^2\\pi - \\pi\^2} \\\
&= r_2 \\da -{\\pi \\over 4} - i {\\pi\^2\\over 16}\
.\]\
Solving for [$I$]{.math .math-inline .is-loaded} above, we have\
\[\
I &= {2\\pi i \\over 4\\pi i}(r_1 + r_2) \\\
&= {1\\over 2} \\qty{- {\\pi \\over 4} - {\\pi \\over 4}} \\\
&= -{\\pi \\over 4}\
.\]\
:::

:::{.exercise title=\"[$\log(x)/x^{2} + a^{2}$]{.math .math-inline
.is-loaded}\"}\
\[\
\\int_0\^\\infty {\\log(x) \\over x\^2+a\^2}\\dx &= {\\pi\\log(a)\\over
2a} && a\>0\
.\]

\#completed

:::

:::{.solution title=\"Semicircle monodromy\"}\
Note that the poles are at [$z = \pm ia$]{.math .math-inline
.is-loaded}, and since
[$\lim\limits_{\text{\textbackslash abs}z \rightarrow \infty}f(z) = 0$]{.math
.math-inline .is-loaded} and
[$\lim{R \rightarrow 0}\frac{R\log(R)}{R^{2} + a^{2}} = 0$]{.math
.math-inline .is-loaded}, an indented semicircular contour will work.

::: {.internal-embed src="figures/2021-12-26_20-04-14.png"}
:::

Computing the contribution from the residues:\
\[\
\\Res*{z=ia}f(z)\
&= \\lim*{z\\to ia }{\\log(z) \\over (z+ia)} \\\
&= {\\log(ia) \\over 2ia} \\\
&= {\\log(a) + i\\pi/2 \\over 2ia} \\\
&= {\\pi \\over 4a} + {\\log(a) \\over 2ia} \\ \\\
\\implies 2\\pi i \\Res*{z=ia}f(z)\
&= {i\\pi\^2 \\over 2a} + {\\pi\\log(a) \\over a}\
.\]\
The contribution from the integrals will come from
\$\\qty{\\int*{\\gamma*1} + \\int*{\\gamma_2}}f\$ where

-   [$\gamma_{1}{: =}\left\{ {tR + (1 - t)\varepsilon{\ |\ }t \in \lbrack\varepsilon,R\rbrack} \right\}$]{.math
    .math-inline .is-loaded}
-   [$\gamma_{2}{: =}\left\{ {t( - \varepsilon) + (1 - t)( - R){\ |\ }t \in \lbrack\varepsilon,R\rbrack} \right\}$]{.math
    .math-inline .is-loaded},

so that the overall contour is oriented counterclockwise.\
Noting that [$\int_{\gamma_{1}}f(z)\, dz \rightarrow I$]{.math
.math-inline .is-loaded} the desired integral, the other contribution
is\
\[\
\\int*{\\gamma_2}f(z)\\dz\
&= \\int*{-R}\^{-\\eps} {\\log(t)\\over t\^2 + a\^2}\\dt \\\
&= - \\int*{-\\eps}\^{-R} {\\log(t) \\over t\^2+a\^2} \\dt \\\
&= \\int*{\\eps}\^{R} {\\log(-x) \\over x\^2+a\^2} \\dt \\qquad x=-t,,
\\dx = -\\dt\\\
&= \\int*\\eps\^R {\\log(x) \\over x\^2 + a\^2}\\dx + i\\pi
\\int*\\eps\^R {1\\over x\^2 +a\^2}\\dx \\\
&= I + i\\pi\\qty{\\pi \\over 2a}\
.\]\
In the limit, by the residue theorem we have\
\[\
{i\\pi\^2 \\over 2a} + {\\pi\\log(a) \\over a}\
&= 2I + i\\pi\\qty{\\pi \\over 2a} \\\
\\implies I &= {\\pi \\log(a) \\over 2a}\
.\]\
:::

:::{.exercise title=\"[$\log(z)/1 + z^{a}$]{.math .math-inline
.is-loaded}\"}\
\[\
I\\da \\int_0\^\\infty {\\log(x) \\over 1+x\^a}\\dx\
&= - \\qty{\\pi \\over a}\^2\\cos\\qty{\\pi\\over a}\\csc\^2\\qty{\\pi
\\over a} \\\
&= - {\\pi\^2\\over a\^2} {\\cos\\qty{\\pi\\over a} \\over
\\sin\^2\\qty{\\pi\\over a}}\
.\]

\#completed

:::

:::{.solution title=\"Sector monodromy\"}\
For the usual reasons, integrals along semicircles of radius [$R$]{.math
.math-inline .is-loaded} and [$\varepsilon$]{.math .math-inline
.is-loaded} go to zero, so noting the poles at
[$\omega_{a}{: =}e^{\frac{i\pi}{a}}$]{.math .math-inline .is-loaded},
take an indented sector:

::: {.internal-embed src="figures/2021-12-22_05-25-35.png"}
:::

Set [$\zeta_{a}{: =}e^{\frac{2\pi i}{a}}$]{.math .math-inline
.is-loaded}.\
Contributions from the contours: let [$\gamma_{1}$]{.math .math-inline
.is-loaded} be the contour along [$\mathbb{R}$]{.math .math-inline
.is-loaded} and [$\gamma_{2}$]{.math .math-inline .is-loaded} along
[$\zeta_{a}\mathbb{R}$]{.math .math-inline .is-loaded}, oriented so the
overall contour is counterclockwise.\
Then [$\int_{\gamma_{1}}f(z)\, dz \rightarrow I$]{.math .math-inline
.is-loaded} for [$f(z){: =}\frac{\log(z)}{1 + z^{a}}$]{.math
.math-inline .is-loaded}, so compute the monodromy term: parameterize
[$\gamma_{2}{: =}\left\{ {\zeta_{a}t{\ |\ }t \in \lbrack\varepsilon,R\rbrack} \right\}$]{.math
.math-inline .is-loaded}, so\
\[\
\\int*{\\gamma_2}f(z) \\dz\
&=\\int_R\^\\eps f(\\zeta_a t) \\zeta_a \\dt \\\
&= -\\zeta_a \\int*\\eps\^R {\\log(\\zeta*a t) \\over (\\zeta_a t)\^a +
1}\\dt \\\
&= -\\zeta_a \\int*{\\eps}\^R {\\log(z) + {2\\pi i \\over a} \\over
t\^a+1}\\dt \\\
&\\to -\\zeta_a I - \\zeta_a {2\\pi i \\over a} \\int_0\^\\infty
{1\\over t\^a + 1 }\\dt \\\
&\\da -\\zeta_a I - {2\\pi i\\over a}\\zeta_a I\'\
.\]

:::{.claim}\
\[\
I\' = {\\pi\\over a}\\csc\\qty{\\pi\\over a}\
.\]\
:::

:::{.proof title=\"?\"}\
Computing the auxiliary integral [$I^{\prime}$]{.math .math-inline
.is-loaded}:\
the integrand has the same pole at [$\omega_{a}$]{.math .math-inline
.is-loaded}, so apply the same technique.\
Write [$g(z){: =}\frac{1}{z^{a} + 1}$]{.math .math-inline .is-loaded}.

The contributions from the contours:\
\[\
\\qty{ \\int*{\\gamma_1} + \\int*{\\gamma_2}} g(z) \\to (1-e\^{2\\pi i
})I\' = -2i\\sin\\qty{\\pi\\over a}e\^{i\\pi\\over a}\
,\]\
using the exponential balancing trick.

Computing the residue:\
\[\
\\Res*{z=e\^{i\\pi\\over a}}g(z)\
&= {1\\over az\^{a-1}}\\evalfrom*{z=e\^{i\\pi\\over a}} = {1\\over
ae\^{i\\pi\\qty{a-1\\over a}}} = {1\\over a e\^{i\\pi} e\^{-i\\pi\\over
a}} \\\
\\implies 2\\pi i \\Res\_{z=e\^{i\\pi\\over a}}g(z)\
&= -{2\\pi i \\over a}e\^{i \\pi \\over a}\
.\]

Combining and solving:\
\[\
I\' = { - {2\\pi i\\over a} e\^{i\\pi \\over a} \\over
-2i\\sin\\qty{\\pi\\over a}e\^{i\\pi\\over a}} = {\\pi \\over
a}\\csc\\qty{\\pi \\over a}\
.\]\
:::

Given this, the RHS of the residue theorem limits to\
\[\
(1-\\zeta_a) I - {2\\pi i\\over a}\\zeta_a \\qty{ {\\pi \\over
a}\\csc\\qty{\\pi\\over a} }\
= (1-\\zeta_a) I - {2\\pi\^2\\over a\^2}i\\zeta_a \\csc\\qty{\\pi\\over
a}\
.\]

For the LHS, we compute the residue at [$\omega_{a}$]{.math .math-inline
.is-loaded}:\
\[\
\\Res*{z=\\omega_a} f(z)\
&= \\lim*{z\\to \\omega*a} {(z-\\omega_a) \\log(z) \\over z\^a + 1} \\\
&\\eqLH \\lim*{z\\to \\omega*k} {\\log(z) \\over az\^{a-1}}\\\
&= {\\log\\qty{e\^{i\\pi \\over a}} \\over ae\^{i\\pi \\qty{a-1\\over
a}} } \\\
&= -{i\\pi /a \\over ae\^{- i\\pi \\over a} } \\\
&= -{i\\pi \\over a\^2} e\^{i\\pi\\over a}\
,\]\
so\
\[\
2\\pi i \\Res*{z=\\omega_a} f(z) = -2\\pi i \\qty{i\\pi\\over
a\^2}e\^{i\\pi \\over a}\
= {2\\pi\^2\\over a\^2}e\^{i\\pi\\over a}\
.\]

After some truly arduous arithmetic, this assembles to:\
\[\
{2\\pi\^2\\over a\^2}e\^{i\\pi\\over a}\
&= (1-\\zeta_a) I - {2\\pi\^2\\over a\^2}i\\zeta_a \\csc\\qty{\\pi\\over
a} \\ \\\
\\implies\
{2\\pi\^2\\over a\^2}e\^{i\\pi\\over a}\
&= (1-e\^{2\\pi i\\over a}) I - {2\\pi\^2\\over a\^2}ie\^{2\\pi i \\over
a} \\csc\\qty{\\pi\\over a} \\ \\\
\\implies\
{2\\pi\^2\\over a\^2}\
&= (e\^{-{i\\pi\\over a}}-e\^{\\pi i\\over a}) I - {2\\pi\^2\\over
a\^2}ie\^{\\pi i \\over a} \\csc\\qty{\\pi\\over a} \\ \\\
&= -2i\\sin\\qty{\\pi\\over a}I - {2\\pi\^2\\over a\^2}ie\^{\\pi i
\\over a} \\csc\\qty{\\pi\\over a} \\ \\\
\\implies\
I\
&= { {2\\pi\^2\\over a\^2} + {2\\pi\^2\\over a\^2}ie\^{\\pi i \\over a}
\\csc\\qty{\\pi\\over a} \\over -2i\\sin\\qty{\\pi \\over a} } \\\\\
&= {2\\pi\^2\\over a\^2} \\qty{ 1 + ie\^{\\pi i \\over a}
\\csc\\qty{\\pi\\over a} \\over -2i\\sin\\qty{\\pi \\over a} } \\ \\\
&= -{\\pi\^2\\over a\^2}\\csc\\qty{\\pi\\over a} \\cdot (-i)\\qty{1 +
ie\^{i\\pi\\over a}\\csc\\qty{\\pi\\over a}} \\ \\\
&= -{\\pi\^2\\over a\^2}\\csc\\qty{\\pi\\over a} \\qty{ -i +
\\qty{\\cos\\qty{\\pi\\over a} +i\\sin\\qty{\\pi\\over
a}}\\csc\\qty{\\pi\\over a}} \\ \\\
&= -{\\pi\^2\\over a\^2}\\csc\\qty{\\pi\\over a} \\qty{-i +
\\cot\\qty{\\pi\\over a} + i } \\ \\\
&= -{\\pi\^2\\over a\^2}\\csc\\qty{\\pi\\over a} \\cot\\qty{\\pi\\over
a} \\\
&= -{\\pi\^2\\over a\^2}\\cos\\qty{\\pi\\over a}
\\csc\^2\\qty{\\pi\\over a} \\\
.\]

:::

### Power Functions {#power-functions heading="Power Functions"}

:::{.exercise title=\"[$x^{\alpha}/(x + 1)^{2}$]{.math .math-inline
.is-loaded}\"}\
\[\
I \\da \\int_0\^\\infty {x\^\\alpha \\over (x+1)\^2}\\dx && 0 \< \\alpha
\< 2\
.\]

\#completed

:::

:::{.solution title=\"Keyhole contour\"}\
Note the single pole of order 2 at [$z = - 1$]{.math .math-inline
.is-loaded}, and also the branch singularity.\
Choose a branch cut of [$\log$]{.math .math-inline .is-loaded} by
deleting [$\theta = 0$]{.math .math-inline .is-loaded}, and take a
keyhole contour.

::: {.internal-embed alt="Keyhole contour" src="figures/2021-12-24_04-00-31.png"}
:::

Write the contours as

-   [$\gamma_{\varepsilon} = \left\{ {\varepsilon e^{it}{\ |\ }t \in \lbrack 0 + \varepsilon,2\pi - \varepsilon\rbrack} \right\}$]{.math
    .math-inline .is-loaded}
-   [$\gamma_{+} = \left\{ {x + i\varepsilon{\ |\ }x \in \lbrack\varepsilon,R\rbrack} \right\}$]{.math
    .math-inline .is-loaded}
-   [$\gamma_{R} = \left\{ {Re^{it}{\ |\ }t \in \lbrack 0 + \varepsilon,2\pi - \varepsilon\rbrack} \right\}$]{.math
    .math-inline .is-loaded}
-   [$\gamma_{-} = \left\{ {x - i\varepsilon{\ |\ }t \in \lbrack\varepsilon,R\rbrack} \right\}$]{.math
    .math-inline .is-loaded},

all oriented so that the total curve [$\Gamma$]{.math .math-inline
.is-loaded} is traversed counter-clockwise.

The claim is that
[$\int_{\gamma_{\varepsilon}}f,\int_{\gamma_{R}}f \rightarrow 0$]{.math
.math-inline .is-loaded}, and [$\int_{\gamma_{+}}f$]{.math .math-inline
.is-loaded} is a multiple of [$\int\gamma_{-}f$]{.math .math-inline
.is-loaded}.\
For [$z = x - i\varepsilon$]{.math .math-inline .is-loaded} on
[$\gamma_{-}$]{.math .math-inline .is-loaded}, we have\
\[\
\\log(z) = \\log(x-i\\eps) = \\ln\\abs{x-i\\eps} +
i\\Arg(x-i\\eps)\\convergesto{\\eps\\to 0} \\ln\\abs{x} + 2\\pi i =
e\^{2\\pi i}z\
,\]\
and\
\[\
f(e\^{2\\pi i}z) = {(e\^{2\\pi i}z)\^\\alpha \\over ((e\^{2\\pi
i}z)\^2+1)\^2 } = e\^{2\\pi i\\alpha } {z \\over z\^2+1} = e\^{2\\pi
i\\alpha}f(z)\
.\]\
Thus\
\[\
\\int*{\\gamma*-} f(z)\\dz\
&\\too \\int*R\^\\eps f(e\^{2\\pi i }z)\\dz \\\
&= \\int_R\^\\eps e\^{2\\pi i \\alpha}f(z)\\dz \\\
&= -e\^{2\\pi i \\alpha}\\int*\\eps\^R f(z)\\dz \\\
&= -e\^{2\\pi i\\alpha}\\int*{\\gamma*+}f(z)\\dz\
.\]

Thus in the limit,\
\[\
2\\pi i \\sum*{z_k\\in \\CC\\sm\\RR*{\\geq 0}} \\Res*{z=z_k}f(z)\
&= \\int*\\Gamma f(z)\\dz \\\
&= \\int*{\\gamma*+}f(z)\\dz + \\int*{\\gamma*-}f(z)\\dz \\\
&= (1-e\^{2\\pi i\\alpha})\\int*{\\gamma*+}f(z)\\dz \\\
&= (1-e\^{2\\pi i\\alpha})\\int\_{\\RR}f(z)\\dz \\\
.\]

Computing the residue at [$z_{0} = - 1$]{.math .math-inline
.is-loaded}:\
\[\
\\Res*{z=-1}f(z)\
&= \\lim*{z\\to -1} \\dd{}{z} (z+1)\^2 f(z) \\\
&= \\lim*{z\\to -1} \\dd{}{z} z\^\\alpha \\\
&= \\alpha (-1)\^{\\alpha - 1} \\\
&= \\alpha e\^{i\\pi(\\alpha - 1)} \\\
&= -\\alpha e\^{i\\pi \\alpha}\
.\]\
Thus\
\[\
\\int*\\RR f(z) \\dz\
&= 2\\pi i \\cdot {-\\alpha e\^{i\\pi \\alpha}\\over 1 - e\^{2\\pi i
\\alpha}} \\\
&=-2\\pi i \\alpha {1\\over e\^{-i\\pi\\alpha} (1- e\^{2\\pi i
\\alpha})} \\\
&=-2\\pi i \\alpha {1\\over e\^{-i\\pi\\alpha} - e\^{i\\pi\\alpha}} \\\
&=2\\pi i \\alpha {1\\over e\^{-i\\pi\\alpha} - e\^{-i\\pi\\alpha}} \\\
&= \\pi \\alpha \\csc(\\pi\\alpha)\
.\]

:::

:::{.exercise title=\"[$x^{?}/1 + x^{2}$]{.math .math-inline
.is-loaded}\"}\
\[\
I\\da \\int_0\^\\infty {x\^{1\\over 3} \\over 1 + x\^2} \\dx = {\\pi
\\over \\sqrt 3}\
.\]

\#completed

:::

:::{.solution title=\"Semicircle monodromy\"}\
Write [$f(z){: =}\frac{z^{\frac{1}{3}}}{z^{2} + 1}$]{.math .math-inline
.is-loaded}, the claim is that an indented semicircular contour will
work:

::: {.internal-embed src="figures/2021-12-26_20-04-14.png"}
:::

Why:\
after parameterizing [$C_{R}$]{.math .math-inline .is-loaded}, the
integrand is approximately
[$R \cdot R^{\frac{1}{3}}/R^{2} \sim R^{\frac{4}{3} - 2} = R{- \frac{2}{3}}$]{.math
.math-inline .is-loaded}, which goes to zero as
[$R \rightarrow \infty$]{.math .math-inline .is-loaded}.\
Similarly, on [$C_{\varepsilon}$]{.math .math-inline .is-loaded}, the
integrand is approximately
[$\varepsilon^{\frac{4}{3}}/(\varepsilon^{2} + 1)$]{.math .math-inline
.is-loaded}, which goes to zero as [$\varepsilon \rightarrow 0$]{.math
.math-inline .is-loaded}.

Note the poles at [$z = \pm i$]{.math .math-inline .is-loaded}.\
Computing the residue contribution at [$z = i$]{.math .math-inline
.is-loaded}:\
\[\
\\Res\_{z=i} f(z) &= {i\^{1\\over 3} \\over 2i} = {1\\over 2e\^{i\\pi
\\over 3}}\
.\]

Computing the contribution from the integrals: let [$\gamma_{1}$]{.math
.math-inline .is-loaded} be the contour along
[$\mathbb{R}_{\geq \varepsilon}$]{.math .math-inline .is-loaded}, and
[$\gamma_{2}$]{.math .math-inline .is-loaded} along
[$\mathbb{R}_{\leq \varepsilon}$]{.math .math-inline .is-loaded}.\
Noting that [$I = \int_{\gamma_{1}}f(z)\, dz$]{.math .math-inline
.is-loaded},\
\[\
\\int*{\\gamma_2}f(z)\\dz\
&= \\int*{-R}\^{-\\eps} { t\^{1\\over 3} \\over t\^2 +1 } \\dt \\\
&= -\\int*R\^\\eps {(-x)\^{1\\over 3} \\over x\^2+1}\\dx \\qquad x=-t,,
\\dx = -\\dt \\\
&= \\int*\\eps\^R {(\\zeta*2 x)\^{1\\over 3} \\over x\^2+1}\\dx \\\
&= \\zeta_2\^{1\\over 3} I \\\
&= e\^{i\\pi\\over 3}I\
,\]\
so \$\\qty{\\int*{\\gamma*1} + \\int*{\\gamma_2}} f\$ contributes
[$(1 + e^{\frac{i\pi}{3}})I$]{.math .math-inline .is-loaded}.\
By the residue theorem,\
\[\
2\\pi i \\cdot\
{1\\over 2e\^{i\\pi \\over 3} }\
&=\
(1+e\^{i\\pi \\over 3})I \\ \\\
\\implies\
I\
&= {i\\pi \\over 2e\^{i\\pi \\over 3} (1+e\^{i\\pi \\over 3}) } \\\
&= {i\\pi \\over 2} \\qty{ e\^{i\\pi \\over 3} + e\^{2i\\pi \\over 3}
}\\inv \\\
&= {i\\pi \\over 2} \\qty{ e\^{i\\omega} + e\^{2i\\omega} }\\inv,\\qquad
\\omega={\\pi\\over 3} \\\
&= {i\\pi \\over 2} \\qty{ e\^{3i\\omega\\over 2} \\qty{
e\^{-i\\omega\\over 2} + e\^{i\\omega\\over 2}} }\\inv \\\
&= i\\pi e\^{-3i\\omega\\over 2}{1\\over \\cos\\qty{\\omega\\over 2}}
\\\
&= i\\pi e\^{-i\\pi\\over 2 }{1\\over \\cos\\qty{\\pi \\over 6}} \\\
&= {\\pi \\over \\sqrt{3}}\
,\]\
where we\'ve used the \"exponential balancing trick\" (see complex
arithmetic section).\
:::

:::{.solution title=\"Keyhole monodromy\"}\
For the same reasons as in the semicircular solution, a keyhole will
work:

::: {.internal-embed alt="figures/2021-07-29_18-51-17.png" src="figures/2021-07-29_18-51-17.png"}
:::

The contributions from [$C_{2}$]{.math .math-inline .is-loaded}:\
\[\
\\int*{C_2}f(z) \\dz\
&= \\int_R\^\\eps { (t-i\\eps)\^{1\\over 3} \\over (t-i\\eps)\^2 + 1
}\\dt \\\
&= - \\int\^R*\\eps { e\^{{1\\over 3}\\qty{\\ln\\abs{t-i\\eps} +
i\\Arg(t-i\\eps) } } \\over (t-i\\eps)\^2 + 1 }\\dt \\\
&\\to - \\int\^R*\\eps { e\^{{1\\over 3}\\qty{\\ln\\abs{t} + 2\\pi i } }
\\over t\^2 + 1 }\\dt \\\
&= -\\int*\\eps\^R { e\^{2\\pi i \\over 3} t\^{1\\over 3} \\over t\^2 +
1}\\dt \\\
&= - \\zeta_3 I\
,\]\
so the contributions from the contours sums to
[$(1 - \zeta_{3}I)$]{.math .math-inline .is-loaded}.

The contributions from residues:\
\[\
\\Res\_{z=\\pm i} f(z)\
&= { (\\pm i)\^{1\\over 3} \\over \\pm 2i} \\cdot \\\
&= { (e\^{k\\pi \\over 2})\^{1\\over 3} \\over \\pm 2i},\\qquad k=1,3\\\
&= { e\^{k\\pi \\over 6} \\over \\pm 2i} \\\
&=\
\\begin{cases}\
{ e\^{\\pi\\over 6} \\over 2i} & z=i\
\\\
{e\^{3\\pi \\over 6} \\over -2i} = -{1\\over 2} & z=-i.\
\\end{cases}\
.\]\
So the contribution from the residue theorem is\
\[\
2\\pi i\\qty{ {e\^{\\pi\\over 6} \\over 2i} - {i\\over 2i} } =
\\pi\\qty{e\^{\\pi\\over 6} - 1}\
.\]

Solving for the integral:\
\[\
I\
&= {\\pi (e\^{\\pi \\over 6} - i) \\over 1 - e\^{2i\\pi \\over 3}} \\\
&=\\pi { e\^{i\\omega} - e\^{3i\\omega} \\over e\^{0i\\omega} -
e\^{4i\\omega}},\\qquad \\omega = {\\pi\\over 6} \\\
&= \\pi {e\^{2i\\omega} \\qty{e\^{-i\\omega} - e\^{i\\omega} } \\over
e\^{2i\\omega}\\qty{e\^{-2i\\omega} - e\^{2i\\omega} } } \\\
&= \\pi {-2i\\sin(\\omega) \\over -2i\\sin(2\\omega)} \\\
&= \\pi {\\sin\\qty{\\pi\\over 6} \\over \\sin\\qty{\\pi\\over 3}} \\\
&= \\pi{ 1/2\\over \\sqrt{3}/2}\\\
&= {\\pi \\over \\sqrt 3}\
.\]

:::

### Square Roots / Slits {#square-roots-slits heading="Square Roots / Slits"}

:::{.concept}\
\\envlist

-   The residue at [$\infty$]{.math .math-inline .is-loaded}: if
    [$\Gamma$]{.math .math-inline .is-loaded} is a positively oriented
    curve (counterclockwise about [$z = 0$]{.math .math-inline
    .is-loaded}), then\
    \[\
    \\Res*{z=\\infty}f(z) = -{1\\over 2\\pi i}\\oint*\\Gamma f(z)
    \\dz,\\quad \\Res*{z=\\infty}f(z) = \\Res*{z=0} -{1\\over
    z\^2}f\\qty{1\\over z}\
    .\]
-   Slits: for
    [$f(z) = \sqrt{(z - z_{1})(z - z_{2})\cdots(z - z_{n})}$]{.math
    .math-inline .is-loaded}, one needs to introduce slits that disallow
    winding around an odd number of the branch points [$z_{k}$]{.math
    .math-inline .is-loaded}.
    -   Be sure to check to see if [$z = \infty$]{.math .math-inline
        .is-loaded} is a branch point!
-   A standard argument: for [$f(z) = \sqrt{z}$]{.math .math-inline
    .is-loaded}, take a path [$\gamma(t) = e^{2\pi it}$]{.math
    .math-inline .is-loaded} for [$t \in \lbrack 0,1\rbrack$]{.math
    .math-inline .is-loaded}.\
    Then [$f(\gamma(0)) = f(z)$]{.math .math-inline .is-loaded} and
    [$f(\gamma(1)) = \sqrt{e^{2\pi i}z} = e^{i\pi}\sqrt{z} = - \sqrt{z}$]{.math
    .math-inline .is-loaded}, so the monodromy/phase factor introduced
    by square roots is [$- 1$]{.math .math-inline .is-loaded}.

:::

:::{.exercise title=\"[$\sqrt{x^{2} - 1}$]{.math .math-inline
.is-loaded} \"}\
\[\
I\\da \\int\_{-1}\^1 \\sqrt{1-x\^2} \\dx = {\\pi \\over 2}\
.\]

\#completed

:::

:::{.solution title=\"Dogbone and residue at [$\infty$]{.math
.math-inline .is-loaded}\"}\
Take a branch cut [$\lbrack - 1,1\rbrack$]{.math .math-inline
.is-loaded} and [$\Gamma$]{.math .math-inline .is-loaded} the standard
dogbone contour:

::: {.internal-embed src="figures/2021-12-28_01-50-50.png"}
:::

Orient [$\Gamma$]{.math .math-inline .is-loaded} positively about
*infinity*, i.e. counterclockwise.

Contribution from
[$\gamma_{1}{: =}\left\{ {t + i\varepsilon{\ |\ }t \in \lbrack - 1,1\rbrack} \right\}$]{.math
.math-inline .is-loaded}, the upper horizontal piece:\
\[\
\\int*{\\gamma_1}f(z)\\dz \\to \\int*{-1}\^1 \\sqrt{1-t\^2} \\dt = I\
.\]

Contribution from
[$\gamma_{2}{: =}\left\{ {t - i\varepsilon{\ |\ }t \in \lbrack - 1,1\rbrack} \right\}$]{.math
.math-inline .is-loaded}, the lower horizontal piece:\
note that following [$e^{2\pi it}z$]{.math .math-inline .is-loaded} to
[$t = 1$]{.math .math-inline .is-loaded} sends [$\sqrt{z}$]{.math
.math-inline .is-loaded} to [$- \sqrt{z}$]{.math .math-inline
.is-loaded}, so\
\[\
\\int*{\\gamma_2}f(z)\\dz \\to \\int*{1}\^{-1} - \\sqrt{1-t\^2} \\dt =
I\
.\]

Contributions from the circles: use that
[$f(z){: =}\sqrt{z^{2} - 1}$]{.math .math-inline .is-loaded} is a
continuous function and these arcs are compact, so they are uniformly
bounded.\
Thus [$\int f \rightarrow 0$]{.math .math-inline .is-loaded} by the ML
estimate on these arcs.

The total contribution:\
\[\
\\qty{\\int*{\\gamma_1} + \\int*{\\gamma_2}} f = 2I\
.\]

The residue at infinity:\
\[\
\\Res*{z=\\infty}f(z)\
&= \\Res*{z=0} - {1\\over z\^2}\\sqrt{1 - {1\\over z\^2}} \\\
&= \\Res*{z=0} - {1\\over z\^2}\\sqrt{z\^2-1 \\over z\^2} \\\
&= \\Res*{z=0} - {i\\over z\^3}\\sqrt{1-z\^2} \\\
&= \\Res*{z=0} - {i\\over z\^3}\\sum*{k\\geq 0} {1/2\\choose k}z\^{2k}
\\\
&= \\Res\_{z=0} - {i\\over z\^3} \\qty{1 - {1\\over 2}z\^2 -
\\bigo(z\^3) } \\\
&= {i\\over 2}\
,\]\
thus\
\[\
2\\pi i \\cdot -{i\\over 2} = 2I \\implies I = {\\pi \\over 2}\
.\]\
:::

:::{.exercise title=\"[$1/\sqrt{x^{2} - 1}$]{.math .math-inline
.is-loaded} \"}\
\[\
I \\da \\int_0\^1 {1\\over \\sqrt{x\^2-1}}\\dx = {i\\pi \\over 2}\
.\]

\#completed

:::

:::{.solution}\
Write [$f(z) = \sqrt{z^{2} - 1} = \sqrt{(z + 1)(z - 1)}$]{.math
.math-inline .is-loaded}.\
First note [$f$]{.math .math-inline .is-loaded} is even, so\
\[\
I = {1\\over 2}I\',\\qquad I\' \\da \\int\_{-1}\^1 {1\\over
\\sqrt{z\^2-1}} \\dz\
.\]

Each branch point [$\pm 1$]{.math .math-inline .is-loaded} introduces a
monodromy factor of [$\sqrt{e^{2i\pi}} = e^{i\pi} = - 1$]{.math
.math-inline .is-loaded}, which cancel provided loops are not able to
encircle a single branch point.\
So take the branch cut to be the slit [$\lbrack - 1,1\rbrack$]{.math
.math-inline .is-loaded}, forcing any loop to encircle neither or both
of [$\pm 1$]{.math .math-inline .is-loaded} \-- now use a dogbone
contour [$\Gamma$]{.math .math-inline .is-loaded} around the slit and
apply the residue theorem to the *exterior* region:

::: {.internal-embed src="figures/2021-12-28_00-37-42.png"}
:::

The contribution from the top segment [$\gamma_{1}$]{.math .math-inline
.is-loaded}:\
\[\
\\int*{\\gamma_1}f(z)\\dz \\to \\int_1\^{-1} {1\\over
\\sqrt{x\^2-1}}\\dx = -I\'\
.\]\
The contribution from the bottom segment [$\gamma_{2}$]{.math
.math-inline .is-loaded}:\
a monodromy factor of [$- 1$]{.math .math-inline .is-loaded} is
introduced to [$g(z){: =}\sqrt{z}$]{.math .math-inline .is-loaded} over
a path that traces an angle of [$2\pi$]{.math .math-inline .is-loaded},
so\
\[\
\\int*{\\gamma*2}f(z)\\dz = \\int*{-1}\^1 {1\\over -\\sqrt{x\^2-1}} =
-I\'\
.\]

These combine to contribute\
\[\
\\qty{\\int*{\\gamma_1} + \\int*{\\gamma_2}}f = -2I\'\
.\]

Note \-- we\'ll want the contour to actually be positively oriented with
respect to [$z = \infty$]{.math .math-inline .is-loaded}, so we should
reverse the orientation of [$\Gamma$]{.math .math-inline .is-loaded} to
get a total contribution to [$2I$]{.math .math-inline .is-loaded}
instead.

The contribution from the small circles:\
parameterize the first as [$- 1 + Re^{2\pi it}$]{.math .math-inline
.is-loaded}, then\
\[\
\\abs{ \\int*{C*\\eps\^1}f(z)\\dz} = \\abs{\\int_0\^1 {2\\pi i R
e\^{2\\pi i t}\\over \\sqrt{ (-1 + R e\^{2\\pi i t} )\^2 - 1 } } \\dt}
\\sim \\int_0\^1 {R\\over \\sqrt{R\^2-1}} \\dt \\convergesto{R\\to 0} 0\
.\]\
A similar bound works for the second circle using the parameterization
[$1 + Re^{2\pi it}$]{.math .math-inline .is-loaded}.

Contributions from residues: take the residue at infinity,\
\[\
\\Res*{z=\\infty}f(z)\
&= \\Res*{z=0}-{1\\over z\^2}f\\qty{1\\over z} \\\
&= \\Res*{z=0} {-1\\over z\^2\\sqrt{z\^{-2} - 1 }} \\\
&= \\Res*{z=0} {-1\\over z\\sqrt{1-z\^2}} \\\
&= \\lim\_{z\\to 0} {-1\\over \\sqrt{1-z\^2}}\\\
&= -1\
.\]

Putting this together\
\[\
-2\\pi i \\Res*{z=\\infty}f(z)\
&= \\oint*\\Gamma f(z)\\dz = 2I\' \\\
\\implies 2\\pi i &= 2I\' \\\
\\implies \\pi i &= I\' = 2I \\\
\\implies I &= {i\\pi \\over 2}\
.\]\
:::

:::{.exercise title=\"[$1/(x - a)\sqrt{1 - x^{2}}$]{.math .math-inline
.is-loaded} \"}\
\[\
I \\da \\int\_{-1}\^1 {1\\over (x-a) \\sqrt{1-x\^2} }\\dx = {\\pi \\over
\\sqrt{a\^2-1}}\
.\]

\#completed

:::

:::{.solution title=\"T-bone\"}\
Note the simple pole at [$x = a$]{.math .math-inline .is-loaded} and the
branch points [$x = \pm 1$]{.math .math-inline .is-loaded}, coming from
factoring [$\sqrt{1 - z^{2}} = \sqrt{(1 - z)(1 + z)}$]{.math
.math-inline .is-loaded}.\
The standard dog bone contour will work, but will involve a residue at
[$z = a$]{.math .math-inline .is-loaded} and at [$z = \infty$]{.math
.math-inline .is-loaded}.\
Instead of taking the usual branch cut [$\lbrack - 1,1\rbrack$]{.math
.math-inline .is-loaded}, take instead
[$( - \infty, - 1\rbrack \cup \lbrack 1,\infty)$]{.math .math-inline
.is-loaded} and the following T-bone contour (noting that it is oriented
*negatively*):

::: {.internal-embed src="figures/2021-12-28_02-47-45.png"}
:::

Note that in the limit, the two vertical pieces cancel since there is no
phase introduced in [$f$]{.math .math-inline .is-loaded} when taking a
path from [$Q_{1}$]{.math .math-inline .is-loaded} to [$Q_{2}$]{.math
.math-inline .is-loaded}, and the two upper horizontal segment limit to
[$\gamma_{1}{: =}\left\{ {t + i\varepsilon{\ |\ }t \in \lbrack - 1,1\rbrack} \right\}$]{.math
.math-inline .is-loaded}.\
Also note that [$\int_{\gamma_{1}}f(z)\, dz \rightarrow I$]{.math
.math-inline .is-loaded}.

Let [$\gamma_{2}$]{.math .math-inline .is-loaded} be the bottom
horizontal segment.\
As in the arguments for the standard bone contour,\
\[\
\\int*{\\gamma_2}f(z)\\dz = -\\int*{\\gamma*1} -f(z)\\dz = I\
,\]\
so\
\[\
\\qty{\\int*{\\gamma*1} + \\int*{\\gamma_2} }f \\to 2I\
.\]

The contribution from the residue:\
\[\
2\\pi i \\Res\_{z=a} {1\\over (z-a) \\sqrt{1-z\^2} }\
= {2\\pi i \\over \\sqrt{1-a\^2}}\
= {2\\pi \\over \\sqrt{a\^2-1}}\
,\]\
so\
\[\
{2\\pi \\over \\sqrt{a\^2-1}} = 2I \\implies I = {\\pi \\over
\\sqrt{a\^2-1}}\
.\]

:::

:::{.exercise title=\"[$1/x\sqrt{x^{2} - 1}$]{.math .math-inline
.is-loaded} \"}\
\[\
\\int\_{1}\^{\\infty} \\frac{d x}{x \\sqrt{x\^{2}-1}} = {\\pi \\over 2}\
.\]

\#completed

:::

:::{.solution}\
Write [$f(z){: =}(z^{2} - 1)^{- \frac{1}{2}}/z$]{.math .math-inline
.is-loaded}.\
In order for [$(z^{2} - 1)^{- \frac{1}{2}}$]{.math .math-inline
.is-loaded} to be well-defined, one needs to introduce a branch cut.\
Note that [$f$]{.math .math-inline .is-loaded} has a simple pole at
[$z = 0$]{.math .math-inline .is-loaded} and is holomorphic away from
[$z = 0$]{.math .math-inline .is-loaded} **if** [$z^{2} - 1$]{.math
.math-inline .is-loaded} is not on the positive real axis, where we\'ve
chosen the branch cut [$\theta = 0$]{.math .math-inline .is-loaded} for
[${Log}(z)$]{.math .math-inline .is-loaded} and define
[$z^{\frac{1}{2}} = e^{\frac{1}{2}{Log}(z)}$]{.math .math-inline
.is-loaded}.\
But
[$z^{2} - 1 \in \mathbb{R}_{\geq 0}\;\Longleftrightarrow\; z \in \lbrack - 1,1\rbrack^{c}$]{.math
.math-inline .is-loaded}, which is what we\'ve cut.

So take the branch cut
[$( - \infty,1\rbrack \cup \lbrack 1,\infty)$]{.math .math-inline
.is-loaded} and use the following indented double-keyhole contour:

::: {.internal-embed alt="figures/2021-07-29_18-53-35.png" src="figures/2021-07-29_18-53-35.png"}
:::

Contributions along [$C_{8}$]{.math .math-inline .is-loaded} and
[$C_{6}$]{.math .math-inline .is-loaded}: note that
[$\int_{C_{8}}f \rightarrow I$]{.math .math-inline .is-loaded}, the
desired integral.\
For reference, note that [$z^{2} - 1 = (z + 1)(z - 1)$]{.math
.math-inline .is-loaded}, and we can parameterize\
\[\
C*8 = \\ts{t+1+ i\\eps \\st t\\in \[\\eps, R\] } \\implies \\\
\\int*{C*8}f(z)\\dz \\to \\int_0\^\\infty t\\inv (t+2)\^{-{1\\over 2}}
t\^{-{1\\over 2}} \\dt\
,\]\
where on [$C_{8}$]{.math .math-inline .is-loaded} we choose a branch of
the square root so that [$\arg(z + 1) \in \lbrack - \pi,\pi)$]{.math
.math-inline .is-loaded} and
[$\arg(z - 1) \in \lbrack - \pi,\pi)$]{.math .math-inline .is-loaded}.\
Now consider [$C_{6}$]{.math .math-inline .is-loaded}.\
Write [$\zeta_{0}{: =}e^{2\pi i}$]{.math .math-inline .is-loaded}, then\
\[\
C_6 = \\ts{\\zeta_0 t + 1 - i\\eps \\st t\\in \[\\eps, R\]} \\implies
\\\
\\int*{C*6} f(z)\\dz\
&\\to \\int_R\^{\\eps} (\\zeta_0 t)\\inv(\\zeta_0 t + 2)\^{-{1\\over
2}}(\\zeta_0 t)\^{-{1\\over 2}}\\dt \\\
&\\to -\\zeta_0\^{-{3 \\over 2}} \\int_0\^\\infty t\\inv
(t+2)\^{-{1\\over 2}} t\^{-{1\\over 2}}\\dt \\\
&= I\
,\]\
since [$- \zeta_{0}^{- \frac{3}{2}}{: =} - e^{- 3\pi i} = 1$]{.math
.math-inline .is-loaded}.\
So in the limit [$\varepsilon \rightarrow 0,R \rightarrow \infty$]{.math
.math-inline .is-loaded},\
\[\
\\qty{ \\int*{C*8} + \\int*{C_6}}f \\too 2I\
.\]

The contribution from [$C_{2}$]{.math .math-inline .is-loaded}:\
parameterize\
\[\
C*2 = \\ts{s + i\\eps \\st x\\in \[-R, -1-\\eps\]}\
,\]\
which implies\
\[\
\\int*{C*2}f(z)\\dz\
&= \\int*{-\\infty}\^{-1} {1\\over s\\sqrt{s\^2-1}}\\ds \\\
&= - \\int*{\\infty}\^{1} {1\\over (-x) \\sqrt{(-x)\^2-1}}\\dx,\\qquad
x=-s,, \\dx = -\\ds \\\
&= \\int*\\infty\^1 {1\\over (-x) \\sqrt{ (-x)\^2 - 1} }\\dx \\\
&= - \\int*\\infty\^1 {1\\over x \\sqrt{ x\^2 - 1} }\\dx \\\
&= \\int_1\^\\infty {1\\over x \\sqrt{ x\^2 - 1} }\\dx \\\
&= I\
,\]\
so the same argument as above shows\
\[\
\\qty{ \\int*{C*2} + \\int*{C_4}}f \\too 2I\
.\]

Computing the residues: the full contour encloses a simple pole at
[$z = 0$]{.math .math-inline .is-loaded}, so\
\[\
2\\pi i \\Res*{z=0} f(z) = 2\\pi i \\lim*{z\\to 0} {1\\over
\\sqrt{z\^2-1}} = 2\\pi \\cdot (-i) = 2\\pi\
.\]

So by the residue theorem,\
\[\
2\\pi = 2I + 2I \\implies I = {\\pi \\over 2}\
.\]\
:::

:::{.exercise title=\"[$1/x^{2} + 3x + 2$]{.math .math-inline
.is-loaded}\"}\
\[\
I\\da \\int\_\\RR {1\\over x\^2 + 3x+ 2 }\\dx\
.\]

\#completed

:::

:::{.solution title=\"Phantom log trick\"}\
Note that [$f(x) = (x + 2)(x + 1)$]{.math .math-inline .is-loaded}, so
the singularities on on [$\mathbb{R}_{< 0}$]{.math .math-inline
.is-loaded}.\
The function isn\'t even, so a semicircular contour won\'t work.\
Attempting to find a ray-like symmetry only yields one option:\
\[\
f(z) = f(e\^{i\\theta } z) \\implies \\theta = 2k\\pi\
,\]\
which suggests a keyhole.\
But since there\'s no [$\log$]{.math .math-inline .is-loaded} in
[$f$]{.math .math-inline .is-loaded}, there\'s no monodromy, and the
contributions cancel out.\
So introduce a log with a branch cut along [$\theta = 0$]{.math
.math-inline .is-loaded}, and consider\
\[\
\\int f(z) \\log(z)\
.\]

::: {.internal-embed src="figures/2021-12-24_04-03-05.png"}
:::

Let
[$\gamma_{+} = \left\{ {t + i\varepsilon{\ |\ }t \geq 0} \right\}$]{.math
.math-inline .is-loaded} (right-to left) and
[$\gamma_{0} = \left\{ {t - i\varepsilon{\ |\ }t \geq 0} \right\}$]{.math
.math-inline .is-loaded} (left-to-right).\
Now use the general fact\
\[\
\\int*{\\gamma*+}f(z)\\log(z) \\dz &= \\int*\\eps\^R
f(t+i\\eps)\\log(t+i\\eps) \\dt \\too \\int*\\RR f(t)\\log(t)\\dt \\\
\\int*{\\gamma*-}f(z)\\log(z) \\dz &= \\int*R\^\\eps
f(t-i\\eps)\\log(t-i\\eps) \\dt \\too -\\int*\\RR f(t)\\qty{ \\log(t) +
2\\pi i} \\dt \\\
,\]\
thus\
\[\
\\int*{\\gamma*+}f(z)\\log(z)\\dz + \\int*{\\gamma*-}f(z)\\log(z)\
&\\too \\int_0\^\\infty f(t)\\log(t)\\dt - \\int_0\^\\infty
f(t)(\\log(t) + 2\\pi i) \\dt \\\
&= -2\\pi i \\int_0\^\\infty f(t) \\dt\
.\]

By the ML estimate, the semicircular piece vanishes.\
Miraculously, since
[$\lim\limits_{x \rightarrow 0}\frac{x\log(x)}{x^{n} + c} = 0$]{.math
.math-inline .is-loaded} for any [$c > 0$]{.math .math-inline
.is-loaded} and [$n \geq 1$]{.math .math-inline .is-loaded}, the inner
indented pieces goes to zero.\
Parameterize by [$z = \varepsilon e^{it}$]{.math .math-inline
.is-loaded}\
\[\
\\int*{C*\\eps} f(z)\\log(z)\\dz\
&\\approx \\int*{\\eps}\^{2\\pi - \\eps} {\\log(\\eps e\^{it}) \\over
\\eps\^2 + 3\\eps + 2} \\eps e\^{it}\\dt \\\
&= \\int*{\\eps}\^{2\\pi - \\eps} {\\log(\\eps) + it \\over \\eps\^2 +
3\\eps + 2} \\eps e\^{it}\\dt \\\
&\\approx \\int*\\eps\^{2\\pi - \\eps} {\\eps \\log(\\eps) + c_1 \\over
\\eps\^2 + c_2}\\dt \\\
&\\convergesto{\\eps\\to 0} 0\
,\]\
where I\'ve been *extremely* sloppy and left out many negligible
[$e^{it}$]{.math .math-inline .is-loaded} terms.\
By the residue theorem,\
\[\
2\\pi i \\sum*{z*k\\in \\CC} \\Res*{z=z*k} f(z)\\log(z) = \\int*\\Gamma
f(z)\\log(z)\\dz = -2\\pi i\\int*\\RR f(z)\\dz\
.\]\
There are just two simple poles at [$z_{1} = - 1,z_{2} = - 2$]{.math
.math-inline .is-loaded}, so\
For [$z_{1}$]{.math .math-inline .is-loaded}:\
\[\
\\Res*{z=-1}{\\log(z) \\over (z+1)(z+2)}\
= \\lim*{z\\to -1} {\\log(z) \\over z+2}\
= \\log(-1)\
,\]\
and for [$z_{2}$]{.math .math-inline .is-loaded},\
\[\
\\Res*{z=-2}{\\log(z) \\over (z+1)(z+2)}\
= \\lim\_{z\\to -2} {\\log(z) \\over z+1}\
= -\\log(-2)\
.\]

Thus\
\[\
I\
&= -(\\log(-1) - \\log(-2)) \\\
&= - (\\ln(1) + i\\pi) + (\\ln(2) + i\\pi) \\\
&= \\ln(2)\
,\]\
noting that we\'ve chosen a branch of
[$\log(z){: =}\ln\text{\textbackslash qty}{\text{\textbackslash abs}z} + i{Arg}(z)$]{.math
.math-inline .is-loaded} where [${Arg}(z) \in (0,2\pi)$]{.math
.math-inline .is-loaded}.\
:::

## UGA Courses {#uga-courses heading="UGA Courses"}

-   Problem Session Problems \#problems

-   Spring 2021 HW1 \#problems\

-   Spring 2021 HW2 \#problems\

-   Spring 2021 HW3 \#problems\

-   Spring 2021 Midterm \#problems\

-   Extra Questions from Tie \#problems

-   attachments/Azoff Problems by Topic.pdf

-   UGA Qual Problems

-   [Problem sheet from Cambridge Part
    1B](https://dec41.user.srcf.net/notes/IB_L/complex_methods_eg.pdf){.external-link}\

## Misc {#misc heading="Misc"}

-   [Utah Math 6220
    Assignments.](http://www.math.utah.edu/~astephan/134.pdf){.external-link}
    \#problems
-   [Lots of problems from
    JHU](https://math.jhu.edu/gradexam/analysisexams.pdf){.external-link}
