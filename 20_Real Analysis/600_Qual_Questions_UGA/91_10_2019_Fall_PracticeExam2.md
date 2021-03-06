# Practice Exam (November 2014)


## Fall 2018 Practice Midterm 2.1 #real_analysis/qual/work
a.
Carefully state Tonelli's theorem for a nonnegative function $F(x, t)$ on $\RR^n\cross \RR$.

b.
  Let $f:\RR^n\to [0, \infty]$ and define
\[
\mca \definedas \theset{(x, t) \in \RR^n\cross \RR \suchthat 0\leq t \leq f(x)}
.\]

  Prove the validity of the following two statements:

  1. $f$ is Lebesgue measurable on $\RR^{n} \iff \mca$ is a Lebesgue measurable subset of $\RR^{n+1}$.
  2. If $f$ is Lebesgue measurable on $\RR^n$ then
  \[
  m(\mathcal{A})=\int_{\mathbb{R}^{n}} f(x) d x=\int_{0}^{\infty} m\left(\left\{x \in \mathbb{R}^{n}\suchthat f(x) \geq t\right\}\right) d t
  .\]


## Fall 2018 Practice Midterm 2.2 #real_analysis/qual/work

a.
Let $f, g\in L^1(\RR^n)$ and give a definition of $f\ast g$.

b.
Prove that if $f, g$ are integrable and bounded, then
\[
(f\ast g)(x) \converges{\abs x\to\infty}\to 0
.\]


c. In parts:

    1. Define the *Fourier transform* of an integrable function $f$ on $\RR^n$.
    2. Give an outline of the proof of the Fourier inversion formula.
    3. Give an example of a function $f\in L^1(\RR^n)$ such that $\hat{f}$ is not in $L^1(\RR^n)$.


## Fall 2018 Practice Midterm 2.3 #real_analysis/qual/work

\label{hilbert_space_exam_question}

Let $\theset{u_n}_{n=1}^\infty$ be an orthonormal sequence in a Hilbert space $H$.

a. Let $x\in H$ and verify that 
\[
\left\|x-\sum_{n=1}^{N}\left\langle x, u_{n}\right\rangle u_{n}\right\|_H^{2} =
\|x\|_H^{2}-\sum_{n=1}^{N}\left|\left\langle x, u_{n}\right\rangle\right|^{2}
.\]
for any $N\in \NN$ and deduce that
\[
\sum_{n=1}^{\infty}\left|\left\langle x, u_{n}\right\rangle\right|^{2} \leq\|x\|_H^{2}
.\]

b. Let $\theset{a_n}_{n\in \NN} \in \ell^2(\NN)$ and prove that there exists an $x\in H$ such that $a_n = \inner{x}{u_n}$ for all $n\in \NN$, and moreover $x$ may be chosen such that 
\[
\norm{x}_H = \qty{ \sum_{n\in \NN} \abs{a_n}^2}^{1\over 2}
.\]

c. Prove that if $\theset{u_n}$ is *complete*, Bessel's inequality becomes an equality.

:::{.solution title="part b"}
\envlist

- Take $\theset{a_n} \in \ell^2$, then note that $\sum \abs{a_n}^2 < \infty \implies$ the tails vanish.

- Define $x \definedas \displaystyle\lim_{N\to\infty} S_N$ where $S_N = \sum_{k=1}^N a_k u_k$

- $\theset{S_N}$ is Cauchy and $H$ is complete, so $x\in H$.

- By construction, 
\[
\inner{x}{u_n} = \inner{\sum_k a_k u_k}{u_n} = \sum_k a_k \inner{u_k}{u_n} = a_n 
\]
since the $u_k$ are all orthogonal.

- By Pythagoras since the $u_k$ are normal,
\[
\norm{x}^2 = \norm{\sum_k a_k u_k}^2 = \sum_k \norm{a_k u_k}^2 = \sum_k \abs{a_k}^2
.\]

:::

:::{.solution title="part c"}
Let $x$ and $u_n$ be arbitrary. 

\[
\inner{x - \sum_{k=1}^\infty \inner{x}{u_k}u_k }{u_n}
&=
\inner{x}{u_n}
-
\inner{\sum_{k=1}^\infty \inner{x}{u_k}u_k }{u_n} \\
&=
\inner{x}{u_n}
-
\sum_{k=1}^\infty  \inner{\inner{x}{u_k}u_k }{u_n} \\
&=
\inner{x}{u_n}
-
\sum_{k=1}^\infty  \inner{x}{u_k} \inner{u_k }{u_n} \\
&= \inner{x}{u_n} - \inner{x}{u_n} = 0 \\
\implies 
x - \sum_{k=1}^\infty \inner{x}{u_k}u_k &= 0 \quad\text{by completeness}
.\]

So 
\[
x = \sum_{k=1}^\infty \inner{x}{u_k} u_k
\implies
\norm{x}^2 = \sum_{k=1}^\infty \abs{\inner{x}{u_k}}^2. \qed
.\]


:::

## Fall 2018 Practice Midterm 2.4 #real_analysis/qual/work

a. Prove Holder's inequality:
  let $f\in L^p, g\in L^q$ with $p, q$ conjugate, and show that
\[
\pnorm{fg}p \leq \pnorm{f}p \cdot \pnorm{g}q
.\]

b. Prove Minkowski's Inequality:
\[
1\leq p < \infty \implies \pnorm{f+g}{p} \leq \pnorm{f}{p}+ \pnorm{g}{p}
.\]
Conclude that if $f, g\in L^p(\RR^n)$ then so is $f+g$.

c. Let $X = [0, 1] \subset \RR$.

    1. Give a definition of the Banach space $L^\infty(X)$ of essentially bounded functions of $X$.

    2. Let $f$ be non-negative and measurable on $X$, prove that
    \[
    \int_X f(x)^p \,dx \converges{p\to\infty}\to
    \begin{dcases}
    \infty \quad\text{or} \\
    m\qty{\theset{f\inv(1)}}
    \end{dcases}
    ,\]
    and characterize the functions of each type


:::{.solution}
\[
\int f^p 
&= \int_{x < 1} f^p + \int_{x=1}f^p + \int_{x > 1} f^p\\
&= \int_{x < 1} f^p + \int_{x=1}1 + \int_{x > 1} f^p \\
&= \int_{x < 1} f^p + m(\theset{f = 1}) + \int_{x > 1} f^p \\
&\converges{p\to\infty}\to 0  + m(\theset{f = 1}) + 
\begin{cases} 
0 & m(\theset{x\geq 1}) = 0 \\ 
\infty & m(\theset{x\geq 1}) > 0.
\end{cases}
\] 

:::

## Fall 2018 Practice Midterm 2.5 #real_analysis/qual/work

Let $X$ be a normed vector space.

a. Give the definition of what it means for a map $L:X\to \CC$ to be a *linear functional*.

b. Define what it means for $L$ to be *bounded* and show $L$ is bounded $\iff L$ is continuous.

c. Prove that $(X\dual, \norm{\wait}_{\op})$ is a Banach space.

