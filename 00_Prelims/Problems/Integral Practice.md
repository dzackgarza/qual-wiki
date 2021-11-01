
# Integral Sheet

Here is a [youtube video](https://www.youtube.com/watch?v=dgm4-3-Iv3s) that potentially has many more integrals.

Note: some of these were incorrect, and the solutions need to all be checked in detail.

Techniques to cover, in order of difficulty:

- Elementary antiderivatives
  - Exponentials, polynomials, trig functions, logs
- u-substitutions
- Trig identities
  - e.g. $\displaystyle \int \cos^2(x) = \displaystyle \int \frac 1 2 (1 + \cos(2x))$
- Trigonometric substitutions
- Partial Fraction Decomposition
- Reverse chain rule
  - e.g. $\displaystyle \int \tan(x)$
- Integration by parts
  - e.g. $\displaystyle \int x^2 e^x$
- "Periodic" integration by parts
  - e.g. $\displaystyle \int e^x \sin(x)$
- Products of powers of trigonometric functions
  - e.g. $\displaystyle \int \sin^3(x)\cos^2(x)$
- u-sub with a back-substitution
  - e.g. $\displaystyle \int \frac{1}{x-3\sqrt{x+10}}, u=\sqrt{x+10} \implies x = u^2-10$
- Trionometric reduction formulas
  - e.g. $\displaystyle \int \sec^3 x$
- Completing the square
  - e.g. $\displaystyle \int \sqrt{x^2+4x+5} = \displaystyle \int \sqrt{(x+2)^2 + 1}$, then trig sub
- Polynomial long division
- Exotic antiderivatives
  - e.g. $\displaystyle \int e^x + e^{-x} = \displaystyle \int 2\cosh(x)$
- Product to sum formulas
- Shoelace method of integration by parts
- Weierstrass substitution
  - e.g. $\displaystyle \int \frac 1 {1 + \sin(x)}, \sin(x) = \frac{2t}{1+t^2}$ wher $t=\tan(\frac x 2)$
- "Rigged" integration by parts
  - e.g. for $\displaystyle \int f(x) dx$, let $u=f(x), v' = 1$
- Integrating even/odd functions over symmetric domains
  - e.g. $\displaystyle \int_{-1}^1 \sin(x)$
- Bonus round: $\displaystyle \int_\mathbb{R} e^{-x^2}$
  - Every math student should know one way of deriving this. :)



## Definitions

##### Level 1

1. $\displaystyle \int x^a ~dx = \frac {x^{a+1}}{a+1}$ 

2. $\displaystyle \int a^{bx} ~dx = \frac {a^{bx}}{b \ln (a)}$

   1. $\displaystyle \int 2018^x ~dx = \color {blue} {\frac {2018^x}{\ln (2018)}}$

   - **Used 2018**

3. $\displaystyle \int \frac {1}{x} ~dx = \ln (x)​$

4. $\displaystyle \int \sin (ax) ~dx = - \frac {1}{a} \cos (ax)$

   $\displaystyle \int \cos (ax) ~dx = \frac {1}{a} \sin (ax)$

   $\displaystyle \int \tan (ax) ~dx = - \frac {1}{a} \ln (\cos (ax))$

   1. $\displaystyle \int \frac {\sin^3(x)}{\cos(x) - \cos^3(x)} ~dx = \color {blue} {- \ln (\cos(x))}$

   - **Solution:** $\frac {\sin^3(x)}{\cos(x) - \cos^3(x)} = \frac {\sin^3(x)}{\cos(x) \sin ^2 (x)} = \tan (x)$
   - **Used 2019**

   $\displaystyle \int \cot (ax) ~dx = \frac {1}{a} \ln (\sin (ax))​$

   $\displaystyle \int \sec (ax) ~dx = \frac {1}{a} \ln (\sec (ax) + \tan (ax))​$

   $\displaystyle \int \csc (ax) ~dx = - \frac {1}{a} \ln (\csc (ax) + \cot (ax))$

5. $\displaystyle \int \cos (ax) ~dx = \frac {1}{a} \sin (ax)$

   $\displaystyle \int \sin (ax) ~dx = - \frac {1}{a} \cos (ax)$

   $\displaystyle \int \sec ^2 (ax) ~dx = \frac {1}{a} \tan (ax)​$

   $\displaystyle \int \csc ^2 (ax) ~dx = - \frac {1}{a} \cot (ax)$

   $\displaystyle \int \sec (ax) \tan (ax) ~dx = \frac {1}{a} \sec (ax)$

   1. $\displaystyle \int \frac {\sin (x)}{\cos ^2 (x)} ~dx = \color {blue} {\sec (x)}$

   - **Solution:** $\frac {\sin (x)}{\cos ^2 (x)} = \tan (x) \sec (x)​$

   $\displaystyle \int \csc (ax) \cot (ax) ~dx = - \frac {1}{a} \csc (ax)$

   1. $\displaystyle \int \frac {\cos(x)}{\sin ^2 (x)} ~dx = \color {blue} {- \csc (x)}$

   - **Solution:** $\frac {\cos (x)}{\sin ^2 (x)} = \cot (x) \csc (x)$

6. $\displaystyle \int \frac {1}{\sqrt {a^2-x^2}}~dx = \sin ^{-1} (\frac {x}{a})$

   1. $\displaystyle \int \frac {1}{\sqrt {4-9x^2}} ~dx = \color {blue} {\frac {1}{3}\sin ^{-1} (\frac {3}{2} x)}$
   - **Solution:** $\frac {1}{\sqrt {4-9x^2}} = \frac {1}{3 \sqrt {(\frac {2}{3})^2 - x^2}}$

   $\displaystyle \int \frac {1}{x^2+a^2}~dx = \frac {1}{a} \tan ^{-1} (\frac {x}{a})$

   1. $\displaystyle \int \frac {1}{9+x^2} ~dx = \color {blue} {\frac {1}{3} \tan ^{-1} (\frac {x}{3})}$
      - **Used 2018**

   $\displaystyle \int \frac {1}{x \sqrt {x^2 - 1}} ~dx = \sec ^{-1} (x)$

   1. $\displaystyle \int_{1}^{2} \frac {1}{x\sqrt {x^2 -1}} dx = \color {blue} {\frac {\pi}{3}}$

   - **Solution:** $\sec ^{-1} (x) |_{1}^{2}$

7. $\displaystyle \int \sin^{-1}(x) ~dx = x\sin^{-1}(x) + \sqrt {1 - x^2}$

   - **Used 2018**, *Unsolved*

   $\displaystyle \int \tan^{-1}(x) ~dx = x \tan^{-1}(x) - \frac {1}{2} \ln (x^2 + 1)$

   $\displaystyle \int \sec ^{-1} (x) ~dx = x \sec ^{-1} (x) - \ln (\sqrt {x^2 - 1} + x)$



## Easy

##### Level 1

1. $\displaystyle \int \frac {\sin^2(2x)}{1+\cos(2x)} ~dx = \color{blue} {x-\cos(x)\sin(x)}$

- **Solution:** $\frac {\sin ^2 (2x)}{1 + \cos (2x)} = \frac {1 - \cos ^2 (2x)}{1 + \cos (2x)} = 1 - \cos (2x)$
- **Used 2019**

2. $\displaystyle \int_{\frac {\pi}{3}}^{\frac {\pi}{2}} \frac {1-\cos (x)}{\sin (x)} ~dx = (- \ln (\csc (x) + \cot (x))- \ln (\sin (x)))|_{x = \frac {\pi}{3}}^{x = \frac {\pi}{2}} = - \ln (1 + \cos (x))|_{x = \frac {\pi}{3}}^{x = \frac {\pi}{2}} = \color {blue} {\log(\frac {3}{2})}$

- **Solution:** $\frac {1-\cos (x)}{\sin (x)} = \csc (x) - \cot (x)$

3. $\displaystyle \int \frac {\sec^3(x) + e^{\sin(x)}}{\sec(x)} ~dx = \color {blue} {\tan(x) + e^{\sin(x)}}$

- **Solution:** $\frac {\sec ^3 (x) + e^{\sin(x)}}{\sec(x)} = \sec ^2 (x) + \cos (x) \cdot e^{\sin(x)}$
- **Used 2018**

4. $\displaystyle \int \frac {1}{\tan (x) + \cot (x)} ~dx = \color {blue} {\frac {1}{2}\sin ^2 (x)} = \color {blue} {- \frac {1}{2}\cos ^2 (x)}$

- **Solution:** $\frac {1}{\tan (x) + \cot (x)} = \frac {1}{\frac {\sin (x)}{\cos (x)} + \frac {\cos (x)}{\sin (x)}} = \frac {\sin (x) \cos (x)}{\sin ^2 (x) + \cos ^2 (x)} = \sin (x) \cos (x)$
- **Used 2019**

5. $\displaystyle \int \sin (x) \cos (x) \cot (x) \tan (x) ~dx = \color {blue} {\frac {1}{2} \sin^2 (x)}$

- **Solution:** $\sin (x) \cos (x) \cot (x) \tan (x) = \sin (x) \cos (x)$

6. $\displaystyle \int \sqrt {1 + \cos (2ax)} ~dx = \color {blue} {\frac {\sqrt {2}}{a} \sin (ax)}$

- **Solution:** $\sqrt {1 + \cos (2ax)} = \sqrt {2 \cos ^2 (ax)} = \sqrt {2} \cos (ax)$
- **Used 2019**

  1. $\displaystyle \int_{0}^{\pi} \sqrt {1 + \cos (2x)} ~dx= \color {blue} {2\sqrt {2}}$
   - **Solution:** $\sqrt {1 + \cos (2x)} = \sqrt {2 \cos ^2 (x)} = \sqrt {2} \cos (x)$




## Interesting tricks

##### Level 1

###### Change the order of integration

1. $\displaystyle \int_0^1 \int_y^1 \sin (x^2) ~dx dy = \color {blue} {\sin ^2 (\frac {1}{2})}$


##### Level 2

###### Odd funtion

1. $\displaystyle \int_{-\pi}^{\pi} e^{-x^2}\sin (x) dx = \color {blue} {0}$

2. $\displaystyle \int_{-1729}^{1729} \sin^5(x^3) + \sin^3(x^5) + x = \color {blue} {0}$



##### Level 3

###### Gaussian distribution

1. $\displaystyle \int_{-\infty}^{\infty} e^{- \frac {(x-\mu)^2}{2 \sigma ^2}} ~dx = \sqrt {2 \pi \sigma ^2}$

   1. $\displaystyle \int_{-\infty}^{\infty} e^{-x^2} ~dx = \color {blue} {\sqrt {\pi}}$
   2. $\displaystyle \int_{-\infty}^{\infty} e^{-\frac {1}{2}x^2} ~dx = \color {blue} {\sqrt {2\pi}}$
   3. $\displaystyle \int_{-\infty}^{\infty} e^{-x^2+6x-3} ~dx = \color {blue} {e^{6}\sqrt {\pi}}$

   - **Used 2019**, *Unsolved*



###### Reverse Quotient Rule

2. $\displaystyle \int \frac {xe^x\ln x - e^x}{x\ln^2 x} = \color {blue} {\frac {e^x}{\ln x}}$

- **Used 2018**

3. $\displaystyle \int (\tan(x) + \cot(x))^2 ~dx = \color {blue} {\tan(x)-\cot(x)}$

- **Solution:** $\sin ^2 (x) + \cos ^2 (x) = 1$
- **Used 2018**



## u-Substitutions

##### Level 1

1. $\displaystyle \int \sin(x) \cos (\cos (x)) ~dx = \color{blue} {- \sin (\cos (x))}​$

- **Solution:** $u = \cos (x)​$, $du = - \sin (x)~dx ​$
- **Used 2018**

2. $\displaystyle \int e^{\sin ^2 (x)} \sin (2x) ~dx = \color{blue} {e^{\sin^2(x)}}​$

