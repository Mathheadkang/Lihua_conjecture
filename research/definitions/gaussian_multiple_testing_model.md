---
type: definition
title: Definition (Gaussian multiple-testing model)
status: approved
source:
  kind: original
depends_on: []
tags:
  - gaussian
  - model
  - unrestricted
---

## Definition

For a positive integer $N$, put $[N]=\{1,\ldots,N\}$ and let
$$
\mathcal C_N=\{\Sigma\in\mathbb R^{N\times N}:\Sigma=\Sigma^{\mathsf T},\ x^{\mathsf T}\Sigma x\geq0\text{ for every }x\in\mathbb R^N,\ \Sigma_{ii}=1\text{ for every }i\in[N]\}.
$$
An admissible Gaussian multiple-testing model is a triple $(N,\theta,\Sigma)$ with $\theta\in\mathbb R^N$ and $\Sigma\in\mathcal C_N$, together with an observation $T=(T_1,\ldots,T_N)\sim\mathcal N_N(\theta,\Sigma)$. Joint Gaussianity means that $a^{\mathsf T}(T-\theta)$ has the centered normal distribution with variance $a^{\mathsf T}\Sigma a$ for every $a\in\mathbb R^N$; variance zero denotes the constant zero. Singular covariance matrices are admissible. The notation $\mathbb E_{N,\theta,\Sigma}$ denotes expectation under this law.

Uniform assertions allow $N$, $\theta$, and $\Sigma$ to depend arbitrarily on the testing level $q\in(0,1)$; no bound on dimension, means, correlations, or null proportion is imposed beyond these conditions.
