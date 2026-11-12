---
type: definition
title: Definition (Gaussian factor dimension budget)
status: approved
source:
  kind: original
depends_on:
  - gaussian_multifactor_representation
  - gaussian_worst_case_bh_fdr
tags:
  - gaussian
  - multifactor
  - dimension_budget
  - uniform_fdr
definition_kind: definition
---

## Definition

Fix $q_0\in(0,1/2)$ and a deterministic function $D:(0,q_0)\to[1,\infty)$ with finite values. A [Gaussian multifactor representation](./gaussian_multifactor_representation.md) satisfies the factor dimension budget at level $q$ if its positive integer dimension obeys $1\leq d\leq\lfloor D(q)\rfloor$. Using the [uniform worst-case Gaussian BH false discovery rate](./gaussian_worst_case_bh_fdr.md) notation, define the restricted one-sided supremum
$$
F_{1,D}(q)=\sup_{\substack{m\geq1,\ 1\leq d\leq\lfloor D(q)\rfloor\\
\theta\in\mathbb R^m,\ a_1,\ldots,a_m\in\mathbb R^d,\ \|a_i\|\leq1}}
\operatorname{FDR}_{\mathrm{BH}}^{(1)}(q;m,\theta,\Sigma(A)).
$$
The supremum is taken separately at every level $q$ over all displayed means, loadings, numbers of tests, and dimensions. It includes all negative one-sided null means and zero residual variances. A model belongs to this class when it admits such a representation; no minimality of $d$ is required. All logarithms are natural logarithms. We use $\ell(q)=\log(1/q)$ for the logarithmic level, reserving the existing $L(q)$ for the scale $q\sqrt{\log(1/q)}$.