- **Solution:** $u = \sin ^2 (x)​$, $du = 2 \sin (x) \cos (x) ~dx = \sin (2x) ~dx​$
- **Used 2018**
- **Used 2019**

3. $\displaystyle \int e^{(x + e^x)} ~dx = \color{blue} {e^{e^{x}}}​$

- **Solution:** $u = e^x​$, $du = e^x ~dx​$
- **Used 2018**

4. $\displaystyle \int \frac 1 {x(\ln(x))^2} ~dx = \color{blue} {\frac 1 {\ln(x)}}​$

- **Solution:** $u = \ln(x)​$, $du = \frac {1}{x} ~dx​$
- **Used 2018**
  1. $\displaystyle \int_2^\infty \frac {1}{x(\ln (x))^2} ~dx =  \color{blue} {\frac {1}{\log(2)}}$

5. $\displaystyle \int \frac 1 {x^2} \cos(\frac 1 x) = \color{blue} {- \sin \frac {1}{x}}​$

- **Solution:** $u = \frac {1}{x}​$, $du = - \frac {1}{x^2}~dx ​$
- **Used 2018**

6. $\displaystyle \int \frac {e^x}{e^x + 1} ~dx = \color{blue} {\ln (e^x + 1)}​$

- **Solution:** $u = e^x + 1​$, $du = e^x ~dx ​$
- **Used 2018**
- **Used 2019**

7. $\displaystyle \int \frac {1 + e^x}{1 - e^x} ~dx = \color{blue} {x - \ln (1 - e^x)}​$

- **Solution:** $u = 1-  e^x$, $du = - e^x ~dx $
- **Used 2018**

8. $\displaystyle \int \frac {x+1}{x^2+2x+3} ~dx = \color{blue} {\frac 1 2 \ln(x^2 + 2x + 3)}​$

- **Solution:** $u = x^2 + 2x + 3$, $du = 2x + 2 ~dx $

9. $\displaystyle \int \frac {4x^3 + 2x}{x^4 + 1} ~dx = \color{blue} {\ln (x^4 + 1) + \tan ^{-1} (x^2)}$

- **Solution:** $u_1 = x^4 + 1$, $du_1 = 4 x^3 ~dx$
- **Solution:** $u_2 = x^2$, $du_2 = 2x ~dx$
- **Solution:** $\frac {4x^3 + 2x}{x^4 + 1} ~dx = \frac {1}{u_1} ~du_1 + \frac {1}{u_2^2 + 1} ~du_2$
- **Used 2019**

10. $\displaystyle \int \sqrt {4-x} ~dx = \color{blue} {- \frac {2}{3}(4-x)^{\frac {3}{2}}}$

- **Solution:** $u = 4 - x$, $du = - ~dx$
- **Solution:** $\sqrt {4-x} ~dx = - u^{\frac {1}{2}} ~du$

11. $\displaystyle \int x\sqrt {x+1}~dx =  \color {blue} {\frac {2}{5} (x + 1)^{\frac {5}{2}} - \frac {2}{3} (x + 1)^{\frac {3}{2}}}$

- **Solution:** $u = x + 1$, $du = dx$
- **Solution:** $x\sqrt {x + 1} ~dx = (u - 1) \sqrt {u} ~du = u^{\frac {3}{2}} - u^{- \frac {1}{2}} ~du$
- **Used 2019**

12. $\displaystyle \int \frac {x}{x^2+9} ~dx = \color{blue} {\frac 1 2 \ln(x^2 + 9)}$

- **Solution:** $u = x^2 + 9$, $du = 2x ~dx$
- **Solution:** $\frac {x}{x^2+9} ~dx = \frac {1}{2} \cdot \frac {1}{u} ~du$
- **Used 2018**

13. $\displaystyle \int \frac {x}{1+x^4} ~dx = \color{blue} {\frac {1}{2} \tan ^{-1} (x^2)}$

- **Solution:** $u =x^2$, $du = 2x ~dx$
- **Solution:** $\frac {1}{2} \cdot \frac {2x ~dx}{1+x^4} = \frac {1}{2} \frac {du}{1 + u^2}$

14. $\displaystyle \int \frac {x^2}{1+x^6} ~dx = \color{blue} {\frac {1}{3} \tan ^{-1} (x^3)}$

- **Solution:** $u =x^3$, $du = 3 x^2 ~dx$
- **Solution:** $\frac {1}{3} \cdot \frac {3 x^2 ~dx}{1+x^6} = \frac {1}{3} \frac {du}{1 + u^2}$

- **Used 2018**



##### Level 2

1. $\displaystyle \int \frac {1}{e^x + e^{-x}} ~dx = \color{blue} {\tan ^{-1} e^x}​$

- **Solution:** $u = e^x$, $du = e^x ~dx$

- **Solution:** $\frac {1}{e^x + e^{-x}} ~dx = \frac {e^x}{e^{2x} + 1} ~dx = \frac {1}{u^2 + 1} ~du​$

  1. $\displaystyle \int \frac {e^x}{1+e^{2x}} ~dx = \color{blue} {\tan ^{-1} (e^x)}​$

  - **Solution:** $\frac {1}{e^x + e^{-x}} =  \frac {e^x}{1+e^{2x}}$

2. $\displaystyle \int \frac {1}{\sqrt {e^{2x}-1}} ~dx = \color{blue} {\sin ^{-1} (e^{-x})} = \color{blue} {\tan ^{-1} (\sqrt {e^{2x} - 1})}$

- **Solution:** $u = e^{-x}$, $du = - e^{-x} ~dx$
- **Solution:** $\frac {1}{\sqrt {e^{2x}-1}} ~dx = \frac {e^{-x} ~dx}{\sqrt {1- e^{-2x}}} = \frac {du}{\sqrt {1 - u^2}}$
- **Another Solution:** $u = \sqrt {e^{2x} - 1}$, $x = \frac {1}{2} \ln (u^2 + 1)$, $dx = \frac {u}{u^2 + 1} ~du$
- **Another Solution:** $\frac {1}{\sqrt {e^{2x}-1}} ~dx = \frac {1}{u} \cdot \frac {u ~du}{u^2 + 1} = \frac {1}{u^2 + 1} ~du$

3. $\displaystyle \int \frac {\sqrt {1 + \ln (x)}}{x \ln (x)} ~dx = \color {blue} {2 \sqrt {1 + \ln (x)} + \ln (\sqrt {1 + \ln (x)} - 1) - \ln (\sqrt {1 + \ln (x)} + 1)}$ 

- **Solution:** $u = \sqrt {1 + \ln (x)}$, $x = e^{u^2 - 1}$, $dx = 2u e^{u^2 - 1} ~du$
- **Solution:** $\frac {\sqrt {1 + \ln (x)}}{x \ln (x)} ~dx = \frac {u}{e^{u^2 - 1} {u^2 - 1}} \cdot 2u e^{u^2 - 1} ~du = \frac {2u^2}{u^2 - 1} ~du = 2 + \frac {1}{u - 1} - \frac {1}{u + 1} ~du$

4. $\displaystyle \int \frac {7 - \ln (x)}{x(3 + \ln (x))} ~dx = \color{blue} {- \ln (x) + 10 \ln (\ln (x) + 3)}$

- **Solution: ** $u = \ln (x) + 3$, $du = \frac {1}{x} ~dx$
- **Solution:** $\frac {7 - \ln (x)}{x(3 + \ln (x))} ~dx = - \frac {dx}{x} + 10 \frac {\frac {1}{x} ~dx}{3 + \ln (x)} = - \frac {dx}{x} + 10 \frac {du}{u}$

5. $\displaystyle \int \frac {\sec^2(x)}{1+\tan(x)} ~dx = \color {blue} {\ln (\tan (x) + 1)}$

- **Solution:** $u = 1 + \tan (x)$, $du = \sec ^2 (x) ~dx$

6. $\displaystyle \int \frac {\sin(x)}{\sqrt {4-\cos^2(x)}} ~dx = \color {blue} {- \sin^{-1}(\frac {1}{2} \cos(x))}$

- **Solution:** $u = \frac {1}{2} \cos (x)$, $du = - \frac {1}{2} \sin (x) ~ dx$
- **Solution:** $\frac {\sin(x)}{\sqrt {4-\cos^2(x)}} ~dx = - \frac {1}{\sqrt {1 - u^2}} ~du$

7. $\displaystyle \int \frac {\sec ^2 (x)}{\sqrt {9 - \tan^2(x)}} ~dx = \color {blue} {- \sin^{-1}(\frac {1}{3} \tan(x))}$

- **Solution:** $u = \frac {1}{3} \tan (x)$, $du = - \frac {1}{3} \sec ^2 (x) ~ dx$
- **Solution:** $\frac {\sec ^2 (x)}{\sqrt {9 - \tan^2(x)}} ~dx = - \frac {1}{\sqrt {1 - u^2}} ~du$



##### Level 3

1. $\displaystyle \int \frac {1 - \sqrt {x}}{1 + \sqrt {x}} ~dx = \color{blue} {- x + 4 \sqrt {x} - 4 \ln (1 + x)}$

- **Solution:** $u = 1 + \sqrt {x}$, $x = (u - 1)^2$, $dx = 2(u - 1) ~du$
- **Solution:** $\frac {1 - \sqrt {x}}{1 + \sqrt {x}} ~dx = \frac {2 - u}{u} 2(u - 1) ~du = -2u + 6 - 4 \cdot \frac {1}{u} ~du$
- **Used 2019**, *Unsolved*

2. $\displaystyle \int \frac {1}{\sqrt {x}+2\sqrt[3]{x}} ~dx = \color {blue} {2\sqrt {x} - 6\sqrt[3]{x} + 24\sqrt[6]{x} - 48\ln (\sqrt[6]{x} + 2)}$

- **Solution:** $u_1^6 = x$, $6 u_1^5 ~du_1 = dx$
- **Solution:** $u_2 = u_1 + 2$, $du_2 = du_1$
- **Solution:** $\frac {1}{\sqrt {x}+2\sqrt[3]{x}} ~dx = \frac {1}{u_1^3 + 2 u_1^2} \cdot 6u_1^5 ~du_1 = \frac {6u_1^3}{u_1 + 2} ~du_1 = \frac {6(u_2 - 2)^3}{u_2} ~du_2 = 6 (u_2^2 - 6u_2 + 12 - 8 \cdot \frac {1}{u_2}) ~du_2$

3. $\displaystyle \int \frac {1}{\sqrt {x} - \sqrt[3]{x}} ~dx ＝ \color {blue} {2\sqrt {x}+3\sqrt[3]{x}+6\sqrt[6]{x}+6\ln (\sqrt[6]{x} - 1)}$

- **Solution:** $u_1^6 = x$, $6 u_1^5 ~du_1 = dx$
- **Solution:** $u_2 = u_1 - 1$, $du_2 = du_1$
- **Solution: ** $\frac {1}{\sqrt {x} - \sqrt[3]{x}} ~dx = \frac {1}{u_1^3 - u_1^2} \cdot 6 u_1^5 ~du_1 = \frac {6u_1^3}{u_1 - 1} ~du_1 = \frac {6(u_2 + 1)^3}{u_2} ~du_2 = 6 (u_2^2 + 3u_2 + 3 + \cdot \frac {1}{u_2}) ~du_2$
- **Used 2019**, *Unosolved*

4. $\displaystyle \int \frac {1}{\sqrt {x} + \sqrt[4]{x}} ~dx = \color {blue} {2\sqrt {x}-4\sqrt[4]{x}+4\ln(\sqrt[4]{x}+1)}$

- **Solution:** $u_1^4 = x$, $4 u_1^3 ~du_1 = dx$
- **Solution:** $u_2 = u_1 + 1$, $du_2 = du_1$
- **Solution:** $\frac {1}{\sqrt {x} + \sqrt[4]{x}} ~dx = \frac {1}{u_1^2 + u_1} \cdot 4 u_1^3 ~du_1 = \frac {4 u_1^2}{u_1 + 1} ~du_1 = \frac {4 (u_2 - 1)^2}{u_2} ~du_2 = 4(u_2 - 2 + \frac {1}{u_2}) ~du_2$

