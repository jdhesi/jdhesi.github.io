---
layout: page
title: Linear Algebra
nameof: false
permalink: /projects/cppproject
katex: True
---

# Implementing Linear Algebra Algorithms in C++ ([View PDF](https://jdhesi.github.io/pdfs/NLA_in_CPP.pdf))

Matlab is a very convinient language for scientists; what it lacks in speed it makes up with exceptionally easy matrix manipulation and a simple user experience. In this project we task ourselves with recreating some of the robust functionality that makes Matlab easy to use in a lower level programming language, C++.

To acheive a robust basic functionality we overload the standard binary $$+,-, *$$ and unary $$-$$ operators to allow for matrix and vector inputs. We also allow for linear systems to be solved by overloading the $$\backslash$$ operator, so that $$A\mathbf{x}=\mathbf{b} \implies \mathbf{x} = A^{-1}\mathbf{b}$$. We implement Gaussian elimination with partial pivoting for this operator (and thus we implicitly implement $$LU$$ decomposition). Gaussian elimination is a direct algorithm which obtains an exact solution to a linear system, however its $$\sim \mathcal{O(n^3)}$$ time complexity can be improved on by iterative, inexact methods. 

The Generalised Minimimal Residual Method (GMRES) is an iterative method which approximates the solution to $$A\mathbf{x}=\mathbf{b}$$ in a Krylov subspace, 

$$
K_n= \text{span}\{\mathbf{b}-A\mathbf{x}_0, A(\mathbf{b}-A\mathbf{x}_0),A^2(\mathbf{b}-A\mathbf{x}_0), \\ \ldots, A^{n-1}(\mathbf{b}-A\mathbf{x})\}
$$

for some initial guess, $$\mathbf{x}_0$$ of the solution. It provides an accurate approximation to the solution in at most $$m$$ iterations for matrices of size $$m \times m$$, with a general time complexity of $$\sim \mathcal{O}(m^2)$$, improving to $$\sim \mathcal{O}(m)$$ for some special sparse matrices. We implement GMRES as an alternative linear system solver, to allow for robustness in the case of larger matrix inputs.

We verify our implementations of Gaussian elimination and GMRES by using the finite element method to numerically solve 

$$
\begin{aligned}
-\Delta u &= f \quad \text{in} \,\, \Omega \\
u &= 0 \quad \text{on} \, \, \partial \Omega.
\end{aligned}
$$

Beyond solving linear systems, finding eigenvalues is a particularly important task, and one that Matlab can easily solve using $$\text{eig}(A)$$. We implement similar functionality, using the famous QR-algorithm which relies on repeatedly taking $$QR$$ decompositions. We verify our implementation by finding eigenvalues $$\lambda_n$$ that satisfy

$$
\begin{aligned}
-u''(x) + c(x)u(x) = \lambda u(x) \\
u(a) = u(b) = 0
\end{aligned}
$$

for $$x \in [a,b]$$. 


