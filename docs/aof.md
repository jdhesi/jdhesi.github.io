---
layout: page
title: Approximation Theory
nameof: false
permalink: /projects/aofproject
katex: True
---

## Convergence Rates of Chebyshev Approximation
Chebyshev approximation is a method of approximation functions using Chebyshev polynomials. These are polynomials of the form 

$$
T_n(\cos{\theta}) = \cos{n  \theta}.
$$

Alternatively, these can be defined by the recurrence relation $$T_0(x) = 1$$, $$\, T_1(x) = x$$, $$\, T_{n+1}(x)= 2xT_n(x) - T_{n-1}(x)$$. For a general Lipschitz function $$f(x)$$ defined on $$[-1,1]$$, we know it can be written 

$$
f(x) = \sum_{k=0}^{\infty}a_k \, T_k(x)
$$

for Chebyshev coefficients  

$$
a_k = \frac{2}{\pi}\int_{-1}^{1}\frac{f(x) \, T_k(x)}{\sqrt{1-x^2}}\, \mathrm{d}x.
$$

Therefore, a natural option for approximating $$f$$ is to truncate our infinite series at some finite $$n$$. This is known as Chebyshev projection. It is sometimes unfavourable to compute these complicated coefficients for approximation, and we could also use a method of approximation called Chebyshev interpolation. This method avoids computing these integrals by employing an aliasing formula to compute alternative coefficients that can be done quickly by the Fast Fourier Transform. 

We in investigate the convergence of these different approximation methods to the true value for functions $$f$$ of different smoothness.

When $$f(x) \in C^{\nu}([-1,1])$$ for $$\nu \in \mathbb{Z}$$, i.e. when $$f$$ is $$\nu$$ times continuously differentiable functions, Chebyshev approximation can be proven to have algebraic convergence, that is $$\mathcal{O}(n^{-\nu})$$.

When $$f(x) \in C^\infty([-1,1])$$ and $$f(x)$$ is $$\underline{\text{analytic}}$$ on $$[-1,1]$$, Chebysehv approximation can be proven to have geometric convergence, that is $$\mathcal{O}(\rho^{-n})$$ for a constant $$\rho$$ related to the region of analyticity of $$f$$. Entire functions are therefore a best case scenario in terms of convergence rates by Chebyshev approximation. 

There is however, an in between degree of smoothness between these two above cases. Consider a function which is infinitely differentiable, yet nowhere analytic. An example of such a function is the following given by *Cellèrier* in 1890:

$$
f(x) = \sum_{n=1}^{\infty} \frac{\sin{a^nx}}{n!}
$$

for $$a>1$$. We consider a range of general $$C^{\infty}$$ nowhere analytic functions in this report and conclude that they exhibit root exponential convergence when approximated by Chebyshev polynomials. That is $$\mathcal{O}(c_1^{-n^{c_2}})$$ for $$c_1>1$$ and $$0<c_2<1$$. 
