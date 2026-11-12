---
type: theorem
title: Lei finite Gaussian lower bound for one-sided BH
status: approved
source:
  kind: paper
  paper_id: lei2026_gaussian_bh
  location: >-
    Theorem 3.1 and Propositions 3.2-3.3, p. 43; construction in Section 3.3,
    pp. 44-45; proofs in Section 3.5, pp. 57-58
depends_on: []
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
  - gaussian_worst_case_bh_fdr
  - gaussian_one_common_factor_model
  - lei2026_gaussian_lower_envelopes
tags:
  - gaussian
  - benjamini_hochberg
  - one_sided
  - lower_bounds
  - paper_source
---

## Statement

Use the [Lei Gaussian BH lower-bound envelopes](../definitions/lei2026_gaussian_lower_envelopes.md). For every $q\in(0,1)$ and $\delta>0$, there is a finite [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md) $(N,\theta,\Sigma)$ with a positive definite correlation matrix such that the [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md), applied to the one-sided [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md), satisfies
$$
\operatorname{FDR}_{\mathrm{BH}}^{(1)}(q;N,\theta,\Sigma)>\ell_{\leq}(q)-\delta.
$$
Every true null in this construction has $\theta_i=0$, and every non-null has $\theta_i>0$. Consequently the composite-null [uniform worst-case Gaussian BH false discovery rate](../definitions/gaussian_worst_case_bh_fdr.md) satisfies $F_1(q)\geq\ell_{\leq}(q)>q$, with
$$
\ell_{\leq}(q)=\frac{q\sqrt{\log(1/q)}}{\sqrt\pi}+\frac q2+o(q),\qquad q\downarrow0.
$$
The true-null convention remains $\{i:\theta_i\leq0\}$; the source only chooses its examples on the boundary.

## Source proof route

This is a paraphrase of the cited results. The source uses a [one-common-factor Gaussian testing model](../definitions/gaussian_one_common_factor_model.md) with null loading $r>0$ and non-null loading $-1$. A three-component design produces a conditional false discovery proportion tending to $q$ for $z<0$, $qe^{z^2/2}$ for $0<z<y_q^+$ and $1$ for $z>y_q^+$. Averaging these values gives $\ell_{\leq}(q)$. Finite-dimensional transfer and the independent perturbation preserve the means, null labels and covariance sign pattern; the perturbed example remains in the common-factor class, so $F_{1,\mathrm{cf}}(q)\geq\ell_{\leq}(q)$.

Null-null covariances are positive and null-to-non-null covariances negative in this construction. The node records the paper's claimed [false discovery rate](../definitions/false_discovery_rate.md) lower bound, with no independent proof verdict.
