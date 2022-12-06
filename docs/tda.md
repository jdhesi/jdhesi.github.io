---
layout: page
title: Topological Data Analysis
nameof: false
permalink: /projects/tdaproject
katex: True
---

# Topological Data Analysis

Topological data analysis is a field at the intersection of algebraic topology and data science. It is used to study the shape of data and can identify patterns that may not be easily seen using traditional ML methods. The features derived using algebraic topology are interporable and therefore this method may be an alternative to some black box methods when spatial distibutions are of key importance.

In our report we use topological data analysis methods to analyse spatial data simulated by an agent based model of the interaction between the immune system and a tumour. The abstract is stated below.

***Abstract***
*In the immune response to a tumour, specialised white blood cells called macrophages are released by blood vessels to attack and destroy the tumour. Environmental cues in the tumour microenvironment may alter the behaviour of macrophages causing them to enact pro-tumour tendencies, promoting the growth and spreading of the tumour. This heterogeneity in the macrophage population gives rise to complex spatial patterns. We employ methods from topological data analysis (TDA) to determine the concentration of pro-tumour macrophages, given only dynamic spatial data of the involved cells from an agent-based model. Moreover, we use machine learning methods to predict the future concentration of pro-tumour macrophages given spatial data at an earlier time.*

In our analysis of the topological features that we derive for our point cloud data set, we perform both a binary classification task and a regression task. For our binary classification, we use a Support-vector Machine (SVM) which finds the best seperating hyperplane of our two classes. For our regression task we use a basic feedforward neural network, a multilayer perceptron (MLP), which makes use of the backpropogation algorithm. To visualise our high dimensional feature vectors, we make use of multidimensional scaling (MDS). This dimensionality reduction method preserves distances (Euclidean in our case) between feature vectors in the resulting projection. 

We find that the topological features accurately predict the dominant macrophage phenotype in these simulations, and in particular it improves the benchmark classification accuracy set by more standard statistics. Moreover, the interperobility of the topological features further justify the use of TDA for this data set. 


## [View Project](https://jdhesi.github.io/pdfs/TDA_dissertation_dhesi.pdf)
