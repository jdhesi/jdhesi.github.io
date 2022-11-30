---
layout: page
title: Statistical Modelling
nameof: false
permalink: /projects/smproject
katex: True
---


# Stochastic Models of Higher Order Interactions in Epidemics
Epidimiological models have been of unprecedented importance in the past few years. SIR models have been used to predict the dynamics of the numbers of susceptible (S), infected (I) and recovered/removed (R) parties in a population of size $$N$$, given a rate of infection $$\beta$$, and rate of removal $$\mu$$. One can consider the population as an ensemble of nodes, in which infections have a probability of occuring when an infectious node is connected by an edge to a susceptible node. 

### FIGURE HERE

With some basic assumptions such as a well mixed homogeneous population, it is not difficult to arrive at the deterministic system for the time evolution of each of our classes; 

$$
\begin{aligned}
	 \frac{dS(t)}{dt} &= -\beta S(t) I(t)\\
	 \frac{dI(t)}{dt} &= \beta S(t) I(t) - \mu I(t) \\
	\frac{dR(t)}{dt} &= \mu I(t)
\end{aligned}
$$

where we prescribe initial conditions $$I(0) = I_0$$, $$S(0) = 1-I_0$$, $$R(0) = R_0$$. This simple network based dynamical system captures the major events in the event of an epidemic outbreak. The potential shortcoming, however, is in capturing group interactions. Since the model built on a standard network (consiting of only nodes and edges), only pairwise interactions between nodes are included. A concrete example of where pairwise interactions are insufficient is in the case of the spreading of a general contagion in a population. Say the contagion is a rumour. This is much more likely to be 'spread' to a susceptible person if it is coming from a group of people rather than an individual. 

We can extend the model to include group interactions by considering dynamics on a higher dimensional analogue of a network. Hypergraphs offer a natural generalisation of networks to higher dimensions and the use of these is considered heavily in the literature. Instead we consider SIR dynamics on simplicial complexes, which offer a generalisation by including nodes, edges, triangles, tetrahedra and higher order affine hulls. The dynamics described by the above equations become significantly more complicated when considering these extra dimensions on a simplicial complex $$\mathcal{X}$$. 

$$
\begin{aligned}
	 \frac{dS(t)}{dt} &=  - S(t) \sum_{d=1}^{D} \mu_d \sum_{i,j_1, \dots, j_d \in \mathcal{X}} a_{i,j_1, \dots, j_d} \, \prod_{k=1}^{d} I(t)\\
	 \frac{dI(t)}{dt} &= -\gamma I(t) + S(t) \sum_{d=1}^D \mu_d \sum_{i,j_1, \dots, j_d \in \mathcal{X}} a_{i,j_1, \dots, j_d} \, \prod_{k=1}^{d} I(t)\\
	\frac{dR(t)}{dt} &= \gamma I(t)
\end{aligned}
$$

In this report we introduce simplicial complexes, and how we can build stochastic models on them. We then consider the SIR dynamics of our simplicial models to showcase the relevence of higher order interactions in contagion spreading. 