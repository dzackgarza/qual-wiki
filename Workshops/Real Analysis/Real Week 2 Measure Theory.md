---
title: "Real Analysis Qual Prep Week 2: Measure Theory, Fubini Tonelli"
---

Tags: #qualifying_exam #active_projects #qual_real_analysis


# Study Guide

References: 

- Folland's "Real Analysis: Modern Techniques", Ch.1
- Stein and Shakarchi Ch.1, Ch.2

## Convergence Tips/Tricks

- Our favorite tools: **metrics** and **norms**!
	- ![](_attachments/Pasted image 20210528184220.png)
	- So show things are equal by showing $\abs{x-y} = 0$. Know the triangle inequality by heart!
- **Uniform convergence**:
	- ![](_attachments/Pasted image 20210528182641.png)
	- Negating: find a bad $\eps$ and a single bad point $x$.
	- Showing a sum converges uniformly: remember that $\sum_{k\geq 1} a_k$ is *defined* to be $\lim_{N\to\infty} \sum_{k\leq N} a_k$. So the trick is to define $f_n(x) := \sum_{k\leq n} a_k$ and then apply the usual criteria above.
	- It's sometimes useful to trade the $\forall x$ in the definition with $\sup_{x\in X} \abs{f_n(x) - f(x)} < \eps$ instead.
- Compare and contrast to **pointwise convergence**, which is strictly weaker:
	- ![](_attachments/Pasted image 20210528182925.png)
	- The main difference: pointwise can depend on the $x$ and the $\eps$, but uniform needs one $\eps$ that works for *all* $x$ simultaneously.
	- Note uniform implies pointwise but not conversely.
- The sup norm: $\norm{f}_\infty := \sup_{x\in X} \abs{f_n(x)}$
	- A useful way to force uniform convergence: bound your sequence uniformly by a sequence that goes to zero:
	- ![](_attachments/Pasted image 20210528183356.png)
- **Sups and infs**: sup is the least upper bound, inf is the greatest lower bound.
- The $p-$test: 
$$
\sum_{n\geq 1} {1 \over n^p} < \infty \iff p>1
$$
- Useful fact: convergent sums have **small tails**, i.e. 
$$
\sum_{n\geq 1} a_n < \infty \implies \lim_{N\to\infty}\sum_{n\geq N} a_n = 0
$$
- So try bounding things from above by the *tail* of a sum!
- If you can't bound by a tail: as long as you have control over the coefficients, you can pick them to make the sum to converge "fast enough".
	- Example: for a fixed $\eps$, choose $a_n = 1/2^n$. Note that $\sum_{n\geq 1} 1/2^n = 1$, so choose $a_n := \eps/2^n$:
$$
\cdots \leq \sum_{n\geq 1} a_n := \sum_{n\geq 1} {\eps \over 2^n} = \eps \to 0
$$
- The $\eps/3$ trick:
	- ![](_attachments/Pasted image 20210528183619.png)
- **The $M\dash$test**:
	- ![](_attachments/Pasted image 20210528183827.png)

## Measure Theory
-   $F_\sigma$ sets: unions of closed sets ($F$ for *fermi*, French for closed. Sigma for sums, ie unions)
-   $G_\delta$ sets: intersections of open sets
-   $\sigma$ algebras: closed under complements, countable intersections, countable unions
- Some of the most useful properties of measures:

![](_attachments/Pasted image 20210528184432.png)

![](_attachments/Pasted image 20210528184444.png)

![](_attachments/Pasted image 20210528184451.png)

- The proof of continuity of measure contains a very useful trick: replace a sequence of sets $\ts{E_k}$ with a sequence of *disjoint* sets that either union or intersect to the same thing.
	- Example: if $A_1 \subseteq A_2 \subseteq \cdots$, set $F_1=A_1$ and $F_k = A_k \sm A_{k-1}$ for $k\geq 2$. Then $\Union_{k\geq 1} A_k = \Disjoint_{k\geq 1} F_k$.
- Occasionally you need some properties of **outer measures**:

![](_attachments/Pasted image 20210528184814.png)

![](_attachments/Pasted image 20210528184827.png)

- Outer measure for $\RR^n$: you consider all collections of cubes that cover your set, sum up their volumes, and take the infimum over all such collections:

![](_attachments/Pasted image 20210528184951.png)

- "Almost everywhere *blah*" : the set where *blah* does not happen has measure zero.
- "Infinitely many/all but finitely many" types of sets, which show up in Borel-Cantelli style problems

![](_attachments/Pasted image 20210528183952.png)

![](_attachments/Pasted image 20210528184004.png)

- Lemmas that sometimes show up on quals:

![](_attachments/Pasted image 20210528185216.png)

![](_attachments/Pasted image 20210528185223.png)

## Fubini-Tonelli

Quick statement:

![](_attachments/Pasted image 20210528185415.png)


Explained in Stein and Shakarchi (Fubini, which requires **integrability**)

![](_attachments/Pasted image 20210528185725.png)

![](_attachments/Pasted image 20210528185759.png)

And Tonelli, which only requires **measurability**:

![](_attachments/Pasted image 20210528185956.png)

![](_attachments/Pasted image 20210528190018.png)


A more precise statement from Folland:

![](_attachments/Pasted image 20210528185618.png)

![](_attachments/Pasted image 20210528185433.png)


Some things that qual questions are commonly based on:

![](_attachments/Pasted image 20210528190107.png)

![](_attachments/Pasted image 20210528190142.png)

![](_attachments/Pasted image 20210528190207.png)

# Qual Problems

> Suggested by Peter Woolfitt!

Spring 2012

![](_attachments/Pasted image 20210528180450.png)

Fall 2016.2

![](_attachments/Pasted image 20210528181507.png)

Fall 2018.5

![](_attachments/Pasted image 20210528181558.png)

 Spring 2019.4: This is an expanded version of Fall 2018 #5 above.

![](_attachments/Pasted image 20210528181615.png)


