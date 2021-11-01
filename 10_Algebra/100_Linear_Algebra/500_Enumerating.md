# Enumerating

:::{.proposition title="Size of $\GL_n(\FF_p)$"}
\[
\abs{\GL_n(\FF_p)} = (p^n-1)(p^n-p)(p^n-p^2)\cdots(p^n - p^{n-1})
.\]

It suffices to count ordered bases of $\FF_p^n$:

- Choose $\vector v_1$: there are $p$ choices for each coefficient, but leave out the vector $0$, so $p^n-1$ choices.
- Choose any $\vector v_2 \neq \lambda \vector v_1$, so $p^n-p$ choices.
- Choose any nonzero $\vector v_3 \neq \lambda \vector v_1 + \eta \vector v_2$, so $p^n-p^2$ choices.
- Etc.

:::
