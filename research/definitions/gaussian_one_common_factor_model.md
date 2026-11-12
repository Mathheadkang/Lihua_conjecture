---
type: definition
title: Definition (one-common-factor Gaussian testing model)
status: approved
source:
  kind: paper
  paper_id: lei2026_gaussian_bh
  location: 'Section 4.1, equation (189), p. 59'
depends_on:
  - gaussian_multiple_testing_model
  - gaussian_worst_case_bh_fdr
tags:
  - gaussian
  - one_common_factor
  - paper_source
---

## Definition

For a positive integer $m$, a deterministic mean vector $\theta\in\mathbb R^m$ and scalar loadings $a=(a_1,\ldots,a_m)\in[-1,1]^m$, the one-common-factor Gaussian testing model is
$$
T_i=\theta_i+a_iZ+\sqrt{1-a_i^2}\,\varepsilon_i,\qquad 1\leq i\leq m,
$$
where $Z,\varepsilon_1,\ldots,\varepsilon_m$ are independent standard normal random variables. Its covariance is
$$
\Sigma(a)=aa^{\mathsf T}+\operatorname{diag}(1-a_1^2,\ldots,1-a_m^2).
$$
Thus it is a [Gaussian multiple-testing model](gaussian_multiple_testing_model.md); the coordinates are conditionally independent given the scalar factor $Z$. Loadings of either sign and residual variances equal to zero are allowed.

Using the two testing tracks and FDR notation in the [uniform worst-case Gaussian BH false discovery rate](gaussian_worst_case_bh_fdr.md), define the restricted supremum
$$
F_{s,\mathrm{cf}}(q)=\sup_{m\geq1,\ \theta\in\mathbb R^m,\ a\in[-1,1]^m}\operatorname{FDR}_{\mathrm{BH}}^{(s)}(q;m,\theta,\Sigma(a)),\qquad s\in\{1,2\}.
$$
The notation $F_{s,\mathrm{cf}}$ is local to these extracted nodes. It distinguishes the source's restricted class from its unrestricted Gaussian conjecture.