5. $\displaystyle \int \frac {\sqrt[3]{x}+1}{\sqrt[3]{x} - 1} ~dx = \color {blue} {x+3\sqrt[3]{x}^2+6\sqrt[3]{x}+6\ln(\sqrt[3]{x} - 1)}$

- **Solution:** $u_1^3 = x$, $3 u_1^2 ~du_1 = dx$
- **Solution:** $u_2 = u_1 - 1$, $du_2 = du_1$
- **Solution:** $\frac {\sqrt[3]{x}+1}{\sqrt[3]{x} - 1} ~dx = \frac {u_1 + 1}{u_1 - 1} \cdot 3 u_1^2 ~du_1 = \frac {3(u_2 + 2)(u_2 + 1)^2}{u_2} ~du_2 = 3(u_2^2 + 4u_2 + 5 + 2 \cdot \frac {1}{u_2}) ~du_2$
- **Used 2019**

6. $\displaystyle \int \frac {1}{(x+1)\sqrt {x}} ~dx = \color{blue} {2 \tan ^{-1} (\sqrt {x})}$

- **Solution:** $u = \sqrt {x}​$, $du = \frac {1}{2 \sqrt {x}} ~dx​$

- **Solution:** $\frac {1}{(x+1)\sqrt {x}} ~dx = \frac {2}{u^2 + 1} ~du​$

  1. $\displaystyle \int \frac {1}{2x\sqrt {x-1}} ~dx =  \color{blue} {\tan^{-1}(\sqrt {x-1})}​$

  - **Solution:** $\frac {1}{2x \sqrt {x-1}} = \frac {1}{2(x - 1 + 1) \sqrt {x-1}}$

7. $\displaystyle \int \frac {x}{\sqrt[3]{x + 1}} ~dx = \color {blue} {\frac {3}{5} (x + 1)^{\frac {5}{3}} - \frac {3}{2} (x + 1)^{\frac {2}{3}}}​$

- **Solution:** $u = x + 1$, $du = dx$
- **Solution:** $\frac {x}{\sqrt[3]{x + 1}} ~dx = \frac {u - 1}{\sqrt[3]{u}} ~du = u^{\frac {2}{3}} - u^{- \frac {1}{3}} ~du$
- **Used 2019**

8. $\displaystyle \int \frac {1}{x\sqrt {4x-1}} ~dx = \color{blue} {2 \tan ^{-1} (\sqrt {4x - 1})}​$

- **Solution:** $u = \sqrt {4x-1}​$, $x = \frac {1}{4} (u^2 + 1)​$, $dx = \frac {1}{2} u ~du​$
- **Solution:** $\frac {1}{x\sqrt {4x-1}} ~dx = \frac {2}{u^2 + 1} ~du​$

9. $\displaystyle \int \frac {2}{x\sqrt {25x^4-1}} ~dx = \color{blue} {\tan^{-1}(\sqrt {25x^4-1})}​$

- **Solution:** $u = \sqrt {25x^4 - 1}​$, $x^4 = \frac {1}{25} (u^2 + 1)​$, $4x^3 ~dx = \frac {2}{25} u ~du​$
- **Solution:** $\frac {2}{x\sqrt {25x^4-1}} ~dx = \frac {1}{u^2 + 1} ~du$

10. $\displaystyle \int \frac {1}{\sqrt {x}\sqrt {1-4x}} ~dx = \color{blue} {\frac {1}{2} \sin ^{-1} (8x - 1)} = \color{blue} {\sin ^{-1} (2\sqrt {x})}$

- **Solution:** $u = 8x - 1$, $du = 8 ~dx$
- **Solution:** $\frac {1}{\sqrt {x}\sqrt {1-4x}} ~dx = \frac {1}{\sqrt {1 - (8x - 1)^2}} ~dx = \frac {1}{2} \cdot \frac {1}{\sqrt {1 - u^2}} ~du​$
- **Another Solution:** $u = 2 \sqrt {x}$, $du = \frac {1}{\sqrt {x}} ~dx$
- **Another Solution:** $\frac {1}{\sqrt {x}\sqrt {1-4x}} ~dx = \frac {1}{\sqrt {1 - u^2}} ~du​$

11. $\displaystyle \int \frac {6-2x}{\sqrt {9-x^2}} ~dx = \color {blue} {6 \sin ^{-1} (\frac {x}{3}) + 2 \sqrt {9-x^2}}$

- **Solution:** $u = \frac {1}{3} x​$, $du = \frac {1}{3} ~dx​$
- **Solution:** $\frac {6-2x}{\sqrt {9-x^2}} ~dx = \frac {6}{\sqrt {1-u^2}} ~du + \frac {- 2x}{\sqrt {9-x^2}} ~dx$

12. $\displaystyle \int \frac {1}{\sqrt {x\sqrt {x}-x^2}} ~dx = \color {blue} {4 \sin ^{-1} (\sqrt[4]{x})}$

- **Solution:** $u = \sqrt[4]{x}$, $du = \frac {1}{4 \sqrt[4]{x^3}} ~dx$
- **Solution:** $\frac {1}{\sqrt {x\sqrt {x}-x^2}} ~dx = \frac {1}{\sqrt {1 - (\sqrt[4]{x})^2}} \cdot \frac {1}{4 \sqrt[4]{x^3}} ~dx = 4 \frac {1}{\sqrt {1 - u^2}} ~du$
- **Used 2019**, *Unsolved*

13. $\displaystyle \int_{0}^{1} \frac {1}{\sqrt {x(1-x)}} ~dx = 2 \sin ^{-1} (\sqrt {x}) |_{0}^{1} = \color {blue} {\pi}$

- **Solution:** $u = \sqrt {x}$, $du = \frac {1}{2 \sqrt {x}} ~dx$

- **Solution:** $\frac {1}{\sqrt {x(1-x)}} ~dx = \frac {2}{\sqrt {1 - u^2}} ~du$

  1. $\displaystyle \int_{e^{\frac {1}{2}}}^{e^{\frac {3}{4}}} \frac {1}{x\sqrt {\ln(x)(1-\ln(x))}} ~dx = \color {blue} {\frac {\pi}{6}}$

  - **Solution:** $u = \ln (x)$, $du = \frac {1}{x} ~dx$
  - **Solution:** $\int_{e^{\frac {1}{2}}}^{e^{\frac {3}{4}}} \frac {1}{x\sqrt {\ln(x)(1-\ln(x))}} ~dx = \int_{\frac {1}{2}}^{\frac {3}{4}} \frac {1}{\sqrt {x(1-x)}} ~dx = 2 \sin ^{-1} (\sqrt {x}) |_{\frac {1}{2}}^{\frac {3}{4}} = 2(\frac {\pi}{3} - \frac {\pi}{4})$
  - **Used 2019**, *Unsolved*

14. $\displaystyle \int \frac {x}{1-x^2 + \sqrt {1- x^2}} ~dx = \color {blue} {- \ln (\sqrt {1-x^2}+1)}$

- **Solution:** $u^2 = 1 - x^2$, $u ~du = - x ~dx$
- **Solution:** $\frac {x}{1-x^2 + \sqrt {1- x^2}} ~dx = \frac {1}{1-x^2 + \sqrt {1- x^2}} \cdot x ~dx = \frac {1}{u^2 + u} \cdot (-u) ~du = - \frac {1}{u + 1} ~du$

15. $\displaystyle \int_{1}^{\infty} \frac {1}{x(x^2+1)} ~dx = \frac {1}{2} \ln (\frac {1}{x^2} + 1) |_{1}^{\infty} = \color {blue} {\frac {1}{2} \ln (2)}$

- **Solution:** $u = \frac {1}{x^2} + 1​$, $du = -2 \frac {1}{x^3} ~dx​$
- **Solution:** $\frac {1}{x(x^2+1)} ~dx = \frac {1}{(\frac {1}{x^2} + 1)} \cdot \frac {1}{x^3} ~dx = - \frac {1}{2u} du$
- **Used 2019**



## Trigonometric Substitution

##### Level 2

###### Sin

1. $\displaystyle \int \sqrt {1 -x^2} ~dx = \frac {1}{2} (\sin ^{-1} (x) + \frac {1}{2} \sin (2 \sin ^{-1} (x))) = \color {blue} {\frac {1}{2} (\sin ^{-1} (x) + x \sqrt {1 - x^2})}$

- **Solution:** $\sin (u) = x​$, $\cos (u) ~du = dx​$

- **Solution:** $\sqrt {1 -x^2} ~dx = \sqrt {1 - (\sin (u))^2} \cos (u) ~du = \cos ^2 (u) ~du = \frac {1}{2} (1 + \cos (u)) ~du​$

  1. $\displaystyle \int_{-4}^{4} \sqrt {16 - x^2} ~dx = \color {blue} {8\pi}$

  - **Solution:** the area of semi-circle
  - **Used 2019**

  2. $\displaystyle \int_{-1}^{1} (1+x)\sqrt {1-x^2} ~dx = \color {blue} {\frac {1}{2} \pi}$

  - **Solution:** $\int_{-1}^{1} (1+x)\sqrt {1-x^2} ~dx = \int_{-1}^{1} \sqrt {1-x^2} ~dx + \int_{-1}^{1} \sqrt {1-x^2} x ~dx = \frac {1}{2} \pi + \frac {2}{3} (1-x^2)^{\frac {3}{2}} |_{-1}^{1}$
  - **Used 2019**

2. $\displaystyle \int \frac {x^3}{\sqrt {25-x^2}} ~dx = \color {blue} {\frac {1}{3} (\sqrt {25-x^2})^3 - 25 \sqrt {25-x^2}}$

- **Solution:** $\sin (u) = \frac {1}{5} x$, $\cos (u) ~du = \frac {1}{5} ~dx$
- **Solution:** $\frac {x^3}{\sqrt {25-x^2}} ~dx = \frac {\sin ^3 (u)}{125 \cos (u)} \cos (u) ~du = \frac {1}{125} \cdot \sin ^3 (u) ~du$
- **Another Solution:** $u = \sqrt {25 - x^2}$, $u ~du = - x ~dx$
- **Another Solution:** $\frac {x^2}{\sqrt {25-x^2}} \cdot x ~dx = \frac {25 - u^2}{u} \cdot u ~du = (25 - u^2) ~du$

3. $\displaystyle \int \frac {x+1}{\sqrt {4-x^2}} ~dx = \color {blue} {-\sqrt {4-x^2}+\sin ^{-1} (\frac {x}{2})}$

- **Solution:** $\frac {x+1}{\sqrt {4-x^2}} ~dx = - \frac {1}{2} \frac {-2x}{\sqrt {4-x^2}} ~dx + \frac {1}{\sqrt {4-x^2}} ~dx​$
- **Solution:** $\sin (u) = \frac {1}{2} x$, $\cos (u) ~du = \frac {1}{2} ~dx$
- **Solution:** $\frac {1}{\sqrt {4-x^2}} ~dx =  \frac {1}{2 \cos (u)} 2 \cdot \cos (u) ~du = du$
- **Used 2019**

4. $\displaystyle \int \frac {x}{\sqrt {4-x^4}} ~dx = \color {blue} {\frac {1}{2} \sin ^{-1} (\frac {x^2}{2})}$

- **Solution:** $2 \sin (u) = x^2$, $\cos (u) ~du = x ~dx$
- **Solution:** $\frac {1}{\sqrt {4-x^4}} \cdot x ~dx = \frac {1}{2 \cos (u)} \cdot \cos (u) ~du \frac {1}{2} ~du$
- **Another Solution:** $u = \frac {1}{2} x^2$, $du = x ~dx$
- **Another Solution:** $\frac {1}{\sqrt {4-x^4}} \cdot x ~dx = \frac {1}{2 \sqrt {1-u^2}} ~du$

###### Sec

