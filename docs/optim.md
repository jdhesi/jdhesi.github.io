---
layout: page
title: test
name: false
permalink: /projects/optimproject
katex: True
---

# Colour Recovery using Optimisation and Functional Analysis

Given a greyscale image of size $$L \times W = N$$, with colour information of a small number $$n << N$$ of pixels, can we accurately recover the full colour information of all grey pixels?

It turns out that this problem can be formulated using functional analysis, and subsequently solved using numerical optimisation techniques. 

Given the set of all pixels $$\Omega = \{z_1, \ldots , z_N\}$$ and a subset which have colour information $$D = \{x_1,\ldots,x_n\} \subset \Omega$$, having greyscale information at all pixels is equivalent to the existence of a map $$\gamma:\Omega \mapsto I = \{i \in \mathbb{\Z} : 0 \leq i \leq 255\}$$, where the value assigned to each pixel represents its greyscale intensity. In a similar fashion, pixels in the coloured set can be mapped to three colour channels representing their red, green and blue intensities, namely there exists the map $$f:D\mapsto I^3$$. Our objective is to accurately map pixels whose grey scale information is known; elements of $$\Omega$$, to RGB channels; elements of $$I^3$$. This can be done by finding $$F = (F^r, F^g, F^b) : \Omega \mapsto I^3$$ such that $$F\lvert_D \approx f_D$$ (so that known colour information is retained).

# Reproducing Kernel Hilbert Spaces

A Hilbert space is an inner product space with the special property that the completeness is ensured in the inner-product induced norm. Reproducing Kernel Hilbert Spaces (RKHS) are a special case of Hilbert space which is defined by a Kernel $$K(x,y)$$;

$$
\mathcal{H}_k = \text{cl}\left( \{\sum_{i=1}^{n} K(x,x_i) \, a_i :n \in \mathbb{N} \} \right)
$$

for real coefficients $$a_i$$, and elements $$x, x_i$$ defined on the domain of the Kernel. Moreover, the span of the Kernel must be dense inside the space and the defining property, $$f(x) = \langle f,K \rangle_{\mathcal{H}_k}$$ must be satisfied. Here $$\langle \cdot,\cdot \rangle_{\mathcal{H}_k}$$ is the inner product norm of the Hilbert space. 

# RKHS Solution
We assume solutions $$F^s$$ (where $$s = r,g,b$$) exists in some RKHS; $$F^s \in \mathcal{H}_K$$, and therefore express solutions as

$$
F^s = \sum_{j=1}^N K(x,x_j)a_j^s
$$

where we can now choose an approriate Kernel, and thus finding coefficients $$a_j^s$$ for each $$s$$ would yield a solution. It turns out that this is equivalent to solving the linear system 

$$
(K_D+\delta NI)a^s = f^s
$$

for the identity matrix $$I$$, and a real parameter $$\delta$$, whose value will impact the 'accuracy' of the solution. In our report we show the detailed derivation of this linear system, and the impact of chaning parameters and Kernel functions on the recoloured image. 