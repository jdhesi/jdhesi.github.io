---
layout: page
title: Neuronal Growth
nameof: false
permalink: /projects/mbproject
katex: True
---

# Modelling Axonal Growth

Though key to understanding how neural networks form and evolve, neuronal growth is a poorly understood process. In the early stages of morphogenesis a neuronal cell consists of the main cell body, known as the soma, and a multitude of protruding dendrites. Eventually, a single dendrite referred to as the axon outgrows the rest.

The protein tubulin is created in its soluble form within the soma, and exists in its polymerised form as the main constituent of the cytoskeleton of the axon. Referred to as microtubules, these cross-linked chains
of solid, polymerised tubulin are what give the axonal shaft its structural integrity.

There are two main approaches used in the literature to model how an axon grows: transport mediated growth and mechanically mediated growth.

# Transport Mediated Growth
Let $$c(x,t)$$ denote the concentration of tubulin along the extent of the axon. Then, the continuity equation

$$
\frac{\partial c}{\partial t}(x,t) + \frac{\partial J}{\partial x}(x,t) = S(x,t)
$$ 

describes the conservation of tubulin. Here, $$J$$ denotes the flux of tubulin and $$S$$ denotes a general sink term. This theory of growth is defined by the choice of flux as the sum of diffusion (passive) and active transport terms:

$$
J(x,t) = \underbrace{-D\frac{\partial c}{\partial t}(x,t)}_{\text{diffusion}} + \underbrace{ac(x,t)}_{\text{active transport}}.
$$

Our PDE is first order in space and time, and thus we also apply an initial and boundary condition. We apply a range of different initial tubulin concentration profiles in our report. Furthermore, we apply a distal moving boundary condition, from which we can derive the rate of growth of the axon.

# Mechanically Mediated Growth
This theory investigates the effects of a towing force $$F_0$$ at the distal boundary of the axon, with friction opposing the induced motion. What results is a force profile along the axon, and thus implying growth at each point along the axon, rather than just at the tip as assumed by the transport limited model. We can derive the force profile

$$
f(x,l(t)) = F_0 \frac{\cosh(x(\eta/G)^{1/2})}{\cosh(l(t)(\eta/G)^{1/2})}
$$

where $$l(t)$$ describes the length of the axon at time $$t$$, and $$\eta$$ and $$G$$ are physical constants.

# Coupling Tubulin Transport and Mechanical Forces
In this report, we couple the above models into a single model which considers the elongation of the axon due to the dynamics of tubulin inside the axon as well as the mechanical forces arising due to the environment. We provide analytic solutions for simplified cases and numerical solutions for the full PDE arising from this coupling. We show that our model agrees with each of the previous two theories when regarded in their specific regimes. 