5. $\displaystyle \int \frac {\sqrt {x^2-a^2}}{x} ~dx = \tan (\sec ^{-1} (\frac {x}{a})) - a \sec ^{-1} (\frac {x}{a}) = \color {blue} {\sqrt {x^2-a^2} - a \sec ^{-1} (\frac {x}{a})} = \color {blue} {\sqrt {x^2-a^2} - a \tan ^{-1} (\frac {\sqrt {x^2 - a^2}}{a})}​$

- **Solution:** $\sec (u) = \frac {1}{a} x$, $\tan (u) \sec (u) ~du = \frac {1}{a} ~dx$
- **Solution:** $\frac {\sqrt {x^2-a^2}}{x} ~dx = \frac {a \tan (u)}{a \sec (u)} \cdot a \tan (u) \sec (u) ~du = a \tan ^2 (u) ~du = a (\sec ^2 (u) - 1) ~du$

  1. $\displaystyle \int \frac {\sqrt {x^2-1}}{x} ~dx = \color {blue} {\sqrt {x^2-1} - \sec ^{-1} (x)} = \color {blue} {\sqrt {x^2-1} - \tan ^{-1} (\sqrt {x^2-1})}$
  2. $\displaystyle \int \frac {\sqrt {x^2-9}}{x} ~dx = \color {blue} {\sqrt {x^2-9} - 3 \sec ^{-1} (\frac {x}{3})} = \color {blue} {\sqrt {x^2-9} - 3 \tan ^{-1} (\frac {\sqrt {x^2-9}}{3})}$

  - **Used 2019**, *Unsolved*

6. $\displaystyle \int \frac {1}{x^2\sqrt {x^2-a^2}} ~dx = \frac {1}{a^2} \sin(\sec ^{-1} (\frac {x}{a})) = \color {blue} {\frac {\sqrt {x^2 - a^2}}{a^2 x}}​$

- **Solution:** $\sec (u) = \frac {1}{a} \cdot x$, $\tan (u) \sec (u) ~du = \frac {1}{a} ~dx$

- **Solution:** $\frac {1}{x^2 \sqrt {x^2 - a^2}} ~dx = \frac {a^2}{\sec ^2 (u) \cdot a \tan (u)} \cdot a \tan (u) \sec (u) ~du = \frac {1}{a^2} \cos (u) ~du$

  1. $\displaystyle \int \frac {1}{x^2\sqrt {x^2-4}} ~dx = \color {blue} {\frac {\sqrt {x^2 - 4}}{4x}}$

  - **Used 2019**

  1. $\displaystyle \int \frac {1}{x^2\sqrt {x^2-9}} ~dx = \color {blue} {\frac {\sqrt {x^2 - 9}}{9x}}​$
  2. $\displaystyle \int \frac {1}{x^2\sqrt {4x^2-1}} ~dx = 2\sin(\sec ^{-1} (2x))= \color {blue} {\frac {\sqrt {4x^2-1}}{x}}$

  - **Solution:** $\frac {1}{x^2\sqrt {4x^2-1}} = \frac {1}{2} \cdot \frac {1}{x^2\sqrt {x^2 - (\frac {1}{2})^2}} $
  - **Used 2018**, *Unsolved*

7. $\displaystyle \int \frac {1}{2x\sqrt {x^2-16}} ~dx = \color {blue} {\frac {1}{8} \sec ^{-1} (\frac {x}{4})} = \color {blue} {\frac {1}{8} \tan ^{-1} (\frac {\sqrt {x^2-16}}{4})}$

- **Solution: **$\sec (u) = \frac {1}{4} x​$, $\tan (u) \sec (u) ~du = \frac {1}{4} dx​$
- **Solution:** $\frac {1}{2x\sqrt {x^2-16}} ~dx = \frac {1}{2 \cdot 4 \sec (u) \cdot 4 \tan (u)} \cdot 4 \tan (u) \sec (u) ~du = \frac {1}{8} ~du$
- **Another Solution:** $u^2 = x^2 - 16​$, $u ~du = x ~dx​$
- **Another Solution:** $\frac {1}{2x\sqrt {x^2-16}} ~dx = \frac {1}{2 (u^2 + 16) u} \cdot u ~du = \frac {1}{2} \cdot. \frac {1}{u^2 + 16}$

###### Tan

8. $\displaystyle \int \frac {1}{\sqrt {x^2 + 25}} ~dx = \ln (\frac {x}{5} + \sec (\tan ^ {-1} (\frac {x}{5}))) = \color {blue} {\ln(x + \sqrt {x^2+25})}$

- **Solution:** $\tan (u) = \frac {1}{5} x$, $\sec ^2 (u) ~du = \frac {1}{5} ~dx$
- **Solution:** $\frac {1}{\sec (u)} \cdot \sec ^2 (u) ~du = \sec (u) ~du$
- **Used 2018**, *Unsolved*

9. $\displaystyle \int \frac {1}{(1+x^2)^{\frac {3}{2}}} ~dx = \sin (\tan ^{-1} (x)) = \color {blue} {\frac {x}{\sqrt {1+x^2}}}$

- **Solution:** $\tan (u) = x$, $\sec ^2 (u) ~du = dx$
- **Solution:** $\frac {1}{(1+x^2)^{\frac {3}{2}}} ~dx = \frac {1}{\sec ^3 (u)} \cdot \sec ^2 (u) ~du = \cos (u) ~du$ 



##### Level 3

1. $\displaystyle \int \frac {x^2 + 2x + 1}{x\sqrt {x^2-1}}~dx = \color {blue} {2\ln(\sqrt {x^2-1}+x)+\sqrt {x^2-1}+\sec ^{-1} (x)}$

- **Solution:** $\sec (u) = x$, $\tan (u) \sec (u) ~du = dx$
- **Solution:** $\frac {x^2 + 2x + 1}{x\sqrt {x^2-1}} ~dx = (\frac {x^2}{x\sqrt {x^2-1}} + \frac {2x + 1}{x\sqrt {x^2-1}}) ~dx = \frac {2}{\tan (u)} \cdot \tan (u) \sec (u) ~du + (\frac {2}{\sqrt {x^2-1}} + \frac {1}{x\sqrt {x^2-1}}) ~dx$
- **Used 2019**

2. $\displaystyle \int \frac {x+16}{\sqrt {x^2-4x+8}} ~dx = \color {blue} {\sqrt {x^2-4x+8} + 18 \ln (\sqrt {x^2-4x+8} + x - 2)}$

- **Solution:** $2 \tan (u) = x - 2$, $ \sec ^2 (u) ~du = dx$
- **Solution:** $\frac {x+16}{\sqrt {x^2-4x+8}} ~dx = \frac {2 \tan (u) + 18}{2 \sec (u)} \cdot 2 \sec ^2 (u) ~du = 2 (\tan (u) \sec (u) + 9 \sec (u)) ~du$
- **Used 2019**, *Unsolved*



## Integration by Parts

##### Level 1

1. $\displaystyle \int \ln (ax + b) ~dx = \color{blue} {\frac {ax + b}{a} \ln (ax + b) - x}$

- **Solution:** $u = \ln (ax + b)​$, $v = x​$, $du = \frac {a}{ax + b} ~dx​$, $dv = dx​$

  1. $\displaystyle \int \log _3 (x) ~dx = \color{blue} { \frac {x \ln (x) - x}{\ln (3)}}​$

  - **Solution:** $ \log _3 (x) =  \frac {\ln (x)}{\ln (3)}$
  - **Used 2019**

  2. $\displaystyle \int_{1}^{e} \ln (\sqrt {x}) ~dx = \color{blue} { \frac {1}{2}}​$

  - **Solution:** $ \ln (\sqrt {x}) =  \frac {1}{2} \ln (x)​$

  3. $\displaystyle \int \ln(x^2 + 6x + 5) ~dx = \color{blue} { (x + 1) \ln (x + 1) + (x + 5) \ln (x + 5) - 2x}​$

  - **Solution:** $ \ln(x^2 + 6x + 5)=  \ln (x + 5)(x + 1) = \ln (x + 5) + \ln (x + 1)​$
  - **Used 2018**, *Unsolved*
  - **Used 2019**

  4. $\displaystyle \int \ln(x^2-1) ~dx =  \color{blue} { (x + 1) \ln(x + 1) + (x - 1) \ln(x - 1) - 2x}$

  - **Solution:** $\ln (x^2 - 1) = \ln (x + 1)(x - 1) = \ln (x + 1) + \ln (x - 1)​$

2. $\displaystyle \int x^n \ln(x) ~dx =  \color{blue} { \frac {x^{n + 1}}{n + 1} (\ln (x) - \frac {1}{n + 1})}​$

