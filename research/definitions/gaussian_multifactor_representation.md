---
type: definition
title: Definition (Gaussian multifactor representation)
status: approved
source:
  kind: original
depends_on:
  - gaussian_multiple_testing_model
tags:
  - gaussian
  - multifactor
  - conditional_independence
---

## Definition

For positive integers $m,d$, deterministic means $\theta\in\mathbb R^m$, and deterministic loading vectors $a_i\in\mathbb R^d$ with $\|a_i\|\leq1$, a Gaussian multifactor representation is
$$
T_i=\theta_i+a_i^{\mathsf T}Z+\sqrt{1-\|a_i\|^2}\,\varepsilon_i,\qquad 1\leq i\leq m,
$$
where $Z\sim\mathcal N_d(0,I_d)$ and $\varepsilon_1,\ldots,\varepsilon_m\sim\mathcal N(0,1)$ are mutually independent. Here $I_d$ is the $d\times d$ identity matrix, $\|\cdot\|$ is the Euclidean norm, and $a_i^{\mathsf T}Z$ is the Euclidean inner product. Write $A$ for the $m\times d$ matrix with rows $a_i^{\mathsf T}$ and
$$
\Sigma(A)=AA^{\mathsf T}+\operatorname{diag}(1-\|a_1\|^2,\ldots,1-\|a_m\|^2).
$$
This is a [Gaussian multiple-testing model](./gaussian_multiple_testing_model.md) with $N=m$ and unit marginal variances. Given $Z$, the coordinates are independent; a coordinate with $\|a_i\|=1$ is conditionally deterministic. Zero loadings, loadings of either orientation, singular covariance matrices, and arbitrary means are allowed. The positive integer $d$ is the dimension of this representation, rather than a claim that it is the smallest possible factor dimension.
