# The mean value theorem

:::{.theorem title="Mean Value Property for Holomorphic Functions"}
If $f$ is holomorphic on $D_r(z_0)$ 
\[
f(z_0) 
= {1\over 2\pi} \int_0^{2\pi} f(z_0 + re^{i\theta}) \dtheta
= {1\over \pi r^2} \iint_{D_r(z_0)} f(z)\, dA
.\]
Taking the real part of both sides, one can replace $f=u+iv$ with $u$.
:::

:::{.proof title="?"}
\[
f\left(z_{0}\right)=\frac{1}{2 \pi i} \int_{\left|z-z_{0}\right|=r} \frac{f(z)}{z-z_{0}} d z=\frac{1}{2 \pi i} \int_{0}^{2 \pi} \frac{f\left(z_{0}+r e^{i \theta}\right)}{r e^{i \theta}} r i e^{i \theta} d \theta=\frac{1}{2 \pi} \int_{0}^{2 \pi} f\left(r e^{z_{0}+r i \theta}\right) d \theta,
.\]


:::

## Exercises

#todo