- **Solution:** $u = \ln (x)​$, $v = \frac {x^{n + 1}}{n + 1}​$, $du = \frac {1}{x} ~dx​$, $dv = x^n ~dx​$

  1. $\displaystyle \int_{1}^{\infty} \frac {\ln(x)}{x^2} ~dx = \color{blue} {1}​$

  - **Solution:** $\frac {x^{(-2) + 1}}{(-2) + 1} (\ln (x) - \frac {1}{(-2) + 1}) = - \frac {\ln (x) + 1}{x}​$
  - **Solution:** $\lim_{x \to \infty} \frac {\ln (x) + 1}{x} = \lim_{x \to \infty} \frac {\frac {1}{x} + 0}{1} = 0​$ (L'Hospital Rule)

  2. $\displaystyle \int \sqrt {x} \ln(x) ~dx = \color{blue} {\frac {2}{3} x^{\frac {3}{2}} \ln (x) - \frac {4}{9} x^{\frac {3}{2}}}​$

  - **Solution:** $\frac {x^{\frac {1}{2} + 1}}{\frac {1}{2} + 1} (\ln (x) - \frac {1}{\frac {1}{2} + 1}) = \frac {2}{3} x^{\frac {3}{2}} (\ln (x) - \frac {2}{3}) ​$

  3. $\displaystyle \int x^2\ln(x) ~dx = \color{blue} {\frac {1}{3} x^3 \ln (x) - \frac {1}{9} x^3}​$

  - **Solution:** $\frac {x^{2 + 1}}{2 + 1} (\ln (x) - \frac {1}{2 + 1}) = \frac {x^3}{3} (\ln (x) - \frac {1}{3})​$

  4. $\displaystyle \int x \ln(x) ~dx = \color{blue} {\frac {1}{2} x^2 \ln (x) - \frac {1}{4} x^2}$

  - **Solution:** $\frac {x^{1 + 1}}{1 + 1} (\ln (x) - \frac {1}{1 + 1}) = \frac {x^2}{2} (\ln (x) - \frac {1}{2})$
  - **Used 2018**

  5. $\displaystyle \int \frac {\ln(x)}{x} ~dx = \color {blue} {\frac {1}{2} \ln ^2 (x)}$

  - **Solution:** $u = \ln (x)$, $du = \frac {1}{x} ~dx$
  - THIS IS DIFFERENT FROM THE REST (u-sub)

3. $\displaystyle \int \ln ^2 (x) ~dx = \color{blue} {2 x - 2 x \ln (x) + x \ln ^2 (x)}​$

- **Solution:** $u = \ln ^2 (x)​$, $v = x​$, $du = \frac {2 \ln (x)}{x} ~dx​$, $dv = dx​$
- **Solution:** $x \ln ^2 (x) - \int x \cdot \frac {2 \ln (x)}{x} ~dx = x \ln ^2 (x) - 2(x \ln (x) - x)$
- **Used 2019**

4. $\displaystyle \int x^a e^{bx} ~dx = \frac {1}{b} x^a e^{bx} - \int \frac {a}{b} x^{a-1} e^{bx}$

   1. $\displaystyle \int xe^{2x} ~dx = \color {blue} {\frac {1}{4} (2x-1) e^{2x}}​$
   2. $\displaystyle \int x^3 e^{-x} ~dx = \color {blue} {- (x^3 + 3x^2 + 6x + 6) e^{-x}}$
   3. $\displaystyle \int_0^{\infty} x^3 e^{-x} ~dx = \color {blue} {6}​$
   4. $\displaystyle \int x^2e^x ~dx =\color {blue}{(x^2 - 2x + 2) e^x}​$

   - **Used 2018**

   5. $\displaystyle \int xe^{-x} ~dx = \color {blue} {- (x + 1) e^ {-x}}$
   6. $\displaystyle \int_{0}^{\infty} x^3e^{-x^2} ~dx = \color {blue} {\frac {1}{2}}​$

   - **Solution:** $x^3e^{-x^2} dx = \frac {1}{2} x^2 e^{-x^2} dx^2$
   - **Used 2019**

5. $\displaystyle \int e^{x^{\frac {1}{a}}} ~dx$

- **Solution:** $u = x^{\frac {1}{a}}$, $u^a = x$, $a u^{a - 1} ~du = dx$
- **Solution:** $\int e^{x^{\frac {1}{a}}} ~dx = \int e^{u} a u^{a - 1} ~du$

   1. $\displaystyle \int e^{\sqrt {x}} ~dx = \color {blue} {2 (\sqrt {x} - 1) e^{\sqrt {x}}}$

   - **Used 2019**

   1. $\displaystyle \int e^{\sqrt[3]{x}} ~dx = \color {blue} {(x^{\frac {2}{3}} - 2x^{\frac {1}{3}} + 2) e^{x^{\frac {1}{3}}}}$

6. $\displaystyle \int e^{x} \sin (x) ~dx = \color {blue} {\frac {1}{2} e^{x} (\sin (x) - \cos (x))}​$   

- **Solution:** $u_1 = \sin (x)​$, $v_1 = e^x​$, $du_1 = \cos (x) ~dx​$, $dv_1 = e^x ~dx​$
- **Solution:** $u_2 = \cos (x)$, $v_2 = e^x$, $du_2 = - \sin (x) ~dx$, $dv_2 = e^x ~dx$
- **Solution:** $e^x \sin (x) - \int e^x \cos (x) ~dx = e^x \sin (x) - (e^x \cos (x) - \int - e^x \sin (x) ~dx)$

  1. $\displaystyle \int \frac {\sin(\sqrt {x})e^{\sqrt {x}}}{\sqrt {x}}~dx = \color {blue} {e^{\sqrt {x}}(\sin(\sqrt {x})-\cos(\sqrt {x}))}$

  - **Solution:** $\frac {\sin(\sqrt {x})e^{\sqrt {x}}}{\sqrt {x}}~dx = 2 \sin (\sqrt {x}) e^{\sqrt {x}} ~d\sqrt {x}$
  - **Used 2019**

7. $\displaystyle \int e^x\cos(x) ~dx = \color {blue} {\frac {1}{2} e^x (\cos(x) +\sin(x))}$

- **Solution:** $u_1 = \cos (x)​$, $v_1 = e^x​$, $du_1 = - \sin (x) ~dx​$, $dv_1 = e^x ~dx​$
- **Solution:** $ u_2 = \sin (x)$, $v_2 = e^x$, $du_2 = \cos (x) ~dx$, $dv_2 = e^x ~dx$
- **Solution:** $e^x \cos (x) - \int - e^x \sin (x) ~dx = e^x \cos (x) + (e^x \sin (x) - \int e^x \cos (x) ~dx)$

8. $\displaystyle \int \sin(\ln(x)) ~dx = \color {blue} {\frac {1}{2} x (\sin (\ln (x)) - \cos (\ln (x)))}​$

- **Solution:** $u_1 = \sin (\ln (x))​$, $v_1 = x​$, $du_1 = \frac {\cos (\ln (x))}{x}​$, $dv_1 = dx​$
- **Solution:** $u_2 = \cos (\ln (x))$, $v_2 = x$, $du_2 = \frac {- \sin (\ln (x))}{x}$, $dv_2 = dx$
- **Solution:** $x \sin (\ln (x)) - \int \frac {\cos (\ln (x))}{x} \cdot x ~dx = x \sin (\ln (x)) - (x \cos (\ln (x)) - \int \frac {- \sin (\ln (x))}{x} \cdot x ~dx)​$



##### Level 2

1. $\displaystyle \int x\sec ^{-1} (x) ~dx = \color {blue} {\frac {1}{2} (x^2 \sec ^{-1} (x) - \sqrt {x^2 - 1})}​$

- **Solution:** $u = \sec ^{-1} (x)$, $v = \frac {1}{2} x^2$, $du = \frac {1}{x \sqrt {x^2-1}} ~dx$, $dv = x ~dx$
- **Solution:** $\frac {1}{2} x^2 \sec ^{-1} (x) - \int \frac {1}{x \sqrt {x^2-1}} \cdot \frac {1}{2} x^2 ~dx​$

2. $\displaystyle \int x\sec ^{-1} (x) ~dx = \color {blue} {\frac {1}{2} (x^2 \csc ^{-1} (x) + \sqrt {x^2 - 1})}​$

- **Solution:** $u = \csc ^{-1} (x)​$, $v = \frac {1}{2} x^2​$, $du = - \frac {1}{x \sqrt {x^2-1}} ~dx​$, $dv = x ~dx​$

- **Solution:** $\frac {1}{2} x^2 \csc ^{-1} (x) - \int - \frac {1}{x \sqrt {x^2-1}} \cdot \frac {1}{2} x^2 ~dx​$

  1. $\displaystyle \int x\sin^{-1}(\frac {1}{x}) ~dx = \color {blue} {\frac {1}{2} (x^2 \csc ^{-1} (x) + \sqrt {x^2 - 1})} = \color {blue} {\frac {1}{2} (x^2 \sin ^{-1} (\frac {1}{x}) + \sqrt {x^2 - 1})}$

  - **Solution:** $x \sin ^{-1} (\frac {1}{x}) = x \csc ^{-1} (x)$

3. $\displaystyle \int x\tan ^{-1} (x) ~dx = \color {blue} {\frac {1}{2} (x^2 \tan^{-1}(x) - x +\tan^{-1}(x))}$

- **Solution:** $u = \tan ^{-1} (x)$, $v = \frac {1}{2} x^2$, $du = \frac {1}{x^2 + 1} ~dx$, $dv = x ~dx$
- **Solution:** $\frac {1}{2} x^2 \tan ^{-1} (x) - \int \frac {1}{x^2 + 1} \cdot \frac {1}{2} x^2 ~dx = \frac {1}{2} x^2 \tan ^{-1} (x) - \frac {1}{2} \int (1 - \frac {1}{x^2 + 1}) ~dx$

  1. $\displaystyle \int_{0}^{1} x \tan ^{-1} (x) ~dx = \color {blue} {\frac {\pi}{4}-\frac {1}{2}}$

  - **Solution:** $\frac {1}{2} ((x^2 +1) \tan^{-1}(x) - x) |_{0}^{1} = (\tan ^{-1} (1) - \frac {1}{2}) - (0 - 0)​$

4. $\displaystyle \int x \sin(2x) ~dx = \color {blue} {\frac {1}{2} x \cos (2x) + \frac {1}{4} \sin (2x)}$

- **Solution:** $u = x$, $v = - \frac {1}{2} \cos (2x)$, $du = dx$, $dv = \sin (2x) ~dx$
- **Solution:** $- \frac {1}{2} x \cos (2x) - \int \sin (2x) ~dx$
- **Used 2018**



##### Level 3

1. $\displaystyle \int \frac {x + \sin(x)}{1 + \cos(x)}~dx = \color {blue} {\frac {x \sin (x)}{1 + \cos (x)}} = \color {blue} {x \tan \frac {x}{2}}$

- **Solution:** $u = x$, $v = \frac {\sin (x)}{1 + \cos (x)}$, $du = dx$, $dv = \frac {\cos (x) + \cos ^2 (x) + \sin ^2 (x)}{(1 + \cos (x))^2} = \frac {1}{1 + \cos (x)} ~dx$
- **Solution:** $\int \frac {x + \sin(x)}{1 + \cos(x)}~dx = \int \frac {x}{1 + \cos(x)} ~dx + \int \frac {\sin (x)}{1 + \cos(x)} ~dx = x \cdot \frac {\sin (x)}{1 + \cos (x)} - \int \frac {\sin (x)}{1 + \cos(x)} ~dx  + \int \frac {\sin (x)}{1 + \cos(x)} ~dx$

2. $\displaystyle \int \frac {xe^x}{(e^x + 1)^2}~dx = \color {blue} {- \frac {x}{e^x+1} + x  - \ln(e^x+1)} = \color {blue} {\frac {xe^x}{e^x+1} - \ln(e^x  + 1)}$ 

- **Solution:** $u = x$, $v = - \frac {1}{e^x + 1}$, $du = dx$, $dv = \frac {e^x}{(e^x + 1)^2} ~dx$
- **Solution:** $- \frac {x}{e^x + 1} - \int - \frac {1}{e^x + 1} ~dx = - \frac {x}{e^x + 1} + \int (1 - \frac {e^x}{e^x + 1}) ~dx$

3. $\displaystyle \int \ln (\sqrt {x^2+1}) ~dx = \color {blue} {\frac {1}{2} x \ln (x^2+1) - x + \tan ^{-1} (x)}​$

- **Solution:** $u = \frac {1}{2} \ln (x^2 + 1)$, $v = x$, $du = \frac {2x}{x^2 + 1}~dx $, $dv = dx$
- **Solution** $\frac {1}{2} x \ln (x^2 + 1) - \int \frac {2x}{x^2 + 1} \cdot x ~dx = \frac {1}{2} x \ln (x^2 + 1) - \int (1 - \frac {1}{x^2 + 1}) ~dx$
- **Used 2019**, *Unsolved*

4. $\displaystyle \int \frac {2 \tan ^{-1} e^x}{e^{2x}} ~dx = \color {blue} {- e^{2x} \tan ^{-1} (e^x) - e^{-x} - \tan ^{-1} (e^x)}$

- **Solution:** $u = \tan ^{-1} (e^x)$, $v = - \frac {1}{2} e^{-2x}$, $du = \frac {e^x}{e^{2x} + 1} ~dx$, $dv = e^{-2x} ~dx$
- **Solution:** $2(- \frac {1}{2} e^{-2x} \tan ^{-1} (e^x) - \int - \frac {1}{2} e^{-2x} \cdot \frac {e^x}{e^{2x} + 1} ~dx) = - e^{-2x} \tan ^{-1} (e^x) + \int \frac {e^{-x}}{e^{2x} + 1} ~dx = - e^{-2x} \tan ^{-1} (e^x) + \int (e^{-x} - \frac {e^x}{e^{2x} + 1}) ~dx$
- **Used 2018**




## Partial Fraction Decomposition

##### Level 1

1. $\displaystyle \int \frac {x}{x-1} ~dx = \color{blue} {x + \ln (1 - x)}$

- **Solution:** $\frac {x}{x-1} = 1 + \frac {1}{x-1}$
- **Used 2018**

2. $\displaystyle \int \frac {7x + 5}{x^2 + x - 2} ~dx = \color{blue} {3 \ln (x + 2) + 4 \ln (x - 1)}$

-  **Solution:** $\frac {7x + 5}{x^2 + x - 2} = 3 \cdot \frac {1}{x + 2} + 4 \cdot \frac {1}{x - 1}$

3. $\displaystyle \int \frac {x}{x^2 - x - 6} ~dx = \color{blue} {\frac {3}{5} \ln (x - 3) + \frac {2}{5} \ln (x + 2)}$ 

- **Solution:** $\frac {x}{x^2 - x - 6} = \frac {3}{5} \cdot \frac {1}{x - 3} + \frac {2}{5} \cdot \frac {1}{x + 2}$

4. $\displaystyle \int \frac {1+x^2}{1-x^2} ~dx = \color{blue} {- x + \ln(x+1) - \ln(x-1)}$

- **Solution: ** $\frac {1+x^2}{1-x^2} = - 1 + \frac {1}{x + 1} - \frac {1}{x - 1}$

5. $\displaystyle \int \frac {1}{x(x-1)^2} ~dx = \color{blue} {\ln (x) - \ln (x - 1) - \frac {1}{x - 1}}$

- **Solution:** $\frac {1}{x(x - 1)^2} = \frac {1}{x} - \frac {1}{x - 1} + \frac {1}{(x -1)^2}$
- **Used 2018**, *Unsolved*
- **Used 2019**

6. $\displaystyle \int \frac {x}{(x+5)^2} ~dx = \color{blue} {\frac {5}{x+5} + \ln (x+5)}$

- **Solution:** $\frac {x}{(x+5)^2} = \frac {1}{x + 5} - 5 \cdot \frac {1}{(x+5)^2}$
- **Used 2018**, *Unsolved*



##### Level 2

1. $\displaystyle \int \frac {x^3 + 4x^2}{x^2 + 4x + 3} ~dx = \color{blue} {\frac {1}{2} x^2 - \frac {9}{2} \ln (x + 3) + \frac {3}{2} \ln (x+1)}$

- **Solution:** $\frac {x^3 + 4x^2}{x^2 + 4x + 3} = x - \frac {9}{2} \cdot \frac {1}{x + 3} + \frac {3}{2} \cdot \frac {1}{x + 1}$

2. $\displaystyle \int \frac {2x^3 + 2x^2 - 9x - 1}{x^2 + x - 6} ~dx = \color{blue} {x^2 +2 \ln (x + 3) + \ln (x - 2)}$

- **Solution:** $\frac {2x^3 + 2x^2 - 9x - 1}{x^2 + x - 6} = 2x + 2 \cdot \frac {1}{x + 3} + \frac {1}{x - 2}$
- **Used 2019**, *Unsolved*

3. $\displaystyle \int \frac {x^3 - x^2 -3x +1}{x^2 - x - 6} ~dx = \color{blue} {\frac {1}{2} x^2 + 2 \ln (x - 3) + \ln (x + 2)}$

- **Solution:** $\frac {x^3 - x^2 -3x +1}{x^2 - x - 6} = x + 2 \cdot \frac {1}{x - 3} + \frac {1}{x + 2}$

4. $\displaystyle \int \frac {3x^3 - 12x^2 + 15x - 5}{x^2 - 4x + 4} ~dx = \color{blue} {\frac {3}{2} x^2 + 3 \ln (x - 2) - \frac {1}{x - 2}}$

- **Solution:** $\frac {3x^3 - 12x^2 + 15x - 5}{x^2 - 4x + 4} = 3x + 3 \cdot \frac {1}{x - 2} + \frac {1}{(x - 2)^2}$

5. $\displaystyle \int \frac {x(x^2 - 3x + 5)}{x^2 - 2x + 1} ~dx = \color{blue} {\frac {1}{2} x^2 - x + \ln (x - 1) - \frac {3}{x - 1}}$

- **Solution:** $\frac {x(x^2 - 3x + 5)}{x^2 - 2x + 1} = x - 1 + 2 \cdot \frac {1}{x - 1} + 3 \cdot \frac {1}{(x - 1)^2}$

6. $\displaystyle \int \frac {x^3 -4x^2 + 2x - 3}{x+2} ~dx = \color{blue} {\frac 1 3 x^3 -3x^2 + 14x - 31\ln(x+2)}$

- **Solution:** $\frac {x^3 - 4x^2 + 2x - 3}{x+2} = x^2 - 6x + 14 - 31 \cdot \frac {1}{x + 2}$
- **Used 2018**, *Unsolved*

7. $\displaystyle \int \frac {x^4 - 2x^3 - 8x^2 + 2x + 10 }{x^2 - 2x - 8} ~dx =  \color{blue} {\frac {1}{3} x^3 + 3 \ln (x - 4) - \ln (x + 2)}$ 

- **Solution:** $\frac {x^4 - 2x^3 - 8x^2 + 2x + 10 }{x^2 - 2x - 8} = x^2 + 3 \cdot \frac {1}{x - 4} - \frac {1}{x + 2}$



##### Level 3

1. $\displaystyle \int \frac {x^2}{x^2+1} ~dx = \color{blue} {x - \tan ^{-1} (x)}$

- **Solution:** $\frac {x^2}{x^2+1} = 1 - \frac {1}{x^2+1}$

2. $\displaystyle \int \frac {4x^2 + x + 7}{x^2 + 1} ~dx = \color{blue}  {4x + \frac {1}{2} \ln (x^2 + 1) + 3 \tan ^{-1} (x)}$

- **Solution:** $\frac {4x^2 + x + 7}{x^2 + 1} = 4 + \frac {1}{2} \cdot \frac {2x}{x^2 + 1} + 3 \cdot \frac {1}{x^2 + 1}$

3. $\displaystyle \int \frac {3x^2 + x + 3}{x(x^2+1)} ~dx = \color{blue} {3 \ln (x) + \tan ^{-1} (x)}$

- **Solution:** $\frac {3x^2 + x + 3}{x(x^2+1)} = 3 \cdot \frac {1}{x} + \frac {1}{x^2 + 1}$

4. $\displaystyle \int \frac {2x-3}{x^3 + x} ~dx = \color{blue} {- 3 \ln (x) + \frac {3}{2} \ln (x^2+1) +2\tan ^{-1} (x)}$

- **Solution:** $\frac {2x - 3}{x^3 + x} = - 3 \cdot \frac {1}{x} + \frac {3}{2} \cdot \frac {2x}{x^2 + 1} + 2 \cdot \frac {1}{x^2 +  1}$

5. $\displaystyle \int \frac {4x^2 - 11x - 19}{(x-5)(x^2 + 1)} ~dx =  \color{blue} {\ln (x - 5) + \frac {3}{2} \ln (x^2 + 1) + 4 \tan ^{-1} (x)}$

- **Solution:** $\frac {4x^2 - 11x - 19}{(x-5)(x^2 + 1)} = \frac {1}{x - 5} + \frac {3}{2} \cdot \frac {2x}{x^2 + 1} + 4 \cdot \frac {1}{x^2 + 1}$

6. $\displaystyle \int \frac {3x^2 + 2x - 7}{x^2(x-5) + (x-5)} ~dx = \color{blue} {3 \ln (x - 5) + 2 \tan ^{-1} (x)}$

- **Solution: ** $\frac {3x^2 + 2x - 7}{x^2(x-5) + (x-5)} = 3 \cdot \frac {1}{x - 5} + 2 \frac {1}{x^2 + 1}$

7. $\displaystyle \int \frac {-2x+4}{(x^2+1)(x-1)^2} ~dx = \color{blue} {- 2 \ln (x - 1) - \frac {1}{x-1} + \ln (x^2 + 1) + \tan ^{-1} (x)}$

- **Solution:** $\frac {-2x+4}{(x^2+1)(x-1)^2} = - 2 \cdot \frac {1}{x - 1} + \frac {1}{(x - 1)^2} + \frac {2x}{x^2 + 1} + \frac {1}{x^2 + 1}$

8. $\displaystyle \int \frac {x^4 + 2x^3 + 5x^2 + 4x + 6}{x^3 + x^2 + x + 1} ~dx = \color{blue} {\frac {1}{2} x^2 + x + 3 \ln (x + 1) + 2 \tan ^{-1} (x)}$

- **Solution:** $\frac {x^4 + 2x^3 + 5x^2 + 4x + 6}{x^3 + x^2 + x + 1} = x + 1 + 3 \cdot \frac {1}{x + 1} + 2 \cdot \frac {1}{x^2 + 1}$

9. $\displaystyle \int \frac {2x^5 + 4x^3 + 4x}{x^4+1} ~dx = \color{blue} {x^2 + \ln (x^4+1) + \tan ^{-1} (x^2)}$

- **Solution:** $\frac {2x^5 + 4x^3 + 4x}{(x^4+1)} = 2x + \frac {4x^3}{x^4 + 1} + \frac {2x}{x^4 + 1}$
- **Used 2019**



## Powers of Sine and Cosine

##### Trick

$\displaystyle \int \sin ^n (x) ~dx = \frac {n - 1}{n} \int \sin ^{n - 2} (x) ~dx - \frac {1}{n} \cos (x) \sin ^{n - 1} (x)$

$\displaystyle \int \cos ^n (x) ~dx = \frac {n - 1}{n} \int \cos ^{n - 2} (x) ~dx + \frac {1}{n} \sin (x) \cos ^{n - 1} (x)$



##### Level 2

1. $\displaystyle \int \sin ^2 (x) ~dx = \color {blue} {\frac {1}{2} (x - \sin (x) \cos (x))}$

- **Solution:** $\sin ^2 (x) = \frac {1 - \cos (2x)}{2}$

2. $\displaystyle \int \cos ^2 (x) ~dx = \color {blue} {\frac {1}{2} (x + \sin (x) \cos (x))}$

- **Solution:** $\cos ^2 (x) = \frac {1 + \cos (2x)}{2}$

3. $\displaystyle \int \sin ^3 (x) ~dx = \color {blue} {\frac {1}{3} \cos ^3 (x) - \cos (x)} = \color {blue} {\frac {1}{12} \cos (3x) - \frac {3}{4} \cos (x)}$

- **Solution:** $\sin ^3 (x) ~dx = (1 - \cos ^2 (x)) \sin (x) ~dx = (\cos ^2 (x) - 1) ~d\cos(x)$

- **Another Solution:** $\sin ^3 (x) = \frac {1}{4} (3 \sin (x) - \sin (3x))$

  1. $\displaystyle\int \frac {\sin ^3 {\sqrt {x}}}{2\sqrt {x}} ~dx  = \color {blue} {\frac {1}{3} \cos ^3 (\sqrt {x}) - \cos (\sqrt {x})} = \color {blue} {\frac {1}{12} \cos (3\sqrt {x}) - \frac {3}{4} \cos (\sqrt {x})}$

  - **Solution:** $\frac {\sin ^3 {\sqrt {x}}}{2\sqrt {x}} ~dx = \sin^3{\sqrt {x}} ~d\sqrt {x}​$

4. $\displaystyle \int \cos ^3 (x) ~dx = \color {blue} {\sin (x) - \frac {1}{3} \sin ^3 (x)} = \color {blue} {\frac {1}{12} \sin (3x) + \frac {3}{4} \sin (x)}$

- **Solution:** $\cos ^3 (x) ~dx = (1 - \sin ^2 (x)) \cos (x) ~dx = (1 - \sin ^2 (x)) ~d\sin(x)$
- **Another Solution:** $\cos ^3 (x) = \frac {1}{4} (3 \cos (x) + \cos (3x))$

5. $\displaystyle \int (\sin(x)+1)^3 ~dx = \color {blue} {\frac {5}{2}x+\frac {1}{3}\cos ^3(x)-4\cos (x)-\frac {3}{4}\sin (2x)}$

- **Solution:** $(\sin(x)+1)^3 = \sin ^3 (x) + 3 \sin ^2 (x) + 3 \sin (x) + 1$

6. $\displaystyle \int (\cos(x)+1)^3 ~dx = \color {blue} {\frac {5}{2}x-\frac {1}{3}\sin ^3(x)+4\sin (x)+\frac {3}{4}\sin (2x)}$

- **Solution:** $(\cos(x)+1)^3 = \cos ^3 (x) + 3 \cos ^2 (x) + 3 \cos (x) + 1$

7. $\displaystyle \int \sin ^4 (x) ~dx = \color {blue} {\frac {3}{8} x - \frac {3}{8} \sin (x) \cos (x) - \frac {1}{4} \sin ^3 (x) \cos (x)}​$

- **Solution:** $\frac {4 - 1}{4} \int \sin ^{4 - 2} (x) ~dx - \frac {1}{4} \cos (x) \sin ^{4 - 1} (x) = \frac {3}{4} (\frac {1}{2} (x - \sin (x) \cos (x))) - \frac {1}{4} \cos (x) \sin ^3 (x)$

8. $\displaystyle \int \cos ^4 (x) ~dx = \color {blue} {\frac {3}{8} x + \frac {3}{8} \sin (x) \cos (x) + \frac {1}{4} \sin (x)\cos ^3 (x)}​$

- **Solution:** $\frac {4 - 1}{4} \int \cos ^{4 - 2} (x) ~dx + \frac {1}{4} \sin (x) \cos ^{4 - 1} (x) = \frac {3}{4} (\frac {1}{2} (x + \sin (x) \cos (x))) + \frac {1}{4} \sin (x) \cos ^3 (x)$

9. $\displaystyle \int \cos^4(x) - \sin^4(x) dx = \color {blue} {\frac {1}{2}\sin{2x}}$

- **Solution:** $\cos ^4 (x) - \sin ^4 (x) = (\cos ^2 (x) - \sin ^2 (x)) (\cos ^2 (x) + \sin ^2 (x)) = \cos ^2 (x) - \sin ^2 (x) = \cos (2x)$
- **Used 2019**



##### Level 3

1. $\displaystyle \int (\sin(x) + \cos(x))^2 ~dx = \color {blue} {x-\frac {1}{2}\cos(2x)}$

- **Solution:** $(\sin(x) + \cos(x))^2 = 1 + 2 \sin(x) \cos(x)$

2. $\displaystyle \int \frac {3}{2} \sin(2x)(\sin (x) + \cos (x)) ~dx = \color {blue} {\sin^3 (x) - \cos^3 (x)}$

- **Solution:** $\frac {3}{2} \sin(2x) (\sin (x) + \cos (x)) = 3\sin ^2 (x) \cos (x) + 3\sin (x) \cos ^2 (x)$

3. $\displaystyle \int \cos^2(x)(\sin(x) + 1) ~dx = \color {blue} {- \frac {1}{3} \cos^3(x) + \frac {1}{2} (x + \sin (x) \cos (x))}$

- **Solution:** $\cos^2(x)(\sin(x) + 1) = \cos ^2 (x) \sin (x) + \cos ^2 (x)$

4. $\displaystyle \int \sin^3(x)\cos^5(x) ~dx = \color {blue} {-\frac {1}{6} \cos ^6(x) + \frac {1}{8} \cos ^8(x)}​$

- **Solution:** $\sin ^3 (x) \cos ^5 (x) ~dx = \sin (x) (1 - \cos ^2 (x)) \cos ^5 (x) ~dx = - (\cos ^5 (x) - \cos ^7 (x)) ~d \cos (x)$

5. $\displaystyle \int \cos^3(x) \sin(x) ~dx = \color {blue} {- \frac {1}{4} \cos ^4 (x)} = \color {blue} {\frac {1}{2} \sin ^2 (x) - \frac {1}{4} \sin ^4 (x)}$

- **Solution:** $\cos^3(x) \sin(x) ~dx = - \cos^3(x) ~d \cos (x)$
- **Another Solution:** $\cos^3(x) \sin(x) ~dx = \cos (x) (1 - \sin ^2 (x)) \sin(x) ~dx = (\sin(x) - \sin ^3 (x)) ~d \sin (x)​$

6. $\displaystyle \int \sin^3(x)\sqrt {\cos(x)} dx = \color {blue} {-\frac {2}{3}\cos ^{\frac {3}{2}}(x)+\frac {2}{7}\cos ^{\frac {7}{2}}(x)}$

- **Solution:** $\sin^3(x)\cos ^{\frac {1}{2}} (x) ~dx = \sin (x) (1 - \cos ^2 (x)) \cos ^{\frac {1}{2}} (x) ~dx = - (\cos ^{\frac {1}{2}} (x) - \cos ^{\frac {5}{2}} (x)) ~d \cos (x)$



## Powers of Tangent and Cosecant

##### Trick

$\displaystyle \int \sec ^n (x) ~dx = \frac {n - 2}{n - 1} \int \sec ^{n - 2} (x) ~dx + \frac {1}{n - 1} \tan (x) \sec ^{n - 2} (x)$





##### Level 3

1. $\displaystyle \int \sec^3(x) ~dx = \color {blue} {\frac {1}{2} (\ln (\sec (x) + \tan (x)) + \tan (x) \sec (x))} = \color {blue} {\frac {1}{2} (\ln(\frac {\cos(\frac {x}{2}) +\sin(\frac {x}{2})}{\cos(\frac {x}{2}) -\sin(\frac {x}{2})}) + \tan (x) \sec (x))}$

- **Solution:** $\frac {3 - 2}{3 - 1} \int \sec ^{3 - 2} (x) ~dx + \frac {1}{3 - 1} \tan (x) \sec ^{3 - 2} (x) = \frac {1}{2}  \int \sec (x) ~dx + \frac {1}{2} \tan (x) \sec (x)$

2. $\displaystyle \int \sec^4(x) ~dx = \color {blue} {\frac {2}{3} \tan (x) + \frac {1}{3} \tan (x) \sec ^2 (x)} = \color {blue} {\frac {1}{3} \tan ^3 (x) + \tan (x)}$

- **Solution:** $\frac {4 - 2}{4 - 1} \int \sec ^{4 - 2} (x) ~dx + \frac {1}{4 - 1} \tan (x) \sec ^{4 - 2} (x) = \frac {2}{3} \int \sec ^2 (x) ~dx + \frac {1}{3} \tan (x) \sec ^2 (x)$

   1. $\displaystyle \int \frac {1}{\cos^4(x)} ~dx = \color {blue} {\frac {2}{3} \tan (x) + \frac {1}{3} \tan (x) \sec ^2 (x)} = \color {blue} {\frac {1}{3} \tan ^3 (x) + \tan (x)}$

   - **Solution:** $\frac {1}{\cos^4(x)} = \sec ^4 (x)$

3. $\displaystyle \int \tan ^2 (x) ~dx = \color {blue} {\tan (x) - x}$

- **Solution:** $\tan ^2 (x) = \sec ^2 (x) - 1$

4. $\displaystyle \int \tan ^3 (x) ~dx = \color {blue} {\frac {1}{2} \tan ^2 (x) + \ln (\cos (x))} = \color {blue} {\frac {1}{2} \sec^2 (x) - \ln (\sec (x))}$

- **Solution:** $\tan ^3 (x) = (\sec ^2 (x) - 1) \tan (x)$
- **Another Solution:** $u = \sec (x)$, $du = \sec (x) \tan (x) ~dx$
- **Another Solution:** $\tan ^3 (x) ~dx = (\sec ^2 (x) - 1) \tan (x) ~dx = \frac {u^2 - 1}{u} ~du = (u - \frac {1}{u}) ~du$

5. $\displaystyle \int \tan ^4 (x) ~dx = \color {blue} {\frac {1}{3} \tan ^3 (x) - \tan (x) + x}$

- **Solution:** $\tan ^4 (x) = (\sec ^2 (x) - 1) \tan ^2 (x) = \sec ^2 (x) \tan ^2 (x) - (\sec ^2 (x) - 1)$

6. $\displaystyle \int \sec^3(x)\tan^3(x) ~dx = \color {blue} {-\frac {1}{3} \sec ^3(x) + \frac {1}{5} \sec ^5(x)}$

- **Solution:** $ \sec^3(x)\tan^3(x) ~dx =  \sec ^2 (x) (\sec ^2 (x) - 1) \sec (x) \tan (x) ~dx = \sec ^4 (x) - \sec ^2 (x)) ~d \sec (x)$

