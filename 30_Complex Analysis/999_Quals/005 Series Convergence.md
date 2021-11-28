# Series Convergence 

## Exercises
## Tie,Fall 2015 and Spring 2020 HW2: Ratio Test #work 

Let $a_n\neq 0$ and show that
\[
\lim_{n\to \infty} {\abs{a_{n+1}} \over \abs{a_n}} = L \implies \lim_{n\to\infty} \abs{a_n}^{1\over n} = L
.\]

In particular, this shows that when applicable, the ratio test can be used to calculate the radius of convergence of a power series.


## 1 #work 

Suppose $f$ is analytic on a region $\Omega$ such that $\DD \subseteq \Omega \subseteq \CC$ and $f(z) = \sum_{n=0}^\infty a_n z^n$ is a power series with radius of convergence exactly 1.

a. 
Give an example of such an $f$ that converges at every point of $S^1$.

b.  
Give an example of such an $f$ which is analytic at $1$ but $\sum_{n=0}^\infty a_n$ diverges.

c.  
Prove that $f$ can not be analytic at *every* point of $S^1$.

:::{.concept}
?
:::

\todo[inline]{Missing part (c)}
:::{.solution}
\hfill

a.  

- Take $\sum {z^n \over n^2}$
- Then \[\abs{z}\leq 1 \implies \abs{z^n\over n^2} \leq {1\over n^2}\] which is summable
- So the series converges for $\abs{z}\leq 1$.

b. 
- Take $\sum {z^n \over n}$; 
- Then $z=1$ yields the harmonic series, which diverges.

- For $z\in S^1\setminus\theset{1}$, we have $z = e^{2\pi it}$ for $0<t<2\pi$. 
- So fix $t$.

- Toward applying the Dirichlet test, set $a_n = 1/n, b_n = z^n$.

- Then for all $N$,
\[
\abs{\sum_{n=1}^N b_n}
= \abs{\sum_{n=1}^N b_n}
= \abs{\sum_{n=1}^N z^n}
= \abs{  {z-z^{N+1} \over \abs{1 - z}} } 
\leq {2 \over 1-z} < \infty
.\]

- Thus $\sum a_n b_n < \infty$ and $\sum z^n/n$ converges.

c. ?

:::

## 7 #work

Suppose $\sum_{n=0}^\infty a_n z^n$ converges for some $z_0 \neq 0$.

a.  
Prove that the series converges absolutely for each $z$ with $\abs z < \abs z_0$.

b.  
Suppose $0 < r < \abs{z_0}$ and show that the series converges uniformly on $\abs{z} \leq r$.

## 10 #work

Prove that the following series converges uniformly on the set $\theset{z \suchthat \Im(z) < \ln 2}$:
\[
\sum_{n=1}^\infty {\sin(nz) \over 2^n}
.\]
Suppose $0 < r < \abs{z_0}$ and show that the series converges uniformly on $\abs{z} \leq r$.

### Tie's Extra Questions: Fall 2015 #work

Assume $f(z)$ is analytic in ${\mathbb D}$ and $f(0)=0$ and is not a rotation (i.e. $f(z) \neq e^{i \theta} z$). 
Show that $\displaystyle \sum_{n=1}^\infty f^{n}(z)$ converges uniformly to an analytic function on compact subsets of ${\mathbb D}$, where $f^{n+1}(z) = f(f^{n}(z))$.

### Spring 20202 HW 2 #  2 #work
Let $f$ be a power series centered at the origin.
Prove that $f$ has a power series expansion about any point in its disc of convergence.


### Spring 20202 HW 2 #  3 #work
Prove the following:

a. $\sum_{n} nz^n$ does not converge at any point of $S^1$

b. $\sum_n {z^n \over n^2}$ converges at every point of $S^1$.

c. $\sum_n {z^n \over n}$ converges at every point of $S^1$ except $z=1$.
