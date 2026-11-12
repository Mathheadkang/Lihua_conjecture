---
type: theorem
title: Lei finite Gaussian lower bound for two-sided BH
status: draft
source:
  kind: paper
  paper_id: lei2026_gaussian_bh
  location: Theorem 2.1 and Proposition 2.2, p. 5; Proposition 2.3, p. 6; proofs in Section 2.7, pp. 40-42
depends_on: []
uses_definitions: [gaussian_multiple_testing_model, gaussian_test_pvalues, benjamini_hochberg_step_up, false_discovery_rate, gaussian_worst_case_bh_fdr, gaussian_one_common_factor_model, lei2026_gaussian_lower_envelopes]
tags: [gaussian, benjamini_hochberg, two_sided, lower_bounds, paper_source]
---

## Statement

Use the [Lei Gaussian BH lower-bound envelopes](../definitions/lei2026_gaussian_lower_envelopes.md). For every $q\in(0,1)$ and $\delta>0$, there is a finite [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md) $(N,\theta,\Sigma)$ with a positive definite correlation matrix such that the [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md), applied to the two-sided [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md), satisfies
$$
\operatorname{FDR}_{\mathrm{BH}}^{(2)}(q;N,\theta,\Sigma)>\ell_{=}(q)-\delta.
$$
Consequently the [uniform worst-case Gaussian BH false discovery rate](../definitions/gaussian_worst_case_bh_fdr.md) satisfies $F_2(q)\geq\ell_{=}(q)>q$, and
$$
\ell_{=}(q)=\frac{q\sqrt{\log(1/q)}}{2\sqrt\pi}+c_\ell q+o(q),\qquad q\downarrow0,
$$
where
$$
c_\ell=\Phi(1)-\frac1{2\sqrt{2\pi}}+\int_1^\infty\left(M(y)\phi(y)-\frac1{2\sqrt{2\pi}}\right)dy=0.6492828\ldots.
$$

## Source proof route

This is a paraphrase of the cited results, with a source-based proof summary. The source uses a [one-common-factor Gaussian testing model](../definitions/gaussian_one_common_factor_model.md) with a null block of loading $r$, a primary non-null block and a continuum of secondary non-nulls of loading $1$. A compact-uniform first-crossing argument, conditional empirical-CDF concentration, averaging over random finite designs and then a small independent Gaussian perturbation give a deterministic finite positive definite example. The perturbation remains in the one-common-factor class. Therefore the construction also gives $F_{2,\mathrm{cf}}(q)\geq\ell_{=}(q)$.

The limiting conditional [false discovery rate](../definitions/false_discovery_rate.md) integrand is $q$ for $z>-1$, $qM(-z)$ for $-y_q<z<-1$ and $1$ for $z<-y_q$. Its expectation is $\ell_{=}(q)$. This is a source claim awaiting citation approval and independent verification, not a newly audited proof.
