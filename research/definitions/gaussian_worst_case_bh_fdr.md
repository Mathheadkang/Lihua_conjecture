---
type: definition
title: Definition (uniform worst-case Gaussian BH false discovery rate)
status: approved
source:
  kind: original
depends_on:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
tags:
  - gaussian
  - benjamini_hochberg
  - fdr
  - uniform_asymptotics
---

## Definition

For an admissible [Gaussian multiple-testing model](gaussian_multiple_testing_model.md), a track $s\in\{1,2\}$ with its [Gaussian test p-values and true nulls](gaussian_test_pvalues.md), and $q\in(0,1)$, apply the [ordinary Benjamini-Hochberg step-up procedure](benjamini_hochberg_step_up.md) to $p^{(s)}$. Put
$$
\mathcal R_q^{(s)}=\mathcal R_q(p^{(s)}),\qquad R_q^{(s)}=|\mathcal R_q^{(s)}|,\qquad V_q^{(s)}=|\mathcal R_q^{(s)}\cap I_0^{(s)}(\theta)|.
$$
Its [false discovery rate](false_discovery_rate.md) and its worst-case value at level $q$ are
$$
\operatorname{FDR}_{\mathrm{BH}}^{(s)}(q;N,\theta,\Sigma)=\mathbb E_{N,\theta,\Sigma}\!\left[\frac{V_q^{(s)}}{R_q^{(s)}\vee1}\right],
$$
$$
F_s(q)=\sup_{N\in\{1,2,\ldots\}}\ \sup_{\theta\in\mathbb R^N}\ \sup_{\Sigma\in\mathcal C_N}\operatorname{FDR}_{\mathrm{BH}}^{(s)}(q;N,\theta,\Sigma).
$$
The supremum is taken separately at every $q$, so the optimizing dimension, mean vector, covariance, and null proportion may vary with $q$. It includes singular matrices and, when $s=1$, negative true-null means. Define the asymptotic scale
$$
L(q)=q\sqrt{\log(1/q)},\qquad 0<q<1,
$$
where $\log$ is the natural logarithm. The notation $\limsup_{q\downarrow0}$ is the upper limit over all real levels tending to zero through $(0,1)$.