7. $\displaystyle \int \tan^4(x) + \tan^2(x) ~dx = \color {blue} {\frac {1}{3} \tan^3(x)}$

- **Solution:** $\tan^4(x) + \tan^2(x) ~dx = \tan ^2 (x) (\tan^2(x) + 1) ~dx = \tan ^2 (x) \sec ^2 (x) ~dx = \tan ^2 (x) ~d \tan (x)$

8. $\displaystyle \int \frac {2\sin^2 (x)}{\cos^3 (x)} ~dx = \color {blue} {- \ln(\tan (x) + \sec (x)) + \tan (x) \sec (x)} = \color {blue} {\ln(\sec (x) - \tan (x)) + \tan (x) \sec (x)} = \tan (x) \sec (x) - \frac {1}{2}(\ln (\sin (x)+1) - \ln (\sin (x)-1))???$

- **Solution:** $\frac {2\sin^2 (x)}{\cos^3 (x)} = 2 \tan^2 (x) \sec (x) = 2 (\sec^2 (x) - 1) \sec (x) = 2(\sec^3 (x) -\sec (x))$


## Products to Sum / Sums to Product formulas

##### Trick

$\sin (x) + \sin (y) = 2 \sin (\frac {x + y}{2}) \cos (\frac {x - y}{2})$

