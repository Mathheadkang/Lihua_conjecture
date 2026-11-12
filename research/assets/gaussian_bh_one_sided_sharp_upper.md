---
type: theorem
title: Sharp uniform upper-bound target for one-sided Gaussian BH
status: draft
source:
  kind: original
depends_on:
  - gaussian_bh_one_sided_free_central_window_core
  - gaussian_bh_radial_strip_refinement_defined_entropy
  - gaussian_simplex_factor_envelope_obstruction
  - gaussian_unit_variance_mixture_hugging_rigidity
  - gaussian_sibling_factor_bounds_and_critical_background_obstruction
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
  - gaussian_worst_case_bh_fdr
tags:
  - gaussian
  - benjamini_hochberg
  - one_sided
  - sharp_upper_bound
  - conjecture
---

## Statement

For the [uniform worst-case Gaussian BH false discovery rate](../definitions/gaussian_worst_case_bh_fdr.md), the proposed one-sided bound is
$$
\limsup_{q\downarrow0}\frac{F_1(q)}{q\sqrt{\log(1/q)}}\leq\frac{1}{\sqrt\pi}.
$$
Equivalently, for every $\varepsilon>0$ there is $q_\varepsilon\in(0,1)$ such that, for every $q\in(0,q_\varepsilon)$ and every admissible [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md) $(N,\theta,\Sigma)$,
$$
\operatorname{FDR}_{\mathrm{BH}}^{(1)}(q;N,\theta,\Sigma)\leq\left(\frac{1}{\sqrt\pi}+\varepsilon\right)q\sqrt{\log(1/q)}.
$$
Here the [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md) are $p_i^{(1)}=\overline\Phi(T_i)$ and $I_0^{(1)}(\theta)=\{i:\theta_i\leq0\}$, including every negative true-null mean; the [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md) and [false discovery rate](../definitions/false_discovery_rate.md) are used exactly as defined. The quantifiers allow arbitrary dependence of $N$, $\theta$, and $\Sigma$ on $q$, including singular positive-semidefinite unit-diagonal covariance matrices.

## Research status

This node records the conjectured unrestricted upper-bound target from the project specification. It supplies no proof or verification verdict. The proposed leading constant is a target, not a proved sharp constant.