$\sin (x) - \sin (y) = 2 \cos (\frac {x + y}{2}) \sin (\frac {x - y}{2})​$

$\cos (x) + \cos (y) = 2 \cos (\frac {x + y}{2}) \cos (\frac {x - y}{2})​$

$\cos (x) - \cos (y) = - 2 \sin (\frac {x + y}{2}) \sin (\frac {x - y}{2})​$

$\tan (x) - \tan (y) = \frac {\sin (x + y)}{\cos {x} \cos (y)}$



$\sin (x) \cos (y) = \frac {1}{2} (\sin (x + y) + \sin (x - y))$

$\cos (x) \sin (y) = \frac {1}{2} (\sin (x + y) - \sin (x - y))$

$\cos (x) \cos (y) = \frac {1}{2} (\cos (x + y) + \cos (x - y))$

$\sin (x) \sin (y) = - \frac {1}{2} (\cos (x + y) - \cos (x - y))$



##### Level 1

1. $\displaystyle \int \cos (x+\frac {\pi}{4}) \cos(x- \frac {\pi}{4}) ~dx = \color {blue} {\frac {1}{4} \sin(2x)}$

- **Solution:** $\cos (x+\frac {\pi}{4}) \cos (x- \frac {\pi}{4}) = \frac {1}{2} (\cos ((x + \frac {\pi}{4}) + (x - \frac {\pi}{4})) + \cos ((x + \frac {\pi}{4}) - (x - \frac {\pi}{4}))) =  \frac {1}{2} \cos (2x)$

2. $\displaystyle \int \sin(4x)\cos(3x)~dx = \color {blue} {- \frac {1}{14} \cos(7x) - \frac {1}{2} \cos(x)}$

- **Solution:** $\sin (4x) \cos (3x) = \frac {1}{2} (\sin (4x + 3x) + \sin (4x - 3x)) = \frac {1}{2} (\sin (7x) + \sin (x))$
- **Used 2018**, *Unsolved*

3. $\displaystyle \int 4\cos (x) \cos (2x) \sin (3x) ~dx = \color {blue} {- \frac {1}{6} \cos (6x) - \frac {1}{4} \cos (4x) - \frac {1}{2} \cos (2x)}$

- **Solution:** $2 \cos (x) \cos (2x) = \cos (x + 2x) + \cos (x - 2x) = \cos (3x) + \cos (x)$
- **Solution:** $2 \cos (3x) \sin (3x) = \sin (6x)$
- **Solution:** $2 \cos (x) \sin (3x) = \sin (x + 3x) - \sin (x - 3x) = \sin (4x).+ \sin (2x)$ 
- **Used 2018**



## Weierstauss substitution

##### Trick

Let $u = \tan (\frac {x}{2})$

Then, $\sin (x) = \frac {2u}{1 + u^2}​$, $\cos (x) = \frac {1 - u^2}{1 + u^2}​$, $dx = \frac {2}{1 + u^2} ~du​$



##### Level 3

1. $\displaystyle \int \frac {1-\sin(x)}{1 + \cos(x)} ~dx = \color {blue} {\tan (\frac {x}{2}) - \ln (1 + \tan ^2 (\frac {x}{2}))} = \color {blue} {\tan (\frac {x}{2}) - 2 \ln (\sec (\frac {x}{2}))} = \color {blue} {\tan (\frac {x}{2}) + 2 \ln (\cos (\frac {x}{2}))} = \color {blue} {\tan (\frac {x}{2}) + \ln (1+\cos (x))}​$

- **Solution:** $\frac {1-\sin(x)}{1 + \cos(x)} ~dx = \frac {1 - \frac {2u}{1 + u^2}}{1 + \frac {1 - u^2}{1 + u^2}} \cdot \frac {2}{1 + u^2} ~du = \frac {1 + u^2 - 2u}{1 + u^2 + 1 - u^2} \cdot \frac {2}{1 + u^2} ~du = \frac {1 + u^2 - 2u}{1 + u^2} ~du = 1 - \frac {2u}{1 + u^2} ~du$

2. $\displaystyle \int \frac {1+ \sin (x)}{1+\cos (x)} ~dx = \color {blue} {\tan (\frac {x}{2}) + \ln (1 + \tan ^2 (\frac {x}{2}))} = \color {blue} {\tan (\frac {x}{2}) + 2 \ln (\sec (\frac {x}{2}))} = \color {blue} {\tan (\frac {x}{2}) - 2 \ln (\cos (\frac {x}{2}))} = \color {blue} {\tan (\frac {x}{2}) - \ln (1+\cos (x))}$

- **Solution:** $\frac {1+ \sin (x)}{1+\cos (x)} ~dx = \frac {1 + \frac {2u}{1 + u^2}}{1 + \frac {1 - u^2}{1 + u^2}} \cdot \frac {2}{1 + u^2} ~du = \frac {1 + u^2 + 2u}{1 + u^2 + 1 - u^2} \cdot \frac {2}{1 + u^2} ~du = 1 + \frac {2u}{1 + u^2} ~du$

3. $\displaystyle \int \frac {1}{1 + \sin(x) + \cos(x)}~dx = \color {blue} {\ln(\tan(\frac {x}{2}) + 1)}$

- **Solution:** $\frac {1}{1 + \sin (x) + \cos (x)} ~dx = \frac {1}{1 + \frac {2u}{1 + u^2} + \frac {1 - u^2}{1 + u^2}} \cdot  \frac {2}{1 + u^2} ~du = \frac {1 + u^2}{1 + u^2 + 2u + 1 - u^2} \cdot  \frac {2}{1 + u^2} ~du = \frac {1}{1 + u} ~du​$
- **Used 2018**, *Unsolved*



##### Level 4

1. $\displaystyle \int \frac {1}{\sin (x) + \cos (x)} ~dx = \color {blue}{\frac {1}{\sqrt {2}} (\ln (\tan (\frac {x}{2}) - 1 + \sqrt {2}) - \ln (\tan (\frac {x}{2}) - 1 - \sqrt {2}))} = \color {blue} {- \frac {1}{\sqrt {2}} \ln (\csc (x + \frac {\pi}{4}) - \cot (x + \frac {\pi}{4}))}$

- **Solution:** $\frac {1}{\sin (x) + \cos (x)} ~dx = \frac {1}{\frac {2u}{1 + u^2} + \frac {1 - u^2}{1 + u^2}} \cdot  \frac {2}{1 + u^2} ~du = \frac {1 + u^2}{2u + 1 - u^2} \cdot  \frac {2}{1 + u^2} ~du = \frac {1}{\sqrt {2}} (\frac {1}{u + \sqrt {2} - 1} - \frac {1}{u - \sqrt {2} - 1}) ~du​$
- **Another Solution:** $\frac {1}{\sin (x) + \cos (x)} ~dx = \frac {1}{\sqrt {2} \sin (x + \frac {\pi}{4})} ~dx = \frac {1}{\sqrt {2}} \csc (x + \frac {\pi}{4}) ~dx$
- $\ln (\csc (x + \frac {\pi}{4}) - \cot (x + \frac {\pi}{4}))​$
- $= \frac {1 - \cos (x + \frac {\pi}{4})}{\sin (x + \frac {\pi}{4})} = \frac {1 - \frac {1}{\sqrt {2}} (- \sin (x) + \cos (x))}{\frac {1}{\sqrt {2}} (\sin (x) + \cos (x))} = \frac {1 + \frac {1}{\sqrt {2}} (\frac {2 \tan (\frac {x}{2})}{1 + \tan ^2 (\frac {x}{2})} - \frac {1 - \tan ^2 (\frac {x}{2})}{1 + \tan ^2 (\frac {x}{2})})}{\frac {1}{\sqrt {2}} (\frac {2 \tan (\frac {x}{2})}{1 + \tan ^2 (\frac {x}{2})} + \frac {1 - \tan ^2 (\frac {x}{2})}{1 + \tan ^2 (\frac {x}{2})})}$
- $= \frac {1 + \tan ^2 (\frac {x}{2}) + \frac {1}{\sqrt {2}} (2 \tan (\frac {x}{2}) - 1 + \tan ^2 (\frac {x}{2}))}{\frac {1}{\sqrt {2}} (2 \tan (\frac {x}{2}) + 1 - \tan ^2 (\frac {x}{2}))} = \frac {(\frac {1}{\sqrt {2}} + 1) \tan ^2 (\frac {x}{2}) + \sqrt {2} \tan (\frac {x}{2}) + (- \frac {1}{\sqrt {2}} + 1)}{- \frac {1}{\sqrt {2}} ((\tan (\frac {x}{2}) - 1)^2 - 2)} = - \frac {(\sqrt {2} + 1) (\tan (\frac {x}{2}) -1 + \sqrt {2})^2}{(\tan (\frac {x}{2}) - 1 + \sqrt {2})(\tan (\frac {x}{2}) - 1 - \sqrt {2})}​$
- $= - (\sqrt {2} + 1) \frac {\tan (\frac {x}{2}) - 1 + \sqrt {2}}{\tan (\frac {x}{2}) - 1 - \sqrt {2}}​$

2. $\displaystyle \int \frac {\sin(x)}{1 + \sin(x)} ~dx = 2(\tan ^{-1} (\tan (\frac {x}{2})) + \frac {1}{\tan (\frac {x}{2}) + 1}) = \color {blue} {x + \frac {2}{\tan (\frac {x}{2}) + 1}}= \color {blue} {x + \frac {2\sin(\frac {x}{2})}{\sin(\frac {x}{2}) + \cos(\frac {x}{2})}} = \color {blue} {x + \sec (x) - \tan (x)}$

- **Solution:** $\frac {\sin(x)}{1 + \sin(x)} ~dx = \frac {\frac {2u}{1 + u^2}}{1 + \frac {2u}{1 + u^2}} \cdot \frac {2}{1 + u^2} ~du = \frac {2u}{1 + u^2 + 2u} \cdot \frac {2}{1 + u^2} ~du = 2(\frac {1}{1 + u^2} - \frac {1}{(u + 1)^2}) ~du​$

  1. $\displaystyle \int \frac {1}{1+\sin (x)} ~dx = \color {blue} {- \frac {2}{\tan (\frac {x}{2}) + 1}} $

  - **Solution:** $\frac {1}{1 + \sin(x)} = 1 - \frac {\sin(x)}{1 + \sin(x)}$

  2. $\displaystyle \int \frac {\tan(x)}{\tan(x) + \sec(x)} ~dx =\color {blue} {x + \frac {2}{\tan (\frac {x}{2}) + 1}}​$

  - **Solution:** $\frac {\tan(x)}{\tan(x) + \sec(x)} = \frac {\sin (x)}{1 + \sin (x)}$
  - **Used 2019**, *Unsolved*

3. $\displaystyle \int \frac {\sin (x)}{1-\sin(x)} ~dx = 2(- \frac {1}{\tan (\frac {x}{2}) - 1} - \tan ^{-1} (\tan (\frac {x}{2}))) = \color {blue} {- \frac {2}{\tan (\frac {x}{2}) - 1} - x} = \color {blue} {- \frac {2\sin(\frac {x}{2})}{\cos(\frac {x}{2}) -\sin(\frac {x}{2})} - x}$

- **Solution:** $\frac {\sin(x)}{1 - \sin(x)} ~dx = \frac {\frac {2u}{1 + u^2}}{1 - \frac {2u}{1 + u^2}} \cdot \frac {2}{1 + u^2} ~du = \frac {2u}{1 + u^2 - 2u} \cdot \frac {2}{1 + u^2} ~du = 2(\frac {1}{(u - 1)^2} - \frac {1}{1 + u^2}) ~du$



## Combined Techniques

##### Level 3

1. $\displaystyle \int \frac {x}{x^4-16} ~dx = \color{blue} {\frac {1}{16} (\ln (x^2 - 4) - \ln (x^2 + 4))}$

- **Solution:** $u =x^2$, $du = 2x ~dx$
- **Solution:** $\frac {1}{2} \cdot  \frac {2x ~dx}{x^4 - 16} = \frac {1}{2} \frac {du}{u^2 - 16} = \frac {1}{16} (\frac {1}{u - 4} - \frac {1}{u + 4}) ~du$

2. $\displaystyle \int \frac {x\tan^{-1}(x)}{(x^2+1)^2} ~dx = \color {blue} {- \frac {1}{2 (1 + x^2)} \tan^{-1}(x) + \frac {1}{4 (1 + x^2)} + \frac {1}{4} \tan ^{-1} (x)}$

- **Solution:** $u_1 = \tan ^{-1} (x)$, $v_1 = - \frac {1}{2(x^2 + 1)}$, $du_1 = \frac {1}{x^2 + 1} ~dx$,$dv_1 = \frac {x}{(x^2+1)^2} ~dx$
- **Solution:** $u_2 = \tan ^{-1} (x)$, $\tan (u_2) = x$, $\sec ^2 (u_2) ~du_2 = dx$
- **Solution:** $- \frac {1}{2(x^2 + 1)} \tan ^{-1} (x) - \int - \frac {1}{2(x^2 + 1)^2} ~dx = - \frac {1}{2(x^2 + 1)} \tan ^{-1} (x) + \int \frac {1}{(\sec ^2 (u_2))^2} \cdot \sec ^2 (u_2) ~du_2 = - \frac {1}{2(x^2 + 1)} \tan ^{-1} (x) + \int \cos ^2 (u_2) ~du_2$
- **Used 2019**




## Too Hard

- $\displaystyle \int\sqrt {x\cdot\sqrt[3]{x\cdot\sqrt[4]{x\cdot\sqrt[5]{x...}}}} dx = \frac {x^{e-1}}{e-1}$
  --level 5
  --talyor expansion....
- $\displaystyle \int_{0}^{1} \frac {\sin({\ln(x)})}{\ln(x)} dx = \frac {\pi}{4}$ 
  --level 5
  --requires feynmann technique
- $\displaystyle \int_{-\infty}^{\infty} \frac {\sin^2(x)}{x^2}~dx = \pi$
  --level 5
  --parseval’s theorem
- $\displaystyle lim_{n\to\infty} \int_{0}^{1} \frac {x^n}{1+x}~dx=0$
  --level 4
  --u-substitution
  --interchange of limit and integration (but this method may need theorem to interchange)
- **Used 2019**, *Unsolved*
- $\displaystyle \int_{0}^{\infty} \frac {\sin(x)}{xe^{\sqrt {3}x}}~dx=\frac {\pi}{6}$
  --level 5
  --not sure
- $\displaystyle \int_{-\infty}^{\infty}\frac {\cos(x)}{x^2+1}~dx=\frac {\pi}{e}$
  --level 5
  --not sure
- $\displaystyle \int \sqrt {\frac {1+x}{1-x}}~dx = (x-1)\sqrt {\frac {1+x}{1-x}} - 2\arcsin(\frac {\sqrt {1-x}}{2})$
  - Solution: u-sub $u=1-x$, integration by parts with $u$ equals the square root term, "exotic" elementary antiderivative involving $\arcsin$, a nasty simplification. Probably too hard.